# OneCore::Base::Telemetry::OneSettingsQuery::GetRegistryRedirectionLocation(ushort *,ulong,ushort const *,ushort const *)

- ea: `0x180004200`
- end: `0x1800042a4`
- name: `?GetRegistryRedirectionLocation@OneSettingsQuery@Telemetry@Base@OneCore@@QEAAJPEAGKPEBG1@Z`
- size: `164`
- prototype: `int(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800039c8`

## callees

- `0x180004200`
- `0x18001a010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000428a`
- `msvcrt!wcscpy_s` at `0x18000428a`
- `KERNEL32!LoadLibraryExW` at `0x18000421c`
- `KERNEL32!LoadLibraryExW` at `0x18000421c`
- `KERNEL32!GetProcAddress` at `0x180004238`
- `KERNEL32!GetProcAddress` at `0x180004238`

## string_xrefs

- `0x18000420d`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::GetRegistryRedirectionLocation(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  HMODULE Library; // rax
  unsigned int v6; // ebx
  FARPROC ProcAddress; // rax
  int v8; // eax

  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  if ( Library && (ProcAddress = GetProcAddress(Library, "RtlGetPersistedStateLocation")) != 0 )
  {
    v8 = ((__int64 (__fastcall *)(const WCHAR *, _QWORD, const wchar_t *, _QWORD, unsigned __int16 *, int, _QWORD))ProcAddress)(
           L"OneSettingsQuery",
           0,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OneSettings",
           0,
           a2,
           520,
           0);
    v6 = v8 | 0x10000000;
    if ( v8 >= 0 )
      return v6;
  }
  else
  {
    v6 = -2147467259;
  }
  if ( !wcscpy_s(a2, 0x104u, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OneSettings") )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x180004200  mov     [rsp+arg_0], rbx
0x180004205  push    rdi
0x180004206  sub     rsp, 40h
0x18000420a  mov     rdi, rdx
0x18000420d  lea     rcx, LibFileName; "ntdll.dll"
0x180004214  xor     edx, edx; hFile
0x180004216  mov     r8d, 800h; dwFlags
0x18000421c  call    cs:__imp_LoadLibraryExW
0x180004222  test    rax, rax
0x180004225  jnz     short loc_18000422E
0x180004227  mov     ebx, 80004005h
0x18000422c  jmp     short loc_18000427B
0x18000422e  lea     rdx, aRtlgetpersiste; "RtlGetPersistedStateLocation"
0x180004235  mov     rcx, rax; hModule
0x180004238  call    cs:__imp_GetProcAddress
0x18000423e  test    rax, rax
0x180004241  jz      short loc_180004227
0x180004243  mov     [rsp+48h+var_18], 0
0x18000424c  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180004253  mov     [rsp+48h+var_20], 208h
0x18000425b  lea     rcx, pszAgentW; "OneSettingsQuery"
0x180004262  xor     r9d, r9d
0x180004265  mov     [rsp+48h+var_28], rdi
0x18000426a  xor     edx, edx
0x18000426c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004271  mov     ebx, eax
0x180004273  or      ebx, 10000000h
0x180004279  jge     short loc_180004297
0x18000427b  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180004282  mov     edx, 104h; SizeInWords
0x180004287  mov     rcx, rdi; Destination
0x18000428a  call    cs:__imp_wcscpy_s
0x180004290  xor     ecx, ecx
0x180004292  test    eax, eax
0x180004294  cmovz   ebx, ecx
0x180004297  mov     eax, ebx
0x180004299  mov     rbx, [rsp+48h+arg_0]
0x18000429e  add     rsp, 40h
0x1800042a2  pop     rdi
0x1800042a3  retn
```
