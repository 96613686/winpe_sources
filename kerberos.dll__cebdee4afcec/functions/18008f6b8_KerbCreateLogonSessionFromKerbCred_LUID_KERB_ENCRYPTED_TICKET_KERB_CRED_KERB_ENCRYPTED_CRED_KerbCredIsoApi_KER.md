# KerbCreateLogonSessionFromKerbCred(_LUID *,KERB_ENCRYPTED_TICKET *,KERB_CRED *,KERB_ENCRYPTED_CRED *,KerbCredIsoApi *,_KERB_LOGON_SESSION * *)

- ea: `0x18008f6b8`
- end: `0x18008f96a`
- name: `?KerbCreateLogonSessionFromKerbCred@@YAJPEAU_LUID@@PEAUKERB_ENCRYPTED_TICKET@@PEAUKERB_CRED@@PEAUKERB_ENCRYPTED_CRED@@PEAVKerbCredIsoApi@@PEAPEAU_KERB_LOGON_SESSION@@@Z`
- size: `690`
- prototype: `__int64 __usercall@<rax>(struct _LUID *@<rcx>, struct KERB_ENCRYPTED_TICKET *@<rdx>, struct KERB_CRED *@<r8>, struct KERB_ENCRYPTED_CRED *@<r9>, struct KerbCredIsoApi *, struct _KERB_LOGON_SESSION **)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800816e0`
- `0x1800bfc00`

## callees

- `0x180005aa0`
- `0x1800068d0`
- `0x18000a630`
- `0x180015740`
- `0x1800643dc`
- `0x18008b70c`
- `0x18008f6b8`
- `0x18008f970`
- `0x18008ff1c`
- `0x180090068`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18008f759`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18008f759`
- `ntdll!RtlInitUnicodeString` at `0x18008f774`
- `ntdll!RtlInitUnicodeString` at `0x18008f774`
- `ntdll!RtlEnterCriticalSection` at `0x18008f836`
- `ntdll!RtlEnterCriticalSection` at `0x18008f836`
- `ntdll!RtlLeaveCriticalSection` at `0x18008f91e`
- `ntdll!RtlLeaveCriticalSection` at `0x18008f91e`

## string_xrefs

- `0x18008f708`: `KerbCreateLogonSessionFromKerbCred creating logon session for %#x:%#x\n`
- `0x18008f713`: `KerbCreateLogonSessionFromKerbCred`
- `0x18008f7b1`: `KerbCreateLogonSessionFromKerbCred`
- `0x18008f8ed`: `KerbCreateLogonSessionFromKerbCred`
- `0x18008f8dc`: `Failed to populate ticket caches from KERB_CRED: 0x%x`

## pseudocode

