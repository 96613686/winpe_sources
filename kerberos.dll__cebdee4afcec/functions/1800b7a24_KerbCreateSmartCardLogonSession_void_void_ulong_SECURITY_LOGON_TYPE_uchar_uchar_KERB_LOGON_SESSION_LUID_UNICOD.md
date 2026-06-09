# KerbCreateSmartCardLogonSession(void *,void *,ulong,_SECURITY_LOGON_TYPE,uchar,uchar,_KERB_LOGON_SESSION * *,_LUID *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x1800b7a24`
- end: `0x1800b8205`
- name: `?KerbCreateSmartCardLogonSession@@YAJPEAX0KW4_SECURITY_LOGON_TYPE@@EEPEAPEAU_KERB_LOGON_SESSION@@PEAU_LUID@@PEAU_UNICODE_STRING@@44@Z`
- size: `2017`
- prototype: `__int64 __fastcall(void *, void *, unsigned int, enum _SECURITY_LOGON_TYPE, char, char, struct _KERB_LOGON_SESSION **, struct _LUID *, struct _UNICODE_STRING *, PUNICODE_STRING DomainName2, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180025680`

## callees

- `0x1800068d0`
- `0x1800069a0`
- `0x1800093f0`
- `0x18000a630`
- `0x18000b300`
- `0x1800326a0`
- `0x18005f7fc`
- `0x18006cb94`
- `0x18007108c`
- `0x1800744cf`
- `0x18008b70c`
- `0x1800b63a4`
- `0x1800b7a24`
- `0x1800dcd98`
- `0x1800dcfe8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b81a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b81a5`
- `ntdll!RtlEqualComputerName` at `0x1800b80e3`
- `ntdll!RtlEqualComputerName` at `0x1800b80e3`
- `ntdll!RtlEqualDomainName` at `0x1800b80d1`
- `ntdll!RtlEqualDomainName` at `0x1800b80d1`
- `ntdll!RtlReleaseResource` at `0x1800b7e21`
- `ntdll!RtlReleaseResource` at `0x1800b7ea3`
- `ntdll!RtlReleaseResource` at `0x1800b7e21`
- `ntdll!RtlReleaseResource` at `0x1800b7ea3`
- `ntdll!RtlAcquireResourceShared` at `0x1800b7dfc`
- `ntdll!RtlAcquireResourceShared` at `0x1800b7e7e`
- `ntdll!RtlAcquireResourceShared` at `0x1800b7dfc`
- `ntdll!RtlAcquireResourceShared` at `0x1800b7e7e`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800b7ef1`
- `ntdll!NtAllocateLocallyUniqueId` at `0x1800b7ef1`
- `CRYPT32!CertFreeCertificateContext` at `0x1800b81b4`
- `CRYPT32!CertFreeCertificateContext` at `0x1800b81b4`

## string_xrefs

- `0x1800b7ab9`: `KerbCreateSmartCardLogonSession`
- `0x1800b7e53`: `KerbCreateSmartCardLogonSession`
- `0x1800b7ed5`: `KerbCreateSmartCardLogonSession`
- `0x1800b8060`: `KerbCreateSmartCardLogonSession`
- `0x1800b8112`: `KerbCreateSmartCardLogonSession`
- `0x1800b8146`: `KerbCreateSmartCardLogonSession`

## pseudocode

```c
__int64 __fastcall KerbCreateSmartCardLogonSession(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned int a3,
        enum _SECURITY_LOGON_TYPE a4,
        char a5,
        char a6,
        struct _KERB_LOGON_SESSION **a7,
        struct _LUID *a8,
        struct _UNICODE_STRING *a9,
        PUNICODE_STRING DomainName2,
        struct _UNICODE_STRING *a11)
{
  unsigned __int64 v11; // rbx
  WCHAR *v14; // r15
  struct _KERB_LOGON_SESSION *v15; // r13
  __int64 v16; // r8
  int v17; // ebx
  unsigned __int64 v18; // rcx
  __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  __int64 v21; // rdx
  unsigned __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned __int64 v24; // rcx
  unsigned int v25; // edx
  unsigned __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned __int64 v28; // rcx
  unsigned int v29; // edx
  char *v30; // rax
  WCHAR *v31; // rax
  _KerberosSystemRole *v32; // rcx
  struct _UNICODE_STRING *v33; // r14
  bool IsAnyKdc; // al
  char v35; // r15
  struct _UNICODE_STRING *v36; // r12
  struct _UNICODE_STRING *v37; // r14
  __int64 v38; // r8
  NTSTATUS v39; // eax
  int v40; // eax
  int v41; // eax
  bool v42; // zf
  int DnsNameArrayFromCertificate; // eax
  unsigned int v44; // edi
  USHORT Length; // ax
  unsigned int v46; // r14d
  struct _UNICODE_STRING *v47; // r15
  int v48; // eax
  unsigned __int8 v50[8]; // [rsp+20h] [rbp-E0h]
  enum _CRED_PROTECTION_TYPE *v51; // [rsp+28h] [rbp-D8h]
  __int64 v52; // [rsp+30h] [rbp-D0h]
  struct _KERB_LOGON_SESSION *v53; // [rsp+68h] [rbp-98h] BYREF
  LUID LocallyUniqueId; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING ComputerName2; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING ComputerName1; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING DomainName1; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING v60; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v61[40]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v62; // [rsp+F8h] [rbp-8h]
  unsigned int v63; // [rsp+10Ch] [rbp+Ch]
  char *v64; // [rsp+110h] [rbp+10h]
  WCHAR *v65; // [rsp+160h] [rbp+60h]
  unsigned int v66; // [rsp+178h] [rbp+78h] BYREF

