# Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(ushort,ulong,_SID const *,_SID const *,_ACL const *,_ACL const *,Windows::Auto<_SECURITY_DESCRIPTOR> *)

- ea: `0x180116224`
- end: `0x18011652f`
- name: `?CreateSecurityDescriptorFromParts@Rtl@Implementation@WCP@Windows@@YAJGKPEBU_SID@@0PEBU_ACL@@1PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@4@@Z`
- size: `779`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801159a4`
- `0x1802280e0`
- `0x18027f254`

## callees

- `0x1800aa1a4`
- `0x1800c16bc`
- `0x1800eb920`
- `0x180115e5c`
- `0x180116224`

## import_xrefs

- `ntdll!RtlCreateSecurityDescriptor` at `0x180116282`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180116282`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18011632b`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x18011632b`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18011638e`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18011645d`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18011638e`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18011645d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1801163d4`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1801163d4`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1801162df`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1801162df`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180116486`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x180116486`

## string_xrefs

- `0x180116292`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801162f2`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18011633b`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801163a6`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1801163e4`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180116496`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180116310`: `::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)`
- `0x1801162b0`: `RtlCreateSecurityDescriptor( &AbsoluteSD, (1))`
- `0x1801162a5`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x180116305`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x18011634e`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x1801163b1`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x1801163f7`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x1801164a9`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x1801164b4`: `::RtlSetSaclSecurityDescriptor( &AbsoluteSD, 1, fUseAcl ? const_cast<ACL*>(Sacl) : nullptr, 0)`
- `0x180116402`: `::RtlSetDaclSecurityDescriptor( &AbsoluteSD, 1, const_cast<ACL *>(Dacl), 0)`
- `0x1801163bc`: `::RtlSetControlSecurityDescriptor(&AbsoluteSD, SetAclBits, SetAclBits)`
- `0x180116359`: `::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(
        __int16 a1,
        int a2,
        void *a3,
        void *a4,
        struct _ACL *Dacl,
        PACL Sacl,
        const char **a7)
{
  NTSTATUS v11; // eax
  const char *v12; // rcx
  SECURITY_DESCRIPTOR_CONTROL v14; // r8
  int v15; // ebx
  char v16; // al
  SECURITY_DESCRIPTOR_CONTROL v17; // r8
  int v18; // ebx
  const char *v19; // rcx
  const char *v20; // rax
  const char *v21; // rcx
  const char *v22; // [rsp+20h] [rbp-60h] BYREF
  const char *v23; // [rsp+28h] [rbp-58h]
  __int64 v24; // [rsp+30h] [rbp-50h]
  const char *v25; // [rsp+38h] [rbp-48h]
  int v26; // [rsp+40h] [rbp-40h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v28; // [rsp+68h] [rbp-18h]

  v26 = 0;
  v28 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v11 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v11 < 0 )
  {
    v24 = 346;
    v22 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
    v12 = "RtlCreateSecurityDescriptor( &AbsoluteSD, (1))";
LABEL_3:
    v25 = v12;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v26,
             &v22,
             (unsigned int)v11);
  }
  if ( (a2 & 1) != 0 )
  {
    v11 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, a3, 0);
    if ( v11 < 0 )
    {
      v24 = 355;
      v22 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
      v12 = "::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)";
      goto LABEL_3;
    }
  }
  if ( (a2 & 2) != 0 )
  {
    v11 = RtlSetGroupSecurityDescriptor(SecurityDescriptor, a4, 0);
    if ( v11 < 0 )
    {
      v24 = 363;
      v22 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
      v12 = "::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)";
      goto LABEL_3;
    }
  }
  if ( (a2 & 4) != 0 )
  {
    v14 = a1 & 0x1500 | (a2 >> 31) & 0x1000;
    v11 = RtlSetControlSecurityDescriptor(SecurityDescriptor, v14, v14);
    if ( v11 < 0 )
    {
      v24 = 371;
LABEL_13:
      v22 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
      v12 = "::RtlSetControlSecurityDescriptor(&AbsoluteSD, SetAclBits, SetAclBits)";
      goto LABEL_3;
    }
    v11 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0);
    if ( v11 < 0 )
    {
      v24 = 377;
      v22 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
      v12 = "::RtlSetDaclSecurityDescriptor( &AbsoluteSD, 1, const_cast<ACL *>(Dacl), 0)";
      goto LABEL_3;
    }
  }
  if ( (a2 & 8) != 0 )
  {
    v15 = a2 & 0x40000000;
    if ( !Sacl || (v16 = 1, !Sacl->AceCount) )
      v16 = 0;
    if ( v15 || v16 || (a1 & 0x10) != 0 )
    {
      v17 = a1 & 0x2A00 | (v15 != 0 ? 0x2000 : 0);
      v11 = RtlSetControlSecurityDescriptor(SecurityDescriptor, v17, v17);
      if ( v11 < 0 )
      {
        v24 = 400;
        goto LABEL_13;
      }
      v11 = RtlSetSaclSecurityDescriptor(SecurityDescriptor, 1u, Sacl, 0);
      if ( v11 < 0 )
      {
        v24 = 406;
        v22 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
        v23 = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
        v12 = "::RtlSetSaclSecurityDescriptor( &AbsoluteSD, 1, fUseAcl ? const_cast<ACL*>(Sacl) : nullptr, 0)";
        goto LABEL_3;
      }
    }
  }
  v22 = 0;
  v23 = 0;
  v18 = Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(&v22, SecurityDescriptor);
  if ( v18 >= 0 )
  {
    v19 = v22;
    v18 = 0;
    v22 = *a7;
    v20 = a7[1];
    *a7 = v19;
    v21 = v23;
    v23 = v20;
    a7[1] = v21;
  }
  Windows::Auto<_SECURITY_DESCRIPTOR>::Close(&v22);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180116224  mov     [rsp-38h+arg_8], rbx
