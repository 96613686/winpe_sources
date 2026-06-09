# Win32LiveSystemProvider::WintrustVerifyMicrosoftSignature(ushort const *)

- ea: `0x180402908`
- end: `0x180402c22`
- name: `?WintrustVerifyMicrosoftSignature@Win32LiveSystemProvider@@AEAAJPEBG@Z`
- size: `794`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180402690`

## callees

- `0x1800f0f40`
- `0x180402908`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040296f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180402990`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1804029b1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1804029f2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18040296f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180402990`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1804029b1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1804029f2`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180402949`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1804029d0`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x180402949`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x1804029d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180402b44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180402b58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180402b44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180402b58`

## string_xrefs

- `0x180402940`: `wintrust.dll`
- `0x1804029c0`: `crypt32.dll`

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
  __int64 (__fastcall *v10)(_QWORD, _DWORD *, _QWORD *); // rbx
  signed int LastError; // eax
  unsigned int v12; // ebx
  bool v13; // cc
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rdx
  unsigned int (__fastcall *v18)(_QWORD, __int64, __int128 *, __int128 *); // rax
  void (__fastcall *v19)(_QWORD, _DWORD *, _QWORD *); // rax
  __int64 v20; // rdx
  unsigned int (__fastcall *v21)(__int64, __int64, __int128 *, __int128 *); // rax
  __int128 v23; // [rsp+30h] [rbp-89h] BYREF
  __int128 v24; // [rsp+40h] [rbp-79h] BYREF
  __int64 v25; // [rsp+50h] [rbp-69h]
  _QWORD v26[2]; // [rsp+58h] [rbp-61h] BYREF
  __int128 v27; // [rsp+68h] [rbp-51h]
  _QWORD v28[12]; // [rsp+80h] [rbp-39h] BYREF
  _DWORD v29[4]; // [rsp+E0h] [rbp+27h] BYREF

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
  v10 = (__int64 (__fastcall *)(_QWORD, _DWORD *, _QWORD *))*((_QWORD *)this + 76);
  if ( !v10 || !*((_QWORD *)this + 77) || !*((_QWORD *)this + 78) || !*((_QWORD *)this + 80) )
    return (unsigned int)-2147467263;
  v26[1] = a2;
  v29[0] = 11191659;
  v29[1] = 298896708;
  v29[2] = -1073692020;
  v29[3] = -292175281;
  v26[0] = 32;
  v27 = 0;
  memset(v28, 0, 0x58u);
  LODWORD(v28[0]) = 88;
  v28[5] = v26;
  LODWORD(v28[3]) = 2;
  LODWORD(v28[9]) = 4160;
  LODWORD(v28[6]) = 1;
  LODWORD(v28[4]) = 1;
  LastError = v10(0, v29, v28);
  v12 = LastError;
  v13 = LastError <= 0;
  if ( LastError )
    goto LABEL_16;
  v14 = (*((__int64 (__fastcall **)(_QWORD))this + 77))(v28[7]);
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
  v19 = (void (__fastcall *)(_QWORD, _DWORD *, _QWORD *))*((_QWORD *)this + 76);
  LODWORD(v28[6]) = 2;
  v19(0, v29, v28);
  return v12;
}

