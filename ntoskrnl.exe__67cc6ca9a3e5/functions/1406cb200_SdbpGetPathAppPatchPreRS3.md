# SdbpGetPathAppPatchPreRS3

- ea: `0x1406cb200`
- end: `0x1406cb36e`
- name: `SdbpGetPathAppPatchPreRS3`
- size: `366`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callees

- `0x1402dc448`
- `0x1406cb200`
- `0x1406d9d70`
- `0x140824750`
- `0x140824bf0`
- `0x1408270c8`
- `0x14097d158`

## string_xrefs

- `0x1406cb2ea`: `RtlStringCchCopyW failed to copy FileName [%x]`
- `0x1406cb29a`: `SdbpGetPathAppPatchPreRS3`
- `0x1406cb325`: `AslPathCombine failed [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetPathAppPatchPreRS3(wchar_t *a1, size_t a2, const wchar_t *a3, __int64 a4)
{
  NTSTATUS ProcessHostGuestArchitectures; // ebx
  const char *v9; // r9
  int v10; // r8d
  __int16 v11[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v12; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v13[22]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF

  *(_OWORD *)v13 = *(_OWORD *)L"AppPatch64";
  *(_QWORD *)&v13[14] = *(_QWORD *)L"h64";
  if ( a2 < 0xB )
    return 3221225507LL;
  pszDest[0] = 0;
  v12 = -1;
  v11[0] = -1;
  ProcessHostGuestArchitectures = SdbpGetProcessHostGuestArchitectures(&v12, v11, a4);
  if ( ProcessHostGuestArchitectures >= 0 )
  {
    if ( v11[0] == 9 || v11[0] == 12 )
    {
      if ( !a3 )
        a3 = &cchOriginalDestLength;
      ProcessHostGuestArchitectures = AslPathCombine(v13, a3, pszDest, 260);
      if ( ProcessHostGuestArchitectures < 0 )
      {
        v9 = "AslPathCombine failed [%x]";
        v10 = 1018;
        goto LABEL_5;
      }
    }
    else
    {
      if ( !a3 )
        a3 = &cchOriginalDestLength;
      ProcessHostGuestArchitectures = RtlStringCchCopyW(pszDest, 0x104u, a3);
      if ( ProcessHostGuestArchitectures < 0 )
      {
        v9 = "RtlStringCchCopyW failed to copy FileName [%x]";
        v10 = 1024;
        goto LABEL_5;
      }
    }
    return (unsigned int)SdbpGetPathAppPatch(a1, a2, pszDest);
  }
  v9 = "SdbpGetProcessHostGuestArchitectures failed [%x]";
  v10 = 1006;
LABEL_5:
  AslLogCallPrintf(1, (unsigned int)"SdbpGetPathAppPatchPreRS3", v10, (_DWORD)v9);
  return (unsigned int)ProcessHostGuestArchitectures;
}

```

## disassembly

