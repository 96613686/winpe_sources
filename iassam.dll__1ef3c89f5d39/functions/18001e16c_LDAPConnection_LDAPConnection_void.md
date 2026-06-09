# LDAPConnection::~LDAPConnection(void)

- ea: `0x18001e16c`
- end: `0x18001e1a6`
- name: `??1LDAPConnection@@IEAA@XZ`
- size: `58`
- prototype: `void __fastcall(LDAPConnection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e3fc`

## callees

- `0x18001e620`

## import_xrefs

- `msvcrt!free` at `0x18001e179`
- `msvcrt!free` at `0x18001e179`
- `KERNEL32!DeleteCriticalSection` at `0x18001e19f`
- `WLDAP32!__imp_ldap_unbind` at `0x18001e183`
- `WLDAP32!__imp_ldap_unbind` at `0x18001e183`

## pseudocode

```c
void __fastcall LDAPConnection::~LDAPConnection(LDAPConnection *this)
{
  __int64 v2; // rdx

  free(*((void **)this + 13));
  ldap_unbind(*((LDAP **)this + 11));
  LOBYTE(v2) = 1;
  std::wstring::_Tidy((char *)this + 56, v2, 0);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18001e16c  push    rbx
0x18001e16e  sub     rsp, 20h
0x18001e172  mov     rbx, rcx
0x18001e175  mov     rcx, [rcx+68h]; Block
0x18001e179  call    cs:__imp_free
0x18001e17f  mov     rcx, [rbx+58h]; ld
0x18001e183  call    cs:__imp_ldap_unbind
0x18001e189  lea     rcx, [rbx+38h]
0x18001e18d  xor     r8d, r8d
0x18001e190  mov     dl, 1
0x18001e192  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001e197  mov     rcx, rbx
0x18001e19a  add     rsp, 20h
0x18001e19e  pop     rbx
0x18001e19f  jmp     cs:__imp_DeleteCriticalSection
```
