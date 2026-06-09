# SignRightsDataProc(void *)

- ea: `0x180031110`
- end: `0x18003175b`
- name: `?SignRightsDataProc@@YAIPEAX@Z`
- size: `1611`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x1800046c8`
- `0x180017210`
- `0x180031110`
- `0x1800472d4`
- `0x180047678`
- `0x180047c38`
- `0x180047c68`
- `0x180048764`
- `0x180048b20`
- `0x180048edc`
- `0x18004a92c`
- `0x18004aa40`
- `0x18004ab54`
- `0x18004ac50`
- `0x18004b218`
- `0x18004ba58`
- `0x18005bd72`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031288`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031549`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800316ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031288`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031549`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800316ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031334`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031334`

## string_xrefs

- `0x180031422`: `PublishingService`
- `0x1800311c7`: `http://microsoft.com/DRM/PublishingService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SignRightsDataProc(void *a1)
{
  void (__fastcall *v2)(_QWORD, _QWORD, _QWORD, _QWORD); // r14
  __int64 v3; // r13
  CDRMSoapRequest *v4; // rax
  CDRMSoapRequest *v5; // rdi
  int Request; // ebx
  __int64 v7; // rax
  const unsigned __int16 *v8; // rdx
  unsigned int v9; // r8d
  __int64 v10; // rdx
  __int64 v11; // rdx
  int v12; // edx
  __int64 v13; // rax
  unsigned __int64 v14; // r14
  void *v15; // rax
  unsigned __int16 *v16; // r12
  unsigned __int16 *v17; // r15
  void *v18; // rcx
  int v19; // ecx
  const unsigned __int16 *v21; // r9
  int v22; // eax
  int v23; // r15d
  unsigned int v24; // r14d
  unsigned int v25; // r12d
  unsigned __int16 *v26; // rax
  __int64 v27; // rcx
  unsigned __int64 v28; // r13
  unsigned __int16 *v29; // rax
  unsigned __int16 *v30; // rbx
  unsigned __int16 *v31; // r15
  unsigned int v32; // r14d
  unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  DWORD v35; // eax
  unsigned __int16 *v36; // [rsp+30h] [rbp-38h] BYREF
  __int64 v37; // [rsp+38h] [rbp-30h]
  void *v38; // [rsp+40h] [rbp-28h]
  void *Block; // [rsp+48h] [rbp-20h]
  __int64 v40; // [rsp+50h] [rbp-18h]
  CDRMSoapRequest *v41; // [rsp+58h] [rbp-10h]
  unsigned int v42; // [rsp+B0h] [rbp+48h] BYREF
  unsigned __int16 *v43; // [rsp+B8h] [rbp+50h] BYREF
  unsigned __int16 *v44; // [rsp+C0h] [rbp+58h] BYREF
  void (__fastcall *v45)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+C8h] [rbp+60h]

  v40 = -2;
  _RTLTRACE("[msdrm]: +SignRightsDataProc");
  v42 = 0;
  v36 = 0;
  v43 = 0;
  v44 = 0;
  if ( !a1 )
    goto LABEL_34;
  Block = 0;
  v38 = 0;
  v2 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))*((_QWORD *)a1 + 3);
  v45 = v2;
  v3 = *((_QWORD *)a1 + 4);
  v37 = v3;
  v4 = (CDRMSoapRequest *)operator new(0x110u);
  v41 = v4;
  if ( v4 )
    v5 = CDRMSoapRequest::CDRMSoapRequest(v4);
  else
    v5 = 0;
  if ( !v5 )
  {
    Request = -2147024882;
LABEL_20:
    v16 = v44;
    v17 = v43;
    goto LABEL_21;
  }
  v7 = *((_QWORD *)a1 + 4);
  *((_QWORD *)v5 + 1) = v2;
  *((_DWORD *)v5 + 4) = 4;
  *((_QWORD *)v5 + 3) = v7;
  *((_QWORD *)v5 + 10) = *((_QWORD *)a1 + 5);
  Request = CDRMSoapRequest::CreateRequest(
              v5,
              L"AcquireIssuanceLicense",
              L"RequestParams",
              L"http://microsoft.com/DRM/PublishingService",
              1u);
  if ( Request < 0 )
    goto LABEL_20;
  Request = CDRMSoapRequest::CreateHeader(v5, v8, v9);
  if ( Request < 0 )
    goto LABEL_20;
  Request = CDRMSoapRequest::AddHeaderParameter(v5, v10, L"MinimumVersion");
  if ( Request < 0 )
    goto LABEL_20;
  Request = CDRMSoapRequest::AddHeaderParameter(v5, v11, L"MaximumVersion");
  if ( Request < 0 )
    goto LABEL_20;
  Request = CDRMSoapRequest::AddStruct(v5, v12, L"AcquireIssuanceLicenseParams", 1u);
  if ( Request < 0 )
    goto LABEL_20;
  Request = CDRMSoapRequest::AddParam(
              v5,
              1,
              L"AcquireIssuanceLicenseParams",
              L"UnsignedIssuanceLicense",
              2,
              *((_QWORD *)a1 + 1));
  if ( Request < 0 )
    goto LABEL_20;
  if ( !WaitForSingleObject(*((HANDLE *)a1 + 5), 0) )
  {
    Request = -2147168447;
    goto LABEL_20;
  }
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(*(_QWORD *)a1 + 2 * v13) );
  v14 = v13 + 14;
  v15 = operator new(saturated_mul(v13 + 14, 2u));
  Block = v15;
  if ( !v15 )
  {
    Request = -2147024882;
LABEL_19:
    v2 = v45;
    goto LABEL_20;
  }
  Request = StringCchCopyW((unsigned __int16 *)v15, v14, *(const unsigned __int16 **)a1);
  if ( Request < 0 )
    goto LABEL_19;
  Request = StringCchCatW((unsigned __int16 *)Block, v14, L"/publish.asmx");
  if ( Request < 0 )
    goto LABEL_19;
  Request = CHttpBase::SetServerInfo(v5, (const unsigned __int16 *)Block, 0, v21);
  if ( Request < 0 )
    goto LABEL_19;
  Request = CDRMSoapRequest::SetServerMethod(v5, L"PublishingService", L"AcquireIssuanceLicense");
  if ( Request < 0 )
    goto LABEL_19;
  v22 = (*(__int64 (__fastcall **)(CDRMSoapRequest *, _QWORD, _QWORD))(*(_QWORD *)v5 + 16LL))(v5, 0, 0);
  Request = v22;
  if ( v22 != -2147168300 )
  {
    if ( v22 < 0 )
    {
      _RTLTRACE("[msdrm]: FAILED : %x ", v22);
      goto LABEL_19;
    }
    if ( !WaitForSingleObject(*((HANDLE *)a1 + 5), 0) )
    {
      Request = -2147168447;
      goto LABEL_19;
    }
    Request = CDRMSoapRequest::GetParameterValueCount(v5, L"AcquireIssuanceLicenseResponse", L"CertificateChain", &v42);
    if ( Request < 0 )
      goto LABEL_19;
    v23 = 0;
    v24 = 0;
    v25 = v42;
    if ( v42 )
    {
      v26 = v36;
      do
      {
        operator delete(v26);
        v36 = 0;
        Request = CDRMSoapRequest::GetParameterValue(
                    v5,
                    L"AcquireIssuanceLicenseResponse",
                    L"CertificateChain",
                    v24,
                    &v36);
        if ( Request < 0 )
          goto LABEL_19;
        v26 = v36;
        v27 = -1;
        do
          ++v27;
        while ( v36[v27] );
        v23 += v27;
      }
      while ( ++v24 < v25 );
    }
    v28 = (unsigned int)(v23 + 1);
    v29 = (unsigned __int16 *)operator new(saturated_mul(v28, 2u));
    v30 = v29;
    v38 = v29;
    if ( v29 )
    {
      memset_0(v29, 0, 2 * v28);
      v31 = v30;
      v32 = 0;
      if ( !v25 )
      {
LABEL_71:
        v35 = WaitForSingleObject(*((HANDLE *)a1 + 5), 0);
        v2 = v45;
        if ( v35 )
        {
          Request = 315140;
          if ( v45 )
            v45(4, 315140, v38, *((_QWORD *)a1 + 4));
        }
        else
        {
          Request = -2147168447;
        }
        goto LABEL_63;
      }
      v33 = v36;
      while ( 1 )
      {
        operator delete(v33);
        v36 = 0;
        Request = CDRMSoapRequest::GetParameterValue(
                    v5,
                    L"AcquireIssuanceLicenseResponse",
                    L"CertificateChain",
                    v32,
                    &v36);
        if ( Request < 0 )
          break;
        Request = StringCchCopyW(v31, v28 - (((char *)v31 - (_BYTE *)v38) >> 1), v36);
        if ( Request < 0 )
          break;
        v33 = v36;
        v34 = -1;
        do
          ++v34;
        while ( v36[v34] );
        v31 += v34;
        if ( ++v32 >= v25 )
          goto LABEL_71;
      }
    }
    else
    {
      Request = -2147024882;
    }
    v2 = v45;
LABEL_63:
    v3 = v37;
    goto LABEL_20;
  }
  CDRMSoapRequest::GetFaultCode(v5, &v43);
  CDRMSoapRequest::GetFaultString(v5, &v44);
  v16 = v44;
  v17 = v43;
  _RTLTRACE(" [msdrm]:SignRightsDataProc  FaultCode = %S , FaultString = %S", v43, v44);
  if ( CDRMSoapRequest::IsExceptionType(v5, L"Microsoft.DigitalRightsManagement.Licensing.UserIsExcludedException")
    || CDRMSoapRequest::IsExceptionType(v5, L"Microsoft.DigitalRightsManagement.Licensing.DrmacIsExcludedException")
    || CDRMSoapRequest::IsExceptionType(
         v5,
         L"Microsoft.DigitalRightsManagement.Licensing.InvalidPersonaCertTimeException")
    || CDRMSoapRequest::IsExceptionType(
         v5,
         L"Microsoft.DigitalRightsManagement.Licensing.InvalidPersonaCertSignatureException")
    || CDRMSoapRequest::IsExceptionType(
         v5,
         L"Microsoft.DigitalRightsManagement.Licensing.UntrustedPersonaCertException")
    || CDRMSoapRequest::IsExceptionType(
         v5,
         L"Microsoft.DigitalRightsManagement.Licensing.UnexpectedPersonaCertException") )
  {
    Request = -2147168450;
  }
  else
  {
    Request = CDRMSoapRequest::IsExceptionType(
                v5,
                L"Microsoft.DigitalRightsManagement.Licensing.BlackBoxIsInvalidException") != 0
            ? -2147168451
            : -2147168444;
  }
  v2 = v45;
