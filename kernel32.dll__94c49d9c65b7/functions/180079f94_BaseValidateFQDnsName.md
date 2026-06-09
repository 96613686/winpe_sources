# BaseValidateFQDnsName

- ea: `0x180079f94`
- end: `0x18007a02a`
- name: `BaseValidateFQDnsName`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180067f10`

## callees

- `0x180079f94`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180079fc0`
- `ntdll!RtlSetLastWin32Error` at `0x180079fc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180079fd4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180079fd4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180079fe2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007a001`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180079fe2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007a001`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180079fad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180079fad`

## string_xrefs

- `0x180079fa4`: `DNSAPI.DLL`

## pseudocode

```c
__int64 __fastcall BaseValidateFQDnsName(__int64 a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  ULONG v4; // ecx
  FARPROC ProcAddress; // rax
  int v7; // edi

  Library = LoadLibraryExW(L"DNSAPI.DLL", 0, 0);
  v3 = Library;
  if ( !Library )
  {
    v4 = 1157;
LABEL_3:
    RtlSetLastWin32Error(v4);
    return 0;
  }
  ProcAddress = GetProcAddress(Library, "DnsValidateName_W");
  if ( !ProcAddress )
  {
    FreeLibrary(v3);
    v4 = 1154;
    goto LABEL_3;
  }
  v7 = ((__int64 (__fastcall *)(__int64, __int64))ProcAddress)(a1, 2);
  FreeLibrary(v3);
  if ( v7 && v7 != 9556 )
  {
    v4 = 87;
    goto LABEL_3;
  }
  return 1;
}

```

## disassembly

```asm
0x180079f94  mov     [rsp+arg_0], rbx
0x180079f99  push    rdi
0x180079f9a  sub     rsp, 20h
0x180079f9e  mov     rdi, rcx
0x180079fa1  xor     r8d, r8d; dwFlags
0x180079fa4  lea     rcx, DnsApiDllString; "DNSAPI.DLL"
0x180079fab  xor     edx, edx; hFile
0x180079fad  call    cs:__imp_LoadLibraryExW
0x180079fb3  mov     rbx, rax
0x180079fb6  test    rax, rax
0x180079fb9  jnz     short loc_180079FCA
0x180079fbb  mov     ecx, 485h; LastError
0x180079fc0  call    cs:__imp_RtlSetLastWin32Error
0x180079fc6  xor     eax, eax
0x180079fc8  jmp     short loc_18007A01F
0x180079fca  lea     rdx, aDnsvalidatenam; "DnsValidateName_W"
0x180079fd1  mov     rcx, rbx; hModule
0x180079fd4  call    cs:__imp_GetProcAddress
0x180079fda  test    rax, rax
0x180079fdd  jnz     short loc_180079FEF
0x180079fdf  mov     rcx, rbx; hLibModule
0x180079fe2  call    cs:__imp_FreeLibrary
0x180079fe8  mov     ecx, 482h
0x180079fed  jmp     short loc_180079FC0
0x180079fef  mov     edx, 2
0x180079ff4  mov     rcx, rdi
0x180079ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079ffc  mov     rcx, rbx; hLibModule
0x180079fff  mov     edi, eax
0x18007a001  call    cs:__imp_FreeLibrary
0x18007a007  test    edi, edi
0x18007a009  jz      short loc_18007A01A
0x18007a00b  cmp     edi, 2554h
0x18007a011  jz      short loc_18007A01A
0x18007a013  mov     ecx, 57h ; 'W'
0x18007a018  jmp     short loc_180079FC0
0x18007a01a  mov     eax, 1
0x18007a01f  mov     rbx, [rsp+28h+arg_0]
0x18007a024  add     rsp, 20h
0x18007a028  pop     rdi
0x18007a029  retn
```
