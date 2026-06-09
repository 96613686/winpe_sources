# Win32LiveSystemProvider::WintrustVerifyMicrosoftSignature(ushort const *)

- ea: `0x180016438`
- end: `0x180016721`
- name: `?WintrustVerifyMicrosoftSignature@Win32LiveSystemProvider@@AEAAJPEBG@Z`
- size: `745`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016198`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180016438`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180016499`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800164b4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800164cf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180016504`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180016499`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800164b4`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800164cf`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180016504`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180016479`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1800164e8`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180016479`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1800164e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001665e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001665e`

## string_xrefs

- `0x180016470`: `wintrust.dll`
- `0x1800164d8`: `crypt32.dll`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::WintrustVerifyMicrosoftSignature(
        Win32LiveSystemProvider *this,
        const unsigned __int16 *a2)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v6; // rcx
  FARPROC v7; // rax
  HMODULE v8; // rcx
  HMODULE v9; // rax
  __int64 (__fastcall *v10)(_QWORD, _DWORD *, _DWORD *); // rbx
  signed int LastError; // eax
  unsigned int v12; // ebx
  bool v13; // cc
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rdx
  unsigned int (__fastcall *v18)(_QWORD, __int64, __int128 *, __int128 *); // rax
  void (__fastcall *v19)(_QWORD, _DWORD *, _DWORD *); // rax
  __int64 v20; // rdx
  unsigned int (__fastcall *v21)(__int64, __int64, __int128 *, __int128 *); // rax
  __int128 v23; // [rsp+30h] [rbp-89h] BYREF
  __int128 v24; // [rsp+40h] [rbp-79h] BYREF
  __int64 v25; // [rsp+50h] [rbp-69h]
  _QWORD v26[2]; // [rsp+58h] [rbp-61h] BYREF
  __int128 v27; // [rsp+68h] [rbp-51h]
  _DWORD v28[10]; // [rsp+80h] [rbp-39h] BYREF
  _QWORD *v29; // [rsp+A8h] [rbp-11h]
  int v30; // [rsp+B0h] [rbp-9h]
  __int64 v31; // [rsp+B8h] [rbp-1h]
  int v32; // [rsp+C8h] [rbp+Fh]
  _DWORD v33[4]; // [rsp+E0h] [rbp+27h] BYREF

  if ( !*((_DWORD *)this + 162) )
  {
    Library = LoadLibraryExA("wintrust.dll", 0, 0);
    *((_QWORD *)this + 75) = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "WinVerifyTrust");
      v6 = (HMODULE)*((_QWORD *)this + 75);
      *((_QWORD *)this + 76) = ProcAddress;
      v7 = GetProcAddress(v6, "WTHelperProvDataFromStateData");
      v8 = (HMODULE)*((_QWORD *)this + 75);
      *((_QWORD *)this + 77) = v7;
      *((_QWORD *)this + 78) = GetProcAddress(v8, "WTHelperGetProvSignerFromChain");
      v9 = LoadLibraryExA("crypt32.dll", 0, 0);
      *((_QWORD *)this + 79) = v9;
      if ( v9 )
        *((_QWORD *)this + 80) = GetProcAddress(v9, "CertVerifyCertificateChainPolicy");
    }
    *((_DWORD *)this + 162) = 1;
  }
  v10 = (__int64 (__fastcall *)(_QWORD, _DWORD *, _DWORD *))*((_QWORD *)this + 76);
  if ( !v10 || !*((_QWORD *)this + 77) || !*((_QWORD *)this + 78) || !*((_QWORD *)this + 80) )
    return (unsigned int)-2147467263;
  v26[1] = a2;
  v33[0] = 11191659;
  v33[1] = 298896708;
  v33[2] = -1073692020;
  v33[3] = -292175281;
  v26[0] = 32;
  v27 = 0;
  memset_0(v28, 0, 0x58u);
  v28[0] = 88;
  v29 = v26;
  v28[6] = 2;
  v32 = 4160;
  v30 = 1;
  v28[8] = 1;
  LastError = v10(0, v33, v28);
  v12 = LastError;
  v13 = LastError <= 0;
  if ( LastError )
    goto LABEL_16;
  v14 = (*((__int64 (__fastcall **)(__int64))this + 77))(v31);
  if ( v14 )
  {
    v15 = (*((__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))this + 78))(v14, 0, 0, 0);
    v16 = v15;
    if ( v15 )
    {
      v17 = *(_QWORD *)(v15 + 56);
      v25 = 0;
      v18 = (unsigned int (__fastcall *)(_QWORD, __int64, __int128 *, __int128 *))*((_QWORD *)this + 80);
      v23 = 0;
      LODWORD(v23) = 16;
      v24 = 0;
      LODWORD(v24) = 24;
      if ( v18(v12 + 7, v17, &v23, &v24) )
      {
        v12 = 0;
        if ( !DWORD1(v24) )
          goto LABEL_18;
        v20 = *(_QWORD *)(v16 + 56);
        v25 = 0;
        v21 = (unsigned int (__fastcall *)(__int64, __int64, __int128 *, __int128 *))*((_QWORD *)this + 80);
        v24 = 0;
        v23 = 0x2000000000010uLL;
        LODWORD(v24) = 24;
        if ( v21(7, v20, &v23, &v24) )
        {
          if ( DWORD1(v24) )
            v12 = DWORD1(v24);
          goto LABEL_18;
        }
      }
    }
  }
  if ( GetLastError() )
  {
    LastError = GetLastError();
    v12 = LastError;
    v13 = LastError <= 0;
LABEL_16:
    if ( !v13 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_18;
  }
  v12 = -2147467259;
LABEL_18:
  v19 = (void (__fastcall *)(_QWORD, _DWORD *, _DWORD *))*((_QWORD *)this + 76);
  v30 = 2;
  v19(0, v33, v28);
  return v12;
}

