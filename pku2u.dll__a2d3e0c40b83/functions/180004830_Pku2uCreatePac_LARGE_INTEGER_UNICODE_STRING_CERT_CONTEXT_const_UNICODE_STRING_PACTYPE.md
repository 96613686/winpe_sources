# Pku2uCreatePac(_LARGE_INTEGER *,_UNICODE_STRING *,_CERT_CONTEXT const *,_UNICODE_STRING *,_PACTYPE * *)

- ea: `0x180004830`
- end: `0x180004c1c`
- name: `?Pku2uCreatePac@@YAJPEAT_LARGE_INTEGER@@PEAU_UNICODE_STRING@@PEBU_CERT_CONTEXT@@1PEAPEAU_PACTYPE@@@Z`
- size: `1004`
- prototype: `__int64 __fastcall(union _LARGE_INTEGER *, struct _UNICODE_STRING *, const struct _CERT_CONTEXT *, struct _UNICODE_STRING *, struct _PACTYPE **)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d5f8`
- `0x180035dc0`

## callees

- `0x180004830`
- `0x180004d60`
- `0x1800057f0`
- `0x180016860`
- `0x180019334`
- `0x18001b190`
- `0x18001fce8`
- `0x1800210f0`
- `0x180021a54`
- `0x180023ce0`
- `0x1800396bc`
- `0x18003970c`
- `0x180044434`
- `0x180046010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800049c0`
- `ntdll!RtlInitUnicodeString` at `0x1800049c0`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstMapCertificateToProvider` at `0x180004915`
- `ext-ms-win-security-certpoleng-l1-1-0!IntPstMapCertificateToProvider` at `0x180004915`

## pseudocode

```c
__int64 __fastcall Pku2uCreatePac(
        union _LARGE_INTEGER *a1,
        struct _UNICODE_STRING *a2,
        const struct _CERT_CONTEXT *a3,
        struct _UNICODE_STRING *a4,
        struct _PACTYPE **a5)
{
  struct _PAC_INFO_BUFFER *v8; // r14
  void *v9; // rsi
  int LogonServerName; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r13
  unsigned __int8 v14; // r8
  struct _UNICODE_STRING *v15; // rdi
  int v16; // eax
  _DWORD *v17; // rcx
  size_t v19; // [rsp+38h] [rbp-D0h]
  unsigned int v20; // [rsp+40h] [rbp-C8h]
  union _LARGE_INTEGER *v21; // [rsp+58h] [rbp-B0h]
  union _LARGE_INTEGER *v22; // [rsp+60h] [rbp-A8h]
  struct _LSA_LAST_INTER_LOGON_INFO *v23; // [rsp+68h] [rbp-A0h]
  __int64 v24; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v25; // [rsp+80h] [rbp-88h] BYREF
  void *v26; // [rsp+88h] [rbp-80h] BYREF
  struct _PAC_INFO_BUFFER *v27; // [rsp+90h] [rbp-78h] BYREF
  struct _UNICODE_STRING v28; // [rsp+98h] [rbp-70h] BYREF
  struct _UNICODE_STRING v29; // [rsp+A8h] [rbp-60h] BYREF
  union _LARGE_INTEGER *v30; // [rsp+B8h] [rbp-50h]
  struct _PACTYPE **v31; // [rsp+C0h] [rbp-48h]
  _DWORD v32[2]; // [rsp+C8h] [rbp-40h] BYREF
  _DWORD *v33; // [rsp+D0h] [rbp-38h]
  void *v34[2]; // [rsp+D8h] [rbp-30h] BYREF
  void *v35[2]; // [rsp+E8h] [rbp-20h] BYREF
  struct _UNICODE_STRING v36; // [rsp+F8h] [rbp-10h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+108h] [rbp+0h] BYREF
  int v38; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v39[44]; // [rsp+11Ch] [rbp+14h] BYREF
  struct _UNICODE_STRING v40; // [rsp+148h] [rbp+40h] BYREF
  __int128 v41; // [rsp+258h] [rbp+150h] BYREF

