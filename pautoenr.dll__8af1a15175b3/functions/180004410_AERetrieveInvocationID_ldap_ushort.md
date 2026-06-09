# AERetrieveInvocationID(ldap *,ushort * *)

- ea: `0x180004410`
- end: `0x180004628`
- name: `?AERetrieveInvocationID@@YAHPEAUldap@@PEAPEAG@Z`
- size: `536`
- prototype: `_BOOL8 __fastcall(LDAP *ExternalHandle, RPC_WSTR *StringUuid)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003d10`

## callees

- `0x180004410`
- `0x180007ce6`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800045b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800045b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045fc`
- `WLDAP32!__imp_ldap_first_entry` at `0x1800044b3`
- `WLDAP32!__imp_ldap_first_entry` at `0x18000453e`
- `WLDAP32!__imp_ldap_first_entry` at `0x1800044b3`
- `WLDAP32!__imp_ldap_first_entry` at `0x18000453e`
- `WLDAP32!__imp_ldap_msgfree` at `0x180004604`
- `WLDAP32!__imp_ldap_msgfree` at `0x18000461d`
- `WLDAP32!__imp_ldap_msgfree` at `0x180004604`
- `WLDAP32!__imp_ldap_msgfree` at `0x18000461d`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800045a9`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800045a9`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800044cd`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x1800044cd`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x180004554`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x180004554`
- `WLDAP32!__imp_ldap_search_stW` at `0x18000449a`
- `WLDAP32!__imp_ldap_search_stW` at `0x180004529`
- `WLDAP32!__imp_ldap_search_stW` at `0x18000449a`
- `WLDAP32!__imp_ldap_search_stW` at `0x180004529`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180004612`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180004612`
- `RPCRT4!UuidToStringW` at `0x1800045e9`
- `RPCRT4!UuidToStringW` at `0x1800045e9`

## string_xrefs

- `0x18000441f`: `dsServiceName`

## pseudocode

```c
_BOOL8 __fastcall AERetrieveInvocationID(LDAP *ExternalHandle, RPC_WSTR *StringUuid)
{
  BOOL v4; // ebp
  PWCHAR *v5; // rdi
  LDAPMessage *entry; // rax
  PWCHAR *valuesW; // rax
  LDAPMessage *v8; // rax
  struct berval **values_lenW; // rax
  struct berval **v10; // rbx
  struct berval *v12; // rax
  UUID *v13; // r14
  ULONG bv_len; // ecx
  PCHAR bv_val; // rdx
  PWSTR attr[2]; // [rsp+40h] [rbp-48h] BYREF
  PWSTR attrs[2]; // [rsp+50h] [rbp-38h] BYREF
  struct l_timeval timeout; // [rsp+90h] [rbp+8h] BYREF
  PLDAPMessage v19; // [rsp+A0h] [rbp+18h] BYREF
  LDAPMessage *res; // [rsp+A8h] [rbp+20h] BYREF

  attr[0] = L"dsServiceName";
  attrs[0] = L"invocationId";
  attr[1] = 0;
  attrs[1] = 0;
  v4 = 0;
  res = 0;
  v19 = 0;
  if ( ExternalHandle && StringUuid )
  {
    *StringUuid = 0;
    v5 = 0;
    timeout = (struct l_timeval)300LL;
    if ( !ldap_search_stW(ExternalHandle, 0, 0, (const PWSTR)L"(objectCategory=*)", attr, 0, &timeout, &res) )
    {
      entry = ldap_first_entry(ExternalHandle, res);
      if ( entry )
      {
        valuesW = ldap_get_valuesW(ExternalHandle, entry, attr[0]);
        v5 = valuesW;
        if ( valuesW )
        {
          if ( *valuesW )
          {
            timeout = (struct l_timeval)300LL;
            if ( !ldap_search_stW(
                    ExternalHandle,
                    *valuesW,
                    0,
                    (const PWSTR)L"(objectCategory=*)",
                    attrs,
                    0,
                    &timeout,
                    &v19) )
            {
              v8 = ldap_first_entry(ExternalHandle, v19);
              if ( v8 )
              {
                values_lenW = ldap_get_values_lenW(ExternalHandle, v8, attrs[0]);
                v10 = values_lenW;
                if ( values_lenW )
                {
                  v12 = *values_lenW;
                  if ( v12 )
                  {
                    v13 = (UUID *)LocalAlloc(0x40u, v12->bv_len);
                    if ( v13 )
                    {
                      bv_len = (*v10)->bv_len;
                      if ( bv_len )
                      {
                        bv_val = (*v10)->bv_val;
                        if ( bv_val )
                        {
                          memcpy_0(v13, bv_val, bv_len);
                          v4 = UuidToStringW(v13, StringUuid) == 0;
                        }
                      }
                      LocalFree(v13);
                    }
                  }
                  ldap_value_free_len(v10);
                }
              }
            }
          }
        }
      }
    }
    if ( v19 )
      ldap_msgfree(v19);
    if ( v5 )
      ldap_value_freeW(v5);
    if ( res )
      ldap_msgfree(res);
  }
  return v4;
}

