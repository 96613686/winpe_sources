# NetpEnumerateServiceAccounts(ushort *,ulong,ulong *,ushort * * *)

- ea: `0x1800660e0`
- end: `0x180066477`
- name: `?NetpEnumerateServiceAccounts@@YAJPEAGKPEAKPEAPEAPEAG@Z`
- size: `919`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned int *, unsigned __int16 ***)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000da50`
- `0x180068210`

## callees

- `0x1800046b0`
- `0x180007518`
- `0x18000d7a0`
- `0x18000f3e4`
- `0x1800660e0`
- `0x18006655c`
- `0x180066b80`
- `0x180066d98`
- `0x180090204`

## import_xrefs

- `LSASRV!LsaIIsContainerized` at `0x180066135`
- `LSASRV!LsaIIsContainerized` at `0x180066135`
- `netutils!NetApiBufferFree` at `0x180066383`
- `netutils!NetApiBufferFree` at `0x1800663af`
- `netutils!NetApiBufferFree` at `0x180066440`
- `netutils!NetApiBufferFree` at `0x180066457`
- `netutils!NetApiBufferFree` at `0x180066383`
- `netutils!NetApiBufferFree` at `0x1800663af`
- `netutils!NetApiBufferFree` at `0x180066440`
- `netutils!NetApiBufferFree` at `0x180066457`
- `netutils!NetApiBufferAllocate` at `0x18006628f`
- `netutils!NetApiBufferAllocate` at `0x180066323`
- `netutils!NetApiBufferAllocate` at `0x18006628f`
- `netutils!NetApiBufferAllocate` at `0x180066323`
- `WLDAP32!__imp_ldap_unbind` at `0x180066397`
- `WLDAP32!__imp_ldap_unbind` at `0x180066397`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180066271`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x1800662ee`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180066271`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x1800662ee`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180066353`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800663c3`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800663d7`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180066353`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800663c3`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800663d7`

## string_xrefs

- `0x1800661eb`: `computer`
- `0x180066145`: `NetpEnumerateServiceAccounts: not supported when containerized\n`
- `0x180066192`: `NetrEnumerateServiceAccounts: Failed to find usable DC\n`
- `0x1800661ba`: `NetrEnumerateServiceAccounts: Failed to LDAP bind as SYSTEM\n`
- `0x18006620c`: `NetrEnumerateServiceAccounts: Failed to find computer object for %s\n`
- `0x18006622a`: `msDS-HostServiceAccount`
- `0x180066262`: `NetrEnumerateServiceAccounts: Failed to read msDS-HostServiceAccount attribute on computer account\n`
- `0x180066400`: `NetrEnumerateServiceAccounts: Failed to get account name for %s\n`

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
    DcNameEx2 = DsrGetDcNameEx2(0, 0, 0, 0x40000000u, (__int64)&v23);
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
0x1800660e0  mov     rax, rsp
0x1800660e3  mov     [rax+20h], r9
0x1800660e7  mov     [rax+18h], r8
0x1800660eb  mov     [rax+10h], edx
0x1800660ee  mov     [rax+8], rcx
0x1800660f2  push    rbp
0x1800660f3  push    rbx
0x1800660f4  push    rsi
0x1800660f5  push    rdi
0x1800660f6  push    r12
0x1800660f8  push    r13
0x1800660fa  push    r14
0x1800660fc  push    r15
0x1800660fe  mov     rbp, rsp
0x180066101  sub     rsp, 78h
0x180066105  xor     ebx, ebx
0x180066107  mov     r12, r9
0x18006610a  mov     [r8], ebx
0x18006610d  mov     r13, r8
0x180066110  mov     [r9], rbx
0x180066113  mov     r14d, ebx
0x180066116  mov     [rbp+ld], rbx
0x18006611a  mov     esi, ebx
0x18006611c  mov     [rbp+var_28], rbx
0x180066120  mov     r15d, ebx
0x180066123  mov     [rbp+vals], rbx
0x180066127  mov     edi, ebx
0x180066129  mov     [rbp+var_20], rbx
0x18006612d  mov     [rbp+Buffer], rbx
0x180066131  mov     [rbp+var_38], rbx
0x180066135  call    cs:__imp_LsaIIsContainerized
0x18006613c  nop     dword ptr [rax+rax+00h]
0x180066141  test    al, al
0x180066143  jz      short loc_18006615B
0x180066145  lea     rdx, aNetpenumerates; "NetpEnumerateServiceAccounts: not suppo"...
0x18006614c  mov     ecx, 40h ; '@'; unsigned int
0x180066151  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180066156  jmp     loc_18006637A
0x18006615b  lea     rax, [rbp+var_28]
0x18006615f  xor     r9d, r9d
0x180066162  mov     [rsp+78h+var_40], rax
0x180066167  xor     r8d, r8d
0x18006616a  mov     [rsp+78h+var_48], 40000000h
0x180066172  xor     edx, edx
0x180066174  mov     [rsp+78h+var_50], rbx
0x180066179  xor     ecx, ecx
0x18006617b  mov     [rsp+78h+var_58], rbx
0x180066180  call    DsrGetDcNameEx2
0x180066185  mov     ecx, eax
0x180066187  call    NetpApiStatusToNtStatus
0x18006618c  mov     ebx, eax
0x18006618e  test    eax, eax
0x180066190  jns     short loc_18006619B
0x180066192  lea     rdx, aNetrenumerates; "NetrEnumerateServiceAccounts: Failed to"...
0x180066199  jmp     short loc_18006614C
0x18006619b  mov     rcx, [rbp+var_28]
0x18006619f  lea     r8, [rbp+ld]; struct ldap **
0x1800661a3  mov     dword ptr [rsp+78h+var_58], r14d; int
0x1800661a8  mov     rdx, [rcx+28h]; unsigned __int16 *
0x1800661ac  mov     rcx, [rcx]; HostName
0x1800661af  call    ?NetpLdapBind@@YAJPEBG0PEAPEAUldap@@PEAXH@Z; NetpLdapBind(ushort const *,ushort const *,ldap * *,void *,int)
0x1800661b4  mov     ebx, eax
0x1800661b6  test    eax, eax
0x1800661b8  jns     short loc_1800661D4
0x1800661ba  lea     rdx, aNetrenumerates_2; "NetrEnumerateServiceAccounts: Failed to"...
0x1800661c1  mov     ecx, 40h ; '@'; unsigned int
0x1800661c6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800661cb  mov     r14, [rbp+ld]
0x1800661cf  jmp     loc_18006637A
0x1800661d4  mov     rdx, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; unsigned __int16 *
0x1800661db  lea     rax, [rbp+Size]
0x1800661df  mov     dword ptr [rbp+Size], r14d
0x1800661e3  lea     r9, [rbp+var_20]; unsigned __int16 **
0x1800661e7  mov     r14, [rbp+ld]
0x1800661eb  lea     r8, aComputer; "computer"
0x1800661f2  mov     rcx, r14; ld
0x1800661f5  mov     [rsp+78h+var_58], rax; int *
0x1800661fa  call    ?NetpGetAccountObject@@YAJPEAUldap@@PEBG1PEAPEAGPEAH@Z; NetpGetAccountObject(ldap *,ushort const *,ushort const *,ushort * *,int *)
0x1800661ff  mov     ebx, eax
0x180066201  test    eax, eax
0x180066203  jns     short loc_180066222
0x180066205  mov     r8, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; ushort * NlGlobalUnicodeComputerName
0x18006620c  lea     rdx, aNetrenumerates_1; "NetrEnumerateServiceAccounts: Failed to"...
0x180066213  mov     ecx, 40h ; '@'; unsigned int
0x180066218  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006621d  jmp     loc_18006637A
0x180066222  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x180066226  lea     r9, [rbp+vals]; unsigned __int16 ***
0x18006622a  lea     r8, aMsdsHostservic; "msDS-HostServiceAccount"
0x180066231  mov     rcx, r14; ld
0x180066234  call    ?NetpGetSingleAttribute@@YAJPEAUldap@@PEBG1PEAPEAPEAG@Z; NetpGetSingleAttribute(ldap *,ushort const *,ushort const *,ushort * * *)
0x180066239  mov     rsi, [rbp+vals]
0x18006623d  xor     ecx, ecx
0x18006623f  mov     ebx, eax
0x180066241  cmp     eax, 0C0000225h
0x180066246  jz      loc_18006641A
0x18006624c  test    rsi, rsi
0x18006624f  jz      loc_18006641A
0x180066255  cmp     [rsi], rcx
0x180066258  jz      loc_18006641A
0x18006625e  test    eax, eax
0x180066260  jns     short loc_18006626E
0x180066262  lea     rdx, aNetrenumerates_0; "NetrEnumerateServiceAccounts: Failed to"...
0x180066269  jmp     loc_18006614C
0x18006626e  mov     rcx, rsi; vals
0x180066271  call    cs:__imp_ldap_count_valuesW
0x180066278  nop     dword ptr [rax+rax+00h]
0x18006627d  lea     rdx, [rbp+Buffer]; Buffer
0x180066281  mov     r15d, eax
0x180066284  lea     r12d, ds:0[rax*8]
0x18006628c  mov     ecx, r12d; ByteCount
0x18006628f  call    cs:__imp_NetApiBufferAllocate
0x180066296  nop     dword ptr [rax+rax+00h]
0x18006629b  mov     ecx, eax
0x18006629d  call    NetpApiStatusToNtStatus
0x1800662a2  xor     edx, edx; Val
0x1800662a4  mov     ebx, eax
0x1800662a6  test    eax, eax
0x1800662a8  js      loc_180066376
0x1800662ae  mov     rcx, [rbp+Buffer]; void *
0x1800662b2  mov     r8d, r12d; Size
0x1800662b5  call    memset_0
0x1800662ba  xor     r12d, r12d
0x1800662bd  cmp     r12d, r15d
0x1800662c0  jnb     loc_180066372
0x1800662c6  mov     rdx, [rsi+r12*8]; unsigned __int16 *
0x1800662ca  lea     r9, [rbp+var_38]; unsigned __int16 ***
0x1800662ce  lea     r8, aCn; "cn"
0x1800662d5  mov     rcx, r14; ld
0x1800662d8  call    ?NetpGetSingleAttribute@@YAJPEAUldap@@PEBG1PEAPEAPEAG@Z; NetpGetSingleAttribute(ldap *,ushort const *,ushort const *,ushort * * *)
0x1800662dd  mov     ebx, eax
0x1800662df  test    eax, eax
0x1800662e1  js      loc_1800663FC
0x1800662e7  mov     rdi, [rbp+var_38]
0x1800662eb  mov     rcx, rdi; vals
0x1800662ee  call    cs:__imp_ldap_count_valuesW
0x1800662f5  nop     dword ptr [rax+rax+00h]
0x1800662fa  cmp     eax, 1
0x1800662fd  jnz     short loc_18006636D
0x1800662ff  mov     rcx, [rdi]
0x180066302  or      rax, 0FFFFFFFFFFFFFFFFh
0x180066306  xor     edx, edx
0x180066308  inc     rax
0x18006630b  cmp     [rcx+rax*2], dx
0x18006630f  jnz     short loc_180066308
0x180066311  lea     ecx, ds:2[rax*2]; ByteCount
0x180066318  mov     rax, [rbp+Buffer]
0x18006631c  mov     dword ptr [rbp+Size], ecx
0x18006631f  lea     rdx, [rax+r12*8]; Buffer
0x180066323  call    cs:__imp_NetApiBufferAllocate
0x18006632a  nop     dword ptr [rax+rax+00h]
0x18006632f  mov     ecx, eax
0x180066331  call    NetpApiStatusToNtStatus
0x180066336  mov     ebx, eax
0x180066338  test    eax, eax
0x18006633a  js      short loc_180066372
0x18006633c  mov     rcx, [rbp+Buffer]
0x180066340  mov     r8d, dword ptr [rbp+Size]; Size
0x180066344  mov     rdx, [rdi]; Src
0x180066347  mov     rcx, [rcx+r12*8]; void *
0x18006634b  call    memcpy_0
0x180066350  mov     rcx, rdi; vals
0x180066353  call    cs:__imp_ldap_value_freeW
0x18006635a  nop     dword ptr [rax+rax+00h]
0x18006635f  xor     edi, edi
0x180066361  mov     [rbp+var_38], rdi
0x180066365  inc     r12d
0x180066368  jmp     loc_1800662BD
0x18006636d  mov     ebx, 0C0000404h
0x180066372  mov     r13, [rbp+arg_10]
0x180066376  mov     r12, [rbp+arg_18]
0x18006637a  mov     rcx, [rbp+var_28]; Buffer
0x18006637e  test    rcx, rcx
0x180066381  jz      short loc_18006638F
0x180066383  call    cs:__imp_NetApiBufferFree
0x18006638a  nop     dword ptr [rax+rax+00h]
0x18006638f  test    r14, r14
0x180066392  jz      short loc_1800663A3
0x180066394  mov     rcx, r14; ld
0x180066397  call    cs:__imp_ldap_unbind
0x18006639e  nop     dword ptr [rax+rax+00h]
0x1800663a3  mov     rcx, [rbp+var_20]; Buffer
0x1800663a7  xor     r14d, r14d
0x1800663aa  test    rcx, rcx
0x1800663ad  jz      short loc_1800663BB
0x1800663af  call    cs:__imp_NetApiBufferFree
0x1800663b6  nop     dword ptr [rax+rax+00h]
0x1800663bb  test    rsi, rsi
0x1800663be  jz      short loc_1800663CF
0x1800663c0  mov     rcx, rsi; vals
0x1800663c3  call    cs:__imp_ldap_value_freeW
0x1800663ca  nop     dword ptr [rax+rax+00h]
0x1800663cf  test    rdi, rdi
0x1800663d2  jz      short loc_1800663E3
0x1800663d4  mov     rcx, rdi; vals
0x1800663d7  call    cs:__imp_ldap_value_freeW
0x1800663de  nop     dword ptr [rax+rax+00h]
0x1800663e3  test    ebx, ebx
0x1800663e5  js      short loc_180066421
0x1800663e7  mov     rax, [rbp+Buffer]
0x1800663eb  mov     rcx, r14
0x1800663ee  mov     [r12], rax
0x1800663f2  mov     [r13+0], r15d
0x1800663f6  mov     [rbp+Buffer], rcx
0x1800663fa  jmp     short loc_180066425
0x1800663fc  mov     r8, [rsi+r12*8]
0x180066400  lea     rdx, aNetrenumerates_4; "NetrEnumerateServiceAccounts: Failed to"...
0x180066407  mov     ecx, 40h ; '@'; unsigned int
0x18006640c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180066411  mov     rdi, [rbp+var_38]
0x180066415  jmp     loc_180066372
0x18006641a  mov     ebx, ecx
0x18006641c  jmp     loc_18006637A
0x180066421  mov     rcx, [rbp+Buffer]
0x180066425  test    rcx, rcx
0x180066428  jz      short loc_180066463
0x18006642a  mov     edi, r14d
0x18006642d  test    r15d, r15d
0x180066430  jz      short loc_180066457
0x180066432  mov     eax, edi
0x180066434  mov     rdx, [rcx+rax*8]
0x180066438  test    rdx, rdx
0x18006643b  jz      short loc_180066450
0x18006643d  mov     rcx, rdx; Buffer
0x180066440  call    cs:__imp_NetApiBufferFree
0x180066447  nop     dword ptr [rax+rax+00h]
0x18006644c  mov     rcx, [rbp+Buffer]; Buffer
0x180066450  inc     edi
0x180066452  cmp     edi, r15d
0x180066455  jb      short loc_180066432
0x180066457  call    cs:__imp_NetApiBufferFree
0x18006645e  nop     dword ptr [rax+rax+00h]
0x180066463  mov     eax, ebx
0x180066465  add     rsp, 78h
0x180066469  pop     r15
0x18006646b  pop     r14
0x18006646d  pop     r13
0x18006646f  pop     r12
0x180066471  pop     rdi
0x180066472  pop     rsi
0x180066473  pop     rbx
0x180066474  pop     rbp
0x180066475  retn
```
