# BaseValidateFQDnsName

- ea: `0x180081e0c`
- end: `0x180081ec1`
- name: `BaseValidateFQDnsName`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18006eec0`

## callees

- `0x180081e0c`
- `0x180084010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180081e3e`
- `ntdll!RtlSetLastWin32Error` at `0x180081e3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180081e58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180081e58`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180081e6c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180081e91`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180081e6c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180081e91`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180081e25`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180081e25`

## string_xrefs

- `0x180081e1c`: `DNSAPI.DLL`

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
0x180081e0c  mov     [rsp+arg_0], rbx
0x180081e11  push    rdi
0x180081e12  sub     rsp, 20h
0x180081e16  mov     rdi, rcx
0x180081e19  xor     r8d, r8d; dwFlags
0x180081e1c  lea     rcx, DnsApiDllString; "DNSAPI.DLL"
0x180081e23  xor     edx, edx; hFile
0x180081e25  call    cs:__imp_LoadLibraryExW
0x180081e2c  nop     dword ptr [rax+rax+00h]
0x180081e31  mov     rbx, rax
0x180081e34  test    rax, rax
0x180081e37  jnz     short loc_180081E4E
0x180081e39  mov     ecx, 485h; LastError
0x180081e3e  call    cs:__imp_RtlSetLastWin32Error
0x180081e45  nop     dword ptr [rax+rax+00h]
0x180081e4a  xor     eax, eax
0x180081e4c  jmp     short loc_180081EB5
0x180081e4e  lea     rdx, aDnsvalidatenam; "DnsValidateName_W"
0x180081e55  mov     rcx, rbx; hModule
0x180081e58  call    cs:__imp_GetProcAddress
0x180081e5f  nop     dword ptr [rax+rax+00h]
0x180081e64  test    rax, rax
0x180081e67  jnz     short loc_180081E7F
0x180081e69  mov     rcx, rbx; hLibModule
0x180081e6c  call    cs:__imp_FreeLibrary
0x180081e73  nop     dword ptr [rax+rax+00h]
0x180081e78  mov     ecx, 482h
0x180081e7d  jmp     short loc_180081E3E
0x180081e7f  mov     edx, 2
0x180081e84  mov     rcx, rdi
0x180081e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081e8c  mov     rcx, rbx; hLibModule
0x180081e8f  mov     edi, eax
0x180081e91  call    cs:__imp_FreeLibrary
0x180081e98  nop     dword ptr [rax+rax+00h]
0x180081e9d  test    edi, edi
0x180081e9f  jz      short loc_180081EB0
0x180081ea1  cmp     edi, 2554h
0x180081ea7  jz      short loc_180081EB0
0x180081ea9  mov     ecx, 57h ; 'W'
0x180081eae  jmp     short loc_180081E3E
0x180081eb0  mov     eax, 1
0x180081eb5  mov     rbx, [rsp+28h+arg_0]
0x180081eba  add     rsp, 20h
0x180081ebe  pop     rdi
0x180081ebf  retn
```
