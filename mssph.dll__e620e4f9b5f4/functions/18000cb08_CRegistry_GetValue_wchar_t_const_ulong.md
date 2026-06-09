# CRegistry::GetValue(wchar_t const *,ulong *)

- ea: `0x18000cb08`
- end: `0x18000cba6`
- name: `?GetValue@CRegistry@@QEAAHPEB_WPEAK@Z`
- size: `158`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18000c5a0`

## callees

- `0x18000cb08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cb73`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cb73`

## string_xrefs

- `0x18000cb67`: `NtfsDisableLastAccessUpdate`

## pseudocode

```c
__int64 __fastcall CRegistry::GetValue(CRegistry *this, const wchar_t *a2, unsigned int *a3)
{
  HKEY v5; // rcx
  DWORD v6; // ecx
  LSTATUS v7; // eax
  unsigned int Data; // [rsp+40h] [rbp+8h] BYREF
  const wchar_t *Type; // [rsp+48h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF

  Type = a2;
  SetLastError(0);
  v5 = (HKEY)*((_QWORD *)this + 22);
  cbData = 4;
  LODWORD(Type) = 0;
  Data = 0;
  if ( v5 )
  {
    v7 = RegQueryValueExW(v5, L"NtfsDisableLastAccessUpdate", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData);
    if ( !v7 && (_DWORD)Type == 4 )
    {
      *a3 = Data;
      return 1;
    }
    v6 = v7;
  }
  else
  {
    v6 = 6;
  }
  SetLastError(v6);
  return 0;
}

```

## disassembly

```asm
0x18000cb08  mov     [rsp+arg_10], rbx
0x18000cb0d  mov     [rsp+Type], rdx
0x18000cb12  push    rdi
0x18000cb13  sub     rsp, 30h
0x18000cb17  mov     rbx, rcx
0x18000cb1a  mov     rdi, r8
0x18000cb1d  xor     ecx, ecx; dwErrCode
0x18000cb1f  call    cs:__imp_SetLastError
0x18000cb25  mov     rcx, [rbx+0B0h]; hKey
0x18000cb2c  mov     [rsp+38h+cbData], 4
0x18000cb34  mov     dword ptr [rsp+38h+Type], 0
0x18000cb3c  mov     [rsp+38h+Data], 0
0x18000cb44  test    rcx, rcx
0x18000cb47  jnz     short loc_18000CB50
0x18000cb49  mov     ecx, 6
0x18000cb4e  jmp     short loc_18000CB93
0x18000cb50  lea     rax, [rsp+38h+cbData]
0x18000cb55  xor     r8d, r8d; lpReserved
0x18000cb58  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000cb5d  lea     r9, [rsp+38h+Type]; lpType
0x18000cb62  lea     rax, [rsp+38h+Data]
0x18000cb67  lea     rdx, aNtfsdisablelas; "NtfsDisableLastAccessUpdate"
0x18000cb6e  mov     [rsp+38h+lpData], rax; lpData
0x18000cb73  call    cs:__imp_RegQueryValueExW
0x18000cb79  test    eax, eax
0x18000cb7b  jnz     short loc_18000CB91
0x18000cb7d  cmp     dword ptr [rsp+38h+Type], 4
0x18000cb82  jnz     short loc_18000CB91
0x18000cb84  mov     eax, [rsp+38h+Data]
0x18000cb88  mov     [rdi], eax
0x18000cb8a  mov     eax, 1
0x18000cb8f  jmp     short loc_18000CB9B
0x18000cb91  mov     ecx, eax; dwErrCode
0x18000cb93  call    cs:__imp_SetLastError
0x18000cb99  xor     eax, eax
0x18000cb9b  mov     rbx, [rsp+38h+arg_10]
0x18000cba0  add     rsp, 30h
0x18000cba4  pop     rdi
0x18000cba5  retn
```
