# _lambda_f582acd5b9504eb834dd17ecbdb6718d_::operator()

- ea: `0x18014dc2c`
- end: `0x18014e283`
- name: `_lambda_f582acd5b9504eb834dd17ecbdb6718d_::operator()`
- size: `1623`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18014e28c`

## callees

- `0x18000dff0`
- `0x18005997c`
- `0x180059c54`
- `0x18005d410`
- `0x180088660`
- `0x1800a2d84`
- `0x1800a3154`
- `0x180114950`
- `0x18014dc2c`
- `0x180194f10`

## import_xrefs

- `ntdll!NtQuerySecurityObject` at `0x18014dd07`
- `ntdll!NtQuerySecurityObject` at `0x18014ddbb`
- `ntdll!NtQuerySecurityObject` at `0x18014dd07`
- `ntdll!NtQuerySecurityObject` at `0x18014ddbb`
- `ntdll!RtlGetAce` at `0x18014dfc7`
- `ntdll!RtlGetAce` at `0x18014dfc7`
- `ntdll!RtlQueryInformationAcl` at `0x18014de6e`
- `ntdll!RtlQueryInformationAcl` at `0x18014de6e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18014dd15`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18014dd15`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18014de0d`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18014de0d`
- `ntdll!RtlCreateAcl` at `0x18014ded3`
- `ntdll!RtlCreateAcl` at `0x18014ded3`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18014df78`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x18014df78`
- `ntdll!RtlAddAce` at `0x18014dff4`
- `ntdll!RtlAddAce` at `0x18014dff4`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18014e042`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18014e042`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18014e0cc`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18014e0cc`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18014e106`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18014e106`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18014e13f`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x18014e13f`
- `ntdll!NtSetSecurityObject` at `0x18014e174`
- `ntdll!NtSetSecurityObject` at `0x18014e174`
- `ntdll!RtlAllocateHeap` at `0x18014dd86`
- `ntdll!RtlAllocateHeap` at `0x18014deac`
- `ntdll!RtlAllocateHeap` at `0x18014e01e`
- `ntdll!RtlAllocateHeap` at `0x18014dd86`
- `ntdll!RtlAllocateHeap` at `0x18014deac`
- `ntdll!RtlAllocateHeap` at `0x18014e01e`

## string_xrefs

