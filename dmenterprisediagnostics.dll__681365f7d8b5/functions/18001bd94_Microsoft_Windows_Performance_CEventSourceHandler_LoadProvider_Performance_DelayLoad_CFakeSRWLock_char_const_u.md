# Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(char const *,ulong,Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock> &)

- ea: `0x18001bd94`
- end: `0x18001bf8d`
- name: `??$LoadProvider@VCFakeSRWLock@DelayLoad@Performance@@@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBDKAEAV?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@1@@Z`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bf94`

## callees

- `0x180001800`
- `0x180006c6c`
- `0x180019030`
- `0x18001934c`
- `0x18001bd94`
- `0x18001eab8`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001bdda`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001bdda`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bdfa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bdfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bebc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001bf57`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001bf57`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001be86`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001beac`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001be86`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001beac`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001be2a`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001be2a`

## string_xrefs

- `0x18001bdd3`: `kernelbase.dll`
- `0x18001bdf0`: `GetTempPath2W`
- `0x18001bf00`: `TdhLoadManifest`

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
0x18001bd94  mov     [rsp-8+arg_0], rbx
0x18001bd99  mov     [rsp-8+arg_18], rsi
0x18001bd9e  push    rbp
0x18001bd9f  push    rdi
0x18001bda0  push    r14
0x18001bda2  lea     rbp, [rsp-380h]
0x18001bdaa  sub     rsp, 480h
0x18001bdb1  mov     rax, cs:__security_cookie
0x18001bdb8  xor     rax, rsp
0x18001bdbb  mov     [rbp+390h+var_20], rax
0x18001bdc2  mov     rdi, r9
0x18001bdc5  mov     r14d, r8d
0x18001bdc8  mov     rsi, rdx
0x18001bdcb  xor     edx, edx; hFile
0x18001bdcd  mov     r8d, 800h; dwFlags
0x18001bdd3  lea     rcx, ModuleName; "kernelbase.dll"
0x18001bdda  call    cs:__imp_LoadLibraryExW
0x18001bde1  nop     dword ptr [rax+rax+00h]
0x18001bde6  mov     [rsp+490h+var_470], rax
0x18001bdeb  test    rax, rax
0x18001bdee  jz      short loc_18001BE1E
0x18001bdf0  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18001bdf7  mov     rcx, rax; hModule
0x18001bdfa  call    cs:__imp_GetProcAddress
0x18001be01  nop     dword ptr [rax+rax+00h]
0x18001be06  test    rax, rax
0x18001be09  jz      short loc_18001BE1E
0x18001be0b  lea     rdx, [rbp+390h+Buffer]
0x18001be12  mov     ecx, 104h
0x18001be17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be1c  jmp     short loc_18001BE36
0x18001be1e  lea     rdx, [rbp+390h+Buffer]; lpBuffer
0x18001be25  mov     ecx, 104h; nBufferLength
0x18001be2a  call    cs:__imp_GetTempPathW
0x18001be31  nop     dword ptr [rax+rax+00h]
0x18001be36  mov     ebx, eax
0x18001be38  lea     rcx, [rsp+490h+var_470]
0x18001be3d  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x18001be42  test    ebx, ebx
0x18001be44  jz      short loc_18001BE50
0x18001be46  lea     eax, [rbx+1]
0x18001be49  cmp     eax, 104h
0x18001be4e  jbe     short loc_18001BE70
0x18001be50  lea     r8, PathName; "."
0x18001be57  mov     edx, 104h; unsigned __int64
0x18001be5c  lea     rcx, [rbp+390h+Buffer]; unsigned __int16 *
0x18001be63  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001be68  test    eax, eax
0x18001be6a  js      loc_18001BF65
0x18001be70  lea     r9, [rsp+490h+TempFileName]; lpTempFileName
0x18001be75  xor     r8d, r8d; uUnique
0x18001be78  lea     rdx, PrefixString; "xpf"
0x18001be7f  lea     rcx, [rbp+390h+Buffer]; lpPathName
0x18001be86  call    cs:__imp_GetTempFileNameW
0x18001be8d  nop     dword ptr [rax+rax+00h]
0x18001be92  test    eax, eax
0x18001be94  jnz     short loc_18001BEDD
0x18001be96  lea     r9, [rsp+490h+TempFileName]; lpTempFileName
0x18001be9b  xor     r8d, r8d; uUnique
0x18001be9e  lea     rdx, PrefixString; "xpf"
0x18001bea5  lea     rcx, PathName; "."
0x18001beac  call    cs:__imp_GetTempFileNameW
0x18001beb3  nop     dword ptr [rax+rax+00h]
0x18001beb8  test    eax, eax
0x18001beba  jnz     short loc_18001BEDD
0x18001bebc  call    cs:__imp_GetLastError
0x18001bec3  nop     dword ptr [rax+rax+00h]
0x18001bec8  test    eax, eax
0x18001beca  jle     loc_18001BF65
0x18001bed0  movzx   eax, ax
0x18001bed3  or      eax, 80070000h
0x18001bed8  jmp     loc_18001BF65
0x18001bedd  mov     r9d, r14d; unsigned int
0x18001bee0  mov     r8, rsi; char *
0x18001bee3  lea     rdx, [rsp+490h+TempFileName]; unsigned __int16 *
0x18001bee8  call    ?WriteManifestFile@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBGPEBDK@Z; Microsoft::Windows::Performance::CEventSourceHandler::WriteManifestFile(ushort const *,char const *,ulong)
0x18001beed  test    eax, eax
0x18001beef  js      short loc_18001BF65
0x18001bef1  lea     rax, [rsp+490h+TempFileName]
0x18001bef6  mov     [rsp+490h+var_470], rax
0x18001befb  mov     [rsp+490h+var_468], rdi
0x18001bf00  lea     rax, aTdhloadmanifes; "TdhLoadManifest"
0x18001bf07  mov     [rsp+490h+var_460], rax
0x18001bf0c  mov     [rsp+490h+var_458], 0
0x18001bf15  mov     [rsp+490h+var_450], 0
0x18001bf1a  lea     rcx, [rsp+490h+var_468]
0x18001bf1f  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001bf24  test    rax, rax
0x18001bf27  jz      short loc_18001BF50
0x18001bf29  lea     rcx, [rsp+490h+var_468]
0x18001bf2e  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001bf33  lea     rcx, [rsp+490h+TempFileName]
0x18001bf38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf3d  mov     ebx, eax
0x18001bf3f  test    eax, eax
0x18001bf41  jz      short loc_18001BF50
0x18001bf43  jle     short loc_18001BF52
0x18001bf45  movzx   ebx, ax
0x18001bf48  or      ebx, 80070000h
0x18001bf4e  jmp     short loc_18001BF52
0x18001bf50  xor     ebx, ebx
0x18001bf52  lea     rcx, [rsp+490h+TempFileName]; lpFileName
0x18001bf57  call    cs:__imp_DeleteFileW
0x18001bf5e  nop     dword ptr [rax+rax+00h]
0x18001bf63  mov     eax, ebx
0x18001bf65  mov     rcx, [rbp+390h+var_20]
0x18001bf6c  xor     rcx, rsp; StackCookie
0x18001bf6f  call    __security_check_cookie
0x18001bf74  lea     r11, [rsp+490h+var_10]
0x18001bf7c  mov     rbx, [r11+20h]
0x18001bf80  mov     rsi, [r11+38h]
0x18001bf84  mov     rsp, r11
0x18001bf87  pop     r14
0x18001bf89  pop     rdi
0x18001bf8a  pop     rbp
0x18001bf8b  retn
```