  v30 = a1;
  v31 = a5;
  v24 = 0;
  DestinationString = 0;
  v8 = 0;
  v27 = 0;
  v41 = 0;
  v38 = 0;
  *(_OWORD *)v34 = 0;
  *(_OWORD *)v35 = 0;
  memset_0(v39, 0, 0x138u);
  *(_QWORD *)&v29.Length = 2097182;
  v26 = 0;
  v29.Buffer = (PWSTR)L"WELLKNOWN:PKU2U";
  v36 = 0;
  v9 = 0;
  v25 = 0;
  v28 = 0;
  v32[1] = 0;
  *(_DWORD *)&a4->Length = 0;
  a4->Buffer = 0;
  LogonServerName = Pku2uGetLogonServerName(&v36);
  if ( LogonServerName >= 0 )
  {
    LogonServerName = IntPstMapCertificateToProvider(a3, &v41, 0);
    if ( LogonServerName >= 0 )
    {
      LogonServerName = (*((__int64 (__fastcall **)(__int128 *, _QWORD, const struct _CERT_CONTEXT *, __int64 *))Pku2uGlobalIdpExtTable
                         + 1))(
                          &v41,
                          0,
                          a3,
                          &v24);
      if ( LogonServerName >= 0 )
      {
        if ( *(_DWORD *)v24 != 2 )
        {
          LogonServerName = -1073741637;
          goto LABEL_27;
        }
        v13 = *(_QWORD *)(v24 + 8);
        RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v24 + 16));
        LogonServerName = KerbDuplicateStringEx2(&v28, &DestinationString, v14);
        if ( LogonServerName >= 0 )
        {
          v15 = &v28;
          if ( a2 )
            v15 = a2;
          v16 = Pku2uComputeDomainRelativeSid(*(PSID *)(v13 + 8), &v26, &v25);
          v9 = v26;
          LogonServerName = v16;
          if ( v16 >= 0 )
          {
            v17 = *(_DWORD **)(v13 + 24);
            if ( !v17
              || (v32[0] = *v17,
                  v33 = v17 + 2,
                  LogonServerName = Pku2uFilterGroupMembership(
                                      (struct _SID_AND_ATTRIBUTES_LIST *)v32,
                                      v26,
                                      (struct _SAMPR_GET_GROUPS_BUFFER *)v34,
                                      (struct _SID_AND_ATTRIBUTES_LIST *)v35,
                                      (unsigned int *)&v26),
                  LogonServerName >= 0) )
            {
              LogonServerName = Pku2uComputeUserInfo(v15, v25, v25, (struct _SAMPR_USER_ALL_INFORMATION *)&v38);
              if ( LogonServerName >= 0 )
              {
                LogonServerName = Pku2uBuildPacVerifier(v30, v15, &v27);
                if ( LogonServerName >= 0 )
                {
                  LogonServerName = PAC_InitEx2(
                                      (struct _SAMPR_USER_ALL_INFORMATION *)&v38,
                                      (struct _SAMPR_GET_GROUPS_BUFFER *)v34,
                                      (struct _SID_AND_ATTRIBUTES_LIST *)v35,
                                      v9,
                                      &v29,
                                      &v36,
                                      v19,
                                      v20,
                                      1u,
                                      &v27,
                                      v21,
                                      v22,
                                      v23,
                                      v31);
                  if ( LogonServerName >= 0 )
                  {
                    a4->Length = v28.Length;
                    a4->MaximumLength = v28.MaximumLength;
                    a4->Buffer = v28.Buffer;
                    v28.Buffer = 0;
                  }
                }
                v8 = v27;
              }
            }
          }
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v12 = 58;
            goto LABEL_16;
          }
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 57;
          goto LABEL_16;
        }
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 56;
LABEL_16:
        WPP_SF_d(v11[2], v12, &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids, (unsigned int)LogonServerName);
      }
    }
  }
LABEL_27:
  if ( v24 )
  {
    if ( *(_QWORD *)(v24 + 8) )
      ((void (*)(void))Pku2uGlobalLsaFunctions->FreeLsaHeap)();
    if ( *(_QWORD *)(v24 + 16) )
      ((void (*)(void))Pku2uGlobalLsaFunctions->FreeLsaHeap)();
    ((void (__fastcall *)(__int64))Pku2uGlobalLsaFunctions->FreeLsaHeap)(v24);
  }
  KerbFreeString(&v40);
  if ( v34[1] )
    Pku2uFree(v34[1]);
  if ( v35[1] )
    Pku2uFree(v35[1]);
  if ( v8 )
    Pku2uFree(v8);
  if ( v9 )
    Pku2uFree(v9);
  if ( v36.Buffer )
    Pku2uFree(v36.Buffer);
  if ( v28.Buffer )
    ((void (*)(void))Pku2uGlobalLsaFunctions->FreeLsaHeap)();
  return (unsigned int)LogonServerName;
}

