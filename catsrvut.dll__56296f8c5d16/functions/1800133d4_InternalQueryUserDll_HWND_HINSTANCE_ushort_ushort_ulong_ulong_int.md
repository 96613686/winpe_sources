# InternalQueryUserDll(HWND__ *,HINSTANCE__ *,ushort *,ushort *,ulong,ulong *,int)

- ea: `0x1800133d4`
- end: `0x1800135af`
- name: `?InternalQueryUserDll@@YAJPEAUHWND__@@PEAUHINSTANCE__@@PEAG2KPEAKH@Z`
- size: `475`
- prototype: `int(HWND, HINSTANCE, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180009f84`
- `0x180015f70`

## callees

- `0x18000eaf8`
- `0x1800133d4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013417`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013417`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001344c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013488`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800134c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001344c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013488`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800134c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001345c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013498`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001345c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013498`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180013408`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18001358b`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180013408`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18001358b`

## string_xrefs

- `0x180013442`: `DllRegisterServer`
- `0x18001347e`: `DllUnregisterServer`
- `0x1800134ba`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall InternalQueryUserDll(
        HWND a1,
        HINSTANCE a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned __int16 *v6; // r12
  const WCHAR *v7; // r15
  unsigned int *v8; // rdi
  HMODULE Library; // r14
  unsigned int v10; // ebx
  unsigned int v11; // esi
  __int64 v12; // rdx
  __int64 v13; // rcx
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int LastError; // eax
  int v18; // eax
  unsigned int v23; // [rsp+90h] [rbp+38h]

  v6 = a4;
  v7 = a3;
  v8 = a6;
  *a6 = 0;
  try
  {
    SetErrorMode(0x8001u);
    Library = LoadLibraryExW(v7, 0, 8u);
  }
  catch ( ... )
  {
    v8 = a6;
    v6 = a4;
    v7 = a3;
    goto LABEL_20;
  }
  if ( !Library )
  {
LABEL_20:
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    v11 = a5;
LABEL_23:
    v23 = v10;
    goto LABEL_24;
  }
  v10 = 0;
  v23 = 0;
  *a6 |= 1u;
  v11 = a5;
  if ( (a5 & 2) != 0 )
  {
    if ( GetProcAddress(Library, "DllRegisterServer") )
    {
      *a6 |= 2u;
    }
    else
    {
      v14 = GetLastError();
      v10 = v14;
      if ( v14 > 0 )
        v10 = (unsigned __int16)v14 | 0x80070000;
      v23 = v10;
    }
  }
  if ( (a5 & 4) != 0 )
  {
    if ( GetProcAddress(Library, "DllUnregisterServer") )
    {
      *a6 |= 4u;
    }
    else
    {
      v15 = GetLastError();
      v10 = v15;
      if ( v15 > 0 )
        v10 = (unsigned __int16)v15 | 0x80070000;
      v23 = v10;
    }
  }
  if ( (a5 & 8) != 0 )
  {
    if ( GetProcAddress(Library, "DllGetClassObject") )
    {
      *a6 |= 8u;
      goto LABEL_24;
    }
    v16 = GetLastError();
    v10 = v16;
    if ( v16 > 0 )
      v10 = (unsigned __int16)v16 | 0x80070000;
    goto LABEL_23;
  }
LABEL_24:
  if ( (v11 & 0x10) != 0 )
  {
    z_fIsBasePartition = (v11 >> 5) & 1;
    z_fCopyToRegistry = (v11 & 0x40) == 0;
    z_fDeleteOldKeys = (v11 >> 7) & 1;
    z_fCleanup = (v11 >> 8) & 1;
    z_fRefCountFile = (v11 >> 9) & 1;
    v18 = InternalRegisterUserDllToSelfRegW(v13, v12, v7, v6);
    if ( v18 < 0 )
    {
      v10 = v18;
      v23 = v18;
    }
    else
    {
      *v8 |= 0x10u;
    }
  }
  try
  {
    SetErrorMode(0);
  }
  catch ( ... )
  {
    return v23;
  }
  return v10;
}

```

## disassembly

