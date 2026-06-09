# Windows::Isolation::Implementation::Rtl::iso_RegDeleteKey(HKEY__ *,Windows::Isolation::Implementation::Rtl::CWin32FullPath const &)

- ea: `0x180025eb8`
- end: `0x180026059`
- name: `?iso_RegDeleteKey@Rtl@Implementation@Isolation@Windows@@YAJPEAUHKEY__@@AEBVCWin32FullPath@1234@@Z`
- size: `417`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY, const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024240`

## callees

- `0x1800069d9`
- `0x180025eb8`
- `0x1800b8c4c`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180025ee5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180025ee5`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x180025fec`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x180025fec`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180026046`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180026046`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025f92`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025fdc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026036`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025f92`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025fdc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026036`

## string_xrefs

- `0x180025ede`: `advapi32.dll`
- `0x180025ef3`: `RegDeleteKeyExA`
- `0x180025f02`: `RegDeleteKeyExW`

## pseudocode

```c
LSTATUS __fastcall Windows::Isolation::Implementation::Rtl::iso_RegDeleteKey(
        LSTATUS (__stdcall *hKey)(HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, DWORD Reserved),
        _DWORD *a2,
        const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *a3)
{
  HKEY v4; // rsi
  HMODULE ModuleHandleA; // rax
  HMODULE v6; // rdi
  LSTATUS (__stdcall *RegDeleteKeyExA)(HKEY, LPCSTR, REGSAM, DWORD); // rbp
  LSTATUS (__stdcall *RegDeleteKeyExW)(HKEY, LPCWSTR, REGSAM, DWORD); // rax
  __int64 (__fastcall *v9)(HKEY, _QWORD, __int64, _QWORD); // rdi
  bool v10; // zf
  HKEY v11; // rbx
  HKEY v13; // rbx
  HKEY v14; // rbx

  v4 = (HKEY)hKey;
  if ( !dword_1801668D8 )
  {
    ModuleHandleA = GetModuleHandleA("advapi32.dll");
    v6 = ModuleHandleA;
    if ( ModuleHandleA
      && (RegDeleteKeyExA = (LSTATUS (__stdcall *)(HKEY, LPCSTR, REGSAM, DWORD))GetProcAddress_0(
                                                                                  ModuleHandleA,
                                                                                  "RegDeleteKeyExA"),
          RegDeleteKeyExW = (LSTATUS (__stdcall *)(HKEY, LPCWSTR, REGSAM, DWORD))GetProcAddress_0(v6, "RegDeleteKeyExW"),
          hKey = RegDeleteKeyExW,
          RegDeleteKeyExA)
      && RegDeleteKeyExW )
    {
      _InterlockedCompareExchange64(&qword_1801668D0, (signed __int64)RegDeleteKeyExA, 0);
      _InterlockedCompareExchange64(&qword_1801668C8, (signed __int64)RegDeleteKeyExW, 0);
      _InterlockedCompareExchange(&dword_1801668D8, 2, 0);
    }
    else
    {
      _InterlockedCompareExchange(&dword_1801668D8, 1, 0);
    }
  }
  if ( a2[14] == 1 )
  {
    if ( Windows::Isolation::Implementation::Rtl::IsopWindowsVersionAcceptsWow64RegistryFlags((Windows::Isolation::Implementation::Rtl *)hKey) )
    {
      v9 = (__int64 (__fastcall *)(HKEY, _QWORD, __int64, _QWORD))qword_1801668D0;
      if ( qword_1801668D0 )
      {
        v10 = a2[14] == 1;
        goto LABEL_11;
      }
    }
    if ( a2[14] == 1 )
    {
      v13 = (HKEY)(a2 + 12);
      if ( *(_QWORD *)v13 )
        return RegDeleteKeyA(v4, *(LPCSTR *)(*(_QWORD *)v13 + 16LL));
    }
    else
    {
      v13 = (HKEY)(a2 + 12);
    }
    RaiseException(0xC00000E5, 1u, 0, 0);
    return RegDeleteKeyA(v4, *(LPCSTR *)(*(_QWORD *)v13 + 16LL));
  }
  if ( Windows::Isolation::Implementation::Rtl::IsopWindowsVersionAcceptsWow64RegistryFlags((Windows::Isolation::Implementation::Rtl *)hKey) )
  {
    v9 = (__int64 (__fastcall *)(HKEY, _QWORD, __int64, _QWORD))qword_1801668C8;
    if ( qword_1801668C8 )
    {
      v10 = a2[14] == 2;
LABEL_11:
      if ( v10 )
      {
        v11 = (HKEY)(a2 + 12);
        if ( *(_QWORD *)v11 )
          return v9(v4, *(_QWORD *)(*(_QWORD *)v11 + 16LL), 256, 0);
      }
      else
      {
        v11 = (HKEY)(a2 + 12);
      }
      RaiseException(0xC00000E5, 1u, 0, 0);
      return v9(v4, *(_QWORD *)(*(_QWORD *)v11 + 16LL), 256, 0);
    }
  }
  if ( a2[14] == 2 )
  {
    v14 = (HKEY)(a2 + 12);
    if ( *(_QWORD *)v14 )
      return RegDeleteKeyW(v4, *(LPCWSTR *)(*(_QWORD *)v14 + 16LL));
  }
  else
  {
    v14 = (HKEY)(a2 + 12);
  }
  RaiseException(0xC00000E5, 1u, 0, 0);
  return RegDeleteKeyW(v4, *(LPCWSTR *)(*(_QWORD *)v14 + 16LL));
}

```

