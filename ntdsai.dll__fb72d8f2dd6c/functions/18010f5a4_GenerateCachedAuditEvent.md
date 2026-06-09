# GenerateCachedAuditEvent

- ea: `0x18010f5a4`
- end: `0x18010fd5b`
- name: `GenerateCachedAuditEvent`
- size: `1975`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800434d8`
- `0x18007bdd4`
- `0x1800c5fd8`
- `0x1800c6054`

## callees

- `0x180006330`
- `0x18001e090`
- `0x18001ea60`
- `0x18002a010`
- `0x180035f7c`
- `0x18010f29c`
- `0x18010f5a4`
- `0x18010feec`
- `0x18011cc00`
- `0x180126038`
- `0x18016af30`
- `0x180172edc`
- `0x180173e2c`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`
- `0x1804533b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18010f65d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18010fa5d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18010f65d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18010fa5d`
- `RPCRT4!UuidCreate` at `0x18010f6b6`
- `RPCRT4!UuidCreate` at `0x18010f6b6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18010fa27`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18010fa27`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18010fbb8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18010fbb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010fc15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010fc15`
- `AUTHZ!AuthzGetInformationFromContext` at `0x18010fc08`
- `AUTHZ!AuthzGetInformationFromContext` at `0x18010fc08`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18010f6db`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18010f6db`

## pseudocode

