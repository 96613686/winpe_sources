# CCAInfo::Delete(ldap *)

- ea: `0x180035bd0`
- end: `0x180035cf4`
- name: `?Delete@CCAInfo@@QEAAJPEAUldap@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(const PWSTR *this, struct ldap *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18002dcc0`

## callees

- `0x1800062d0`
- `0x180008400`
- `0x18000ac20`
- `0x180011600`
- `0x180035bd0`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035c18`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035c7d`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035cb9`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035c18`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035c7d`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180035cb9`
- `WLDAP32!__imp_ldap_unbind` at `0x180035ce0`
- `WLDAP32!__imp_ldap_unbind` at `0x180035ce0`
- `WLDAP32!__imp_ldap_delete_sW` at `0x180035c9d`
- `WLDAP32!__imp_ldap_delete_sW` at `0x180035c9d`

## pseudocode

```c
__int64 __fastcall CCAInfo::Delete(const PWSTR *this, struct ldap *a2)
{
  int DoesDSExist; // eax
  unsigned int v5; // esi
  void (*v6)(unsigned int, struct _EXCEPTION_POINTERS *); // rbx
  LDAP *v7; // rdi
  int v8; // eax
  ULONG v9; // eax
  unsigned int v10; // r9d
  unsigned __int16 **v12; // [rsp+20h] [rbp-48h]
  LDAP *ld; // [rsp+80h] [rbp+18h] BYREF
  void (*v14)(unsigned int, struct _EXCEPTION_POINTERS *); // [rsp+88h] [rbp+20h]

  ld = 0;
  DoesDSExist = myDoesDSExist(1);
  v5 = DoesDSExist;
  if ( DoesDSExist )
  {
    CSPrintErrorLineFile(0x53F0325u, DoesDSExist);
    return v5;
  }
  v6 = _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
  v14 = v6;
  if ( a2 )
  {
    v7 = a2;
    ld = a2;
LABEL_8:
    v9 = ldap_delete_sW(v7, this[4]);
    v5 = myHLdapError3(v7, v9, 0, v10, v12);
    _set_se_translator(v6);
    goto LABEL_9;
  }
  v8 = myRobustLdapBindEx(0, (const unsigned __int16 *)8, (const unsigned __int16 *)2, 0, &ld, 0);
  v5 = v8;
  if ( !v8 )
  {
    v7 = ld;
    goto LABEL_8;
  }
  CSPrintErrorLineFile(0x5520325u, v8);
  _set_se_translator(v6);
  v7 = ld;
LABEL_9:
  if ( v7 && v7 != a2 )
    ldap_unbind(v7);
  return v5;
}

```

## disassembly

```asm
0x180035bd0  mov     rax, rsp
0x180035bd3  mov     [rax+10h], rdx
0x180035bd7  push    rbx
0x180035bd8  push    rsi
0x180035bd9  push    rdi
0x180035bda  push    r14
0x180035bdc  push    r15
0x180035bde  sub     rsp, 40h
0x180035be2  mov     r14, rdx
0x180035be5  mov     r15, rcx
0x180035be8  mov     qword ptr [rax+18h], 0
0x180035bf0  mov     ecx, 1; int
0x180035bf5  call    ?myDoesDSExist@@YAJH@Z; myDoesDSExist(int)
0x180035bfa  mov     esi, eax
0x180035bfc  test    eax, eax
0x180035bfe  jz      short loc_180035C11
0x180035c00  mov     edx, eax; int
0x180035c02  mov     ecx, 53F0325h; unsigned int
0x180035c07  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035c0c  jmp     loc_180035CE6
0x180035c11  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x180035c18  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180035c1e  mov     rbx, rax
0x180035c21  mov     [rsp+68h+arg_18], rax
0x180035c29  test    r14, r14
0x180035c2c  jz      short loc_180035C3B
0x180035c2e  mov     rdi, r14
0x180035c31  mov     [rsp+68h+ld], r14
0x180035c39  jmp     short loc_180035C96
0x180035c3b  mov     [rsp+68h+var_40], 0
0x180035c44  lea     rax, [rsp+68h+ld]
0x180035c4c  mov     [rsp+68h+var_48], rax; unsigned __int16 **
0x180035c51  xor     r9d, r9d
0x180035c54  lea     edx, [r9+8]
0x180035c58  xor     ecx, ecx
0x180035c5a  lea     r8d, [r9+2]
0x180035c5e  call    myRobustLdapBindEx
0x180035c63  mov     esi, eax
0x180035c65  mov     [rsp+68h+var_38], eax
0x180035c69  test    eax, eax
0x180035c6b  jz      short loc_180035C8E
0x180035c6d  mov     edx, eax; int
0x180035c6f  mov     ecx, 5520325h; unsigned int
0x180035c74  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035c79  nop
0x180035c7a  mov     rcx, rbx
0x180035c7d  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180035c83  nop
0x180035c84  mov     rdi, [rsp+68h+ld]
0x180035c8c  jmp     short loc_180035CD3
0x180035c8e  mov     rdi, [rsp+68h+ld]
0x180035c96  mov     rdx, [r15+20h]; dn
0x180035c9a  mov     rcx, rdi; ld
0x180035c9d  call    cs:__imp_ldap_delete_sW
0x180035ca3  xor     r8d, r8d; unsigned int
0x180035ca6  mov     edx, eax; unsigned int
0x180035ca8  mov     rcx, rdi; ld
0x180035cab  call    ?myHLdapError3@@YAJPEAUldap@@KKKPEAPEAG@Z; myHLdapError3(ldap *,ulong,ulong,ulong,ushort * *)
0x180035cb0  mov     esi, eax
0x180035cb2  mov     [rsp+68h+var_38], eax
0x180035cb6  mov     rcx, rbx
0x180035cb9  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180035cbf  nop
0x180035cc0  jmp     short loc_180035CD3
0x180035cc2  mov     r14, [rsp+68h+arg_8]
0x180035cc7  mov     rdi, [rsp+68h+ld]
0x180035ccf  mov     esi, [rsp+68h+var_38]
0x180035cd3  test    rdi, rdi
0x180035cd6  jz      short loc_180035CE6
0x180035cd8  cmp     rdi, r14
0x180035cdb  jz      short loc_180035CE6
0x180035cdd  mov     rcx, rdi; ld
0x180035ce0  call    cs:__imp_ldap_unbind
0x180035ce6  mov     eax, esi
0x180035ce8  add     rsp, 40h
0x180035cec  pop     r15
0x180035cee  pop     r14
0x180035cf0  pop     rdi
0x180035cf1  pop     rsi
0x180035cf2  pop     rbx
0x180035cf3  retn
```
