# SdbpGetPathAppPatchPreRS3

- ea: `0x1406cde60`
- end: `0x1406cdfce`
- name: `SdbpGetPathAppPatchPreRS3`
- size: `366`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callees

- `0x140438468`
- `0x1406cde60`
- `0x1406dc8c0`
- `0x1408266c0`
- `0x140826b60`
- `0x140829038`
- `0x1408c2f88`

## string_xrefs

- `0x1406cdefa`: `SdbpGetPathAppPatchPreRS3`
- `0x1406cdf4a`: `RtlStringCchCopyW failed to copy FileName [%x]`
- `0x1406cdf85`: `AslPathCombine failed [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetPathAppPatchPreRS3(wchar_t *a1, size_t a2, const wchar_t *a3, __int64 a4)
{
  NTSTATUS ProcessHostGuestArchitectures; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  int v11; // r8d
  NTSTATUS v12; // [rsp+20h] [rbp-E0h]
  __int16 v13[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v14; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v15[22]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF

  *(_OWORD *)v15 = *(_OWORD *)L"AppPatch64";
  *(_QWORD *)&v15[14] = *(_QWORD *)L"h64";
  if ( a2 < 0xB )
    return 3221225507LL;
  pszDest[0] = 0;
  v14 = -1;
  v13[0] = -1;
  ProcessHostGuestArchitectures = SdbpGetProcessHostGuestArchitectures(&v14, v13, a4);
  v9 = ProcessHostGuestArchitectures;
  if ( ProcessHostGuestArchitectures >= 0 )
  {
    if ( v13[0] == 9 || v13[0] == 12 )
    {
      if ( !a3 )
        a3 = &cchOriginalDestLength;
      ProcessHostGuestArchitectures = AslPathCombine(v15, a3, pszDest, 260);
      v9 = ProcessHostGuestArchitectures;
      if ( ProcessHostGuestArchitectures < 0 )
      {
        v10 = "AslPathCombine failed [%x]";
        v11 = 1018;
        goto LABEL_5;
      }
    }
    else
    {
      if ( !a3 )
        a3 = &cchOriginalDestLength;
      ProcessHostGuestArchitectures = RtlStringCchCopyW(pszDest, 0x104u, a3);
      v9 = ProcessHostGuestArchitectures;
      if ( ProcessHostGuestArchitectures < 0 )
      {
        v10 = "RtlStringCchCopyW failed to copy FileName [%x]";
        v11 = 1024;
        goto LABEL_5;
      }
    }
    return (unsigned int)SdbpGetPathAppPatch(a1, a2, pszDest);
  }
  v10 = "SdbpGetProcessHostGuestArchitectures failed [%x]";
  v11 = 1006;
LABEL_5:
  v12 = ProcessHostGuestArchitectures;
  AslLogCallPrintf(1, (unsigned int)"SdbpGetPathAppPatchPreRS3", v11, (_DWORD)v10, v12);
  return v9;
}

```

## disassembly

