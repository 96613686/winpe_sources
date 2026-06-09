# CTdsParser::InitEncryptSettings(void)

- ea: `0x100460fa0`
- end: `0x1004610b1`
- name: `?InitEncryptSettings@CTdsParser@@AEAAJXZ`
- size: `273`
- prototype: `__int64 __fastcall(CTdsParser *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10045ff60`

## callees

- `0x100460fa0`
- `0x100545d74`
- `0x1005495d0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x100461061`
- `ADVAPI32!RegQueryValueExW` at `0x100461061`
- `ADVAPI32!RegOpenKeyExW` at `0x100461033`
- `ADVAPI32!RegOpenKeyExW` at `0x100461033`
- `ADVAPI32!RegCloseKey` at `0x100461086`
- `ADVAPI32!RegCloseKey` at `0x100461086`

## string_xrefs

- `0x100461055`: `Force Protocol Encryption`

## pseudocode

```c
__int64 __fastcall CTdsParser::InitEncryptSettings(CTdsParser *this)
{
  char v2; // bl
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  int v5; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  *((_DWORD *)this + 11) = 0;
  if ( !(unsigned int)IsEmbeddedSNAC() )
  {
    v2 = 0;
    if ( !g_AllocatorInUse )
    {
      v5 = 0;
      (*(void (__fastcall **)(struct ISOSHost *, int *))(*(_QWORD *)g_pISOSHost + 24LL))(g_pISOSHost, &v5);
      if ( !v5 )
      {
        (*(void (__fastcall **)(struct ISOSHost *))(*(_QWORD *)g_pISOSHost + 200LL))(g_pISOSHost);
        v2 = 1;
      }
    }
    hKey = 0;
    Data = 0;
    cbData = 4;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSSQLServer\\Client\\MSODBCSQL", 0, 1u, &hKey)
      && !RegQueryValueExW(hKey, L"Force Protocol Encryption", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && cbData == 4 )
    {
      *((_DWORD *)this + 11) = Data;
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v2 )
      (*(void (__fastcall **)(struct ISOSHost *))(*(_QWORD *)g_pISOSHost + 208LL))(g_pISOSHost);
  }
  return 0;
}

```

## disassembly

```asm
0x100460fa0  push    rbp
0x100460fa2  push    rbx
0x100460fa3  push    rdi
0x100460fa4  mov     rbp, rsp
0x100460fa7  sub     rsp, 40h
0x100460fab  and     dword ptr [rcx+2Ch], 0
0x100460faf  mov     rdi, rcx
0x100460fb2  call    ?IsEmbeddedSNAC@@YAHXZ; IsEmbeddedSNAC(void)
0x100460fb7  test    eax, eax
0x100460fb9  jnz     loc_1004610A7
0x100460fbf  xor     bl, bl
0x100460fc1  cmp     cs:?g_AllocatorInUse@@3W4AllocatorEnum@@A, eax; AllocatorEnum g_AllocatorInUse
0x100460fc7  jnz     short loc_100461003
0x100460fc9  and     [rbp+arg_0], eax
0x100460fcc  lea     rdx, [rbp+arg_0]
0x100460fd0  mov     rcx, cs:?g_pISOSHost@@3PEAUISOSHost@@EA; ISOSHost * g_pISOSHost
0x100460fd7  mov     rax, [rcx]
0x100460fda  mov     rax, [rax+18h]
0x100460fde  call    cs:__guard_dispatch_icall_fptr
0x100460fe4  cmp     [rbp+arg_0], 0
0x100460fe8  jnz     short loc_100461003
0x100460fea  mov     rcx, cs:?g_pISOSHost@@3PEAUISOSHost@@EA; ISOSHost * g_pISOSHost
0x100460ff1  mov     rax, [rcx]
0x100460ff4  mov     rax, [rax+0C8h]
0x100460ffb  call    cs:__guard_dispatch_icall_fptr
0x100461001  mov     bl, 1
0x100461003  and     [rbp+hKey], 0
0x100461008  lea     rax, [rbp+hKey]
0x10046100c  and     [rbp+Data], 0
0x100461010  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MSSQLServer\\Clien"...
0x100461017  mov     r9d, 1; samDesired
0x10046101d  mov     [rsp+40h+phkResult], rax; phkResult
0x100461022  xor     r8d, r8d; ulOptions
0x100461025  mov     [rbp+cbData], 4
0x10046102c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x100461033  call    cs:__imp_RegOpenKeyExW
0x100461039  test    eax, eax
0x10046103b  jnz     short loc_10046107D
0x10046103d  mov     rcx, [rbp+hKey]; hKey
0x100461041  lea     rax, [rbp+cbData]
0x100461045  mov     [rsp+40h+lpcbData], rax; lpcbData
0x10046104a  lea     r9, [rbp+Type]; lpType
0x10046104e  lea     rax, [rbp+Data]
0x100461052  xor     r8d, r8d; lpReserved
0x100461055  lea     rdx, aForceProtocolE; "Force Protocol Encryption"
0x10046105c  mov     [rsp+40h+phkResult], rax; lpData
0x100461061  call    cs:__imp_RegQueryValueExW
0x100461067  test    eax, eax
0x100461069  jnz     short loc_10046107D
0x10046106b  cmp     [rbp+Type], 4
0x10046106f  jnz     short loc_10046107D
0x100461071  cmp     [rbp+cbData], 4
0x100461075  jnz     short loc_10046107D
0x100461077  mov     eax, [rbp+Data]
0x10046107a  mov     [rdi+2Ch], eax
0x10046107d  mov     rcx, [rbp+hKey]; hKey
0x100461081  test    rcx, rcx
0x100461084  jz      short loc_10046108C
0x100461086  call    cs:__imp_RegCloseKey
0x10046108c  test    bl, bl
0x10046108e  jz      short loc_1004610A7
0x100461090  mov     rcx, cs:?g_pISOSHost@@3PEAUISOSHost@@EA; ISOSHost * g_pISOSHost
0x100461097  mov     rax, [rcx]
0x10046109a  mov     rax, [rax+0D0h]
0x1004610a1  call    cs:__guard_dispatch_icall_fptr
0x1004610a7  xor     eax, eax
0x1004610a9  add     rsp, 40h
0x1004610ad  pop     rdi
0x1004610ae  pop     rbx
0x1004610af  pop     rbp
0x1004610b0  retn
```
