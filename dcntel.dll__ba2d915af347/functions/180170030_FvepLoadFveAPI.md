# FvepLoadFveAPI

- ea: `0x180170030`
- end: `0x180170346`
- name: `FvepLoadFveAPI`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18016fde4`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x180012734`
- `0x180170030`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801700f0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801700f0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180170269`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180170269`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170108`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170126`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170144`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170162`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18017017b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170199`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801701bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801701db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801701f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18017020e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170228`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170241`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18017027e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170293`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801702a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170108`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170126`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170144`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170162`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18017017b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170199`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801701bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801701db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801701f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18017020e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170228`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170241`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18017027e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180170293`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801702a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801700ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180170251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801700ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180170251`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801700a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801700a2`

## string_xrefs

- `0x18017021e`: `FveDeleteAuthMethod`
- `0x180170237`: `FveCommitChanges`
- `0x180170274`: `FveCommitChangesEx`
- `0x1801700ca`: `\FVEAPI.DLL`
- `0x1801700fe`: `FveOpenVolumeW`

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
0x180170030  mov     [rsp-8+arg_10], rbx
0x180170035  mov     [rsp-8+arg_18], rsi
0x18017003a  push    rbp
0x18017003b  push    rdi
0x18017003c  push    r14
0x18017003e  lea     rbp, [rsp-200h]
0x180170046  sub     rsp, 300h
0x18017004d  mov     rax, cs:__security_cookie
0x180170054  xor     rax, rsp
0x180170057  mov     [rbp+210h+var_20], rax
0x18017005e  mov     rsi, rdx
0x180170061  mov     r14, rcx
0x180170064  xor     edx, edx; Val
0x180170066  lea     rcx, [rbp+210h+Buffer]; void *
0x18017006a  mov     r8d, 208h; Size
0x180170070  call    memset_0
0x180170075  xor     edx, edx; Val
0x180170077  lea     rcx, [rsp+310h+var_2E0]; void *
0x18017007c  mov     r8d, 0A8h; Size
0x180170082  call    memset_0
0x180170087  mov     ebx, 104h
0x18017008c  mov     qword ptr [r14], 0
0x180170093  mov     edx, ebx; uSize
0x180170095  mov     qword ptr [rsp+310h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x18017009e  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x1801700a2  call    cs:__imp_GetSystemDirectoryW
0x1801700a8  test    eax, eax
0x1801700aa  jnz     short loc_1801700CA
0x1801700ac  call    cs:__imp_GetLastError
0x1801700b2  mov     ebx, eax
0x1801700b4  test    eax, eax
0x1801700b6  jle     loc_18017031D
0x1801700bc  movzx   ebx, ax
0x1801700bf  or      ebx, 80070000h
0x1801700c5  jmp     loc_18017031D
0x1801700ca  lea     r8, aFveapiDll_1; "\\FVEAPI.DLL"
0x1801700d1  mov     rdx, rbx; unsigned __int64
0x1801700d4  lea     rcx, [rbp+210h+Buffer]; unsigned __int16 *
0x1801700d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801700dd  mov     ebx, eax
0x1801700df  test    eax, eax
0x1801700e1  js      loc_18017031D
0x1801700e7  xor     r8d, r8d; dwFlags
0x1801700ea  lea     rcx, [rbp+210h+Buffer]; lpLibFileName
0x1801700ee  xor     edx, edx; hFile
0x1801700f0  call    cs:__imp_LoadLibraryExW
0x1801700f6  mov     rdi, rax
0x1801700f9  test    rax, rax
0x1801700fc  jz      short loc_1801700AC
0x1801700fe  lea     rdx, aFveopenvolumew_0; "FveOpenVolumeW"
0x180170105  mov     rcx, rax; hModule
0x180170108  call    cs:__imp_GetProcAddress
0x18017010e  mov     qword ptr [rsp+310h+var_2F0+8], rax
0x180170113  mov     rcx, rdi; hModule
0x180170116  test    rax, rax
0x180170119  jnz     loc_1801701B6
0x18017011f  lea     rdx, aFvegetstatusba; "FveGetStatusBasicW"
0x180170126  call    cs:__imp_GetProcAddress
0x18017012c  mov     qword ptr [rsp+310h+var_2C0+8], rax
0x180170131  test    rax, rax
0x180170134  jz      loc_180170251
0x18017013a  lea     rdx, aFvesetfipsallo; "FveSetFipsAllowDisabled"
0x180170141  mov     rcx, rdi; hModule
0x180170144  call    cs:__imp_GetProcAddress
0x18017014a  mov     qword ptr [rsp+310h+var_2B0], rax
0x18017014f  test    rax, rax
0x180170152  jz      loc_180170251
0x180170158  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x18017015f  mov     rcx, rdi; hModule
0x180170162  call    cs:__imp_GetProcAddress
0x180170168  test    rax, rax
0x18017016b  jz      loc_180170251
0x180170171  lea     rdx, aFvedisableauth; "FveDisableAuthenticationW"
0x180170178  mov     rcx, rdi; hModule
0x18017017b  call    cs:__imp_GetProcAddress
0x180170181  mov     qword ptr [rsp+310h+var_2B0+8], rax
0x180170186  test    rax, rax
0x180170189  jz      loc_180170251
0x18017018f  lea     rdx, aFveenableauthe; "FveEnableAuthenticationW"
0x180170196  mov     rcx, rdi; hModule
0x180170199  call    cs:__imp_GetProcAddress
0x18017019f  mov     qword ptr [rsp+310h+var_2A0], rax
0x1801701a4  test    rax, rax
0x1801701a7  jz      loc_180170251
0x1801701ad  mov     rax, [rbp+210h+var_240]
0x1801701b1  jmp     loc_1801702AD
0x1801701b6  lea     rdx, aFveclosevolume_0; "FveCloseVolume"
0x1801701bd  call    cs:__imp_GetProcAddress
0x1801701c3  mov     qword ptr [rsp+310h+var_2E0], rax
0x1801701c8  test    rax, rax
0x1801701cb  jz      loc_180170251
0x1801701d1  lea     rdx, aFvegetstatus_0; "FveGetStatus"
0x1801701d8  mov     rcx, rdi; hModule
0x1801701db  call    cs:__imp_GetProcAddress
0x1801701e1  mov     qword ptr [rsp+310h+var_2C0], rax
0x1801701e6  test    rax, rax
0x1801701e9  jz      short loc_180170251
0x1801701eb  lea     rdx, aFveaddauthmeth; "FveAddAuthMethodInformation"
0x1801701f2  mov     rcx, rdi; hModule
0x1801701f5  call    cs:__imp_GetProcAddress
0x1801701fb  mov     qword ptr [rbp+210h+var_290], rax
0x1801701ff  test    rax, rax
0x180170202  jz      short loc_180170251
0x180170204  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x18017020b  mov     rcx, rdi; hModule
0x18017020e  call    cs:__imp_GetProcAddress
0x180170214  mov     qword ptr [rsp+310h+var_2A0+8], rax
0x180170219  test    rax, rax
0x18017021c  jz      short loc_180170251
0x18017021e  lea     rdx, aFvedeleteauthm; "FveDeleteAuthMethod"
0x180170225  mov     rcx, rdi; hModule
0x180170228  call    cs:__imp_GetProcAddress
0x18017022e  mov     qword ptr [rbp+210h+var_290+8], rax
0x180170232  test    rax, rax
0x180170235  jz      short loc_180170251
0x180170237  lea     rdx, aFvecommitchang_0; "FveCommitChanges"
0x18017023e  mov     rcx, rdi; hModule
0x180170241  call    cs:__imp_GetProcAddress
0x180170247  mov     qword ptr [rsp+310h+var_2E0+8], rax
0x18017024c  test    rax, rax
0x18017024f  jnz     short loc_180170274
0x180170251  call    cs:__imp_GetLastError
0x180170257  mov     ebx, eax
0x180170259  test    eax, eax
0x18017025b  jle     short loc_180170266
0x18017025d  movzx   ebx, ax
0x180170260  or      ebx, 80070000h
0x180170266  mov     rcx, rdi; hLibModule
0x180170269  call    cs:__imp_FreeLibrary
0x18017026f  jmp     loc_18017031D
0x180170274  lea     rdx, aFvecommitchang; "FveCommitChangesEx"
0x18017027b  mov     rcx, rdi; hModule
0x18017027e  call    cs:__imp_GetProcAddress
0x180170284  lea     rdx, aFvegetsecurebo; "FveGetSecureBootBindingState"
0x18017028b  mov     rcx, rdi; hModule
0x18017028e  mov     qword ptr [rsp+310h+var_2D0], rax
0x180170293  call    cs:__imp_GetProcAddress
0x180170299  lea     rdx, aFvecontrol; "FveControl"
0x1801702a0  mov     rcx, rdi; hModule
0x1801702a3  mov     qword ptr [rbp+210h+var_280], rax
0x1801702a7  call    cs:__imp_GetProcAddress
0x1801702ad  movaps  xmm0, [rsp+310h+var_2F0]
0x1801702b2  movaps  xmm1, [rsp+310h+var_2E0]
0x1801702b7  mov     [r14], rdi
0x1801702ba  movups  xmmword ptr [rsi], xmm0
0x1801702bd  movaps  xmm0, [rsp+310h+var_2D0]
0x1801702c2  movups  xmmword ptr [rsi+10h], xmm1
0x1801702c6  movaps  xmm1, [rsp+310h+var_2C0]
0x1801702cb  movups  xmmword ptr [rsi+20h], xmm0
0x1801702cf  movaps  xmm0, [rsp+310h+var_2B0]
0x1801702d4  movups  xmmword ptr [rsi+30h], xmm1
0x1801702d8  movaps  xmm1, [rsp+310h+var_2A0]
0x1801702dd  movups  xmmword ptr [rsi+40h], xmm0
0x1801702e1  movaps  xmm0, [rbp+210h+var_290]
0x1801702e5  movups  xmmword ptr [rsi+50h], xmm1
0x1801702e9  movaps  xmm1, [rbp+210h+var_280]
0x1801702ed  movups  xmmword ptr [rsi+60h], xmm0
0x1801702f1  movaps  xmm0, [rbp+210h+var_270]
0x1801702f5  movups  xmmword ptr [rsi+70h], xmm1
0x1801702f9  movaps  xmm1, [rbp+210h+var_260]
0x1801702fd  movups  xmmword ptr [rsi+80h], xmm0
0x180170304  movaps  xmm0, [rbp+210h+var_250]
0x180170308  movups  xmmword ptr [rsi+90h], xmm1
0x18017030f  movups  xmmword ptr [rsi+0A0h], xmm0
0x180170316  mov     [rsi+0B0h], rax
0x18017031d  mov     eax, ebx
0x18017031f  mov     rcx, [rbp+210h+var_20]
0x180170326  xor     rcx, rsp; StackCookie
0x180170329  call    __security_check_cookie
0x18017032e  lea     r11, [rsp+310h+var_10]
0x180170336  mov     rbx, [r11+30h]
0x18017033a  mov     rsi, [r11+38h]
0x18017033e  mov     rsp, r11
0x180170341  pop     r14
0x180170343  pop     rdi
0x180170344  pop     rbp
0x180170345  retn
```
