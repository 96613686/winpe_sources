# _lambda_f582acd5b9504eb834dd17ecbdb6718d_::operator()

- ea: `0x1801437e8`
- end: `0x180143dd8`
- name: `_lambda_f582acd5b9504eb834dd17ecbdb6718d_::operator()`
- size: `1520`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180143de0`

## callees

- `0x180053148`
- `0x1800534f8`
- `0x180056554`
- `0x180057154`
- `0x18005a800`
- `0x180067f80`
- `0x180099b64`
- `0x18010b9d4`
- `0x1801437e8`
- `0x180188f10`

## import_xrefs

- `ntdll!NtQuerySecurityObject` at `0x1801438c3`
- `ntdll!NtQuerySecurityObject` at `0x180143965`
- `ntdll!NtQuerySecurityObject` at `0x1801438c3`
- `ntdll!NtQuerySecurityObject` at `0x180143965`
- `ntdll!RtlGetAce` at `0x180143b4d`
- `ntdll!RtlGetAce` at `0x180143b4d`
- `ntdll!RtlQueryInformationAcl` at `0x180143a0c`
- `ntdll!RtlQueryInformationAcl` at `0x180143a0c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1801438cb`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1801438cb`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1801439b1`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1801439b1`
- `ntdll!RtlCreateAcl` at `0x180143a65`
- `ntdll!RtlCreateAcl` at `0x180143a65`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180143b04`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180143b04`
- `ntdll!RtlAddAce` at `0x180143b74`
- `ntdll!RtlAddAce` at `0x180143b74`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180143bb6`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180143bb6`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180143c3a`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180143c3a`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180143c6e`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x180143c6e`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x180143ca1`
- `ntdll!RtlSetControlSecurityDescriptor` at `0x180143ca1`
- `ntdll!NtSetSecurityObject` at `0x180143cd0`
- `ntdll!NtSetSecurityObject` at `0x180143cd0`
- `ntdll!RtlAllocateHeap` at `0x180143936`
- `ntdll!RtlAllocateHeap` at `0x180143a44`
- `ntdll!RtlAllocateHeap` at `0x180143b98`
- `ntdll!RtlAllocateHeap` at `0x180143936`
- `ntdll!RtlAllocateHeap` at `0x180143a44`
- `ntdll!RtlAllocateHeap` at `0x180143b98`

## string_xrefs

- `0x1801439bb`: `RtlGetDaclSecurityDescriptor`
- `0x1801439d7`: `RtlGetDaclSecurityDescriptor`
- `0x180143a16`: `RtlQueryInformationAcl`
- `0x18014396f`: `NtQuerySecurityObject`
- `0x180143b12`: `RtlAddAccessAllowedAceEx`
- `0x180143a73`: `RtlCreateAcl %u`
- `0x180143abd`: `AppContainerDeriveSidFromMoniker`
- `0x180143864`: `RegCreateKeyEx`
- `0x180143c44`: `RtlSetDaclSecurityDescriptor`
- `0x180143c78`: `RtlGetControlSecurityDescriptor`
- `0x180143bc0`: `RtlCreateSecurityDescriptor`
- `0x180143cab`: `RtlSetControlSecurityDescriptor`
- `0x180143cda`: `NtSetSecurityObject`

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
0x1801437e8  push    rbp
0x1801437ea  push    rbx
0x1801437eb  push    rsi
0x1801437ec  push    rdi
0x1801437ed  push    r14
0x1801437ef  push    r15
0x1801437f1  lea     rbp, [rsp-2Fh]
0x1801437f6  sub     rsp, 0B8h
0x1801437fd  mov     rax, cs:__security_cookie
0x180143804  xor     rax, rsp
0x180143807  mov     [rbp+57h+var_38], rax
0x18014380b  mov     rbx, [rcx+10h]
0x18014380f  mov     r14, rcx
0x180143812  mov     rdi, [rcx+18h]
0x180143816  xor     edx, edx
0x180143818  mov     rcx, rbx
0x18014381b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180143820  mov     rdx, [r14+8]
0x180143824  xor     r15d, r15d
0x180143827  mov     rcx, [r14]
0x18014382a  xor     r9d, r9d
0x18014382d  mov     [rsp+0E0h+var_98], r15
0x180143832  xor     r8d, r8d
0x180143835  mov     [rsp+0E0h+var_A0], rdi
0x18014383a  mov     rdx, [rdx]
0x18014383d  mov     rcx, [rcx]
0x180143840  mov     [rsp+0E0h+var_A8], rbx
0x180143845  mov     [rsp+0E0h+var_B0], r15
0x18014384a  mov     dword ptr [rsp+0E0h+var_B8], 0F003Fh; char *
0x180143852  mov     dword ptr [rsp+0E0h+LengthNeeded], r15d
0x180143857  call    RegCreateKeyExInternalW
0x18014385c  test    eax, eax
0x18014385e  jz      short loc_180143889
0x180143860  mov     rcx, [rbp+5Fh]; this
0x180143864  lea     rdx, aRegcreatekeyex_3; "RegCreateKeyEx"
0x18014386b  mov     [rsp+0E0h+LengthNeeded], rdx; unsigned int
0x180143870  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x180143877  mov     edx, 520h; void *
0x18014387c  mov     r9d, eax; char *
0x18014387f  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180143884  jmp     loc_180143D16
0x180143889  mov     rax, [r14+18h]
0x18014388d  cmp     dword ptr [rax], 1
0x180143890  jnz     loc_180143D14
0x180143896  mov     rcx, [r14+10h]
0x18014389a  xor     eax, eax
0x18014389c  xor     r9d, r9d; Length
0x18014389f  mov     [rbp+57h+Information], rax
0x1801438a3  mov     [rbp+57h+var_40], eax
0x1801438a6  xor     r8d, r8d; SecurityDescriptor
0x1801438a9  lea     rax, [rbp+57h+Length]
0x1801438ad  mov     [rbp+57h+Dacl], r15
0x1801438b1  mov     rcx, [rcx]; Handle
0x1801438b4  lea     edi, [r9+4]
0x1801438b8  mov     [rbp+57h+Length], r15d
0x1801438bc  mov     edx, edi; SecurityInformation
0x1801438be  mov     [rsp+0E0h+LengthNeeded], rax; LengthNeeded
0x1801438c3  call    cs:__imp_NtQuerySecurityObject
0x1801438c9  mov     ecx, eax; Status
0x1801438cb  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1801438d1  mov     ebx, eax
0x1801438d3  test    eax, eax
0x1801438d5  jle     short loc_1801438E0
0x1801438d7  movzx   ebx, ax
0x1801438da  or      ebx, 80070000h
0x1801438e0  test    ebx, ebx
0x1801438e2  js      short loc_180143914
0x1801438e4  mov     ebx, 8007054Fh
0x1801438e9  mov     edx, 53Dh; void *
0x1801438ee  mov     rcx, [rbp+5Fh]; this
0x1801438f2  lea     rax, aStatusntquerys; "statusNtQuerySecutiryObject"
0x1801438f9  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x180143900  mov     [rsp+0E0h+LengthNeeded], rax; int
0x180143905  mov     r9d, ebx; char *
0x180143908  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18014390d  mov     eax, ebx
0x18014390f  jmp     loc_180143D16
0x180143914  cmp     ebx, 8007007Ah
0x18014391a  jz      short loc_180143923
0x18014391c  mov     edx, 53Fh
0x180143921  jmp     short loc_1801438EE
0x180143923  mov     rcx, gs:60h
0x18014392c  xor     edx, edx; Flags
0x18014392e  mov     r8d, [rbp+57h+Length]; Size
0x180143932  mov     rcx, [rcx+30h]; HeapHandle
0x180143936  call    cs:__imp_RtlAllocateHeap
0x18014393c  mov     [rbp+57h+var_50], rax
0x180143940  mov     rsi, rax
0x180143943  test    rax, rax
0x180143946  jz      loc_180143DA1
0x18014394c  mov     rcx, [r14+10h]
0x180143950  lea     rax, [rbp+57h+Length]
0x180143954  mov     r9d, [rbp+57h+Length]; Length
0x180143958  mov     r8, rsi; SecurityDescriptor
0x18014395b  mov     edx, edi; SecurityInformation
0x18014395d  mov     [rsp+0E0h+LengthNeeded], rax; LengthNeeded
0x180143962  mov     rcx, [rcx]; Handle
0x180143965  call    cs:__imp_NtQuerySecurityObject
0x18014396b  test    eax, eax
0x18014396d  jns     short loc_18014399A
0x18014396f  lea     rdx, aNtquerysecurit_0; "NtQuerySecurityObject"
0x180143976  mov     [rsp+0E0h+LengthNeeded], rdx; int
0x18014397b  mov     edx, 54Bh; void *
0x180143980  mov     rcx, [rbp+5Fh]; this
0x180143984  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x18014398b  mov     r9d, eax; char *
0x18014398e  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180143993  mov     ebx, eax
0x180143995  jmp     loc_180143DCA
0x18014399a  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x18014399e  mov     [rbp+57h+DaclPresent], r15b
0x1801439a2  lea     r8, [rbp+57h+Dacl]; Dacl
0x1801439a6  mov     [rbp+57h+DaclDefaulted], r15b
0x1801439aa  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x1801439ae  mov     rcx, rsi; SecurityDescriptor
0x1801439b1  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1801439b7  test    eax, eax
0x1801439b9  jns     short loc_1801439CE
0x1801439bb  lea     rdx, aRtlgetdaclsecu; "RtlGetDaclSecurityDescriptor"
0x1801439c2  mov     [rsp+0E0h+LengthNeeded], rdx
0x1801439c7  mov     edx, 551h
0x1801439cc  jmp     short loc_180143980
0x1801439ce  mov     rcx, [rbp+57h+Dacl]; Acl
0x1801439d2  test    rcx, rcx
0x1801439d5  jnz     short loc_1801439F2
0x1801439d7  lea     rdx, aRtlgetdaclsecu; "RtlGetDaclSecurityDescriptor"
0x1801439de  mov     ebx, 8007054Fh
0x1801439e3  mov     [rsp+0E0h+LengthNeeded], rdx
0x1801439e8  mov     edx, 554h
0x1801439ed  jmp     loc_180143DB7
0x1801439f2  mov     r9d, 2; InformationClass
0x1801439f8  mov     dword ptr [rbp+57h+Information], r15d
0x1801439fc  lea     rdx, [rbp+57h+Information]; Information
0x180143a00  mov     [rbp+57h+Information+4], 8
0x180143a08  lea     r8d, [r9+0Ah]; InformationLength
0x180143a0c  call    cs:__imp_RtlQueryInformationAcl
0x180143a12  test    eax, eax
0x180143a14  jns     short loc_180143A2C
0x180143a16  lea     rdx, aRtlqueryinform; "RtlQueryInformationAcl"
0x180143a1d  mov     [rsp+0E0h+LengthNeeded], rdx
0x180143a22  mov     edx, 55Dh
0x180143a27  jmp     loc_180143980
0x180143a2c  mov     rcx, gs:60h
0x180143a35  xor     edx, edx; Flags
0x180143a37  mov     ebx, dword ptr [rbp+57h+Information+4]
0x180143a3a  add     ebx, 50h ; 'P'
0x180143a3d  mov     r8d, ebx; Size
0x180143a40  mov     rcx, [rcx+30h]; HeapHandle
0x180143a44  call    cs:__imp_RtlAllocateHeap
0x180143a4a  mov     [rbp+57h+var_80], rax
0x180143a4e  mov     rdi, rax
0x180143a51  test    rax, rax
0x180143a54  jz      loc_180143D69
0x180143a5a  mov     r8d, 2; AclRevision
0x180143a60  mov     edx, ebx; AclSize
0x180143a62  mov     rcx, rax; Acl
0x180143a65  call    cs:__imp_RtlCreateAcl
0x180143a6b  test    eax, eax
0x180143a6d  jns     short loc_180143A9E
0x180143a6f  mov     rcx, [rbp+5Fh]; this
0x180143a73  lea     rdx, aRtlcreateaclU; "RtlCreateAcl %u"
0x180143a7a  mov     dword ptr [rsp+0E0h+var_B8], ebx; char *
0x180143a7e  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x180143a85  mov     [rsp+0E0h+LengthNeeded], rdx; int
0x180143a8a  mov     r9d, eax; char *
0x180143a8d  mov     edx, 56Ah; void *
0x180143a92  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180143a97  mov     ebx, eax
0x180143a99  jmp     loc_180143D96
0x180143a9e  mov     rcx, [r14+20h]
0x180143aa2  lea     rdx, [rbp+57h+pSid]
0x180143aa6  mov     [rbp+57h+pSid], r15
0x180143aaa  mov     rcx, [rcx+18h]; char *
0x180143aae  call    AppContainerDeriveSidFromMoniker
0x180143ab3  mov     ebx, eax
0x180143ab5  test    eax, eax
0x180143ab7  jns     short loc_180143AEB
0x180143ab9  mov     rcx, [rbp+5Fh]; this
0x180143abd  lea     rax, aAppcontainerde_0; "AppContainerDeriveSidFromMoniker"
0x180143ac4  mov     r9d, ebx; char *
0x180143ac7  mov     [rsp+0E0h+LengthNeeded], rax; int
0x180143acc  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x180143ad3  mov     edx, 56Fh; void *
0x180143ad8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180143add  lea     rcx, [rbp+57h+pSid]
0x180143ae1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180143ae6  jmp     loc_180143D96
0x180143aeb  mov     rax, [rbp+57h+pSid]
0x180143aef  mov     r9d, 1; AccessMask
0x180143af5  xor     r8d, r8d; AceFlags
0x180143af8  mov     [rsp+0E0h+LengthNeeded], rax; pSid
0x180143afd  mov     rcx, rdi; pAcl
0x180143b00  lea     edx, [r9+1]; dwAceRevision
0x180143b04  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180143b0a  test    eax, eax
0x180143b0c  jns     short loc_180143B36
0x180143b0e  mov     rcx, [rbp+5Fh]; this
0x180143b12  lea     rdx, aRtladdaccessal; "RtlAddAccessAllowedAceEx"
0x180143b19  mov     [rsp+0E0h+LengthNeeded], rdx; int
0x180143b1e  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x180143b25  mov     edx, 574h; void *
0x180143b2a  mov     r9d, eax; char *
0x180143b2d  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180143b32  mov     ebx, eax
0x180143b34  jmp     short loc_180143ADD
0x180143b36  mov     ebx, r15d
0x180143b39  cmp     dword ptr [rbp+57h+Information], r15d
0x180143b3d  jbe     short loc_180143B85
0x180143b3f  mov     rcx, [rbp+57h+Dacl]; Acl
0x180143b43  lea     r8, [rbp+57h+Ace]; Ace
0x180143b47  mov     edx, ebx; AceIndex
0x180143b49  mov     [rbp+57h+Ace], r15
0x180143b4d  call    cs:__imp_RtlGetAce
0x180143b53  test    eax, eax
0x180143b55  js      loc_180143C02
0x180143b5b  mov     r9, [rbp+57h+Ace]; AceList
0x180143b5f  or      r8d, 0FFFFFFFFh; StartingAceIndex
0x180143b63  mov     edx, 2; AceRevision
0x180143b68  mov     rcx, rdi; Acl
0x180143b6b  movzx   eax, word ptr [r9+2]
0x180143b70  mov     dword ptr [rsp+0E0h+LengthNeeded], eax; AceListLength
0x180143b74  call    cs:__imp_RtlAddAce
0x180143b7a  test    eax, eax
0x180143b7c  js      short loc_180143BEB
0x180143b7e  inc     ebx
0x180143b80  cmp     ebx, dword ptr [rbp+57h+Information]
0x180143b83  jb      short loc_180143B3F
0x180143b85  mov     rcx, gs:60h
0x180143b8e  xor     edx, edx; Flags
0x180143b90  mov     rcx, [rcx+30h]; HeapHandle
0x180143b94  lea     r8d, [rdx+28h]; Size
0x180143b98  call    cs:__imp_RtlAllocateHeap
0x180143b9e  mov     [rbp+57h+var_70], rax
0x180143ba2  mov     rbx, rax
0x180143ba5  test    rax, rax
0x180143ba8  jz      loc_180143D32
0x180143bae  mov     edx, 1; Revision
0x180143bb3  mov     rcx, rax; SecurityDescriptor
0x180143bb6  call    cs:__imp_RtlCreateSecurityDescriptor
0x180143bbc  test    eax, eax
0x180143bbe  jns     short loc_180143C2F
0x180143bc0  lea     rdx, aRtlcreatesecur; "RtlCreateSecurityDescriptor"
0x180143bc7  mov     [rsp+0E0h+LengthNeeded], rdx; int
0x180143bcc  mov     edx, 590h; void *
0x180143bd1  mov     rcx, [rbp+5Fh]; this
0x180143bd5  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x180143bdc  mov     r9d, eax; char *
0x180143bdf  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180143be4  mov     ebx, eax
0x180143be6  jmp     loc_180143D5B
0x180143beb  lea     rdx, aRtladdaceLu; "RtlAddAce %lu"
0x180143bf2  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x180143bf6  mov     [rsp+0E0h+LengthNeeded], rdx
0x180143bfb  mov     edx, 586h
0x180143c00  jmp     short loc_180143C17
0x180143c02  lea     rdx, aRtlgetaceLu; "RtlGetAce %lu"
0x180143c09  mov     dword ptr [rsp+0E0h+var_B8], ebx; char *
0x180143c0d  mov     [rsp+0E0h+LengthNeeded], rdx; int
0x180143c12  mov     edx, 582h; void *
0x180143c17  mov     rcx, [rbp+5Fh]; this
0x180143c1b  lea     r8, aOnecoreBaseApp_35; "onecore\\base\\appmodel\\statemanager\\"...
0x180143c22  mov     r9d, eax; char *
0x180143c25  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x180143c2a  jmp     loc_180143B32
0x180143c2f  xor     r9d, r9d; DaclDefaulted
0x180143c32  mov     r8, rdi; Dacl
0x180143c35  mov     dl, 1; DaclPresent
0x180143c37  mov     rcx, rbx; SecurityDescriptor
0x180143c3a  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180143c40  test    eax, eax
0x180143c42  jns     short loc_180143C5A
0x180143c44  lea     rdx, aRtlsetdaclsecu; "RtlSetDaclSecurityDescriptor"
0x180143c4b  mov     [rsp+0E0h+LengthNeeded], rdx
0x180143c50  mov     edx, 594h
0x180143c55  jmp     loc_180143BD1
0x180143c5a  lea     r8, [rbp+57h+Revision]; Revision
0x180143c5e  mov     [rbp+57h+Control], r15w
0x180143c63  lea     rdx, [rbp+57h+Control]; Control
0x180143c67  mov     [rbp+57h+Revision], r15d
0x180143c6b  mov     rcx, rsi; SecurityDescriptor
0x180143c6e  call    cs:__imp_RtlGetControlSecurityDescriptor
0x180143c74  test    eax, eax
0x180143c76  jns     short loc_180143C8E
0x180143c78  lea     rdx, aRtlgetcontrols; "RtlGetControlSecurityDescriptor"
0x180143c7f  mov     [rsp+0E0h+LengthNeeded], rdx
0x180143c84  mov     edx, 59Ch
0x180143c89  jmp     loc_180143BD1
0x180143c8e  movzx   edx, [rbp+57h+Control]
0x180143c92  mov     eax, 500h
0x180143c97  and     dx, ax; ControlBitsOfInterest
0x180143c9a  mov     rcx, rbx; SecurityDescriptor
0x180143c9d  movzx   r8d, dx; ControlBitsToSet
0x180143ca1  call    cs:__imp_RtlSetControlSecurityDescriptor
0x180143ca7  test    eax, eax
0x180143ca9  jns     short loc_180143CC1
0x180143cab  lea     rdx, aRtlsetcontrols; "RtlSetControlSecurityDescriptor"
0x180143cb2  mov     [rsp+0E0h+LengthNeeded], rdx
0x180143cb7  mov     edx, 5A3h
0x180143cbc  jmp     loc_180143BD1
0x180143cc1  mov     rcx, [r14+10h]
  ... truncated ...
```
