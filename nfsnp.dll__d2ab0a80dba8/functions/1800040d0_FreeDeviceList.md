# FreeDeviceList

- ea: `0x1800040d0`
- end: `0x180004170`
- name: `FreeDeviceList`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004178`
- `0x180009f04`

## callees

- `0x1800023f0`
- `0x1800040d0`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x180004127`
- `KERNEL32!GlobalFree` at `0x180004127`

## pseudocode

```c
int __fastcall FreeDeviceList(__int64 a1)
{
  _UNKNOWN **v2; // rcx
  _QWORD *v3; // rax
  _QWORD *v4; // rbx

  v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x10u, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  v3 = *(_QWORD **)(a1 + 72);
  if ( v3 )
  {
    do
    {
      v4 = (_QWORD *)v3[2];
      GlobalFree(v3);
      *(_QWORD *)(a1 + 72) = v4;
      v3 = v4;
    }
    while ( v4 );
    v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
    LODWORD(v3) = WPP_SF_((TRACEHANDLE)v2[2], 0x11u, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
  return (int)v3;
}

```

## disassembly

```asm
0x1800040d0  mov     [rsp+arg_0], rbx
0x1800040d5  mov     [rsp+arg_8], rsi
0x1800040da  push    rdi
0x1800040db  sub     rsp, 20h
0x1800040df  mov     rdi, rcx
0x1800040e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040e9  lea     rsi, WPP_GLOBAL_Control
0x1800040f0  cmp     rcx, rsi
0x1800040f3  jz      short loc_180004117
0x1800040f5  test    byte ptr [rcx+1Ch], 1
0x1800040f9  jz      short loc_180004117
0x1800040fb  mov     rcx, [rcx+10h]
0x1800040ff  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004106  mov     edx, 10h
0x18000410b  call    WPP_SF_
0x180004110  mov     rcx, cs:WPP_GLOBAL_Control
0x180004117  mov     rax, [rdi+48h]
0x18000411b  test    rax, rax
0x18000411e  jz      short loc_180004140
0x180004120  mov     rbx, [rax+10h]
0x180004124  mov     rcx, rax; hMem
0x180004127  call    cs:__imp_GlobalFree
0x18000412d  mov     [rdi+48h], rbx
0x180004131  mov     rax, rbx
0x180004134  test    rbx, rbx
0x180004137  jnz     short loc_180004120
0x180004139  mov     rcx, cs:WPP_GLOBAL_Control
0x180004140  cmp     rcx, rsi
0x180004143  jz      short loc_180004160
0x180004145  test    byte ptr [rcx+1Ch], 1
0x180004149  jz      short loc_180004160
0x18000414b  mov     rcx, [rcx+10h]
0x18000414f  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004156  mov     edx, 11h
0x18000415b  call    WPP_SF_
0x180004160  mov     rbx, [rsp+28h+arg_0]
0x180004165  mov     rsi, [rsp+28h+arg_8]
0x18000416a  add     rsp, 20h
0x18000416e  pop     rdi
0x18000416f  retn
```