```asm
0x1406cde60  push    rbp
0x1406cde62  push    rbx
0x1406cde63  push    rsi
0x1406cde64  push    rdi
0x1406cde65  push    r14
0x1406cde67  push    r15
0x1406cde69  lea     rbp, [rsp-178h]
0x1406cde71  sub     rsp, 278h
0x1406cde78  mov     rax, cs:__security_cookie
0x1406cde7f  xor     rax, rsp
0x1406cde82  mov     [rbp+1A0h+var_40], rax
0x1406cde89  movsd   xmm1, qword ptr cs:aApppatch64+0Eh; "h64"
0x1406cde91  mov     rsi, r9
0x1406cde94  mov     rdi, r8
0x1406cde97  mov     r14, rdx
0x1406cde9a  mov     r15, rcx
0x1406cde9d  movups  xmm0, xmmword ptr cs:aApppatch64; "AppPatch64"
0x1406cdea4  movups  xmmword ptr [rsp+2A0h+var_268], xmm0
0x1406cdea9  movsd   qword ptr [rsp+2A0h+var_268+0Eh], xmm1
0x1406cdeaf  cmp     rdx, 0Bh
0x1406cdeb3  jnb     short loc_1406CDEBF
0x1406cdeb5  mov     eax, 0C0000023h
0x1406cdeba  jmp     loc_1406CDFAE
0x1406cdebf  xor     eax, eax
0x1406cdec1  lea     rdx, [rsp+2A0h+var_270]
0x1406cdec6  mov     [rsp+2A0h+pszDest], ax
0x1406cdecb  lea     rcx, [rsp+2A0h+var_26C]
0x1406cded0  mov     eax, 0FFFFh
0x1406cded5  mov     r8, rsi
0x1406cded8  mov     [rsp+2A0h+var_26C], ax
0x1406cdedd  mov     [rsp+2A0h+var_270], ax
0x1406cdee2  call    SdbpGetProcessHostGuestArchitectures
0x1406cdee7  mov     ebx, eax
0x1406cdee9  test    eax, eax
0x1406cdeeb  jns     short loc_1406CDF14
0x1406cdeed  lea     r9, aSdbpgetprocess; "SdbpGetProcessHostGuestArchitectures fa"...
0x1406cdef4  mov     r8d, 3EEh
0x1406cdefa  lea     rdx, aSdbpgetpathapp; "SdbpGetPathAppPatchPreRS3"
0x1406cdf01  mov     [rsp+2A0h+var_280], eax
0x1406cdf05  mov     ecx, 1
0x1406cdf0a  call    AslLogCallPrintf
0x1406cdf0f  jmp     loc_1406CDFAC
0x1406cdf14  cmp     [rsp+2A0h+var_270], 9
0x1406cdf1a  jz      short loc_1406CDF59
0x1406cdf1c  cmp     [rsp+2A0h+var_270], 0Ch
0x1406cdf22  jz      short loc_1406CDF59
0x1406cdf24  lea     rax, cchOriginalDestLength
0x1406cdf2b  test    rdi, rdi
0x1406cdf2e  mov     edx, 104h; cchDest
0x1406cdf33  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x1406cdf38  cmovz   rdi, rax
0x1406cdf3c  mov     r8, rdi; pszSrc
0x1406cdf3f  call    RtlStringCchCopyW
0x1406cdf44  mov     ebx, eax
0x1406cdf46  test    eax, eax
0x1406cdf48  jns     short loc_1406CDF97
0x1406cdf4a  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed to copy FileNa"...
0x1406cdf51  mov     r8d, 400h
0x1406cdf57  jmp     short loc_1406CDEFA
0x1406cdf59  lea     rax, cchOriginalDestLength
0x1406cdf60  test    rdi, rdi
0x1406cdf63  mov     r9d, 104h
0x1406cdf69  lea     r8, [rsp+2A0h+pszDest]
0x1406cdf6e  cmovz   rdi, rax
0x1406cdf72  lea     rcx, [rsp+2A0h+var_268]
0x1406cdf77  mov     rdx, rdi
0x1406cdf7a  call    AslPathCombine
0x1406cdf7f  mov     ebx, eax
0x1406cdf81  test    eax, eax
0x1406cdf83  jns     short loc_1406CDF97
0x1406cdf85  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x1406cdf8c  mov     r8d, 3FAh
0x1406cdf92  jmp     loc_1406CDEFA
0x1406cdf97  mov     r9, rsi
0x1406cdf9a  lea     r8, [rsp+2A0h+pszDest]
0x1406cdf9f  mov     rdx, r14
0x1406cdfa2  mov     rcx, r15
0x1406cdfa5  call    SdbpGetPathAppPatch
0x1406cdfaa  mov     ebx, eax
0x1406cdfac  mov     eax, ebx
0x1406cdfae  mov     rcx, [rbp+1A0h+var_40]
0x1406cdfb5  xor     rcx, rsp; StackCookie
0x1406cdfb8  call    __security_check_cookie
0x1406cdfbd  add     rsp, 278h
0x1406cdfc4  pop     r15
0x1406cdfc6  pop     r14
0x1406cdfc8  pop     rdi
0x1406cdfc9  pop     rsi
0x1406cdfca  pop     rbx
0x1406cdfcb  pop     rbp
0x1406cdfcc  retn
```