```asm
0x1800133d4  mov     [rsp+arg_0], rbx
0x1800133d9  mov     [rsp+arg_18], r9
0x1800133de  mov     [rsp+arg_10], r8
0x1800133e3  push    rsi
0x1800133e4  push    rdi
0x1800133e5  push    r12
0x1800133e7  push    r14
0x1800133e9  push    r15
0x1800133eb  sub     rsp, 30h
0x1800133ef  mov     r12, r9
0x1800133f2  mov     r15, r8
0x1800133f5  mov     rdi, [rsp+58h+arg_28]
0x1800133fd  mov     dword ptr [rdi], 0
0x180013403  mov     ecx, 8001h; uMode
0x180013408  call    cs:__imp_SetErrorMode
0x18001340e  xor     edx, edx; hFile
0x180013410  lea     r8d, [rdx+8]; dwFlags
0x180013414  mov     rcx, r15; lpLibFileName
0x180013417  call    cs:__imp_LoadLibraryExW
0x18001341d  mov     r14, rax
0x180013420  test    r14, r14
0x180013423  jz      loc_1800134FD
0x180013429  xor     ebx, ebx
0x18001342b  mov     [rsp+58h+arg_30], ebx
0x180013432  or      dword ptr [rdi], 1
0x180013435  mov     esi, [rsp+58h+arg_20]
0x18001343c  test    sil, 2
0x180013440  jz      short loc_180013478
0x180013442  lea     rdx, aDllregisterser_0; "DllRegisterServer"
0x180013449  mov     rcx, r14; hModule
0x18001344c  call    cs:__imp_GetProcAddress
0x180013452  test    rax, rax
0x180013455  jz      short loc_18001345C
0x180013457  or      dword ptr [rdi], 2
0x18001345a  jmp     short loc_180013478
0x18001345c  call    cs:__imp_GetLastError
0x180013462  mov     ebx, eax
0x180013464  test    eax, eax
0x180013466  jle     short loc_180013471
0x180013468  movzx   ebx, ax
0x18001346b  or      ebx, 80070000h
0x180013471  mov     [rsp+58h+arg_30], ebx
0x180013478  test    sil, 4
0x18001347c  jz      short loc_1800134B4
0x18001347e  lea     rdx, aDllunregisters_0; "DllUnregisterServer"
0x180013485  mov     rcx, r14; hModule
0x180013488  call    cs:__imp_GetProcAddress
0x18001348e  test    rax, rax
0x180013491  jz      short loc_180013498
0x180013493  or      dword ptr [rdi], 4
0x180013496  jmp     short loc_1800134B4
0x180013498  call    cs:__imp_GetLastError
0x18001349e  mov     ebx, eax
0x1800134a0  test    eax, eax
0x1800134a2  jle     short loc_1800134AD
0x1800134a4  movzx   ebx, ax
0x1800134a7  or      ebx, 80070000h
0x1800134ad  mov     [rsp+58h+arg_30], ebx
0x1800134b4  test    sil, 8
0x1800134b8  jz      short loc_180013520
0x1800134ba  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x1800134c1  mov     rcx, r14; hModule
0x1800134c4  call    cs:__imp_GetProcAddress
0x1800134ca  test    rax, rax
0x1800134cd  jz      short loc_1800134D4
0x1800134cf  or      dword ptr [rdi], 8
0x1800134d2  jmp     short loc_180013520
0x1800134d4  call    cs:__imp_GetLastError
0x1800134da  mov     ebx, eax
0x1800134dc  test    eax, eax
0x1800134de  jle     short loc_180013519
0x1800134e0  movzx   ebx, ax
0x1800134e3  or      ebx, 80070000h
0x1800134e9  jmp     short loc_180013519
0x1800134eb  mov     rdi, [rsp+58h+arg_28]
0x1800134f3  mov     r12, [rsp+58h+arg_18]
0x1800134f8  mov     r15, [rsp+58h+arg_10]
0x1800134fd  call    cs:__imp_GetLastError
0x180013503  mov     ebx, eax
0x180013505  test    eax, eax
0x180013507  jle     short loc_180013512
0x180013509  movzx   ebx, ax
0x18001350c  or      ebx, 80070000h
0x180013512  mov     esi, [rsp+58h+arg_20]
0x180013519  mov     [rsp+58h+arg_30], ebx
0x180013520  test    sil, 10h
0x180013524  jz      short loc_180013589
0x180013526  mov     eax, esi
0x180013528  shr     eax, 5
0x18001352b  and     eax, 1
0x18001352e  mov     cs:?z_fIsBasePartition@@3HA, eax; int z_fIsBasePartition
0x180013534  mov     eax, esi
0x180013536  shr     eax, 6
0x180013539  not     eax
0x18001353b  and     eax, 1
0x18001353e  mov     cs:?z_fCopyToRegistry@@3HA, eax; int z_fCopyToRegistry
0x180013544  mov     eax, esi
0x180013546  shr     eax, 7
0x180013549  and     eax, 1
0x18001354c  mov     cs:?z_fDeleteOldKeys@@3HA, eax; int z_fDeleteOldKeys
0x180013552  mov     eax, esi
0x180013554  shr     eax, 8
0x180013557  and     eax, 1
0x18001355a  mov     cs:?z_fCleanup@@3HA, eax; int z_fCleanup
0x180013560  shr     esi, 9
0x180013563  and     esi, 1
0x180013566  mov     cs:?z_fRefCountFile@@3HA, esi; int z_fRefCountFile
0x18001356c  mov     r9, r12
0x18001356f  mov     r8, r15
0x180013572  call    InternalRegisterUserDllToSelfRegW
0x180013577  test    eax, eax
0x180013579  js      short loc_180013580
0x18001357b  or      dword ptr [rdi], 10h
0x18001357e  jmp     short loc_180013589
0x180013580  mov     ebx, eax
0x180013582  mov     [rsp+58h+arg_30], eax
0x180013589  xor     ecx, ecx; uMode
0x18001358b  call    cs:__imp_SetErrorMode
0x180013591  nop
0x180013592  jmp     short loc_18001359B
0x180013594  mov     ebx, [rsp+58h+arg_30]
0x18001359b  mov     eax, ebx
0x18001359d  mov     rbx, [rsp+58h+arg_0]
0x1800135a2  add     rsp, 30h
0x1800135a6  pop     r15
0x1800135a8  pop     r14
0x1800135aa  pop     r12
0x1800135ac  pop     rdi
0x1800135ad  pop     rsi
0x1800135ae  retn
```
