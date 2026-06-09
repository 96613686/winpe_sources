# KerbCacheFidoLogon(_NETLOGON_VALIDATION_SAM_INFO4 *,_LSA_TOKEN_INFORMATION_V3 *,_KERB_LOGON_SESSION *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *,void *,ulong)

- ea: `0x1800be9bc`
- end: `0x1800becb5`
- name: `?KerbCacheFidoLogon@@YAXPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAU_LSA_TOKEN_INFORMATION_V3@@PEAU_KERB_LOGON_SESSION@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@PEAXK@Z`
- size: `761`
- prototype: `void __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO4 *, struct _LSA_TOKEN_INFORMATION_V3 *, struct _KERB_LOGON_SESSION *, struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **, void *, size_t)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x1800819b0`

## callees

- `0x1800069a0`
- `0x18003ca2c`
- `0x18008b70c`
- `0x1800b8ef4`
- `0x1800be744`
- `0x1800be9bc`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x1800bead5`
- `ntdll!RtlEqualUnicodeString` at `0x1800bead5`
- `ntdll!RtlEnterCriticalSection` at `0x1800bea00`
- `ntdll!RtlEnterCriticalSection` at `0x1800bea00`
- `ntdll!RtlLeaveCriticalSection` at `0x1800bec58`
- `ntdll!RtlLeaveCriticalSection` at `0x1800bec58`

## string_xrefs

- `0x1800beb8d`: `Unable to update password logon cache entry!\n`
- `0x1800bebf7`: `KerbCacheLogonInformation failed: %#x\n`
- `0x1800beb9a`: `KerbCacheFidoLogon`
- `0x1800bec08`: `KerbCacheFidoLogon`
- `0x1800bec43`: `KerbCacheFidoLogon`
- `0x1800bec32`: `KerbAddFidoCacheToSuppCred failed: %#x\n`

## pseudocode

