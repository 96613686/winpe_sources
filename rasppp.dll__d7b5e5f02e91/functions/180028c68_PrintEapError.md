# PrintEapError

- ea: `0x180028c68`
- end: `0x180028d1a`
- name: `PrintEapError`
- size: `178`
- prototype: `HRESULT __fastcall(int *, int *)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180027090`
- `0x180027458`
- `0x180028d20`
- `0x180029244`
- `0x180029538`
- `0x180029844`
- `0x180029ba0`

## callees

- `0x180001460`
- `0x180014b1c`
- `0x180028c68`
- `0x180034010`

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
      a1 = &dword_18003A974;
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
    if ( (_QWORD)xmmword_18004D740 )
      return ((__int64 (__fastcall *)(__int64, _QWORD, wchar_t *))gRasEapTemplateFunc)(
               gRasEapEtwContext,
               xmmword_18004D740,
               pszDest);
  }
  return result;
}

```

## disassembly

```asm
0x180028c68  test    rdx, rdx
0x180028c6b  jz      locret_180028D18
0x180028c71  sub     rsp, 278h
0x180028c78  mov     rax, cs:__security_cookie
0x180028c7f  xor     rax, rsp
0x180028c82  mov     [rsp+278h+var_18], rax
0x180028c8a  movzx   r8d, byte ptr [rdx+4]
0x180028c8f  lea     rax, dword_18003A974
0x180028c96  test    rcx, rcx
0x180028c99  cmovz   rcx, rax
0x180028c9d  mov     eax, [rdx+14h]
0x180028ca0  mov     [rsp+278h+var_230], eax
0x180028ca4  mov     r9, rcx
0x180028ca7  mov     eax, [rdx+10h]
0x180028caa  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180028caf  mov     [rsp+278h+var_238], eax
0x180028cb3  mov     eax, [rdx+0Ch]
0x180028cb6  mov     [rsp+278h+var_240], eax
0x180028cba  mov     eax, [rdx+8]
0x180028cbd  mov     [rsp+278h+var_248], eax
0x180028cc1  mov     eax, [rdx]
0x180028cc3  mov     edx, 105h; cchDest
0x180028cc8  mov     [rsp+278h+var_250], r8d
0x180028ccd  lea     r8, aHsDwwinerror0x; "%hs   dwWinError = 0x%x\n   type:\n    "...
0x180028cd4  mov     [rsp+278h+var_258], eax
0x180028cd8  call    StringCchPrintfW
0x180028cdd  mov     rdx, qword ptr cs:xmmword_18004D740
0x180028ce4  test    rdx, rdx
0x180028ce7  jz      short loc_180028D01
0x180028ce9  mov     rcx, cs:gRasEapEtwContext
0x180028cf0  lea     r8, [rsp+278h+pszDest]
0x180028cf5  mov     rax, cs:gRasEapTemplateFunc
0x180028cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d01  mov     rcx, [rsp+278h+var_18]
0x180028d09  xor     rcx, rsp; StackCookie
0x180028d0c  call    __security_check_cookie
0x180028d11  add     rsp, 278h
0x180028d18  retn
```
