# FvepLoadFveAPI

- ea: `0x1801f5020`
- end: `0x1801f53af`
- name: `FvepLoadFveAPI`
- size: `911`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801f4e0c`

## callees

- `0x180006350`
- `0x180006dd4`
- `0x1801f5020`
- `0x1801f53b8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801f5092`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801f5092`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f50a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f529b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f50a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f529b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801f50ec`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801f50ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801f52b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801f52b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f510a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f512e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5152`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5176`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5195`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f51b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f51e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5207`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5227`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5246`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5266`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5285`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f52d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f52ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5309`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f510a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f512e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5152`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5176`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5195`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f51b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f51e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5207`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5227`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5246`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5266`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5285`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f52d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f52ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801f5309`

## string_xrefs

- `0x1801f50c6`: `\FVEAPI.DLL`
- `0x1801f5100`: `FveOpenVolumeW`
- `0x1801f525c`: `FveDeleteAuthMethod`
- `0x1801f527b`: `FveCommitChanges`
- `0x1801f52ca`: `FveCommitChangesEx`

## pseudocode

```c
__int64 __fastcall FvepLoadFveAPI(HMODULE *a1, __int64 a2)
{
  signed int v4; // eax
  unsigned int v5; // ebx
  HMODULE Library; // rax
  HMODULE v7; // rdi
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v21; // [rsp+20h] [rbp-E0h]
  __int128 v22; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+40h] [rbp-C0h]
  __int128 v24; // [rsp+50h] [rbp-B0h]
  __int128 v25; // [rsp+60h] [rbp-A0h]
  __int128 v26; // [rsp+70h] [rbp-90h]
  __int128 v27; // [rsp+80h] [rbp-80h]
  __int128 v28; // [rsp+90h] [rbp-70h]
  __int128 v29; // [rsp+A0h] [rbp-60h]
  __int128 v30; // [rsp+B0h] [rbp-50h]
  __int128 v31; // [rsp+C0h] [rbp-40h]
  INT_PTR (__stdcall *v32)(); // [rsp+D0h] [rbp-30h]
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(&v22, 0, 0xA8u);
  *a1 = 0;
  *(_QWORD *)&v21 = -1;
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    goto LABEL_2;
  v5 = StringCchCatW(Buffer, 0x104u, L"\\FVEAPI.DLL");
  if ( (v5 & 0x80000000) != 0 )
    return v5;
  Library = LoadLibraryExW(Buffer, 0, 0);
  v7 = Library;
  if ( Library )
  {
    *((_QWORD *)&v21 + 1) = GetProcAddress(Library, "FveOpenVolumeW");
    if ( *((_QWORD *)&v21 + 1) )
    {
      *(_QWORD *)&v22 = GetProcAddress(v7, "FveCloseVolume");
      if ( (_QWORD)v22 )
      {
        *(_QWORD *)&v24 = GetProcAddress(v7, "FveGetStatus");
        if ( (_QWORD)v24 )
        {
          *(_QWORD *)&v27 = GetProcAddress(v7, "FveAddAuthMethodInformation");
          if ( (_QWORD)v27 )
          {
            *((_QWORD *)&v26 + 1) = GetProcAddress(v7, "FveGetAuthMethodInformation");
            if ( *((_QWORD *)&v26 + 1) )
            {
              *((_QWORD *)&v27 + 1) = GetProcAddress(v7, "FveDeleteAuthMethod");
              if ( *((_QWORD *)&v27 + 1) )
              {
                *((_QWORD *)&v22 + 1) = GetProcAddress(v7, "FveCommitChanges");
                if ( *((_QWORD *)&v22 + 1) )
                {
                  *(_QWORD *)&v23 = GetProcAddress(v7, "FveCommitChangesEx");
                  *(_QWORD *)&v28 = GetProcAddress(v7, "FveGetSecureBootBindingState");
                  ProcAddress = GetProcAddress(v7, "FveControl");
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
      *((_QWORD *)&v24 + 1) = GetProcAddress(v7, "FveGetStatusBasicW");
      if ( *((_QWORD *)&v24 + 1) )
      {
        *(_QWORD *)&v25 = GetProcAddress(v7, "FveSetFipsAllowDisabled");
        if ( (_QWORD)v25 )
        {
          if ( GetProcAddress(v7, "FveDisableAuthenticationW") )
          {
            *((_QWORD *)&v25 + 1) = GetProcAddress(v7, "FveDisableAuthenticationW");
            if ( *((_QWORD *)&v25 + 1) )
            {
              *(_QWORD *)&v26 = GetProcAddress(v7, "FveEnableAuthenticationW");
              if ( (_QWORD)v26 )
              {
                ProcAddress = v32;
LABEL_23:
                v10 = v22;
                *a1 = v7;
                *(_OWORD *)a2 = v21;
                v11 = v23;
                *(_OWORD *)(a2 + 16) = v10;
                v12 = v24;
                *(_OWORD *)(a2 + 32) = v11;
                v13 = v25;
                *(_OWORD *)(a2 + 48) = v12;
                v14 = v26;
                *(_OWORD *)(a2 + 64) = v13;
                v15 = v27;
                *(_OWORD *)(a2 + 80) = v14;
                v16 = v28;
                *(_OWORD *)(a2 + 96) = v15;
                v17 = v29;
                *(_OWORD *)(a2 + 112) = v16;
                v18 = v30;
                *(_OWORD *)(a2 + 128) = v17;
                v19 = v31;
                *(_OWORD *)(a2 + 144) = v18;
                *(_OWORD *)(a2 + 160) = v19;
                *(_QWORD *)(a2 + 176) = ProcAddress;
                return v5;
              }
            }
          }
        }
      }
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    FreeLibrary(v7);
  }
  else
  {
LABEL_2:
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  return v5;
}

```

## disassembly

```asm
0x1801f5020  mov     [rsp-8+arg_10], rbx
0x1801f5025  mov     [rsp-8+arg_18], rsi
0x1801f502a  push    rbp
0x1801f502b  push    rdi
0x1801f502c  push    r14
0x1801f502e  lea     rbp, [rsp-200h]
0x1801f5036  sub     rsp, 300h
0x1801f503d  mov     rax, cs:__security_cookie
0x1801f5044  xor     rax, rsp
0x1801f5047  mov     [rbp+210h+var_20], rax
0x1801f504e  mov     rsi, rdx
0x1801f5051  mov     r14, rcx
0x1801f5054  xor     edx, edx; Val
0x1801f5056  lea     rcx, [rbp+210h+Buffer]; void *
0x1801f505a  mov     r8d, 208h; Size
0x1801f5060  call    memset_0
0x1801f5065  xor     edx, edx; Val
0x1801f5067  lea     rcx, [rsp+310h+var_2E0]; void *
0x1801f506c  mov     r8d, 0A8h; Size
0x1801f5072  call    memset_0
0x1801f5077  mov     ebx, 104h
0x1801f507c  mov     qword ptr [r14], 0
0x1801f5083  mov     edx, ebx; uSize
0x1801f5085  mov     qword ptr [rsp+310h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x1801f508e  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x1801f5092  call    cs:__imp_GetSystemDirectoryW
0x1801f5099  nop     dword ptr [rax+rax+00h]
0x1801f509e  test    eax, eax
0x1801f50a0  jnz     short loc_1801F50C6
0x1801f50a2  call    cs:__imp_GetLastError
0x1801f50a9  nop     dword ptr [rax+rax+00h]
0x1801f50ae  mov     ebx, eax
0x1801f50b0  test    eax, eax
0x1801f50b2  jle     loc_1801F5385
0x1801f50b8  movzx   ebx, ax
0x1801f50bb  or      ebx, 80070000h
0x1801f50c1  jmp     loc_1801F5385
0x1801f50c6  lea     r8, aFveapiDll_0; "\\FVEAPI.DLL"
0x1801f50cd  mov     rdx, rbx; cchDest
0x1801f50d0  lea     rcx, [rbp+210h+Buffer]; pszDest
0x1801f50d4  call    StringCchCatW
0x1801f50d9  mov     ebx, eax
0x1801f50db  test    eax, eax
0x1801f50dd  js      loc_1801F5385
0x1801f50e3  xor     r8d, r8d; dwFlags
0x1801f50e6  lea     rcx, [rbp+210h+Buffer]; lpLibFileName
0x1801f50ea  xor     edx, edx; hFile
0x1801f50ec  call    cs:__imp_LoadLibraryExW
0x1801f50f3  nop     dword ptr [rax+rax+00h]
0x1801f50f8  mov     rdi, rax
0x1801f50fb  test    rax, rax
0x1801f50fe  jz      short loc_1801F50A2
0x1801f5100  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x1801f5107  mov     rcx, rax; hModule
0x1801f510a  call    cs:__imp_GetProcAddress
0x1801f5111  nop     dword ptr [rax+rax+00h]
0x1801f5116  mov     qword ptr [rsp+310h+var_2F0+8], rax
0x1801f511b  mov     rcx, rdi; hModule
0x1801f511e  test    rax, rax
0x1801f5121  jnz     loc_1801F51DC
0x1801f5127  lea     rdx, aFvegetstatusba; "FveGetStatusBasicW"
0x1801f512e  call    cs:__imp_GetProcAddress
0x1801f5135  nop     dword ptr [rax+rax+00h]
0x1801f513a  mov     qword ptr [rsp+310h+var_2C0+8], rax
0x1801f513f  test    rax, rax
0x1801f5142  jz      loc_1801F529B
0x1801f5148  lea     rdx, aFvesetfipsallo; "FveSetFipsAllowDisabled"
0x1801f514f  mov     rcx, rdi; hModule
0x1801f5152  call    cs:__imp_GetProcAddress
0x1801f5159  nop     dword ptr [rax+rax+00h]
0x1801f515e  mov     qword ptr [rsp+310h+var_2B0], rax
0x1801f5163  test    rax, rax
0x1801f5166  jz      loc_1801F529B
0x1801f516c  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x1801f5173  mov     rcx, rdi; hModule
0x1801f5176  call    cs:__imp_GetProcAddress
0x1801f517d  nop     dword ptr [rax+rax+00h]
0x1801f5182  test    rax, rax
0x1801f5185  jz      loc_1801F529B
0x1801f518b  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x1801f5192  mov     rcx, rdi; hModule
0x1801f5195  call    cs:__imp_GetProcAddress
0x1801f519c  nop     dword ptr [rax+rax+00h]
0x1801f51a1  mov     qword ptr [rsp+310h+var_2B0+8], rax
0x1801f51a6  test    rax, rax
0x1801f51a9  jz      loc_1801F529B
0x1801f51af  lea     rdx, aFveenableauthe; "FveEnableAuthenticationW"
0x1801f51b6  mov     rcx, rdi; hModule
0x1801f51b9  call    cs:__imp_GetProcAddress
0x1801f51c0  nop     dword ptr [rax+rax+00h]
0x1801f51c5  mov     qword ptr [rsp+310h+var_2A0], rax
0x1801f51ca  test    rax, rax
0x1801f51cd  jz      loc_1801F529B
0x1801f51d3  mov     rax, [rbp+210h+var_240]
0x1801f51d7  jmp     loc_1801F5315
0x1801f51dc  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x1801f51e3  call    cs:__imp_GetProcAddress
0x1801f51ea  nop     dword ptr [rax+rax+00h]
0x1801f51ef  mov     qword ptr [rsp+310h+var_2E0], rax
0x1801f51f4  test    rax, rax
0x1801f51f7  jz      loc_1801F529B
0x1801f51fd  lea     rdx, aFvegetstatus; "FveGetStatus"
0x1801f5204  mov     rcx, rdi; hModule
0x1801f5207  call    cs:__imp_GetProcAddress
0x1801f520e  nop     dword ptr [rax+rax+00h]
0x1801f5213  mov     qword ptr [rsp+310h+var_2C0], rax
0x1801f5218  test    rax, rax
0x1801f521b  jz      short loc_1801F529B
0x1801f521d  lea     rdx, aFveaddauthmeth; "FveAddAuthMethodInformation"
0x1801f5224  mov     rcx, rdi; hModule
0x1801f5227  call    cs:__imp_GetProcAddress
0x1801f522e  nop     dword ptr [rax+rax+00h]
0x1801f5233  mov     qword ptr [rbp+210h+var_290], rax
0x1801f5237  test    rax, rax
0x1801f523a  jz      short loc_1801F529B
0x1801f523c  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x1801f5243  mov     rcx, rdi; hModule
0x1801f5246  call    cs:__imp_GetProcAddress
0x1801f524d  nop     dword ptr [rax+rax+00h]
0x1801f5252  mov     qword ptr [rsp+310h+var_2A0+8], rax
0x1801f5257  test    rax, rax
0x1801f525a  jz      short loc_1801F529B
0x1801f525c  lea     rdx, aFvedeleteauthm; "FveDeleteAuthMethod"
0x1801f5263  mov     rcx, rdi; hModule
0x1801f5266  call    cs:__imp_GetProcAddress
0x1801f526d  nop     dword ptr [rax+rax+00h]
0x1801f5272  mov     qword ptr [rbp+210h+var_290+8], rax
0x1801f5276  test    rax, rax
0x1801f5279  jz      short loc_1801F529B
0x1801f527b  lea     rdx, aFvecommitchang_0; "FveCommitChanges"
0x1801f5282  mov     rcx, rdi; hModule
0x1801f5285  call    cs:__imp_GetProcAddress
0x1801f528c  nop     dword ptr [rax+rax+00h]
0x1801f5291  mov     qword ptr [rsp+310h+var_2E0+8], rax
0x1801f5296  test    rax, rax
0x1801f5299  jnz     short loc_1801F52CA
0x1801f529b  call    cs:__imp_GetLastError
0x1801f52a2  nop     dword ptr [rax+rax+00h]
0x1801f52a7  mov     ebx, eax
0x1801f52a9  test    eax, eax
0x1801f52ab  jle     short loc_1801F52B6
0x1801f52ad  movzx   ebx, ax
0x1801f52b0  or      ebx, 80070000h
0x1801f52b6  mov     rcx, rdi; hLibModule
0x1801f52b9  call    cs:__imp_FreeLibrary
0x1801f52c0  nop     dword ptr [rax+rax+00h]
0x1801f52c5  jmp     loc_1801F5385
0x1801f52ca  lea     rdx, aFvecommitchang; "FveCommitChangesEx"
0x1801f52d1  mov     rcx, rdi; hModule
0x1801f52d4  call    cs:__imp_GetProcAddress
0x1801f52db  nop     dword ptr [rax+rax+00h]
0x1801f52e0  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x1801f52e7  mov     rcx, rdi; hModule
0x1801f52ea  mov     qword ptr [rsp+310h+var_2D0], rax
0x1801f52ef  call    cs:__imp_GetProcAddress
0x1801f52f6  nop     dword ptr [rax+rax+00h]
0x1801f52fb  lea     rdx, aFvecontrol; "FveControl"
0x1801f5302  mov     rcx, rdi; hModule
0x1801f5305  mov     qword ptr [rbp+210h+var_280], rax
0x1801f5309  call    cs:__imp_GetProcAddress
0x1801f5310  nop     dword ptr [rax+rax+00h]
0x1801f5315  movaps  xmm0, [rsp+310h+var_2F0]
0x1801f531a  movaps  xmm1, [rsp+310h+var_2E0]
0x1801f531f  mov     [r14], rdi
0x1801f5322  movups  xmmword ptr [rsi], xmm0
0x1801f5325  movaps  xmm0, [rsp+310h+var_2D0]
0x1801f532a  movups  xmmword ptr [rsi+10h], xmm1
0x1801f532e  movaps  xmm1, [rsp+310h+var_2C0]
0x1801f5333  movups  xmmword ptr [rsi+20h], xmm0
0x1801f5337  movaps  xmm0, [rsp+310h+var_2B0]
0x1801f533c  movups  xmmword ptr [rsi+30h], xmm1
0x1801f5340  movaps  xmm1, [rsp+310h+var_2A0]
0x1801f5345  movups  xmmword ptr [rsi+40h], xmm0
0x1801f5349  movaps  xmm0, [rbp+210h+var_290]
0x1801f534d  movups  xmmword ptr [rsi+50h], xmm1
0x1801f5351  movaps  xmm1, [rbp+210h+var_280]
0x1801f5355  movups  xmmword ptr [rsi+60h], xmm0
0x1801f5359  movaps  xmm0, [rbp+210h+var_270]
0x1801f535d  movups  xmmword ptr [rsi+70h], xmm1
0x1801f5361  movaps  xmm1, [rbp+210h+var_260]
0x1801f5365  movups  xmmword ptr [rsi+80h], xmm0
0x1801f536c  movaps  xmm0, [rbp+210h+var_250]
0x1801f5370  movups  xmmword ptr [rsi+90h], xmm1
0x1801f5377  movups  xmmword ptr [rsi+0A0h], xmm0
0x1801f537e  mov     [rsi+0B0h], rax
0x1801f5385  mov     eax, ebx
0x1801f5387  mov     rcx, [rbp+210h+var_20]
0x1801f538e  xor     rcx, rsp; StackCookie
0x1801f5391  call    __security_check_cookie
0x1801f5396  lea     r11, [rsp+310h+var_10]
0x1801f539e  mov     rbx, [r11+30h]
0x1801f53a2  mov     rsi, [r11+38h]
0x1801f53a6  mov     rsp, r11
0x1801f53a9  pop     r14
0x1801f53ab  pop     rdi
0x1801f53ac  pop     rbp
0x1801f53ad  retn
```
