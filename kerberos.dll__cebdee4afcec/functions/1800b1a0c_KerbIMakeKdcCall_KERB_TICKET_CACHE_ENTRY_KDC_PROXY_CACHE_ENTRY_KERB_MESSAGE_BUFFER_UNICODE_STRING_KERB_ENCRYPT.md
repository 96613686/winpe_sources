# KerbIMakeKdcCall(_KERB_TICKET_CACHE_ENTRY *,_KDC_PROXY_CACHE_ENTRY *,_KERB_MESSAGE_BUFFER,_UNICODE_STRING,_KERB_ENCRYPTION_KEY,uchar,_DOMAIN_PASSWORD_INFORMATION * *)

- ea: `0x1800b1a0c`
- end: `0x1800b1f90`
- name: `?KerbIMakeKdcCall@@YAJPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KDC_PROXY_CACHE_ENTRY@@U_KERB_MESSAGE_BUFFER@@U_UNICODE_STRING@@U_KERB_ENCRYPTION_KEY@@EPEAPEAU_DOMAIN_PASSWORD_INFORMATION@@@Z`
- size: `1412`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800083b4`
- `0x1800b1f98`

## callees

- `0x1800068d0`
- `0x1800069a0`
- `0x1800093f0`
- `0x1800670f8`
- `0x18006e748`
- `0x180070680`
- `0x180078274`
- `0x18008b70c`
- `0x180099c70`
- `0x1800b1618`
- `0x1800b1a0c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b1e8c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b1f68`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b1e8c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b1f68`
- `WS2_32!__imp_ntohl` at `0x1800b1c0b`
- `WS2_32!__imp_ntohl` at `0x1800b1c1a`
- `WS2_32!__imp_ntohl` at `0x1800b1c2a`
- `WS2_32!__imp_ntohl` at `0x1800b1c44`
- `WS2_32!__imp_ntohl` at `0x1800b1c52`
- `WS2_32!__imp_ntohl` at `0x1800b1c6c`
- `WS2_32!__imp_ntohl` at `0x1800b1c7a`
- `WS2_32!__imp_ntohl` at `0x1800b1c0b`
- `WS2_32!__imp_ntohl` at `0x1800b1c1a`
- `WS2_32!__imp_ntohl` at `0x1800b1c2a`
- `WS2_32!__imp_ntohl` at `0x1800b1c44`
- `WS2_32!__imp_ntohl` at `0x1800b1c52`
- `WS2_32!__imp_ntohl` at `0x1800b1c6c`
- `WS2_32!__imp_ntohl` at `0x1800b1c7a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800b1cdb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800b1cdb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800b1d1f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800b1d1f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800b1e7d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800b1f5d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800b1e7d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800b1f5d`
- `SAMLIB!SamOpenDomain` at `0x1800b1de5`
- `SAMLIB!SamOpenDomain` at `0x1800b1de5`
- `SAMLIB!SamConnect` at `0x1800b1d9a`
- `SAMLIB!SamConnect` at `0x1800b1d9a`
- `SAMLIB!SamFreeMemory` at `0x1800b1efb`
- `SAMLIB!SamFreeMemory` at `0x1800b1efb`
- `SAMLIB!SamCloseHandle` at `0x1800b1e55`
- `SAMLIB!SamCloseHandle` at `0x1800b1e69`
- `SAMLIB!SamCloseHandle` at `0x1800b1f3e`
- `SAMLIB!SamCloseHandle` at `0x1800b1f4e`
- `SAMLIB!SamCloseHandle` at `0x1800b1e55`
- `SAMLIB!SamCloseHandle` at `0x1800b1e69`
- `SAMLIB!SamCloseHandle` at `0x1800b1f3e`
- `SAMLIB!SamCloseHandle` at `0x1800b1f4e`
- `SAMLIB!SamQueryInformationDomain` at `0x1800b1e0e`
- `SAMLIB!SamQueryInformationDomain` at `0x1800b1e0e`

## string_xrefs

- `0x1800b1ac4`: `Failed to send kpasswd request over kdc proxy cache entry %p: %#x`
- `0x1800b1b4d`: `Failed to call kpasswd service: 0x%x`
- `0x1800b1ce7`: `Can not open LSA policy to get domain info: 0x%x`
- `0x1800b1df1`: `Can not open SAM domain to get domain info: 0x%x`