```

## disassembly

```asm
0x180004830  mov     r11, rsp
0x180004833  push    rbp
0x180004834  push    rbx
0x180004835  lea     rbp, [r11-1A8h]
0x18000483c  sub     rsp, 298h
0x180004843  mov     rax, cs:__security_cookie
0x18000484a  xor     rax, rsp
0x18000484d  mov     [rbp+1A0h+var_40], rax
0x180004854  mov     rax, [rbp+1A0h+arg_20]
0x18000485b  xorps   xmm0, xmm0
0x18000485e  mov     [r11+8], rsi
0x180004862  xor     ebx, ebx
0x180004864  mov     [r11-18h], rdi
0x180004868  xorps   xmm1, xmm1
0x18000486b  mov     [r11-20h], r12
0x18000486f  mov     rdi, r8
0x180004872  mov     [r11-30h], r14
0x180004876  mov     r12, rdx
0x180004879  mov     [rbp+1A0h+var_1F0], rcx
0x18000487d  xor     edx, edx; Val
0x18000487f  mov     [r11-38h], r15
0x180004883  lea     rcx, [rbp+1A0h+var_18C]; void *
0x180004887  mov     r8d, 138h; Size
0x18000488d  mov     [rbp+1A0h+var_1E8], rax
0x180004891  mov     r15, r9
0x180004894  mov     [rsp+2A0h+var_230], rbx
0x180004899  movups  xmmword ptr [rbp+1A0h+DestinationString.Length], xmm0
0x18000489d  mov     r14d, ebx
0x1800048a0  mov     [rbp+1A0h+var_218], rbx
0x1800048a4  movups  [rbp+1A0h+var_50], xmm0
0x1800048ab  mov     [rbp+1A0h+var_190], ebx
0x1800048ae  movups  xmmword ptr [rbp+1A0h+var_1D0], xmm1
0x1800048b2  movups  xmmword ptr [rbp+1A0h+var_1C0], xmm0
0x1800048b6  call    memset_0
0x1800048bb  xorps   xmm0, xmm0
0x1800048be  mov     qword ptr [rbp+1A0h+var_200.Length], 20001Eh
0x1800048c6  lea     rax, WideCharStr; "WELLKNOWN:PKU2U"
0x1800048cd  mov     [rbp+1A0h+var_220], rbx
0x1800048d1  lea     rcx, [rbp+1A0h+var_1B0]; struct _UNICODE_STRING *
0x1800048d5  mov     [rbp+1A0h+var_200.Buffer], rax
0x1800048d9  movups  xmmword ptr [rbp+1A0h+var_1B0.Length], xmm0
0x1800048dd  mov     esi, ebx
0x1800048df  mov     [rsp+2A0h+var_228], ebx
0x1800048e3  movups  xmmword ptr [rbp+1A0h+var_210.Length], xmm0
0x1800048e7  mov     [rbp+1A0h+var_1DC], ebx
0x1800048ea  mov     [r15], ebx
0x1800048ed  mov     [r15+8], rbx
0x1800048f1  call    ?Pku2uGetLogonServerName@@YAJPEAU_UNICODE_STRING@@@Z; Pku2uGetLogonServerName(_UNICODE_STRING *)
0x1800048f6  mov     ebx, eax
0x1800048f8  test    eax, eax
0x1800048fa  js      loc_180004B1D
0x180004900  xor     r8d, r8d
0x180004903  mov     [rsp+2A0h+var_20], r13
0x18000490b  lea     rdx, [rbp+1A0h+var_50]
0x180004912  mov     rcx, rdi
0x180004915  call    cs:__imp_IntPstMapCertificateToProvider
0x18000491b  mov     ebx, eax
0x18000491d  test    eax, eax
0x18000491f  jns     short loc_18000494C
0x180004921  mov     rcx, cs:WPP_GLOBAL_Control
0x180004928  lea     rax, WPP_GLOBAL_Control
0x18000492f  cmp     rcx, rax
0x180004932  jz      loc_180004B15
0x180004938  test    byte ptr [rcx+1Ch], 1
0x18000493c  jz      loc_180004B15
0x180004942  mov     edx, 38h ; '8'
0x180004947  jmp     loc_1800049FF
0x18000494c  mov     rax, cs:?Pku2uGlobalIdpExtTable@@3PEAU_LSA_IF_IDPROVEXT_FUNCTION_TABLE@@EA; _LSA_IF_IDPROVEXT_FUNCTION_TABLE * Pku2uGlobalIdpExtTable
0x180004953  lea     r9, [rsp+2A0h+var_230]
0x180004958  mov     r8, rdi
0x18000495b  lea     rcx, [rbp+1A0h+var_50]
0x180004962  xor     edx, edx
0x180004964  mov     rax, [rax+8]
0x180004968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000496d  mov     ebx, eax
0x18000496f  test    eax, eax
0x180004971  jns     short loc_18000499B
0x180004973  mov     rcx, cs:WPP_GLOBAL_Control
0x18000497a  lea     rax, WPP_GLOBAL_Control
0x180004981  cmp     rcx, rax
0x180004984  jz      loc_180004B15
0x18000498a  test    byte ptr [rcx+1Ch], 1
0x18000498e  jz      loc_180004B15
0x180004994  mov     edx, 39h ; '9'
0x180004999  jmp     short loc_1800049FF
0x18000499b  mov     rax, [rsp+2A0h+var_230]
0x1800049a0  cmp     dword ptr [rax], 2
0x1800049a3  jz      short loc_1800049AF
0x1800049a5  mov     ebx, 0C00000BBh
0x1800049aa  jmp     loc_180004B15
0x1800049af  mov     rax, [rsp+2A0h+var_230]
0x1800049b4  lea     rcx, [rbp+1A0h+DestinationString]; DestinationString
0x1800049b8  mov     rdx, [rax+10h]; SourceString
0x1800049bc  mov     r13, [rax+8]
0x1800049c0  call    cs:__imp_RtlInitUnicodeString
0x1800049c6  lea     rdx, [rbp+1A0h+DestinationString]; struct _UNICODE_STRING *
0x1800049ca  lea     rcx, [rbp+1A0h+var_210]; struct _UNICODE_STRING *
0x1800049ce  call    ?KerbDuplicateStringEx2@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx2(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x1800049d3  mov     ebx, eax
0x1800049d5  test    eax, eax
0x1800049d7  jns     short loc_180004A17
0x1800049d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049e0  lea     rax, WPP_GLOBAL_Control
0x1800049e7  cmp     rcx, rax
0x1800049ea  jz      loc_180004B15
0x1800049f0  test    byte ptr [rcx+1Ch], 1
0x1800049f4  jz      loc_180004B15
0x1800049fa  mov     edx, 3Ah ; ':'
0x1800049ff  mov     rcx, [rcx+10h]
0x180004a03  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids
0x180004a0a  mov     r9d, ebx
0x180004a0d  call    WPP_SF_d
0x180004a12  jmp     loc_180004B15
0x180004a17  mov     rcx, [r13+8]; Sid
0x180004a1b  lea     rdi, [rbp+1A0h+var_210]
0x180004a1f  test    r12, r12
0x180004a22  lea     r8, [rsp+2A0h+var_228]; unsigned int *
0x180004a27  lea     rdx, [rbp+1A0h+var_220]; void **
0x180004a2b  cmovnz  rdi, r12
0x180004a2f  call    ?Pku2uComputeDomainRelativeSid@@YAJPEAXPEAPEAXPEAK@Z; Pku2uComputeDomainRelativeSid(void *,void * *,ulong *)
0x180004a34  mov     rsi, [rbp+1A0h+var_220]
0x180004a38  mov     ebx, eax
0x180004a3a  test    eax, eax
0x180004a3c  js      loc_180004B15
0x180004a42  mov     rcx, [r13+18h]
0x180004a46  test    rcx, rcx
0x180004a49  jz      short loc_180004A7F
0x180004a4b  mov     eax, [rcx]
0x180004a4d  lea     r9, [rbp+1A0h+var_1C0]; struct _SID_AND_ATTRIBUTES_LIST *
0x180004a51  mov     [rbp+1A0h+var_1E0], eax
0x180004a54  lea     r8, [rbp+1A0h+var_1D0]; struct _SAMPR_GET_GROUPS_BUFFER *
0x180004a58  lea     rax, [rcx+8]
0x180004a5c  mov     rdx, rsi; void *
0x180004a5f  mov     [rbp+1A0h+var_1D8], rax
0x180004a63  lea     rcx, [rbp+1A0h+var_1E0]; struct _SID_AND_ATTRIBUTES_LIST *
0x180004a67  lea     rax, [rbp+1A0h+var_220]
0x180004a6b  mov     [rsp+2A0h+var_280], rax; unsigned int *
0x180004a70  call    ?Pku2uFilterGroupMembership@@YAJPEAU_SID_AND_ATTRIBUTES_LIST@@PEAXPEAU_SAMPR_GET_GROUPS_BUFFER@@0PEAK@Z; Pku2uFilterGroupMembership(_SID_AND_ATTRIBUTES_LIST *,void *,_SAMPR_GET_GROUPS_BUFFER *,_SID_AND_ATTRIBUTES_LIST *,ulong *)
0x180004a75  mov     ebx, eax
0x180004a77  test    eax, eax
0x180004a79  js      loc_180004B15
0x180004a7f  mov     edx, [rsp+2A0h+var_228]; unsigned int
0x180004a83  lea     r9, [rbp+1A0h+var_190]; struct _SAMPR_USER_ALL_INFORMATION *
0x180004a87  mov     r8d, edx; unsigned int
0x180004a8a  mov     rcx, rdi; struct _UNICODE_STRING *
0x180004a8d  call    ?Pku2uComputeUserInfo@@YAJPEBU_UNICODE_STRING@@KKPEAU_SAMPR_USER_ALL_INFORMATION@@@Z; Pku2uComputeUserInfo(_UNICODE_STRING const *,ulong,ulong,_SAMPR_USER_ALL_INFORMATION *)
0x180004a92  mov     ebx, eax
0x180004a94  test    eax, eax
0x180004a96  js      short loc_180004B15
0x180004a98  mov     rcx, [rbp+1A0h+var_1F0]; union _LARGE_INTEGER *
0x180004a9c  lea     r8, [rbp+1A0h+var_218]; struct _PAC_INFO_BUFFER **
0x180004aa0  mov     rdx, rdi; struct _UNICODE_STRING *
0x180004aa3  call    ?Pku2uBuildPacVerifier@@YAJPEAT_LARGE_INTEGER@@PEBU_UNICODE_STRING@@PEAPEAU_PAC_INFO_BUFFER@@@Z; Pku2uBuildPacVerifier(_LARGE_INTEGER *,_UNICODE_STRING const *,_PAC_INFO_BUFFER * *)
0x180004aa8  mov     ebx, eax
0x180004aaa  test    eax, eax
0x180004aac  js      short loc_180004B11
0x180004aae  mov     rax, [rbp+1A0h+var_1E8]
0x180004ab2  lea     r8, [rbp+1A0h+var_1C0]; struct _SID_AND_ATTRIBUTES_LIST *
0x180004ab6  mov     [rsp+2A0h+var_238], rax; struct _PACTYPE **
0x180004abb  lea     rdx, [rbp+1A0h+var_1D0]; struct _SAMPR_GET_GROUPS_BUFFER *
0x180004abf  lea     rax, [rbp+1A0h+var_218]
0x180004ac3  mov     r9, rsi; void *
0x180004ac6  mov     [rsp+48h], rax; struct _PAC_INFO_BUFFER **
0x180004acb  lea     rcx, [rbp+1A0h+var_190]; struct _SAMPR_USER_ALL_INFORMATION *
0x180004acf  lea     rax, [rbp+1A0h+var_1B0]
0x180004ad3  mov     [rsp+2A0h+var_260], 1; unsigned int
0x180004adb  mov     [rsp+28h], rax; struct _UNICODE_STRING *
0x180004ae0  lea     rax, [rbp+1A0h+var_200]
0x180004ae4  mov     [rsp+2A0h+var_280], rax; struct _UNICODE_STRING *
0x180004ae9  call    ?PAC_InitEx2@@YAJPEAU_SAMPR_USER_ALL_INFORMATION@@PEAU_SAMPR_GET_GROUPS_BUFFER@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAXPEAU_UNICODE_STRING@@4KKKPEAPEAU_PAC_INFO_BUFFER@@PEAT_LARGE_INTEGER@@6PEAU_LSA_LAST_INTER_LOGON_INFO@@PEAPEAU_PACTYPE@@@Z; PAC_InitEx2(_SAMPR_USER_ALL_INFORMATION *,_SAMPR_GET_GROUPS_BUFFER *,_SID_AND_ATTRIBUTES_LIST *,void *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,ulong,_PAC_INFO_BUFFER * *,_LARGE_INTEGER *,_LARGE_INTEGER *,_LSA_LAST_INTER_LOGON_INFO *,_PACTYPE * *)
0x180004aee  mov     ebx, eax
0x180004af0  test    eax, eax
0x180004af2  js      short loc_180004B11
0x180004af4  movzx   eax, [rbp+1A0h+var_210.Length]
0x180004af8  mov     [r15], ax
0x180004afc  movzx   eax, [rbp+1A0h+var_210.MaximumLength]
0x180004b00  mov     [r15+2], ax
0x180004b05  mov     rax, [rbp+1A0h+var_210.Buffer]
0x180004b09  mov     [r15+8], rax
0x180004b0d  mov     [rbp+1A0h+var_210.Buffer], r14
0x180004b11  mov     r14, [rbp+1A0h+var_218]
0x180004b15  mov     r13, [rsp+2A0h+var_20]
0x180004b1d  mov     rax, [rsp+2A0h+var_230]
0x180004b22  mov     r15, [rsp+2A0h+var_30]
0x180004b2a  mov     r12, [rsp+2A0h+var_18]
0x180004b32  mov     rdi, [rsp+290h]
0x180004b3a  test    rax, rax
0x180004b3d  jz      short loc_180004B8B
0x180004b3f  mov     rcx, [rax+8]
0x180004b43  test    rcx, rcx
0x180004b46  jz      short loc_180004B58
0x180004b48  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x180004b4f  mov     rax, [rax+30h]
0x180004b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b58  mov     rax, [rsp+2A0h+var_230]
0x180004b5d  mov     rcx, [rax+10h]
0x180004b61  test    rcx, rcx
0x180004b64  jz      short loc_180004B76
0x180004b66  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x180004b6d  mov     rax, [rax+30h]
0x180004b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b76  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x180004b7d  mov     rcx, [rsp+2A0h+var_230]
0x180004b82  mov     rax, [rax+30h]
0x180004b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b8b  lea     rcx, [rbp+1A0h+var_160]; struct _UNICODE_STRING *
0x180004b8f  call    ?KerbFreeString@@YAXPEAU_UNICODE_STRING@@@Z; KerbFreeString(_UNICODE_STRING *)
0x180004b94  mov     rcx, [rbp+1A0h+var_1D0+8]; void *
0x180004b98  test    rcx, rcx
0x180004b9b  jz      short loc_180004BA2
0x180004b9d  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180004ba2  mov     rcx, [rbp+1A0h+var_1C0+8]; void *
0x180004ba6  test    rcx, rcx
0x180004ba9  jz      short loc_180004BB0
0x180004bab  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180004bb0  test    r14, r14
0x180004bb3  jz      short loc_180004BBD
0x180004bb5  mov     rcx, r14; void *
0x180004bb8  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180004bbd  mov     r14, [rsp+2A0h+var_28]
0x180004bc5  test    rsi, rsi
0x180004bc8  jz      short loc_180004BD2
0x180004bca  mov     rcx, rsi; void *
0x180004bcd  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180004bd2  mov     rcx, [rbp+1A0h+var_1B0.Buffer]; void *
0x180004bd6  mov     rsi, [rsp+2A0h+arg_0]
0x180004bde  test    rcx, rcx
0x180004be1  jz      short loc_180004BE8
0x180004be3  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180004be8  mov     rcx, [rbp+1A0h+var_210.Buffer]
0x180004bec  test    rcx, rcx
0x180004bef  jz      short loc_180004C01
0x180004bf1  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x180004bf8  mov     rax, [rax+30h]
0x180004bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c01  mov     eax, ebx
0x180004c03  mov     rcx, [rbp+1A0h+var_40]
0x180004c0a  xor     rcx, rsp; StackCookie
0x180004c0d  call    __security_check_cookie
0x180004c12  add     rsp, 298h
0x180004c19  pop     rbx
0x180004c1a  pop     rbp
0x180004c1b  retn
```
