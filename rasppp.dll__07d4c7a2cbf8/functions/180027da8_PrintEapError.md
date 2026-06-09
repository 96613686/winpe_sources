# PrintEapError

- ea: `0x180027da8`
- end: `0x180027e59`
- name: `PrintEapError`
- size: `177`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x1800262b0`
- `0x180026654`
- `0x180027e60`
- `0x180028364`
- `0x18002864c`
- `0x180028938`
- `0x180028c84`

## callees

- `0x180001460`
- `0x180014434`
- `0x180027da8`
- `0x180033010`

## pseudocode

```c
HRESULT __fastcall PrintEapError(int *a1, int *a2)
{
  HRESULT result; // eax
  int v3; // [rsp+20h] [rbp-258h]
  int v4; // [rsp+28h] [rbp-250h]
  int v5; // [rsp+30h] [rbp-248h]
  int v6; // [rsp+38h] [rbp-240h]
  int v7; // [rsp+40h] [rbp-238h]
  int v8; // [rsp+48h] [rbp-230h]
  wchar_t pszDest[264]; // [rsp+50h] [rbp-228h] BYREF

  if ( a2 )
  {
    if ( !a1 )
      a1 = &dword_180039974;
    v8 = a2[5];
    v7 = a2[4];
    v6 = a2[3];
    v5 = a2[2];
    v4 = *((unsigned __int8 *)a2 + 4);
    v3 = *a2;
    result = StringCchPrintfW(
               pszDest,
               0x105u,
               L"%hs   dwWinError = 0x%x\n"
                "   type:\n"
                "      eapType: type = %u\n"
                "               dwVendorId = %u\n"
                "               dwVendorType = %u\n"
                "      dwAuthorId = %u\n"
                "   dwReasonCode = 0x%x\n",
               a1,
               v3,
               v4,
               v5,
               v6,
               v7,
               v8);
    if ( (_QWORD)xmmword_18004C740 )
      return ((__int64 (__fastcall *)(__int64, _QWORD, wchar_t *))gRasEapTemplateFunc)(
               gRasEapEtwContext,
               xmmword_18004C740,
               pszDest);
  }
  return result;
}

```

## disassembly

```asm
0x180027da8  test    rdx, rdx
0x180027dab  jz      locret_180027E58
0x180027db1  sub     rsp, 278h
0x180027db8  mov     rax, cs:__security_cookie
0x180027dbf  xor     rax, rsp
0x180027dc2  mov     [rsp+278h+var_18], rax
0x180027dca  movzx   r8d, byte ptr [rdx+4]
0x180027dcf  lea     rax, dword_180039974
0x180027dd6  test    rcx, rcx
0x180027dd9  cmovz   rcx, rax
0x180027ddd  mov     eax, [rdx+14h]
0x180027de0  mov     [rsp+278h+var_230], eax
0x180027de4  mov     r9, rcx
0x180027de7  mov     eax, [rdx+10h]
0x180027dea  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180027def  mov     [rsp+278h+var_238], eax
0x180027df3  mov     eax, [rdx+0Ch]
0x180027df6  mov     [rsp+278h+var_240], eax
0x180027dfa  mov     eax, [rdx+8]
0x180027dfd  mov     [rsp+278h+var_248], eax
0x180027e01  mov     eax, [rdx]
0x180027e03  mov     edx, 105h; cchDest
0x180027e08  mov     [rsp+278h+var_250], r8d
0x180027e0d  lea     r8, aHsDwwinerror0x; "%hs   dwWinError = 0x%x\n   type:\n    "...
0x180027e14  mov     [rsp+278h+var_258], eax
0x180027e18  call    StringCchPrintfW
0x180027e1d  mov     rdx, qword ptr cs:xmmword_18004C740
0x180027e24  test    rdx, rdx
0x180027e27  jz      short loc_180027E41
0x180027e29  mov     rcx, cs:gRasEapEtwContext
0x180027e30  lea     r8, [rsp+278h+pszDest]
0x180027e35  mov     rax, cs:gRasEapTemplateFunc
0x180027e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e41  mov     rcx, [rsp+278h+var_18]
0x180027e49  xor     rcx, rsp; StackCookie
0x180027e4c  call    __security_check_cookie
0x180027e51  add     rsp, 278h
0x180027e58  retn
```