```c
void __fastcall KerbCacheFidoLogon(
        struct _UNICODE_STRING *a1,
        struct _LSA_TOKEN_INFORMATION_V3 *a2,
        struct _RTL_CRITICAL_SECTION *a3,
        struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **a4,
        void *a5,
        size_t a6)
{
  unsigned int v7; // r12d
  unsigned __int8 *v8; // rdi
  struct _FIDO_CACHE_BLOB *v9; // rbx
  int v13; // eax
  struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY *v14; // rcx
  unsigned int v15; // ebx
  __int64 v16; // r15
  BOOLEAN v17; // al
  unsigned int CredentialSize; // edx
  struct _MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL *v19; // r9
  PUCHAR Credentials; // rax
  struct _LM_OWF_PASSWORD *v21; // r8
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdx
  unsigned __int8 *v25; // rax
  size_t v26; // [rsp+50h] [rbp-30h]
  struct _FIDO_CACHE_BLOB *v27; // [rsp+60h] [rbp-20h] BYREF
  PRTL_CRITICAL_SECTION CriticalSection; // [rsp+68h] [rbp-18h]
  UNICODE_STRING String2; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v30; // [rsp+D0h] [rbp+50h] BYREF
  unsigned __int8 *v31; // [rsp+D8h] [rbp+58h] BYREF

  v7 = 0;
  CriticalSection = a3 + 2;
  v8 = 0;
  v30 = 0;
  v9 = 0;
  v31 = 0;
  v27 = 0;
  RtlEnterCriticalSection(a3 + 2);
  if ( a4 )
  {
    if ( *a4 )
    {
      v13 = KerbFilterAndEncodeCachedCredentialData(a2, a4, &v31, &v30);
      v7 = v30;
      v8 = v31;
      if ( v13 < 0 )
        goto LABEL_37;
    }
  }
  if ( (*(_DWORD *)&a1[15].Length & 0x1000) != 0 )
  {
    LODWORD(v26) = 0;
    KerbCacheLogonInformation(
      a1 + 3,
      a1 + 13,
      0,
      0,
      (struct _KERB_LOGON_SESSION *)a3,
      4u,
      (struct _NETLOGON_VALIDATION_SAM_INFO4 *)a1,
      0,
      0,
      0,
      v26,
      0);
    goto LABEL_33;
  }
  if ( a4 )
  {
    v14 = *a4;
    if ( *a4 )
    {
      *(_QWORD *)&String2.Length = 655368;
      String2.Buffer = (PWSTR)L"NTLM";
      if ( v14->CredentialCount )
      {
        v15 = 0;
        while ( 1 )
        {
          v16 = v15;
          v17 = RtlEqualUnicodeString(&v14->Credentials[v16].PackageName, &String2, 1u);
          v14 = *a4;
          if ( v17 )
            break;
          if ( ++v15 >= v14->CredentialCount )
            goto LABEL_33;
        }
        CredentialSize = v14->Credentials[v16].CredentialSize;
        v19 = 0;
        Credentials = v14->Credentials[v16].Credentials;
        if ( CredentialSize < 0x28 || *(_DWORD *)Credentials || (Credentials[4] & 2) == 0 )
        {
          if ( CredentialSize >= 0x2C && *(_DWORD *)Credentials == 2 && (Credentials[4] & 2) != 0 )
          {
            v21 = (struct _LM_OWF_PASSWORD *)(Credentials + 8);
          }
          else
          {
            if ( CredentialSize < 0x44 || *(_DWORD *)Credentials != 4 || (Credentials[4] & 2) == 0 )
            {
              if ( CredentialSize < 0xC || *(_DWORD *)Credentials != -65535 )
              {
LABEL_32:
                KerbTracerT::Log(1, "KerbCacheFidoLogon", 386, "Unable to update password logon cache entry!\n");
                goto LABEL_33;
              }
              v21 = 0;
              v19 = (struct _MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL *)v14->Credentials[v16].Credentials;
LABEL_30:
              if ( v19 )
                goto LABEL_31;
              goto LABEL_32;
            }
            v21 = (struct _LM_OWF_PASSWORD *)(Credentials + 12);
          }
        }
        else
        {
          v21 = (struct _LM_OWF_PASSWORD *)(Credentials + 24);
        }
        if ( v21 )
        {
LABEL_31:
          LODWORD(v26) = a6;
          KerbCacheLogonInformation(
            a1 + 3,
            a1 + 13,
            v21,
            v19,
            (struct _KERB_LOGON_SESSION *)a3,
            0,
            (struct _NETLOGON_VALIDATION_SAM_INFO4 *)a1,
            0,
            0,
            a5,
            v26,
            0);
          goto LABEL_33;
        }
        goto LABEL_30;
      }
    }
  }
LABEL_33:
  LODWORD(v26) = a6;
  v22 = KerbCacheLogonInformation(
          a1 + 3,
          a1 + 13,
          0,
          0,
          (struct _KERB_LOGON_SESSION *)a3,
          0,
          (struct _NETLOGON_VALIDATION_SAM_INFO4 *)a1,
          v8,
          v7,
          a5,
          v26,
          &v27);
  if ( v22 >= 0 )
  {
    v9 = v27;
    v23 = KerbAddFidoCacheToSuppCred(v27, a4);
    if ( v23 < 0 )
      KerbTracerT::Log(1, "KerbCacheFidoLogon", 421, "KerbAddFidoCacheToSuppCred failed: %#x\n", v23);
  }
  else
  {
    KerbTracerT::Log(1, "KerbCacheFidoLogon", 413, "KerbCacheLogonInformation failed: %#x\n", v22);
    v9 = v27;
  }
LABEL_37:
  RtlLeaveCriticalSection(CriticalSection);
  if ( v8 )
  {
    v24 = v7;
    v25 = v8;
    if ( v7 )
    {
      do
      {
        *v25++ = 0;
        --v24;
      }
      while ( v24 );
    }
    KerbFree(v8);
  }
  if ( v9 )
    ((void (__fastcall *)(struct _FIDO_CACHE_BLOB *))LsaFunctions->FreeLsaHeap)(v9);
}

```

## disassembly