```c
__int64 __fastcall KerbCreateLogonSessionFromKerbCred(
        struct _LUID *a1,
        struct KERB_ENCRYPTED_TICKET *a2,
        struct KERB_CRED *a3,
        struct KERB_ENCRYPTED_CRED *a4,
        struct KerbCredIsoApi *a5,
        struct _KERB_LOGON_SESSION **a6)
{
  char v6; // r12
  int inserted; // ebx
  wchar_t *v10; // rax
  __int128 v11; // xmm6
  struct _KERB_LOGON_SESSION **v12; // r14
  int v13; // eax
  struct _KERB_LOGON_SESSION *v14; // rdi
  char v15; // si
  _OWORD *v16; // rbx
  __int128 v17; // xmm0
  __int64 v18; // xmm1_8
  int v19; // eax
  struct _UNICODE_STRING *v21; // [rsp+38h] [rbp-69h]
  __int64 v22; // [rsp+38h] [rbp-69h]
  __int64 v23; // [rsp+48h] [rbp-59h] BYREF
  int v24; // [rsp+50h] [rbp-51h]
  __int16 v25; // [rsp+54h] [rbp-4Dh]
  struct _UNICODE_STRING v26; // [rsp+58h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-39h] BYREF
  wchar_t *Str[2]; // [rsp+78h] [rbp-29h] BYREF
  __int128 v29[6]; // [rsp+88h] [rbp-19h] BYREF
  int v30; // [rsp+F8h] [rbp+57h] BYREF
  struct _KERB_LOGON_SESSION *v31; // [rsp+100h] [rbp+5Fh] BYREF
  struct KERB_CRED *v32; // [rsp+108h] [rbp+67h]
  struct KERB_ENCRYPTED_CRED *v33; // [rsp+110h] [rbp+6Fh]

  v33 = a4;
  v32 = a3;
  v6 = 0;
  v31 = 0;
  v30 = 0;
  *(_OWORD *)Str = 0;
  DestinationString = 0;
  v26 = 0;
  if ( a1 )
    KerbTracerT::Log(
      10,
      "KerbCreateLogonSessionFromKerbCred",
      2526,
      "KerbCreateLogonSessionFromKerbCred creating logon session for %#x:%#x\n",
      a1->HighPart,
      a1->LowPart);
  if ( (unsigned int)KerbConvertPrincipalNameToString(Str, &v30, (char *)a2 + 56) )
    goto LABEL_4;
  v10 = wcsrchr(Str[1], 0x5Cu);
  v11 = *(_OWORD *)Str;
  if ( v10 )
  {
    DestinationString.Buffer = v10 + 1;
    RtlInitUnicodeString(&DestinationString, v10 + 1);
  }
  else
  {
    DestinationString = *(struct _UNICODE_STRING *)Str;
  }
  if ( (unsigned int)KerbConvertRealmToUnicodeString((__int64)&v26, (const char **)a2 + 6) )
  {
LABEL_4:
    inserted = -1073741670;
    goto LABEL_28;
  }
  KerbTracerT::Log(
    3,
    "KerbCreateLogonSessionFromKerbCred",
    2567,
    "Creating delegation logon session for %wZ \\ %wZ\n",
    &v26,
    &DestinationString);
  v12 = a6;
  if ( *a6 )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)*a6 + 2);
    v14 = *v12;
    v15 = 1;
    v16 = (_OWORD *)((char *)*v12 + 120);
    if ( !*(_WORD *)v16 )
    {
      KerbFreeString((__int64)*v12 + 120);
      Str[1] = 0;
      *v16 = v11;
    }
    if ( !*((_WORD *)v14 + 68) )
    {
      KerbFreeString((__int64)v14 + 136);
      *(struct _UNICODE_STRING *)((char *)v14 + 136) = v26;
      v26.Buffer = 0;
    }
  }
  else
  {
    v13 = KerbAllocateLogonSession(a1, &v31);
    v14 = v31;
    inserted = v13;
    if ( v13 < 0
      || (v21 = (struct _UNICODE_STRING *)((char *)v31 + 120),
          *((union _LARGE_INTEGER *)v31 + 9) = KerbGlobalWillNeverTime,
          inserted = KerbCreatePrimaryCredentials(&DestinationString, &v26, 0, 0, a1, v21),
          inserted < 0) )
    {
LABEL_26:
      if ( v14 )
        KerbDereferenceLogonSession(v14);
      goto LABEL_28;
    }
    *((_DWORD *)v14 + 226) |= 2u;
    v15 = 0;
    v6 = 1;
  }
  v17 = *(_OWORD *)((char *)a2 + 56);
  v18 = *((_QWORD *)a2 + 12);
  v24 = *((_DWORD *)a2 + 26);
  v25 = *((_WORD *)a2 + 54);
  v22 = *((_QWORD *)a2 + 6);
  v29[0] = v17;
  v23 = v18;
  v19 = KerbPopulateTicketCacheFromKerbCred((union _LARGE_INTEGER *)v14, (__int64)v32, (__int64)v33, &v23, a5, v29, v22);
  inserted = v19;
  if ( v19 >= 0 )
  {
    if ( !*v12 )
    {
      inserted = KerbInsertLogonSession(v14);
      if ( inserted >= 0 )
        *v12 = v14;
    }
  }
  else
  {
    KerbTracerT::Log(
      1,
      "KerbCreateLogonSessionFromKerbCred",
      2646,
      "Failed to populate ticket caches from KERB_CRED: 0x%x",
      v19);
  }
  if ( v15 )
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v14 + 2);
  if ( v6 && inserted < 0 )
    goto LABEL_26;
LABEL_28:
  KerbFreeString((__int64)Str);
  KerbFreeString((__int64)&v26);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18008f6b8  mov     rax, rsp
0x18008f6bb  mov     [rax+20h], r9
0x18008f6bf  mov     [rax+18h], r8
0x18008f6c3  push    rbp
0x18008f6c4  push    rbx
0x18008f6c5  push    rsi
0x18008f6c6  push    rdi
0x18008f6c7  push    r12
0x18008f6c9  push    r13
0x18008f6cb  push    r14
0x18008f6cd  push    r15
0x18008f6cf  lea     rbp, [rax-4Fh]
0x18008f6d3  sub     rsp, 0A8h
0x18008f6da  xor     r12d, r12d
0x18008f6dd  movaps  xmmword ptr [rax-58h], xmm6
0x18008f6e1  mov     [rbp+47h+arg_8], r12
0x18008f6e5  xorps   xmm0, xmm0
0x18008f6e8  mov     [rbp+47h+arg_0], r12d
0x18008f6ec  xorps   xmm1, xmm1
0x18008f6ef  mov     r15, rdx
0x18008f6f2  mov     rsi, rcx
0x18008f6f5  movups  xmmword ptr [rbp+47h+Str], xmm0
0x18008f6f9  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm1
0x18008f6fd  movups  xmmword ptr [rbp+47h+var_90.Length], xmm0
0x18008f701  test    rcx, rcx
0x18008f704  jz      short loc_18008F731
0x18008f706  mov     eax, [rcx]
0x18008f708  lea     r9, aKerbcreatelogo_2; "KerbCreateLogonSessionFromKerbCred crea"...
0x18008f70f  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18008f713  lea     rdx, aKerbcreatelogo; "KerbCreateLogonSessionFromKerbCred"
0x18008f71a  mov     eax, [rcx+4]
0x18008f71d  mov     r8d, 9DEh
0x18008f723  lea     ecx, [r12+0Ah]
0x18008f728  mov     [rsp+0E0h+var_C0], eax
0x18008f72c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18008f731  lea     r8, [r15+38h]
0x18008f735  lea     rdx, [rbp+47h+arg_0]
0x18008f739  lea     rcx, [rbp+47h+Str]
0x18008f73d  call    KerbConvertPrincipalNameToString
0x18008f742  test    eax, eax
0x18008f744  jz      short loc_18008F750
0x18008f746  mov     ebx, 0C000009Ah
0x18008f74b  jmp     loc_18008F93A
0x18008f750  mov     rcx, [rbp+47h+Str+8]; Str
0x18008f754  mov     edx, 5Ch ; '\'; Ch
0x18008f759  call    cs:__imp_wcsrchr
0x18008f75f  movaps  xmm6, xmmword ptr [rbp+47h+Str]
0x18008f763  test    rax, rax
0x18008f766  jz      short loc_18008F77C
0x18008f768  lea     rdx, [rax+2]; SourceString
0x18008f76c  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x18008f770  mov     [rbp+47h+DestinationString.Buffer], rdx
0x18008f774  call    cs:__imp_RtlInitUnicodeString
0x18008f77a  jmp     short loc_18008F781
0x18008f77c  movdqa  xmmword ptr [rbp+47h+DestinationString.Length], xmm6
0x18008f781  lea     rdx, [r15+30h]
0x18008f785  lea     rcx, [rbp+47h+var_90]
0x18008f789  call    KerbConvertRealmToUnicodeString
0x18008f78e  test    eax, eax
0x18008f790  jnz     short loc_18008F746
0x18008f792  lea     rax, [rbp+47h+DestinationString]
0x18008f796  mov     r8d, 0A07h
0x18008f79c  mov     [rsp+0E0h+var_B8], rax
0x18008f7a1  lea     r9, aCreatingDelega; "Creating delegation logon session for %"...
0x18008f7a8  lea     rax, [rbp+47h+var_90]
0x18008f7ac  mov     ecx, 3
0x18008f7b1  lea     rdx, aKerbcreatelogo; "KerbCreateLogonSessionFromKerbCred"
0x18008f7b8  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18008f7bd  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18008f7c2  mov     r14, [rbp+47h+arg_28]
0x18008f7c6  mov     rcx, [r14]
0x18008f7c9  test    rcx, rcx
0x18008f7cc  jnz     short loc_18008F832
0x18008f7ce  lea     rdx, [rbp+47h+arg_8]; struct _KERB_LOGON_SESSION **
0x18008f7d2  mov     rcx, rsi; struct _LUID *
0x18008f7d5  call    ?KerbAllocateLogonSession@@YAJPEAU_LUID@@PEAPEAU_KERB_LOGON_SESSION@@@Z; KerbAllocateLogonSession(_LUID *,_KERB_LOGON_SESSION * *)
0x18008f7da  mov     rdi, [rbp+47h+arg_8]
0x18008f7de  mov     ebx, eax
0x18008f7e0  test    eax, eax
0x18008f7e2  js      loc_18008F92D
0x18008f7e8  mov     rax, cs:?KerbGlobalWillNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER KerbGlobalWillNeverTime
0x18008f7ef  lea     rcx, [rdi+78h]
0x18008f7f3  mov     [rsp+30h], rcx; UniDest
0x18008f7f8  lea     rdx, [rbp+47h+var_90]; struct _UNICODE_STRING *
0x18008f7fc  mov     [rsp+0E0h+var_B8], rsi; struct _LUID *
0x18008f801  lea     rcx, [rbp+47h+DestinationString]; struct _UNICODE_STRING *
0x18008f805  xor     r9d, r9d
0x18008f808  mov     [rsp+0E0h+var_C0], r12d; int
0x18008f80d  xor     r8d, r8d; struct _KERB_PLAINTEXT_PASSWORD *
0x18008f810  mov     [rdi+48h], rax
0x18008f814  call    ?KerbCreatePrimaryCredentials@@YAJPEAU_UNICODE_STRING@@0PEAU_KERB_PLAINTEXT_PASSWORD@@0U?$BitMask@W4PasswordFlagBits@@@@PEAU_LUID@@PEAU_KERB_PRIMARY_CREDENTIAL@@@Z; KerbCreatePrimaryCredentials(_UNICODE_STRING *,_UNICODE_STRING *,_KERB_PLAINTEXT_PASSWORD *,_UNICODE_STRING *,BitMask<PasswordFlagBits>,_LUID *,_KERB_PRIMARY_CREDENTIAL *)
0x18008f819  mov     ebx, eax
0x18008f81b  test    eax, eax
0x18008f81d  js      loc_18008F92D
0x18008f823  or      dword ptr [rdi+388h], 2
0x18008f82a  mov     sil, r12b
0x18008f82d  mov     r12b, 1
0x18008f830  jmp     short loc_18008F87F
0x18008f832  add     rcx, 50h ; 'P'; CriticalSection
0x18008f836  call    cs:__imp_RtlEnterCriticalSection
0x18008f83c  mov     rdi, [r14]
0x18008f83f  xor     eax, eax
0x18008f841  mov     sil, 1
0x18008f844  lea     rbx, [rdi+78h]
0x18008f848  cmp     [rbx], ax
0x18008f84b  jnz     short loc_18008F85F
0x18008f84d  mov     rcx, rbx
0x18008f850  call    KerbFreeString
0x18008f855  xor     eax, eax
0x18008f857  mov     [rbp+47h+Str+8], rax
0x18008f85b  movdqu  xmmword ptr [rbx], xmm6
0x18008f85f  lea     rbx, [rdi+88h]
0x18008f866  cmp     [rbx], ax
0x18008f869  jnz     short loc_18008F87F
0x18008f86b  mov     rcx, rbx
0x18008f86e  call    KerbFreeString
0x18008f873  movups  xmm0, xmmword ptr [rbp+47h+var_90.Length]
0x18008f877  movdqu  xmmword ptr [rbx], xmm0
0x18008f87b  mov     [rbp+47h+var_90.Buffer], r12
0x18008f87f  mov     eax, [r15+68h]
0x18008f883  lea     r9, [rbp+47h+var_A0]
0x18008f887  movups  xmm0, xmmword ptr [r15+38h]
0x18008f88c  mov     rcx, rdi
0x18008f88f  mov     r8, [rbp+47h+arg_18]
0x18008f893  movsd   xmm1, qword ptr [r15+60h]
0x18008f899  mov     rdx, [rbp+47h+arg_10]
0x18008f89d  mov     [rbp+47h+var_98], eax
0x18008f8a0  movzx   eax, word ptr [r15+6Ch]
0x18008f8a5  mov     [rbp+47h+var_94], ax
0x18008f8a9  mov     rax, [r15+30h]
0x18008f8ad  mov     [rsp+30h], rax
0x18008f8b2  lea     rax, [rbp+47h+var_60]
0x18008f8b6  mov     [rsp+0E0h+var_B8], rax
0x18008f8bb  mov     rax, [rbp+47h+arg_20]
0x18008f8bf  mov     qword ptr [rsp+0E0h+var_C0], rax
0x18008f8c4  movdqu  [rbp+47h+var_60], xmm0
0x18008f8c9  movsd   [rbp+47h+var_A0], xmm1
0x18008f8ce  call    ?KerbPopulateTicketCacheFromKerbCred@@YAJPEAU_KERB_LOGON_SESSION@@PEAUKERB_CRED@@PEAUKERB_ENCRYPTED_CRED@@UtagASN1generalizedtime_t@@PEAVKerbCredIsoApi@@UKERB_PRINCIPAL_NAME@@PEAD@Z; KerbPopulateTicketCacheFromKerbCred(_KERB_LOGON_SESSION *,KERB_CRED *,KERB_ENCRYPTED_CRED *,tagASN1generalizedtime_t,KerbCredIsoApi *,KERB_PRINCIPAL_NAME,char *)
0x18008f8d3  xor     r15d, r15d
0x18008f8d6  mov     ebx, eax
0x18008f8d8  test    eax, eax
0x18008f8da  jns     short loc_18008F8FF
0x18008f8dc  lea     r9, aFailedToPopula_0; "Failed to populate ticket caches from K"...
0x18008f8e3  mov     [rsp+0E0h+var_C0], eax
0x18008f8e7  mov     r8d, 0A56h
0x18008f8ed  lea     rdx, aKerbcreatelogo; "KerbCreateLogonSessionFromKerbCred"
0x18008f8f4  lea     ecx, [r15+1]
0x18008f8f8  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18008f8fd  jmp     short loc_18008F915
0x18008f8ff  cmp     [r14], r15
0x18008f902  jnz     short loc_18008F915
0x18008f904  mov     rcx, rdi; struct _KERB_LOGON_SESSION *
0x18008f907  call    ?KerbInsertLogonSession@@YAJPEAU_KERB_LOGON_SESSION@@@Z; KerbInsertLogonSession(_KERB_LOGON_SESSION *)
0x18008f90c  mov     ebx, eax
0x18008f90e  test    eax, eax
0x18008f910  js      short loc_18008F915
0x18008f912  mov     [r14], rdi
0x18008f915  test    sil, sil
0x18008f918  jz      short loc_18008F924
0x18008f91a  lea     rcx, [rdi+50h]; CriticalSection
0x18008f91e  call    cs:__imp_RtlLeaveCriticalSection
0x18008f924  test    r12b, r12b
0x18008f927  jz      short loc_18008F93A
0x18008f929  test    ebx, ebx
0x18008f92b  jns     short loc_18008F93A
0x18008f92d  test    rdi, rdi
0x18008f930  jz      short loc_18008F93A
0x18008f932  mov     rcx, rdi; struct _KERB_LOGON_SESSION *
0x18008f935  call    ?KerbDereferenceLogonSession@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbDereferenceLogonSession(_KERB_LOGON_SESSION *)
0x18008f93a  lea     rcx, [rbp+47h+Str]
0x18008f93e  call    KerbFreeString
0x18008f943  lea     rcx, [rbp+47h+var_90]
0x18008f947  call    KerbFreeString
0x18008f94c  movaps  xmm6, [rsp+0E0h+var_60+10h]
0x18008f954  mov     eax, ebx
0x18008f956  add     rsp, 0A8h
0x18008f95d  pop     r15
0x18008f95f  pop     r14
0x18008f961  pop     r13
0x18008f963  pop     r12
0x18008f965  pop     rdi
0x18008f966  pop     rsi
0x18008f967  pop     rbx
0x18008f968  pop     rbp
0x18008f969  retn
```
