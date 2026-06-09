# Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(char const *,ulong,Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock> &)

- ea: `0x18001b2d4`
- end: `0x18001b4a2`
- name: `??$LoadProvider@VCFakeSRWLock@DelayLoad@Performance@@@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBDKAEAV?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@1@@Z`
- size: `462`
- prototype: `signed int __fastcall(__int64, const char *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b4a8`

## callees

- `0x1800017e0`
- `0x1800069ec`
- `0x18001872c`
- `0x180018998`
- `0x18001b2d4`
- `0x18001df84`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b31a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b31a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b334`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b3de`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001b473`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001b473`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001b3b4`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001b3d4`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001b3b4`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001b3d4`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001b35e`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001b35e`

## string_xrefs

- `0x18001b313`: `kernelbase.dll`
- `0x18001b32a`: `GetTempPath2W`
- `0x18001b41c`: `TdhLoadManifest`

## pseudocode

```c
signed int __fastcall Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(
        __int64 a1,
        const char *a2,
        unsigned int a3,
        __int64 a4)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  DWORD TempPathW; // eax
  DWORD v10; // ebx
  signed int result; // eax
  Microsoft::Windows::Performance::CEventSourceHandler *v12; // rcx
  __int64 (__fastcall *v13)(WCHAR *); // rax
  int v14; // eax
  unsigned int v15; // ebx
  WCHAR *v16; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v17[3]; // [rsp+28h] [rbp-D8h] BYREF
  char v18; // [rsp+40h] [rbp-C0h]
  WCHAR TempFileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+260h] [rbp+160h] BYREF

  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v16 = (WCHAR *)Library;
  if ( Library && (ProcAddress = GetProcAddress(Library, "GetTempPath2W")) != 0 )
    TempPathW = ((__int64 (__fastcall *)(__int64, WCHAR *))ProcAddress)(260, Buffer);
  else
    TempPathW = GetTempPathW(0x104u, Buffer);
  v10 = TempPathW;
  Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&v16);
  if ( v10 && v10 + 1 <= 0x104 || (result = StringCchCopyW(Buffer, 0x104u, L"."), result >= 0) )
  {
    if ( GetTempFileNameW(Buffer, L"xpf", 0, TempFileName) || GetTempFileNameW(L".", L"xpf", 0, TempFileName) )
    {
      result = Microsoft::Windows::Performance::CEventSourceHandler::WriteManifestFile(v12, TempFileName, a2, a3);
      if ( result >= 0 )
      {
        v16 = TempFileName;
        v17[0] = a4;
        v17[1] = "TdhLoadManifest";
        v17[2] = 0;
        v18 = 0;
        if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v17)
          && (v13 = (__int64 (__fastcall *)(WCHAR *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v17),
              v14 = v13(TempFileName),
              (v15 = v14) != 0) )
        {
          if ( v14 > 0 )
            v15 = (unsigned __int16)v14 | 0x80070000;
        }
        else
        {
          v15 = 0;
        }
        DeleteFileW(TempFileName);
        return v15;
      }
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b2d4  mov     [rsp-8+arg_0], rbx
0x18001b2d9  mov     [rsp-8+arg_18], rsi
0x18001b2de  push    rbp
0x18001b2df  push    rdi
0x18001b2e0  push    r14
0x18001b2e2  lea     rbp, [rsp-380h]
0x18001b2ea  sub     rsp, 480h
0x18001b2f1  mov     rax, cs:__security_cookie
0x18001b2f8  xor     rax, rsp
0x18001b2fb  mov     [rbp+390h+var_20], rax
0x18001b302  mov     rdi, r9
0x18001b305  mov     r14d, r8d
0x18001b308  mov     rsi, rdx
0x18001b30b  xor     edx, edx; hFile
0x18001b30d  mov     r8d, 800h; dwFlags
0x18001b313  lea     rcx, ModuleName; "kernelbase.dll"
0x18001b31a  call    cs:__imp_LoadLibraryExW
0x18001b320  mov     [rsp+490h+var_470], rax
0x18001b325  test    rax, rax
0x18001b328  jz      short loc_18001B352
0x18001b32a  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18001b331  mov     rcx, rax; hModule
0x18001b334  call    cs:__imp_GetProcAddress
0x18001b33a  test    rax, rax
0x18001b33d  jz      short loc_18001B352
0x18001b33f  lea     rdx, [rbp+390h+Buffer]
0x18001b346  mov     ecx, 104h
0x18001b34b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b350  jmp     short loc_18001B364
0x18001b352  lea     rdx, [rbp+390h+Buffer]; lpBuffer
0x18001b359  mov     ecx, 104h; nBufferLength
0x18001b35e  call    cs:__imp_GetTempPathW
0x18001b364  mov     ebx, eax
0x18001b366  lea     rcx, [rsp+490h+var_470]
0x18001b36b  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x18001b370  test    ebx, ebx
0x18001b372  jz      short loc_18001B37E
0x18001b374  lea     eax, [rbx+1]
0x18001b377  cmp     eax, 104h
0x18001b37c  jbe     short loc_18001B39E
0x18001b37e  lea     r8, PathName; "."
0x18001b385  mov     edx, 104h; unsigned __int64
0x18001b38a  lea     rcx, [rbp+390h+Buffer]; unsigned __int16 *
0x18001b391  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b396  test    eax, eax
0x18001b398  js      loc_18001B47B
0x18001b39e  lea     r9, [rsp+490h+TempFileName]; lpTempFileName
0x18001b3a3  xor     r8d, r8d; uUnique
0x18001b3a6  lea     rdx, PrefixString; "xpf"
0x18001b3ad  lea     rcx, [rbp+390h+Buffer]; lpPathName
0x18001b3b4  call    cs:__imp_GetTempFileNameW
0x18001b3ba  test    eax, eax
0x18001b3bc  jnz     short loc_18001B3F9
0x18001b3be  lea     r9, [rsp+490h+TempFileName]; lpTempFileName
0x18001b3c3  xor     r8d, r8d; uUnique
0x18001b3c6  lea     rdx, PrefixString; "xpf"
0x18001b3cd  lea     rcx, PathName; "."
0x18001b3d4  call    cs:__imp_GetTempFileNameW
0x18001b3da  test    eax, eax
0x18001b3dc  jnz     short loc_18001B3F9
0x18001b3de  call    cs:__imp_GetLastError
0x18001b3e4  test    eax, eax
0x18001b3e6  jle     loc_18001B47B
0x18001b3ec  movzx   eax, ax
0x18001b3ef  or      eax, 80070000h
0x18001b3f4  jmp     loc_18001B47B
0x18001b3f9  mov     r9d, r14d; unsigned int
0x18001b3fc  mov     r8, rsi; char *
0x18001b3ff  lea     rdx, [rsp+490h+TempFileName]; unsigned __int16 *
0x18001b404  call    ?WriteManifestFile@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBGPEBDK@Z; Microsoft::Windows::Performance::CEventSourceHandler::WriteManifestFile(ushort const *,char const *,ulong)
0x18001b409  test    eax, eax
0x18001b40b  js      short loc_18001B47B
0x18001b40d  lea     rax, [rsp+490h+TempFileName]
0x18001b412  mov     [rsp+490h+var_470], rax
0x18001b417  mov     [rsp+490h+var_468], rdi
0x18001b41c  lea     rax, aTdhloadmanifes; "TdhLoadManifest"
0x18001b423  mov     [rsp+490h+var_460], rax
0x18001b428  mov     [rsp+490h+var_458], 0
0x18001b431  mov     [rsp+490h+var_450], 0
0x18001b436  lea     rcx, [rsp+490h+var_468]
0x18001b43b  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001b440  test    rax, rax
0x18001b443  jz      short loc_18001B46C
0x18001b445  lea     rcx, [rsp+490h+var_468]
0x18001b44a  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001b44f  lea     rcx, [rsp+490h+TempFileName]
0x18001b454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b459  mov     ebx, eax
0x18001b45b  test    eax, eax
0x18001b45d  jz      short loc_18001B46C
0x18001b45f  jle     short loc_18001B46E
0x18001b461  movzx   ebx, ax
0x18001b464  or      ebx, 80070000h
0x18001b46a  jmp     short loc_18001B46E
0x18001b46c  xor     ebx, ebx
0x18001b46e  lea     rcx, [rsp+490h+TempFileName]; lpFileName
0x18001b473  call    cs:__imp_DeleteFileW
0x18001b479  mov     eax, ebx
0x18001b47b  mov     rcx, [rbp+390h+var_20]
0x18001b482  xor     rcx, rsp; StackCookie
0x18001b485  call    __security_check_cookie
0x18001b48a  lea     r11, [rsp+490h+var_10]
0x18001b492  mov     rbx, [r11+20h]
0x18001b496  mov     rsi, [r11+38h]
0x18001b49a  mov     rsp, r11
0x18001b49d  pop     r14
0x18001b49f  pop     rdi
0x18001b4a0  pop     rbp
0x18001b4a1  retn
```
