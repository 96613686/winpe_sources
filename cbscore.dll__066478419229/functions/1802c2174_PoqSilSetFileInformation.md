# PoqSilSetFileInformation

- ea: `0x1802c2174`
- end: `0x1802c26e7`
- name: `PoqSilSetFileInformation`
- size: `1395`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802c1040`
- `0x1802c5c40`

## callees

- `0x180046198`
- `0x1800a26b0`
- `0x1800aa1a4`
- `0x1800aa1d4`
- `0x1800eb920`
- `0x1800ef360`
- `0x1801f7e90`
- `0x1802be3a4`
- `0x1802c2174`
- `0x1802c5634`
- `0x1802d5010`

## import_xrefs

- `ntdll!RtlDuplicateUnicodeString` at `0x1802c2300`
- `ntdll!RtlDuplicateUnicodeString` at `0x1802c2300`
- `ntdll!RtlEqualUnicodeString` at `0x1802c2227`
- `ntdll!RtlEqualUnicodeString` at `0x1802c2227`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1802c24f8`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1802c24f8`
- `ntdll!RtlFindAceByType` at `0x1802c25d6`
- `ntdll!RtlFindAceByType` at `0x1802c25d6`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x1802c24a8`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x1802c24a8`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1802c245f`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1802c245f`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x1802c2548`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x1802c2548`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1802c2400`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1802c2400`

## string_xrefs

- `0x1802c21ee`: `!Context->GlobalContext->RegistryOnly`
- `0x1802c233d`: `RtlDuplicateUnicodeString( 0, &Operation->FilePath, TempName.GetMutablePointer())`
- `0x1802c2434`: `RtlGetControlSecurityDescriptor( Operation->SecurityDescriptor, &Control, &Revision)`
- `0x1802c21e3`: `PoqSilSetFileInformation`
- `0x1802c232d`: `PoqSilSetFileInformation`
- `0x1802c2428`: `PoqSilSetFileInformation`
- `0x1802c2487`: `PoqSilSetFileInformation`
- `0x1802c24d0`: `PoqSilSetFileInformation`
- `0x1802c2520`: `PoqSilSetFileInformation`
- `0x1802c2570`: `PoqSilSetFileInformation`
- `0x1802c2665`: `PoqSilSetFileInformation`
- `0x1802c252c`: `RtlGetDaclSecurityDescriptor( Operation->SecurityDescriptor, &fDaclPresent, &Dacl, &fDefaulted)`
- `0x1802c257c`: `RtlGetSaclSecurityDescriptor( Operation->SecurityDescriptor, &fSaclPresent, &Sacl, &fDefaulted)`
- `0x1802c2493`: `RtlGetOwnerSecurityDescriptor( Operation->SecurityDescriptor, &Owner, &fDefaulted)`
- `0x1802c24dc`: `RtlGetGroupSecurityDescriptor( Operation->SecurityDescriptor, &Group, &fDefaulted)`

## pseudocode

```c
__int64 __fastcall PoqSilSetFileInformation(char a1, __int64 *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  struct _UNICODE_STRING *p_DestinationString; // rdx
  __int64 result; // rax
  const UNICODE_STRING *v11; // r14
  __int64 v12; // rax
  int v13; // esi
  NTSTATUS v14; // eax
  __int64 v15; // rsi
  void *v16; // rcx
  NTSTATUS ControlSecurityDescriptor; // eax
  __int64 v18; // r8
  const char *v19; // rax
  NTSTATUS OwnerSecurityDescriptor; // eax
  NTSTATUS GroupSecurityDescriptor; // eax
  NTSTATUS DaclSecurityDescriptor; // eax
  NTSTATUS SaclSecurityDescriptor; // eax
  unsigned int v24; // ebx
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  const char *v26; // [rsp+58h] [rbp-A8h]
  __int64 v27; // [rsp+60h] [rbp-A0h]
  const char *v28; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+70h] [rbp-90h]
  __int128 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+90h] [rbp-70h]
  PACL Sacl; // [rsp+A0h] [rbp-60h] BYREF
  PSID Group; // [rsp+A8h] [rbp-58h] BYREF
  PSID Owner; // [rsp+B0h] [rbp-50h] BYREF
  PACL Dacl; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 DaclPresent; // [rsp+C1h] [rbp-3Fh] BYREF
  unsigned __int8 SaclPresent[2]; // [rsp+C2h] [rbp-3Eh] BYREF
  int v39; // [rsp+C4h] [rbp-3Ch] BYREF
  WORD Control[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v41; // [rsp+CCh] [rbp-34h] BYREF
  __int64 v42; // [rsp+D0h] [rbp-30h] BYREF
  ULONG Revision; // [rsp+D8h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v45; // [rsp+F0h] [rbp-10h]
  const char *v46; // [rsp+F8h] [rbp-8h]
  __int128 v47; // [rsp+100h] [rbp+0h] BYREF
  __int64 v48; // [rsp+110h] [rbp+10h]

  v48 = 0;
  v4 = *(_QWORD *)(a4 + 104);
  v47 = 0;
  *(_DWORD *)(a4 + 112) = 0;
  v39 = 0;
  if ( *(_BYTE *)(v4 + 89) )
  {
    v45 = 2356;
    *(_QWORD *)&DestinationString.Length = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    p_DestinationString = &DestinationString;
    DestinationString.Buffer = (PWSTR)"PoqSilSetFileInformation";
    v46 = "!Context->GlobalContext->RegistryOnly";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v39,
             p_DestinationString);
  }
  v11 = (const UNICODE_STRING *)(a3 + 16);
  RtlInitLUnicodeStringFromUnicodeString(a3 + 16, &v47);
  if ( RtlEqualUnicodeString(v11, (PCUNICODE_STRING)(a4 + 56), 1u) )
  {
    v15 = *(_QWORD *)(a4 + 88);
  }
  else
  {
    v42 = 0;
    DestinationString = 0;
    OperationContext::ClearFileContext((OperationContext *)a4);
    v41 = 0;
    v25 = 40;
    v26 = (const char *)&v47;
    v30 = 0;
    v31 = 0;
    v29 = 0;
    v12 = *a2;
    v27 = 64;
    v28 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, __int64 *, int, int, __int64 *, int *))(v12 + 72))(
            a2,
            a1 != 0 ? 15 : 1,
            18743680,
            &v25,
            7,
            2113568,
            &v42,
            &v41);
    if ( v13 < 0 )
    {
LABEL_19:
      Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&DestinationString);
      Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v42);
      return (unsigned int)v13;
    }
    if ( v41 == 2 )
    {
      *(_DWORD *)(a4 + 112) = 0;
LABEL_18:
      v13 = 0;
      goto LABEL_19;
    }
    if ( v41 != 1 )
    {
      switch ( v41 )
      {
        case 3:
          *(_DWORD *)(a4 + 112) = -1073741757;
          break;
        case 5:
          *(_DWORD *)(a4 + 112) = -1072103423;
          break;
        case 6:
          *(_DWORD *)(a4 + 112) = -1073741738;
          break;
        default:
          INTERNAL_ERROR_ACTION(-1073741595);
          JUMPOUT(0x1802C26E6LL);
      }
      goto LABEL_18;
    }
    v14 = RtlDuplicateUnicodeString(0, v11, &DestinationString);
    if ( v14 < 0 )
    {
      v27 = 2403;
      v25 = (__int64)"onecore\\base\\wcp\\poq\\poqsil.cpp";
      v26 = "PoqSilSetFileInformation";
      v28 = "RtlDuplicateUnicodeString( 0, &Operation->FilePath, TempName.GetMutablePointer())";
      v13 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
              &v39,
              &v25,
              (unsigned int)v14);
      goto LABEL_19;
    }
    OperationContext::TakeOwnership(a4, &DestinationString, &v42);
    v15 = *(_QWORD *)(a4 + 88);
    Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(&DestinationString);
    Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v42);
  }
  if ( (*(_BYTE *)a3 & 2) == 0 )
    goto LABEL_59;
  v16 = *(void **)(a3 + 8);
  Control[0] = 0;
  Revision = 0;
  Owner = 0;
  Group = 0;
  Dacl = 0;
  Sacl = 0;
  DaclPresent = 0;
  SaclPresent[0] = 0;
  OwnerDefaulted = 0;
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(v16, Control, &Revision);
  v18 = (unsigned int)ControlSecurityDescriptor;
  if ( ControlSecurityDescriptor < 0 )
  {
    v27 = 2454;
    v25 = (__int64)"onecore\\base\\wcp\\poq\\poqsil.cpp";
    v26 = "PoqSilSetFileInformation";
    v19 = "RtlGetControlSecurityDescriptor( Operation->SecurityDescriptor, &Control, &Revision)";
LABEL_24:
    v28 = v19;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v39,
             &v25,
             v18);
  }
  OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a3 + 8), &Owner, &OwnerDefaulted);
  v18 = (unsigned int)OwnerSecurityDescriptor;
  if ( OwnerSecurityDescriptor < 0 )
  {
    v27 = 2459;
    v25 = (__int64)"onecore\\base\\wcp\\poq\\poqsil.cpp";
    v26 = "PoqSilSetFileInformation";
    v19 = "RtlGetOwnerSecurityDescriptor( Operation->SecurityDescriptor, &Owner, &fDefaulted)";
    goto LABEL_24;
  }
  GroupSecurityDescriptor = RtlGetGroupSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a3 + 8), &Group, &OwnerDefaulted);
  v18 = (unsigned int)GroupSecurityDescriptor;
  if ( GroupSecurityDescriptor < 0 )
  {
    v27 = 2464;
    v25 = (__int64)"onecore\\base\\wcp\\poq\\poqsil.cpp";
    v26 = "PoqSilSetFileInformation";
    v19 = "RtlGetGroupSecurityDescriptor( Operation->SecurityDescriptor, &Group, &fDefaulted)";
    goto LABEL_24;
  }
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(
                             *(PSECURITY_DESCRIPTOR *)(a3 + 8),
                             &DaclPresent,
                             &Dacl,
                             &OwnerDefaulted);
  v18 = (unsigned int)DaclSecurityDescriptor;
  if ( DaclSecurityDescriptor < 0 )
  {
    v27 = 2470;
    v25 = (__int64)"onecore\\base\\wcp\\poq\\poqsil.cpp";
    v26 = "PoqSilSetFileInformation";
    v19 = "RtlGetDaclSecurityDescriptor( Operation->SecurityDescriptor, &fDaclPresent, &Dacl, &fDefaulted)";
    goto LABEL_24;
  }
  SaclSecurityDescriptor = RtlGetSaclSecurityDescriptor(
                             *(PSECURITY_DESCRIPTOR *)(a3 + 8),
                             SaclPresent,
                             &Sacl,
                             &OwnerDefaulted);
  v18 = (unsigned int)SaclSecurityDescriptor;
  if ( SaclSecurityDescriptor < 0 )
  {
    v27 = 2476;
    v25 = (__int64)"onecore\\base\\wcp\\poq\\poqsil.cpp";
    v26 = "PoqSilSetFileInformation";
    v19 = "RtlGetSaclSecurityDescriptor( Operation->SecurityDescriptor, &fSaclPresent, &Sacl, &fDefaulted)";
    goto LABEL_24;
  }
  v24 = Owner != 0;
  if ( Group )
    v24 |= 2u;
  if ( DaclPresent )
  {
    v24 |= 4u;
    if ( (Control[0] & 0x1000) != 0 )
      v24 |= 0x80000000;
  }
  if ( SaclPresent[0] )
  {
    v24 |= ((Control[0] & 0x2000) << 17) | 8;
    if ( RtlFindAceByType(Sacl, 17) )
      v24 |= 0x10u;
  }
  result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, PSID, PSID, PACL, PACL))(*(_QWORD *)v15 + 40LL))(
             v15,
             (*(_DWORD *)a3 >> 6) & 1,
             v24,
             Owner,
             Group,
             Dacl,
             Sacl);
  if ( (int)result >= 0 )
  {
LABEL_59:
    if ( (*(_BYTE *)a3 & 1) == 0
      || (result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 80LL))(v15, *(unsigned int *)(a3 + 4)),
          (int)result >= 0) )
    {
      if ( (*(_BYTE *)a3 & 4) != 0 )
      {
        v27 = 2530;
LABEL_46:
        v25 = (__int64)"onecore\\base\\wcp\\poq\\poqsil.cpp";
        p_DestinationString = (struct _UNICODE_STRING *)&v25;
        v26 = "PoqSilSetFileInformation";
        v28 = "Operation->Flags";
        return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
                 &v39,
                 p_DestinationString);
      }
      if ( (*(_BYTE *)a3 & 8) != 0 )
      {
        v27 = 2531;
        goto LABEL_46;
      }
      if ( (*(_BYTE *)a3 & 0x10) != 0 )
      {
        v27 = 2532;
        goto LABEL_46;
      }
      if ( (*(_BYTE *)a3 & 0x20) != 0 )
      {
        v27 = 2533;
        goto LABEL_46;
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1802c2174  mov     [rsp-8+arg_0], rbx
0x1802c2179  push    rbp
0x1802c217a  push    rsi
0x1802c217b  push    rdi
0x1802c217c  push    r12
0x1802c217e  push    r13
0x1802c2180  push    r14
0x1802c2182  push    r15
0x1802c2184  lea     rbp, [rsp-20h]
0x1802c2189  sub     rsp, 120h
0x1802c2190  mov     rax, cs:__security_cookie
0x1802c2197  xor     rax, rsp
0x1802c219a  mov     [rbp+50h+var_38], rax
0x1802c219e  xor     eax, eax
0x1802c21a0  xor     r12d, r12d
0x1802c21a3  mov     [rbp+50h+var_40], rax
0x1802c21a7  xorps   xmm0, xmm0
0x1802c21aa  mov     rax, [r9+68h]
0x1802c21ae  mov     rbx, r9
0x1802c21b1  movups  [rbp+50h+var_50], xmm0
0x1802c21b5  mov     [r9+70h], r12d
0x1802c21b9  mov     rdi, r8
0x1802c21bc  mov     r15, rdx
0x1802c21bf  mov     [rbp+50h+var_8C], r12d
0x1802c21c3  mov     sil, cl
0x1802c21c6  cmp     [rax+59h], r12b
0x1802c21ca  jz      short loc_1802C2207
0x1802c21cc  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c21d3  mov     [rbp+50h+var_60], 934h
0x1802c21db  mov     qword ptr [rbp+50h+DestinationString.Length], rax
0x1802c21df  lea     rdx, [rbp+50h+DestinationString]
0x1802c21e3  lea     rax, aPoqsilsetfilei; "PoqSilSetFileInformation"
0x1802c21ea  mov     [rbp+50h+DestinationString.Buffer], rax
0x1802c21ee  lea     rax, aContextGlobalc; "!Context->GlobalContext->RegistryOnly"
0x1802c21f5  mov     [rbp+50h+var_58], rax
0x1802c21f9  lea     rcx, [rbp+50h+var_8C]
0x1802c21fd  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1802c2202  jmp     loc_1802C26B4
0x1802c2207  lea     r14, [r8+10h]
0x1802c220b  mov     rcx, r14
0x1802c220e  lea     rdx, [rbp+50h+var_50]
0x1802c2212  call    RtlInitLUnicodeStringFromUnicodeString
0x1802c2217  mov     r13d, 1
0x1802c221d  lea     rdx, [rbx+38h]; String2
0x1802c2221  mov     r8b, r13b; CaseInsensitive
0x1802c2224  mov     rcx, r14; String1
0x1802c2227  call    cs:__imp_RtlEqualUnicodeString
0x1802c222e  nop     dword ptr [rax+rax+00h]
0x1802c2233  test    al, al
0x1802c2235  jnz     loc_1802C23C2
0x1802c223b  xorps   xmm0, xmm0
0x1802c223e  mov     [rbp+50h+var_80], r12
0x1802c2242  mov     rcx, rbx; this
0x1802c2245  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x1802c2249  call    ?ClearFileContext@OperationContext@@QEAAXXZ; OperationContext::ClearFileContext(void)
0x1802c224e  xorps   xmm0, xmm0
0x1802c2251  mov     [rbp+50h+var_84], r12d
0x1802c2255  lea     rax, [rbp+50h+var_50]
0x1802c2259  mov     [rsp+150h+var_100], 28h ; '('
0x1802c2262  mov     [rsp+150h+var_F8], rax
0x1802c2267  lea     rcx, [rbp+50h+var_84]
0x1802c226b  mov     [rsp+150h+var_118], rcx
0x1802c2270  lea     r9, [rsp+150h+var_100]
0x1802c2275  movups  [rbp+50h+var_D0], xmm0
0x1802c2279  mov     eax, dword ptr [rbp+50h+var_D0+0Ch]
0x1802c227c  lea     rcx, [rbp+50h+var_80]
0x1802c2280  mov     dword ptr [rsp+150h+var_F0+4], eax
0x1802c2284  neg     sil
0x1802c2287  mov     [rsp+150h+var_120], rcx
0x1802c228c  mov     r8d, 11E0180h
0x1802c2292  sbb     edx, edx
0x1802c2294  mov     dword ptr [rsp+150h+var_128], 204020h
0x1802c229c  movups  [rbp+50h+var_C0], xmm0
0x1802c22a0  mov     rax, qword ptr [rbp+50h+var_C0+8]
0x1802c22a4  and     edx, 0Eh
0x1802c22a7  mov     [rsp+150h+var_E0], rax
0x1802c22ac  add     edx, r13d
0x1802c22af  mov     rax, [r15]
0x1802c22b2  mov     rcx, r15
0x1802c22b5  mov     dword ptr [rsp+150h+var_F0], 40h ; '@'
0x1802c22bd  mov     [rsp+150h+var_E8], r12
0x1802c22c2  mov     dword ptr [rsp+150h+var_130], 7
0x1802c22ca  mov     rax, [rax+48h]
0x1802c22ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c22d3  mov     esi, eax
0x1802c22d5  test    eax, eax
0x1802c22d7  js      loc_1802C23A9
0x1802c22dd  mov     eax, [rbp+50h+var_84]
0x1802c22e0  cmp     eax, 2
0x1802c22e3  jnz     short loc_1802C22EE
0x1802c22e5  mov     [rbx+70h], r12d
0x1802c22e9  jmp     loc_1802C23A6
0x1802c22ee  cmp     eax, r13d
0x1802c22f1  jnz     loc_1802C237A
0x1802c22f7  lea     r8, [rbp+50h+DestinationString]; DestinationString
0x1802c22fb  mov     rdx, r14; SourceString
0x1802c22fe  xor     ecx, ecx; Flags
0x1802c2300  call    cs:__imp_RtlDuplicateUnicodeString
0x1802c2307  nop     dword ptr [rax+rax+00h]
0x1802c230c  mov     r8d, eax
0x1802c230f  test    eax, eax
0x1802c2311  jns     short loc_1802C2352
0x1802c2313  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c231a  mov     [rsp+150h+var_F0], 963h
0x1802c2323  mov     [rsp+150h+var_100], rax
0x1802c2328  lea     rdx, [rsp+150h+var_100]
0x1802c232d  lea     rax, aPoqsilsetfilei; "PoqSilSetFileInformation"
0x1802c2334  mov     [rsp+150h+var_F8], rax
0x1802c2339  lea     rcx, [rbp+50h+var_8C]
0x1802c233d  lea     rax, aRtlduplicateun_5; "RtlDuplicateUnicodeString( 0, &Operatio"...
0x1802c2344  mov     [rsp+150h+var_E8], rax
0x1802c2349  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1802c234e  mov     esi, eax
0x1802c2350  jmp     short loc_1802C23A9
0x1802c2352  lea     r8, [rbp+50h+var_80]
0x1802c2356  mov     rcx, rbx
0x1802c2359  lea     rdx, [rbp+50h+DestinationString]
0x1802c235d  call    ?TakeOwnership@OperationContext@@QEAAX$$QEAV?$Auto@U_UNICODE_STRING@@@Windows@@$$QEAV?$Auto@PEAUIRtlFilesystemObject@Rtl@Windows@@@3@@Z; OperationContext::TakeOwnership(Windows::Auto<_UNICODE_STRING> &&,Windows::Auto<Windows::Rtl::IRtlFilesystemObject *> &&)
0x1802c2362  mov     rsi, [rbx+58h]
0x1802c2366  lea     rcx, [rbp+50h+DestinationString]
0x1802c236a  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x1802c236f  lea     rcx, [rbp+50h+var_80]
0x1802c2373  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x1802c2378  jmp     short loc_1802C23C6
0x1802c237a  cmp     eax, 3
0x1802c237d  jnz     short loc_1802C2388
0x1802c237f  mov     dword ptr [rbx+70h], 0C0000043h
0x1802c2386  jmp     short loc_1802C23A6
0x1802c2388  cmp     eax, 5
0x1802c238b  jnz     short loc_1802C2396
0x1802c238d  mov     dword ptr [rbx+70h], 0C0190001h
0x1802c2394  jmp     short loc_1802C23A6
0x1802c2396  cmp     eax, 6
0x1802c2399  jnz     loc_1802C26DC
0x1802c239f  mov     dword ptr [rbx+70h], 0C0000056h
0x1802c23a6  mov     esi, r12d
0x1802c23a9  lea     rcx, [rbp+50h+DestinationString]
0x1802c23ad  call    ?Close@?$AutoString@U_UNICODE_STRING@@V?$Auto@U_UNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_UNICODE_STRING,Windows::Auto<_UNICODE_STRING>>::Close(void)
0x1802c23b2  lea     rcx, [rbp+50h+var_80]
0x1802c23b6  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x1802c23bb  mov     eax, esi
0x1802c23bd  jmp     loc_1802C26B4
0x1802c23c2  mov     rsi, [rbx+58h]
0x1802c23c6  test    byte ptr [rdi], 2
0x1802c23c9  jz      loc_1802C262B
0x1802c23cf  mov     rcx, [rdi+8]; SecurityDescriptor
0x1802c23d3  lea     r8, [rbp+50h+Revision]; Revision
0x1802c23d7  lea     rdx, [rbp+50h+Control]; Control
0x1802c23db  mov     [rbp+50h+Control], r12w
0x1802c23e0  mov     [rbp+50h+Revision], r12d
0x1802c23e4  mov     [rbp+50h+Owner], r12
0x1802c23e8  mov     [rbp+50h+Group], r12
0x1802c23ec  mov     [rbp+50h+Dacl], r12
0x1802c23f0  mov     [rbp+50h+Sacl], r12
0x1802c23f4  mov     [rbp+50h+DaclPresent], r12b
0x1802c23f8  mov     [rbp+50h+SaclPresent], r12b
0x1802c23fc  mov     [rbp+50h+OwnerDefaulted], r12b
0x1802c2400  call    cs:__imp_RtlGetControlSecurityDescriptor
0x1802c2407  nop     dword ptr [rax+rax+00h]
0x1802c240c  mov     r8d, eax
0x1802c240f  test    eax, eax
0x1802c2411  jns     short loc_1802C2453
0x1802c2413  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c241a  mov     [rsp+150h+var_F0], 996h
0x1802c2423  mov     [rsp+150h+var_100], rax
0x1802c2428  lea     rax, aPoqsilsetfilei; "PoqSilSetFileInformation"
0x1802c242f  mov     [rsp+150h+var_F8], rax
0x1802c2434  lea     rax, aRtlgetcontrols_0; "RtlGetControlSecurityDescriptor( Operat"...
0x1802c243b  lea     rdx, [rsp+150h+var_100]
0x1802c2440  mov     [rsp+150h+var_E8], rax
0x1802c2445  lea     rcx, [rbp+50h+var_8C]
0x1802c2449  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1802c244e  jmp     loc_1802C26B4
0x1802c2453  mov     rcx, [rdi+8]; SecurityDescriptor
0x1802c2457  lea     r8, [rbp+50h+OwnerDefaulted]; OwnerDefaulted
0x1802c245b  lea     rdx, [rbp+50h+Owner]; Owner
0x1802c245f  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1802c2466  nop     dword ptr [rax+rax+00h]
0x1802c246b  mov     r8d, eax
0x1802c246e  test    eax, eax
0x1802c2470  jns     short loc_1802C249C
0x1802c2472  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c2479  mov     [rsp+150h+var_F0], 99Bh
0x1802c2482  mov     [rsp+150h+var_100], rax
0x1802c2487  lea     rax, aPoqsilsetfilei; "PoqSilSetFileInformation"
0x1802c248e  mov     [rsp+150h+var_F8], rax
0x1802c2493  lea     rax, aRtlgetownersec_0; "RtlGetOwnerSecurityDescriptor( Operatio"...
0x1802c249a  jmp     short loc_1802C243B
0x1802c249c  mov     rcx, [rdi+8]; SecurityDescriptor
0x1802c24a0  lea     r8, [rbp+50h+OwnerDefaulted]; GroupDefaulted
0x1802c24a4  lea     rdx, [rbp+50h+Group]; Group
0x1802c24a8  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x1802c24af  nop     dword ptr [rax+rax+00h]
0x1802c24b4  mov     r8d, eax
0x1802c24b7  test    eax, eax
0x1802c24b9  jns     short loc_1802C24E8
0x1802c24bb  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c24c2  mov     [rsp+150h+var_F0], 9A0h
0x1802c24cb  mov     [rsp+150h+var_100], rax
0x1802c24d0  lea     rax, aPoqsilsetfilei; "PoqSilSetFileInformation"
0x1802c24d7  mov     [rsp+150h+var_F8], rax
0x1802c24dc  lea     rax, aRtlgetgroupsec_1; "RtlGetGroupSecurityDescriptor( Operatio"...
0x1802c24e3  jmp     loc_1802C243B
0x1802c24e8  mov     rcx, [rdi+8]; SecurityDescriptor
0x1802c24ec  lea     r9, [rbp+50h+OwnerDefaulted]; DaclDefaulted
0x1802c24f0  lea     r8, [rbp+50h+Dacl]; Dacl
0x1802c24f4  lea     rdx, [rbp+50h+DaclPresent]; DaclPresent
0x1802c24f8  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1802c24ff  nop     dword ptr [rax+rax+00h]
0x1802c2504  mov     r8d, eax
0x1802c2507  test    eax, eax
0x1802c2509  jns     short loc_1802C2538
0x1802c250b  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c2512  mov     [rsp+150h+var_F0], 9A6h
0x1802c251b  mov     [rsp+150h+var_100], rax
0x1802c2520  lea     rax, aPoqsilsetfilei; "PoqSilSetFileInformation"
0x1802c2527  mov     [rsp+150h+var_F8], rax
0x1802c252c  lea     rax, aRtlgetdaclsecu_0; "RtlGetDaclSecurityDescriptor( Operation"...
0x1802c2533  jmp     loc_1802C243B
0x1802c2538  mov     rcx, [rdi+8]; SecurityDescriptor
0x1802c253c  lea     r9, [rbp+50h+OwnerDefaulted]; SaclDefaulted
0x1802c2540  lea     r8, [rbp+50h+Sacl]; Sacl
0x1802c2544  lea     rdx, [rbp+50h+SaclPresent]; SaclPresent
0x1802c2548  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1802c254f  nop     dword ptr [rax+rax+00h]
0x1802c2554  mov     r8d, eax
0x1802c2557  test    eax, eax
0x1802c2559  jns     short loc_1802C2588
0x1802c255b  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c2562  mov     [rsp+150h+var_F0], 9ACh
0x1802c256b  mov     [rsp+150h+var_100], rax
0x1802c2570  lea     rax, aPoqsilsetfilei; "PoqSilSetFileInformation"
0x1802c2577  mov     [rsp+150h+var_F8], rax
0x1802c257c  lea     rax, aRtlgetsaclsecu; "RtlGetSaclSecurityDescriptor( Operation"...
0x1802c2583  jmp     loc_1802C243B
0x1802c2588  cmp     [rbp+50h+Owner], r12
0x1802c258c  mov     ebx, r12d
0x1802c258f  cmovnz  ebx, r13d
0x1802c2593  cmp     [rbp+50h+Group], r12
0x1802c2597  jz      short loc_1802C259C
0x1802c2599  or      ebx, 2
0x1802c259c  cmp     [rbp+50h+DaclPresent], r12b
0x1802c25a0  jz      short loc_1802C25B4
0x1802c25a2  or      ebx, 4
0x1802c25a5  mov     eax, 1000h
0x1802c25aa  test    [rbp+50h+Control], ax
0x1802c25ae  jz      short loc_1802C25B4
0x1802c25b0  bts     ebx, 1Fh
0x1802c25b4  cmp     [rbp+50h+SaclPresent], r12b
0x1802c25b8  jz      short loc_1802C25EA
0x1802c25ba  movzx   eax, [rbp+50h+Control]
0x1802c25be  xor     r8d, r8d
0x1802c25c1  mov     rcx, [rbp+50h+Sacl]
0x1802c25c5  and     eax, 2000h
0x1802c25ca  shl     eax, 11h
0x1802c25cd  or      ebx, eax
0x1802c25cf  lea     edx, [r8+11h]
0x1802c25d3  or      ebx, 8
0x1802c25d6  call    cs:__imp_RtlFindAceByType
0x1802c25dd  nop     dword ptr [rax+rax+00h]
0x1802c25e2  test    rax, rax
0x1802c25e5  jz      short loc_1802C25EA
0x1802c25e7  or      ebx, 10h
0x1802c25ea  mov     rcx, [rbp+50h+Sacl]
0x1802c25ee  mov     r8d, ebx
0x1802c25f1  mov     rax, [rsi]
0x1802c25f4  mov     edx, [rdi]
0x1802c25f6  mov     r9, [rbp+50h+Owner]
0x1802c25fa  mov     [rsp+150h+var_120], rcx
0x1802c25ff  mov     rcx, [rbp+50h+Dacl]
0x1802c2603  mov     rax, [rax+28h]
0x1802c2607  mov     [rsp+150h+var_128], rcx
0x1802c260c  mov     rcx, [rbp+50h+Group]
0x1802c2610  shr     edx, 6
0x1802c2613  mov     [rsp+150h+var_130], rcx
0x1802c2618  and     edx, r13d
0x1802c261b  mov     rcx, rsi
0x1802c261e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c2623  test    eax, eax
0x1802c2625  js      loc_1802C26B4
0x1802c262b  test    [rdi], r13b
0x1802c262e  jz      short loc_1802C2646
0x1802c2630  mov     rax, [rsi]
0x1802c2633  mov     rcx, rsi
0x1802c2636  mov     edx, [rdi+4]
0x1802c2639  mov     rax, [rax+50h]
0x1802c263d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c2642  test    eax, eax
0x1802c2644  js      short loc_1802C26B4
0x1802c2646  test    byte ptr [rdi], 4
0x1802c2649  jz      short loc_1802C2682
0x1802c264b  mov     [rsp+150h+var_F0], 9E2h
0x1802c2654  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c265b  mov     [rsp+150h+var_100], rax
0x1802c2660  lea     rdx, [rsp+150h+var_100]
0x1802c2665  lea     rax, aPoqsilsetfilei; "PoqSilSetFileInformation"
0x1802c266c  mov     [rsp+150h+var_F8], rax
0x1802c2671  lea     rax, aOperationFlags; "Operation->Flags"
0x1802c2678  mov     [rsp+150h+var_E8], rax
0x1802c267d  jmp     loc_1802C21F9
  ... truncated ...
```
