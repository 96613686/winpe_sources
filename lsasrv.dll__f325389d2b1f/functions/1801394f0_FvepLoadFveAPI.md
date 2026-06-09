# FvepLoadFveAPI

- ea: `0x1801394f0`
- end: `0x18013987a`
- name: `FvepLoadFveAPI`
- size: `906`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180138f68`

## callees

- `0x1800b86d0`
- `0x1800b9304`
- `0x1801394f0`
- `0x180139880`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180139784`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180139784`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801395d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801395f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18013961d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180139641`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180139660`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180139684`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801396ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801396d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801396f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180139711`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180139731`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180139750`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18013979f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801397ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801397d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801395d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801395f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18013961d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180139641`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180139660`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180139684`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801396ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801396d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801396f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180139711`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180139731`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180139750`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18013979f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801397ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801397d4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801395b7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801395b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180139766`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180139560`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180139560`

## string_xrefs

- `0x1801395cb`: `FveOpenVolumeW`
- `0x180139594`: `\FVEAPI.DLL`
- `0x180139746`: `FveCommitChanges`
- `0x180139727`: `FveDeleteAuthMethod`
- `0x180139795`: `FveCommitChangesEx`

## pseudocode

```c
__int64 __fastcall FvepLoadFveAPI(HMODULE *a1, __int64 a2)
{
  size_t v4; // rdx
  signed int v5; // eax
  unsigned int v6; // ebx
  HMODULE Library; // rax
  HMODULE v8; // rdi
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v22; // [rsp+20h] [rbp-E0h]
  __int128 v23; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v24; // [rsp+40h] [rbp-C0h]
  __int128 v25; // [rsp+50h] [rbp-B0h]
  __int128 v26; // [rsp+60h] [rbp-A0h]
  __int128 v27; // [rsp+70h] [rbp-90h]
  __int128 v28; // [rsp+80h] [rbp-80h]
  __int128 v29; // [rsp+90h] [rbp-70h]
  __int128 v30; // [rsp+A0h] [rbp-60h]
  __int128 v31; // [rsp+B0h] [rbp-50h]
  __int128 v32; // [rsp+C0h] [rbp-40h]
  INT_PTR (__stdcall *v33)(); // [rsp+D0h] [rbp-30h]
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(&v23, 0, 0xA8u);
  *a1 = 0;
  *(_QWORD *)&v22 = -1;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    goto LABEL_2;
  v6 = StringCchCatW(Buffer, v4, L"\\FVEAPI.DLL");
  if ( (v6 & 0x80000000) != 0 )
    return v6;
  Library = LoadLibraryExW(Buffer, 0, 0);
  v8 = Library;
  if ( Library )
  {
    *((_QWORD *)&v22 + 1) = GetProcAddress(Library, "FveOpenVolumeW");
    if ( *((_QWORD *)&v22 + 1) )
    {
      *(_QWORD *)&v23 = GetProcAddress(v8, "FveCloseVolume");
      if ( (_QWORD)v23 )
      {
        *(_QWORD *)&v25 = GetProcAddress(v8, "FveGetStatus");
        if ( (_QWORD)v25 )
        {
          *(_QWORD *)&v28 = GetProcAddress(v8, "FveAddAuthMethodInformation");
          if ( (_QWORD)v28 )
          {
            *((_QWORD *)&v27 + 1) = GetProcAddress(v8, "FveGetAuthMethodInformation");
            if ( *((_QWORD *)&v27 + 1) )
            {
              *((_QWORD *)&v28 + 1) = GetProcAddress(v8, "FveDeleteAuthMethod");
              if ( *((_QWORD *)&v28 + 1) )
              {
                *((_QWORD *)&v23 + 1) = GetProcAddress(v8, "FveCommitChanges");
                if ( *((_QWORD *)&v23 + 1) )
                {
                  *(_QWORD *)&v24 = GetProcAddress(v8, "FveCommitChangesEx");
                  *(_QWORD *)&v29 = GetProcAddress(v8, "FveGetSecureBootBindingState");
                  ProcAddress = GetProcAddress(v8, "FveControl");
                  goto LABEL_23;
                }
              }
            }
          }
        }
      }
    }
    else
    {
      *((_QWORD *)&v25 + 1) = GetProcAddress(v8, "FveGetStatusBasicW");
      if ( *((_QWORD *)&v25 + 1) )
      {
        *(_QWORD *)&v26 = GetProcAddress(v8, "FveSetFipsAllowDisabled");
        if ( (_QWORD)v26 )
        {
          if ( GetProcAddress(v8, "FveDisableAuthenticationW") )
          {
            *((_QWORD *)&v26 + 1) = GetProcAddress(v8, "FveDisableAuthenticationW");
            if ( *((_QWORD *)&v26 + 1) )
            {
              *(_QWORD *)&v27 = GetProcAddress(v8, "FveEnableAuthenticationW");
              if ( (_QWORD)v27 )
              {
                ProcAddress = v33;
LABEL_23:
                v11 = v23;
                *a1 = v8;
                *(_OWORD *)a2 = v22;
                v12 = v24;
                *(_OWORD *)(a2 + 16) = v11;
                v13 = v25;
                *(_OWORD *)(a2 + 32) = v12;
                v14 = v26;
                *(_OWORD *)(a2 + 48) = v13;
                v15 = v27;
                *(_OWORD *)(a2 + 64) = v14;
                v16 = v28;
                *(_OWORD *)(a2 + 80) = v15;
                v17 = v29;
                *(_OWORD *)(a2 + 96) = v16;
                v18 = v30;
                *(_OWORD *)(a2 + 112) = v17;
                v19 = v31;
                *(_OWORD *)(a2 + 128) = v18;
                v20 = v32;
                *(_OWORD *)(a2 + 144) = v19;
                *(_OWORD *)(a2 + 160) = v20;
                *(_QWORD *)(a2 + 176) = ProcAddress;
                return v6;
              }
            }
          }
        }
      }
    }
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    FreeLibrary(v8);
  }
  else
  {
LABEL_2:
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x1801394f0  mov     [rsp-8+arg_10], rbx
0x1801394f5  mov     [rsp-8+arg_18], rsi
0x1801394fa  push    rbp
0x1801394fb  push    rdi
0x1801394fc  push    r14
0x1801394fe  lea     rbp, [rsp-200h]
0x180139506  sub     rsp, 300h
0x18013950d  mov     rax, cs:__security_cookie
0x180139514  xor     rax, rsp
0x180139517  mov     [rbp+210h+var_20], rax
0x18013951e  mov     rsi, rdx
0x180139521  mov     r14, rcx
0x180139524  xor     edx, edx; Val
0x180139526  lea     rcx, [rbp+210h+Buffer]; void *
0x18013952a  mov     r8d, 208h; Size
0x180139530  call    memset_0
0x180139535  xor     edx, edx; Val
0x180139537  lea     rcx, [rsp+310h+var_2E0]; void *
0x18013953c  mov     r8d, 0A8h; Size
0x180139542  call    memset_0
0x180139547  mov     edx, 104h; uSize
0x18013954c  mov     qword ptr [r14], 0
0x180139553  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x180139557  mov     qword ptr [rsp+310h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x180139560  call    cs:__imp_GetSystemDirectoryW
0x180139567  nop     dword ptr [rax+rax+00h]
0x18013956c  test    eax, eax
0x18013956e  jnz     short loc_180139594
0x180139570  call    cs:__imp_GetLastError
0x180139577  nop     dword ptr [rax+rax+00h]
0x18013957c  mov     ebx, eax
0x18013957e  test    eax, eax
0x180139580  jle     loc_180139850
0x180139586  movzx   ebx, ax
0x180139589  or      ebx, 80070000h
0x18013958f  jmp     loc_180139850
0x180139594  lea     r8, aFveapiDll; "\\FVEAPI.DLL"
0x18013959b  lea     rcx, [rbp+210h+Buffer]; pszDest
0x18013959f  call    StringCchCatW
0x1801395a4  mov     ebx, eax
0x1801395a6  test    eax, eax
0x1801395a8  js      loc_180139850
0x1801395ae  xor     r8d, r8d; dwFlags
0x1801395b1  lea     rcx, [rbp+210h+Buffer]; lpLibFileName
0x1801395b5  xor     edx, edx; hFile
0x1801395b7  call    cs:__imp_LoadLibraryExW
0x1801395be  nop     dword ptr [rax+rax+00h]
0x1801395c3  mov     rdi, rax
0x1801395c6  test    rax, rax
0x1801395c9  jz      short loc_180139570
0x1801395cb  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x1801395d2  mov     rcx, rax; hModule
0x1801395d5  call    cs:__imp_GetProcAddress
0x1801395dc  nop     dword ptr [rax+rax+00h]
0x1801395e1  mov     qword ptr [rsp+310h+var_2F0+8], rax
0x1801395e6  mov     rcx, rdi; hModule
0x1801395e9  test    rax, rax
0x1801395ec  jnz     loc_1801396A7
0x1801395f2  lea     rdx, aFvegetstatusba; "FveGetStatusBasicW"
0x1801395f9  call    cs:__imp_GetProcAddress
0x180139600  nop     dword ptr [rax+rax+00h]
0x180139605  mov     qword ptr [rsp+310h+var_2C0+8], rax
0x18013960a  test    rax, rax
0x18013960d  jz      loc_180139766
0x180139613  lea     rdx, aFvesetfipsallo; "FveSetFipsAllowDisabled"
0x18013961a  mov     rcx, rdi; hModule
0x18013961d  call    cs:__imp_GetProcAddress
0x180139624  nop     dword ptr [rax+rax+00h]
0x180139629  mov     qword ptr [rsp+310h+var_2B0], rax
0x18013962e  test    rax, rax
0x180139631  jz      loc_180139766
0x180139637  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x18013963e  mov     rcx, rdi; hModule
0x180139641  call    cs:__imp_GetProcAddress
0x180139648  nop     dword ptr [rax+rax+00h]
0x18013964d  test    rax, rax
0x180139650  jz      loc_180139766
0x180139656  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x18013965d  mov     rcx, rdi; hModule
0x180139660  call    cs:__imp_GetProcAddress
0x180139667  nop     dword ptr [rax+rax+00h]
0x18013966c  mov     qword ptr [rsp+310h+var_2B0+8], rax
0x180139671  test    rax, rax
0x180139674  jz      loc_180139766
0x18013967a  lea     rdx, aFveenableauthe; "FveEnableAuthenticationW"
0x180139681  mov     rcx, rdi; hModule
0x180139684  call    cs:__imp_GetProcAddress
0x18013968b  nop     dword ptr [rax+rax+00h]
0x180139690  mov     qword ptr [rsp+310h+var_2A0], rax
0x180139695  test    rax, rax
0x180139698  jz      loc_180139766
0x18013969e  mov     rax, [rbp+210h+var_240]
0x1801396a2  jmp     loc_1801397E0
0x1801396a7  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x1801396ae  call    cs:__imp_GetProcAddress
0x1801396b5  nop     dword ptr [rax+rax+00h]
0x1801396ba  mov     qword ptr [rsp+310h+var_2E0], rax
0x1801396bf  test    rax, rax
0x1801396c2  jz      loc_180139766
0x1801396c8  lea     rdx, aFvegetstatus; "FveGetStatus"
0x1801396cf  mov     rcx, rdi; hModule
0x1801396d2  call    cs:__imp_GetProcAddress
0x1801396d9  nop     dword ptr [rax+rax+00h]
0x1801396de  mov     qword ptr [rsp+310h+var_2C0], rax
0x1801396e3  test    rax, rax
0x1801396e6  jz      short loc_180139766
0x1801396e8  lea     rdx, aFveaddauthmeth; "FveAddAuthMethodInformation"
0x1801396ef  mov     rcx, rdi; hModule
0x1801396f2  call    cs:__imp_GetProcAddress
0x1801396f9  nop     dword ptr [rax+rax+00h]
0x1801396fe  mov     qword ptr [rbp+210h+var_290], rax
0x180139702  test    rax, rax
0x180139705  jz      short loc_180139766
0x180139707  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x18013970e  mov     rcx, rdi; hModule
0x180139711  call    cs:__imp_GetProcAddress
0x180139718  nop     dword ptr [rax+rax+00h]
0x18013971d  mov     qword ptr [rsp+310h+var_2A0+8], rax
0x180139722  test    rax, rax
0x180139725  jz      short loc_180139766
0x180139727  lea     rdx, aFvedeleteauthm; "FveDeleteAuthMethod"
0x18013972e  mov     rcx, rdi; hModule
0x180139731  call    cs:__imp_GetProcAddress
0x180139738  nop     dword ptr [rax+rax+00h]
0x18013973d  mov     qword ptr [rbp+210h+var_290+8], rax
0x180139741  test    rax, rax
0x180139744  jz      short loc_180139766
0x180139746  lea     rdx, aFvecommitchang_0; "FveCommitChanges"
0x18013974d  mov     rcx, rdi; hModule
0x180139750  call    cs:__imp_GetProcAddress
0x180139757  nop     dword ptr [rax+rax+00h]
0x18013975c  mov     qword ptr [rsp+310h+var_2E0+8], rax
0x180139761  test    rax, rax
0x180139764  jnz     short loc_180139795
0x180139766  call    cs:__imp_GetLastError
0x18013976d  nop     dword ptr [rax+rax+00h]
0x180139772  mov     ebx, eax
0x180139774  test    eax, eax
0x180139776  jle     short loc_180139781
0x180139778  movzx   ebx, ax
0x18013977b  or      ebx, 80070000h
0x180139781  mov     rcx, rdi; hLibModule
0x180139784  call    cs:__imp_FreeLibrary
0x18013978b  nop     dword ptr [rax+rax+00h]
0x180139790  jmp     loc_180139850
0x180139795  lea     rdx, aFvecommitchang; "FveCommitChangesEx"
0x18013979c  mov     rcx, rdi; hModule
0x18013979f  call    cs:__imp_GetProcAddress
0x1801397a6  nop     dword ptr [rax+rax+00h]
0x1801397ab  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x1801397b2  mov     rcx, rdi; hModule
0x1801397b5  mov     qword ptr [rsp+310h+var_2D0], rax
0x1801397ba  call    cs:__imp_GetProcAddress
0x1801397c1  nop     dword ptr [rax+rax+00h]
0x1801397c6  lea     rdx, aFvecontrol; "FveControl"
0x1801397cd  mov     rcx, rdi; hModule
0x1801397d0  mov     qword ptr [rbp+210h+var_280], rax
0x1801397d4  call    cs:__imp_GetProcAddress
0x1801397db  nop     dword ptr [rax+rax+00h]
0x1801397e0  movaps  xmm0, [rsp+310h+var_2F0]
0x1801397e5  movaps  xmm1, [rsp+310h+var_2E0]
0x1801397ea  mov     [r14], rdi
0x1801397ed  movups  xmmword ptr [rsi], xmm0
0x1801397f0  movaps  xmm0, [rsp+310h+var_2D0]
0x1801397f5  movups  xmmword ptr [rsi+10h], xmm1
0x1801397f9  movaps  xmm1, [rsp+310h+var_2C0]
0x1801397fe  movups  xmmword ptr [rsi+20h], xmm0
0x180139802  movaps  xmm0, [rsp+310h+var_2B0]
0x180139807  movups  xmmword ptr [rsi+30h], xmm1
0x18013980b  movaps  xmm1, [rsp+310h+var_2A0]
0x180139810  movups  xmmword ptr [rsi+40h], xmm0
0x180139814  movaps  xmm0, [rbp+210h+var_290]
0x180139818  movups  xmmword ptr [rsi+50h], xmm1
0x18013981c  movaps  xmm1, [rbp+210h+var_280]
0x180139820  movups  xmmword ptr [rsi+60h], xmm0
0x180139824  movaps  xmm0, [rbp+210h+var_270]
0x180139828  movups  xmmword ptr [rsi+70h], xmm1
0x18013982c  movaps  xmm1, [rbp+210h+var_260]
0x180139830  movups  xmmword ptr [rsi+80h], xmm0
0x180139837  movaps  xmm0, [rbp+210h+var_250]
0x18013983b  movups  xmmword ptr [rsi+90h], xmm1
0x180139842  movups  xmmword ptr [rsi+0A0h], xmm0
0x180139849  mov     [rsi+0B0h], rax
0x180139850  mov     eax, ebx
0x180139852  mov     rcx, [rbp+210h+var_20]
0x180139859  xor     rcx, rsp; StackCookie
0x18013985c  call    __security_check_cookie
0x180139861  lea     r11, [rsp+310h+var_10]
0x180139869  mov     rbx, [r11+30h]
0x18013986d  mov     rsi, [r11+38h]
0x180139871  mov     rsp, r11
0x180139874  pop     r14
0x180139876  pop     rdi
0x180139877  pop     rbp
0x180139878  retn
```
