# AddFileToWerReport(ushort const *,void *)

- ea: `0x1800187d0`
- end: `0x180018997`
- name: `?AddFileToWerReport@@YAJPEBGPEAX@Z`
- size: `455`
- prototype: `int(const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018f84`

## callees

- `0x180007960`
- `0x1800187d0`
- `0x1800191f0`
- `0x18001a010`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x18001889f`
- `KERNEL32!CreateDirectoryW` at `0x18001889f`
- `KERNEL32!GetSystemDirectoryW` at `0x1800188d3`
- `KERNEL32!GetSystemDirectoryW` at `0x1800188d3`
- `KERNEL32!FreeLibrary` at `0x180018969`
- `KERNEL32!FreeLibrary` at `0x180018969`
- `KERNEL32!GetProcAddress` at `0x18001891b`
- `KERNEL32!GetProcAddress` at `0x18001891b`
- `KERNEL32!LoadLibraryW` at `0x180018903`
- `KERNEL32!LoadLibraryW` at `0x180018903`
- `KERNEL32!GetTempPath2W` at `0x180018824`
- `KERNEL32!GetTempPath2W` at `0x180018824`
- `ntdll!RtlFreeUnicodeString` at `0x18001895b`
- `ntdll!RtlFreeUnicodeString` at `0x18001895b`
- `ntdll!RtlStringFromGUID` at `0x180018854`
- `ntdll!RtlStringFromGUID` at `0x180018854`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001883c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001883c`
- `wer!WerReportAddFile` at `0x18001894e`
- `wer!WerReportAddFile` at `0x18001894e`

## string_xrefs

- `0x1800188ad`: `appcompat.txt`
- `0x1800188e2`: `\apphelp.dll`

## pseudocode

```c
__int64 __fastcall AddFileToWerReport(const unsigned __int16 *a1, void *a2)
{
  HMODULE v4; // rbx
  unsigned int v5; // edi
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  struct _UNICODE_STRING GuidString; // [rsp+20h] [rbp-E0h] BYREF
  GUID pguid; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR PathName[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  v4 = 0;
  v5 = -2147467259;
  pguid = 0;
  GuidString = 0;
  if ( (unsigned int)GetTempPath2W(260, PathName) - 1 <= 0x103
    && CoCreateGuid(&pguid) >= 0
    && RtlStringFromGUID(&pguid, &GuidString) >= 0
    && (int)StringCchCatW(PathName, 0x104u, GuidString.Buffer) >= 0
    && (int)StringCchCatW(PathName, 0x104u, L"\\") >= 0 )
  {
    if ( CreateDirectoryW(PathName, 0) )
    {
      if ( (int)StringCchCatW(PathName, 0x104u, L"appcompat.txt") >= 0
        && GetSystemDirectoryW(Buffer, 0x104u) - 1 <= 0x103
        && (int)StringCchCatW(Buffer, 0x104u, L"\\apphelp.dll") >= 0 )
      {
        LibraryW = LoadLibraryW(Buffer);
        v4 = LibraryW;
        if ( LibraryW )
        {
          ProcAddress = GetProcAddress(LibraryW, "SdbGrabMatchingInfo");
          if ( ProcAddress )
          {
            if ( ((unsigned int (__fastcall *)(const unsigned __int16 *, __int64, WCHAR *))ProcAddress)(
                   a1,
                   1073741825,
                   PathName) )
            {
              WerReportAddFile(a2, PathName, WerFileTypeOther, 1u);
            }
            v5 = 0;
          }
        }
      }
    }
  }
  RtlFreeUnicodeString(&GuidString);
  if ( v4 )
    FreeLibrary(v4);
  return v5;
}

```

## disassembly