## pseudocode

```c
__int64 __fastcall KerbIMakeKdcCall(
        struct _KERB_TICKET_CACHE_ENTRY *a1,
        struct _KDC_PROXY_CACHE_ENTRY *a2,
        struct _KERB_MESSAGE_BUFFER *a3,
        UNICODE_STRING *a4,
        struct _KERB_ENCRYPTION_KEY *a5,
        char a6,
        __int64 a7)
{
  char v7; // r13
  char i; // r15
  int v11; // eax
  unsigned int v12; // esi
  int v13; // eax
  int v14; // eax
  bool v15; // cf
  void *v16; // rax
  unsigned __int8 *v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // rbx
  NTSTATUS v20; // eax
  NTSTATUS v21; // ebx
  NTSTATUS v22; // eax
  int v23; // eax
  const char *v24; // r9
  __int64 v25; // r8
  int v26; // eax
  _QWORD *v27; // rax
  _OWORD *v28; // rcx
  unsigned __int8 *v29; // rax
  __int64 v30; // rcx
  unsigned int *v32; // [rsp+20h] [rbp-E0h]
  bool v33; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v34; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  PVOID PolicyHandle; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 *v38; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v39; // [rsp+98h] [rbp-68h] BYREF
  PVOID Buffer; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD *v41; // [rsp+A8h] [rbp-58h] BYREF
  struct _LSA_UNICODE_STRING SystemName; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v43; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v44; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v45; // [rsp+E0h] [rbp-20h]
  __int128 v46; // [rsp+F0h] [rbp-10h]
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+100h] [rbp+0h] BYREF
  __int64 v48; // [rsp+130h] [rbp+30h] BYREF
  int v49; // [rsp+138h] [rbp+38h]

  v7 = 0;
  v33 = 0;
  v37 = 0;
  v35 = 0;
  v48 = 0;
  v49 = 0;
  PolicyHandle = 0;
  i = 0;
  Buffer = 0;
  v38 = 0;
  v34 = 0;
  v41 = 0;
  v43 = 0;
  SystemName = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a2 )
  {
    v11 = KerbMakeHttpCallByCache(a2, a4, a3, (struct _KERB_MESSAGE_BUFFER *)&v43);
    v12 = v11;
    if ( v11 < 0 )
    {
      KerbTracerT::Log(
        1,
        "KerbIMakeKdcCall",
        2471,
        "Failed to send kpasswd request over kdc proxy cache entry %p: %#x",
        (const void *)WORD1(a2),
        v11);
      goto LABEL_42;
    }
  }
  else
  {
    v39 = 0;
    v13 = KerbMakeSocketCallInternal(
            a4,
            0,
            0,
            0,
            1u,
            a3,
            (struct _KERB_MESSAGE_BUFFER *)&v43,
            0,
            0,
            0,
            &v33,
            (struct _UNICODE_STRING *)&SystemName,
            &v39);
    v12 = v13;
    if ( v13 < 0 )
    {
      KerbTracerT::Log(1, "KerbIMakeKdcCall", 2493, "Failed to call kpasswd service: 0x%x", v13);
      goto LABEL_42;
    }
  }
  v14 = KerbHandleKpasswdReply(a1, a5, (struct _KERB_MESSAGE_BUFFER *)&v43, &v38, &v34);
  v12 = v14;
  if ( v14 < 0 )
  {
    KerbTracerT::Log(2, "KerbIMakeKdcCall", 2507, "Change password reply failed: 0x%x", v14);
    if ( v12 == -1073741716 && SystemName.Length && a7 )
    {
      v15 = v34 < 0x20;
      *(_QWORD *)a7 = 0;
      if ( !v15 )
      {
        v16 = MIDL_user_allocate(0x18u);
        *(_QWORD *)a7 = v16;
        if ( v16 )
        {
          v17 = v38;
          **(_WORD **)a7 = ntohl(*((_DWORD *)v38 + 1));
          *(_WORD *)(*(_QWORD *)a7 + 2LL) = ntohl(*((_DWORD *)v17 + 2));
          *(_DWORD *)(*(_QWORD *)a7 + 4LL) = ntohl(*((_DWORD *)v17 + 3));
          v18 = -*((_QWORD *)v17 + 2);
          *(_DWORD *)(*(_QWORD *)a7 + 8LL) = ntohl(HIDWORD(v18));
          *(_DWORD *)(*(_QWORD *)a7 + 12LL) = ntohl(v18);
          v19 = -*((_QWORD *)v17 + 3);
          *(_DWORD *)(*(_QWORD *)a7 + 16LL) = ntohl(HIDWORD(v19));
          *(_DWORD *)(*(_QWORD *)a7 + 20LL) = ntohl(v19);
        }
        goto LABEL_42;
      }
      if ( !a6 )
        goto LABEL_16;
      if ( LsaFunctions->ImpersonateClient() >= 0 )
      {
        for ( i = 1; ; i = 1 )
        {
LABEL_16:
          ObjectAttributes.Length = 48;
          memset(&ObjectAttributes.RootDirectory, 0, 20);
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v20 = LsaOpenPolicy(&SystemName, &ObjectAttributes, 1u, &PolicyHandle);
          v21 = v20;
          if ( v20 < 0 )
          {
            KerbTracerT::Log(2, "KerbIMakeKdcCall", 2602, "Can not open LSA policy to get domain info: 0x%x", v20);
            PolicyHandle = 0;
            goto LABEL_27;
          }
          v22 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
          v21 = v22;
          if ( v22 < 0 )
          {
            KerbTracerT::Log(2, "KerbIMakeKdcCall", 2612, "Can not query LSA policy to get domain info: 0x%x", v22);
            Buffer = 0;
            goto LABEL_27;
          }
          *((_QWORD *)&v44 + 1) = 0;
          DWORD2(v45) = 0;
          *(_QWORD *)&v45 = 0;
          *(_QWORD *)&v46 = 0;
          LOWORD(v49) = 0;
          *((_QWORD *)&v46 + 1) = &v48;
          LODWORD(v44) = 48;
          v48 = 0x10000000CLL;
          v23 = SamConnect(&SystemName, &v37, 32, &v44);
          v21 = v23;
          if ( v23 < 0 )
            break;
          v23 = SamOpenDomain(v37, 1, *((_QWORD *)Buffer + 2), &v35);
          v21 = v23;
          if ( v23 < 0 )
          {
            v24 = "Can not open SAM domain to get domain info: 0x%x";
            v25 = 2646;
            goto LABEL_22;
          }
          v26 = SamQueryInformationDomain(v35, 1, &v41);
          v21 = v26;
          if ( v26 >= 0 )
          {
            v27 = MIDL_user_allocate(0x18u);
            *(_QWORD *)a7 = v27;
            if ( v27 )
            {
              v28 = v41;
              *(_OWORD *)v27 = *v41;
              v27[2] = *((_QWORD *)v28 + 2);
            }
            goto LABEL_42;
          }
          KerbTracerT::Log(2, "KerbIMakeKdcCall", 2655, " Can not query SAM to get domain info: 0x%x", v26);
LABEL_27:
          if ( v21 != -1073741790 || v7 )
            goto LABEL_42;
          if ( v37 )
          {
            SamCloseHandle();
            v37 = 0;
          }
          if ( v35 )
          {
            SamCloseHandle();
            v35 = 0;
          }
          if ( PolicyHandle )
          {
            LsaClose(PolicyHandle);
            PolicyHandle = 0;
          }
          if ( i && !RevertToSelf() )
            goto LABEL_42;
          i = 0;
          if ( (int)KerbImpersonateNetworkService() < 0 )
            goto LABEL_42;
          v7 = 1;
        }
        v24 = "Can not connect to SAM to get domain info: 0x%x";
        v25 = 2633;
LABEL_22:
        LODWORD(v32) = v23;
        KerbTracerT::Log(2, "KerbIMakeKdcCall", v25, v24, v32);
        v35 = 0;
        goto LABEL_27;
      }
    }
  }
LABEL_42:
  KerbFreeString((__int64)&SystemName);
  if ( *((_QWORD *)&v43 + 1) )
    KerbFree(*((_QWORD *)&v43 + 1));
  if ( v41 )
    SamFreeMemory();
  if ( a2 )
    KerbDereferenceKdcProxyCacheEntry(a2);
  v29 = v38;
  if ( v38 )
  {
    v30 = v34;
    if ( v34 )
    {
      do
      {
        *v29++ = 0;
        --v30;
      }
      while ( v30 );
    }
    KerbFree(v38);
  }
  if ( v37 )
    SamCloseHandle();
  if ( v35 )
    SamCloseHandle();
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( i )
    RevertToSelf();
  return v12;
}

```

