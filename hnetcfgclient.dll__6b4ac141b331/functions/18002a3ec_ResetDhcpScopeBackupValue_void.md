# ResetDhcpScopeBackupValue(void)

- ea: `0x18002a3ec`
- end: `0x18002a4ea`
- name: `?ResetDhcpScopeBackupValue@@YAJXZ`
- size: `254`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800177d0`

## callees

- `0x180007b74`
- `0x180008570`
- `0x18002a1e8`
- `0x18002a3ec`
- `0x18002d200`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a4a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a4a9`

## string_xrefs

- `0x18002a435`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 ResetDhcpScopeBackupValue(void)
{
  int v0; // ebx
  __int64 v1; // rax
  unsigned int v3; // [rsp+30h] [rbp-50h] BYREF
  HKEY hKey[3]; // [rsp+38h] [rbp-48h] BYREF
  BYTE Data[16]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v6; // [rsp+60h] [rbp-20h]

  *(_OWORD *)Data = 0;
  v6 = 0;
  v3 = 32;
  memset(hKey, 0, sizeof(hKey));
  v0 = ATL::CRegKey::Open(
         (ATL::CRegKey *)hKey,
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters",
         0x2001Fu);
  if ( !v0 )
  {
    v0 = ATL::CRegKey::QueryValue((ATL::CRegKey *)hKey, (unsigned __int16 *)Data, L"ScopeAddress", &v3);
    if ( !v0 )
    {
      v1 = -1;
      do
        ++v1;
      while ( *(_WORD *)&Data[2 * v1] );
      v0 = RegSetValueExW(hKey[0], L"ScopeAddressBackup", 0, 1u, Data, 2 * v1 + 2);
    }
  }
  if ( v0 > 0 )
    v0 = (unsigned __int16)v0 | 0x80070000;
  ATL::CRegKey::Close(hKey);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18002a3ec  mov     [rsp-8+arg_0], rbx
0x18002a3f1  mov     [rsp-8+arg_8], rdi
0x18002a3f6  push    rbp
0x18002a3f7  mov     rbp, rsp
0x18002a3fa  sub     rsp, 80h
0x18002a401  mov     rax, cs:__security_cookie
0x18002a408  xor     rax, rsp
0x18002a40b  mov     [rbp+var_10], rax
0x18002a40f  xorps   xmm0, xmm0
0x18002a412  movups  xmmword ptr [rbp+Data], xmm0
0x18002a416  movups  [rbp+var_20], xmm0
0x18002a41a  mov     [rbp+var_50], 20h ; ' '
0x18002a421  xor     edi, edi
0x18002a423  mov     [rbp+hKey], rdi
0x18002a427  mov     [rbp+var_40], rdi
0x18002a42b  mov     [rbp+var_38], rdi
0x18002a42f  mov     r9d, 2001Fh; unsigned int
0x18002a435  lea     r8, ?c_szDhcpScopeKey@@3QBGB; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18002a43c  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002a443  lea     rcx, [rbp+hKey]; this
0x18002a447  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002a44c  mov     ebx, eax
0x18002a44e  test    eax, eax
0x18002a450  jnz     short loc_18002A4B1
0x18002a452  lea     r9, [rbp+var_50]; unsigned int *
0x18002a456  lea     r8, ?c_szDhcpScopeAddressValue@@3QBGB; "ScopeAddress"
0x18002a45d  lea     rdx, [rbp+Data]; unsigned __int16 *
0x18002a461  lea     rcx, [rbp+hKey]; this
0x18002a465  call    ?QueryValue@CRegKey@ATL@@QEAAJPEAGPEBGPEAK@Z; ATL::CRegKey::QueryValue(ushort *,ushort const *,ulong *)
0x18002a46a  mov     ebx, eax
0x18002a46c  test    eax, eax
0x18002a46e  jnz     short loc_18002A4B1
0x18002a470  lea     rcx, [rbp+Data]
0x18002a474  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a478  inc     rax
0x18002a47b  cmp     [rcx+rax*2], di
0x18002a47f  jnz     short loc_18002A478
0x18002a481  lea     eax, ds:2[rax*2]
0x18002a488  mov     [rsp+80h+cbData], eax; cbData
0x18002a48c  lea     rax, [rbp+Data]
0x18002a490  mov     [rsp+80h+lpData], rax; lpData
0x18002a495  mov     r9d, 1; dwType
0x18002a49b  xor     r8d, r8d; Reserved
0x18002a49e  lea     rdx, ?c_szDhcpScopeBackupAddressValue@@3QBGB; "ScopeAddressBackup"
0x18002a4a5  mov     rcx, [rbp+hKey]; hKey
0x18002a4a9  call    cs:__imp_RegSetValueExW
0x18002a4af  mov     ebx, eax
0x18002a4b1  test    ebx, ebx
0x18002a4b3  jle     short loc_18002A4BE
0x18002a4b5  movzx   ebx, bx
0x18002a4b8  or      ebx, 80070000h
0x18002a4be  lea     rcx, [rbp+hKey]; this
0x18002a4c2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002a4c7  mov     eax, ebx
0x18002a4c9  mov     rcx, [rbp+var_10]
0x18002a4cd  xor     rcx, rsp; StackCookie
0x18002a4d0  call    __security_check_cookie
0x18002a4d5  lea     r11, [rsp+80h+var_s0]
0x18002a4dd  mov     rbx, [r11+10h]
0x18002a4e1  mov     rdi, [r11+18h]
0x18002a4e5  mov     rsp, r11
0x18002a4e8  pop     rbp
0x18002a4e9  retn
```
