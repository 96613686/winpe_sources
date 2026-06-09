# GetNextAppContainerSid

- ea: `0x180002ac0`
- end: `0x180002baa`
- name: `GetNextAppContainerSid`
- size: `234`
- prototype: `int __fastcall(__int64, PSID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002ac0`
- `0x180003fdc`
- `0x18000dc34`
- `0x18000fa10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180002b21`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180002b21`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180002b3a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180002b3a`

## pseudocode

```c
int __fastcall GetNextAppContainerSid(__int64 a1, PSID *a2)
{
  DWORD v3; // edx
  HKEY v5; // rcx
  unsigned int v6; // eax
  const char *v7; // r9
  unsigned int lpReserved; // [rsp+20h] [rbp-258h]
  DWORD cchName[4]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v3 = *(_DWORD *)(a1 + 8);
  v5 = *(HKEY *)a1;
  cchName[0] = 260;
  v6 = RegEnumKeyExW(v5, v3, Name, cchName, 0, 0, 0, 0);
  if ( v6 == 259 )
    return 1;
  if ( v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x128,
             (unsigned int)"minio\\profapi\\appcontainer.cpp",
             (const char *)v6,
             lpReserved);
  if ( !ConvertStringSidToSidW(Name, a2) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x12A,
             (unsigned int)"minio\\profapi\\appcontainer.cpp",
             v7);
  ++*(_DWORD *)(a1 + 8);
  return 0;
}

```

## disassembly

```asm
0x180002ac0  mov     [rsp+arg_10], rbx
0x180002ac5  push    rdi
0x180002ac6  sub     rsp, 270h
0x180002acd  mov     rax, cs:__security_cookie
0x180002ad4  xor     rax, rsp
0x180002ad7  mov     [rsp+278h+var_18], rax
0x180002adf  mov     [rsp+278h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180002ae8  lea     r9, [rsp+278h+cchName]; lpcchName
0x180002aed  mov     rdi, rdx
0x180002af0  mov     [rsp+278h+lpcchClass], 0; lpcchClass
0x180002af9  mov     edx, [rcx+8]; dwIndex
0x180002afc  lea     r8, [rsp+278h+Name]; lpName
0x180002b01  mov     rbx, rcx
0x180002b04  mov     [rsp+278h+lpClass], 0; lpClass
0x180002b0d  mov     rcx, [rcx]; hKey
0x180002b10  mov     [rsp+278h+lpReserved], 0; unsigned int
0x180002b19  mov     [rsp+278h+cchName], 104h
0x180002b21  call    cs:__imp_RegEnumKeyExW
0x180002b27  cmp     eax, 103h
0x180002b2c  jz      short loc_180002B88
0x180002b2e  test    eax, eax
0x180002b30  jnz     short loc_180002B6A
0x180002b32  mov     rdx, rdi; Sid
0x180002b35  lea     rcx, [rsp+278h+Name]; StringSid
0x180002b3a  call    cs:__imp_ConvertStringSidToSidW
0x180002b40  test    eax, eax
0x180002b42  jz      short loc_180002B8F
0x180002b44  inc     dword ptr [rbx+8]
0x180002b47  xor     eax, eax
0x180002b49  mov     rcx, [rsp+278h+var_18]
0x180002b51  xor     rcx, rsp; StackCookie
0x180002b54  call    __security_check_cookie
0x180002b59  mov     rbx, [rsp+278h+arg_10]
0x180002b61  add     rsp, 270h
0x180002b68  pop     rdi
0x180002b69  retn
0x180002b6a  mov     rcx, [rsp+278h]; this
0x180002b72  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180002b79  mov     r9d, eax; char *
0x180002b7c  mov     edx, 128h; void *
0x180002b81  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002b86  jmp     short loc_180002B49
0x180002b88  mov     eax, 1
0x180002b8d  jmp     short loc_180002B49
0x180002b8f  mov     rcx, [rsp+278h]; this
0x180002b97  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180002b9e  mov     edx, 12Ah; void *
0x180002ba3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180002ba8  jmp     short loc_180002B49
```
