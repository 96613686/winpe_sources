# Windows::Isolation::Implementation::Rtl::iso_RegCreateKeyEx(HKEY__ *,Windows::Isolation::Implementation::Rtl::CWin32FullPath const &,ulong,Windows::Isolation::Implementation::Rtl::CWin32FullPath const *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)

- ea: `0x180025da8`
- end: `0x180025eb1`
- name: `?iso_RegCreateKeyEx@Rtl@Implementation@Isolation@Windows@@YAJPEAUHKEY__@@AEBVCWin32FullPath@1234@KPEBV61234@KKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU5@PEAK@Z`
- size: `265`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, HKEY@<rdx>, const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *@<r8>, unsigned int@<r9d>, const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, HKEY *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024ed0`

## callees

- `0x180023cec`
- `0x180025da8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180025e29`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180025e29`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025e92`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025e92`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025de0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025e49`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025de0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180025e49`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::iso_RegCreateKeyEx(
        HKEY hKey,
        _DWORD *a2,
        const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *a3,
        __int64 a4,
        const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *a5,
        unsigned int a6,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        HKEY *phkResult,
        HKEY *lpdwDisposition)
{
  HKEY v9; // rbx
  int v10; // eax
  REGSAM samDesired; // esi
  Windows::Isolation::Implementation::Rtl **v13; // rdi
  LSTATUS Key; // eax
  HKEY v15; // rdx
  unsigned int v16; // ebx

  v9 = (HKEY)(a2 + 12);
  v10 = a2[14];
  samDesired = a6 | 1;
  if ( v10 == 1 )
  {
    if ( !*(_QWORD *)v9 )
      RaiseException(0xC00000E5, 1u, 0, 0);
    v13 = (Windows::Isolation::Implementation::Rtl **)phkResult;
    Key = RegCreateKeyExA(
            hKey,
            *(LPCSTR *)(*(_QWORD *)v9 + 16LL),
            0,
            0,
            0,
            samDesired,
            lpSecurityAttributes,
            phkResult,
            (LPDWORD)lpdwDisposition);
  }
  else
  {
    if ( v10 != 2 || !*(_QWORD *)v9 )
      RaiseException(0xC00000E5, 1u, 0, 0);
    v13 = (Windows::Isolation::Implementation::Rtl **)phkResult;
    Key = RegCreateKeyExW(
            hKey,
            *(LPCWSTR *)(*(_QWORD *)v9 + 16LL),
            0,
            0,
            0,
            samDesired,
            lpSecurityAttributes,
            phkResult,
            (LPDWORD)lpdwDisposition);
  }
  v16 = Key;
  if ( !Key )
    Windows::Isolation::Implementation::Rtl::DisbaleWowReflection(*v13, v15);
  return v16;
}

```

## disassembly

```asm
0x180025da8  push    rbx
0x180025daa  push    rbp
0x180025dab  push    rsi
0x180025dac  push    rdi
0x180025dad  sub     rsp, 58h
0x180025db1  mov     esi, [rsp+78h+arg_28]
0x180025db8  lea     rbx, [rdx+30h]
0x180025dbc  mov     eax, [rdx+38h]
0x180025dbf  mov     rbp, rcx
0x180025dc2  mov     ecx, 1
0x180025dc7  or      esi, ecx
0x180025dc9  cmp     eax, ecx
0x180025dcb  jnz     short loc_180025E31
0x180025dcd  cmp     qword ptr [rbx], 0
0x180025dd1  jnz     short loc_180025DE6
0x180025dd3  mov     edx, ecx; dwExceptionFlags
0x180025dd5  xor     r9d, r9d; lpArguments
0x180025dd8  mov     ecx, 0C00000E5h; dwExceptionCode
0x180025ddd  xor     r8d, r8d; nNumberOfArguments
0x180025de0  call    cs:__imp_RaiseException
0x180025de6  mov     rax, [rsp+78h+arg_40]
0x180025dee  xor     r9d, r9d; lpClass
0x180025df1  mov     rdx, [rbx]
0x180025df4  xor     r8d, r8d; Reserved
0x180025df7  mov     rdi, [rsp+78h+arg_38]
0x180025dff  mov     rcx, rbp; hKey
0x180025e02  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180025e07  mov     rax, [rsp+78h+arg_30]
0x180025e0f  mov     rdx, [rdx+10h]; lpSubKey
0x180025e13  mov     [rsp+78h+phkResult], rdi; phkResult
0x180025e18  mov     [rsp+78h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180025e1d  mov     [rsp+78h+samDesired], esi; samDesired
0x180025e21  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180025e29  call    cs:__imp_RegCreateKeyExA
0x180025e2f  jmp     short loc_180025E98
0x180025e31  cmp     eax, 2
0x180025e34  jnz     short loc_180025E3C
0x180025e36  cmp     qword ptr [rbx], 0
0x180025e3a  jnz     short loc_180025E4F
0x180025e3c  mov     edx, ecx; dwExceptionFlags
0x180025e3e  xor     r9d, r9d; lpArguments
0x180025e41  mov     ecx, 0C00000E5h; dwExceptionCode
0x180025e46  xor     r8d, r8d; nNumberOfArguments
0x180025e49  call    cs:__imp_RaiseException
0x180025e4f  mov     rax, [rsp+78h+arg_40]
0x180025e57  xor     r9d, r9d; lpClass
0x180025e5a  mov     rdx, [rbx]
0x180025e5d  xor     r8d, r8d; Reserved
0x180025e60  mov     rdi, [rsp+78h+arg_38]
0x180025e68  mov     rcx, rbp; hKey
0x180025e6b  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x180025e70  mov     rax, [rsp+78h+arg_30]
0x180025e78  mov     rdx, [rdx+10h]; lpSubKey
0x180025e7c  mov     [rsp+78h+phkResult], rdi; phkResult
0x180025e81  mov     [rsp+78h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180025e86  mov     [rsp+78h+samDesired], esi; samDesired
0x180025e8a  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180025e92  call    cs:__imp_RegCreateKeyExW
0x180025e98  mov     ebx, eax
0x180025e9a  test    eax, eax
0x180025e9c  jnz     short loc_180025EA6
0x180025e9e  mov     rcx, [rdi]; this
0x180025ea1  call    ?DisbaleWowReflection@Rtl@Implementation@Isolation@Windows@@YAJPEAUHKEY__@@@Z; Windows::Isolation::Implementation::Rtl::DisbaleWowReflection(HKEY__ *)
0x180025ea6  mov     eax, ebx
0x180025ea8  add     rsp, 58h
0x180025eac  pop     rdi
0x180025ead  pop     rsi
0x180025eae  pop     rbp
0x180025eaf  pop     rbx
0x180025eb0  retn
```