  v11 = a3;
  LocallyUniqueId = 0;
  hMem = 0;
  v66 = 0;
  pCertContext = 0;
  v53 = 0;
  v60 = 0;
  v14 = 0;
  *a7 = 0;
  ComputerName1 = 0;
  v15 = 0;
  DomainName1 = 0;
  ComputerName2 = 0;
  memset_0(v61, 0, 0x48u);
  if ( (unsigned int)v11 >= 4 )
  {
    if ( ((*(_DWORD *)a1 - 6) & 0xFFFFFFFD) != 0 )
    {
      if ( ((*(_DWORD *)a1 - 13) & 0xFFFFFFFD) != 0 )
        goto LABEL_4;
      if ( (unsigned int)v11 < 0x48 )
      {
        v16 = 4517;
        goto LABEL_3;
      }
      v18 = *((_QWORD *)a1 + 6);
      if ( v18 >= a2 )
        v18 = *((_QWORD *)a1 + 6) - a2;
      if ( !v18 )
        goto LABEL_4;
      if ( v18 > v11 )
        goto LABEL_4;
      v19 = a1[20];
      if ( v18 + v19 > v11 )
        goto LABEL_4;
      if ( v18 < 0x48 )
        goto LABEL_4;
      if ( (v18 & 1) != 0 )
        goto LABEL_4;
      a1[21] = v19;
      *((_QWORD *)a1 + 6) = (char *)a1 + v18;
      if ( (v19 & 1) != 0 )
        goto LABEL_4;
      v20 = *((_QWORD *)a1 + 2);
      v21 = a1[4];
      if ( v20 )
      {
        if ( (_WORD)v21 )
        {
          if ( v20 >= a2 )
            v20 -= a2;
          if ( !v20 )
            goto LABEL_4;
          if ( v20 > v11 )
            goto LABEL_4;
          if ( v20 + v21 > v11 )
            goto LABEL_4;
          if ( v20 < 0x48 )
            goto LABEL_4;
          if ( (v20 & 1) != 0 )
            goto LABEL_4;
          a1[5] = v21;
          *((_QWORD *)a1 + 2) = (char *)a1 + v20;
          if ( (v21 & 1) != 0 )
            goto LABEL_4;
        }
        else
        {
          *((_QWORD *)a1 + 2) = 0;
        }
      }
      else if ( (_WORD)v21 )
      {
        goto LABEL_4;
      }
      v22 = *((_QWORD *)a1 + 4);
      v23 = a1[12];
      if ( v22 )
      {
        if ( (_WORD)v23 )
        {
          if ( v22 >= a2 )
            v22 -= a2;
          if ( !v22 )
            goto LABEL_4;
          if ( v22 > v11 )
            goto LABEL_4;
          if ( v22 + v23 > v11 )
            goto LABEL_4;
          if ( v22 < 0x48 )
            goto LABEL_4;
          if ( (v22 & 1) != 0 )
            goto LABEL_4;
          a1[13] = v23;
          *((_QWORD *)a1 + 4) = (char *)a1 + v22;
          if ( (v23 & 1) != 0 )
            goto LABEL_4;
        }
        else
        {
          *((_QWORD *)a1 + 4) = 0;
        }
      }
      else if ( (_WORD)v23 )
      {
        goto LABEL_4;
      }
      v24 = *((_QWORD *)a1 + 8);
      v25 = *((_DWORD *)a1 + 15);
      if ( v24 )
      {
        if ( v25 )
        {
          if ( v24 >= a2 )
            v24 -= a2;
          if ( v25 > (unsigned int)v11 || v24 > (unsigned int)v11 - v25 )
            goto LABEL_4;
          *((_QWORD *)a1 + 8) = (char *)a1 + v24;
        }
        else
        {
          *((_QWORD *)a1 + 8) = 0;
        }
      }
      else if ( v25 )
      {
        goto LABEL_4;
      }
      LODWORD(v15) = *((_DWORD *)a1 + 14) & 1;
LABEL_76:
      if ( (a1[20] & 1) != 0 )
      {
        v17 = -1073741811;
        goto LABEL_121;
      }
      v31 = (WCHAR *)MIDL_user_allocate(a1[20] + 2LL);
      v65 = v31;
      v14 = v31;
      if ( !v31 )
      {
        v17 = -1073741670;
LABEL_121:
        v15 = 0;
        goto LABEL_122;
      }
      memcpy_0(v31, *((const void **)a1 + 6), a1[20]);
      v17 = KerbDecodeSecretEx(v14, 0, 1, &v60, 1u, 0);
      if ( v17 < 0 )
        goto LABEL_121;
      v33 = a11;
      *a11 = v60;
      IsAnyKdc = _KerberosSystemRole::IsAnyKdc(v32);
      v35 = a5;
      if ( IsAnyKdc && a1[4] == 2 && **((_WORD **)a1 + 2) == 46 || a5 )
      {
        RtlAcquireResourceShared(&KerberosGlobalResource, 1u);
        v36 = DomainName2;
        v17 = KerbDuplicateStringEx(DomainName2, &KerbGlobalDnsDomainName);
        RtlReleaseResource(&KerberosGlobalResource);
      }
      else
      {
        v36 = DomainName2;
        v17 = KerbDuplicateStringEx(DomainName2, (const struct _UNICODE_STRING *)(a1 + 4));
      }
      if ( v17 < 0 )
      {
        KerbTracerT::Log(1, "KerbCreateSmartCardLogonSession", 4622, "Failed to allocate locally unique ID: 0x%x", v17);
        v15 = 0;
        v14 = v65;
        goto LABEL_123;
      }
      if ( v35 )
      {
        RtlAcquireResourceShared(&KerberosGlobalResource, 1u);
        v37 = a9;
        v17 = KerbDuplicateStringEx(a9, &KerbGlobalMachineServiceName);
        RtlReleaseResource(&KerberosGlobalResource);
      }
      else
      {
        v37 = a9;
        v17 = KerbDuplicateStringEx(a9, (const struct _UNICODE_STRING *)(a1 + 12));
      }
      if ( v17 < 0 )
      {
        *(_DWORD *)v50 = v17;
        v38 = 4644;
LABEL_93:
        KerbTracerT::Log(
          1,
          "KerbCreateSmartCardLogonSession",
          v38,
          "Failed to allocate locally unique ID: 0x%x",
          *(_QWORD *)v50);
LABEL_94:
        v14 = v65;
        goto LABEL_121;
      }
      v39 = NtAllocateLocallyUniqueId(&LocallyUniqueId);
      v17 = v39;
      if ( v39 < 0 )
      {
        *(_DWORD *)v50 = v39;
        v38 = 4656;
        goto LABEL_93;
      }
      if ( v35 && (a1[28] & 2) != 0 )
      {
        v40 = KerbBuildCertContextFromCertInfo(*((unsigned __int8 **)a1 + 8), *((_DWORD *)a1 + 15), &pCertContext);
        v17 = v40;
        if ( v40 < 0 )
        {
          *(_DWORD *)v50 = v40;
          KerbTracerT::Log(
            1,
            "KerbCreateSmartCardLogonSession",
            4671,
            "Failed to get cert context from cert info: %#x\n",
            *(_QWORD *)v50);
          goto LABEL_94;
        }
        v41 = KerbCreateSmartCardLogonSessionFromCertContextEx(
                &pCertContext,
                &LocallyUniqueId,
                v36,
                a11,
                1u,
                0,
                0,
                a6 != 0 ? 50333696 : 2048,
                &v53,
                v37,
                0);
      }
      else
      {
        v41 = KerbCreateSmartCardLogonSessionFromCertContextEx(
                0,
                &LocallyUniqueId,
                v36,
                a11,
                0,
                *((unsigned __int8 **)a1 + 8),
                *((_DWORD *)a1 + 15),
                (a6 != 0 ? 0x3000000 : 0) | (v35 != 0 ? 0x800 : 0),
                &v53,
                v37,
                0);
      }
      v17 = v41;
      if ( v41 >= 0 )
      {
        v42 = (_DWORD)v15 == 0;
        v15 = v53;
        if ( !v42 )
          *((_DWORD *)v53 + 226) |= 0x400u;
        if ( v35 )
        {
          DnsNameArrayFromCertificate = KerbGetDnsNameArrayFromCertificate(
                                          *(const struct _CERT_CONTEXT **)(*((_QWORD *)v15 + 50) + 32LL),
                                          (struct _UNICODE_STRING **)&hMem,
                                          &v66);
          v17 = DnsNameArrayFromCertificate;
          if ( DnsNameArrayFromCertificate < 0 )
          {
            KerbTracerT::Log(
              1,
              "KerbCreateSmartCardLogonSession",
              4733,
              "KerbGetDnsNameArrayFromCertificate failed: %#x",
              DnsNameArrayFromCertificate);
            goto LABEL_103;
          }
          v44 = 0;
          ComputerName2.Buffer = v37->Buffer;
          Length = v37->Length;
          v46 = v66;
          ComputerName2.Length = Length - 2;
          ComputerName2.MaximumLength = Length - 2;
          if ( v66 )
          {
            while ( 1 )
            {
              KerbFreeString((__int64)&ComputerName1);
              KerbFreeString((__int64)&DomainName1);
              v47 = (struct _UNICODE_STRING *)((char *)hMem + 16 * v44);
              v48 = KerbParseMachineDnsName(v47, &ComputerName1, &DomainName1);
              v17 = v48;
              if ( v48 < 0 )
                break;
              if ( (!RtlEqualDomainName(&DomainName1, v36) || !RtlEqualComputerName(&ComputerName1, &ComputerName2))
                && ++v44 < v46 )
              {
                continue;
              }
              goto LABEL_116;
            }
            LODWORD(v51) = v48;
            KerbTracerT::Log(
              1,
              "KerbCreateSmartCardLogonSession",
              4754,
              "KerbParseMachineDnsName failed to parse %wZ: %#x",
              v47,
              v51);
            goto LABEL_103;
          }
LABEL_116:
          if ( v44 == v46 )
          {
            v17 = -1073741715;
            LODWORD(v52) = -1073741715;
            KerbTracerT::Log(
              1,
              "KerbCreateSmartCardLogonSession",
              4780,
              "Found no DNS name matching %wZ and %wZ: %#x",
              v36,
              &ComputerName2,
              v52);
            goto LABEL_103;
          }
        }
        *a8 = LocallyUniqueId;
        *a7 = v15;
        v15 = 0;
        goto LABEL_103;
      }
      v15 = v53;
LABEL_103:
      v14 = v65;
      goto LABEL_122;
    }
    if ( (unsigned int)v11 < 0x28 )
    {
      v16 = 4481;
      goto LABEL_3;
    }
    v26 = *((_QWORD *)a1 + 2);
    if ( v26 >= a2 )
      v26 = *((_QWORD *)a1 + 2) - a2;
    if ( !v26 )
      goto LABEL_4;
    if ( v26 > v11 )
      goto LABEL_4;
    v27 = a1[4];
    if ( v26 + v27 > v11 )
      goto LABEL_4;
    if ( v26 < 0x28 )
      goto LABEL_4;
    if ( (v26 & 1) != 0 )
      goto LABEL_4;
    a1[5] = v27;
    *((_QWORD *)a1 + 2) = (char *)a1 + v26;
    if ( (v27 & 1) != 0 )
      goto LABEL_4;
    v28 = *((_QWORD *)a1 + 4);
    v29 = *((_DWORD *)a1 + 6);
    v62 = *(_OWORD *)(a1 + 4);
    if ( v28 )
    {
      if ( v29 )
      {
        if ( v28 >= a2 )
          v28 -= a2;
        if ( v29 > (unsigned int)v11 || v28 > (unsigned int)v11 - v29 )
          goto LABEL_4;
        v30 = (char *)a1 + v28;
        *((_QWORD *)a1 + 4) = (char *)a1 + v28;
        goto LABEL_75;
      }
      *((_QWORD *)a1 + 4) = 0;
    }
    else if ( v29 )
    {
      goto LABEL_4;
    }
    v30 = 0;
LABEL_75:
    v64 = v30;
    a1 = (unsigned __int16 *)v61;
    v63 = v29;
    goto LABEL_76;
  }
  v16 = 4471;
LABEL_3:
  KerbTracerT::Log(1, "KerbCreateSmartCardLogonSession", v16, "Submit buffer to logon too small: %d", v11);
LABEL_4:
  v17 = -1073741811;
LABEL_122:
  v33 = a11;
LABEL_123:
  KerbFreeString((__int64)&ComputerName1);
  KerbFreeString((__int64)&DomainName1);
  LocalFree(hMem);
  if ( pCertContext )
    CertFreeCertificateContext(pCertContext);
  if ( v14 )
    KerbFree(v14);
  if ( v17 < 0 )
  {
    *v33 = 0;
    KerbFreeString((__int64)&v60);
  }
  if ( v15 )
    KerbDereferenceLogonSession(v15);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800b7a24  mov     [rsp-8+arg_8], rbx
0x1800b7a29  mov     [rsp-8+arg_18], r9d
0x1800b7a2e  push    rbp
0x1800b7a2f  push    rsi
0x1800b7a30  push    rdi
0x1800b7a31  push    r12
0x1800b7a33  push    r13
0x1800b7a35  push    r14
0x1800b7a37  push    r15
0x1800b7a39  lea     rbp, [rsp-20h]
0x1800b7a3e  sub     rsp, 120h
0x1800b7a45  mov     rax, [rbp+50h+arg_30]
0x1800b7a4c  xor     r12d, r12d
0x1800b7a4f  xorps   xmm0, xmm0
0x1800b7a52  mov     ebx, r8d
0x1800b7a55  mov     r14, rdx
0x1800b7a58  mov     qword ptr [rsp+150h+LocallyUniqueId.LowPart], r12
0x1800b7a5d  mov     rdi, rcx
0x1800b7a60  mov     [rsp+150h+hMem], r12
0x1800b7a65  xorps   xmm1, xmm1
0x1800b7a68  mov     [rbp+50h+arg_18], r12d
0x1800b7a6c  lea     r8d, [r12+48h]; Size
0x1800b7a71  mov     [rbp+50h+pCertContext], r12
0x1800b7a75  xor     edx, edx; Val
0x1800b7a77  mov     [rsp+150h+var_F0], r12
0x1800b7a7c  lea     rcx, [rbp+50h+var_80]; void *
0x1800b7a80  mov     [rsp+150h+var_E8], r12
0x1800b7a85  movups  xmmword ptr [rbp+50h+var_98.Length], xmm0
0x1800b7a89  mov     r15d, r12d
0x1800b7a8c  mov     [rax], r12
0x1800b7a8f  movups  xmmword ptr [rbp+50h+ComputerName1.Length], xmm0
0x1800b7a93  mov     r13d, r12d
0x1800b7a96  movups  xmmword ptr [rbp+50h+DomainName1.Length], xmm1
0x1800b7a9a  movups  xmmword ptr [rbp+50h+ComputerName2.Length], xmm0
0x1800b7a9e  call    memset_0
0x1800b7aa3  cmp     ebx, 4
0x1800b7aa6  jnb     short loc_1800B7AD4
0x1800b7aa8  mov     r8d, 1177h
0x1800b7aae  lea     r9, aSubmitBufferTo; "Submit buffer to logon too small: %d"
0x1800b7ab5  mov     dword ptr [rsp+150h+var_130], ebx
0x1800b7ab9  lea     rdx, aKerbcreatesmar_2; "KerbCreateSmartCardLogonSession"
0x1800b7ac0  mov     ecx, 1
0x1800b7ac5  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b7aca  mov     ebx, 0C000000Dh
0x1800b7acf  jmp     loc_1800B8187
0x1800b7ad4  mov     ecx, [rdi]
0x1800b7ad6  mov     edx, 0FFFFFFFDh
0x1800b7adb  lea     eax, [rcx-6]
0x1800b7ade  test    edx, eax
0x1800b7ae0  jz      loc_1800B7C84
0x1800b7ae6  lea     eax, [rcx-0Dh]
0x1800b7ae9  test    edx, eax
0x1800b7aeb  jnz     short loc_1800B7ACA
0x1800b7aed  cmp     ebx, 48h ; 'H'
0x1800b7af0  jnb     short loc_1800B7AFA
0x1800b7af2  mov     r8d, 11A5h
0x1800b7af8  jmp     short loc_1800B7AAE
0x1800b7afa  mov     rcx, [rdi+30h]
0x1800b7afe  mov     rax, rcx
0x1800b7b01  sub     rax, r14
0x1800b7b04  cmp     rcx, r14
0x1800b7b07  cmovnb  rcx, rax
0x1800b7b0b  test    rcx, rcx
0x1800b7b0e  jz      short loc_1800B7ACA
0x1800b7b10  cmp     rcx, rbx
0x1800b7b13  ja      short loc_1800B7ACA
0x1800b7b15  movzx   edx, word ptr [rdi+28h]
0x1800b7b19  lea     rax, [rcx+rdx]
0x1800b7b1d  cmp     rax, rbx
0x1800b7b20  ja      short loc_1800B7ACA
0x1800b7b22  cmp     rcx, 48h ; 'H'
0x1800b7b26  jb      short loc_1800B7ACA
0x1800b7b28  mov     esi, 1
0x1800b7b2d  test    sil, cl
0x1800b7b30  jnz     short loc_1800B7ACA
0x1800b7b32  mov     [rdi+2Ah], dx
0x1800b7b36  lea     rax, [rcx+rdi]
0x1800b7b3a  mov     [rdi+30h], rax
0x1800b7b3e  test    sil, dl
0x1800b7b41  jnz     short loc_1800B7ACA
0x1800b7b43  mov     rcx, [rdi+10h]
0x1800b7b47  movzx   edx, word ptr [rdi+8]
0x1800b7b4b  test    rcx, rcx
0x1800b7b4e  jnz     short loc_1800B7B5A
0x1800b7b50  test    dx, dx
0x1800b7b53  jz      short loc_1800B7BB9
0x1800b7b55  jmp     loc_1800B7ACA
0x1800b7b5a  test    dx, dx
0x1800b7b5d  jnz     short loc_1800B7B65
0x1800b7b5f  mov     [rdi+10h], r12
0x1800b7b63  jmp     short loc_1800B7BB9
0x1800b7b65  mov     rax, rcx
0x1800b7b68  sub     rax, r14
0x1800b7b6b  cmp     rcx, r14
0x1800b7b6e  cmovnb  rcx, rax
0x1800b7b72  test    rcx, rcx
0x1800b7b75  jz      loc_1800B7ACA
0x1800b7b7b  cmp     rcx, rbx
0x1800b7b7e  ja      loc_1800B7ACA
0x1800b7b84  lea     rax, [rcx+rdx]
0x1800b7b88  cmp     rax, rbx
0x1800b7b8b  ja      loc_1800B7ACA
0x1800b7b91  cmp     rcx, 48h ; 'H'
0x1800b7b95  jb      loc_1800B7ACA
0x1800b7b9b  test    sil, cl
0x1800b7b9e  jnz     loc_1800B7ACA
0x1800b7ba4  mov     [rdi+0Ah], dx
0x1800b7ba8  lea     rax, [rcx+rdi]
0x1800b7bac  mov     [rdi+10h], rax
0x1800b7bb0  test    sil, dl
0x1800b7bb3  jnz     loc_1800B7ACA
0x1800b7bb9  mov     rcx, [rdi+20h]
0x1800b7bbd  movzx   edx, word ptr [rdi+18h]
0x1800b7bc1  test    rcx, rcx
0x1800b7bc4  jnz     short loc_1800B7BD0
0x1800b7bc6  test    dx, dx
0x1800b7bc9  jz      short loc_1800B7C2F
0x1800b7bcb  jmp     loc_1800B7ACA
0x1800b7bd0  test    dx, dx
0x1800b7bd3  jnz     short loc_1800B7BDB
0x1800b7bd5  mov     [rdi+20h], r12
0x1800b7bd9  jmp     short loc_1800B7C2F
0x1800b7bdb  mov     rax, rcx
0x1800b7bde  sub     rax, r14
0x1800b7be1  cmp     rcx, r14
0x1800b7be4  cmovnb  rcx, rax
0x1800b7be8  test    rcx, rcx
0x1800b7beb  jz      loc_1800B7ACA
0x1800b7bf1  cmp     rcx, rbx
0x1800b7bf4  ja      loc_1800B7ACA
0x1800b7bfa  lea     rax, [rcx+rdx]
0x1800b7bfe  cmp     rax, rbx
0x1800b7c01  ja      loc_1800B7ACA
0x1800b7c07  cmp     rcx, 48h ; 'H'
0x1800b7c0b  jb      loc_1800B7ACA
0x1800b7c11  test    sil, cl
0x1800b7c14  jnz     loc_1800B7ACA
0x1800b7c1a  mov     [rdi+1Ah], dx
0x1800b7c1e  lea     rax, [rcx+rdi]
0x1800b7c22  mov     [rdi+20h], rax
0x1800b7c26  test    sil, dl
0x1800b7c29  jnz     loc_1800B7ACA
0x1800b7c2f  mov     rcx, [rdi+40h]
0x1800b7c33  mov     edx, [rdi+3Ch]
0x1800b7c36  test    rcx, rcx
0x1800b7c39  jnz     short loc_1800B7C44
0x1800b7c3b  test    edx, edx
0x1800b7c3d  jz      short loc_1800B7C78
0x1800b7c3f  jmp     loc_1800B7ACA
0x1800b7c44  test    edx, edx
0x1800b7c46  jnz     short loc_1800B7C4E
0x1800b7c48  mov     [rdi+40h], r12
0x1800b7c4c  jmp     short loc_1800B7C78
0x1800b7c4e  mov     rax, rcx
0x1800b7c51  sub     rax, r14
0x1800b7c54  cmp     rcx, r14
0x1800b7c57  cmovnb  rcx, rax
0x1800b7c5b  cmp     edx, ebx
0x1800b7c5d  ja      loc_1800B7ACA
0x1800b7c63  sub     ebx, edx
0x1800b7c65  mov     eax, ebx
0x1800b7c67  cmp     rcx, rax
0x1800b7c6a  ja      loc_1800B7ACA
0x1800b7c70  lea     rax, [rcx+rdi]
0x1800b7c74  mov     [rdi+40h], rax
0x1800b7c78  mov     r13d, [rdi+38h]
0x1800b7c7c  and     r13d, esi
0x1800b7c7f  jmp     loc_1800B7D55
0x1800b7c84  cmp     ebx, 28h ; '('
0x1800b7c87  jnb     short loc_1800B7C94
0x1800b7c89  mov     r8d, 1181h
0x1800b7c8f  jmp     loc_1800B7AAE
0x1800b7c94  mov     rcx, [rdi+10h]
0x1800b7c98  mov     rax, rcx
0x1800b7c9b  sub     rax, r14
0x1800b7c9e  cmp     rcx, r14
0x1800b7ca1  cmovnb  rcx, rax
0x1800b7ca5  test    rcx, rcx
0x1800b7ca8  jz      loc_1800B7ACA
0x1800b7cae  cmp     rcx, rbx
0x1800b7cb1  ja      loc_1800B7ACA
0x1800b7cb7  movzx   edx, word ptr [rdi+8]
0x1800b7cbb  lea     rax, [rcx+rdx]
0x1800b7cbf  cmp     rax, rbx
0x1800b7cc2  ja      loc_1800B7ACA
0x1800b7cc8  cmp     rcx, 28h ; '('
0x1800b7ccc  jb      loc_1800B7ACA
0x1800b7cd2  mov     esi, 1
0x1800b7cd7  test    sil, cl
0x1800b7cda  jnz     loc_1800B7ACA
0x1800b7ce0  mov     [rdi+0Ah], dx
0x1800b7ce4  lea     rax, [rcx+rdi]
0x1800b7ce8  mov     [rdi+10h], rax
0x1800b7cec  test    sil, dl
0x1800b7cef  jnz     loc_1800B7ACA
0x1800b7cf5  movups  xmm0, xmmword ptr [rdi+8]
0x1800b7cf9  mov     rcx, [rdi+20h]
0x1800b7cfd  mov     edx, [rdi+18h]
0x1800b7d00  movdqu  [rbp+50h+var_58], xmm0
0x1800b7d05  test    rcx, rcx
0x1800b7d08  jnz     short loc_1800B7D13
0x1800b7d0a  test    edx, edx
0x1800b7d0c  jz      short loc_1800B7D1B
0x1800b7d0e  jmp     loc_1800B7ACA
0x1800b7d13  test    edx, edx
0x1800b7d15  jnz     short loc_1800B7D20
0x1800b7d17  mov     [rdi+20h], r12
0x1800b7d1b  mov     rax, r12
0x1800b7d1e  jmp     short loc_1800B7D4A
0x1800b7d20  mov     rax, rcx
0x1800b7d23  sub     rax, r14
0x1800b7d26  cmp     rcx, r14
0x1800b7d29  cmovnb  rcx, rax
0x1800b7d2d  cmp     edx, ebx
0x1800b7d2f  ja      loc_1800B7ACA
0x1800b7d35  sub     ebx, edx
0x1800b7d37  mov     eax, ebx
0x1800b7d39  cmp     rcx, rax
0x1800b7d3c  ja      loc_1800B7ACA
0x1800b7d42  lea     rax, [rcx+rdi]
0x1800b7d46  mov     [rdi+20h], rax
0x1800b7d4a  mov     [rbp+50h+var_40], rax
0x1800b7d4e  lea     rdi, [rbp+50h+var_80]
0x1800b7d52  mov     [rbp+50h+var_44], edx
0x1800b7d55  test    [rdi+28h], sil
0x1800b7d59  jnz     loc_1800B817D
0x1800b7d5f  movzx   ecx, word ptr [rdi+28h]
0x1800b7d63  add     rcx, 2; size
0x1800b7d67  call    MIDL_user_allocate
0x1800b7d6c  mov     [rbp+50h+arg_0], rax
0x1800b7d70  mov     r15, rax
0x1800b7d73  test    rax, rax
0x1800b7d76  jnz     short loc_1800B7D82
0x1800b7d78  mov     ebx, 0C000009Ah
0x1800b7d7d  jmp     loc_1800B8182
0x1800b7d82  movzx   r8d, word ptr [rdi+28h]; Size
0x1800b7d87  mov     rcx, r15; void *
0x1800b7d8a  mov     rdx, [rdi+30h]; Src
0x1800b7d8e  call    memcpy_0
0x1800b7d93  lea     r9, [rbp+50h+var_98]; struct _UNICODE_STRING *
0x1800b7d97  mov     [rsp+150h+var_128], r12; enum _CRED_PROTECTION_TYPE *
0x1800b7d9c  mov     r8b, sil; unsigned __int8
0x1800b7d9f  mov     [rsp+150h+var_130], sil; unsigned __int8
0x1800b7da4  xor     edx, edx; Token
0x1800b7da6  mov     rcx, r15; pszProtectedCredentials
0x1800b7da9  call    ?KerbDecodeSecretEx@@YAJPEAGPEAXEPEAU_UNICODE_STRING@@EPEAW4_CRED_PROTECTION_TYPE@@@Z; KerbDecodeSecretEx(ushort *,void *,uchar,_UNICODE_STRING *,uchar,_CRED_PROTECTION_TYPE *)
0x1800b7dae  mov     ebx, eax
0x1800b7db0  test    eax, eax
0x1800b7db2  js      loc_1800B8182
0x1800b7db8  movups  xmm0, xmmword ptr [rbp+50h+var_98.Length]
0x1800b7dbc  mov     r14, [rbp+50h+arg_50]
0x1800b7dc3  movdqu  xmmword ptr [r14], xmm0
0x1800b7dc8  call    ?IsAnyKdc@_KerberosSystemRole@@QEAA_NXZ; _KerberosSystemRole::IsAnyKdc(void)
0x1800b7dcd  mov     r15b, [rbp+50h+arg_20]
0x1800b7dd4  test    al, al
0x1800b7dd6  jz      short loc_1800B7DED
0x1800b7dd8  mov     eax, 2
0x1800b7ddd  cmp     [rdi+8], ax
0x1800b7de1  jnz     short loc_1800B7DED
0x1800b7de3  mov     rax, [rdi+10h]
0x1800b7de7  cmp     word ptr [rax], 2Eh ; '.'
0x1800b7deb  jz      short loc_1800B7DF2
0x1800b7ded  test    r15b, r15b
0x1800b7df0  jz      short loc_1800B7E29
0x1800b7df2  mov     dl, sil; Wait
0x1800b7df5  lea     rcx, ?KerberosGlobalResource@@3U_RTL_RESOURCE@@A; Resource
0x1800b7dfc  call    cs:__imp_RtlAcquireResourceShared
0x1800b7e02  mov     r12, [rbp+50h+DomainName2]
0x1800b7e09  lea     rdx, ?KerbGlobalDnsDomainName@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x1800b7e10  mov     rcx, r12; struct _UNICODE_STRING *
0x1800b7e13  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x1800b7e18  lea     rcx, ?KerberosGlobalResource@@3U_RTL_RESOURCE@@A; Resource
0x1800b7e1f  mov     ebx, eax
0x1800b7e21  call    cs:__imp_RtlReleaseResource
0x1800b7e27  jmp     short loc_1800B7E3E
0x1800b7e29  mov     r12, [rbp+50h+DomainName2]
0x1800b7e30  lea     rdx, [rdi+8]; struct _UNICODE_STRING *
0x1800b7e34  mov     rcx, r12; struct _UNICODE_STRING *
0x1800b7e37  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x1800b7e3c  mov     ebx, eax
0x1800b7e3e  test    ebx, ebx
0x1800b7e40  jns     short loc_1800B7E6F
0x1800b7e42  lea     r9, aFailedToAlloca_5; "Failed to allocate locally unique ID: 0"...
0x1800b7e49  mov     dword ptr [rsp+150h+var_130], ebx
0x1800b7e4d  mov     r8d, 120Eh
0x1800b7e53  lea     rdx, aKerbcreatesmar_2; "KerbCreateSmartCardLogonSession"
0x1800b7e5a  mov     ecx, esi
0x1800b7e5c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b7e61  mov     r13, [rsp+150h+var_F0]
0x1800b7e66  mov     r15, [rbp+50h+arg_0]
0x1800b7e6a  jmp     loc_1800B818E
0x1800b7e6f  test    r15b, r15b
0x1800b7e72  jz      short loc_1800B7EAB
0x1800b7e74  mov     dl, sil; Wait
0x1800b7e77  lea     rcx, ?KerberosGlobalResource@@3U_RTL_RESOURCE@@A; Resource
0x1800b7e7e  call    cs:__imp_RtlAcquireResourceShared
0x1800b7e84  mov     r14, [rbp+50h+arg_40]
0x1800b7e8b  lea     rdx, ?KerbGlobalMachineServiceName@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x1800b7e92  mov     rcx, r14; struct _UNICODE_STRING *
0x1800b7e95  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
  ... truncated ...
```