LABEL_21:
  operator delete(Block);
  operator delete(v36);
  operator delete(v38);
  operator delete(0);
  operator delete(v17);
  operator delete(v16);
  if ( v5 )
    (**(void (__fastcall ***)(CDRMSoapRequest *, __int64))v5)(v5, 1);
  v18 = (void *)*((_QWORD *)a1 + 5);
  if ( v18 )
    CloseHandle(v18);
  operator delete(*(void **)a1);
  operator delete(*((void **)a1 + 1));
  operator delete(a1);
  if ( Request < 0 )
  {
    if ( Request > -2147168438 )
    {
      if ( (unsigned int)(Request + 2147168421) <= 1 )
        goto LABEL_32;
      if ( Request == -2147168304 )
        goto LABEL_31;
      if ( Request == -2147168300 )
      {
LABEL_81:
        Request = -2147168444;
        goto LABEL_32;
      }
      if ( Request != -2147024882 && Request != -2147024809 )
LABEL_80:
        Request = -2147467259;
    }
    else if ( (unsigned int)(Request + 2147168453) > 0xF || (v19 = 32845, !_bittest(&v19, Request + 2147168453)) )
    {
      if ( Request != -2147168444 )
      {
        if ( Request == -2147168441 )
        {
LABEL_31:
          Request = -2147168441;
          goto LABEL_32;
        }
        goto LABEL_80;
      }
      goto LABEL_81;
    }
LABEL_32:
    if ( v2 )
      v2(4, (unsigned int)Request, 0, v3);
  }
