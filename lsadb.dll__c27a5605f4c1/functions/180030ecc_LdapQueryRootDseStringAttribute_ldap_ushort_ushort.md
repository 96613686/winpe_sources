# LdapQueryRootDseStringAttribute(ldap *,ushort *,ushort * *)

- ea: `0x180030ecc`
- end: `0x1800310c6`
- name: `?LdapQueryRootDseStringAttribute@@YAKPEAUldap@@PEAGPEAPEAG@Z`
- size: `506`
- prototype: `unsigned int __fastcall(LDAP *ld, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180031ff8`

## callees

- `0x180030ecc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180030f98`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180030f98`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030fdc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030fdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031086`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031086`
- `WLDAP32!__imp_LdapGetLastError` at `0x180030f8a`
- `WLDAP32!__imp_LdapGetLastError` at `0x180030f8a`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180030f3e`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x180030f3e`
- `WLDAP32!__imp_ldap_first_entry` at `0x180030f56`
- `WLDAP32!__imp_ldap_first_entry` at `0x180030f56`
- `WLDAP32!__imp_ldap_msgfree` at `0x180031094`
- `WLDAP32!__imp_ldap_msgfree` at `0x180031094`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x180030f7c`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x180030f7c`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180030fab`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180030fab`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18003109d`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18003109d`
- `WLDAP32!__imp_ldap_search_sW` at `0x180030f32`
- `WLDAP32!__imp_ldap_search_sW` at `0x180030f32`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800310a6`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800310a6`

## string_xrefs

- `0x180030ef1`: `configurationNamingContext`

## pseudocode

```c
__int64 __fastcall LdapQueryRootDseStringAttribute(LDAP *ld, unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned __int16 *v5; // rsi
  WCHAR *v6; // rbp
  PWCHAR *v7; // r14
  ULONG LastError; // eax
  ULONG v9; // ebx
  LDAPMessage *entry; // rax
  LDAPMessage *v11; // rbx
  PWCHAR v12; // rax
  PWCHAR *valuesW; // rax
  PWCHAR v14; // rcx
  __int64 v15; // rax
  unsigned __int64 v16; // rdi
  unsigned __int16 *v17; // rax
  PWCHAR v18; // rcx
  __int64 v19; // rax
  unsigned __int16 *v20; // rdx
  unsigned __int16 *v21; // rcx
  PWSTR v23[9]; // [rsp+40h] [rbp-48h] BYREF
  LDAPMessage *res; // [rsp+98h] [rbp+10h] BYREF
  BerElement *ptr; // [rsp+A0h] [rbp+18h] BYREF

  *a3 = 0;
  res = 0;
  ptr = 0;
  v23[0] = L"configurationNamingContext";
  v5 = 0;
  v23[1] = 0;
  v6 = 0;
  v7 = 0;
  LastError = ldap_search_sW(ld, 0, 0, (const PWSTR)L"(objectClass=*)", v23, 0, &res);
  if ( LastError )
    goto LABEL_2;
  entry = ldap_first_entry(ld, res);
  v11 = entry;
  if ( !entry )
  {
LABEL_4:
    v9 = 13;
    goto LABEL_27;
  }
  v12 = ldap_first_attributeW(ld, entry, &ptr);
  v6 = v12;
  if ( !v12 )
    goto LABEL_6;
  if ( (unsigned int)_o__wcsicmp(v12, L"configurationNamingContext") )
    goto LABEL_4;
  valuesW = ldap_get_valuesW(ld, v11, v6);
  v7 = valuesW;
  if ( !valuesW )
  {
LABEL_6:
    LastError = LdapGetLastError();
LABEL_2:
    v9 = LdapMapErrorToWin32(LastError);
    goto LABEL_27;
  }
  v14 = *valuesW;
  if ( !*valuesW )
    goto LABEL_4;
  v15 = -1;
  do
    ++v15;
  while ( v14[v15] );
  v16 = (unsigned int)(v15 + 1);
  v17 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v16);
  v5 = v17;
  if ( v17 )
  {
    if ( v16 )
    {
      if ( v16 <= 0x7FFFFFFF )
      {
        v18 = *v7;
        v19 = 2147483646;
        v20 = v5;
        do
        {
          if ( !v19 )
            break;
          if ( !*v18 )
            break;
          *v20++ = *v18++;
          --v19;
          --v16;
        }
        while ( v16 );
        v21 = v20 - 1;
        v9 = v16 == 0 ? 0x8007007A : 0;
        if ( v16 )
          v21 = v20;
        *v21 = 0;
        if ( v16 )
        {
          *a3 = v5;
          v9 = 0;
          v5 = 0;
          goto LABEL_27;
        }
      }
      else
      {
        LOWORD(v9) = 87;
        *v17 = 0;
      }
    }
    else
    {
      LOWORD(v9) = 87;
    }
    v9 = (unsigned __int16)v9;
    goto LABEL_27;
  }
  v9 = 8;
