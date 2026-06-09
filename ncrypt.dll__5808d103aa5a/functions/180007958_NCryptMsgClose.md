# NCryptMsgClose

- ea: `0x180007958`
- end: `0x1800079c6`
- name: `NCryptMsgClose`
- size: `110`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800053ac`
- `0x180006090`
- `0x180007ae0`
- `0x180016128`

## callees

- `0x180004a70`
- `0x180007958`
- `0x18000d02c`

## string_xrefs

- `0x18000798d`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`

## pseudocode

```c
__int64 __fastcall NCryptMsgClose(_DWORD *a1, int a2, int a3)
{
  unsigned int v3; // ebx

  if ( a1 && *a1 == 368 )
  {
    I_CMsgFree(a1);
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
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
        159);
  }
  return v3;
}

```

## disassembly

```asm
0x180007958  push    rbx
0x18000795a  sub     rsp, 40h
0x18000795e  test    rcx, rcx
0x180007961  jz      short loc_18000796B
0x180007963  cmp     dword ptr [rcx], 170h
0x180007969  jz      short loc_1800079BD
0x18000796b  mov     ebx, 80090026h
0x180007970  mov     rcx, cs:WPP_GLOBAL_Control
0x180007977  lea     rax, WPP_GLOBAL_Control
0x18000797e  cmp     rcx, rax
0x180007981  jz      short loc_1800079B5
0x180007983  test    byte ptr [rcx+1Ch], 1
0x180007987  jz      short loc_1800079B5
0x180007989  mov     rcx, [rcx+10h]
0x18000798d  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007994  mov     [rsp+48h+var_18], 9Fh
0x18000799c  lea     r9, aStatus; "Status"
0x1800079a3  mov     [rsp+48h+var_20], rax
0x1800079a8  mov     [rsp+48h+var_28], 80090026h
0x1800079b0  call    WPP_SF_sDsd
0x1800079b5  mov     eax, ebx
0x1800079b7  add     rsp, 40h
0x1800079bb  pop     rbx
0x1800079bc  retn
0x1800079bd  call    I_CMsgFree
0x1800079c2  xor     ebx, ebx
0x1800079c4  jmp     short loc_1800079B5
```