## disassembly

```asm
0x1800b1a0c  push    rbp
0x1800b1a0e  push    rbx
0x1800b1a0f  push    rsi
0x1800b1a10  push    rdi
0x1800b1a11  push    r12
0x1800b1a13  push    r13
0x1800b1a15  push    r14
0x1800b1a17  push    r15
0x1800b1a19  lea     rbp, [rsp-58h]
0x1800b1a1e  sub     rsp, 158h
0x1800b1a25  mov     rax, cs:__security_cookie
0x1800b1a2c  xor     rax, rsp
0x1800b1a2f  mov     [rbp+90h+var_50], rax
0x1800b1a33  mov     rdi, [rbp+90h+arg_20]
0x1800b1a3a  xor     r13d, r13d
0x1800b1a3d  mov     r14, [rbp+90h+arg_30]
0x1800b1a44  xorps   xmm0, xmm0
0x1800b1a47  xorps   xmm1, xmm1
0x1800b1a4a  mov     [rsp+190h+var_120], r13b
0x1800b1a4f  mov     rbx, rcx
0x1800b1a52  mov     [rbp+90h+var_108], r13
0x1800b1a56  xor     ecx, ecx
0x1800b1a58  mov     [rsp+190h+var_118], r13
0x1800b1a5d  mov     [rbp+90h+var_60], rcx
0x1800b1a61  mov     rax, r9
0x1800b1a64  mov     [rbp+90h+var_58], ecx
0x1800b1a67  mov     r12, rdx
0x1800b1a6a  mov     [rbp+90h+PolicyHandle], r13
0x1800b1a6e  mov     r15b, r13b
0x1800b1a71  mov     [rbp+90h+Buffer], r13
0x1800b1a75  mov     [rbp+90h+var_100], r13
0x1800b1a79  mov     [rsp+190h+var_11C], r13d
0x1800b1a7e  mov     [rbp+90h+var_E8], r13
0x1800b1a82  movups  [rbp+90h+var_D0], xmm0
0x1800b1a86  movups  xmmword ptr [rbp+90h+SystemName.Length], xmm0
0x1800b1a8a  movups  [rbp+90h+var_C0], xmm1
0x1800b1a8e  movups  [rbp+90h+var_B0], xmm1
0x1800b1a92  movups  [rbp+90h+var_A0], xmm1
0x1800b1a96  movups  xmmword ptr [rbp+90h+ObjectAttributes.Length], xmm0
0x1800b1a9a  movups  xmmword ptr [rbp+90h+ObjectAttributes.ObjectName], xmm0
0x1800b1a9e  movups  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b1aa2  test    rdx, rdx
0x1800b1aa5  jz      short loc_1800B1AF5
0x1800b1aa7  lea     r9, [rbp+90h+var_D0]; struct _KERB_MESSAGE_BUFFER *
0x1800b1aab  mov     rdx, rax; struct _UNICODE_STRING *
0x1800b1aae  mov     rcx, r12; struct _KDC_PROXY_CACHE_ENTRY *
0x1800b1ab1  call    ?KerbMakeHttpCallByCache@@YAJPEAU_KDC_PROXY_CACHE_ENTRY@@PEAU_UNICODE_STRING@@PEAU_KERB_MESSAGE_BUFFER@@2KPEAE1@Z; KerbMakeHttpCallByCache(_KDC_PROXY_CACHE_ENTRY *,_UNICODE_STRING *,_KERB_MESSAGE_BUFFER *,_KERB_MESSAGE_BUFFER *,ulong,uchar *,_UNICODE_STRING *)
0x1800b1ab6  mov     esi, eax
0x1800b1ab8  test    eax, eax
0x1800b1aba  jns     loc_1800B1B74
0x1800b1ac0  mov     dword ptr [rsp+190h+var_168], eax
0x1800b1ac4  lea     r9, aFailedToSendKp; "Failed to send kpasswd request over kdc"...
0x1800b1acb  mov     rcx, r12
0x1800b1ace  mov     r8d, 9A7h
0x1800b1ad4  shr     rcx, 10h
0x1800b1ad8  movzx   edx, cx
0x1800b1adb  lea     ecx, [r13+1]
0x1800b1adf  mov     [rsp+190h+var_170], rdx
0x1800b1ae4  lea     rdx, aKerbimakekdcca_0; "KerbIMakeKdcCall"
0x1800b1aeb  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b1af0  jmp     loc_1800B1EDB
0x1800b1af5  lea     rcx, [rbp+90h+var_F8]
0x1800b1af9  mov     [rbp+90h+var_F8], r13d
0x1800b1afd  mov     [rsp+190h+var_130], rcx
0x1800b1b02  xor     r9d, r9d
0x1800b1b05  lea     rcx, [rbp+90h+SystemName]
0x1800b1b09  xor     edx, edx
0x1800b1b0b  mov     [rsp+190h+var_138], rcx
0x1800b1b10  lea     rcx, [rsp+190h+var_120]
0x1800b1b15  mov     [rsp+190h+var_140], rcx
0x1800b1b1a  lea     rcx, [rbp+90h+var_D0]
0x1800b1b1e  mov     [rsp+190h+var_148], r13b
0x1800b1b23  mov     [rsp+190h+var_150], r13d
0x1800b1b28  mov     [rsp+190h+var_158], r13
0x1800b1b2d  mov     [rsp+190h+var_160], rcx
0x1800b1b32  mov     rcx, rax
0x1800b1b35  mov     [rsp+190h+var_168], r8
0x1800b1b3a  xor     r8d, r8d
0x1800b1b3d  mov     byte ptr [rsp+190h+var_170], 1
0x1800b1b42  call    ?KerbMakeSocketCallInternal@@YAJPEAU_UNICODE_STRING@@0W4_KERB_KDC_TYPE@@EEPEAU_KERB_MESSAGE_BUFFER@@2PEAU_KERB_BINDING_CACHE_ENTRY@@KEPEAE0PEAK@Z; KerbMakeSocketCallInternal(_UNICODE_STRING *,_UNICODE_STRING *,_KERB_KDC_TYPE,uchar,uchar,_KERB_MESSAGE_BUFFER *,_KERB_MESSAGE_BUFFER *,_KERB_BINDING_CACHE_ENTRY *,ulong,uchar,uchar *,_UNICODE_STRING *,ulong *)
0x1800b1b47  mov     esi, eax
0x1800b1b49  test    eax, eax
0x1800b1b4b  jns     short loc_1800B1B74
0x1800b1b4d  lea     r9, aFailedToCallKp; "Failed to call kpasswd service: 0x%x"
0x1800b1b54  mov     dword ptr [rsp+190h+var_170], eax
0x1800b1b58  mov     r8d, 9BDh
0x1800b1b5e  lea     rdx, aKerbimakekdcca_0; "KerbIMakeKdcCall"
0x1800b1b65  mov     ecx, 1
0x1800b1b6a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b1b6f  jmp     loc_1800B1EDB
0x1800b1b74  lea     rax, [rsp+190h+var_11C]
0x1800b1b79  mov     rdx, rdi; struct _KERB_ENCRYPTION_KEY *
0x1800b1b7c  lea     r9, [rbp+90h+var_100]; unsigned __int8 **
0x1800b1b80  mov     [rsp+190h+var_170], rax; unsigned int *
0x1800b1b85  lea     r8, [rbp+90h+var_D0]; struct _KERB_MESSAGE_BUFFER *
0x1800b1b89  mov     rcx, rbx; struct _KERB_TICKET_CACHE_ENTRY *
0x1800b1b8c  call    ?KerbHandleKpasswdReply@@YAJPEAU_KERB_TICKET_CACHE_ENTRY@@PEAU_KERB_ENCRYPTION_KEY@@PEAU_KERB_MESSAGE_BUFFER@@PEAPEAEPEAK@Z; KerbHandleKpasswdReply(_KERB_TICKET_CACHE_ENTRY *,_KERB_ENCRYPTION_KEY *,_KERB_MESSAGE_BUFFER *,uchar * *,ulong *)
0x1800b1b91  mov     esi, eax
0x1800b1b93  test    eax, eax
0x1800b1b95  jns     loc_1800B1EDB
0x1800b1b9b  lea     rdi, aKerbimakekdcca_0; "KerbIMakeKdcCall"
0x1800b1ba2  mov     dword ptr [rsp+190h+var_170], eax
0x1800b1ba6  mov     rdx, rdi
0x1800b1ba9  lea     r9, aChangePassword; "Change password reply failed: 0x%x"
0x1800b1bb0  mov     r8d, 9CBh
0x1800b1bb6  mov     ecx, 2
0x1800b1bbb  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b1bc0  cmp     esi, 0C000006Ch
0x1800b1bc6  jnz     loc_1800B1EDB
0x1800b1bcc  cmp     r13w, [rbp+90h+SystemName.Length]
0x1800b1bd1  jz      loc_1800B1EDB
0x1800b1bd7  test    r14, r14
0x1800b1bda  jz      loc_1800B1EDB
0x1800b1be0  cmp     [rsp+190h+var_11C], 20h ; ' '
0x1800b1be5  mov     [r14], r13
0x1800b1be8  jb      loc_1800B1C8B
0x1800b1bee  mov     ecx, 18h; size
0x1800b1bf3  call    MIDL_user_allocate
0x1800b1bf8  mov     [r14], rax
0x1800b1bfb  test    rax, rax
0x1800b1bfe  jz      loc_1800B1EDB
0x1800b1c04  mov     rdi, [rbp+90h+var_100]
0x1800b1c08  mov     ecx, [rdi+4]; netlong
0x1800b1c0b  call    cs:__imp_ntohl
0x1800b1c11  mov     rcx, [r14]
0x1800b1c14  mov     [rcx], ax
0x1800b1c17  mov     ecx, [rdi+8]; netlong
0x1800b1c1a  call    cs:__imp_ntohl
0x1800b1c20  mov     rcx, [r14]
0x1800b1c23  mov     [rcx+2], ax
0x1800b1c27  mov     ecx, [rdi+0Ch]; netlong
0x1800b1c2a  call    cs:__imp_ntohl
0x1800b1c30  mov     rcx, [r14]
0x1800b1c33  mov     [rcx+4], eax
0x1800b1c36  mov     rbx, [rdi+10h]
0x1800b1c3a  neg     rbx
0x1800b1c3d  mov     rcx, rbx
0x1800b1c40  shr     rcx, 20h; netlong
0x1800b1c44  call    cs:__imp_ntohl
0x1800b1c4a  mov     rcx, [r14]
0x1800b1c4d  mov     [rcx+8], eax
0x1800b1c50  mov     ecx, ebx; netlong
0x1800b1c52  call    cs:__imp_ntohl
0x1800b1c58  mov     rcx, [r14]
0x1800b1c5b  mov     [rcx+0Ch], eax
0x1800b1c5e  mov     rbx, [rdi+18h]
0x1800b1c62  neg     rbx
0x1800b1c65  mov     rcx, rbx
0x1800b1c68  shr     rcx, 20h; netlong
0x1800b1c6c  call    cs:__imp_ntohl
0x1800b1c72  mov     rcx, [r14]
0x1800b1c75  mov     [rcx+10h], eax
0x1800b1c78  mov     ecx, ebx; netlong
0x1800b1c7a  call    cs:__imp_ntohl
0x1800b1c80  mov     rcx, [r14]
0x1800b1c83  mov     [rcx+14h], eax
0x1800b1c86  jmp     loc_1800B1EDB
0x1800b1c8b  cmp     [rbp+90h+arg_28], r13b
0x1800b1c92  jz      short loc_1800B1CAF
0x1800b1c94  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800b1c9b  mov     rax, [rax+58h]
0x1800b1c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1ca4  test    eax, eax
0x1800b1ca6  js      loc_1800B1EDB
0x1800b1cac  mov     r15b, 1
0x1800b1caf  xor     eax, eax
0x1800b1cb1  mov     [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x1800b1cb8  xorps   xmm0, xmm0
0x1800b1cbb  mov     [rbp+90h+ObjectAttributes.RootDirectory], rax
0x1800b1cbf  lea     r9, [rbp+90h+PolicyHandle]; PolicyHandle
0x1800b1cc3  mov     [rbp+90h+ObjectAttributes.Attributes], eax
0x1800b1cc6  lea     rdx, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x1800b1cca  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x1800b1cce  lea     r8d, [rax+1]; DesiredAccess
0x1800b1cd2  lea     rcx, [rbp+90h+SystemName]; SystemName
0x1800b1cd6  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800b1cdb  call    cs:__imp_LsaOpenPolicy
0x1800b1ce1  mov     ebx, eax
0x1800b1ce3  test    eax, eax
0x1800b1ce5  jns     short loc_1800B1D12
0x1800b1ce7  lea     r9, aCanNotOpenLsaP; "Can not open LSA policy to get domain i"...
0x1800b1cee  mov     dword ptr [rsp+190h+var_170], eax
0x1800b1cf2  mov     r8d, 0A2Ah
0x1800b1cf8  mov     rdx, rdi
0x1800b1cfb  mov     ecx, 2
0x1800b1d00  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b1d05  mov     [rbp+90h+PolicyHandle], 0
0x1800b1d0d  jmp     loc_1800B1E3C
0x1800b1d12  mov     rcx, [rbp+90h+PolicyHandle]; PolicyHandle
0x1800b1d16  lea     r8, [rbp+90h+Buffer]; Buffer
0x1800b1d1a  mov     edx, 5; InformationClass
0x1800b1d1f  call    cs:__imp_LsaQueryInformationPolicy
0x1800b1d25  xor     ecx, ecx
0x1800b1d27  mov     ebx, eax
0x1800b1d29  test    eax, eax
0x1800b1d2b  jns     short loc_1800B1D58
0x1800b1d2d  lea     r9, aCanNotQueryLsa; "Can not query LSA policy to get domain "...
0x1800b1d34  mov     dword ptr [rsp+190h+var_170], eax
0x1800b1d38  mov     r8d, 0A34h
0x1800b1d3e  mov     rdx, rdi
0x1800b1d41  mov     ecx, 2
0x1800b1d46  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b1d4b  mov     [rbp+90h+Buffer], 0
0x1800b1d53  jmp     loc_1800B1E3C
0x1800b1d58  mov     qword ptr [rbp+90h+var_C0+8], rcx
0x1800b1d5c  lea     rax, [rbp+90h+var_60]
0x1800b1d60  mov     dword ptr [rbp+90h+var_B0+8], ecx
0x1800b1d63  lea     r9, [rbp+90h+var_C0]
0x1800b1d67  mov     qword ptr [rbp+90h+var_B0], rcx
0x1800b1d6b  lea     rdx, [rbp+90h+var_108]
0x1800b1d6f  mov     qword ptr [rbp+90h+var_A0], rcx
0x1800b1d73  mov     r8d, 20h ; ' '
0x1800b1d79  mov     word ptr [rbp+90h+var_58], cx
0x1800b1d7d  lea     rcx, [rbp+90h+SystemName]
0x1800b1d81  mov     qword ptr [rbp+90h+var_A0+8], rax
0x1800b1d85  mov     dword ptr [rbp+90h+var_C0], 30h ; '0'
0x1800b1d8c  mov     dword ptr [rbp+90h+var_60], 0Ch
0x1800b1d93  mov     dword ptr [rbp+90h+var_60+4], 1
0x1800b1d9a  call    cs:__imp_SamConnect
0x1800b1da0  mov     ebx, eax
0x1800b1da2  test    eax, eax
0x1800b1da4  jns     short loc_1800B1DCF
0x1800b1da6  lea     r9, aCanNotConnectT; "Can not connect to SAM to get domain in"...
0x1800b1dad  mov     r8d, 0A49h
0x1800b1db3  mov     rdx, rdi
0x1800b1db6  mov     dword ptr [rsp+190h+var_170], eax
0x1800b1dba  mov     ecx, 2
0x1800b1dbf  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b1dc4  mov     [rsp+190h+var_118], 0
0x1800b1dcd  jmp     short loc_1800B1E3C
0x1800b1dcf  mov     r8, [rbp+90h+Buffer]
0x1800b1dd3  lea     r9, [rsp+190h+var_118]
0x1800b1dd8  mov     rcx, [rbp+90h+var_108]
0x1800b1ddc  mov     edx, 1
0x1800b1de1  mov     r8, [r8+10h]
0x1800b1de5  call    cs:__imp_SamOpenDomain
0x1800b1deb  mov     ebx, eax
0x1800b1ded  test    eax, eax
0x1800b1def  jns     short loc_1800B1E00
0x1800b1df1  lea     r9, aCanNotOpenSamD; "Can not open SAM domain to get domain i"...
0x1800b1df8  mov     r8d, 0A56h
0x1800b1dfe  jmp     short loc_1800B1DB3
0x1800b1e00  mov     rcx, [rsp+190h+var_118]
0x1800b1e05  lea     r8, [rbp+90h+var_E8]
0x1800b1e09  mov     edx, 1
0x1800b1e0e  call    cs:__imp_SamQueryInformationDomain
0x1800b1e14  mov     ebx, eax
0x1800b1e16  test    eax, eax
0x1800b1e18  jns     loc_1800B1EB2
0x1800b1e1e  lea     r9, aCanNotQuerySam; " Can not query SAM to get domain info: "...
0x1800b1e25  mov     dword ptr [rsp+190h+var_170], eax
0x1800b1e29  mov     r8d, 0A5Fh
0x1800b1e2f  mov     rdx, rdi
0x1800b1e32  mov     ecx, 2
0x1800b1e37  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b1e3c  cmp     ebx, 0C0000022h
0x1800b1e42  jnz     short loc_1800B1EAD
0x1800b1e44  test    r13b, r13b
0x1800b1e47  jnz     short loc_1800B1EAD
0x1800b1e49  mov     rcx, [rbp+90h+var_108]
0x1800b1e4d  xor     r13d, r13d
0x1800b1e50  test    rcx, rcx
0x1800b1e53  jz      short loc_1800B1E5F
0x1800b1e55  call    cs:__imp_SamCloseHandle
0x1800b1e5b  mov     [rbp+90h+var_108], r13
0x1800b1e5f  mov     rcx, [rsp+190h+var_118]
0x1800b1e64  test    rcx, rcx
0x1800b1e67  jz      short loc_1800B1E74
0x1800b1e69  call    cs:__imp_SamCloseHandle
0x1800b1e6f  mov     [rsp+190h+var_118], r13
0x1800b1e74  mov     rcx, [rbp+90h+PolicyHandle]; ObjectHandle
0x1800b1e78  test    rcx, rcx
0x1800b1e7b  jz      short loc_1800B1E87
0x1800b1e7d  call    cs:__imp_LsaClose
0x1800b1e83  mov     [rbp+90h+PolicyHandle], r13
0x1800b1e87  test    r15b, r15b
0x1800b1e8a  jz      short loc_1800B1E96
0x1800b1e8c  call    cs:__imp_RevertToSelf
0x1800b1e92  test    eax, eax
0x1800b1e94  jz      short loc_1800B1EDB
0x1800b1e96  mov     r15b, r13b
0x1800b1e99  call    ?KerbImpersonateNetworkService@@YAJXZ; KerbImpersonateNetworkService(void)
0x1800b1e9e  test    eax, eax
0x1800b1ea0  js      short loc_1800B1EDB
0x1800b1ea2  mov     r15b, 1
0x1800b1ea5  mov     r13b, r15b
0x1800b1ea8  jmp     loc_1800B1CAF
0x1800b1ead  xor     r13d, r13d
0x1800b1eb0  jmp     short loc_1800B1EDB
0x1800b1eb2  mov     ecx, 18h; size
0x1800b1eb7  call    MIDL_user_allocate
0x1800b1ebc  xor     r13d, r13d
0x1800b1ebf  mov     [r14], rax
0x1800b1ec2  test    rax, rax
0x1800b1ec5  jz      short loc_1800B1EDB
0x1800b1ec7  mov     rcx, [rbp+90h+var_E8]
0x1800b1ecb  movups  xmm0, xmmword ptr [rcx]
0x1800b1ece  movups  xmmword ptr [rax], xmm0
0x1800b1ed1  movsd   xmm1, qword ptr [rcx+10h]
0x1800b1ed6  movsd   qword ptr [rax+10h], xmm1
  ... truncated ...
```