```asm
0x1406cb200  push    rbp
0x1406cb202  push    rbx
0x1406cb203  push    rsi
0x1406cb204  push    rdi
0x1406cb205  push    r14
0x1406cb207  push    r15
0x1406cb209  lea     rbp, [rsp-178h]
0x1406cb211  sub     rsp, 278h
0x1406cb218  mov     rax, cs:__security_cookie
0x1406cb21f  xor     rax, rsp
0x1406cb222  mov     [rbp+1A0h+var_40], rax
0x1406cb229  movsd   xmm1, qword ptr cs:aApppatch64+0Eh; "h64"
0x1406cb231  mov     rsi, r9
0x1406cb234  mov     rdi, r8
0x1406cb237  mov     r14, rdx
0x1406cb23a  mov     r15, rcx
0x1406cb23d  movups  xmm0, xmmword ptr cs:aApppatch64; "AppPatch64"
0x1406cb244  movups  xmmword ptr [rsp+2A0h+var_268], xmm0
0x1406cb249  movsd   qword ptr [rsp+2A0h+var_268+0Eh], xmm1
0x1406cb24f  cmp     rdx, 0Bh
0x1406cb253  jnb     short loc_1406CB25F
0x1406cb255  mov     eax, 0C0000023h
0x1406cb25a  jmp     loc_1406CB34E
0x1406cb25f  xor     eax, eax
0x1406cb261  lea     rdx, [rsp+2A0h+var_270]
0x1406cb266  mov     [rsp+2A0h+pszDest], ax
0x1406cb26b  lea     rcx, [rsp+2A0h+var_26C]
0x1406cb270  mov     eax, 0FFFFh
0x1406cb275  mov     r8, rsi
0x1406cb278  mov     [rsp+2A0h+var_26C], ax
0x1406cb27d  mov     [rsp+2A0h+var_270], ax
0x1406cb282  call    SdbpGetProcessHostGuestArchitectures
0x1406cb287  mov     ebx, eax
0x1406cb289  test    eax, eax
0x1406cb28b  jns     short loc_1406CB2B4
0x1406cb28d  lea     r9, aSdbpgetprocess; "SdbpGetProcessHostGuestArchitectures fa"...
0x1406cb294  mov     r8d, 3EEh
0x1406cb29a  lea     rdx, aSdbpgetpathapp; "SdbpGetPathAppPatchPreRS3"
0x1406cb2a1  mov     [rsp+2A0h+var_280], eax
0x1406cb2a5  mov     ecx, 1
0x1406cb2aa  call    AslLogCallPrintf
0x1406cb2af  jmp     loc_1406CB34C
0x1406cb2b4  cmp     [rsp+2A0h+var_270], 9
0x1406cb2ba  jz      short loc_1406CB2F9
0x1406cb2bc  cmp     [rsp+2A0h+var_270], 0Ch
0x1406cb2c2  jz      short loc_1406CB2F9
0x1406cb2c4  lea     rax, cchOriginalDestLength
0x1406cb2cb  test    rdi, rdi
0x1406cb2ce  mov     edx, 104h; cchDest
0x1406cb2d3  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x1406cb2d8  cmovz   rdi, rax
0x1406cb2dc  mov     r8, rdi; pszSrc
0x1406cb2df  call    RtlStringCchCopyW
0x1406cb2e4  mov     ebx, eax
0x1406cb2e6  test    eax, eax
0x1406cb2e8  jns     short loc_1406CB337
0x1406cb2ea  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed to copy FileNa"...
0x1406cb2f1  mov     r8d, 400h
0x1406cb2f7  jmp     short loc_1406CB29A
0x1406cb2f9  lea     rax, cchOriginalDestLength
0x1406cb300  test    rdi, rdi
0x1406cb303  mov     r9d, 104h
0x1406cb309  lea     r8, [rsp+2A0h+pszDest]
0x1406cb30e  cmovz   rdi, rax
0x1406cb312  lea     rcx, [rsp+2A0h+var_268]
0x1406cb317  mov     rdx, rdi
0x1406cb31a  call    AslPathCombine
0x1406cb31f  mov     ebx, eax
0x1406cb321  test    eax, eax
0x1406cb323  jns     short loc_1406CB337
0x1406cb325  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x1406cb32c  mov     r8d, 3FAh
0x1406cb332  jmp     loc_1406CB29A
0x1406cb337  mov     r9, rsi
0x1406cb33a  lea     r8, [rsp+2A0h+pszDest]
0x1406cb33f  mov     rdx, r14
0x1406cb342  mov     rcx, r15
0x1406cb345  call    SdbpGetPathAppPatch
0x1406cb34a  mov     ebx, eax
0x1406cb34c  mov     eax, ebx
0x1406cb34e  mov     rcx, [rbp+1A0h+var_40]
0x1406cb355  xor     rcx, rsp; StackCookie
0x1406cb358  call    __security_check_cookie
0x1406cb35d  add     rsp, 278h
0x1406cb364  pop     r15
0x1406cb366  pop     r14
0x1406cb368  pop     rdi
0x1406cb369  pop     rsi
0x1406cb36a  pop     rbx
0x1406cb36b  pop     rbp
0x1406cb36c  retn
```
