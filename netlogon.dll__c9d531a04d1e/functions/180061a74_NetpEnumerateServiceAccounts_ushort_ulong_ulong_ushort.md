# NetpEnumerateServiceAccounts(ushort *,ulong,ulong *,ushort * * *)

- ea: `0x180061a74`
- end: `0x180061dbc`
- name: `?NetpEnumerateServiceAccounts@@YAJPEAGKPEAKPEAPEAPEAG@Z`
- size: `840`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, unsigned int *, unsigned __int16 ***)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d4c4`
- `0x1800638c0`

## callees

- `0x180004420`
- `0x180007278`
- `0x18000d100`
- `0x18000ed34`
- `0x180061a74`
- `0x180061e88`
- `0x18006242c`
- `0x180062604`
- `0x180089ab4`

## import_xrefs

- `LSASRV!LsaIIsContainerized` at `0x180061ac9`
- `LSASRV!LsaIIsContainerized` at `0x180061ac9`
- `netutils!NetApiBufferFree` at `0x180061cf3`
- `netutils!NetApiBufferFree` at `0x180061d13`
- `netutils!NetApiBufferFree` at `0x180061d92`
- `netutils!NetApiBufferFree` at `0x180061da3`
- `netutils!NetApiBufferFree` at `0x180061cf3`
- `netutils!NetApiBufferFree` at `0x180061d13`
- `netutils!NetApiBufferFree` at `0x180061d92`
- `netutils!NetApiBufferFree` at `0x180061da3`
- `netutils!NetApiBufferAllocate` at `0x180061c17`
- `netutils!NetApiBufferAllocate` at `0x180061c9f`
- `netutils!NetApiBufferAllocate` at `0x180061c17`
- `netutils!NetApiBufferAllocate` at `0x180061c9f`
- `WLDAP32!__imp_ldap_unbind` at `0x180061d01`
- `WLDAP32!__imp_ldap_unbind` at `0x180061d01`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180061bff`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180061c70`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180061bff`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180061c70`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180061cc9`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180061d21`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180061d2f`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180061cc9`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180061d21`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180061d2f`

## string_xrefs

- `0x180061b79`: `computer`
- `0x180061ad3`: `NetpEnumerateServiceAccounts: not supported when containerized\n`
- `0x180061b20`: `NetrEnumerateServiceAccounts: Failed to find usable DC\n`
- `0x180061b48`: `NetrEnumerateServiceAccounts: Failed to LDAP bind as SYSTEM\n`
- `0x180061b9a`: `NetrEnumerateServiceAccounts: Failed to find computer object for %s\n`
- `0x180061bb8`: `msDS-HostServiceAccount`
- `0x180061bf0`: `NetrEnumerateServiceAccounts: Failed to read msDS-HostServiceAccount attribute on computer account\n`
- `0x180061d52`: `NetrEnumerateServiceAccounts: Failed to get account name for %s\n`

## pseudocode

```c
__int64 __fastcall NetpEnumerateServiceAccounts(unsigned __int16 *a1, int a2, unsigned int *a3, unsigned __int16 ***a4)
{
  int AccountObject; // ebx
  unsigned __int16 ***v5; // r12
  unsigned int *v6; // r13
  LDAP *v7; // r14
  PWCHAR *v8; // rsi
  ULONG v9; // r15d
  const void **v10; // rdi
  unsigned int DcNameEx2; // eax
  void *v12; // r9
  int SingleAttribute; // eax
  DWORD v14; // eax
  __int64 i; // r12
  __int64 v16; // rax
  DWORD v17; // eax
  LPVOID *v18; // rcx
  ULONG j; // edi
  PWCHAR *v21; // [rsp+40h] [rbp-38h] BYREF
  LDAP *ld; // [rsp+48h] [rbp-30h] BYREF
  LPVOID v23; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int16 *v24; // [rsp+58h] [rbp-20h] BYREF
  PWCHAR *vals; // [rsp+60h] [rbp-18h] BYREF
  LPVOID Buffer; // [rsp+C0h] [rbp+48h] BYREF
  size_t Size; // [rsp+C8h] [rbp+50h] BYREF
  unsigned int *v28; // [rsp+D0h] [rbp+58h]
  unsigned __int16 ***v29; // [rsp+D8h] [rbp+60h]

  v29 = a4;
  v28 = a3;
  LODWORD(Size) = a2;
  AccountObject = 0;
  v5 = a4;
  *a3 = 0;
  v6 = a3;
  *a4 = 0;
  v7 = 0;
  ld = 0;
  v8 = 0;
  v23 = 0;
  v9 = 0;
  vals = 0;
  v10 = 0;
  v24 = 0;
  Buffer = 0;
  v21 = 0;
  if ( (unsigned __int8)LsaIIsContainerized() )
  {
    NlPrintRoutine(0x40u, L"NetpEnumerateServiceAccounts: not supported when containerized\n");
  }
  else
  {
    DcNameEx2 = DsrGetDcNameEx2(0, 0, 0, 0, 0, 0, 0x40000000u, (struct _DOMAIN_CONTROLLER_INFOW **)&v23);
    AccountObject = NetpApiStatusToNtStatus(DcNameEx2);
    if ( AccountObject >= 0 )
    {
      AccountObject = NetpLdapBind(*(PWSTR *)v23, *((const unsigned __int16 **)v23 + 5), &ld, v12, 0);
      if ( AccountObject >= 0 )
      {
        LODWORD(Size) = 0;
        v7 = ld;
        AccountObject = NetpGetAccountObject(ld, NlGlobalUnicodeComputerName, L"computer", &v24, (int *)&Size);
        if ( AccountObject >= 0 )
        {
          SingleAttribute = NetpGetSingleAttribute(v7, v24, L"msDS-HostServiceAccount", &vals);
          v8 = vals;
          AccountObject = SingleAttribute;
          if ( SingleAttribute != -1073741275 && vals && *vals )
          {
            if ( SingleAttribute >= 0 )
            {
              v9 = ldap_count_valuesW(vals);
              v14 = NetApiBufferAllocate(8 * v9, &Buffer);
              AccountObject = NetpApiStatusToNtStatus(v14);
              if ( AccountObject >= 0 )
              {
                memset_0(Buffer, 0, 8 * v9);
                for ( i = 0; (unsigned int)i < v9; i = (unsigned int)(i + 1) )
                {
                  AccountObject = NetpGetSingleAttribute(v7, v8[i], L"cn", &v21);
                  if ( AccountObject < 0 )
                  {
                    NlPrintRoutine(0x40u, L"NetrEnumerateServiceAccounts: Failed to get account name for %s\n", v8[i]);
                    v10 = (const void **)v21;
                    break;
                  }
                  v10 = (const void **)v21;
                  if ( ldap_count_valuesW(v21) != 1 )
                  {
                    AccountObject = -1073740796;
                    break;
                  }
                  v16 = -1;
                  do
                    ++v16;
                  while ( *((_WORD *)*v10 + v16) );
                  LODWORD(Size) = 2 * v16 + 2;
                  v17 = NetApiBufferAllocate(Size, (LPVOID *)Buffer + i);
                  AccountObject = NetpApiStatusToNtStatus(v17);
                  if ( AccountObject < 0 )
                    break;
                  memcpy_0(*((void **)Buffer + i), *v10, (unsigned int)Size);
                  ldap_value_freeW((PWCHAR *)v10);
                  v10 = 0;
                  v21 = 0;
                }
                v6 = v28;
              }
              v5 = v29;
            }
            else
            {
              NlPrintRoutine(
                0x40u,
                L"NetrEnumerateServiceAccounts: Failed to read msDS-HostServiceAccount attribute on computer account\n");
            }
          }
          else
          {
            AccountObject = 0;
          }
        }
        else
        {
          NlPrintRoutine(
            0x40u,
            L"NetrEnumerateServiceAccounts: Failed to find computer object for %s\n",
            NlGlobalUnicodeComputerName);
        }
      }
      else
      {
        NlPrintRoutine(0x40u, L"NetrEnumerateServiceAccounts: Failed to LDAP bind as SYSTEM\n");
        v7 = ld;
      }
    }
    else
    {
      NlPrintRoutine(0x40u, L"NetrEnumerateServiceAccounts: Failed to find usable DC\n");
    }
  }
  if ( v23 )
    NetApiBufferFree(v23);
  if ( v7 )
    ldap_unbind(v7);
  if ( v24 )
    NetApiBufferFree(v24);
  if ( v8 )
    ldap_value_freeW(v8);
  if ( v10 )
    ldap_value_freeW((PWCHAR *)v10);
  if ( AccountObject < 0 )
  {
    v18 = (LPVOID *)Buffer;
  }
  else
  {
    v18 = 0;
    *v5 = (unsigned __int16 **)Buffer;
    *v6 = v9;
    Buffer = 0;
  }
  if ( v18 )
  {
    for ( j = 0; j < v9; ++j )
    {
      if ( v18[j] )
      {
        NetApiBufferFree(v18[j]);
        v18 = (LPVOID *)Buffer;
      }
    }
    NetApiBufferFree(v18);
  }
  return (unsigned int)AccountObject;
}