- `0x18014dee7`: `RtlCreateAcl %u`
- `0x18014df31`: `AppContainerDeriveSidFromMoniker`
- `0x18014de1d`: `RtlGetDaclSecurityDescriptor`
- `0x18014de39`: `RtlGetDaclSecurityDescriptor`
- `0x18014de7e`: `RtlQueryInformationAcl`
- `0x18014e052`: `RtlCreateSecurityDescriptor`
- `0x18014df8c`: `RtlAddAccessAllowedAceEx`
- `0x18014ddcb`: `NtQuerySecurityObject`
- `0x18014dca8`: `RegCreateKeyEx`
- `0x18014e14f`: `RtlSetControlSecurityDescriptor`
- `0x18014e184`: `NtSetSecurityObject`
- `0x18014e0dc`: `RtlSetDaclSecurityDescriptor`
- `0x18014e116`: `RtlGetControlSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall lambda_f582acd5b9504eb834dd17ecbdb6718d_::operator()(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rdi
  unsigned int Key; // eax
  void **v6; // rcx
  void *v7; // rcx
  NTSTATUS v8; // eax
  signed int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  PSECURITY_DESCRIPTOR v12; // rsi
  NTSTATUS v13; // eax
  unsigned int v14; // eax
  NTSTATUS DaclSecurityDescriptor; // eax
  NTSTATUS InformationAcl; // eax
  ULONG v17; // ebx
  ACL *v18; // rax
  ACL *v19; // rdi
  NTSTATUS Acl; // eax
  __int64 v21; // rcx
  NTSTATUS v22; // eax
  unsigned int v23; // eax
  ULONG v24; // ebx
  NTSTATUS v25; // eax
  NTSTATUS v26; // eax
  PVOID v27; // rax
  void *v28; // rbx
  NTSTATUS SecurityDescriptor; // eax
  unsigned int v30; // eax
  NTSTATUS v31; // eax
  NTSTATUS ControlSecurityDescriptor; // eax
  NTSTATUS v33; // eax
  NTSTATUS v34; // eax
  char *v35; // [rsp+28h] [rbp-61h]
  unsigned __int8 DaclDefaulted; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int8 DaclPresent[7]; // [rsp+51h] [rbp-38h] BYREF
  PSID pSid; // [rsp+58h] [rbp-31h] BYREF
  ACL *v39; // [rsp+60h] [rbp-29h] BYREF
  WORD Control[2]; // [rsp+68h] [rbp-21h] BYREF
  ULONG Length; // [rsp+6Ch] [rbp-1Dh] BYREF
  PVOID v42; // [rsp+70h] [rbp-19h] BYREF
  ULONG Revision; // [rsp+78h] [rbp-11h] BYREF
  PACL Dacl; // [rsp+80h] [rbp-9h] BYREF
  PVOID Ace; // [rsp+88h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR Heap; // [rsp+90h] [rbp+7h] BYREF
  _QWORD Information[2]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v1 = *(_QWORD *)(a1 + 16);
  v3 = *(_QWORD *)(a1 + 24);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    v1,
    0);
  Key = RegCreateKeyExInternalW(**(_QWORD **)a1, **(_QWORD **)(a1 + 8), 0, 0, 0, 983103, 0, v1, v3, 0);
  if ( Key )
    return wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x520,
             (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
             (const char *)Key,
             (unsigned int)"RegCreateKeyEx",
             v35);
  if ( **(_DWORD **)(a1 + 24) == 1 )
  {
    v6 = *(void ***)(a1 + 16);
    memset(Information, 0, 12);
    Dacl = 0;
    v7 = *v6;
    Length = 0;
    v8 = NtQuerySecurityObject(v7, 4u, 0, 0, &Length);
    v9 = RtlNtStatusToDosErrorNoTeb(v8);
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    if ( (v10 & 0x80000000) == 0 )
    {
      v10 = -2147023537;
      v11 = 1341;
LABEL_8:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
        (const char *)v10,
        (int)"statusNtQuerySecutiryObject",
        v35);
      return v10;
    }
    if ( v10 != -2147024774 )
    {
      v11 = 1343;
      goto LABEL_8;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Length);
    v12 = Heap;
    if ( !Heap )
    {
      v10 = -2147024882;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x546,
        (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
        (const char *)0x8007000ELL,
        (int)"RtlAllocateHeap",
        v35);
      goto LABEL_57;
    }
    v13 = NtQuerySecurityObject(**(HANDLE **)(a1 + 16), 4u, Heap, Length, &Length);
    if ( v13 < 0 )
    {
      v14 = wil::details::in1diag3::Return_NtStatusMsg(
              retaddr,
              (void *)0x54B,
              (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
              (const char *)(unsigned int)v13,
              (int)"NtQuerySecurityObject",
              v35);
LABEL_15:
      v10 = v14;
LABEL_57:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Heap);
      return v10;
    }
    DaclPresent[0] = 0;
    DaclDefaulted = 0;
    DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(v12, DaclPresent, &Dacl, &DaclDefaulted);
    if ( DaclSecurityDescriptor < 0 )
    {
      v14 = wil::details::in1diag3::Return_NtStatusMsg(
              retaddr,
              (void *)0x551,
              (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
              (const char *)(unsigned int)DaclSecurityDescriptor,
              (int)"RtlGetDaclSecurityDescriptor",
              v35);
      goto LABEL_15;
    }
    if ( !Dacl )
    {
      v10 = -2147023537;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x554,
        (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
        (const char *)0x8007054FLL,
        (int)"RtlGetDaclSecurityDescriptor",
        v35);
      goto LABEL_57;
    }
    LODWORD(Information[0]) = 0;
    *(_QWORD *)((char *)Information + 4) = 8;
    InformationAcl = RtlQueryInformationAcl(Dacl, Information, 0xCu, AclSizeInformation);
    if ( InformationAcl < 0 )
    {
      v14 = wil::details::in1diag3::Return_NtStatusMsg(
              retaddr,
              (void *)0x55D,
              (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
              (const char *)(unsigned int)InformationAcl,
              (int)"RtlQueryInformationAcl",
              v35);
      goto LABEL_15;
    }
    v17 = HIDWORD(Information[0]) + 80;
    v18 = (ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(HIDWORD(Information[0]) + 80));
    v39 = v18;
    v19 = v18;
    if ( !v18 )
    {
      LODWORD(v35) = v17;
      v10 = -2147024882;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x566,
        (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
        (const char *)0x8007000ELL,
        (int)"RtlAllocateHeap %u",
        v35);
      goto LABEL_55;
    }
    Acl = RtlCreateAcl(v18, v17, 2u);
    if ( Acl < 0 )
    {
      LODWORD(v35) = v17;
      v10 = wil::details::in1diag3::Return_NtStatusMsg(
              retaddr,
              (void *)0x56A,
              (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
              (const char *)(unsigned int)Acl,
              (int)"RtlCreateAcl %u",
              v35);
LABEL_55:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
      goto LABEL_57;
    }
    v21 = *(_QWORD *)(a1 + 32);
    pSid = 0;
    v10 = AppContainerDeriveSidFromMoniker(*(char **)(v21 + 24));
    if ( (v10 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x56F,
        (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
        (const char *)v10,
        (int)"AppContainerDeriveSidFromMoniker",
        v35);
LABEL_27:
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
      goto LABEL_55;
    }
    v22 = RtlAddAccessAllowedAceEx(v19, 2u, 0, 1u, pSid);
    if ( v22 < 0 )
    {
      v23 = wil::details::in1diag3::Return_NtStatusMsg(
              retaddr,
              (void *)0x574,
              (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
              (const char *)(unsigned int)v22,
              (int)"RtlAddAccessAllowedAceEx",
              v35);
LABEL_30:
      v10 = v23;
      goto LABEL_27;
    }
    v24 = 0;
    if ( LODWORD(Information[0]) )
    {
      while ( 1 )
      {
        Ace = 0;
        v25 = RtlGetAce(Dacl, v24, &Ace);
        if ( v25 < 0 )
          break;
        v26 = RtlAddAce(v19, 2u, 0xFFFFFFFF, Ace, *((unsigned __int16 *)Ace + 1));
        if ( v26 < 0 )
        {
          LODWORD(v35) = v24;
          v23 = wil::details::in1diag3::Return_NtStatusMsg(
                  retaddr,
                  (void *)0x586,
                  (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
                  (const char *)(unsigned int)v26,
                  (int)"RtlAddAce %lu",
                  v35);
          goto LABEL_30;
        }
        if ( ++v24 >= LODWORD(Information[0]) )
          goto LABEL_35;
      }
      LODWORD(v35) = v24;
      v23 = wil::details::in1diag3::Return_NtStatusMsg(
              retaddr,
              (void *)0x582,
              (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
              (const char *)(unsigned int)v25,
              (int)"RtlGetAce %lu",
              v35);
      goto LABEL_30;
    }
LABEL_35:
    v27 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x28u);
    v42 = v27;
    v28 = v27;
    if ( !v27 )
    {
      v10 = -2147024882;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x58C,
        (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
        (const char *)0x8007000ELL,
        (int)"RtlAllocateHeap",
        v35);
      goto LABEL_53;
    }
    SecurityDescriptor = RtlCreateSecurityDescriptor(v27, 1u);
    if ( SecurityDescriptor < 0 )
    {
      v30 = wil::details::in1diag3::Return_NtStatusMsg(
              retaddr,
              (void *)0x590,
              (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
              (const char *)(unsigned int)SecurityDescriptor,
              (int)"RtlCreateSecurityDescriptor",
              v35);
LABEL_38:
      v10 = v30;
LABEL_53:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
      goto LABEL_27;
    }
    v31 = RtlSetDaclSecurityDescriptor(v28, 1u, v19, 0);
    if ( v31 < 0 )
    {
      v30 = wil::details::in1diag3::Return_NtStatusMsg(
              retaddr,
              (void *)0x594,
              (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
              (const char *)(unsigned int)v31,
              (int)"RtlSetDaclSecurityDescriptor",
              v35);
      goto LABEL_38;
    }
    Control[0] = 0;
    Revision = 0;
    ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(v12, Control, &Revision);
    if ( ControlSecurityDescriptor < 0 )
    {
      v30 = wil::details::in1diag3::Return_NtStatusMsg(
              retaddr,
              (void *)0x59C,
              (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
              (const char *)(unsigned int)ControlSecurityDescriptor,
              (int)"RtlGetControlSecurityDescriptor",
              v35);
      goto LABEL_38;
    }
    v33 = RtlSetControlSecurityDescriptor(v28, Control[0] & 0x500, Control[0] & 0x500);
    if ( v33 < 0 )
    {
      v30 = wil::details::in1diag3::Return_NtStatusMsg(
              retaddr,
              (void *)0x5A3,
              (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
              (const char *)(unsigned int)v33,
              (int)"RtlSetControlSecurityDescriptor",
              v35);
      goto LABEL_38;
    }
    v34 = NtSetSecurityObject(**(HANDLE **)(a1 + 16), 4u, v28);
    if ( v34 < 0 )
    {
      v30 = wil::details::in1diag3::Return_NtStatusMsg(
              retaddr,
              (void *)0x5A7,
              (unsigned int)"onecore\\base\\appmodel\\statemanager\\apiset\\lib\\statespace.cpp",
              (const char *)(unsigned int)v34,
              (int)"NtSetSecurityObject",
              v35);
      goto LABEL_38;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Heap);
  }
  return 0;
}

```