```c
__int64 __fastcall GenerateCachedAuditEvent(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        const wchar_t *a4,
        __int64 a5,
        int a6,
        int a7,
        const wchar_t *a8,
        const wchar_t *a9,
        int a10,
        int a11,
        _QWORD *a12)
{
  const wchar_t *v14; // r12
  const wchar_t *v15; // r15
  DWORD v16; // edi
  char *v18; // rax
  char *v19; // rbx
  UUID *v20; // rcx
  RPC_STATUS v21; // eax
  DWORD v22; // eax
  LPOVERLAPPED v23; // rbx
  __int64 ObjectDN; // rax
  __int64 v25; // rdx
  int v26; // r9d
  const wchar_t *v27; // r14
  __int64 v28; // r8
  const wchar_t *v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  int v34; // edi
  int v35; // r12d
  void **v36; // r15
  DWORD LengthSid; // eax
  unsigned int v38; // ecx
  unsigned int v39; // r12d
  wchar_t *v40; // rdi
  __int64 v41; // r11
  __int64 v42; // r11
  __int64 v43; // r11
  __int64 v44; // r11
  void *v45; // rdi
  int v46; // r14d
  void *v47; // r8
  BOOL InformationFromContext; // eax
  _QWORD *v49; // rcx
  _QWORD *i; // rax
  __int64 v51; // [rsp+0h] [rbp-3B8h] BYREF
  DWORD AuthzContextHandle; // [rsp+30h] [rbp-388h]
  DWORD nDestinationSidLength; // [rsp+34h] [rbp-384h] BYREF
  size_t cbDest; // [rsp+38h] [rbp-380h]
  size_t v55; // [rsp+40h] [rbp-378h]
  STRSAFE_LPCWSTR v56; // [rsp+48h] [rbp-370h]
  size_t v57; // [rsp+50h] [rbp-368h] BYREF
  __int64 *v58; // [rsp+58h] [rbp-360h]
  PSID *v59; // [rsp+60h] [rbp-358h] BYREF
  size_t v60; // [rsp+68h] [rbp-350h]
  DWORD pSizeRequired[4]; // [rsp+70h] [rbp-348h] BYREF
  __int64 v62; // [rsp+80h] [rbp-338h]
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+88h] [rbp-330h] BYREF
  __int64 v64; // [rsp+90h] [rbp-328h] BYREF
  __int64 v65; // [rsp+98h] [rbp-320h]
  __int64 v66; // [rsp+A0h] [rbp-318h]
  STRSAFE_LPCWSTR pszSrc; // [rsp+A8h] [rbp-310h]
  STRSAFE_LPCWSTR v68; // [rsp+B0h] [rbp-308h]
  __int64 v69; // [rsp+B8h] [rbp-300h]
  void *Block; // [rsp+C0h] [rbp-2F8h]
  __int64 v71; // [rsp+D0h] [rbp-2E8h] BYREF
  int v72; // [rsp+D8h] [rbp-2E0h]
  int Internal; // [rsp+DCh] [rbp-2DCh]
  __int64 v74; // [rsp+E0h] [rbp-2D8h]
  int v75; // [rsp+E8h] [rbp-2D0h]
  int v76; // [rsp+ECh] [rbp-2CCh]
  __int64 v77; // [rsp+F0h] [rbp-2C8h]
  __int64 v78; // [rsp+F8h] [rbp-2C0h]
  __int64 v79; // [rsp+100h] [rbp-2B8h]
  __int64 v80; // [rsp+108h] [rbp-2B0h]
  __int64 v81; // [rsp+110h] [rbp-2A8h]
  int v82; // [rsp+118h] [rbp-2A0h]
  __int64 v83; // [rsp+11Ch] [rbp-29Ch]
  int v84; // [rsp+124h] [rbp-294h]
  int *v85; // [rsp+128h] [rbp-290h]
  const wchar_t *v86; // [rsp+130h] [rbp-288h]
  wchar_t *v87; // [rsp+138h] [rbp-280h]
  int v88; // [rsp+150h] [rbp-268h] BYREF
  __int64 *v89; // [rsp+158h] [rbp-260h]
  __int64 v90; // [rsp+168h] [rbp-250h] BYREF
  int v91; // [rsp+170h] [rbp-248h]
  const wchar_t *v92; // [rsp+178h] [rbp-240h]
  int v93; // [rsp+190h] [rbp-228h]
  const wchar_t *v94; // [rsp+198h] [rbp-220h]
  int v95; // [rsp+1B0h] [rbp-208h]
  const wchar_t *v96; // [rsp+1B8h] [rbp-200h]

  v58 = &v51;
  v65 = (__int64)a4;
  v14 = a9;
  v68 = a9;
  v15 = a8;
  pszSrc = a8;
  v66 = a1;
  pSizeRequired[2] = 0;
  pSizeRequired[1] = 0;
  nDestinationSidLength = 0;
  v64 = 0;
  pSizeRequired[0] = 0;
  v59 = 0;
  hAuthzClientContext = 0;
  DetermineAuditTypes(a2, a3, &nDestinationSidLength, &v57);
  v16 = nDestinationSidLength;
  if ( !nDestinationSidLength )
    return 0;
  v18 = (char *)malloc(0xA8u);
  v19 = v18;
  Block = v18;
  if ( v18 )
  {
    memset_0(v18 + 28, 0, 0x8Cu);
    *(_QWORD *)v19 = 0;
    *((_QWORD *)v19 + 1) = 0;
    *((_DWORD *)v19 + 4) = 0;
    *((_DWORD *)v19 + 5) = v16;
    *((_DWORD *)v19 + 6) = 0;
    if ( (unsigned int)fNullUuid(a1 + 6072) )
    {
      v21 = UuidCreate(v20);
      AuthzContextHandle = v21;
      if ( v21 )
      {
        if ( v21 != 1824 )
          goto LABEL_83;
      }
    }
    v22 = WaitForSingleObject(hsemDirAuditQueue, 0x1F4u);
    AuthzContextHandle = v22;
    if ( v22 )
    {
      if ( v22 != 258 )
        goto LABEL_83;
      v23 = gpDsEventConfig;
      if ( !gpDsEventConfig )
        goto LABEL_83;
      if ( (gpDsEventConfig[1].Internal & 0x8000000000000000uLL) != 0LL
        && (!HIDWORD(gpDsEventConfig->Internal) || !(unsigned int)DoLogOverride(828, 0)) )
      {
        if ( !(unsigned int)DoLogMsgOverride(3221228338LL) )
          goto LABEL_83;
        v23 = gpDsEventConfig;
      }
      v74 = 0;
      v80 = 0;
      v83 = 0;
      v84 = 0;
      Internal = v23[1].Internal;
      v72 = -1073738958;
      v75 = 0;
      v76 = 1;
      v85 = &v88;
      v88 = 3;
      v90 = (unsigned int)gdwMaxAuditQueueLength;
      v89 = &v90;
      if ( a4 )
      {
        v91 = 6;
        v92 = a4;
      }
      else
      {
        v91 = 1;
        v92 = L"-";
      }
      v93 = 1;
      if ( !a8 )
        v15 = L"-";
      v94 = v15;
      v95 = 1;
      if ( !a9 )
        v14 = L"-";
      v96 = v14;
      v71 = 4;
      v79 = 0;
      v78 = 828;
      v77 = 1;
      v81 = 0;
      v82 = 0;
      DoLogEventAndTrace(&v71);
      goto LABEL_83;
    }
    v56 = 0;
    v62 = 0;
    ++*(_DWORD *)(a1 + 6108);
    *(_OWORD *)(v19 + 28) = *(_OWORD *)(a1 + 6072);
    if ( a7 != 8 || (v62 = qword_18052B430) != 0 )
    {
      AuthzContextHandle = GetAuthzContextHandle(a1, &hAuthzClientContext);
      if ( AuthzContextHandle )
        local_unwind_0(v58, &loc_18010FD27);
      AuthzContextHandle = AuthzGetInfoHelper(a1, hAuthzClientContext, 1, &v59);
      if ( AuthzContextHandle )
        local_unwind_0(v58, &loc_18010FD27);
      ObjectDN = GetObjectDN(a4, &v64);
      v69 = ObjectDN;
      v27 = L"-";
      v28 = 0;
      if ( ObjectDN )
        v27 = (const wchar_t *)ObjectDN;
      v69 = (__int64)v27;
      if ( *(_DWORD *)gfADAM )
      {
        v29 = (const wchar_t *)ADAMGetUserDN(a1, v25, 0);
        v56 = v29;
        v86 = v29;
        v28 = 0;
      }
      else
      {
        v29 = v56;
      }
      v30 = -1;
      if ( a8 )
      {
        v31 = -1;
        do
          ++v31;
        while ( a8[v31] );
        LODWORD(cbDest) = 2 * v31 + 2;
      }
      else
      {
        LODWORD(cbDest) = 0;
      }
      if ( a9 )
      {
        v32 = -1;
        do
          ++v32;
        while ( a9[v32] );
        LODWORD(v55) = 2 * v32 + 2;
      }
      else
      {
        LODWORD(v55) = 0;
      }
      if ( v29 )
      {
        v33 = -1;
        do
          ++v33;
        while ( v29[v33] );
        v34 = 2 * v33 + 2;
        LODWORD(v60) = v34;
      }
      else
      {
        v34 = 0;
        LODWORD(v60) = 0;
      }
      do
        ++v30;
      while ( v27[v30] );
      v35 = 2 * v30 + 2;
      LODWORD(v57) = v35;
      v36 = v59;
      if ( a7 == 8 )
      {
        LengthSid = *(_DWORD *)(v62 + 4);
      }
      else
      {
        LengthSid = GetLengthSid(*v59);
        v28 = 0;
      }
      nDestinationSidLength = LengthSid;
      v38 = cbDest + v55 + v34 + v35 + LengthSid;
      v39 = v38 + 11;
      if ( v38 + 11 >= v38 )
      {
        if ( v38 == -11 )
        {
          v46 = a7;
        }
        else
        {
          v40 = (wchar_t *)malloc(v39);
          if ( !v40 )
          {
            AuthzContextHandle = 14;
            local_unwind_0(v58, &loc_18010FD27);
          }
          *((_QWORD *)v19 + 19) = v40;
          *((_DWORD *)v19 + 40) = v39;
          if ( pszSrc )
          {
            StringCbCopyW(v40, (unsigned int)cbDest, pszSrc);
            *((_QWORD *)v19 + 14) = v40;
            pszSrc = v40;
            v40 = (wchar_t *)(((unsigned __int64)v40 + v41 + 1) & 0xFFFFFFFFFFFFFFFEuLL);
            cbDest = (size_t)v40;
          }
          if ( v68 )
          {
            StringCbCopyW(v40, (unsigned int)v55, v68);
            *((_QWORD *)v19 + 15) = v40;
            v68 = v40;
            v40 = (wchar_t *)(((unsigned __int64)v40 + v42 + 1) & 0xFFFFFFFFFFFFFFFEuLL);
            v55 = (size_t)v40;
          }
          if ( v56 )
          {
            StringCbCopyW(v40, (unsigned int)v60, v56);
            *((_QWORD *)v19 + 8) = v40;
            v60 = (size_t)v40;
            v40 = (wchar_t *)(((unsigned __int64)v40 + v43 + 1) & 0xFFFFFFFFFFFFFFFEuLL);
            v56 = v40;
          }
          StringCbCopyW(v40, (unsigned int)v57, v27);
          *((_QWORD *)v19 + 12) = v40;
          v87 = v40;
          v45 = (void *)(((unsigned __int64)v40 + v44 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
          v57 = (size_t)v45;
          v46 = a7;
          if ( a7 == 8 )
            v47 = (void *)(v62 + 24);
          else
            v47 = *v36;
          CopySid(nDestinationSidLength, v45, v47);
          *((_QWORD *)v19 + 6) = v45;
          v28 = 0;
        }
        *((_DWORD *)v19 + 18) = *(_DWORD *)(a5 + 20);
        if ( (*(_DWORD *)(a1 + 5612) & 0x200000) == 0 )
        {
          InformationFromContext = AuthzGetInformationFromContext(
                                     hAuthzClientContext,
                                     AuthzContextInfoAuthenticationId,
                                     8u,
                                     pSizeRequired,
                                     v19 + 56);
          v28 = 0;
          if ( !InformationFromContext )
          {
            AuthzContextHandle = GetLastError();
            local_unwind_0(v58, &loc_18010FD27);
          }
        }
        *(_OWORD *)(v19 + 76) = *(_OWORD *)(v65 + 8);
        *((_DWORD *)v19 + 36) = a6;
        *((_DWORD *)v19 + 26) = v46;
        *((_DWORD *)v19 + 32) = a10;
        *((_DWORD *)v19 + 35) = a11;
        if ( a12 )
        {
          v65 = v28;
          v65 = 10000000LL * *a12;
          *(_QWORD *)(v19 + 132) = v65;
        }
        v49 = (_QWORD *)(a1 + 6016);
        for ( i = *(_QWORD **)(a1 + 6016); i; i = (_QWORD *)*i )
          v49 = i;
        *v49 = v19;
        ++*(_DWORD *)(a1 + 6104);
        if ( v64 )
          THFreeAux(a1, v64, v28, v26, 54264666);
        if ( v36 )
          THFreeAux(a1, (_DWORD)v36, v28, v26, 54264670);
        return AuthzContextHandle;
      }
      AuthzContextHandle = 534;
      local_unwind_0(v58, &loc_18010FD27);
      local_unwind_0(v58, &loc_18010FD27);
    }
    else
    {
      AuthzContextHandle = 12;
    }
  }
  else
  {
    AuthzContextHandle = 14;
  }
LABEL_83:
  FreeCachedAuditEvent(Block);
  return AuthzContextHandle;
}

```