LABEL_34:
  _RTLTRACE("[msdrm]: -SignRightsDataProc");
  return 0;
}

```

## disassembly

```asm
0x180031110  push    rbp
0x180031112  push    rbx
0x180031113  push    rsi
0x180031114  push    rdi
0x180031115  push    r12
0x180031117  push    r13
0x180031119  push    r14
0x18003111b  push    r15
0x18003111d  mov     rbp, rsp
0x180031120  sub     rsp, 68h
0x180031124  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x18003112c  mov     rsi, rcx
0x18003112f  lea     rcx, aMsdrmSignright; "[msdrm]: +SignRightsDataProc"
0x180031136  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18003113b  xor     r12d, r12d
0x18003113e  mov     [rbp+arg_0], r12d
0x180031142  mov     [rbp+var_38], r12
0x180031146  mov     [rbp+arg_8], r12
0x18003114a  mov     [rbp+arg_10], r12
0x18003114e  test    rsi, rsi
0x180031151  jz      loc_1800313AC
0x180031157  mov     [rbp+Block], r12
0x18003115b  mov     [rbp+var_28], r12
0x18003115f  mov     r14, [rsi+18h]
0x180031163  mov     [rbp+arg_18], r14
0x180031167  mov     r13, [rsi+20h]
0x18003116b  mov     [rbp+var_30], r13
0x18003116f  mov     ecx, 110h; Size
0x180031174  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031179  mov     [rbp+var_10], rax
0x18003117d  test    rax, rax
0x180031180  jz      short loc_18003118F
0x180031182  mov     rcx, rax; this
0x180031185  call    ??0CDRMSoapRequest@@QEAA@XZ; CDRMSoapRequest::CDRMSoapRequest(void)
0x18003118a  mov     rdi, rax
0x18003118d  jmp     short loc_180031192
0x18003118f  mov     rdi, r12
0x180031192  mov     r15d, 1
0x180031198  test    rdi, rdi
0x18003119b  jnz     short loc_1800311A7
0x18003119d  mov     ebx, 8007000Eh
0x1800311a2  jmp     loc_1800312D9
0x1800311a7  mov     rax, [rsi+20h]
0x1800311ab  mov     [rdi+8], r14
0x1800311af  mov     dword ptr [rdi+10h], 4
0x1800311b6  mov     [rdi+18h], rax
0x1800311ba  mov     rax, [rsi+28h]
0x1800311be  mov     [rdi+50h], rax
0x1800311c2  mov     dword ptr [rsp+68h+var_48], r15d; unsigned int
0x1800311c7  lea     r9, ?g_wszPUB_PublishingServiceNamespace@@3QBGB; "http://microsoft.com/DRM/PublishingServ"...
0x1800311ce  lea     r8, ?g_wszLA_RequestParams@@3QBGB; "RequestParams"
0x1800311d5  lea     rdx, ?g_wszPUB_SignRightsData@@3QBGB; "AcquireIssuanceLicense"
0x1800311dc  mov     rcx, rdi; this
0x1800311df  call    ?CreateRequest@CDRMSoapRequest@@QEAAJPEBG00I@Z; CDRMSoapRequest::CreateRequest(ushort const *,ushort const *,ushort const *,uint)
0x1800311e4  mov     ebx, eax
0x1800311e6  test    eax, eax
0x1800311e8  js      loc_1800312D9
0x1800311ee  mov     rcx, rdi; this
0x1800311f1  call    ?CreateHeader@CDRMSoapRequest@@QEAAJPEBGI@Z; CDRMSoapRequest::CreateHeader(ushort const *,uint)
0x1800311f6  mov     ebx, eax
0x1800311f8  test    eax, eax
0x1800311fa  js      loc_1800312D9
0x180031200  lea     r8, ?g_wszACT_MinimumVersion@@3QBGB; "MinimumVersion"
0x180031207  mov     rcx, rdi
0x18003120a  call    ?AddHeaderParameter@CDRMSoapRequest@@QEAAJPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddHeaderParameter(ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x18003120f  mov     ebx, eax
0x180031211  test    eax, eax
0x180031213  js      loc_1800312D9
0x180031219  lea     r8, ?g_wszACT_MaximumVersion@@3QBGB; "MaximumVersion"
0x180031220  mov     rcx, rdi
0x180031223  call    ?AddHeaderParameter@CDRMSoapRequest@@QEAAJPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddHeaderParameter(ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x180031228  mov     ebx, eax
0x18003122a  test    eax, eax
0x18003122c  js      loc_1800312D9
0x180031232  mov     r9d, r15d; unsigned int
0x180031235  lea     r8, ?g_wszPUB_SignDataParams@@3QBGB; "AcquireIssuanceLicenseParams"
0x18003123c  mov     rcx, rdi; this
0x18003123f  call    ?AddStruct@CDRMSoapRequest@@IEAAJHPEBGI@Z; CDRMSoapRequest::AddStruct(int,ushort const *,uint)
0x180031244  mov     ebx, eax
0x180031246  test    eax, eax
0x180031248  js      loc_1800312D9
0x18003124e  mov     rax, [rsi+8]
0x180031252  mov     [rsp+68h+var_40], rax
0x180031257  mov     r15d, 2
0x18003125d  mov     dword ptr [rsp+68h+var_48], r15d
0x180031262  lea     r9, ?g_wszPUB_UnsignedRightsData@@3QBGB; "UnsignedIssuanceLicense"
0x180031269  lea     r8, ?g_wszPUB_SignDataParams@@3QBGB; "AcquireIssuanceLicenseParams"
0x180031270  lea     edx, [r15-1]
0x180031274  mov     rcx, rdi
0x180031277  call    ?AddParam@CDRMSoapRequest@@IEAAJHPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddParam(int,ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x18003127c  mov     ebx, eax
0x18003127e  test    eax, eax
0x180031280  js      short loc_1800312D9
0x180031282  xor     edx, edx; dwMilliseconds
0x180031284  mov     rcx, [rsi+28h]; hHandle
0x180031288  call    cs:__imp_WaitForSingleObject
0x18003128e  test    eax, eax
0x180031290  jnz     short loc_180031299
0x180031292  mov     ebx, 8004CF41h
0x180031297  jmp     short loc_1800312D9
0x180031299  mov     rcx, [rsi]
0x18003129c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800312a0  mov     rax, r8
0x1800312a3  inc     rax
0x1800312a6  cmp     [rcx+rax*2], r12w
0x1800312ab  jnz     short loc_1800312A3
0x1800312ad  lea     r14, [rax+0Eh]
0x1800312b1  mov     rax, r15
0x1800312b4  mul     r14
0x1800312b7  cmovb   rax, r8
0x1800312bb  mov     rcx, rax; Size
0x1800312be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800312c3  mov     [rbp+Block], rax
0x1800312c7  test    rax, rax
0x1800312ca  jnz     loc_1800313CB
0x1800312d0  mov     ebx, 8007000Eh
0x1800312d5  mov     r14, [rbp+arg_18]
0x1800312d9  mov     r12, [rbp+arg_10]
0x1800312dd  mov     r15, [rbp+arg_8]
0x1800312e1  mov     rcx, [rbp+Block]; Block
0x1800312e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800312ea  mov     rcx, [rbp+var_38]; Block
0x1800312ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800312f3  mov     rcx, [rbp+var_28]; Block
0x1800312f7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800312fc  xor     ecx, ecx; Block
0x1800312fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031303  mov     rcx, r15; Block
0x180031306  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003130b  mov     rcx, r12; Block
0x18003130e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031313  test    rdi, rdi
0x180031316  jz      short loc_18003132B
0x180031318  mov     rax, [rdi]
0x18003131b  mov     edx, 1
0x180031320  mov     rcx, rdi
0x180031323  mov     rax, [rax]
0x180031326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003132b  mov     rcx, [rsi+28h]; hObject
0x18003132f  test    rcx, rcx
0x180031332  jz      short loc_18003133A
0x180031334  call    cs:__imp_CloseHandle
0x18003133a  mov     rcx, [rsi]; Block
0x18003133d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031342  mov     rcx, [rsi+8]; Block
0x180031346  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003134b  mov     rcx, rsi; Block
0x18003134e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031353  test    ebx, ebx
0x180031355  jns     short loc_1800313AC
0x180031357  mov     edx, 8004CF47h
0x18003135c  cmp     ebx, 8004CF4Ah
0x180031362  jg      loc_18003170C
0x180031368  lea     eax, [rbx+7FFB30C5h]
0x18003136e  cmp     eax, 0Fh
0x180031371  ja      short loc_18003137D
0x180031373  mov     ecx, 804Dh
0x180031378  bt      ecx, eax
0x18003137b  jb      short loc_180031393
0x18003137d  cmp     ebx, 8004CF44h
0x180031383  jz      loc_180031751
0x180031389  cmp     ebx, edx
0x18003138b  jnz     loc_180031747
0x180031391  mov     ebx, edx
0x180031393  test    r14, r14
0x180031396  jz      short loc_1800313AC
0x180031398  mov     r9, r13
0x18003139b  xor     r8d, r8d
0x18003139e  mov     edx, ebx
0x1800313a0  lea     ecx, [r8+4]
0x1800313a4  mov     rax, r14
0x1800313a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313ac  lea     rcx, aMsdrmSignright_2; "[msdrm]: -SignRightsDataProc"
0x1800313b3  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x1800313b8  xor     eax, eax
0x1800313ba  add     rsp, 68h
0x1800313be  pop     r15
0x1800313c0  pop     r14
0x1800313c2  pop     r13
0x1800313c4  pop     r12
0x1800313c6  pop     rdi
0x1800313c7  pop     rsi
0x1800313c8  pop     rbx
0x1800313c9  pop     rbp
0x1800313ca  retn
0x1800313cb  mov     r8, [rsi]; unsigned __int16 *
0x1800313ce  mov     rdx, r14; unsigned __int64
0x1800313d1  mov     rcx, rax; unsigned __int16 *
0x1800313d4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800313d9  mov     ebx, eax
0x1800313db  test    eax, eax
0x1800313dd  js      loc_1800312D5
0x1800313e3  lea     r8, ?g_wszPUB_PublishingServicePadding@@3QBGB; "/publish.asmx"
0x1800313ea  mov     rdx, r14; unsigned __int64
0x1800313ed  mov     r14, [rbp+Block]
0x1800313f1  mov     rcx, r14; unsigned __int16 *
0x1800313f4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800313f9  mov     ebx, eax
0x1800313fb  test    eax, eax
0x1800313fd  js      loc_1800312D5
0x180031403  xor     r8d, r8d; unsigned int
0x180031406  mov     rdx, r14; unsigned __int16 *
0x180031409  mov     rcx, rdi; this
0x18003140c  call    ?SetServerInfo@CHttpBase@@QEAAJPEBGI0@Z; CHttpBase::SetServerInfo(ushort const *,uint,ushort const *)
0x180031411  mov     ebx, eax
0x180031413  test    eax, eax
0x180031415  js      loc_1800312D5
0x18003141b  lea     r8, ?g_wszPUB_SignRightsData@@3QBGB; "AcquireIssuanceLicense"
0x180031422  lea     rdx, ?g_wszPUB_PublishingService@@3QBGB; "PublishingService"
0x180031429  mov     rcx, rdi; this
0x18003142c  call    ?SetServerMethod@CDRMSoapRequest@@QEAAJPEBG0@Z; CDRMSoapRequest::SetServerMethod(ushort const *,ushort const *)
0x180031431  mov     ebx, eax
0x180031433  test    eax, eax
0x180031435  js      loc_1800312D5
0x18003143b  mov     rax, [rdi]
0x18003143e  xor     r8d, r8d
0x180031441  xor     edx, edx
0x180031443  mov     rcx, rdi
0x180031446  mov     rax, [rax+10h]
0x18003144a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003144f  mov     ebx, eax
0x180031451  cmp     eax, 8004CFD4h
0x180031456  jnz     loc_18003152C
0x18003145c  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x180031460  mov     rcx, rdi; this
0x180031463  call    ?GetFaultCode@CDRMSoapRequest@@QEAAJPEAPEAG@Z; CDRMSoapRequest::GetFaultCode(ushort * *)
0x180031468  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x18003146c  mov     rcx, rdi; this
0x18003146f  call    ?GetFaultString@CDRMSoapRequest@@QEAAJPEAPEAG@Z; CDRMSoapRequest::GetFaultString(ushort * *)
0x180031474  mov     r12, [rbp+arg_10]
0x180031478  mov     r8, r12
0x18003147b  mov     r15, [rbp+arg_8]
0x18003147f  mov     rdx, r15
0x180031482  lea     rcx, aMsdrmSignright_1; " [msdrm]:SignRightsDataProc  FaultCode "...
0x180031489  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18003148e  lea     rdx, ?g_wszACT_UserIsExcludedException@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
0x180031495  mov     rcx, rdi; this
0x180031498  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x18003149d  test    eax, eax
0x18003149f  jnz     short loc_18003151E
0x1800314a1  lea     rdx, ?g_wszACT_DrmacIsExcludedException@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
0x1800314a8  mov     rcx, rdi; this
0x1800314ab  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x1800314b0  test    eax, eax
0x1800314b2  jnz     short loc_18003151E
0x1800314b4  lea     rdx, ?g_wszACT_InvalidPersonaCertTimeException@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
0x1800314bb  mov     rcx, rdi; this
0x1800314be  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x1800314c3  test    eax, eax
0x1800314c5  jnz     short loc_18003151E
0x1800314c7  lea     rdx, ?g_wszACT_InvalidPersonaCertSignatureException@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
0x1800314ce  mov     rcx, rdi; this
0x1800314d1  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x1800314d6  test    eax, eax
0x1800314d8  jnz     short loc_18003151E
0x1800314da  lea     rdx, ?g_wszACT_UntrustedPersonaCertException@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
0x1800314e1  mov     rcx, rdi; this
0x1800314e4  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x1800314e9  test    eax, eax
0x1800314eb  jnz     short loc_18003151E
0x1800314ed  lea     rdx, ?g_wszACT_UnexpectedPersonaCertException@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
0x1800314f4  mov     rcx, rdi; this
0x1800314f7  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x1800314fc  test    eax, eax
0x1800314fe  jnz     short loc_18003151E
0x180031500  lea     rdx, ?g_wszACT_BlackboxIsInvalidExclusion@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
0x180031507  mov     rcx, rdi; this
0x18003150a  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x18003150f  neg     eax
0x180031511  sbb     ebx, ebx
0x180031513  and     ebx, 0FFFFFFF9h
0x180031516  add     ebx, 8004CF44h
0x18003151c  jmp     short loc_180031523
0x18003151e  mov     ebx, 8004CF3Eh
0x180031523  mov     r14, [rbp+arg_18]
0x180031527  jmp     loc_1800312E1
0x18003152c  test    eax, eax
0x18003152e  jns     short loc_180031543
0x180031530  mov     edx, eax
0x180031532  lea     rcx, aMsdrmFailedX; "[msdrm]: FAILED : %x "
0x180031539  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18003153e  jmp     loc_1800312D5
0x180031543  xor     edx, edx; dwMilliseconds
0x180031545  mov     rcx, [rsi+28h]; hHandle
0x180031549  call    cs:__imp_WaitForSingleObject
0x18003154f  test    eax, eax
0x180031551  jnz     short loc_18003155D
0x180031553  mov     ebx, 8004CF41h
0x180031558  jmp     loc_1800312D5
0x18003155d  lea     r9, [rbp+arg_0]; unsigned int *
0x180031561  lea     r8, ?g_wszPUB_CertificateChain@@3QBGB; "CertificateChain"
0x180031568  lea     rdx, ?g_wszPUB_SignDataResponse@@3QBGB; "AcquireIssuanceLicenseResponse"
0x18003156f  mov     rcx, rdi; this
0x180031572  call    ?GetParameterValueCount@CDRMSoapRequest@@QEAAJPEBG0PEAI@Z; CDRMSoapRequest::GetParameterValueCount(ushort const *,ushort const *,uint *)
0x180031577  mov     ebx, eax
0x180031579  test    eax, eax
0x18003157b  js      loc_1800312D5
0x180031581  mov     r15d, r12d
0x180031584  mov     r14d, r12d
0x180031587  mov     r12d, [rbp+arg_0]
  ... truncated ...
```