## disassembly

```asm
0x18014dc2c  push    rbp
0x18014dc2e  push    rbx
0x18014dc2f  push    rsi
0x18014dc30  push    rdi
0x18014dc31  push    r14
0x18014dc33  push    r15
0x18014dc35  lea     rbp, [rsp-2Fh]
0x18014dc3a  sub     rsp, 0B8h
0x18014dc41  mov     rax, cs:__security_cookie
0x18014dc48  xor     rax, rsp
0x18014dc4b  mov     [rbp+57h+var_38], rax
0x18014dc4f  mov     rbx, [rcx+10h]
0x18014dc53  mov     r14, rcx
0x18014dc56  mov     rdi, [rcx+18h]
0x18014dc5a  xor     edx, edx
0x18014dc5c  mov     rcx, rbx
0x18014dc5f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18014dc64  mov     rdx, [r14+8]
0x18014dc68  xor     r15d, r15d
0x18014dc6b  mov     rcx, [r14]
0x18014dc6e  xor     r9d, r9d
0x18014dc71  mov     [rsp+0E0h+var_98], r15
0x18014dc76  xor     r8d, r8d
0x18014dc79  mov     [rsp+0E0h+var_A0], rdi
0x18014dc7e  mov     rdx, [rdx]
0x18014dc81  mov     rcx, [rcx]
0x18014dc84  mov     [rsp+0E0h+var_A8], rbx
0x18014dc89  mov     [rsp+0E0h+var_B0], r15
0x18014dc8e  mov     dword ptr [rsp+0E0h+var_B8], 0F003Fh; char *
0x18014dc96  mov     dword ptr [rsp+0E0h+LengthNeeded], r15d
0x18014dc9b  call    RegCreateKeyExInternalW
0x18014dca0  test    eax, eax
0x18014dca2  jz      short loc_18014DCCD
0x18014dca4  mov     rcx, [rbp+5Fh]; this
0x18014dca8  lea     rdx, aRegcreatekeyex_3; "RegCreateKeyEx"
0x18014dcaf  mov     [rsp+0E0h+LengthNeeded], rdx; unsigned int
0x18014dcb4  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x18014dcbb  mov     edx, 520h; void *
0x18014dcc0  mov     r9d, eax; char *
0x18014dcc3  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18014dcc8  jmp     loc_18014E1C0
0x18014dccd  mov     rax, [r14+18h]
0x18014dcd1  cmp     dword ptr [rax], 1
0x18014dcd4  jnz     loc_18014E1BE
0x18014dcda  mov     rcx, [r14+10h]
0x18014dcde  xor     eax, eax
0x18014dce0  xor     r9d, r9d; Length
0x18014dce3  mov     [rbp+57h+Information], rax
0x18014dce7  mov     [rbp+57h+var_40], eax
0x18014dcea  xor     r8d, r8d; SecurityDescriptor
0x18014dced  lea     rax, [rbp+57h+Length]
0x18014dcf1  mov     [rbp+57h+Dacl], r15
0x18014dcf5  mov     rcx, [rcx]; Handle
0x18014dcf8  lea     edi, [r9+4]
0x18014dcfc  mov     [rbp+57h+Length], r15d
0x18014dd00  mov     edx, edi; SecurityInformation
0x18014dd02  mov     [rsp+0E0h+LengthNeeded], rax; LengthNeeded
0x18014dd07  call    cs:__imp_NtQuerySecurityObject
0x18014dd0e  nop     dword ptr [rax+rax+00h]
0x18014dd13  mov     ecx, eax; Status
0x18014dd15  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18014dd1c  nop     dword ptr [rax+rax+00h]
0x18014dd21  mov     ebx, eax
0x18014dd23  test    eax, eax
0x18014dd25  jle     short loc_18014DD30
0x18014dd27  movzx   ebx, ax
0x18014dd2a  or      ebx, 80070000h
0x18014dd30  test    ebx, ebx
0x18014dd32  js      short loc_18014DD64
0x18014dd34  mov     ebx, 8007054Fh
0x18014dd39  mov     edx, 53Dh; void *
0x18014dd3e  mov     rcx, [rbp+5Fh]; this
0x18014dd42  lea     rax, aStatusntquerys; "statusNtQuerySecutiryObject"
0x18014dd49  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x18014dd50  mov     [rsp+0E0h+LengthNeeded], rax; int
0x18014dd55  mov     r9d, ebx; char *
0x18014dd58  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18014dd5d  mov     eax, ebx
0x18014dd5f  jmp     loc_18014E1C0
0x18014dd64  cmp     ebx, 8007007Ah
0x18014dd6a  jz      short loc_18014DD73
0x18014dd6c  mov     edx, 53Fh
0x18014dd71  jmp     short loc_18014DD3E
0x18014dd73  mov     rcx, gs:60h
0x18014dd7c  xor     edx, edx; Flags
0x18014dd7e  mov     r8d, [rbp+57h+Length]; Size
0x18014dd82  mov     rcx, [rcx+30h]; HeapHandle
0x18014dd86  call    cs:__imp_RtlAllocateHeap
0x18014dd8d  nop     dword ptr [rax+rax+00h]
0x18014dd92  mov     [rbp+57h+var_50], rax
0x18014dd96  mov     rsi, rax
0x18014dd99  test    rax, rax
0x18014dd9c  jz      loc_18014E24C
0x18014dda2  mov     rcx, [r14+10h]
0x18014dda6  lea     rax, [rbp+57h+Length]
0x18014ddaa  mov     r9d, [rbp+57h+Length]; Length
0x18014ddae  mov     r8, rsi; SecurityDescriptor
0x18014ddb1  mov     edx, edi; SecurityInformation
0x18014ddb3  mov     [rsp+0E0h+LengthNeeded], rax; LengthNeeded
0x18014ddb8  mov     rcx, [rcx]; Handle
0x18014ddbb  call    cs:__imp_NtQuerySecurityObject
0x18014ddc2  nop     dword ptr [rax+rax+00h]
0x18014ddc7  test    eax, eax
0x18014ddc9  jns     short loc_18014DDF6
0x18014ddcb  lea     rdx, aNtquerysecurit_0; "NtQuerySecurityObject"
0x18014ddd2  mov     [rsp+0E0h+LengthNeeded], rdx; int
0x18014ddd7  mov     edx, 54Bh; void *
0x18014dddc  mov     rcx, [rbp+5Fh]; this
0x18014dde0  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x18014dde7  mov     r9d, eax; char *
0x18014ddea  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18014ddef  mov     ebx, eax
0x18014ddf1  jmp     loc_18014E275
0x18014ddf6  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x18014ddfa  mov     [rbp+57h+DaclPresent], r15b
0x18014ddfe  lea     r8, [rbp+57h+Dacl]; Dacl
0x18014de02  mov     [rbp+57h+DaclDefaulted], r15b
0x18014de06  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x18014de0a  mov     rcx, rsi; SecurityDescriptor
0x18014de0d  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18014de14  nop     dword ptr [rax+rax+00h]
0x18014de19  test    eax, eax
0x18014de1b  jns     short loc_18014DE30
0x18014de1d  lea     rdx, aRtlgetdaclsecu; "RtlGetDaclSecurityDescriptor"
0x18014de24  mov     [rsp+0E0h+LengthNeeded], rdx
0x18014de29  mov     edx, 551h
0x18014de2e  jmp     short loc_18014DDDC
0x18014de30  mov     rcx, [rbp+57h+Dacl]; Acl
0x18014de34  test    rcx, rcx
0x18014de37  jnz     short loc_18014DE54
0x18014de39  lea     rdx, aRtlgetdaclsecu; "RtlGetDaclSecurityDescriptor"
0x18014de40  mov     ebx, 8007054Fh
0x18014de45  mov     [rsp+0E0h+LengthNeeded], rdx
0x18014de4a  mov     edx, 554h
0x18014de4f  jmp     loc_18014E262
0x18014de54  mov     r9d, 2; InformationClass
0x18014de5a  mov     dword ptr [rbp+57h+Information], r15d
0x18014de5e  lea     rdx, [rbp+57h+Information]; Information
0x18014de62  mov     [rbp+57h+Information+4], 8
0x18014de6a  lea     r8d, [r9+0Ah]; InformationLength
0x18014de6e  call    cs:__imp_RtlQueryInformationAcl
0x18014de75  nop     dword ptr [rax+rax+00h]
0x18014de7a  test    eax, eax
0x18014de7c  jns     short loc_18014DE94
0x18014de7e  lea     rdx, aRtlqueryinform; "RtlQueryInformationAcl"
0x18014de85  mov     [rsp+0E0h+LengthNeeded], rdx
0x18014de8a  mov     edx, 55Dh
0x18014de8f  jmp     loc_18014DDDC
0x18014de94  mov     rcx, gs:60h
0x18014de9d  xor     edx, edx; Flags
0x18014de9f  mov     ebx, dword ptr [rbp+57h+Information+4]
0x18014dea2  add     ebx, 50h ; 'P'
0x18014dea5  mov     r8d, ebx; Size
0x18014dea8  mov     rcx, [rcx+30h]; HeapHandle
0x18014deac  call    cs:__imp_RtlAllocateHeap
0x18014deb3  nop     dword ptr [rax+rax+00h]
0x18014deb8  mov     [rbp+57h+var_80], rax
0x18014debc  mov     rdi, rax
0x18014debf  test    rax, rax
0x18014dec2  jz      loc_18014E214
0x18014dec8  mov     r8d, 2; AclRevision
0x18014dece  mov     edx, ebx; AclSize
0x18014ded0  mov     rcx, rax; Acl
0x18014ded3  call    cs:__imp_RtlCreateAcl
0x18014deda  nop     dword ptr [rax+rax+00h]
0x18014dedf  test    eax, eax
0x18014dee1  jns     short loc_18014DF12
0x18014dee3  mov     rcx, [rbp+5Fh]; this
0x18014dee7  lea     rdx, aRtlcreateaclU; "RtlCreateAcl %u"
0x18014deee  mov     dword ptr [rsp+0E0h+var_B8], ebx; char *
0x18014def2  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x18014def9  mov     [rsp+0E0h+LengthNeeded], rdx; int
0x18014defe  mov     r9d, eax; char *
0x18014df01  mov     edx, 56Ah; void *
0x18014df06  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18014df0b  mov     ebx, eax
0x18014df0d  jmp     loc_18014E241
0x18014df12  mov     rcx, [r14+20h]
0x18014df16  lea     rdx, [rbp+57h+pSid]
0x18014df1a  mov     [rbp+57h+pSid], r15
0x18014df1e  mov     rcx, [rcx+18h]
0x18014df22  call    AppContainerDeriveSidFromMoniker
0x18014df27  mov     ebx, eax
0x18014df29  test    eax, eax
0x18014df2b  jns     short loc_18014DF5F
0x18014df2d  mov     rcx, [rbp+5Fh]; this
0x18014df31  lea     rax, aAppcontainerde_0; "AppContainerDeriveSidFromMoniker"
0x18014df38  mov     r9d, ebx; char *
0x18014df3b  mov     [rsp+0E0h+LengthNeeded], rax; int
0x18014df40  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x18014df47  mov     edx, 56Fh; void *
0x18014df4c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18014df51  lea     rcx, [rbp+57h+pSid]
0x18014df55  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18014df5a  jmp     loc_18014E241
0x18014df5f  mov     rax, [rbp+57h+pSid]
0x18014df63  mov     r9d, 1; AccessMask
0x18014df69  xor     r8d, r8d; AceFlags
0x18014df6c  mov     [rsp+0E0h+LengthNeeded], rax; pSid
0x18014df71  mov     rcx, rdi; pAcl
0x18014df74  lea     edx, [r9+1]; dwAceRevision
0x18014df78  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18014df7f  nop     dword ptr [rax+rax+00h]
0x18014df84  test    eax, eax
0x18014df86  jns     short loc_18014DFB0
0x18014df88  mov     rcx, [rbp+5Fh]; this
0x18014df8c  lea     rdx, aRtladdaccessal; "RtlAddAccessAllowedAceEx"
0x18014df93  mov     [rsp+0E0h+LengthNeeded], rdx; int
0x18014df98  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x18014df9f  mov     edx, 574h; void *
0x18014dfa4  mov     r9d, eax; char *
0x18014dfa7  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18014dfac  mov     ebx, eax
0x18014dfae  jmp     short loc_18014DF51
0x18014dfb0  mov     ebx, r15d
0x18014dfb3  cmp     dword ptr [rbp+57h+Information], r15d
0x18014dfb7  jbe     short loc_18014E00B
0x18014dfb9  mov     rcx, [rbp+57h+Dacl]; Acl
0x18014dfbd  lea     r8, [rbp+57h+Ace]; Ace
0x18014dfc1  mov     edx, ebx; AceIndex
0x18014dfc3  mov     [rbp+57h+Ace], r15
0x18014dfc7  call    cs:__imp_RtlGetAce
0x18014dfce  nop     dword ptr [rax+rax+00h]
0x18014dfd3  test    eax, eax
0x18014dfd5  js      loc_18014E094
0x18014dfdb  mov     r9, [rbp+57h+Ace]; AceList
0x18014dfdf  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x18014dfe3  mov     edx, 2; AceRevision
0x18014dfe8  mov     rcx, rdi; Acl
0x18014dfeb  movzx   eax, word ptr [r9+2]
0x18014dff0  mov     dword ptr [rsp+0E0h+LengthNeeded], eax; AceListLength
0x18014dff4  call    cs:__imp_RtlAddAce
0x18014dffb  nop     dword ptr [rax+rax+00h]
0x18014e000  test    eax, eax
0x18014e002  js      short loc_18014E07D
0x18014e004  inc     ebx
0x18014e006  cmp     ebx, dword ptr [rbp+57h+Information]
0x18014e009  jb      short loc_18014DFB9
0x18014e00b  mov     rcx, gs:60h
0x18014e014  xor     edx, edx; Flags
0x18014e016  mov     rcx, [rcx+30h]; HeapHandle
0x18014e01a  lea     r8d, [rdx+28h]; Size
0x18014e01e  call    cs:__imp_RtlAllocateHeap
0x18014e025  nop     dword ptr [rax+rax+00h]
0x18014e02a  mov     [rbp+57h+var_70], rax
0x18014e02e  mov     rbx, rax
0x18014e031  test    rax, rax
0x18014e034  jz      loc_18014E1DD
0x18014e03a  mov     edx, 1; Revision
0x18014e03f  mov     rcx, rax; SecurityDescriptor
0x18014e042  call    cs:__imp_RtlCreateSecurityDescriptor
0x18014e049  nop     dword ptr [rax+rax+00h]
0x18014e04e  test    eax, eax
0x18014e050  jns     short loc_18014E0C1
0x18014e052  lea     rdx, aRtlcreatesecur; "RtlCreateSecurityDescriptor"
0x18014e059  mov     [rsp+0E0h+LengthNeeded], rdx; int
0x18014e05e  mov     edx, 590h; void *
0x18014e063  mov     rcx, [rbp+5Fh]; this
0x18014e067  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x18014e06e  mov     r9d, eax; char *
0x18014e071  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18014e076  mov     ebx, eax
0x18014e078  jmp     loc_18014E206
0x18014e07d  lea     rdx, aRtladdaceLu; "RtlAddAce %lu"
0x18014e084  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x18014e088  mov     [rsp+0E0h+LengthNeeded], rdx
0x18014e08d  mov     edx, 586h
0x18014e092  jmp     short loc_18014E0A9
0x18014e094  lea     rdx, aRtlgetaceLu; "RtlGetAce %lu"
0x18014e09b  mov     dword ptr [rsp+0E0h+var_B8], ebx; char *
0x18014e09f  mov     [rsp+0E0h+LengthNeeded], rdx; int
0x18014e0a4  mov     edx, 582h; void *
0x18014e0a9  mov     rcx, [rbp+5Fh]; this
0x18014e0ad  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x18014e0b4  mov     r9d, eax; char *
0x18014e0b7  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x18014e0bc  jmp     loc_18014DFAC
0x18014e0c1  xor     r9d, r9d; DaclDefaulted
0x18014e0c4  mov     r8, rdi; Dacl
0x18014e0c7  mov     dl, 1; DaclPresent
0x18014e0c9  mov     rcx, rbx; SecurityDescriptor
0x18014e0cc  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18014e0d3  nop     dword ptr [rax+rax+00h]
0x18014e0d8  test    eax, eax
0x18014e0da  jns     short loc_18014E0F2
0x18014e0dc  lea     rdx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor"
0x18014e0e3  mov     [rsp+0E0h+LengthNeeded], rdx
0x18014e0e8  mov     edx, 594h
0x18014e0ed  jmp     loc_18014E063
0x18014e0f2  lea     r8, [rbp+57h+Revision]; Revision
0x18014e0f6  mov     [rbp+57h+Control], r15w
0x18014e0fb  lea     rdx, [rbp+57h+Control]; Control
0x18014e0ff  mov     [rbp+57h+Revision], r15d
0x18014e103  mov     rcx, rsi; SecurityDescriptor
0x18014e106  call    cs:__imp_RtlGetControlSecurityDescriptor
0x18014e10d  nop     dword ptr [rax+rax+00h]
0x18014e112  test    eax, eax
0x18014e114  jns     short loc_18014E12C
0x18014e116  lea     rdx, aRtlgetcontrols; "RtlGetControlSecurityDescriptor"
0x18014e11d  mov     [rsp+0E0h+LengthNeeded], rdx
  ... truncated ...
```