## disassembly

```asm
0x18010f5a4  push    rbx
0x18010f5a6  push    rsi
0x18010f5a7  push    rdi
0x18010f5a8  push    r12
0x18010f5aa  push    r13
0x18010f5ac  push    r14
0x18010f5ae  push    r15
0x18010f5b0  sub     rsp, 380h
0x18010f5b7  mov     rax, cs:__security_cookie
0x18010f5be  xor     rax, rsp
0x18010f5c1  mov     [rsp+3B8h+var_48], rax
0x18010f5c9  mov     [rsp+3B8h+var_360], rsp
0x18010f5ce  mov     r14, r9
0x18010f5d1  mov     [rsp+3B8h+var_320], r9
0x18010f5d9  mov     r10, r8
0x18010f5dc  mov     eax, edx
0x18010f5de  mov     rsi, rcx
0x18010f5e1  mov     r12, [rsp+3B8h+arg_40]
0x18010f5e9  mov     [rsp+3B8h+var_308], r12
0x18010f5f1  mov     r15, [rsp+3B8h+arg_38]
0x18010f5f9  mov     [rsp+3B8h+pszSrc], r15
0x18010f601  mov     [rsp+3B8h+var_318], rcx
0x18010f609  xor     r13d, r13d
0x18010f60c  mov     [rsp+3B8h+var_340], r13d
0x18010f611  mov     [rsp+3B8h+var_344], r13d
0x18010f616  mov     [rsp+3B8h+nDestinationSidLength], r13d
0x18010f61b  mov     [rsp+3B8h+var_328], r13
0x18010f623  mov     [rsp+3B8h+pSizeRequired], r13d
0x18010f628  mov     [rsp+3B8h+var_358], r13
0x18010f62d  mov     [rsp+3B8h+hAuthzClientContext], r13
0x18010f635  lea     r9, [rsp+3B8h+var_368]
0x18010f63a  lea     r8, [rsp+3B8h+nDestinationSidLength]
0x18010f63f  mov     rdx, r10
0x18010f642  mov     ecx, eax
0x18010f644  call    DetermineAuditTypes
0x18010f649  mov     edi, [rsp+3B8h+nDestinationSidLength]
0x18010f64d  test    edi, edi
0x18010f64f  jnz     short loc_18010F658
0x18010f651  xor     eax, eax
0x18010f653  jmp     loc_18010FD38
0x18010f658  mov     ecx, 0A8h; Size
0x18010f65d  call    cs:__imp_malloc
0x18010f663  mov     rbx, rax
0x18010f666  mov     [rsp+3B8h+Block], rax
0x18010f66e  test    rax, rax
0x18010f671  jnz     short loc_18010F680
0x18010f673  mov     [rsp+3B8h+var_388], 0Eh
0x18010f67b  jmp     loc_18010FD27
0x18010f680  lea     rcx, [rax+1Ch]; void *
0x18010f684  xor     edx, edx; Val
0x18010f686  mov     r8d, 8Ch; Size
0x18010f68c  call    memset_0
0x18010f691  mov     [rbx], r13
0x18010f694  mov     [rbx+8], r13
0x18010f698  mov     [rbx+10h], r13d
0x18010f69c  mov     [rbx+14h], edi
0x18010f69f  mov     [rbx+18h], r13d
0x18010f6a3  lea     rdi, [rsi+17B8h]
0x18010f6aa  mov     rcx, rdi
0x18010f6ad  call    fNullUuid
0x18010f6b2  test    eax, eax
0x18010f6b4  jz      short loc_18010F6CF
0x18010f6b6  call    cs:__imp_UuidCreate
0x18010f6bc  mov     [rsp+3B8h+var_388], eax
0x18010f6c0  test    eax, eax
0x18010f6c2  jz      short loc_18010F6CF
0x18010f6c4  cmp     eax, 720h
0x18010f6c9  jnz     loc_18010FD27
0x18010f6cf  mov     edx, 1F4h; dwMilliseconds
0x18010f6d4  mov     rcx, cs:hsemDirAuditQueue; hHandle
0x18010f6db  call    cs:__imp_WaitForSingleObject
0x18010f6e1  mov     [rsp+3B8h+var_388], eax
0x18010f6e5  test    eax, eax
0x18010f6e7  jz      loc_18010F873
0x18010f6ed  cmp     eax, 102h
0x18010f6f2  jnz     loc_18010FD27
0x18010f6f8  mov     rbx, cs:gpDsEventConfig
0x18010f6ff  test    rbx, rbx
0x18010f702  jz      loc_18010FD27
0x18010f708  cmp     [rbx+24h], r13d
0x18010f70c  jge     short loc_18010F73D
0x18010f70e  cmp     [rbx+4], r13d
0x18010f712  jz      short loc_18010F724
0x18010f714  xor     edx, edx
0x18010f716  mov     ecx, 33Ch
0x18010f71b  call    DoLogOverride
0x18010f720  test    eax, eax
0x18010f722  jnz     short loc_18010F73D
0x18010f724  mov     ecx, 0C0000B32h
0x18010f729  call    DoLogMsgOverride
0x18010f72e  test    eax, eax
0x18010f730  jz      loc_18010FD27
0x18010f736  mov     rbx, cs:gpDsEventConfig
0x18010f73d  xor     eax, eax
0x18010f73f  mov     [rsp+3B8h+var_2D8], rax
0x18010f747  mov     [rsp+3B8h+var_2B0], rax
0x18010f74f  mov     [rsp+3B8h+var_29C], rax
0x18010f757  mov     [rsp+3B8h+var_294], eax
0x18010f75e  mov     eax, [rbx+20h]
0x18010f761  mov     [rsp+3B8h+var_2DC], eax
0x18010f768  mov     [rsp+3B8h+var_2E0], 0C0000B32h
0x18010f773  mov     [rsp+3B8h+var_2D0], r13d
0x18010f77b  mov     r13d, 1
0x18010f781  mov     [rsp+3B8h+var_2CC], r13d
0x18010f789  lea     rax, [rsp+3B8h+var_268]
0x18010f791  mov     [rsp+3B8h+var_290], rax
0x18010f799  mov     [rsp+3B8h+var_268], 3
0x18010f7a4  mov     eax, cs:gdwMaxAuditQueueLength
0x18010f7aa  mov     [rsp+3B8h+var_250], rax
0x18010f7b2  lea     rax, [rsp+3B8h+var_250]
0x18010f7ba  mov     [rsp+3B8h+var_260], rax
0x18010f7c2  xor     eax, eax
0x18010f7c4  test    r14, r14
0x18010f7c7  jz      short loc_18010F7E5
0x18010f7c9  mov     [rsp+3B8h+var_248], 6
0x18010f7d4  mov     [rsp+3B8h+var_240], r14
0x18010f7dc  lea     r14, asc_1804AB17C; "-"
0x18010f7e3  jmp     short loc_18010F7FC
0x18010f7e5  mov     [rsp+3B8h+var_248], r13d
0x18010f7ed  lea     r14, asc_1804AB17C; "-"
0x18010f7f4  mov     [rsp+3B8h+var_240], r14
0x18010f7fc  mov     [rsp+3B8h+var_228], r13d
0x18010f804  test    r15, r15
0x18010f807  cmovz   r15, r14
0x18010f80b  mov     [rsp+3B8h+var_220], r15
0x18010f813  mov     [rsp+3B8h+var_208], r13d
0x18010f81b  test    r12, r12
0x18010f81e  cmovz   r12, r14
0x18010f822  mov     [rsp+3B8h+var_200], r12
0x18010f82a  mov     [rsp+3B8h+var_2E8], 4
0x18010f836  mov     [rsp+3B8h+var_2B8], rax
0x18010f83e  mov     [rsp+3B8h+var_2C0], 33Ch
0x18010f84a  mov     [rsp+3B8h+var_2C8], r13
0x18010f852  mov     [rsp+3B8h+var_2A8], rax
0x18010f85a  mov     [rsp+3B8h+var_2A0], eax
0x18010f861  lea     rcx, [rsp+3B8h+var_2E8]
0x18010f869  call    DoLogEventAndTrace
0x18010f86e  jmp     loc_18010FD27
0x18010f873  mov     [rsp+3B8h+var_370], r13
0x18010f878  mov     [rsp+3B8h+var_338], r13
0x18010f880  mov     r13d, 1
0x18010f886  add     [rsi+17DCh], r13d
0x18010f88d  movups  xmm0, xmmword ptr [rdi]
0x18010f890  movdqu  xmmword ptr [rbx+1Ch], xmm0
0x18010f895  cmp     [rsp+3B8h+arg_30], 8
0x18010f89d  jnz     short loc_18010F8C0
0x18010f89f  mov     rax, cs:qword_18052B430
0x18010f8a6  mov     [rsp+3B8h+var_338], rax
0x18010f8ae  test    rax, rax
0x18010f8b1  jnz     short loc_18010F8C0
0x18010f8b3  mov     [rsp+3B8h+var_388], 0Ch
0x18010f8bb  jmp     loc_18010FD27
0x18010f8c0  lea     rdx, [rsp+3B8h+hAuthzClientContext]
0x18010f8c8  mov     rcx, rsi
0x18010f8cb  call    GetAuthzContextHandle
0x18010f8d0  mov     [rsp+3B8h+var_388], eax
0x18010f8d4  mov     eax, [rsp+3B8h+var_388]
0x18010f8d8  test    eax, eax
0x18010f8da  jz      short loc_18010F8ED
0x18010f8dc  lea     rdx, loc_18010FD27
0x18010f8e3  mov     rcx, [rsp+3B8h+var_360]
0x18010f8e8  call    _local_unwind_0
0x18010f8ed  lea     r9, [rsp+3B8h+var_358]
0x18010f8f2  mov     r8d, r13d
0x18010f8f5  mov     rdx, [rsp+3B8h+hAuthzClientContext]
0x18010f8fd  mov     rcx, rsi
0x18010f900  call    AuthzGetInfoHelper
0x18010f905  mov     [rsp+3B8h+var_388], eax
0x18010f909  mov     eax, [rsp+3B8h+var_388]
0x18010f90d  test    eax, eax
0x18010f90f  jz      short loc_18010F922
0x18010f911  lea     rdx, loc_18010FD27
0x18010f918  mov     rcx, [rsp+3B8h+var_360]
0x18010f91d  call    _local_unwind_0
0x18010f922  lea     rdx, [rsp+3B8h+var_328]
0x18010f92a  mov     rcx, r14
0x18010f92d  call    GetObjectDN
0x18010f932  mov     [rsp+3B8h+var_300], rax
0x18010f93a  lea     r14, asc_1804AB17C; "-"
0x18010f941  xor     r8d, r8d
0x18010f944  test    rax, rax
0x18010f947  cmovnz  r14, rax
0x18010f94b  mov     [rsp+3B8h+var_300], r14
0x18010f953  cmp     cs:gfADAM, r8d
0x18010f95a  jz      short loc_18010F979
0x18010f95c  mov     rcx, rsi
0x18010f95f  call    ADAMGetUserDN
0x18010f964  mov     rdx, rax
0x18010f967  mov     [rsp+3B8h+var_370], rax
0x18010f96c  mov     [rsp+3B8h+var_288], rax
0x18010f974  xor     r8d, r8d
0x18010f977  jmp     short loc_18010F97E
0x18010f979  mov     rdx, [rsp+3B8h+var_370]
0x18010f97e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010f982  test    r15, r15
0x18010f985  jz      short loc_18010F9A1
0x18010f987  mov     rcx, rax
0x18010f98a  inc     rcx
0x18010f98d  cmp     [r15+rcx*2], r8w
0x18010f992  jnz     short loc_18010F98A
0x18010f994  lea     ecx, ds:2[rcx*2]
0x18010f99b  mov     dword ptr [rsp+3B8h+cbDest], ecx
0x18010f99f  jmp     short loc_18010F9A6
0x18010f9a1  mov     dword ptr [rsp+3B8h+cbDest], r8d
0x18010f9a6  test    r12, r12
0x18010f9a9  jz      short loc_18010F9C5
0x18010f9ab  mov     rcx, rax
0x18010f9ae  inc     rcx
0x18010f9b1  cmp     [r12+rcx*2], r8w
0x18010f9b6  jnz     short loc_18010F9AE
0x18010f9b8  lea     ecx, ds:2[rcx*2]
0x18010f9bf  mov     dword ptr [rsp+3B8h+var_378], ecx
0x18010f9c3  jmp     short loc_18010F9CA
0x18010f9c5  mov     dword ptr [rsp+3B8h+var_378], r8d
0x18010f9ca  test    rdx, rdx
0x18010f9cd  jz      short loc_18010F9E9
0x18010f9cf  mov     rcx, rax
0x18010f9d2  inc     rcx
0x18010f9d5  cmp     [rdx+rcx*2], r8w
0x18010f9da  jnz     short loc_18010F9D2
0x18010f9dc  lea     edi, ds:2[rcx*2]
0x18010f9e3  mov     dword ptr [rsp+3B8h+var_350], edi
0x18010f9e7  jmp     short loc_18010F9F1
0x18010f9e9  mov     edi, r8d
0x18010f9ec  mov     dword ptr [rsp+3B8h+var_350], r8d
0x18010f9f1  inc     rax
0x18010f9f4  cmp     [r14+rax*2], r8w
0x18010f9f9  jnz     short loc_18010F9F1
0x18010f9fb  lea     r12d, ds:2[rax*2]
0x18010fa03  mov     dword ptr [rsp+3B8h+var_368], r12d
0x18010fa08  mov     r15, [rsp+3B8h+var_358]
0x18010fa0d  cmp     [rsp+3B8h+arg_30], 8
0x18010fa15  jnz     short loc_18010FA24
0x18010fa17  mov     rax, [rsp+3B8h+var_338]
0x18010fa1f  mov     eax, [rax+4]
0x18010fa22  jmp     short loc_18010FA30
0x18010fa24  mov     rcx, [r15]; pSid
0x18010fa27  call    cs:__imp_GetLengthSid
0x18010fa2d  xor     r8d, r8d
0x18010fa30  mov     [rsp+3B8h+nDestinationSidLength], eax
0x18010fa34  lea     ecx, [r12+rax]
0x18010fa38  add     ecx, edi
0x18010fa3a  add     ecx, dword ptr [rsp+3B8h+var_378]
0x18010fa3e  mov     eax, dword ptr [rsp+3B8h+cbDest]
0x18010fa42  add     ecx, eax
0x18010fa44  lea     r12d, [rcx+0Bh]
0x18010fa48  cmp     r12d, ecx
0x18010fa4b  jb      loc_18010FCFB
0x18010fa51  test    r12d, r12d
0x18010fa54  jz      loc_18010FBC7
0x18010fa5a  mov     ecx, r12d; Size
0x18010fa5d  call    cs:__imp_malloc
0x18010fa63  mov     rdi, rax
0x18010fa66  test    rax, rax
0x18010fa69  jnz     short loc_18010FA84
0x18010fa6b  mov     [rsp+3B8h+var_388], 0Eh
0x18010fa73  lea     rdx, loc_18010FD27
0x18010fa7a  mov     rcx, [rsp+3B8h+var_360]
0x18010fa7f  call    _local_unwind_0
0x18010fa84  mov     [rbx+98h], rdi
0x18010fa8b  mov     [rbx+0A0h], r12d
0x18010fa92  mov     r8, [rsp+3B8h+pszSrc]; pszSrc
0x18010fa9a  test    r8, r8
0x18010fa9d  jz      short loc_18010FAD6
0x18010fa9f  mov     r11d, dword ptr [rsp+3B8h+cbDest]
0x18010faa4  mov     edx, r11d; cbDest
0x18010faa7  mov     rcx, rdi; pszDest
0x18010faaa  call    StringCbCopyW
0x18010faaf  mov     [rbx+70h], rdi
0x18010fab3  mov     [rsp+3B8h+cbDest], rdi
0x18010fab8  mov     [rsp+3B8h+pszSrc], rdi
0x18010fac0  lea     rax, [r11+rdi]
0x18010fac4  mov     [rsp+3B8h+cbDest], rax
0x18010fac9  lea     rdi, [rax+1]
0x18010facd  and     rdi, 0FFFFFFFFFFFFFFFEh
0x18010fad1  mov     [rsp+3B8h+cbDest], rdi
0x18010fad6  mov     r8, [rsp+3B8h+var_308]; pszSrc
0x18010fade  test    r8, r8
0x18010fae1  jz      short loc_18010FB1A
0x18010fae3  mov     r11d, dword ptr [rsp+3B8h+var_378]
0x18010fae8  mov     edx, r11d; cbDest
0x18010faeb  mov     rcx, rdi; pszDest
0x18010faee  call    StringCbCopyW
0x18010faf3  mov     [rbx+78h], rdi
0x18010faf7  mov     [rsp+3B8h+var_378], rdi
0x18010fafc  mov     [rsp+3B8h+var_308], rdi
0x18010fb04  lea     rax, [r11+rdi]
0x18010fb08  mov     [rsp+3B8h+var_378], rax
0x18010fb0d  lea     rdi, [rax+1]
0x18010fb11  and     rdi, 0FFFFFFFFFFFFFFFEh
0x18010fb15  mov     [rsp+3B8h+var_378], rdi
0x18010fb1a  mov     r8, [rsp+3B8h+var_370]; pszSrc
0x18010fb1f  test    r8, r8
0x18010fb22  jz      short loc_18010FB58
0x18010fb24  mov     r11d, dword ptr [rsp+3B8h+var_350]
0x18010fb29  mov     edx, r11d; cbDest
0x18010fb2c  mov     rcx, rdi; pszDest
0x18010fb2f  call    StringCbCopyW
0x18010fb34  mov     [rbx+40h], rdi
0x18010fb38  mov     [rsp+3B8h+var_370], rdi
  ... truncated ...
```