0x180116229  push    rbp
0x18011622a  push    rsi
0x18011622b  push    rdi
0x18011622c  push    r12
0x18011622e  push    r13
0x180116230  push    r14
0x180116232  push    r15
0x180116234  mov     rbp, rsp
0x180116237  sub     rsp, 80h
0x18011623e  mov     rax, cs:__security_cookie
0x180116245  xor     rax, rsp
0x180116248  mov     [rbp+var_10], rax
0x18011624c  mov     r14, [rbp+Sacl]
0x180116250  xor     eax, eax
0x180116252  mov     r13, [rbp+Dacl]
0x180116256  xorps   xmm0, xmm0
0x180116259  mov     rdi, [rbp+arg_30]
0x18011625d  mov     ebx, edx
0x18011625f  movzx   esi, cx
0x180116262  mov     [rbp+var_40], 0
0x180116269  lea     edx, [rax+1]; Revision
0x18011626c  mov     [rbp+var_18], rax
0x180116270  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180116274  mov     r12, r9
0x180116277  mov     r15, r8
0x18011627a  movups  [rbp+SecurityDescriptor], xmm0
0x18011627e  movups  [rbp+var_28], xmm0
0x180116282  call    cs:__imp_RtlCreateSecurityDescriptor
0x180116289  nop     dword ptr [rax+rax+00h]
0x18011628e  test    eax, eax
0x180116290  jns     short loc_1801162D0
0x180116292  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180116299  mov     [rbp+var_50], 15Ah
0x1801162a1  mov     [rbp+var_60], rcx
0x1801162a5  lea     rcx, aWindowsWcpImpl_18; "Windows::WCP::Implementation::Rtl::Crea"...
0x1801162ac  mov     [rbp+var_58], rcx
0x1801162b0  lea     rcx, aRtlcreatesecur; "RtlCreateSecurityDescriptor( &AbsoluteS"...
0x1801162b7  mov     [rbp+var_48], rcx
0x1801162bb  lea     rdx, [rbp+var_60]
0x1801162bf  lea     rcx, [rbp+var_40]
0x1801162c3  mov     r8d, eax
0x1801162c6  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1801162cb  jmp     loc_180116507
0x1801162d0  test    bl, 1
0x1801162d3  jz      short loc_180116319
0x1801162d5  xor     r8d, r8d; OwnerDefaulted
0x1801162d8  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1801162dc  mov     rdx, r15; Owner
0x1801162df  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1801162e6  nop     dword ptr [rax+rax+00h]
0x1801162eb  xor     r15d, r15d
0x1801162ee  test    eax, eax
0x1801162f0  jns     short loc_18011631C
0x1801162f2  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801162f9  mov     [rbp+var_50], 163h
0x180116301  mov     [rbp+var_60], rcx
0x180116305  lea     rcx, aWindowsWcpImpl_18; "Windows::WCP::Implementation::Rtl::Crea"...
0x18011630c  mov     [rbp+var_58], rcx
0x180116310  lea     rcx, aRtlsetownersec_0; "::RtlSetOwnerSecurityDescriptor( &Absol"...
0x180116317  jmp     short loc_1801162B7
0x180116319  xor     r15d, r15d
0x18011631c  test    bl, 2
0x18011631f  jz      short loc_180116365
0x180116321  xor     r8d, r8d; GroupDefaulted
0x180116324  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180116328  mov     rdx, r12; Group
0x18011632b  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x180116332  nop     dword ptr [rax+rax+00h]
0x180116337  test    eax, eax
0x180116339  jns     short loc_180116365
0x18011633b  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180116342  mov     [rbp+var_50], 16Bh
0x18011634a  mov     [rbp+var_60], rcx
0x18011634e  lea     rcx, aWindowsWcpImpl_18; "Windows::WCP::Implementation::Rtl::Crea"...
0x180116355  mov     [rbp+var_58], rcx
0x180116359  lea     rcx, aRtlsetgroupsec; "::RtlSetGroupSecurityDescriptor( &Absol"...
0x180116360  jmp     loc_1801162B7
0x180116365  test    bl, 4
0x180116368  jz      loc_18011640E
0x18011636e  mov     eax, 0FAFFh
0x180116373  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180116377  mov     edx, ebx
0x180116379  sar     edx, 1Fh
0x18011637c  and     dx, ax
0x18011637f  mov     eax, 1500h
0x180116384  or      dx, si
0x180116387  and     dx, ax; ControlBitsOfInterest
0x18011638a  movzx   r8d, dx; ControlBitsToSet
0x18011638e  call    cs:__imp_RtlSetControlSecurityDescriptor
0x180116395  nop     dword ptr [rax+rax+00h]
0x18011639a  test    eax, eax
0x18011639c  jns     short loc_1801163C8
0x18011639e  mov     [rbp+var_50], 173h
0x1801163a6  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801163ad  mov     [rbp+var_60], rcx
0x1801163b1  lea     rcx, aWindowsWcpImpl_18; "Windows::WCP::Implementation::Rtl::Crea"...
0x1801163b8  mov     [rbp+var_58], rcx
0x1801163bc  lea     rcx, aRtlsetcontrols; "::RtlSetControlSecurityDescriptor(&Abso"...
0x1801163c3  jmp     loc_1801162B7
0x1801163c8  xor     r9d, r9d; DaclDefaulted
0x1801163cb  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1801163cf  mov     r8, r13; Dacl
0x1801163d2  mov     dl, 1; DaclPresent
0x1801163d4  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1801163db  nop     dword ptr [rax+rax+00h]
0x1801163e0  test    eax, eax
0x1801163e2  jns     short loc_18011640E
0x1801163e4  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801163eb  mov     [rbp+var_50], 179h
0x1801163f3  mov     [rbp+var_60], rcx
0x1801163f7  lea     rcx, aWindowsWcpImpl_18; "Windows::WCP::Implementation::Rtl::Crea"...
0x1801163fe  mov     [rbp+var_58], rcx
0x180116402  lea     rcx, aRtlsetdaclsecu_0; "::RtlSetDaclSecurityDescriptor( &Absolu"...
0x180116409  jmp     loc_1801162B7
0x18011640e  test    bl, 8
0x180116411  jz      loc_1801164C0
0x180116417  and     ebx, 40000000h
0x18011641d  test    r14, r14
0x180116420  jz      short loc_18011642B
0x180116422  mov     al, 1
0x180116424  cmp     [r14+4], r15w
0x180116429  ja      short loc_18011642E
0x18011642b  mov     al, r15b
0x18011642e  test    ebx, ebx
0x180116430  jnz     short loc_180116440
0x180116432  test    al, al
0x180116434  jnz     short loc_180116440
0x180116436  test    sil, 10h
0x18011643a  jz      loc_1801164C0
0x180116440  mov     eax, 2A00h
0x180116445  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180116449  neg     ebx
0x18011644b  sbb     dx, dx
0x18011644e  and     si, ax
0x180116451  and     dx, 2000h
0x180116456  or      dx, si; ControlBitsOfInterest
0x180116459  movzx   r8d, dx; ControlBitsToSet
0x18011645d  call    cs:__imp_RtlSetControlSecurityDescriptor
0x180116464  nop     dword ptr [rax+rax+00h]
0x180116469  test    eax, eax
0x18011646b  jns     short loc_18011647A
0x18011646d  mov     [rbp+var_50], 190h
0x180116475  jmp     loc_1801163A6
0x18011647a  xor     r9d, r9d; SaclDefaulted
0x18011647d  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180116481  mov     r8, r14; Sacl
0x180116484  mov     dl, 1; SaclPresent
0x180116486  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x18011648d  nop     dword ptr [rax+rax+00h]
0x180116492  test    eax, eax
0x180116494  jns     short loc_1801164C0
0x180116496  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18011649d  mov     [rbp+var_50], 196h
0x1801164a5  mov     [rbp+var_60], rcx
0x1801164a9  lea     rcx, aWindowsWcpImpl_18; "Windows::WCP::Implementation::Rtl::Crea"...
0x1801164b0  mov     [rbp+var_58], rcx
0x1801164b4  lea     rcx, aRtlsetsaclsecu; "::RtlSetSaclSecurityDescriptor( &Absolu"...
0x1801164bb  jmp     loc_1801162B7
0x1801164c0  lea     rdx, [rbp+SecurityDescriptor]
0x1801164c4  mov     [rbp+var_60], r15
0x1801164c8  lea     rcx, [rbp+var_60]
0x1801164cc  mov     [rbp+var_58], r15
0x1801164d0  call    ?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z; Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)
0x1801164d5  mov     ebx, eax
0x1801164d7  test    eax, eax
0x1801164d9  js      short loc_1801164FC
0x1801164db  mov     rcx, [rbp+var_60]
0x1801164df  mov     ebx, r15d
0x1801164e2  mov     rax, [rdi]
0x1801164e5  mov     [rbp+var_60], rax
0x1801164e9  mov     rax, [rdi+8]
0x1801164ed  mov     [rdi], rcx
0x1801164f0  mov     rcx, [rbp+var_58]
0x1801164f4  mov     [rbp+var_58], rax
0x1801164f8  mov     [rdi+8], rcx
0x1801164fc  lea     rcx, [rbp+var_60]
0x180116500  call    ?Close@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAXXZ; Windows::Auto<_SECURITY_DESCRIPTOR>::Close(void)
0x180116505  mov     eax, ebx
0x180116507  mov     rcx, [rbp+var_10]
0x18011650b  xor     rcx, rsp; StackCookie
0x18011650e  call    __security_check_cookie
0x180116513  mov     rbx, [rsp+80h+arg_8]
0x18011651b  add     rsp, 80h
0x180116522  pop     r15
0x180116524  pop     r14
0x180116526  pop     r13
0x180116528  pop     r12
0x18011652a  pop     rdi
0x18011652b  pop     rsi
0x18011652c  pop     rbp
0x18011652d  retn
```
