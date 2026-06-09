# NlGetNt4TrustedDomainList(ushort *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID *,_DS_DOMAIN_TRUSTSW * *,ulong *,ulong *)

- ea: `0x180088690`
- end: `0x1800889ec`
- name: `?NlGetNt4TrustedDomainList@@YAJPEAGPEAU_UNICODE_STRING@@1PEAXPEAU_GUID@@PEAPEAU_DS_DOMAIN_TRUSTSW@@PEAK5@Z`
- size: `860`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, struct _UNICODE_STRING *@<rdx>, struct _UNICODE_STRING *@<r8>, void *@<r9>, struct _GUID *, struct _DS_DOMAIN_TRUSTSW **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006e50c`

## callees

- `0x180018f68`
- `0x180088374`
- `0x180088690`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180088710`
- `ntdll!RtlInitUnicodeString` at `0x180088710`
- `netutils!NetApiBufferFree` at `0x1800889b4`
- `netutils!NetApiBufferFree` at `0x1800889b4`
- `api-ms-win-security-lsalookup-l2-1-0!LsaEnumerateTrustedDomains` at `0x1800888a1`
- `api-ms-win-security-lsalookup-l2-1-0!LsaEnumerateTrustedDomains` at `0x1800888a1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180088747`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180088747`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800887a2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800887a2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180088876`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18008899f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800889c9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180088876`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18008899f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800889c9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180088989`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180088989`

## pseudocode

```c
__int64 __fastcall NlGetNt4TrustedDomainList(
        PCWSTR SourceString,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        void *a4,
        struct _GUID *a5,
        struct _DS_DOMAIN_TRUSTSW **a6,
        unsigned int *a7,
        unsigned int *CountReturned)
{
  unsigned int *v8; // rsi
  NTSTATUS v12; // eax
  int v13; // ebx
  NTSTATUS v14; // eax
  struct _GUID *v15; // rax
  char v16; // r15
  NTSTATUS v17; // eax
  unsigned int i; // edi
  unsigned int v20; // [rsp+60h] [rbp-91h] BYREF
  ULONG EnumerationContext; // [rsp+64h] [rbp-8Dh] BYREF
  PVOID PolicyHandle; // [rsp+68h] [rbp-89h] BYREF
  PVOID v23; // [rsp+70h] [rbp-81h] BYREF
  PVOID Buffer; // [rsp+78h] [rbp-79h] BYREF
  struct _DS_DOMAIN_TRUSTSW *v25; // [rsp+80h] [rbp-71h] BYREF
  LPVOID v26; // [rsp+88h] [rbp-69h] BYREF
  __int128 v27; // [rsp+90h] [rbp-61h]
  __int64 v28; // [rsp+A0h] [rbp-51h]
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-49h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-39h] BYREF

  v8 = CountReturned;
  PolicyHandle = 0;
  *CountReturned = 0;
  *a7 = 0;
  *a6 = 0;
  EnumerationContext = 0;
  DestinationString = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v23 = 0;
  v28 = 0;
  v25 = 0;
  v27 = 0;
  v20 = 0;
  v26 = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v12 = LsaOpenPolicy((PLSA_UNICODE_STRING)&DestinationString, &ObjectAttributes, 1u, &PolicyHandle);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_77890e3e29a538987c36ac046a982df3_Traceguids,
        (unsigned int)v12);
    PolicyHandle = 0;
    goto LABEL_32;
  }
  if ( a2 )
  {
    v15 = a5;
  }
  else
  {
    v14 = LsaQueryInformationPolicy(PolicyHandle, PolicyPrimaryDomainInformation, &Buffer);
    a3 = 0;
    v13 = v14;
    if ( v14 < 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          &WPP_77890e3e29a538987c36ac046a982df3_Traceguids,
          (unsigned int)v14);
      goto LABEL_30;
    }
    a2 = (struct _UNICODE_STRING *)Buffer;
    v15 = 0;
    a4 = (void *)*((_QWORD *)Buffer + 2);
  }
  v13 = NlAllocateForestTrustListEntry((struct _BUFFER_DESCRIPTOR *)&v26, a2, a3, 8, 0, 1u, 0, a4, v15, &v20, &v25);
  if ( v13 < 0 )
    goto LABEL_30;
  v16 = 0;
  *a7 += v20;
  ++*v8;
  EnumerationContext = 0;
  while ( 1 )
  {
    LODWORD(CountReturned) = 0;
    if ( v23 )
      LsaFreeMemory(v23);
    v17 = LsaEnumerateTrustedDomains(PolicyHandle, &EnumerationContext, &v23, 0xFFFFFFFF, (PULONG)&CountReturned);
    v13 = v17;
    if ( v17 == -2147483622 )
    {
      v16 = 1;
      goto LABEL_20;
    }
    if ( v17 < 0 )
      break;
LABEL_20:
    for ( i = 0; i < (unsigned int)CountReturned; ++i )
    {
      v13 = NlAllocateForestTrustListEntry(
              (struct _BUFFER_DESCRIPTOR *)&v26,
              (struct _UNICODE_STRING *)((char *)v23 + 24 * i),
              0,
              2,
              0,
              1u,
              0,
              *((PSID *)v23 + 3 * i + 2),
              0,
              &v20,
              &v25);
      if ( v13 < 0 )
        goto LABEL_30;
      *a7 += v20;
      ++*v8;
    }
    if ( v16 )
    {
      v13 = 0;
      *a6 = (struct _DS_DOMAIN_TRUSTSW *)v26;
      v26 = 0;
      goto LABEL_30;
    }
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_77890e3e29a538987c36ac046a982df3_Traceguids,
      (unsigned int)v17);
  v23 = 0;
