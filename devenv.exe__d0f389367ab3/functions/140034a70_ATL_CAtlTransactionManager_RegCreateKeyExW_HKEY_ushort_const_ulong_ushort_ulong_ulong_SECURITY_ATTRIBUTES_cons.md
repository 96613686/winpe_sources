# ATL::CAtlTransactionManager::RegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)

- ea: `0x140034a70`
- end: `0x140034b7a`
- name: `?RegCreateKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEBGKPEAGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU3@PEAK@Z`
- size: `266`
- prototype: `int(ATL::CAtlTransactionManager *__hidden this, HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *const, HKEY *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140034b7c`
- `0x140035738`

## callees

- `0x140034a70`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x140034b5d`
- `ADVAPI32!RegCreateKeyExW` at `0x140034b5d`
- `KERNEL32!GetModuleHandleW` at `0x140034a99`
- `KERNEL32!GetModuleHandleW` at `0x140034a99`
- `KERNEL32!GetProcAddress` at `0x140034ab2`
- `KERNEL32!GetProcAddress` at `0x140034ab2`

## string_xrefs

- `0x140034aa8`: `RegCreateKeyTransactedW`
- `0x140034a92`: `Advapi32.dll`

## pseudocode

```c
LSTATUS __fastcall ATL::CAtlTransactionManager::RegCreateKeyExW(
        ATL::CAtlTransactionManager *this,
        HKEY a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        DWORD dwOptions,
        REGSAM samDesired,
        struct _SECURITY_ATTRIBUTES *const a8,
        HKEY *phkResult,
        unsigned int *lpdwDisposition)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  if ( *(_QWORD *)this )
  {
    ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "RegCreateKeyTransactedW");
      if ( ProcAddress )
        return ((__int64 (__fastcall *)(HKEY, const unsigned __int16 *, _QWORD, _QWORD, DWORD, REGSAM, _QWORD, HKEY *, unsigned int *, _QWORD, _QWORD))ProcAddress)(
                 a2,
                 a3,
                 0,
                 0,
                 dwOptions,
                 samDesired,
                 0,
                 phkResult,
                 lpdwDisposition,
                 *(_QWORD *)this,
                 0);
    }
  }
  else if ( *((_DWORD *)this + 2) )
  {
    return RegCreateKeyExW(a2, a3, 0, 0, dwOptions, samDesired, 0, phkResult, lpdwDisposition);
  }
  return 1;
}

```

## disassembly

```asm
0x140034a70  mov     [rsp+arg_0], rbx
0x140034a75  mov     [rsp+arg_8], rsi
0x140034a7a  push    rdi
0x140034a7b  sub     rsp, 60h
0x140034a7f  cmp     qword ptr [rcx], 0
0x140034a83  mov     rdi, r8
0x140034a86  mov     rsi, rdx
0x140034a89  mov     rbx, rcx
0x140034a8c  jz      loc_140034B15
0x140034a92  lea     rcx, aAdvapi32Dll_1; "Advapi32.dll"
0x140034a99  call    cs:__imp_GetModuleHandleW
0x140034a9f  test    rax, rax
0x140034aa2  jz      loc_140034B65
0x140034aa8  lea     rdx, aRegcreatekeytr; "RegCreateKeyTransactedW"
0x140034aaf  mov     rcx, rax; hModule
0x140034ab2  call    cs:__imp_GetProcAddress
0x140034ab8  test    rax, rax
0x140034abb  jz      loc_140034B65
0x140034ac1  and     [rsp+68h+var_18], 0
0x140034ac7  xor     r9d, r9d
0x140034aca  mov     rcx, [rbx]
0x140034acd  xor     r8d, r8d
0x140034ad0  mov     [rsp+68h+var_20], rcx
0x140034ad5  mov     rdx, rdi
0x140034ad8  mov     rcx, [rsp+68h+arg_48]
0x140034ae0  mov     [rsp+68h+lpdwDisposition], rcx
0x140034ae5  mov     rcx, [rsp+68h+arg_40]
0x140034aed  mov     [rsp+68h+phkResult], rcx
0x140034af2  and     [rsp+68h+var_38], 0
0x140034af8  mov     ecx, [rsp+68h+arg_30]
0x140034aff  mov     [rsp+68h+samDesired], ecx
0x140034b03  mov     ecx, [rsp+68h+arg_28]
0x140034b0a  mov     [rsp+68h+dwOptions], ecx
0x140034b0e  mov     rcx, rsi
0x140034b11  call    rax
0x140034b13  jmp     short loc_140034B6A
0x140034b15  cmp     dword ptr [rcx+8], 0
0x140034b19  jz      short loc_140034B65
0x140034b1b  mov     rax, [rsp+68h+arg_48]
0x140034b23  xor     r9d, r9d; lpClass
0x140034b26  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x140034b2b  xor     r8d, r8d; Reserved
0x140034b2e  mov     rax, [rsp+68h+arg_40]
0x140034b36  mov     rdx, rdi; lpSubKey
0x140034b39  mov     [rsp+68h+phkResult], rax; phkResult
0x140034b3e  mov     rcx, rsi; hKey
0x140034b41  and     [rsp+68h+var_38], 0
0x140034b47  mov     eax, [rsp+68h+arg_30]
0x140034b4e  mov     [rsp+68h+samDesired], eax; samDesired
0x140034b52  mov     eax, [rsp+68h+arg_28]
0x140034b59  mov     [rsp+68h+dwOptions], eax; dwOptions
0x140034b5d  call    cs:__imp_RegCreateKeyExW
0x140034b63  jmp     short loc_140034B6A
0x140034b65  mov     eax, 1
0x140034b6a  mov     rbx, [rsp+68h+arg_0]
0x140034b6f  mov     rsi, [rsp+68h+arg_8]
0x140034b74  add     rsp, 60h
0x140034b78  pop     rdi
0x140034b79  retn
```