```asm
0x1800187d0  mov     [rsp-8+arg_10], rbx
0x1800187d5  push    rbp
0x1800187d6  push    rsi
0x1800187d7  push    rdi
0x1800187d8  push    r14
0x1800187da  push    r15
0x1800187dc  lea     rbp, [rsp-370h]
0x1800187e4  sub     rsp, 470h
0x1800187eb  mov     rax, cs:__security_cookie
0x1800187f2  xor     rax, rsp
0x1800187f5  mov     [rbp+390h+var_30], rax
0x1800187fc  xorps   xmm0, xmm0
0x1800187ff  mov     rsi, rdx
0x180018802  mov     r14, rcx
0x180018805  lea     rdx, [rsp+490h+PathName]
0x18001880a  mov     r15d, 104h
0x180018810  xor     ebx, ebx
0x180018812  mov     ecx, r15d
0x180018815  mov     edi, 80004005h
0x18001881a  movups  xmmword ptr [rsp+490h+pguid.Data1], xmm0
0x18001881f  movups  xmmword ptr [rsp+490h+GuidString.Length], xmm0
0x180018824  call    cs:__imp_GetTempPath2W
0x18001882a  dec     eax
0x18001882c  cmp     eax, 103h
0x180018831  ja      loc_180018956
0x180018837  lea     rcx, [rsp+490h+pguid]; pguid
0x18001883c  call    cs:__imp_CoCreateGuid
0x180018842  test    eax, eax
0x180018844  js      loc_180018956
0x18001884a  lea     rdx, [rsp+490h+GuidString]; GuidString
0x18001884f  lea     rcx, [rsp+490h+pguid]; Guid
0x180018854  call    cs:__imp_RtlStringFromGUID
0x18001885a  test    eax, eax
0x18001885c  js      loc_180018956
0x180018862  mov     r8, [rsp+490h+GuidString.Buffer]; unsigned __int16 *
0x180018867  lea     rcx, [rsp+490h+PathName]; unsigned __int16 *
0x18001886c  mov     edx, r15d; unsigned __int64
0x18001886f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018874  test    eax, eax
0x180018876  js      loc_180018956
0x18001887c  lea     r8, asc_18001D1B4; "\\"
0x180018883  mov     edx, r15d; unsigned __int64
0x180018886  lea     rcx, [rsp+490h+PathName]; unsigned __int16 *
0x18001888b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018890  test    eax, eax
0x180018892  js      loc_180018956
0x180018898  xor     edx, edx; lpSecurityAttributes
0x18001889a  lea     rcx, [rsp+490h+PathName]; lpPathName
0x18001889f  call    cs:__imp_CreateDirectoryW
0x1800188a5  test    eax, eax
0x1800188a7  jz      loc_180018956
0x1800188ad  lea     r8, aAppcompatTxt; "appcompat.txt"
0x1800188b4  mov     edx, r15d; unsigned __int64
0x1800188b7  lea     rcx, [rsp+490h+PathName]; unsigned __int16 *
0x1800188bc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800188c1  test    eax, eax
0x1800188c3  js      loc_180018956
0x1800188c9  mov     edx, r15d; uSize
0x1800188cc  lea     rcx, [rbp+390h+Buffer]; lpBuffer
0x1800188d3  call    cs:__imp_GetSystemDirectoryW
0x1800188d9  dec     eax
0x1800188db  cmp     eax, 103h
0x1800188e0  ja      short loc_180018956
0x1800188e2  lea     r8, aApphelpDll_0; "\\apphelp.dll"
0x1800188e9  mov     edx, r15d; unsigned __int64
0x1800188ec  lea     rcx, [rbp+390h+Buffer]; unsigned __int16 *
0x1800188f3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800188f8  test    eax, eax
0x1800188fa  js      short loc_180018956
0x1800188fc  lea     rcx, [rbp+390h+Buffer]; lpLibFileName
0x180018903  call    cs:__imp_LoadLibraryW
0x180018909  mov     rbx, rax
0x18001890c  test    rax, rax
0x18001890f  jz      short loc_180018956
0x180018911  lea     rdx, aSdbgrabmatchin; "SdbGrabMatchingInfo"
0x180018918  mov     rcx, rax; hModule
0x18001891b  call    cs:__imp_GetProcAddress
0x180018921  test    rax, rax
0x180018924  jz      short loc_180018956
0x180018926  lea     r8, [rsp+490h+PathName]
0x18001892b  mov     edx, 40000001h
0x180018930  mov     rcx, r14
0x180018933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018938  test    eax, eax
0x18001893a  jz      short loc_180018954
0x18001893c  mov     r9d, 1; dwFileFlags
0x180018942  lea     rdx, [rsp+490h+PathName]; pwzPath
0x180018947  mov     rcx, rsi; hReportHandle
0x18001894a  lea     r8d, [r9+4]; repFileType
0x18001894e  call    cs:__imp_WerReportAddFile
0x180018954  xor     edi, edi
0x180018956  lea     rcx, [rsp+490h+GuidString]; UnicodeString
0x18001895b  call    cs:__imp_RtlFreeUnicodeString
0x180018961  test    rbx, rbx
0x180018964  jz      short loc_18001896F
0x180018966  mov     rcx, rbx; hLibModule
0x180018969  call    cs:__imp_FreeLibrary
0x18001896f  mov     eax, edi
0x180018971  mov     rcx, [rbp+390h+var_30]
0x180018978  xor     rcx, rsp; StackCookie
0x18001897b  call    __security_check_cookie
0x180018980  mov     rbx, [rsp+490h+arg_10]
0x180018988  add     rsp, 470h
0x18001898f  pop     r15
0x180018991  pop     r14
0x180018993  pop     rdi
0x180018994  pop     rsi
0x180018995  pop     rbp
0x180018996  retn
```
