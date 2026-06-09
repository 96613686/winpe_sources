# WcpSetPrivilege

- ea: `0x14000fa88`
- end: `0x14000fb2f`
- name: `WcpSetPrivilege`
- size: `167`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14000eb48`
- `0x14000efd0`

## callees

- `0x1400020b0`
- `0x14000fa88`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x14000faec`
- `ntdll!NtAdjustPrivilegesToken` at `0x14000faec`

## pseudocode

```c
NTSTATUS __fastcall WcpSetPrivilege(void *a1, int a2, __int64 a3, _DWORD *a4)
{
  NTSTATUS result; // eax
  ULONG v6; // [rsp+30h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES v7; // [rsp+38h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES v8; // [rsp+48h] [rbp-20h] BYREF

  v7.Privileges[0].Luid = (LUID)a2;
  v7.PrivilegeCount = 1;
  v6 = 16;
  v8 = 0;
  v7.Privileges[0].Attributes = 2;
  result = NtAdjustPrivilegesToken(a1, 0, &v7, 0x10u, &v8, &v6);
  if ( result >= 0 )
  {
    if ( a4 && v8.PrivilegeCount )
      *a4 = 1;
    if ( result == 262 )
      return -1073281772;
  }
  return result;
}

```

## disassembly

```asm
0x14000fa88  mov     r11, rsp
0x14000fa8b  push    rbx
0x14000fa8c  sub     rsp, 60h
0x14000fa90  mov     rax, cs:__security_cookie
0x14000fa97  xor     rax, rsp
0x14000fa9a  mov     [rsp+68h+var_10], rax
0x14000fa9f  movsxd  rax, edx
0x14000faa2  lea     r8, [r11-30h]; NewState
0x14000faa6  mov     rdx, rax
0x14000faa9  mov     dword ptr [rsp+68h+var_2C], eax
0x14000faad  lea     rax, [r11-38h]
0x14000fab1  shr     rdx, 20h
0x14000fab5  mov     [r11-40h], rax
0x14000fab9  mov     rbx, r9
0x14000fabc  mov     dword ptr [rsp+68h+var_2C+4], edx
0x14000fac0  lea     rax, [r11-20h]
0x14000fac4  xorps   xmm0, xmm0
0x14000fac7  mov     [r11-48h], rax
0x14000facb  mov     r9d, 10h; BufferLength
0x14000fad1  mov     [rsp+68h+var_30], 1
0x14000fad9  xor     edx, edx; DisableAllPrivileges
0x14000fadb  mov     [r11-38h], r9d
0x14000fadf  movups  [rsp+68h+var_20], xmm0
0x14000fae4  mov     [rsp+68h+var_24], 2
0x14000faec  call    cs:__imp_NtAdjustPrivilegesToken
0x14000faf3  nop     dword ptr [rax+rax+00h]
0x14000faf8  test    eax, eax
0x14000fafa  js      short loc_14000FB1B
0x14000fafc  test    rbx, rbx
0x14000faff  jz      short loc_14000FB0E
0x14000fb01  cmp     dword ptr [rsp+68h+var_20], 0
0x14000fb06  jz      short loc_14000FB0E
0x14000fb08  mov     dword ptr [rbx], 1
0x14000fb0e  cmp     eax, 106h
0x14000fb13  mov     ecx, 0C0070514h
0x14000fb18  cmovz   eax, ecx
0x14000fb1b  mov     rcx, [rsp+68h+var_10]
0x14000fb20  xor     rcx, rsp; StackCookie
0x14000fb23  call    __security_check_cookie
0x14000fb28  add     rsp, 60h
0x14000fb2c  pop     rbx
0x14000fb2d  retn
```
