# GetRegistryValue(ushort *,ushort * *,_RAREGHIVE)

- ea: `0x180014c24`
- end: `0x180014d98`
- name: `?GetRegistryValue@@YAJPEAGPEAPEAGW4_RAREGHIVE@@@Z`
- size: `372`
- prototype: `__int64 __fastcall(__int64, BYTE **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180016c38`

## callees

- `0x1800020b4`
- `0x180014660`
- `0x180014c24`
- `0x18001a5a2`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180014d5f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180014d5f`
- `ADVAPI32!RegQueryValueExW` at `0x180014cb3`
- `ADVAPI32!RegQueryValueExW` at `0x180014d50`
- `ADVAPI32!RegQueryValueExW` at `0x180014cb3`
- `ADVAPI32!RegQueryValueExW` at `0x180014d50`
- `ADVAPI32!RegOpenKeyExW` at `0x180014c6e`
- `ADVAPI32!RegOpenKeyExW` at `0x180014c6e`
- `ADVAPI32!RegCloseKey` at `0x180014d80`
- `ADVAPI32!RegCloseKey` at `0x180014d80`

## string_xrefs

- `0x180014d09`: `base\diagnosis\ra\racommon\src\fileutils.cpp`
- `0x180014c60`: `SYSTEM\CurrentControlSet\Services\W32Time\Parameters`
- `0x180014cef`: `GetRegistryValue`

## pseudocode

```c
__int64 __fastcall GetRegistryValue(__int64 a1, BYTE **a2)
{
  LSTATUS v3; // eax
  LSTATUS v4; // ebx
  bool v5; // cc
  unsigned __int64 v6; // rax
  BYTE *v7; // rax
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  BYTE *v10; // rdi
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  cbData = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\W32Time\\Parameters", 0, 1u, &hKey);
  v4 = v3;
  v5 = v3 <= 0;
  if ( v3 || (v3 = RegQueryValueExW(hKey, L"NtpServer", 0, 0, 0, &cbData), v4 = v3, v5 = v3 <= 0, v3) )
  {
    if ( v5 )
      goto LABEL_14;
    v4 = (unsigned __int16)v3;
    goto LABEL_4;
  }
  v6 = 2 * (cbData + 2LL);
  if ( !is_mul_ok(cbData + 2LL, 2u) )
    v6 = -1;
  v7 = (BYTE *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v7;
  if ( !v7 )
  {
    v4 = -2147024882;
    CEventLogger::LogError(
      v9,
      v8,
      L"base\\diagnosis\\ra\\racommon\\src\\fileutils.cpp",
      0x1E3u,
      L"GetRegistryValue",
      0x8007000E);
    goto LABEL_14;
  }
  memset_0(v7, 0, cbData + 2LL);
  v4 = RegQueryValueExW(hKey, L"NtpServer", 0, 0, v10, &cbData);
  if ( v4 )
  {
    operator delete[](v10);
    if ( v4 > 0 )
    {
      v4 = (unsigned __int16)v4;
LABEL_4:
      v4 |= 0x80070000;
    }
  }
  else
  {
    *a2 = v10;
    v4 = 0;
  }
LABEL_14:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014c24  mov     rax, rsp
0x180014c27  mov     [rax+10h], rbx
0x180014c2b  mov     [rax+20h], rsi
0x180014c2f  mov     [rax+18h], r8d
0x180014c33  mov     [rax+8], rcx
0x180014c37  push    rdi
0x180014c38  sub     rsp, 30h
0x180014c3c  mov     qword ptr [rax+8], 0
0x180014c44  mov     rsi, rdx
0x180014c47  mov     dword ptr [rax+18h], 0
0x180014c4e  lea     rax, [rax+8]
0x180014c52  mov     r9d, 1; samDesired
0x180014c58  mov     [rsp+38h+phkResult], rax; phkResult
0x180014c5d  xor     r8d, r8d; ulOptions
0x180014c60  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\W3"...
0x180014c67  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014c6e  call    cs:__imp_RegOpenKeyExW
0x180014c74  mov     ebx, eax
0x180014c76  test    eax, eax
0x180014c78  jz      short loc_180014C8E
0x180014c7a  jle     loc_180014D76
0x180014c80  movzx   ebx, ax
0x180014c83  or      ebx, 80070000h
0x180014c89  jmp     loc_180014D76
0x180014c8e  mov     rcx, [rsp+38h+hKey]; hKey
0x180014c93  lea     rax, [rsp+38h+cbData]
0x180014c98  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180014c9d  lea     rdx, ValueName; "NtpServer"
0x180014ca4  xor     r9d, r9d; lpType
0x180014ca7  mov     [rsp+38h+phkResult], 0; lpData
0x180014cb0  xor     r8d, r8d; lpReserved
0x180014cb3  call    cs:__imp_RegQueryValueExW
0x180014cb9  mov     ebx, eax
0x180014cbb  test    eax, eax
0x180014cbd  jnz     short loc_180014C7A
0x180014cbf  mov     ecx, [rsp+38h+cbData]
0x180014cc3  lea     eax, [rbx+2]
0x180014cc6  add     rcx, 2
0x180014cca  mul     rcx
0x180014ccd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180014cd4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014cdb  cmovb   rax, rcx
0x180014cdf  mov     rcx, rax; unsigned __int64
0x180014ce2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180014ce7  mov     rdi, rax
0x180014cea  test    rax, rax
0x180014ced  jnz     short loc_180014D1C
0x180014cef  lea     rax, aGetregistryval; "GetRegistryValue"
0x180014cf6  mov     dword ptr [rsp+38h+lpcbData], 8007000Eh; unsigned int
0x180014cfe  mov     r9d, 1E3h; unsigned int
0x180014d04  mov     [rsp+38h+phkResult], rax; unsigned __int16 *
0x180014d09  lea     r8, aBaseDiagnosisR_4; "base\\diagnosis\\ra\\racommon\\src\\fil"...
0x180014d10  mov     ebx, 8007000Eh
0x180014d15  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180014d1a  jmp     short loc_180014D76
0x180014d1c  mov     r8d, [rsp+38h+cbData]
0x180014d21  xor     edx, edx; Val
0x180014d23  add     r8, 2; Size
0x180014d27  mov     rcx, rdi; void *
0x180014d2a  call    memset_0
0x180014d2f  mov     rcx, [rsp+38h+hKey]; hKey
0x180014d34  lea     rax, [rsp+38h+cbData]
0x180014d39  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180014d3e  lea     rdx, ValueName; "NtpServer"
0x180014d45  xor     r9d, r9d; lpType
0x180014d48  mov     [rsp+38h+phkResult], rdi; lpData
0x180014d4d  xor     r8d, r8d; lpReserved
0x180014d50  call    cs:__imp_RegQueryValueExW
0x180014d56  mov     ebx, eax
0x180014d58  test    eax, eax
0x180014d5a  jz      short loc_180014D71
0x180014d5c  mov     rcx, rdi
0x180014d5f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180014d65  test    ebx, ebx
0x180014d67  jle     short loc_180014D76
0x180014d69  movzx   ebx, bx
0x180014d6c  jmp     loc_180014C83
0x180014d71  mov     [rsi], rdi
0x180014d74  xor     ebx, ebx
0x180014d76  mov     rcx, [rsp+38h+hKey]; hKey
0x180014d7b  test    rcx, rcx
0x180014d7e  jz      short loc_180014D86
0x180014d80  call    cs:__imp_RegCloseKey
0x180014d86  mov     rsi, [rsp+38h+arg_18]
0x180014d8b  mov     eax, ebx
0x180014d8d  mov     rbx, [rsp+38h+arg_8]
0x180014d92  add     rsp, 30h
0x180014d96  pop     rdi
0x180014d97  retn
```
