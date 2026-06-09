# NCryptStreamClose

- ea: `0x1800160b0`
- end: `0x18001611f`
- name: `NCryptStreamClose`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d02c`
- `0x1800160b0`
- `0x180016128`

## string_xrefs

- `0x1800160e6`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`

## pseudocode

```c
__int64 __fastcall NCryptStreamClose(_QWORD *a1, int a2, int a3)
{
  unsigned int v3; // ebx

  if ( a1 && *a1 == 192 )
  {
    I_StreamFree(a1);
    return 0;
  }
  else
  {
    v3 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c",
        104);
  }
  return v3;
}

```

## disassembly

```asm
0x1800160b0  push    rbx
0x1800160b2  sub     rsp, 40h
0x1800160b6  test    rcx, rcx
0x1800160b9  jz      short loc_1800160C4
0x1800160bb  cmp     qword ptr [rcx], 0C0h
0x1800160c2  jz      short loc_180016116
0x1800160c4  mov     ebx, 80090026h
0x1800160c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160d0  lea     rax, WPP_GLOBAL_Control
0x1800160d7  cmp     rcx, rax
0x1800160da  jz      short loc_18001610E
0x1800160dc  test    byte ptr [rcx+1Ch], 1
0x1800160e0  jz      short loc_18001610E
0x1800160e2  mov     rcx, [rcx+10h]
0x1800160e6  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800160ed  mov     [rsp+48h+var_18], 368h
0x1800160f5  lea     r9, aStatus; "Status"
0x1800160fc  mov     [rsp+48h+var_20], rax
0x180016101  mov     [rsp+48h+var_28], 80090026h
0x180016109  call    WPP_SF_sDsd
0x18001610e  mov     eax, ebx
0x180016110  add     rsp, 40h
0x180016114  pop     rbx
0x180016115  retn
0x180016116  call    I_StreamFree
0x18001611b  xor     ebx, ebx
0x18001611d  jmp     short loc_18001610E
```