LABEL_27:
  LocalFree(v5);
  ldap_msgfree(res);
  ldap_memfreeW(v6);
  ldap_value_freeW(v7);
  return v9;
}

```

## disassembly

```asm
0x180030ecc  mov     r11, rsp
0x180030ecf  mov     [r11+8], rbx
0x180030ed3  mov     [r11+10h], rdx
0x180030ed7  push    rbp
0x180030ed8  push    rsi
0x180030ed9  push    rdi
0x180030eda  push    r12
0x180030edc  push    r13
0x180030ede  push    r14
0x180030ee0  push    r15
0x180030ee2  sub     rsp, 50h
0x180030ee6  xor     r12d, r12d
0x180030ee9  lea     rax, [r11+10h]
0x180030eed  mov     [r11-58h], rax
0x180030ef1  lea     r13, aConfigurationn; "configurationNamingContext"
0x180030ef8  lea     rax, [r11-48h]
0x180030efc  mov     [r8], r12
0x180030eff  mov     r15, r8
0x180030f02  mov     [r11-60h], r12d
0x180030f06  lea     r9, aObjectclass; "(objectClass=*)"
0x180030f0d  mov     [r11-68h], rax
0x180030f11  xor     r8d, r8d; scope
0x180030f14  mov     [r11+10h], r12
0x180030f18  xor     edx, edx; base
0x180030f1a  mov     [r11+18h], r12
0x180030f1e  mov     rdi, rcx
0x180030f21  mov     [r11-48h], r13
0x180030f25  mov     esi, r12d
0x180030f28  mov     [r11-40h], r12
0x180030f2c  mov     ebp, r12d
0x180030f2f  mov     r14d, r12d
0x180030f32  call    cs:__imp_ldap_search_sW
0x180030f38  test    eax, eax
0x180030f3a  jz      short loc_180030F4B
0x180030f3c  mov     ecx, eax; LdapError
0x180030f3e  call    cs:__imp_LdapMapErrorToWin32
0x180030f44  mov     ebx, eax
0x180030f46  jmp     loc_180031083
0x180030f4b  mov     rdx, [rsp+88h+res]; res
0x180030f53  mov     rcx, rdi; ld
0x180030f56  call    cs:__imp_ldap_first_entry
0x180030f5c  mov     rbx, rax
0x180030f5f  test    rax, rax
0x180030f62  jnz     short loc_180030F6E
0x180030f64  mov     ebx, 0Dh
0x180030f69  jmp     loc_180031083
0x180030f6e  lea     r8, [rsp+88h+ptr]; ptr
0x180030f76  mov     rdx, rbx; entry
0x180030f79  mov     rcx, rdi; ld
0x180030f7c  call    cs:__imp_ldap_first_attributeW
0x180030f82  mov     rbp, rax
0x180030f85  test    rax, rax
0x180030f88  jnz     short loc_180030F92
0x180030f8a  call    cs:__imp_LdapGetLastError
0x180030f90  jmp     short loc_180030F3C
0x180030f92  mov     rdx, r13
0x180030f95  mov     rcx, rbp
0x180030f98  call    cs:__imp__o__wcsicmp
0x180030f9e  test    eax, eax
0x180030fa0  jnz     short loc_180030F64
0x180030fa2  mov     r8, rbp; attr
0x180030fa5  mov     rdx, rbx; entry
0x180030fa8  mov     rcx, rdi; ld
0x180030fab  call    cs:__imp_ldap_get_valuesW
0x180030fb1  mov     r14, rax
0x180030fb4  test    rax, rax
0x180030fb7  jz      short loc_180030F8A
0x180030fb9  mov     rcx, [rax]
0x180030fbc  test    rcx, rcx
0x180030fbf  jz      short loc_180030F64
0x180030fc1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030fc5  inc     rax
0x180030fc8  cmp     [rcx+rax*2], r12w
0x180030fcd  jnz     short loc_180030FC5
0x180030fcf  inc     eax
0x180030fd1  mov     ecx, 40h ; '@'; uFlags
0x180030fd6  mov     edi, eax
0x180030fd8  lea     rdx, [rax+rax]; uBytes
0x180030fdc  call    cs:__imp_LocalAlloc
0x180030fe2  mov     rsi, rax
0x180030fe5  test    rax, rax
0x180030fe8  jnz     short loc_180030FF2
0x180030fea  lea     ebx, [rax+8]
0x180030fed  jmp     loc_180031083
0x180030ff2  test    rdi, rdi
0x180030ff5  jz      short loc_180031072
0x180030ff7  cmp     rdi, 7FFFFFFFh
0x180030ffe  jbe     short loc_180031007
0x180031000  mov     ebx, 80070057h
0x180031005  jmp     short loc_18003107C
0x180031007  mov     rcx, [r14]
0x18003100a  mov     eax, 7FFFFFFEh
0x18003100f  mov     rdx, rsi
0x180031012  test    rax, rax
0x180031015  jz      short loc_180031036
0x180031017  movzx   r8d, word ptr [rcx]
0x18003101b  test    r8w, r8w
0x18003101f  jz      short loc_180031036
0x180031021  mov     [rdx], r8w
0x180031025  add     rcx, 2
0x180031029  add     rdx, 2
0x18003102d  dec     rax
0x180031030  sub     rdi, 1
0x180031034  jnz     short loc_180031012
0x180031036  mov     rax, rdi
0x180031039  lea     rcx, [rdx-2]
0x18003103d  neg     rax
0x180031040  sbb     ebx, ebx
0x180031042  not     ebx
0x180031044  and     ebx, 8007007Ah
0x18003104a  test    rdi, rdi
0x18003104d  cmovnz  rcx, rdx
0x180031051  mov     [rcx], r12w
0x180031055  jnz     short loc_180031067
0x180031057  mov     eax, ebx
0x180031059  and     eax, 1FFF0000h
0x18003105e  cmp     eax, 70000h
0x180031063  jz      short loc_180031080
0x180031065  jmp     short loc_180031083
0x180031067  mov     [r15], rsi
0x18003106a  mov     ebx, r12d
0x18003106d  mov     rsi, r12
0x180031070  jmp     short loc_180031083
0x180031072  mov     ebx, 80070057h
0x180031077  test    rdi, rdi
0x18003107a  jz      short loc_180031080
0x18003107c  mov     [rax], r12w
0x180031080  movzx   ebx, bx
0x180031083  mov     rcx, rsi; hMem
0x180031086  call    cs:__imp_LocalFree
0x18003108c  mov     rcx, [rsp+88h+res]; res
0x180031094  call    cs:__imp_ldap_msgfree
0x18003109a  mov     rcx, rbp; Block
0x18003109d  call    cs:__imp_ldap_memfreeW
0x1800310a3  mov     rcx, r14; vals
0x1800310a6  call    cs:__imp_ldap_value_freeW
0x1800310ac  mov     eax, ebx
0x1800310ae  mov     rbx, [rsp+88h+arg_0]
0x1800310b6  add     rsp, 50h
0x1800310ba  pop     r15
0x1800310bc  pop     r14
0x1800310be  pop     r13
0x1800310c0  pop     r12
0x1800310c2  pop     rdi
0x1800310c3  pop     rsi
0x1800310c4  pop     rbp
0x1800310c5  retn
```
