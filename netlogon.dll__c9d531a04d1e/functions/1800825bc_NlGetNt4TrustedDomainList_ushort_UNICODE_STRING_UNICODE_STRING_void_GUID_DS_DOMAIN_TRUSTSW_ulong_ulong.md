# NlGetNt4TrustedDomainList(ushort *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID *,_DS_DOMAIN_TRUSTSW * *,ulong *,ulong *)

- ea: `0x1800825bc`
- end: `0x1800828e1`
- name: `?NlGetNt4TrustedDomainList@@YAJPEAGPEAU_UNICODE_STRING@@1PEAXPEAU_GUID@@PEAPEAU_DS_DOMAIN_TRUSTSW@@PEAK5@Z`
- size: `805`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, struct _UNICODE_STRING *@<rdx>, struct _UNICODE_STRING *@<r8>, void *@<r9>, struct _GUID *, struct _DS_DOMAIN_TRUSTSW **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180069580`

## callees

- `0x18001843c`
- `0x1800822bc`
- `0x1800825bc`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18008263c`
- `ntdll!RtlInitUnicodeString` at `0x18008263c`
- `netutils!NetApiBufferFree` at `0x1800828b6`
- `netutils!NetApiBufferFree` at `0x1800828b6`
- `api-ms-win-security-lsalookup-l2-1-0!LsaEnumerateTrustedDomains` at `0x1800827b5`
- `api-ms-win-security-lsalookup-l2-1-0!LsaEnumerateTrustedDomains` at `0x1800827b5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18008266d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18008266d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800826c2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800826c2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180082790`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800828a7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800828c5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180082790`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800828a7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800828c5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180082897`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180082897`

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
0x1800825bc  push    rbp
0x1800825be  push    rbx
0x1800825bf  push    rsi
0x1800825c0  push    rdi
0x1800825c1  push    r12
0x1800825c3  push    r13
0x1800825c5  push    r14
0x1800825c7  push    r15
0x1800825c9  lea     rbp, [rsp-7]
0x1800825ce  sub     rsp, 0F8h
0x1800825d5  mov     rsi, qword ptr [rbp+3Fh+arg_38]
0x1800825dc  xor     ebx, ebx
0x1800825de  mov     r14, [rbp+3Fh+arg_30]
0x1800825e2  xorps   xmm1, xmm1
0x1800825e5  mov     r13, [rbp+3Fh+arg_28]
0x1800825e9  xorps   xmm0, xmm0
0x1800825ec  mov     rdi, rdx
0x1800825ef  mov     [rsp+130h+PolicyHandle], rbx
0x1800825f4  mov     rdx, rcx; SourceString
0x1800825f7  mov     [rsi], ebx
0x1800825f9  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1800825fd  mov     [r14], ebx
0x180082600  mov     [r13+0], rbx
0x180082604  mov     r15, r9
0x180082607  mov     r12, r8
0x18008260a  mov     [rsp+130h+EnumerationContext], ebx
0x18008260e  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x180082612  mov     [rbp+3Fh+Buffer], rbx
0x180082616  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm1
0x18008261a  mov     [rsp+130h+var_C0], rbx
0x18008261f  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm1
0x180082623  mov     [rbp+3Fh+var_90], rbx
0x180082627  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm1
0x18008262b  mov     [rbp+3Fh+var_B0], rbx
0x18008262f  movdqu  [rbp+3Fh+var_A0], xmm0
0x180082634  mov     [rsp+130h+var_D0], ebx
0x180082638  mov     [rbp+3Fh+var_A8], rbx
0x18008263c  call    cs:__imp_RtlInitUnicodeString
0x180082642  xorps   xmm0, xmm0
0x180082645  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x18008264c  lea     r9, [rsp+130h+PolicyHandle]; PolicyHandle
0x180082651  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rbx
0x180082655  lea     r8d, [rbx+1]; DesiredAccess
0x180082659  mov     [rbp+3Fh+ObjectAttributes.Attributes], ebx
0x18008265c  lea     rdx, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x180082660  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rbx
0x180082664  lea     rcx, [rbp+3Fh+DestinationString]; SystemName
0x180082668  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18008266d  call    cs:__imp_LsaOpenPolicy
0x180082673  mov     ebx, eax
0x180082675  test    eax, eax
0x180082677  jns     short loc_1800826B1
0x180082679  mov     rcx, cs:WPP_GLOBAL_Control
0x180082680  test    byte ptr [rcx+1Ch], 10h
0x180082684  jz      short loc_1800826A4
0x180082686  cmp     byte ptr [rcx+19h], 2
0x18008268a  jb      short loc_1800826A4
0x18008268c  mov     rcx, [rcx+10h]
0x180082690  lea     r8, WPP_77890e3e29a538987c36ac046a982df3_Traceguids
0x180082697  mov     edx, 0Ah
0x18008269c  mov     r9d, eax
0x18008269f  call    WPP_SF_d
0x1800826a4  xor     r12d, r12d
0x1800826a7  mov     [rsp+130h+PolicyHandle], r12
0x1800826ac  jmp     loc_18008289D
0x1800826b1  test    rdi, rdi
0x1800826b4  jnz     short loc_180082713
0x1800826b6  mov     rcx, [rsp+130h+PolicyHandle]; PolicyHandle
0x1800826bb  lea     r8, [rbp+3Fh+Buffer]; Buffer
0x1800826bf  lea     edx, [rdi+3]; InformationClass
0x1800826c2  call    cs:__imp_LsaQueryInformationPolicy
0x1800826c8  xor     r12d, r12d
0x1800826cb  mov     ebx, eax
0x1800826cd  test    eax, eax
0x1800826cf  jns     short loc_180082707
0x1800826d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800826d8  test    byte ptr [rcx+1Ch], 10h
0x1800826dc  jz      loc_18008288D
0x1800826e2  cmp     byte ptr [rcx+19h], 2
0x1800826e6  jb      loc_18008288D
0x1800826ec  mov     rcx, [rcx+10h]
0x1800826f0  lea     edx, [rdi+0Bh]
0x1800826f3  mov     r9d, eax
0x1800826f6  lea     r8, WPP_77890e3e29a538987c36ac046a982df3_Traceguids
0x1800826fd  call    WPP_SF_d
0x180082702  jmp     loc_18008288D
0x180082707  mov     rdi, [rbp+3Fh+Buffer]
0x18008270b  xor     eax, eax
0x18008270d  mov     r15, [rdi+10h]
0x180082711  jmp     short loc_180082717
0x180082713  mov     rax, [rbp+3Fh+arg_20]
0x180082717  lea     rcx, [rbp+3Fh+var_B0]
0x18008271b  mov     r9d, 8; unsigned int
0x180082721  mov     [rsp+130h+var_E0], rcx; struct _DS_DOMAIN_TRUSTSW **
0x180082726  mov     r8, r12; struct _UNICODE_STRING *
0x180082729  lea     rcx, [rsp+130h+var_D0]
0x18008272e  mov     rdx, rdi; struct _UNICODE_STRING *
0x180082731  mov     [rsp+130h+var_E8], rcx; unsigned int *
0x180082736  lea     rcx, [rbp+3Fh+var_A8]; struct _BUFFER_DESCRIPTOR *
0x18008273a  mov     [rsp+130h+var_F0], rax; struct _GUID *
0x18008273f  mov     [rsp+130h+Sid], r15; Sid
0x180082744  mov     [rsp+130h+var_100], 0; unsigned int
0x18008274c  mov     [rsp+130h+var_108], 1; unsigned int
0x180082754  mov     dword ptr [rsp+130h+CountReturned], 0; unsigned int
0x18008275c  call    ?NlAllocateForestTrustListEntry@@YAJPEAU_BUFFER_DESCRIPTOR@@PEAU_UNICODE_STRING@@1KKKKPEAXPEAU_GUID@@PEAKPEAPEAU_DS_DOMAIN_TRUSTSW@@@Z; NlAllocateForestTrustListEntry(_BUFFER_DESCRIPTOR *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,ulong,ulong,void *,_GUID *,ulong *,_DS_DOMAIN_TRUSTSW * *)
0x180082761  xor     r12d, r12d
0x180082764  mov     ebx, eax
0x180082766  test    eax, eax
0x180082768  js      loc_18008288D
0x18008276e  mov     eax, [rsp+130h+var_D0]
0x180082772  mov     r15b, r12b
0x180082775  add     [r14], eax
0x180082778  inc     dword ptr [rsi]
0x18008277a  mov     [rsp+130h+EnumerationContext], r12d
0x18008277f  mov     rcx, [rsp+130h+var_C0]; Buffer
0x180082784  mov     [rbp+3Fh+arg_38], r12d
0x18008278b  test    rcx, rcx
0x18008278e  jz      short loc_180082796
0x180082790  call    cs:__imp_LsaFreeMemory
0x180082796  mov     rcx, [rsp+130h+PolicyHandle]; PolicyHandle
0x18008279b  lea     rax, [rbp+3Fh+arg_38]
0x1800827a2  or      r9d, 0FFFFFFFFh; PreferedMaximumLength
0x1800827a6  mov     [rsp+130h+CountReturned], rax; CountReturned
0x1800827ab  lea     r8, [rsp+130h+var_C0]; Buffer
0x1800827b0  lea     rdx, [rsp+130h+EnumerationContext]; EnumerationContext
0x1800827b5  call    cs:__imp_LsaEnumerateTrustedDomains
0x1800827bb  mov     ebx, eax
0x1800827bd  cmp     eax, 8000001Ah
0x1800827c2  jnz     short loc_1800827C9
0x1800827c4  mov     r15b, 1
0x1800827c7  jmp     short loc_1800827D1
0x1800827c9  test    eax, eax
0x1800827cb  js      loc_18008285D
0x1800827d1  mov     edi, r12d
0x1800827d4  cmp     edi, [rbp+3Fh+arg_38]
0x1800827da  jnb     short loc_180082843
0x1800827dc  mov     eax, edi
0x1800827de  mov     r9d, 2; unsigned int
0x1800827e4  xor     r8d, r8d; struct _UNICODE_STRING *
0x1800827e7  lea     rcx, [rax+rax*2]
0x1800827eb  mov     rax, [rsp+130h+var_C0]
0x1800827f0  lea     rdx, [rax+rcx*8]; struct _UNICODE_STRING *
0x1800827f4  lea     rax, [rbp+3Fh+var_B0]
0x1800827f8  mov     [rsp+130h+var_E0], rax; struct _DS_DOMAIN_TRUSTSW **
0x1800827fd  lea     rcx, [rbp+3Fh+var_A8]; struct _BUFFER_DESCRIPTOR *
0x180082801  lea     rax, [rsp+130h+var_D0]
0x180082806  mov     [rsp+130h+var_E8], rax; unsigned int *
0x18008280b  mov     rax, [rdx+10h]
0x18008280f  mov     [rsp+130h+var_F0], r12; struct _GUID *
0x180082814  mov     [rsp+130h+Sid], rax; Sid
0x180082819  mov     [rsp+130h+var_100], r12d; unsigned int
0x18008281e  mov     [rsp+130h+var_108], 1; unsigned int
0x180082826  mov     dword ptr [rsp+130h+CountReturned], r12d; unsigned int
0x18008282b  call    ?NlAllocateForestTrustListEntry@@YAJPEAU_BUFFER_DESCRIPTOR@@PEAU_UNICODE_STRING@@1KKKKPEAXPEAU_GUID@@PEAKPEAPEAU_DS_DOMAIN_TRUSTSW@@@Z; NlAllocateForestTrustListEntry(_BUFFER_DESCRIPTOR *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,ulong,ulong,void *,_GUID *,ulong *,_DS_DOMAIN_TRUSTSW * *)
0x180082830  mov     ebx, eax
0x180082832  test    eax, eax
0x180082834  js      short loc_18008288D
0x180082836  mov     eax, [rsp+130h+var_D0]
0x18008283a  add     [r14], eax
0x18008283d  inc     dword ptr [rsi]
0x18008283f  inc     edi
0x180082841  jmp     short loc_1800827D4
0x180082843  test    r15b, r15b
0x180082846  jz      loc_18008277F
0x18008284c  mov     rax, [rbp+3Fh+var_A8]
0x180082850  mov     ebx, r12d
0x180082853  mov     [r13+0], rax
0x180082857  mov     [rbp+3Fh+var_A8], r12
0x18008285b  jmp     short loc_18008288D
0x18008285d  mov     rcx, cs:WPP_GLOBAL_Control
0x180082864  test    byte ptr [rcx+1Ch], 10h
0x180082868  jz      short loc_180082888
0x18008286a  cmp     byte ptr [rcx+19h], 2
0x18008286e  jb      short loc_180082888
0x180082870  mov     rcx, [rcx+10h]
0x180082874  lea     r8, WPP_77890e3e29a538987c36ac046a982df3_Traceguids
0x18008287b  mov     edx, 0Ch
0x180082880  mov     r9d, eax
0x180082883  call    WPP_SF_d
0x180082888  mov     [rsp+130h+var_C0], r12
0x18008288d  mov     rcx, [rsp+130h+PolicyHandle]; ObjectHandle
0x180082892  test    rcx, rcx
0x180082895  jz      short loc_18008289D
0x180082897  call    cs:__imp_LsaClose
0x18008289d  mov     rcx, [rsp+130h+var_C0]; Buffer
0x1800828a2  test    rcx, rcx
0x1800828a5  jz      short loc_1800828AD
0x1800828a7  call    cs:__imp_LsaFreeMemory
0x1800828ad  mov     rcx, [rbp+3Fh+var_A8]; Buffer
0x1800828b1  test    rcx, rcx
0x1800828b4  jz      short loc_1800828BC
0x1800828b6  call    cs:__imp_NetApiBufferFree
0x1800828bc  mov     rcx, [rbp+3Fh+Buffer]; Buffer
0x1800828c0  test    rcx, rcx
0x1800828c3  jz      short loc_1800828CB
0x1800828c5  call    cs:__imp_LsaFreeMemory
0x1800828cb  mov     eax, ebx
0x1800828cd  add     rsp, 0F8h
0x1800828d4  pop     r15
0x1800828d6  pop     r14
0x1800828d8  pop     r13
0x1800828da  pop     r12
0x1800828dc  pop     rdi
0x1800828dd  pop     rsi
0x1800828de  pop     rbx
0x1800828df  pop     rbp
0x1800828e0  retn
```
