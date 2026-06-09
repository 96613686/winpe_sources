# CLdap::DeleteEntry(ushort const *,int)

- ea: `0x140049af4`
- end: `0x140049b9b`
- name: `?DeleteEntry@CLdap@@QEAAHPEBGH@Z`
- size: `167`
- prototype: `int(CLdap *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14003e714`

## callees

- `0x140049af4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049b71`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140049b71`
- `WLDAP32!__imp_ldap_delete_ext_sW` at `0x140049b50`
- `WLDAP32!__imp_ldap_delete_ext_sW` at `0x140049b50`

## pseudocode

```c
__int64 __fastcall CLdap::DeleteEntry(LDAP **this, WCHAR *a2)
{
  unsigned int v2; // ebx
  signed int v5; // eax
  signed int v6; // edi
  PLDAPControlW ServerControls[2]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v9; // [rsp+30h] [rbp-28h] BYREF
  __int128 v10; // [rsp+40h] [rbp-18h]

  v2 = 0;
  ServerControls[1] = 0;
  v9 = 0;
  v10 = 0;
  *(_QWORD *)&v9 = L"1.2.840.113556.1.4.805";
  DWORD2(v9) = 0;
  *(_QWORD *)&v10 = 0;
  BYTE8(v10) = 1;
  ServerControls[0] = (PLDAPControlW)&v9;
  do
  {
    v5 = ldap_delete_ext_sW(*this, a2, ServerControls, 0);
    v6 = v5;
  }
  while ( v5 == 11 );
  TlsSetValue(CLdap::gm_LdapErrorTlsIndex, (LPVOID)v5);
  LOBYTE(v2) = v6 == 0;
  return v2;
}

```

## disassembly

```asm
0x140049af4  mov     r11, rsp
0x140049af7  mov     [r11+8], rbx
0x140049afb  mov     [r11+10h], rsi
0x140049aff  mov     [r11+18h], rdi
0x140049b03  push    r14
0x140049b05  sub     rsp, 50h
0x140049b09  xor     ebx, ebx
0x140049b0b  lea     rax, a12840113556148; "1.2.840.113556.1.4.805"
0x140049b12  xorps   xmm0, xmm0
0x140049b15  mov     [r11-30h], rbx
0x140049b19  movups  [rsp+58h+var_28], xmm0
0x140049b1e  mov     rsi, rdx
0x140049b21  mov     r14, rcx
0x140049b24  movups  [rsp+58h+var_18], xmm0
0x140049b29  mov     [r11-28h], rax
0x140049b2d  lea     rax, [r11-28h]
0x140049b31  mov     dword ptr [rsp+58h+var_28+8], ebx
0x140049b35  mov     [r11-18h], rbx
0x140049b39  mov     byte ptr [rsp+58h+var_18+8], 1
0x140049b3e  mov     [r11-38h], rax
0x140049b42  mov     rcx, [r14]; ld
0x140049b45  lea     r8, [rsp+58h+ServerControls]; ServerControls
0x140049b4a  xor     r9d, r9d; ClientControls
0x140049b4d  mov     rdx, rsi; dn
0x140049b50  call    cs:__imp_ldap_delete_ext_sW
0x140049b57  nop     dword ptr [rax+rax+00h]
0x140049b5c  movsxd  rdi, eax
0x140049b5f  test    eax, eax
0x140049b61  jz      short loc_140049B68
0x140049b63  cmp     edi, 0Bh
0x140049b66  jz      short loc_140049B42
0x140049b68  mov     ecx, cs:?gm_LdapErrorTlsIndex@CLdap@@0KA; dwTlsIndex
0x140049b6e  mov     rdx, rdi; lpTlsValue
0x140049b71  call    cs:__imp_TlsSetValue
0x140049b78  nop     dword ptr [rax+rax+00h]
0x140049b7d  mov     rsi, [rsp+58h+arg_8]
0x140049b82  test    edi, edi
0x140049b84  mov     rdi, [rsp+58h+arg_10]
0x140049b89  setz    bl
0x140049b8c  mov     eax, ebx
0x140049b8e  mov     rbx, [rsp+58h+arg_0]
0x140049b93  add     rsp, 50h
0x140049b97  pop     r14
0x140049b99  retn
```