LABEL_30:
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
LABEL_32:
  if ( v23 )
    LsaFreeMemory(v23);
  if ( v26 )
    NetApiBufferFree(v26);
  if ( Buffer )
    LsaFreeMemory(Buffer);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180088690  push    rbp
0x180088692  push    rbx
0x180088693  push    rsi
0x180088694  push    rdi
0x180088695  push    r12
0x180088697  push    r13
0x180088699  push    r14
0x18008869b  push    r15
0x18008869d  lea     rbp, [rsp-7]
0x1800886a2  sub     rsp, 0F8h
0x1800886a9  mov     rsi, qword ptr [rbp+3Fh+arg_38]
0x1800886b0  xor     ebx, ebx
0x1800886b2  mov     r14, [rbp+3Fh+arg_30]
0x1800886b6  xorps   xmm1, xmm1
0x1800886b9  mov     r13, [rbp+3Fh+arg_28]
0x1800886bd  xorps   xmm0, xmm0
0x1800886c0  mov     rdi, rdx
0x1800886c3  mov     [rsp+130h+PolicyHandle], rbx
0x1800886c8  mov     rdx, rcx; SourceString
0x1800886cb  mov     [rsi], ebx
0x1800886cd  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1800886d1  mov     [r14], ebx
0x1800886d4  mov     [r13+0], rbx
0x1800886d8  mov     r15, r9
0x1800886db  mov     r12, r8
0x1800886de  mov     [rsp+130h+EnumerationContext], ebx
0x1800886e2  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x1800886e6  mov     [rbp+3Fh+Buffer], rbx
0x1800886ea  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm1
0x1800886ee  mov     [rsp+130h+var_C0], rbx
0x1800886f3  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm1
0x1800886f7  mov     [rbp+3Fh+var_90], rbx
0x1800886fb  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm1
0x1800886ff  mov     [rbp+3Fh+var_B0], rbx
0x180088703  movdqu  [rbp+3Fh+var_A0], xmm0
0x180088708  mov     [rsp+130h+var_D0], ebx
0x18008870c  mov     [rbp+3Fh+var_A8], rbx
0x180088710  call    cs:__imp_RtlInitUnicodeString
0x180088717  nop     dword ptr [rax+rax+00h]
0x18008871c  xorps   xmm0, xmm0
0x18008871f  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x180088726  lea     r9, [rsp+130h+PolicyHandle]; PolicyHandle
0x18008872b  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rbx
0x18008872f  lea     r8d, [rbx+1]; DesiredAccess
0x180088733  mov     [rbp+3Fh+ObjectAttributes.Attributes], ebx
0x180088736  lea     rdx, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x18008873a  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rbx
0x18008873e  lea     rcx, [rbp+3Fh+DestinationString]; SystemName
0x180088742  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180088747  call    cs:__imp_LsaOpenPolicy
0x18008874e  nop     dword ptr [rax+rax+00h]
0x180088753  mov     ebx, eax
0x180088755  test    eax, eax
0x180088757  jns     short loc_180088791
0x180088759  mov     rcx, cs:WPP_GLOBAL_Control
0x180088760  test    byte ptr [rcx+1Ch], 10h
0x180088764  jz      short loc_180088784
0x180088766  cmp     byte ptr [rcx+19h], 2
0x18008876a  jb      short loc_180088784
0x18008876c  mov     rcx, [rcx+10h]
0x180088770  lea     r8, WPP_77890e3e29a538987c36ac046a982df3_Traceguids
0x180088777  mov     edx, 0Ah
0x18008877c  mov     r9d, eax
0x18008877f  call    WPP_SF_d
0x180088784  xor     r12d, r12d
0x180088787  mov     [rsp+130h+PolicyHandle], r12
0x18008878c  jmp     loc_180088995
0x180088791  test    rdi, rdi
0x180088794  jnz     short loc_1800887F9
0x180088796  mov     rcx, [rsp+130h+PolicyHandle]; PolicyHandle
0x18008879b  lea     r8, [rbp+3Fh+Buffer]; Buffer
0x18008879f  lea     edx, [rdi+3]; InformationClass
0x1800887a2  call    cs:__imp_LsaQueryInformationPolicy
0x1800887a9  nop     dword ptr [rax+rax+00h]
0x1800887ae  xor     r12d, r12d
0x1800887b1  mov     ebx, eax
0x1800887b3  test    eax, eax
0x1800887b5  jns     short loc_1800887ED
0x1800887b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800887be  test    byte ptr [rcx+1Ch], 10h
0x1800887c2  jz      loc_18008897F
0x1800887c8  cmp     byte ptr [rcx+19h], 2
0x1800887cc  jb      loc_18008897F
0x1800887d2  mov     rcx, [rcx+10h]
0x1800887d6  lea     edx, [rdi+0Bh]
0x1800887d9  mov     r9d, eax
0x1800887dc  lea     r8, WPP_77890e3e29a538987c36ac046a982df3_Traceguids
0x1800887e3  call    WPP_SF_d
0x1800887e8  jmp     loc_18008897F
0x1800887ed  mov     rdi, [rbp+3Fh+Buffer]
0x1800887f1  xor     eax, eax
0x1800887f3  mov     r15, [rdi+10h]
0x1800887f7  jmp     short loc_1800887FD
0x1800887f9  mov     rax, [rbp+3Fh+arg_20]
0x1800887fd  lea     rcx, [rbp+3Fh+var_B0]
0x180088801  mov     r9d, 8; unsigned int
0x180088807  mov     [rsp+130h+var_E0], rcx; struct _DS_DOMAIN_TRUSTSW **
0x18008880c  mov     r8, r12; struct _UNICODE_STRING *
0x18008880f  lea     rcx, [rsp+130h+var_D0]
0x180088814  mov     rdx, rdi; struct _UNICODE_STRING *
0x180088817  mov     [rsp+130h+var_E8], rcx; unsigned int *
0x18008881c  lea     rcx, [rbp+3Fh+var_A8]; struct _BUFFER_DESCRIPTOR *
0x180088820  mov     [rsp+130h+var_F0], rax; struct _GUID *
0x180088825  mov     [rsp+130h+Sid], r15; Sid
0x18008882a  mov     [rsp+130h+var_100], 0; unsigned int
0x180088832  mov     [rsp+130h+var_108], 1; unsigned int
0x18008883a  mov     dword ptr [rsp+130h+CountReturned], 0; unsigned int
0x180088842  call    ?NlAllocateForestTrustListEntry@@YAJPEAU_BUFFER_DESCRIPTOR@@PEAU_UNICODE_STRING@@1KKKKPEAXPEAU_GUID@@PEAKPEAPEAU_DS_DOMAIN_TRUSTSW@@@Z; NlAllocateForestTrustListEntry(_BUFFER_DESCRIPTOR *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,ulong,ulong,void *,_GUID *,ulong *,_DS_DOMAIN_TRUSTSW * *)
0x180088847  xor     r12d, r12d
0x18008884a  mov     ebx, eax
0x18008884c  test    eax, eax
0x18008884e  js      loc_18008897F
0x180088854  mov     eax, [rsp+130h+var_D0]
0x180088858  mov     r15b, r12b
0x18008885b  add     [r14], eax
0x18008885e  inc     dword ptr [rsi]
0x180088860  mov     [rsp+130h+EnumerationContext], r12d
0x180088865  mov     rcx, [rsp+130h+var_C0]; Buffer
0x18008886a  mov     [rbp+3Fh+arg_38], r12d
0x180088871  test    rcx, rcx
0x180088874  jz      short loc_180088882
0x180088876  call    cs:__imp_LsaFreeMemory
0x18008887d  nop     dword ptr [rax+rax+00h]
0x180088882  mov     rcx, [rsp+130h+PolicyHandle]; PolicyHandle
0x180088887  lea     rax, [rbp+3Fh+arg_38]
0x18008888e  or      r9d, 0FFFFFFFFh; PreferedMaximumLength
0x180088892  mov     [rsp+130h+CountReturned], rax; CountReturned
0x180088897  lea     r8, [rsp+130h+var_C0]; Buffer
0x18008889c  lea     rdx, [rsp+130h+EnumerationContext]; EnumerationContext
0x1800888a1  call    cs:__imp_LsaEnumerateTrustedDomains
0x1800888a8  nop     dword ptr [rax+rax+00h]
0x1800888ad  mov     ebx, eax
0x1800888af  cmp     eax, 8000001Ah
0x1800888b4  jnz     short loc_1800888BB
0x1800888b6  mov     r15b, 1
0x1800888b9  jmp     short loc_1800888C3
0x1800888bb  test    eax, eax
0x1800888bd  js      loc_18008894F
0x1800888c3  mov     edi, r12d
0x1800888c6  cmp     edi, [rbp+3Fh+arg_38]
0x1800888cc  jnb     short loc_180088935
0x1800888ce  mov     eax, edi
0x1800888d0  mov     r9d, 2; unsigned int
0x1800888d6  xor     r8d, r8d; struct _UNICODE_STRING *
0x1800888d9  lea     rcx, [rax+rax*2]
0x1800888dd  mov     rax, [rsp+130h+var_C0]
0x1800888e2  lea     rdx, [rax+rcx*8]; struct _UNICODE_STRING *
0x1800888e6  lea     rax, [rbp+3Fh+var_B0]
0x1800888ea  mov     [rsp+130h+var_E0], rax; struct _DS_DOMAIN_TRUSTSW **
0x1800888ef  lea     rcx, [rbp+3Fh+var_A8]; struct _BUFFER_DESCRIPTOR *
0x1800888f3  lea     rax, [rsp+130h+var_D0]
0x1800888f8  mov     [rsp+130h+var_E8], rax; unsigned int *
0x1800888fd  mov     rax, [rdx+10h]
0x180088901  mov     [rsp+130h+var_F0], r12; struct _GUID *
0x180088906  mov     [rsp+130h+Sid], rax; Sid
0x18008890b  mov     [rsp+130h+var_100], r12d; unsigned int
0x180088910  mov     [rsp+130h+var_108], 1; unsigned int
0x180088918  mov     dword ptr [rsp+130h+CountReturned], r12d; unsigned int
0x18008891d  call    ?NlAllocateForestTrustListEntry@@YAJPEAU_BUFFER_DESCRIPTOR@@PEAU_UNICODE_STRING@@1KKKKPEAXPEAU_GUID@@PEAKPEAPEAU_DS_DOMAIN_TRUSTSW@@@Z; NlAllocateForestTrustListEntry(_BUFFER_DESCRIPTOR *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,ulong,ulong,void *,_GUID *,ulong *,_DS_DOMAIN_TRUSTSW * *)
0x180088922  mov     ebx, eax
0x180088924  test    eax, eax
0x180088926  js      short loc_18008897F
0x180088928  mov     eax, [rsp+130h+var_D0]
0x18008892c  add     [r14], eax
0x18008892f  inc     dword ptr [rsi]
0x180088931  inc     edi
0x180088933  jmp     short loc_1800888C6
0x180088935  test    r15b, r15b
0x180088938  jz      loc_180088865
0x18008893e  mov     rax, [rbp+3Fh+var_A8]
0x180088942  mov     ebx, r12d
0x180088945  mov     [r13+0], rax
0x180088949  mov     [rbp+3Fh+var_A8], r12
0x18008894d  jmp     short loc_18008897F
0x18008894f  mov     rcx, cs:WPP_GLOBAL_Control
0x180088956  test    byte ptr [rcx+1Ch], 10h
0x18008895a  jz      short loc_18008897A
0x18008895c  cmp     byte ptr [rcx+19h], 2
0x180088960  jb      short loc_18008897A
0x180088962  mov     rcx, [rcx+10h]
0x180088966  lea     r8, WPP_77890e3e29a538987c36ac046a982df3_Traceguids
0x18008896d  mov     edx, 0Ch
0x180088972  mov     r9d, eax
0x180088975  call    WPP_SF_d
0x18008897a  mov     [rsp+130h+var_C0], r12
0x18008897f  mov     rcx, [rsp+130h+PolicyHandle]; ObjectHandle
0x180088984  test    rcx, rcx
0x180088987  jz      short loc_180088995
0x180088989  call    cs:__imp_LsaClose
0x180088990  nop     dword ptr [rax+rax+00h]
0x180088995  mov     rcx, [rsp+130h+var_C0]; Buffer
0x18008899a  test    rcx, rcx
0x18008899d  jz      short loc_1800889AB
0x18008899f  call    cs:__imp_LsaFreeMemory
0x1800889a6  nop     dword ptr [rax+rax+00h]
0x1800889ab  mov     rcx, [rbp+3Fh+var_A8]; Buffer
0x1800889af  test    rcx, rcx
0x1800889b2  jz      short loc_1800889C0
0x1800889b4  call    cs:__imp_NetApiBufferFree
0x1800889bb  nop     dword ptr [rax+rax+00h]
0x1800889c0  mov     rcx, [rbp+3Fh+Buffer]; Buffer
0x1800889c4  test    rcx, rcx
0x1800889c7  jz      short loc_1800889D5
0x1800889c9  call    cs:__imp_LsaFreeMemory
0x1800889d0  nop     dword ptr [rax+rax+00h]
0x1800889d5  mov     eax, ebx
0x1800889d7  add     rsp, 0F8h
0x1800889de  pop     r15
0x1800889e0  pop     r14
0x1800889e2  pop     r13
0x1800889e4  pop     r12
0x1800889e6  pop     rdi
0x1800889e7  pop     rsi
0x1800889e8  pop     rbx
0x1800889e9  pop     rbp
0x1800889ea  retn
```
