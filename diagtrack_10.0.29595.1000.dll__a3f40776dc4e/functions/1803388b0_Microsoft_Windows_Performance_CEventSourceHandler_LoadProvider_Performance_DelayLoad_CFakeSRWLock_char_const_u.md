# Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(char const *,ulong,Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock> &)

- ea: `0x1803388b0`
- end: `0x180338a7e`
- name: `??$LoadProvider@VCFakeSRWLock@DelayLoad@Performance@@@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBDKAEAV?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@1@@Z`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180338a84`

## callees

- `0x1800e65d4`
- `0x180107754`
- `0x18020aac0`
- `0x1803388b0`
- `0x180338ed4`
- `0x180338f64`
- `0x180369010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180338910`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180338910`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1803388f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1803388f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803389ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803389ba`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180338990`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1803389b0`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180338990`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1803389b0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180338a4f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180338a4f`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18033893a`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18033893a`

## string_xrefs

- `0x1803388ef`: `kernelbase.dll`
- `0x1803389f8`: `TdhLoadManifest`
- `0x180338906`: `GetTempPath2W`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
        if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(wchar_t *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(wchar_t *)(v17)
          && (v13 = (__int64 (__fastcall *)(WCHAR *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(wchar_t *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(wchar_t *)(v17),
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
0x1803388b0  mov     [rsp-8+arg_0], rbx
0x1803388b5  mov     [rsp-8+arg_18], rsi
0x1803388ba  push    rbp
0x1803388bb  push    rdi
0x1803388bc  push    r14
0x1803388be  lea     rbp, [rsp-380h]
0x1803388c6  sub     rsp, 480h
0x1803388cd  mov     rax, cs:__security_cookie
0x1803388d4  xor     rax, rsp
0x1803388d7  mov     [rbp+390h+var_20], rax
0x1803388de  mov     rdi, r9
0x1803388e1  mov     r14d, r8d
0x1803388e4  mov     rsi, rdx
0x1803388e7  xor     edx, edx; hFile
0x1803388e9  mov     r8d, 800h; dwFlags
0x1803388ef  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1803388f6  call    cs:__imp_LoadLibraryExW
0x1803388fc  mov     [rsp+490h+var_470], rax
0x180338901  test    rax, rax
0x180338904  jz      short loc_18033892E
0x180338906  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18033890d  mov     rcx, rax; hModule
0x180338910  call    cs:__imp_GetProcAddress
0x180338916  test    rax, rax
0x180338919  jz      short loc_18033892E
0x18033891b  lea     rdx, [rbp+390h+Buffer]
0x180338922  mov     ecx, 104h
0x180338927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033892c  jmp     short loc_180338940
0x18033892e  lea     rdx, [rbp+390h+Buffer]; lpBuffer
0x180338935  mov     ecx, 104h; nBufferLength
0x18033893a  call    cs:__imp_GetTempPathW
0x180338940  mov     ebx, eax
0x180338942  lea     rcx, [rsp+490h+var_470]
0x180338947  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x18033894c  test    ebx, ebx
0x18033894e  jz      short loc_18033895A
0x180338950  lea     eax, [rbx+1]
0x180338953  cmp     eax, 104h
0x180338958  jbe     short loc_18033897A
0x18033895a  lea     r8, PathName; "."
0x180338961  mov     edx, 104h; unsigned __int64
0x180338966  lea     rcx, [rbp+390h+Buffer]; wchar_t *
0x18033896d  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180338972  test    eax, eax
0x180338974  js      loc_180338A57
0x18033897a  lea     r9, [rsp+490h+TempFileName]; lpTempFileName
0x18033897f  xor     r8d, r8d; uUnique
0x180338982  lea     rdx, PrefixString; "xpf"
0x180338989  lea     rcx, [rbp+390h+Buffer]; lpPathName
0x180338990  call    cs:__imp_GetTempFileNameW
0x180338996  test    eax, eax
0x180338998  jnz     short loc_1803389D5
0x18033899a  lea     r9, [rsp+490h+TempFileName]; lpTempFileName
0x18033899f  xor     r8d, r8d; uUnique
0x1803389a2  lea     rdx, PrefixString; "xpf"
0x1803389a9  lea     rcx, PathName; "."
0x1803389b0  call    cs:__imp_GetTempFileNameW
0x1803389b6  test    eax, eax
0x1803389b8  jnz     short loc_1803389D5
0x1803389ba  call    cs:__imp_GetLastError
0x1803389c0  test    eax, eax
0x1803389c2  jle     loc_180338A57
0x1803389c8  movzx   eax, ax
0x1803389cb  or      eax, 80070000h
0x1803389d0  jmp     loc_180338A57
0x1803389d5  mov     r9d, r14d; unsigned int
0x1803389d8  mov     r8, rsi; char *
0x1803389db  lea     rdx, [rsp+490h+TempFileName]; wchar_t *
0x1803389e0  call    ?WriteManifestFile@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEB_WPEBDK@Z; Microsoft::Windows::Performance::CEventSourceHandler::WriteManifestFile(wchar_t const *,char const *,ulong)
0x1803389e5  test    eax, eax
0x1803389e7  js      short loc_180338A57
0x1803389e9  lea     rax, [rsp+490h+TempFileName]
0x1803389ee  mov     [rsp+490h+var_470], rax
0x1803389f3  mov     [rsp+490h+var_468], rdi
0x1803389f8  lea     rax, aTdhloadmanifes; "TdhLoadManifest"
0x1803389ff  mov     [rsp+490h+var_460], rax
0x180338a04  mov     [rsp+490h+var_458], 0
0x180338a0d  mov     [rsp+490h+var_450], 0
0x180338a12  lea     rcx, [rsp+490h+var_468]
0x180338a17  call    ??B?$CDelayLoadedImport@P6AKPEA_W@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEA_W@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(wchar_t *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(wchar_t *)(void)
0x180338a1c  test    rax, rax
0x180338a1f  jz      short loc_180338A48
0x180338a21  lea     rcx, [rsp+490h+var_468]
0x180338a26  call    ??B?$CDelayLoadedImport@P6AKPEA_W@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEA_W@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(wchar_t *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(wchar_t *)(void)
0x180338a2b  lea     rcx, [rsp+490h+TempFileName]
0x180338a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180338a35  mov     ebx, eax
0x180338a37  test    eax, eax
0x180338a39  jz      short loc_180338A48
0x180338a3b  jle     short loc_180338A4A
0x180338a3d  movzx   ebx, ax
0x180338a40  or      ebx, 80070000h
0x180338a46  jmp     short loc_180338A4A
0x180338a48  xor     ebx, ebx
0x180338a4a  lea     rcx, [rsp+490h+TempFileName]; lpFileName
0x180338a4f  call    cs:__imp_DeleteFileW
0x180338a55  mov     eax, ebx
0x180338a57  mov     rcx, [rbp+390h+var_20]
0x180338a5e  xor     rcx, rsp; StackCookie
0x180338a61  call    __security_check_cookie
0x180338a66  lea     r11, [rsp+490h+var_10]
0x180338a6e  mov     rbx, [r11+20h]
0x180338a72  mov     rsi, [r11+38h]
0x180338a76  mov     rsp, r11
0x180338a79  pop     r14
0x180338a7b  pop     rdi
0x180338a7c  pop     rbp
0x180338a7d  retn
```