```

## disassembly

```asm
0x180016438  mov     [rsp-8+arg_10], rbx
0x18001643d  push    rbp
0x18001643e  push    rsi
0x18001643f  push    rdi
0x180016440  lea     rbp, [rsp-47h]
0x180016445  sub     rsp, 100h
0x18001644c  mov     rax, cs:__security_cookie
0x180016453  xor     rax, rsp
0x180016456  mov     [rbp+57h+var_20], rax
0x18001645a  cmp     dword ptr [rcx+288h], 0
0x180016461  mov     rsi, rdx
0x180016464  mov     rdi, rcx
0x180016467  jnz     loc_18001651B
0x18001646d  xor     r8d, r8d; dwFlags
0x180016470  lea     rcx, aWintrustDll; "wintrust.dll"
0x180016477  xor     edx, edx; hFile
0x180016479  call    cs:__imp_LoadLibraryExA
0x18001647f  mov     [rdi+258h], rax
0x180016486  test    rax, rax
0x180016489  jz      loc_180016511
0x18001648f  lea     rdx, aWinverifytrust; "WinVerifyTrust"
0x180016496  mov     rcx, rax; hModule
0x180016499  call    cs:__imp_GetProcAddress
0x18001649f  mov     rcx, [rdi+258h]; hModule
0x1800164a6  lea     rdx, aWthelperprovda; "WTHelperProvDataFromStateData"
0x1800164ad  mov     [rdi+260h], rax
0x1800164b4  call    cs:__imp_GetProcAddress
0x1800164ba  mov     rcx, [rdi+258h]; hModule
0x1800164c1  lea     rdx, aWthelpergetpro; "WTHelperGetProvSignerFromChain"
0x1800164c8  mov     [rdi+268h], rax
0x1800164cf  call    cs:__imp_GetProcAddress
0x1800164d5  xor     r8d, r8d; dwFlags
0x1800164d8  lea     rcx, aCrypt32Dll; "crypt32.dll"
0x1800164df  xor     edx, edx; hFile
0x1800164e1  mov     [rdi+270h], rax
0x1800164e8  call    cs:__imp_LoadLibraryExA
0x1800164ee  mov     [rdi+278h], rax
0x1800164f5  test    rax, rax
0x1800164f8  jz      short loc_180016511
0x1800164fa  lea     rdx, aCertverifycert; "CertVerifyCertificateChainPolicy"
0x180016501  mov     rcx, rax; hModule
0x180016504  call    cs:__imp_GetProcAddress
0x18001650a  mov     [rdi+280h], rax
0x180016511  mov     dword ptr [rdi+288h], 1
0x18001651b  mov     rbx, [rdi+260h]
0x180016522  test    rbx, rbx
0x180016525  jz      loc_1800166FB
0x18001652b  cmp     qword ptr [rdi+268h], 0
0x180016533  jz      loc_1800166FB
0x180016539  cmp     qword ptr [rdi+270h], 0
0x180016541  jz      loc_1800166FB
0x180016547  cmp     qword ptr [rdi+280h], 0
0x18001654f  jz      loc_1800166FB
0x180016555  xorps   xmm0, xmm0
0x180016558  mov     [rbp+57h+var_B0], rsi
0x18001655c  mov     esi, 58h ; 'X'
0x180016561  mov     [rbp+57h+var_30], 0AAC56Bh
0x180016568  mov     r8d, esi; Size
0x18001656b  mov     [rbp+57h+var_2C], 11D0CD44h
0x180016572  xor     edx, edx; Val
0x180016574  mov     [rbp+57h+var_28], 0C000C28Ch
0x18001657b  lea     rcx, [rbp+57h+var_90]; void *
0x18001657f  mov     [rbp+57h+var_24], 0EE95C24Fh
0x180016586  mov     [rbp+57h+var_B8], 20h ; ' '
0x18001658e  movdqu  [rbp+57h+var_A8], xmm0
0x180016593  call    memset_0
0x180016598  lea     rax, [rbp+57h+var_B8]
0x18001659c  mov     [rbp+57h+var_90], esi
0x18001659f  mov     [rbp+57h+var_68], rax
0x1800165a3  lea     r8, [rbp+57h+var_90]
0x1800165a7  mov     rax, rbx
0x1800165aa  mov     [rbp+57h+var_78], 2
0x1800165b1  lea     rdx, [rbp+57h+var_30]
0x1800165b5  mov     [rbp+57h+var_48], 1040h
0x1800165bc  xor     ecx, ecx
0x1800165be  mov     [rbp+57h+var_60], 1
0x1800165c5  mov     [rbp+57h+var_70], 1
0x1800165cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165d1  mov     ebx, eax
0x1800165d3  test    eax, eax
0x1800165d5  jnz     loc_180016668
0x1800165db  mov     rcx, [rbp+57h+var_58]
0x1800165df  mov     rax, [rdi+268h]
0x1800165e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165eb  test    rax, rax
0x1800165ee  jz      short loc_180016650
0x1800165f0  mov     rcx, rax
0x1800165f3  xor     r9d, r9d
0x1800165f6  mov     rax, [rdi+270h]
0x1800165fd  xor     r8d, r8d
0x180016600  xor     edx, edx
0x180016602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016607  mov     rsi, rax
0x18001660a  test    rax, rax
0x18001660d  jz      short loc_180016650
0x18001660f  mov     rdx, [rsi+38h]
0x180016613  lea     r9, [rbp+57h+var_D0]
0x180016617  xor     eax, eax
0x180016619  lea     r8, [rsp+110h+var_E0]
0x18001661e  xorps   xmm0, xmm0
0x180016621  mov     [rbp+57h+var_C0], rax
0x180016625  mov     rax, [rdi+280h]
0x18001662c  lea     ecx, [rbx+7]
0x18001662f  movups  [rsp+110h+var_E0], xmm0
0x180016634  mov     dword ptr [rsp+110h+var_E0], 10h
0x18001663c  movups  [rbp+57h+var_D0], xmm0
0x180016640  mov     dword ptr [rbp+57h+var_D0], 18h
0x180016647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001664c  test    eax, eax
0x18001664e  jnz     short loc_180016692
0x180016650  call    cs:__imp_GetLastError
0x180016656  test    eax, eax
0x180016658  jz      loc_1800166F1
0x18001665e  call    cs:__imp_GetLastError
0x180016664  mov     ebx, eax
0x180016666  test    eax, eax
0x180016668  jle     short loc_180016673
0x18001666a  movzx   ebx, ax
0x18001666d  or      ebx, 80070000h
0x180016673  mov     rax, [rdi+260h]
0x18001667a  lea     r8, [rbp+57h+var_90]
0x18001667e  lea     rdx, [rbp+57h+var_30]
0x180016682  mov     [rbp+57h+var_60], 2
0x180016689  xor     ecx, ecx
0x18001668b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016690  jmp     short loc_180016700
0x180016692  xor     ebx, ebx
0x180016694  cmp     dword ptr [rbp+57h+var_D0+4], ebx
0x180016697  jz      short loc_180016673
0x180016699  mov     rdx, [rsi+38h]
0x18001669d  lea     r9, [rbp+57h+var_D0]
0x1800166a1  xor     eax, eax
0x1800166a3  mov     qword ptr [rsp+110h+var_E0+8], rbx
0x1800166a8  xorps   xmm0, xmm0
0x1800166ab  mov     [rbp+57h+var_C0], rax
0x1800166af  mov     rax, [rdi+280h]
0x1800166b6  lea     r8, [rsp+110h+var_E0]
0x1800166bb  movups  [rbp+57h+var_D0], xmm0
0x1800166bf  lea     ecx, [rbx+7]
0x1800166c2  mov     dword ptr [rsp+110h+var_E0], 10h
0x1800166ca  mov     dword ptr [rsp+110h+var_E0+4], 20000h
0x1800166d2  mov     dword ptr [rbp+57h+var_D0], 18h
0x1800166d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166de  test    eax, eax
0x1800166e0  jz      loc_180016650
0x1800166e6  mov     eax, dword ptr [rbp+57h+var_D0+4]
0x1800166e9  test    eax, eax
0x1800166eb  jz      short loc_180016673
0x1800166ed  mov     ebx, eax
0x1800166ef  jmp     short loc_180016673
0x1800166f1  mov     ebx, 80004005h
0x1800166f6  jmp     loc_180016673
0x1800166fb  mov     ebx, 80004001h
0x180016700  mov     eax, ebx
0x180016702  mov     rcx, [rbp+57h+var_20]
0x180016706  xor     rcx, rsp; StackCookie
0x180016709  call    __security_check_cookie
0x18001670e  mov     rbx, [rsp+110h+arg_10]
0x180016716  add     rsp, 100h
0x18001671d  pop     rdi
0x18001671e  pop     rsi
0x18001671f  pop     rbp
0x180016720  retn
```