```

## disassembly

```asm
0x180402908  mov     [rsp-8+arg_10], rbx
0x18040290d  push    rbp
0x18040290e  push    rsi
0x18040290f  push    rdi
0x180402910  lea     rbp, [rsp-47h]
0x180402915  sub     rsp, 100h
0x18040291c  mov     rax, cs:__security_cookie
0x180402923  xor     rax, rsp
0x180402926  mov     [rbp+57h+var_20], rax
0x18040292a  cmp     dword ptr [rcx+288h], 0
0x180402931  mov     rsi, rdx
0x180402934  mov     rdi, rcx
0x180402937  jnz     loc_180402A0F
0x18040293d  xor     r8d, r8d; dwFlags
0x180402940  lea     rcx, aWintrustDll; "wintrust.dll"
0x180402947  xor     edx, edx; hFile
0x180402949  call    cs:__imp_LoadLibraryExA
0x180402950  nop     dword ptr [rax+rax+00h]
0x180402955  mov     [rdi+258h], rax
0x18040295c  test    rax, rax
0x18040295f  jz      loc_180402A05
0x180402965  lea     rdx, aWinverifytrust; "WinVerifyTrust"
0x18040296c  mov     rcx, rax; hModule
0x18040296f  call    cs:__imp_GetProcAddress
0x180402976  nop     dword ptr [rax+rax+00h]
0x18040297b  mov     rcx, [rdi+258h]; hModule
0x180402982  lea     rdx, aWthelperprovda; "WTHelperProvDataFromStateData"
0x180402989  mov     [rdi+260h], rax
0x180402990  call    cs:__imp_GetProcAddress
0x180402997  nop     dword ptr [rax+rax+00h]
0x18040299c  mov     rcx, [rdi+258h]; hModule
0x1804029a3  lea     rdx, aWthelpergetpro; "WTHelperGetProvSignerFromChain"
0x1804029aa  mov     [rdi+268h], rax
0x1804029b1  call    cs:__imp_GetProcAddress
0x1804029b8  nop     dword ptr [rax+rax+00h]
0x1804029bd  xor     r8d, r8d; dwFlags
0x1804029c0  lea     rcx, aCrypt32Dll; "crypt32.dll"
0x1804029c7  xor     edx, edx; hFile
0x1804029c9  mov     [rdi+270h], rax
0x1804029d0  call    cs:__imp_LoadLibraryExA
0x1804029d7  nop     dword ptr [rax+rax+00h]
0x1804029dc  mov     [rdi+278h], rax
0x1804029e3  test    rax, rax
0x1804029e6  jz      short loc_180402A05
0x1804029e8  lea     rdx, aCertverifycert; "CertVerifyCertificateChainPolicy"
0x1804029ef  mov     rcx, rax; hModule
0x1804029f2  call    cs:__imp_GetProcAddress
0x1804029f9  nop     dword ptr [rax+rax+00h]
0x1804029fe  mov     [rdi+280h], rax
0x180402a05  mov     dword ptr [rdi+288h], 1
0x180402a0f  mov     rbx, [rdi+260h]
0x180402a16  test    rbx, rbx
0x180402a19  jz      loc_180402BFB
0x180402a1f  cmp     qword ptr [rdi+268h], 0
0x180402a27  jz      loc_180402BFB
0x180402a2d  cmp     qword ptr [rdi+270h], 0
0x180402a35  jz      loc_180402BFB
0x180402a3b  cmp     qword ptr [rdi+280h], 0
0x180402a43  jz      loc_180402BFB
0x180402a49  xorps   xmm0, xmm0
0x180402a4c  mov     [rbp+57h+var_B0], rsi
0x180402a50  mov     esi, 58h ; 'X'
0x180402a55  mov     [rbp+57h+var_30], 0AAC56Bh
0x180402a5c  mov     r8d, esi; Size
0x180402a5f  mov     [rbp+57h+var_2C], 11D0CD44h
0x180402a66  xor     edx, edx; Val
0x180402a68  mov     [rbp+57h+var_28], 0C000C28Ch
0x180402a6f  lea     rcx, [rbp+57h+var_90]; void *
0x180402a73  mov     [rbp+57h+var_24], 0EE95C24Fh
0x180402a7a  mov     [rbp+57h+var_B8], 20h ; ' '
0x180402a82  movdqu  [rbp+57h+var_A8], xmm0
0x180402a87  call    memset
0x180402a8c  lea     rax, [rbp+57h+var_B8]
0x180402a90  mov     [rbp+57h+var_90], esi
0x180402a93  mov     [rbp+57h+var_68], rax
0x180402a97  lea     r8, [rbp+57h+var_90]
0x180402a9b  mov     rax, rbx
0x180402a9e  mov     [rbp+57h+var_78], 2
0x180402aa5  lea     rdx, [rbp+57h+var_30]
0x180402aa9  mov     [rbp+57h+var_48], 1040h
0x180402ab0  xor     ecx, ecx
0x180402ab2  mov     [rbp+57h+var_60], 1
0x180402ab9  mov     [rbp+57h+var_70], 1
0x180402ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180402ac5  mov     ebx, eax
0x180402ac7  test    eax, eax
0x180402ac9  jnz     loc_180402B68
0x180402acf  mov     rcx, [rbp+57h+var_58]
0x180402ad3  mov     rax, [rdi+268h]
0x180402ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180402adf  test    rax, rax
0x180402ae2  jz      short loc_180402B44
0x180402ae4  mov     rcx, rax
0x180402ae7  xor     r9d, r9d
0x180402aea  mov     rax, [rdi+270h]
0x180402af1  xor     r8d, r8d
0x180402af4  xor     edx, edx
0x180402af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180402afb  mov     rsi, rax
0x180402afe  test    rax, rax
0x180402b01  jz      short loc_180402B44
0x180402b03  mov     rdx, [rsi+38h]
0x180402b07  lea     r9, [rbp+57h+var_D0]
0x180402b0b  xor     eax, eax
0x180402b0d  lea     r8, [rsp+110h+var_E0]
0x180402b12  xorps   xmm0, xmm0
0x180402b15  mov     [rbp+57h+var_C0], rax
0x180402b19  mov     rax, [rdi+280h]
0x180402b20  lea     ecx, [rbx+7]
0x180402b23  movups  [rsp+110h+var_E0], xmm0
0x180402b28  mov     dword ptr [rsp+110h+var_E0], 10h
0x180402b30  movups  [rbp+57h+var_D0], xmm0
0x180402b34  mov     dword ptr [rbp+57h+var_D0], 18h
0x180402b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180402b40  test    eax, eax
0x180402b42  jnz     short loc_180402B92
0x180402b44  call    cs:__imp_GetLastError
0x180402b4b  nop     dword ptr [rax+rax+00h]
0x180402b50  test    eax, eax
0x180402b52  jz      loc_180402BF1
0x180402b58  call    cs:__imp_GetLastError
0x180402b5f  nop     dword ptr [rax+rax+00h]
0x180402b64  mov     ebx, eax
0x180402b66  test    eax, eax
0x180402b68  jle     short loc_180402B73
0x180402b6a  movzx   ebx, ax
0x180402b6d  or      ebx, 80070000h
0x180402b73  mov     rax, [rdi+260h]
0x180402b7a  lea     r8, [rbp+57h+var_90]
0x180402b7e  lea     rdx, [rbp+57h+var_30]
0x180402b82  mov     [rbp+57h+var_60], 2
0x180402b89  xor     ecx, ecx
0x180402b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180402b90  jmp     short loc_180402C00
0x180402b92  xor     ebx, ebx
0x180402b94  cmp     dword ptr [rbp+57h+var_D0+4], ebx
0x180402b97  jz      short loc_180402B73
0x180402b99  mov     rdx, [rsi+38h]
0x180402b9d  lea     r9, [rbp+57h+var_D0]
0x180402ba1  xor     eax, eax
0x180402ba3  mov     qword ptr [rsp+110h+var_E0+8], rbx
0x180402ba8  xorps   xmm0, xmm0
0x180402bab  mov     [rbp+57h+var_C0], rax
0x180402baf  mov     rax, [rdi+280h]
0x180402bb6  lea     r8, [rsp+110h+var_E0]
0x180402bbb  movups  [rbp+57h+var_D0], xmm0
0x180402bbf  lea     ecx, [rbx+7]
0x180402bc2  mov     dword ptr [rsp+110h+var_E0], 10h
0x180402bca  mov     dword ptr [rsp+110h+var_E0+4], 20000h
0x180402bd2  mov     dword ptr [rbp+57h+var_D0], 18h
0x180402bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180402bde  test    eax, eax
0x180402be0  jz      loc_180402B44
0x180402be6  mov     eax, dword ptr [rbp+57h+var_D0+4]
0x180402be9  test    eax, eax
0x180402beb  jz      short loc_180402B73
0x180402bed  mov     ebx, eax
0x180402bef  jmp     short loc_180402B73
0x180402bf1  mov     ebx, 80004005h
0x180402bf6  jmp     loc_180402B73
0x180402bfb  mov     ebx, 80004001h
0x180402c00  mov     eax, ebx
0x180402c02  mov     rcx, [rbp+57h+var_20]
0x180402c06  xor     rcx, rsp; StackCookie
0x180402c09  call    __security_check_cookie
0x180402c0e  mov     rbx, [rsp+110h+arg_10]
0x180402c16  add     rsp, 100h
0x180402c1d  pop     rdi
0x180402c1e  pop     rsi
0x180402c1f  pop     rbp
0x180402c20  retn
```