```

## disassembly

```asm
0x180061a74  mov     rax, rsp
0x180061a77  mov     [rax+20h], r9
0x180061a7b  mov     [rax+18h], r8
0x180061a7f  mov     [rax+10h], edx
0x180061a82  mov     [rax+8], rcx
0x180061a86  push    rbp
0x180061a87  push    rbx
0x180061a88  push    rsi
0x180061a89  push    rdi
0x180061a8a  push    r12
0x180061a8c  push    r13
0x180061a8e  push    r14
0x180061a90  push    r15
0x180061a92  mov     rbp, rsp
0x180061a95  sub     rsp, 78h
0x180061a99  xor     ebx, ebx
0x180061a9b  mov     r12, r9
0x180061a9e  mov     [r8], ebx
0x180061aa1  mov     r13, r8
0x180061aa4  mov     [r9], rbx
0x180061aa7  mov     r14d, ebx
0x180061aaa  mov     [rbp+ld], rbx
0x180061aae  mov     esi, ebx
0x180061ab0  mov     [rbp+var_28], rbx
0x180061ab4  mov     r15d, ebx
0x180061ab7  mov     [rbp+vals], rbx
0x180061abb  mov     edi, ebx
0x180061abd  mov     [rbp+var_20], rbx
0x180061ac1  mov     [rbp+Buffer], rbx
0x180061ac5  mov     [rbp+var_38], rbx
0x180061ac9  call    cs:__imp_LsaIIsContainerized
0x180061acf  test    al, al
0x180061ad1  jz      short loc_180061AE9
0x180061ad3  lea     rdx, aNetpenumerates; "NetpEnumerateServiceAccounts: not suppo"...
0x180061ada  mov     ecx, 40h ; '@'; unsigned int
0x180061adf  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061ae4  jmp     loc_180061CEA
0x180061ae9  lea     rax, [rbp+var_28]
0x180061aed  xor     r9d, r9d
0x180061af0  mov     [rsp+78h+var_40], rax
0x180061af5  xor     r8d, r8d
0x180061af8  mov     [rsp+78h+var_48], 40000000h
0x180061b00  xor     edx, edx
0x180061b02  mov     [rsp+78h+var_50], rbx
0x180061b07  xor     ecx, ecx
0x180061b09  mov     [rsp+78h+var_58], rbx
0x180061b0e  call    DsrGetDcNameEx2
0x180061b13  mov     ecx, eax
0x180061b15  call    NetpApiStatusToNtStatus
0x180061b1a  mov     ebx, eax
0x180061b1c  test    eax, eax
0x180061b1e  jns     short loc_180061B29
0x180061b20  lea     rdx, aNetrenumerates; "NetrEnumerateServiceAccounts: Failed to"...
0x180061b27  jmp     short loc_180061ADA
0x180061b29  mov     rcx, [rbp+var_28]
0x180061b2d  lea     r8, [rbp+ld]; struct ldap **
0x180061b31  mov     dword ptr [rsp+78h+var_58], r14d; int
0x180061b36  mov     rdx, [rcx+28h]; unsigned __int16 *
0x180061b3a  mov     rcx, [rcx]; HostName
0x180061b3d  call    ?NetpLdapBind@@YAJPEBG0PEAPEAUldap@@PEAXH@Z; NetpLdapBind(ushort const *,ushort const *,ldap * *,void *,int)
0x180061b42  mov     ebx, eax
0x180061b44  test    eax, eax
0x180061b46  jns     short loc_180061B62
0x180061b48  lea     rdx, aNetrenumerates_2; "NetrEnumerateServiceAccounts: Failed to"...
0x180061b4f  mov     ecx, 40h ; '@'; unsigned int
0x180061b54  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061b59  mov     r14, [rbp+ld]
0x180061b5d  jmp     loc_180061CEA
0x180061b62  mov     rdx, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; unsigned __int16 *
0x180061b69  lea     rax, [rbp+Size]
0x180061b6d  mov     dword ptr [rbp+Size], r14d
0x180061b71  lea     r9, [rbp+var_20]; unsigned __int16 **
0x180061b75  mov     r14, [rbp+ld]
0x180061b79  lea     r8, aComputer; "computer"
0x180061b80  mov     rcx, r14; ld
0x180061b83  mov     [rsp+78h+var_58], rax; int *
0x180061b88  call    ?NetpGetAccountObject@@YAJPEAUldap@@PEBG1PEAPEAGPEAH@Z; NetpGetAccountObject(ldap *,ushort const *,ushort const *,ushort * *,int *)
0x180061b8d  mov     ebx, eax
0x180061b8f  test    eax, eax
0x180061b91  jns     short loc_180061BB0
0x180061b93  mov     r8, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; ushort * NlGlobalUnicodeComputerName
0x180061b9a  lea     rdx, aNetrenumerates_1; "NetrEnumerateServiceAccounts: Failed to"...
0x180061ba1  mov     ecx, 40h ; '@'; unsigned int
0x180061ba6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061bab  jmp     loc_180061CEA
0x180061bb0  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x180061bb4  lea     r9, [rbp+vals]; unsigned __int16 ***
0x180061bb8  lea     r8, aMsdsHostservic; "msDS-HostServiceAccount"
0x180061bbf  mov     rcx, r14; ld
0x180061bc2  call    ?NetpGetSingleAttribute@@YAJPEAUldap@@PEBG1PEAPEAPEAG@Z; NetpGetSingleAttribute(ldap *,ushort const *,ushort const *,ushort * * *)
0x180061bc7  mov     rsi, [rbp+vals]
0x180061bcb  xor     ecx, ecx
0x180061bcd  mov     ebx, eax
0x180061bcf  cmp     eax, 0C0000225h
0x180061bd4  jz      loc_180061D6C
0x180061bda  test    rsi, rsi
0x180061bdd  jz      loc_180061D6C
0x180061be3  cmp     [rsi], rcx
0x180061be6  jz      loc_180061D6C
0x180061bec  test    eax, eax
0x180061bee  jns     short loc_180061BFC
0x180061bf0  lea     rdx, aNetrenumerates_0; "NetrEnumerateServiceAccounts: Failed to"...
0x180061bf7  jmp     loc_180061ADA
0x180061bfc  mov     rcx, rsi; vals
0x180061bff  call    cs:__imp_ldap_count_valuesW
0x180061c05  lea     rdx, [rbp+Buffer]; Buffer
0x180061c09  mov     r15d, eax
0x180061c0c  lea     r12d, ds:0[rax*8]
0x180061c14  mov     ecx, r12d; ByteCount
0x180061c17  call    cs:__imp_NetApiBufferAllocate
0x180061c1d  mov     ecx, eax
0x180061c1f  call    NetpApiStatusToNtStatus
0x180061c24  xor     edx, edx; Val
0x180061c26  mov     ebx, eax
0x180061c28  test    eax, eax
0x180061c2a  js      loc_180061CE6
0x180061c30  mov     rcx, [rbp+Buffer]; void *
0x180061c34  mov     r8d, r12d; Size
0x180061c37  call    memset_0
0x180061c3c  xor     r12d, r12d
0x180061c3f  cmp     r12d, r15d
0x180061c42  jnb     loc_180061CE2
0x180061c48  mov     rdx, [rsi+r12*8]; unsigned __int16 *
0x180061c4c  lea     r9, [rbp+var_38]; unsigned __int16 ***
0x180061c50  lea     r8, aCn; "cn"
0x180061c57  mov     rcx, r14; ld
0x180061c5a  call    ?NetpGetSingleAttribute@@YAJPEAUldap@@PEBG1PEAPEAPEAG@Z; NetpGetSingleAttribute(ldap *,ushort const *,ushort const *,ushort * * *)
0x180061c5f  mov     ebx, eax
0x180061c61  test    eax, eax
0x180061c63  js      loc_180061D4E
0x180061c69  mov     rdi, [rbp+var_38]
0x180061c6d  mov     rcx, rdi; vals
0x180061c70  call    cs:__imp_ldap_count_valuesW
0x180061c76  cmp     eax, 1
0x180061c79  jnz     short loc_180061CDD
0x180061c7b  mov     rcx, [rdi]
0x180061c7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180061c82  xor     edx, edx
0x180061c84  inc     rax
0x180061c87  cmp     [rcx+rax*2], dx
0x180061c8b  jnz     short loc_180061C84
0x180061c8d  lea     ecx, ds:2[rax*2]; ByteCount
0x180061c94  mov     rax, [rbp+Buffer]
0x180061c98  mov     dword ptr [rbp+Size], ecx
0x180061c9b  lea     rdx, [rax+r12*8]; Buffer
0x180061c9f  call    cs:__imp_NetApiBufferAllocate
0x180061ca5  mov     ecx, eax
0x180061ca7  call    NetpApiStatusToNtStatus
0x180061cac  mov     ebx, eax
0x180061cae  test    eax, eax
0x180061cb0  js      short loc_180061CE2
0x180061cb2  mov     rcx, [rbp+Buffer]
0x180061cb6  mov     r8d, dword ptr [rbp+Size]; Size
0x180061cba  mov     rdx, [rdi]; Src
0x180061cbd  mov     rcx, [rcx+r12*8]; void *
0x180061cc1  call    memcpy_0
0x180061cc6  mov     rcx, rdi; vals
0x180061cc9  call    cs:__imp_ldap_value_freeW
0x180061ccf  xor     edi, edi
0x180061cd1  mov     [rbp+var_38], rdi
0x180061cd5  inc     r12d
0x180061cd8  jmp     loc_180061C3F
0x180061cdd  mov     ebx, 0C0000404h
0x180061ce2  mov     r13, [rbp+arg_10]
0x180061ce6  mov     r12, [rbp+arg_18]
0x180061cea  mov     rcx, [rbp+var_28]; Buffer
0x180061cee  test    rcx, rcx
0x180061cf1  jz      short loc_180061CF9
0x180061cf3  call    cs:__imp_NetApiBufferFree
0x180061cf9  test    r14, r14
0x180061cfc  jz      short loc_180061D07
0x180061cfe  mov     rcx, r14; ld
0x180061d01  call    cs:__imp_ldap_unbind
0x180061d07  mov     rcx, [rbp+var_20]; Buffer
0x180061d0b  xor     r14d, r14d
0x180061d0e  test    rcx, rcx
0x180061d11  jz      short loc_180061D19
0x180061d13  call    cs:__imp_NetApiBufferFree
0x180061d19  test    rsi, rsi
0x180061d1c  jz      short loc_180061D27
0x180061d1e  mov     rcx, rsi; vals
0x180061d21  call    cs:__imp_ldap_value_freeW
0x180061d27  test    rdi, rdi
0x180061d2a  jz      short loc_180061D35
0x180061d2c  mov     rcx, rdi; vals
0x180061d2f  call    cs:__imp_ldap_value_freeW
0x180061d35  test    ebx, ebx
0x180061d37  js      short loc_180061D73
0x180061d39  mov     rax, [rbp+Buffer]
0x180061d3d  mov     rcx, r14
0x180061d40  mov     [r12], rax
0x180061d44  mov     [r13+0], r15d
0x180061d48  mov     [rbp+Buffer], rcx
0x180061d4c  jmp     short loc_180061D77
0x180061d4e  mov     r8, [rsi+r12*8]
0x180061d52  lea     rdx, aNetrenumerates_4; "NetrEnumerateServiceAccounts: Failed to"...
0x180061d59  mov     ecx, 40h ; '@'; unsigned int
0x180061d5e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180061d63  mov     rdi, [rbp+var_38]
0x180061d67  jmp     loc_180061CE2
0x180061d6c  mov     ebx, ecx
0x180061d6e  jmp     loc_180061CEA
0x180061d73  mov     rcx, [rbp+Buffer]
0x180061d77  test    rcx, rcx
0x180061d7a  jz      short loc_180061DA9
0x180061d7c  mov     edi, r14d
0x180061d7f  test    r15d, r15d
0x180061d82  jz      short loc_180061DA3
0x180061d84  mov     eax, edi
0x180061d86  mov     rdx, [rcx+rax*8]
0x180061d8a  test    rdx, rdx
0x180061d8d  jz      short loc_180061D9C
0x180061d8f  mov     rcx, rdx; Buffer
0x180061d92  call    cs:__imp_NetApiBufferFree
0x180061d98  mov     rcx, [rbp+Buffer]; Buffer
0x180061d9c  inc     edi
0x180061d9e  cmp     edi, r15d
0x180061da1  jb      short loc_180061D84
0x180061da3  call    cs:__imp_NetApiBufferFree
0x180061da9  mov     eax, ebx
0x180061dab  add     rsp, 78h
0x180061daf  pop     r15
0x180061db1  pop     r14
0x180061db3  pop     r13
0x180061db5  pop     r12
0x180061db7  pop     rdi
0x180061db8  pop     rsi
0x180061db9  pop     rbx
0x180061dba  pop     rbp
0x180061dbb  retn
```
