# IASReportSecurityEvent$catch$0

- ea: `0x180018716`
- end: `0x18001879e`
- name: `IASReportSecurityEvent$catch$0`
- size: `136`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d1c8`
- `0x180017754`
- `0x180018716`

## string_xrefs

- `0x18001874a`: `IASReportSecurityEvent failed  0x%x`

## pseudocode

```c
__int64 __fastcall IASReportSecurityEvent_catch_0(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx

  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
  {
    v3 = *(_QWORD *)(a2 + 56);
  }
  else
  {
    v3 = *(_QWORD *)(a2 + 56);
    WppDbgPrint("IASReportSecurityEvent failed  0x%x");
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)&WPP_8ed8de69590d30c8f13474de64c7f7ed_Traceguids,
      (unsigned int)"NPSSVC",
      *(_DWORD *)(v3 + 8));
  }
  *(_DWORD *)(a2 + 48) = *(_DWORD *)(v3 + 8);
  return 0;
}

```

## disassembly

```asm
0x180018716  mov     [rsp+arg_8], rdx
0x18001871b  push    rbx
0x18001871c  push    rbp
0x18001871d  sub     rsp, 38h
0x180018721  mov     rbp, rdx
0x180018724  lea     rcx, WPP_GLOBAL_Control
0x18001872b  mov     rax, cs:WPP_GLOBAL_Control
0x180018732  cmp     rax, rcx
0x180018735  jz      short loc_180018782
0x180018737  cmp     byte ptr [rax+19h], 2
0x18001873b  jb      short loc_180018782
0x18001873d  test    byte ptr [rax+1Ch], 4
0x180018741  jz      short loc_180018782
0x180018743  mov     rbx, [rbp+38h]
0x180018747  mov     edx, [rbx+8]
0x18001874a  lea     rcx, aIasreportsecur_0; "IASReportSecurityEvent failed  0x%x"
0x180018751  call    WppDbgPrint
0x180018756  mov     edx, 0Bh
0x18001875b  mov     eax, [rbx+8]
0x18001875e  mov     [rsp+48h+var_28], eax
0x180018762  lea     r9, aNpssvc; "NPSSVC"
0x180018769  lea     r8, WPP_8ed8de69590d30c8f13474de64c7f7ed_Traceguids
0x180018770  mov     rcx, cs:WPP_GLOBAL_Control
0x180018777  mov     rcx, [rcx+10h]
0x18001877b  call    WPP_SF_sD
0x180018780  jmp     short loc_180018786
0x180018782  mov     rbx, [rbp+38h]
0x180018786  mov     eax, [rbx+8]
0x180018789  mov     [rbp+30h], eax
0x18001878c  mov     rax, 0
0x180018796  add     rsp, 38h
0x18001879a  pop     rbp
0x18001879b  pop     rbx
0x18001879c  retn
```
