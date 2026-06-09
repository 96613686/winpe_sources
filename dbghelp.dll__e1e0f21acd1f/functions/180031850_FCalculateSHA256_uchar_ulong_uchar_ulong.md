# FCalculateSHA256(uchar *,ulong,uchar * *,ulong *)

- ea: `0x180031850`
- end: `0x180031a6c`
- name: `?FCalculateSHA256@@YAHPEAEKPEAPEAEPEAK@Z`
- size: `540`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180035090`

## callees

- `0x180031850`
- `0x180035180`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180031881`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180031881`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003189d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800318bd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800318dd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800318fd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003191d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003193d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003195d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003189d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800318bd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800318dd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800318fd`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003191d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003193d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003195d`

## string_xrefs

- `0x180031877`: `bcrypt.dll`
- `0x180031893`: `BCryptOpenAlgorithmProvider`
- `0x1800318f3`: `BCryptCreateHash`

## pseudocode

```c
__int64 __fastcall FCalculateSHA256(unsigned __int8 *a1, unsigned int a2, unsigned __int8 **a3, unsigned int *a4)
{
  HMODULE Library; // rax
  HMODULE v9; // rbx
  _BYTE v11[24]; // [rsp+40h] [rbp-18h] BYREF

  Library = LoadLibraryExW(L"bcrypt.dll", 0, 0);
  v9 = Library;
  if ( !Library )
    return 0;
  g_pfnOpenAlg = (int (*)(void **, const wchar_t *, const wchar_t *, unsigned int))GetProcAddress(
                                                                                     Library,
                                                                                     "BCryptOpenAlgorithmProvider");
  if ( !g_pfnOpenAlg )
    return 0;
  g_pfnCloseAlg = (int (*)(void *, unsigned int))GetProcAddress(v9, "BCryptCloseAlgorithmProvider");
  if ( !g_pfnCloseAlg )
    return 0;
  g_pfnGetProp = (int (*)(void *, const wchar_t *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))GetProcAddress(v9, "BCryptGetProperty");
  if ( !g_pfnGetProp )
    return 0;
  g_pfnCreateHash = (int (*)(void *, void **, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int))GetProcAddress(v9, "BCryptCreateHash");
  if ( !g_pfnCreateHash )
    return 0;
  g_pfnHashData = (int (*)(void *, unsigned __int8 *, unsigned int, unsigned int))GetProcAddress(v9, "BCryptHashData");
  if ( !g_pfnHashData )
    return 0;
  g_pfnFinishHash = (int (*)(void *, unsigned __int8 *, unsigned int, unsigned int))GetProcAddress(
                                                                                      v9,
                                                                                      "BCryptFinishHash");
  if ( !g_pfnFinishHash )
    return 0;
  g_pfnDestroyHash = (int (*)(void *))GetProcAddress(v9, "BCryptDestroyHash");
  if ( !g_pfnDestroyHash
    || (unsigned int)((__int64 (__fastcall *)(void **, const wchar_t *, _QWORD, _QWORD))g_pfnOpenAlg)(
                       &g_hAlg256,
                       L"SHA256",
                       0,
                       0)
    || (unsigned int)((__int64 (__fastcall *)(void *, const wchar_t *, unsigned __int64 *, __int64, _BYTE *, _DWORD))g_pfnGetProp)(
                       g_hAlg256,
                       L"HashDigestLength",
                       &g_cbHash256,
                       4,
                       v11,
                       0)
    || (unsigned int)((__int64 (__fastcall *)(void *, const wchar_t *, unsigned __int64 *, __int64, _BYTE *, _DWORD))g_pfnGetProp)(
                       g_hAlg256,
                       L"ObjectLength",
                       &g_cbObj256,
                       4,
                       v11,
                       0)
    || (unsigned int)SHA256(a1, a2, a3, a4) )
  {
    return 0;
  }
  if ( g_hAlg256 )
  {
    ((void (__fastcall *)(void *, _QWORD))g_pfnCloseAlg)(g_hAlg256, 0);
    g_hAlg256 = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180031850  mov     [rsp+arg_0], rbx
0x180031855  mov     [rsp+arg_8], rbp
0x18003185a  mov     [rsp+arg_10], rsi
0x18003185f  mov     [rsp+arg_18], rdi
0x180031864  push    r14
0x180031866  sub     rsp, 50h
0x18003186a  mov     rsi, r8
0x18003186d  mov     ebp, edx
0x18003186f  mov     r14, rcx
0x180031872  xor     r8d, r8d; dwFlags
0x180031875  xor     edx, edx; hFile
0x180031877  lea     rcx, aBcryptDll; "bcrypt.dll"
0x18003187e  mov     rdi, r9
0x180031881  call    cs:__imp_LoadLibraryExW
0x180031887  mov     rbx, rax
0x18003188a  test    rax, rax
0x18003188d  jz      loc_180031A4F
0x180031893  lea     rdx, aBcryptopenalgo; "BCryptOpenAlgorithmProvider"
0x18003189a  mov     rcx, rax; hModule
0x18003189d  call    cs:__imp_GetProcAddress
0x1800318a3  mov     cs:?g_pfnOpenAlg@@3P6AJPEAPEAXPEB_W1K@ZEA, rax; long (*g_pfnOpenAlg)(void * *,wchar_t const *,wchar_t const *,ulong)
0x1800318aa  test    rax, rax
0x1800318ad  jz      loc_180031A4F
0x1800318b3  lea     rdx, aBcryptclosealg; "BCryptCloseAlgorithmProvider"
0x1800318ba  mov     rcx, rbx; hModule
0x1800318bd  call    cs:__imp_GetProcAddress
0x1800318c3  mov     cs:?g_pfnCloseAlg@@3P6AJPEAXK@ZEA, rax; long (*g_pfnCloseAlg)(void *,ulong)
0x1800318ca  test    rax, rax
0x1800318cd  jz      loc_180031A4F
0x1800318d3  lea     rdx, aBcryptgetprope; "BCryptGetProperty"
0x1800318da  mov     rcx, rbx; hModule
0x1800318dd  call    cs:__imp_GetProcAddress
0x1800318e3  mov     cs:?g_pfnGetProp@@3P6AJPEAXPEB_WPEAEKPEAKK@ZEA, rax; long (*g_pfnGetProp)(void *,wchar_t const *,uchar *,ulong,ulong *,ulong)
0x1800318ea  test    rax, rax
0x1800318ed  jz      loc_180031A4F
0x1800318f3  lea     rdx, aBcryptcreateha; "BCryptCreateHash"
0x1800318fa  mov     rcx, rbx; hModule
0x1800318fd  call    cs:__imp_GetProcAddress
0x180031903  mov     cs:?g_pfnCreateHash@@3P6AJPEAXPEAPEAXPEAEK2KK@ZEA, rax; long (*g_pfnCreateHash)(void *,void * *,uchar *,ulong,uchar *,ulong,ulong)
0x18003190a  test    rax, rax
0x18003190d  jz      loc_180031A4F
0x180031913  lea     rdx, aBcrypthashdata; "BCryptHashData"
0x18003191a  mov     rcx, rbx; hModule
0x18003191d  call    cs:__imp_GetProcAddress
0x180031923  mov     cs:?g_pfnHashData@@3P6AJPEAXPEAEKK@ZEA, rax; long (*g_pfnHashData)(void *,uchar *,ulong,ulong)
0x18003192a  test    rax, rax
0x18003192d  jz      loc_180031A4F
0x180031933  lea     rdx, aBcryptfinishha; "BCryptFinishHash"
0x18003193a  mov     rcx, rbx; hModule
0x18003193d  call    cs:__imp_GetProcAddress
0x180031943  mov     cs:?g_pfnFinishHash@@3P6AJPEAXPEAEKK@ZEA, rax; long (*g_pfnFinishHash)(void *,uchar *,ulong,ulong)
0x18003194a  test    rax, rax
0x18003194d  jz      loc_180031A4F
0x180031953  lea     rdx, aBcryptdestroyh; "BCryptDestroyHash"
0x18003195a  mov     rcx, rbx; hModule
0x18003195d  call    cs:__imp_GetProcAddress
0x180031963  mov     cs:?g_pfnDestroyHash@@3P6AJPEAX@ZEA, rax; long (*g_pfnDestroyHash)(void *)
0x18003196a  test    rax, rax
0x18003196d  jz      loc_180031A4F
0x180031973  mov     rax, cs:?g_pfnOpenAlg@@3P6AJPEAPEAXPEB_W1K@ZEA; long (*g_pfnOpenAlg)(void * *,wchar_t const *,wchar_t const *,ulong)
0x18003197a  lea     rdx, aSha256; "SHA256"
0x180031981  xor     r9d, r9d
0x180031984  lea     rcx, ?g_hAlg256@@3PEAXEA; void * g_hAlg256
0x18003198b  xor     r8d, r8d
0x18003198e  call    cs:__guard_dispatch_icall_fptr
0x180031994  test    eax, eax
0x180031996  jnz     loc_180031A4F
0x18003199c  mov     rcx, cs:?g_hAlg256@@3PEAXEA; void * g_hAlg256
0x1800319a3  lea     rax, [rsp+58h+var_18]
0x1800319a8  xor     ebx, ebx
0x1800319aa  lea     r8, ?g_cbHash256@@3KA; ulong g_cbHash256
0x1800319b1  mov     [rsp+58h+var_30], ebx
0x1800319b5  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800319bc  mov     [rsp+58h+var_38], rax
0x1800319c1  mov     r9d, 4
0x1800319c7  mov     rax, cs:?g_pfnGetProp@@3P6AJPEAXPEB_WPEAEKPEAKK@ZEA; long (*g_pfnGetProp)(void *,wchar_t const *,uchar *,ulong,ulong *,ulong)
0x1800319ce  call    cs:__guard_dispatch_icall_fptr
0x1800319d4  test    eax, eax
0x1800319d6  jnz     short loc_180031A4F
0x1800319d8  mov     rcx, cs:?g_hAlg256@@3PEAXEA; void * g_hAlg256
0x1800319df  lea     rax, [rsp+58h+var_18]
0x1800319e4  mov     [rsp+58h+var_30], ebx
0x1800319e8  lea     r8, ?g_cbObj256@@3KA; ulong g_cbObj256
0x1800319ef  mov     [rsp+58h+var_38], rax
0x1800319f4  lea     rdx, aObjectlength; "ObjectLength"
0x1800319fb  mov     rax, cs:?g_pfnGetProp@@3P6AJPEAXPEB_WPEAEKPEAKK@ZEA; long (*g_pfnGetProp)(void *,wchar_t const *,uchar *,ulong,ulong *,ulong)
0x180031a02  mov     r9d, 4
0x180031a08  call    cs:__guard_dispatch_icall_fptr
0x180031a0e  test    eax, eax
0x180031a10  jnz     short loc_180031A4F
0x180031a12  mov     r9, rdi; unsigned int *
0x180031a15  mov     r8, rsi; unsigned __int8 **
0x180031a18  mov     edx, ebp; unsigned int
0x180031a1a  mov     rcx, r14; unsigned __int8 *
0x180031a1d  call    ?SHA256@@YAJPEAEKPEAPEAEPEAK@Z; SHA256(uchar *,ulong,uchar * *,ulong *)
0x180031a22  test    eax, eax
0x180031a24  jnz     short loc_180031A4F
0x180031a26  mov     rcx, cs:?g_hAlg256@@3PEAXEA; void * g_hAlg256
0x180031a2d  test    rcx, rcx
0x180031a30  jz      short loc_180031A48
0x180031a32  mov     rax, cs:?g_pfnCloseAlg@@3P6AJPEAXK@ZEA; long (*g_pfnCloseAlg)(void *,ulong)
0x180031a39  xor     edx, edx
0x180031a3b  call    cs:__guard_dispatch_icall_fptr
0x180031a41  mov     cs:?g_hAlg256@@3PEAXEA, rbx; void * g_hAlg256
0x180031a48  mov     eax, 1
0x180031a4d  jmp     short loc_180031A51
0x180031a4f  xor     eax, eax
0x180031a51  mov     rbx, [rsp+58h+arg_0]
0x180031a56  mov     rbp, [rsp+58h+arg_8]
0x180031a5b  mov     rsi, [rsp+58h+arg_10]
0x180031a60  mov     rdi, [rsp+58h+arg_18]
0x180031a65  add     rsp, 50h
0x180031a69  pop     r14
0x180031a6b  retn
```