## disassembly

```asm
0x180025eb8  push    rbx
0x180025eba  push    rbp
0x180025ebb  push    rsi
0x180025ebc  push    rdi
0x180025ebd  push    r12
0x180025ebf  push    r15
0x180025ec1  sub     rsp, 38h
0x180025ec5  cmp     cs:dword_1801668D8, 0
0x180025ecc  mov     r15d, 1
0x180025ed2  mov     rbx, rdx
0x180025ed5  mov     rsi, rcx
0x180025ed8  lea     r12d, [r15+1]
0x180025edc  jnz     short loc_180025F4F
0x180025ede  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180025ee5  call    cs:__imp_GetModuleHandleA
0x180025eeb  mov     rdi, rax
0x180025eee  test    rax, rax
0x180025ef1  jz      short loc_180025F44
0x180025ef3  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExA"
0x180025efa  mov     rcx, rax; hModule
0x180025efd  call    GetProcAddress_0
0x180025f02  lea     rdx, aRegdeletekeyex_0; "RegDeleteKeyExW"
0x180025f09  mov     rcx, rdi; hModule
0x180025f0c  mov     rbp, rax
0x180025f0f  call    GetProcAddress_0
0x180025f14  mov     rcx, rax
0x180025f17  test    rbp, rbp
0x180025f1a  jz      short loc_180025F44
0x180025f1c  test    rax, rax
0x180025f1f  jz      short loc_180025F44
0x180025f21  xor     eax, eax
0x180025f23  lock cmpxchg cs:qword_1801668D0, rbp
0x180025f2c  xor     eax, eax
0x180025f2e  lock cmpxchg cs:qword_1801668C8, rcx
0x180025f37  xor     eax, eax
0x180025f39  lock cmpxchg cs:dword_1801668D8, r12d
0x180025f42  jmp     short loc_180025F4F
0x180025f44  xor     eax, eax
0x180025f46  lock cmpxchg cs:dword_1801668D8, r15d
0x180025f4f  cmp     [rbx+38h], r15d
0x180025f53  jnz     loc_180025FF4
0x180025f59  call    ?IsopWindowsVersionAcceptsWow64RegistryFlags@Rtl@Implementation@Isolation@Windows@@YA_NXZ; Windows::Isolation::Implementation::Rtl::IsopWindowsVersionAcceptsWow64RegistryFlags(void)
0x180025f5e  test    al, al
0x180025f60  jz      short loc_180025FB8
0x180025f62  mov     rdi, cs:qword_1801668D0
0x180025f69  test    rdi, rdi
0x180025f6c  jz      short loc_180025FB8
0x180025f6e  cmp     [rbx+38h], r15d
0x180025f72  jnz     short loc_180025F80
0x180025f74  add     rbx, 30h ; '0'
0x180025f78  cmp     qword ptr [rbx], 0
0x180025f7c  jz      short loc_180025F84
0x180025f7e  jmp     short loc_180025F98
0x180025f80  add     rbx, 30h ; '0'
0x180025f84  xor     r9d, r9d; lpArguments
0x180025f87  xor     r8d, r8d; nNumberOfArguments
0x180025f8a  mov     edx, r15d; dwExceptionFlags
0x180025f8d  mov     ecx, 0C00000E5h; dwExceptionCode
0x180025f92  call    cs:__imp_RaiseException
0x180025f98  mov     rdx, [rbx]
0x180025f9b  xor     r9d, r9d
0x180025f9e  mov     r8d, 100h
0x180025fa4  mov     rcx, rsi
0x180025fa7  mov     rax, rdi
0x180025faa  mov     rdx, [rdx+10h]
0x180025fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fb3  jmp     loc_18002604C
0x180025fb8  cmp     [rbx+38h], r15d
0x180025fbc  jnz     short loc_180025FCA
0x180025fbe  add     rbx, 30h ; '0'
0x180025fc2  cmp     qword ptr [rbx], 0
0x180025fc6  jz      short loc_180025FCE
0x180025fc8  jmp     short loc_180025FE2
0x180025fca  add     rbx, 30h ; '0'
0x180025fce  xor     r9d, r9d; lpArguments
0x180025fd1  xor     r8d, r8d; nNumberOfArguments
0x180025fd4  mov     edx, r15d; dwExceptionFlags
0x180025fd7  mov     ecx, 0C00000E5h; dwExceptionCode
0x180025fdc  call    cs:__imp_RaiseException
0x180025fe2  mov     rdx, [rbx]
0x180025fe5  mov     rcx, rsi; hKey
0x180025fe8  mov     rdx, [rdx+10h]; lpSubKey
0x180025fec  call    cs:__imp_RegDeleteKeyA
0x180025ff2  jmp     short loc_18002604C
0x180025ff4  call    ?IsopWindowsVersionAcceptsWow64RegistryFlags@Rtl@Implementation@Isolation@Windows@@YA_NXZ; Windows::Isolation::Implementation::Rtl::IsopWindowsVersionAcceptsWow64RegistryFlags(void)
0x180025ff9  test    al, al
0x180025ffb  jz      short loc_180026012
0x180025ffd  mov     rdi, cs:qword_1801668C8
0x180026004  test    rdi, rdi
0x180026007  jz      short loc_180026012
0x180026009  cmp     [rbx+38h], r12d
0x18002600d  jmp     loc_180025F72
0x180026012  cmp     [rbx+38h], r12d
0x180026016  jnz     short loc_180026024
0x180026018  add     rbx, 30h ; '0'
0x18002601c  cmp     qword ptr [rbx], 0
0x180026020  jz      short loc_180026028
0x180026022  jmp     short loc_18002603C
0x180026024  add     rbx, 30h ; '0'
0x180026028  xor     r9d, r9d; lpArguments
0x18002602b  xor     r8d, r8d; nNumberOfArguments
0x18002602e  mov     edx, r15d; dwExceptionFlags
0x180026031  mov     ecx, 0C00000E5h; dwExceptionCode
0x180026036  call    cs:__imp_RaiseException
0x18002603c  mov     rdx, [rbx]
0x18002603f  mov     rcx, rsi; hKey
0x180026042  mov     rdx, [rdx+10h]; lpSubKey
0x180026046  call    cs:__imp_RegDeleteKeyW
0x18002604c  add     rsp, 38h
0x180026050  pop     r15
0x180026052  pop     r12
0x180026054  pop     rdi
0x180026055  pop     rsi
0x180026056  pop     rbp
0x180026057  pop     rbx
0x180026058  retn
```