```

## disassembly

```asm
0x180004410  mov     r11, rsp
0x180004413  push    rbx
0x180004414  push    rbp
0x180004415  push    rsi
0x180004416  push    r14
0x180004418  sub     rsp, 68h
0x18000441c  xor     r14d, r14d
0x18000441f  lea     rax, aDsservicename; "dsServiceName"
0x180004426  mov     [r11-48h], rax
0x18000442a  lea     rax, aInvocationid; "invocationId"
0x180004431  mov     [r11-38h], rax
0x180004435  mov     rsi, rdx
0x180004438  mov     [r11-40h], r14
0x18000443c  mov     rbx, rcx
0x18000443f  mov     [r11-30h], r14
0x180004443  mov     ebp, r14d
0x180004446  mov     [r11+20h], r14
0x18000444a  mov     [r11+18h], r14
0x18000444e  test    rcx, rcx
0x180004451  jz      loc_180004592
0x180004457  test    rdx, rdx
0x18000445a  jz      loc_180004592
0x180004460  lea     rax, [r11+20h]
0x180004464  mov     [rdx], r14
0x180004467  mov     [r11-50h], rax
0x18000446b  lea     r9, aObjectcategory_1; "(objectCategory=*)"
0x180004472  lea     rax, [r11+8]
0x180004476  mov     [r11-28h], rdi
0x18000447a  mov     [r11-58h], rax
0x18000447e  xor     r8d, r8d; scope
0x180004481  lea     rax, [r11-48h]
0x180004485  mov     [r11-60h], r14d
0x180004489  xor     edx, edx; base
0x18000448b  mov     [r11-68h], rax
0x18000448f  mov     edi, r14d
0x180004492  mov     qword ptr [r11+8], 12Ch
0x18000449a  call    cs:__imp_ldap_search_stW
0x1800044a0  test    eax, eax
0x1800044a2  jnz     loc_180004562
0x1800044a8  mov     rdx, [rsp+88h+res]; res
0x1800044b0  mov     rcx, rbx; ld
0x1800044b3  call    cs:__imp_ldap_first_entry
0x1800044b9  test    rax, rax
0x1800044bc  jz      loc_180004562
0x1800044c2  mov     r8, [rsp+88h+attr]; attr
0x1800044c7  mov     rdx, rax; entry
0x1800044ca  mov     rcx, rbx; ld
0x1800044cd  call    cs:__imp_ldap_get_valuesW
0x1800044d3  mov     rdi, rax
0x1800044d6  test    rax, rax
0x1800044d9  jz      loc_180004562
0x1800044df  cmp     [rax], rbp
0x1800044e2  jz      short loc_180004562
0x1800044e4  lea     rax, [rsp+88h+arg_10]
0x1800044ec  mov     qword ptr [rsp+88h+arg_0.tv_sec], 12Ch
0x1800044f8  mov     rdx, [rdi]; base
0x1800044fb  lea     r9, aObjectcategory_1; "(objectCategory=*)"
0x180004502  mov     [rsp+88h+var_50], rax; res
0x180004507  xor     r8d, r8d; scope
0x18000450a  lea     rax, [rsp+88h+arg_0]
0x180004512  mov     rcx, rbx; ld
0x180004515  mov     [rsp+88h+timeout], rax; timeout
0x18000451a  lea     rax, [rsp+88h+var_38]
0x18000451f  mov     [rsp+88h+attrsonly], r14d; attrsonly
0x180004524  mov     [rsp+88h+attrs], rax; attrs
0x180004529  call    cs:__imp_ldap_search_stW
0x18000452f  test    eax, eax
0x180004531  jnz     short loc_180004562
0x180004533  mov     rdx, [rsp+88h+arg_10]; res
0x18000453b  mov     rcx, rbx; ld
0x18000453e  call    cs:__imp_ldap_first_entry
0x180004544  test    rax, rax
0x180004547  jz      short loc_180004562
0x180004549  mov     r8, [rsp+88h+var_38]; attr
0x18000454e  mov     rdx, rax; Message
0x180004551  mov     rcx, rbx; ExternalHandle
0x180004554  call    cs:__imp_ldap_get_values_lenW
0x18000455a  mov     rbx, rax
0x18000455d  test    rax, rax
0x180004560  jnz     short loc_18000459E
0x180004562  mov     rcx, [rsp+88h+arg_10]; res
0x18000456a  test    rcx, rcx
0x18000456d  jnz     loc_180004604
0x180004573  test    rdi, rdi
0x180004576  jnz     loc_18000460F
0x18000457c  mov     rcx, [rsp+88h+res]; res
0x180004584  mov     rdi, [rsp+88h+var_28]
0x180004589  test    rcx, rcx
0x18000458c  jnz     loc_18000461D
0x180004592  mov     eax, ebp
0x180004594  add     rsp, 68h
0x180004598  pop     r14
0x18000459a  pop     rsi
0x18000459b  pop     rbp
0x18000459c  pop     rbx
0x18000459d  retn
0x18000459e  mov     rax, [rax]
0x1800045a1  test    rax, rax
0x1800045a4  jnz     short loc_1800045B1
0x1800045a6  mov     rcx, rbx; vals
0x1800045a9  call    cs:__imp_ldap_value_free_len
0x1800045af  jmp     short loc_180004562
0x1800045b1  mov     edx, [rax]; uBytes
0x1800045b3  mov     ecx, 40h ; '@'; uFlags
0x1800045b8  call    cs:__imp_LocalAlloc
0x1800045be  mov     r14, rax
0x1800045c1  test    rax, rax
0x1800045c4  jz      short loc_1800045A6
0x1800045c6  mov     rax, [rbx]
0x1800045c9  mov     ecx, [rax]
0x1800045cb  test    ecx, ecx
0x1800045cd  jz      short loc_1800045F9
0x1800045cf  mov     rdx, [rax+8]; Src
0x1800045d3  test    rdx, rdx
0x1800045d6  jz      short loc_1800045F9
0x1800045d8  mov     r8d, ecx; Size
0x1800045db  mov     rcx, r14; void *
0x1800045de  call    memcpy_0
0x1800045e3  mov     rdx, rsi; StringUuid
0x1800045e6  mov     rcx, r14; Uuid
0x1800045e9  call    cs:__imp_UuidToStringW
0x1800045ef  test    eax, eax
0x1800045f1  mov     ecx, 1
0x1800045f6  cmovz   ebp, ecx
0x1800045f9  mov     rcx, r14; hMem
0x1800045fc  call    cs:__imp_LocalFree
0x180004602  jmp     short loc_1800045A6
0x180004604  call    cs:__imp_ldap_msgfree
0x18000460a  jmp     loc_180004573
0x18000460f  mov     rcx, rdi; vals
0x180004612  call    cs:__imp_ldap_value_freeW
0x180004618  jmp     loc_18000457C
0x18000461d  call    cs:__imp_ldap_msgfree
0x180004623  jmp     loc_180004592
```