```asm
0x1800be9bc  mov     [rsp-38h+arg_0], rbx
0x1800be9c1  push    rbp
0x1800be9c2  push    rsi
0x1800be9c3  push    rdi
0x1800be9c4  push    r12
0x1800be9c6  push    r13
0x1800be9c8  push    r14
0x1800be9ca  push    r15
0x1800be9cc  mov     rbp, rsp
0x1800be9cf  sub     rsp, 80h
0x1800be9d6  lea     rax, [r8+50h]
0x1800be9da  mov     rsi, rcx
0x1800be9dd  xor     r12d, r12d
0x1800be9e0  mov     [rbp+CriticalSection], rax
0x1800be9e4  xor     edi, edi
0x1800be9e6  mov     [rbp+arg_10], r12d
0x1800be9ea  xor     ebx, ebx
0x1800be9ec  mov     [rbp+arg_18], rdi
0x1800be9f0  mov     rcx, rax; CriticalSection
0x1800be9f3  mov     [rbp+var_20], rbx
0x1800be9f7  mov     r14, r9
0x1800be9fa  mov     r13, r8
0x1800be9fd  mov     r15, rdx
0x1800bea00  call    cs:__imp_RtlEnterCriticalSection
0x1800bea06  test    r14, r14
0x1800bea09  jz      short loc_1800BEA37
0x1800bea0b  cmp     [r14], rbx
0x1800bea0e  jz      short loc_1800BEA37
0x1800bea10  lea     r9, [rbp+arg_10]; unsigned int *
0x1800bea14  mov     rdx, r14; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x1800bea17  lea     r8, [rbp+arg_18]; unsigned __int8 **
0x1800bea1b  mov     rcx, r15; struct _LSA_TOKEN_INFORMATION_V3 *
0x1800bea1e  call    ?KerbFilterAndEncodeCachedCredentialData@@YAJPEAU_LSA_TOKEN_INFORMATION_V3@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@PEAPEAEPEAK@Z; KerbFilterAndEncodeCachedCredentialData(_LSA_TOKEN_INFORMATION_V3 *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *,uchar * *,ulong *)
0x1800bea23  mov     r12d, [rbp+arg_10]
0x1800bea27  xor     r15d, r15d
0x1800bea2a  mov     rdi, [rbp+arg_18]
0x1800bea2e  test    eax, eax
0x1800bea30  jns     short loc_1800BEA3A
0x1800bea32  jmp     loc_1800BEC54
0x1800bea37  xor     r15d, r15d
0x1800bea3a  test    dword ptr [rsi+0F0h], 1000h
0x1800bea44  jz      short loc_1800BEA8C
0x1800bea46  mov     [rsp+80h+var_28], r15; struct _FIDO_CACHE_BLOB **
0x1800bea4b  xor     r9d, r9d; struct _MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL *
0x1800bea4e  mov     dword ptr [rsp+80h+var_30], r15d; size_t
0x1800bea53  xor     r8d, r8d; struct _LM_OWF_PASSWORD *
0x1800bea56  mov     [rsp+80h+var_38], r15; void *
0x1800bea5b  mov     [rsp+80h+var_40], r15d; unsigned int
0x1800bea60  mov     [rsp+80h+var_48], r15; void *
0x1800bea65  mov     [rsp+80h+var_50], rsi; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x1800bea6a  mov     [rsp+80h+var_58], 4; unsigned int
0x1800bea72  lea     rcx, [rsi+30h]; struct _UNICODE_STRING *
0x1800bea76  mov     [rsp+80h+var_60], r13; struct _KERB_LOGON_SESSION *
0x1800bea7b  lea     rdx, [rsi+0D0h]; struct _UNICODE_STRING *
0x1800bea82  call    ?KerbCacheLogonInformation@@YAJPEAU_UNICODE_STRING@@0PEAU_LM_OWF_PASSWORD@@PEAU_MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL@@PEAU_KERB_LOGON_SESSION@@KPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAXK5KPEAPEAU_FIDO_CACHE_BLOB@@@Z; KerbCacheLogonInformation(_UNICODE_STRING *,_UNICODE_STRING *,_LM_OWF_PASSWORD *,_MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL *,_KERB_LOGON_SESSION *,ulong,_NETLOGON_VALIDATION_SAM_INFO4 *,void *,ulong,void *,ulong,_FIDO_CACHE_BLOB * *)
0x1800bea87  jmp     loc_1800BEBAB
0x1800bea8c  test    r14, r14
0x1800bea8f  jz      loc_1800BEBAB
0x1800bea95  mov     rcx, [r14]
0x1800bea98  test    rcx, rcx
0x1800bea9b  jz      loc_1800BEBAB
0x1800beaa1  lea     rax, aNtlm; "NTLM"
0x1800beaa8  mov     qword ptr [rbp+String2.Length], 0A0008h
0x1800beab0  mov     [rbp+String2.Buffer], rax
0x1800beab4  cmp     [rcx], r15d
0x1800beab7  jbe     loc_1800BEBAB
0x1800beabd  mov     ebx, r15d
0x1800beac0  add     rcx, 8
0x1800beac4  mov     r15d, ebx
0x1800beac7  shl     r15, 5
0x1800beacb  lea     rdx, [rbp+String2]; String2
0x1800beacf  add     rcx, r15; String1
0x1800bead2  mov     r8b, 1; CaseInsensitive
0x1800bead5  call    cs:__imp_RtlEqualUnicodeString
0x1800beadb  mov     rcx, [r14]
0x1800beade  test    al, al
0x1800beae0  jnz     short loc_1800BEAF0
0x1800beae2  inc     ebx
0x1800beae4  cmp     ebx, [rcx]
0x1800beae6  jb      short loc_1800BEAC0
0x1800beae8  xor     r15d, r15d
0x1800beaeb  jmp     loc_1800BEBAB
0x1800beaf0  mov     edx, [r15+rcx+18h]
0x1800beaf5  xor     r9d, r9d
0x1800beaf8  mov     rax, [r15+rcx+20h]
0x1800beafd  xor     r15d, r15d
0x1800beb00  cmp     edx, 28h ; '('
0x1800beb03  jb      short loc_1800BEB16
0x1800beb05  cmp     [rax], r15d
0x1800beb08  jnz     short loc_1800BEB16
0x1800beb0a  test    byte ptr [rax+4], 2
0x1800beb0e  jz      short loc_1800BEB16
0x1800beb10  lea     r8, [rax+18h]
0x1800beb14  jmp     short loc_1800BEB40
0x1800beb16  cmp     edx, 2Ch ; ','
0x1800beb19  jb      short loc_1800BEB2C
0x1800beb1b  cmp     dword ptr [rax], 2
0x1800beb1e  jnz     short loc_1800BEB2C
0x1800beb20  test    byte ptr [rax+4], 2
0x1800beb24  jz      short loc_1800BEB2C
0x1800beb26  lea     r8, [rax+8]
0x1800beb2a  jmp     short loc_1800BEB40
0x1800beb2c  cmp     edx, 44h ; 'D'
0x1800beb2f  jb      short loc_1800BEB47
0x1800beb31  cmp     dword ptr [rax], 4
0x1800beb34  jnz     short loc_1800BEB47
0x1800beb36  test    byte ptr [rax+4], 2
0x1800beb3a  jz      short loc_1800BEB47
0x1800beb3c  lea     r8, [rax+0Ch]
0x1800beb40  test    r8, r8
0x1800beb43  jnz     short loc_1800BEB5F
0x1800beb45  jmp     short loc_1800BEB5A
0x1800beb47  cmp     edx, 0Ch
0x1800beb4a  jb      short loc_1800BEB8D
0x1800beb4c  cmp     dword ptr [rax], 0FFFF0001h
0x1800beb52  jnz     short loc_1800BEB8D
0x1800beb54  mov     r8, r15
0x1800beb57  mov     r9, rax
0x1800beb5a  test    r9, r9
0x1800beb5d  jz      short loc_1800BEB8D
0x1800beb5f  mov     eax, dword ptr [rbp+arg_28]
0x1800beb62  mov     [rsp+80h+var_28], r15
0x1800beb67  mov     dword ptr [rsp+80h+var_30], eax
0x1800beb6b  mov     rax, [rbp+arg_20]
0x1800beb6f  mov     [rsp+80h+var_38], rax
0x1800beb74  mov     [rsp+80h+var_40], r15d
0x1800beb79  mov     [rsp+80h+var_48], r15
0x1800beb7e  mov     [rsp+80h+var_50], rsi
0x1800beb83  mov     [rsp+80h+var_58], r15d
0x1800beb88  jmp     loc_1800BEA72
0x1800beb8d  lea     r9, aUnableToUpdate; "Unable to update password logon cache e"...
0x1800beb94  mov     r8d, 182h
0x1800beb9a  lea     rdx, aKerbcachefidol; "KerbCacheFidoLogon"
0x1800beba1  mov     ecx, 1
0x1800beba6  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800bebab  lea     rax, [rbp+var_20]
0x1800bebaf  xor     r9d, r9d; struct _MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL *
0x1800bebb2  mov     [rsp+80h+var_28], rax; struct _FIDO_CACHE_BLOB **
0x1800bebb7  lea     rdx, [rsi+0D0h]; struct _UNICODE_STRING *
0x1800bebbe  mov     eax, dword ptr [rbp+arg_28]
0x1800bebc1  lea     rcx, [rsi+30h]; struct _UNICODE_STRING *
0x1800bebc5  mov     dword ptr [rsp+80h+var_30], eax; size_t
0x1800bebc9  xor     r8d, r8d; struct _LM_OWF_PASSWORD *
0x1800bebcc  mov     rax, [rbp+arg_20]
0x1800bebd0  mov     [rsp+80h+var_38], rax; void *
0x1800bebd5  mov     [rsp+80h+var_40], r12d; unsigned int
0x1800bebda  mov     [rsp+80h+var_48], rdi; void *
0x1800bebdf  mov     [rsp+80h+var_50], rsi; struct _NETLOGON_VALIDATION_SAM_INFO4 *
0x1800bebe4  mov     [rsp+80h+var_58], r15d; unsigned int
0x1800bebe9  mov     [rsp+80h+var_60], r13; struct _KERB_LOGON_SESSION *
0x1800bebee  call    ?KerbCacheLogonInformation@@YAJPEAU_UNICODE_STRING@@0PEAU_LM_OWF_PASSWORD@@PEAU_MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL@@PEAU_KERB_LOGON_SESSION@@KPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAXK5KPEAPEAU_FIDO_CACHE_BLOB@@@Z; KerbCacheLogonInformation(_UNICODE_STRING *,_UNICODE_STRING *,_LM_OWF_PASSWORD *,_MSV1_0_IUM_SUPPLEMENTAL_CREDENTIAL *,_KERB_LOGON_SESSION *,ulong,_NETLOGON_VALIDATION_SAM_INFO4 *,void *,ulong,void *,ulong,_FIDO_CACHE_BLOB * *)
0x1800bebf3  test    eax, eax
0x1800bebf5  jns     short loc_1800BEC1F
0x1800bebf7  lea     r9, aKerbcachelogon_0; "KerbCacheLogonInformation failed: %#x\n"
0x1800bebfe  mov     dword ptr [rsp+80h+var_60], eax
0x1800bec02  mov     r8d, 19Dh
0x1800bec08  lea     rdx, aKerbcachefidol; "KerbCacheFidoLogon"
0x1800bec0f  mov     ecx, 1
0x1800bec14  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800bec19  mov     rbx, [rbp+var_20]
0x1800bec1d  jmp     short loc_1800BEC54
0x1800bec1f  mov     rbx, [rbp+var_20]
0x1800bec23  mov     rdx, r14; struct _SECPKG_SUPPLEMENTAL_CRED_ARRAY **
0x1800bec26  mov     rcx, rbx; struct _FIDO_CACHE_BLOB *
0x1800bec29  call    ?KerbAddFidoCacheToSuppCred@@YAJPEAU_FIDO_CACHE_BLOB@@PEAPEAU_SECPKG_SUPPLEMENTAL_CRED_ARRAY@@@Z; KerbAddFidoCacheToSuppCred(_FIDO_CACHE_BLOB *,_SECPKG_SUPPLEMENTAL_CRED_ARRAY * *)
0x1800bec2e  test    eax, eax
0x1800bec30  jns     short loc_1800BEC54
0x1800bec32  lea     r9, aKerbaddfidocac; "KerbAddFidoCacheToSuppCred failed: %#x"...
0x1800bec39  mov     dword ptr [rsp+80h+var_60], eax
0x1800bec3d  mov     r8d, 1A5h
0x1800bec43  lea     rdx, aKerbcachefidol; "KerbCacheFidoLogon"
0x1800bec4a  mov     ecx, 1
0x1800bec4f  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800bec54  mov     rcx, [rbp+CriticalSection]; CriticalSection
0x1800bec58  call    cs:__imp_RtlLeaveCriticalSection
0x1800bec5e  test    rdi, rdi
0x1800bec61  jz      short loc_1800BEC82
0x1800bec63  mov     edx, r12d
0x1800bec66  mov     rax, rdi
0x1800bec69  test    r12d, r12d
0x1800bec6c  jz      short loc_1800BEC7A
0x1800bec6e  mov     [rax], r15b
0x1800bec71  inc     rax
0x1800bec74  sub     rdx, 1
0x1800bec78  jnz     short loc_1800BEC6E
0x1800bec7a  mov     rcx, rdi
0x1800bec7d  call    KerbFree
0x1800bec82  test    rbx, rbx
0x1800bec85  jz      short loc_1800BEC9A
0x1800bec87  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800bec8e  mov     rcx, rbx
0x1800bec91  mov     rax, [rax+30h]
0x1800bec95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bec9a  mov     rbx, [rsp+80h+arg_0]
0x1800beca2  add     rsp, 80h
0x1800beca9  pop     r15
0x1800becab  pop     r14
0x1800becad  pop     r13
0x1800becaf  pop     r12
0x1800becb1  pop     rdi
0x1800becb2  pop     rsi
0x1800becb3  pop     rbp
0x1800becb4  retn
```
