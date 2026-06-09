# Logger::WriteNgcPolicyEvaluationCompleteEvent(_NgcPolicyCheckResult,_NgcCertEnrollmentMethod,int)

- ea: `0x18000e2dc`
- end: `0x18000e80d`
- name: `?WriteNgcPolicyEvaluationCompleteEvent@Logger@@SAJU_NgcPolicyCheckResult@@W4_NgcCertEnrollmentMethod@@H@Z`
- size: `1329`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e848`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000dfd0`
- `0x18000e2dc`
- `0x18000e814`
- `0x1800203f4`
- `0x1800333c4`
- `0x1800386b0`
- `0x18008cce4`
- `0x180093998`
- `0x180093c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e461`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e499`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e499`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7f1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000e42f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000e42f`

## string_xrefs

- `0x18000e585`: `Logger::WriteNgcPolicyEvaluationCompleteEvent`
- `0x18000e6df`: `Logger::WriteNgcPolicyEvaluationCompleteEvent`
- `0x18000e7e1`: `Logger::WriteNgcPolicyEvaluationCompleteEvent`
- `0x18000e3f9`: `%s: EventWriteNgcEnrollPolicyWillRun failed with error code: 0x%08x.`
- `0x18000e58c`: `%s: EventWriteNgcEnrollPolicyWillNotRunMdmCert failed with error code: 0x%08x.`
- `0x18000e7d7`: `%s: EventWriteNgcEnrollPolicyWillNotRunNoCert failed with error code: 0x%08x.`
- `0x18000e6e6`: `%s: EventWriteNgcEnrollPolicyWillNotRunRACert failed with error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall Logger::WriteNgcPolicyEvaluationCompleteEvent(unsigned int *a1, int a2, char **a3)
{
  __int64 NgcPolicyStageResult; // r15
  __int64 v6; // r14
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 NgcCertEnrollmentName; // rsi
  __int64 v10; // rdi
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // r10
  __int64 v16; // r11
  const wchar_t *v17; // r8
  unsigned int v18; // eax
  DWORD v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 LastError; // rbx
  bool v23; // sf
  const wchar_t *v24; // r8
  int v25; // edi
  __int64 v26; // r14
  __int64 v27; // rsi
  __int64 v28; // rdi
  __int64 v29; // rbx
  int v30; // eax
  __int64 v31; // rdx
  int v32; // ecx
  int v33; // r8d
  __int64 v34; // r9
  __int64 v35; // r10
  __int64 v36; // r11
  unsigned int v37; // eax
  bool v38; // zf
  unsigned __int16 *v39; // r14
  __int64 v40; // rax
  unsigned __int16 *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // r15
  __int64 v44; // rsi
  __int64 v45; // rdi
  __int64 v46; // rbx
  int v47; // eax
  __int64 v48; // rdx
  __int64 v49; // r9
  __int64 v50; // r10
  __int64 v51; // r11
  const wchar_t *v52; // r8
  unsigned int v53; // eax
  __int64 v54; // r15
  __int64 v55; // r14
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // rsi
  __int64 v59; // rdi
  __int64 v60; // rbx
  int v61; // eax
  __int64 v62; // rdx
  int v63; // ecx
  int v64; // r8d
  __int64 v65; // r9
  __int64 v66; // r10
  __int64 v67; // r11
  unsigned int v68; // eax
  unsigned __int16 *v70; // [rsp+70h] [rbp+7h] BYREF
  __int64 v71; // [rsp+78h] [rbp+Fh]
  _WORD *Buffer; // [rsp+E8h] [rbp+7Fh] BYREF

  Buffer = 0;
  if ( (_DWORD)a3 )
  {
    Logger::GetLocalizedMessage(0x83u, (LPWSTR)&Buffer, a3);
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
    {
      NgcPolicyStageResult = GetNgcPolicyStageResult(a1[17]);
      v6 = GetNgcPolicyStageResult(a1[16]);
      NgcCertEnrollmentName = GetNgcCertEnrollmentName(a1[12], v7, v8);
      v10 = GetNgcPolicyStageResult(a1[3]);
      v11 = GetNgcPolicyStageResult(a1[5]);
      GetNgcPolicyStageResult(a1[8]);
      GetNgcPolicyStageResult(a1[7]);
      GetNgcPolicyStageResult(a1[6]);
      GetNgcPolicyStageResult(a1[1]);
      v12 = GetNgcPolicyStageResult(*a1);
      v17 = L"Hello for business enrollment will run";
      if ( Buffer )
        LODWORD(v17) = (_DWORD)Buffer;
      v18 = McTemplateU0zzzzzzzzzzz_EventWriteTransfer(
              (_DWORD)Buffer,
              (unsigned int)NgcEnrollPolicyWillRun,
              (_DWORD)v17,
              v12,
              v13,
              v14,
              v15,
              v16,
              v11,
              v10,
              NgcCertEnrollmentName,
              v6,
              NgcPolicyStageResult);
      if ( v18 )
        Logger::TraceError(
          L"%s: EventWriteNgcEnrollPolicyWillRun failed with error code: 0x%08x.",
          L"Logger::WriteNgcPolicyEvaluationCompleteEvent",
          v18);
    }
    goto LABEL_42;
  }
  v19 = FormatMessageW(0x900u, &_ImageBase, 0x84u, 0, (LPWSTR)&Buffer, 0, 0);
  if ( v19 )
  {
    if ( v19 > 1 )
    {
      v21 = v19 - 2;
      if ( Buffer[v21] == 13 && Buffer[v19 - 1] == 10 )
        Buffer[v21] = 0;
    }
  }
  else
  {
    LastError = GetLastError();
    Logger::TraceWarning(
      (wchar_t *)L"%s: FormatMessageW failed with error code: 0x%08x. Message ID = %lu.",
      L"Logger::GetLocalizedMessage",
      LastError,
      132);
    v23 = (int)LastError < 0;
    if ( (_DWORD)LastError )
    {
      if ( (int)LastError > 0 )
        v23 = 1;
      if ( v23 )
      {
        LocalFree(Buffer);
        Buffer = 0;
      }
    }
  }
  v24 = L"Hello for business enrollment will not run";
  if ( a2 )
  {
    v25 = a2 - 1;
    if ( v25 )
    {
      if ( v25 != 1 )
        goto LABEL_37;
    }
    else if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 4) != 0 )
    {
      v26 = GetNgcCertEnrollmentName(a1[12], v20, L"Hello for business enrollment will not run");
      v27 = GetNgcPolicyStageResult(a1[4]);
      v28 = GetNgcPolicyStageResult(a1[3]);
      v29 = GetNgcPolicyStageResult(a1[5]);
      GetNgcPolicyStageResult(a1[8]);
      GetNgcPolicyStageResult(a1[7]);
      GetNgcPolicyStageResult(a1[6]);
      GetNgcPolicyStageResult(a1[1]);
      v30 = GetNgcPolicyStageResult(*a1);
      if ( Buffer )
        v33 = (int)Buffer;
      v37 = McTemplateU0zzzzzzzzzz_EventWriteTransfer(v32, v31, v33, v30, v31, v34, v35, v36, v29, v28, v27, v26);
      if ( v37 )
        Logger::TraceError(
          L"%s: EventWriteNgcEnrollPolicyWillNotRunMdmCert failed with error code: 0x%08x.",
          L"Logger::WriteNgcPolicyEvaluationCompleteEvent",
          v37);
    }
    v38 = (a1[10] & 0xFFFFFFFD) == 0;
    v39 = 0;
    v70 = 0;
    if ( v38 )
    {
      GetLogonTemplateName(a1[11]);
      v40 = GetNgcPolicyStageResult(a1[10]);
      Logger::StringPrint(&v70, L"%s ( %d : %s ) ", v40);
      v39 = v70;
    }
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 4) != 0 )
    {
      v41 = (unsigned __int16 *)GetNgcCertEnrollmentName(a1[12], v20, v24);
      v42 = a1[2];
      v70 = v41;
      v71 = GetNgcPolicyStageResult(v42);
      if ( v39 )
        v43 = (__int64)v39;
      else
        v43 = GetNgcPolicyStageResult(a1[10]);
      v44 = GetNgcPolicyStageResult(a1[9]);
      v45 = GetNgcPolicyStageResult(a1[3]);
      v46 = GetNgcPolicyStageResult(a1[5]);
      GetNgcPolicyStageResult(a1[8]);
      GetNgcPolicyStageResult(a1[7]);
      GetNgcPolicyStageResult(a1[6]);
      GetNgcPolicyStageResult(a1[1]);
      v47 = GetNgcPolicyStageResult(*a1);
      v52 = L"Hello for business enrollment will not run";
      if ( Buffer )
        LODWORD(v52) = (_DWORD)Buffer;
      v53 = McTemplateU0zzzzzzzzzzzz_EventWriteTransfer(
              v71,
              v48,
              (_DWORD)v52,
              v47,
              v48,
              v49,
              v50,
              v51,
              v46,
              v45,
              v44,
              v43,
              v71,
              (__int64)v70);
      if ( v53 )
        Logger::TraceError(
          L"%s: EventWriteNgcEnrollPolicyWillNotRunRACert failed with error code: 0x%08x.",
          L"Logger::WriteNgcPolicyEvaluationCompleteEvent",
          v53);
    }
    SafeFree(v39);
  }
LABEL_37:
  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 4) != 0 )
  {
    v54 = GetNgcPolicyStageResult(a1[17]);
    v55 = GetNgcPolicyStageResult(a1[16]);
    v58 = GetNgcCertEnrollmentName(a1[12], v56, v57);
    v59 = GetNgcPolicyStageResult(a1[3]);
    v60 = GetNgcPolicyStageResult(a1[5]);
    GetNgcPolicyStageResult(a1[8]);
    GetNgcPolicyStageResult(a1[7]);
    GetNgcPolicyStageResult(a1[6]);
    GetNgcPolicyStageResult(a1[1]);
    v61 = GetNgcPolicyStageResult(*a1);
    if ( Buffer )
      v64 = (int)Buffer;
    v68 = McTemplateU0zzzzzzzzzzz_EventWriteTransfer(
            v63,
            (unsigned int)NgcEnrollPolicyWillNotRunNoCert,
            v64,
            v61,
            v62,
            v65,
            v66,
            v67,
            v60,
            v59,
            v58,
            v55,
            v54);
    if ( v68 )
      Logger::TraceError(
        L"%s: EventWriteNgcEnrollPolicyWillNotRunNoCert failed with error code: 0x%08x.",
        L"Logger::WriteNgcPolicyEvaluationCompleteEvent",
        v68);
  }
LABEL_42:
  LocalFree(Buffer);
  return 0;
}

```

## disassembly

```asm
0x18000e2dc  push    rbp
0x18000e2de  push    rbx
0x18000e2df  push    rsi
0x18000e2e0  push    rdi
0x18000e2e1  push    r12
0x18000e2e3  push    r13
0x18000e2e5  push    r14
0x18000e2e7  push    r15
0x18000e2e9  lea     rbp, [rsp-1Fh]
0x18000e2ee  sub     rsp, 88h
0x18000e2f5  xor     r15d, r15d
0x18000e2f8  mov     edi, edx
0x18000e2fa  mov     [rbp+57h+Buffer], r15
0x18000e2fe  mov     r12, rcx
0x18000e301  test    r8d, r8d
0x18000e304  jz      loc_18000E405
0x18000e30a  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18000e30e  mov     ecx, 83h; dwMessageId
0x18000e313  call    ?GetLocalizedMessage@Logger@@SAJKPEAPEAGPEAPEAD@Z; Logger::GetLocalizedMessage(ulong,ushort * *,char * *)
0x18000e318  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x18000e31f  jz      loc_18000E7ED
0x18000e325  mov     ecx, [r12+44h]
0x18000e32a  call    GetNgcPolicyStageResult
0x18000e32f  mov     ecx, [r12+40h]
0x18000e334  mov     r15, rax
0x18000e337  call    GetNgcPolicyStageResult
0x18000e33c  mov     ecx, [r12+30h]
0x18000e341  mov     r14, rax
0x18000e344  call    GetNgcCertEnrollmentName
0x18000e349  mov     ecx, [r12+0Ch]
0x18000e34e  mov     rsi, rax
0x18000e351  call    GetNgcPolicyStageResult
0x18000e356  mov     ecx, [r12+14h]
0x18000e35b  mov     rdi, rax
0x18000e35e  call    GetNgcPolicyStageResult
0x18000e363  mov     ecx, [r12+20h]
0x18000e368  mov     rbx, rax
0x18000e36b  call    GetNgcPolicyStageResult
0x18000e370  mov     ecx, [r12+1Ch]
0x18000e375  mov     r11, rax
0x18000e378  call    GetNgcPolicyStageResult
0x18000e37d  mov     ecx, [r12+18h]
0x18000e382  mov     r10, rax
0x18000e385  call    GetNgcPolicyStageResult
0x18000e38a  mov     ecx, [r12+4]
0x18000e38f  mov     r9, rax
0x18000e392  call    GetNgcPolicyStageResult
0x18000e397  mov     ecx, [r12]
0x18000e39b  mov     rdx, rax
0x18000e39e  call    GetNgcPolicyStageResult
0x18000e3a3  mov     rcx, [rbp+57h+Buffer]
0x18000e3a7  lea     r8, aHelloForBusine; "Hello for business enrollment will run"
0x18000e3ae  mov     [rsp+0C0h+var_60], r15
0x18000e3b3  test    rcx, rcx
0x18000e3b6  mov     [rsp+0C0h+var_68], r14
0x18000e3bb  mov     [rsp+0C0h+var_70], rsi
0x18000e3c0  cmovnz  r8, rcx
0x18000e3c4  mov     [rsp+0C0h+var_78], rdi
0x18000e3c9  mov     [rsp+0C0h+var_80], rbx
0x18000e3ce  mov     [rsp+0C0h+var_88], r11
0x18000e3d3  mov     [rsp+0C0h+Arguments], r10
0x18000e3d8  mov     qword ptr [rsp+0C0h+nSize], r9
0x18000e3dd  mov     r9, rax
0x18000e3e0  mov     [rsp+0C0h+lpBuffer], rdx
0x18000e3e5  lea     rdx, NgcEnrollPolicyWillRun
0x18000e3ec  call    McTemplateU0zzzzzzzzzzz_EventWriteTransfer
0x18000e3f1  test    eax, eax
0x18000e3f3  jz      loc_18000E7ED
0x18000e3f9  lea     rcx, aSEventwritengc_1; "%s: EventWriteNgcEnrollPolicyWillRun fa"...
0x18000e400  jmp     loc_18000E7DE
0x18000e405  mov     [rsp+0C0h+Arguments], r15; Arguments
0x18000e40a  lea     rax, [rbp+57h+Buffer]
0x18000e40e  mov     esi, 84h
0x18000e413  mov     [rsp+0C0h+nSize], r15d; nSize
0x18000e418  mov     r8d, esi; dwMessageId
0x18000e41b  mov     [rsp+0C0h+lpBuffer], rax; lpBuffer
0x18000e420  xor     r9d, r9d; dwLanguageId
0x18000e423  lea     rdx, __ImageBase; lpSource
0x18000e42a  mov     ecx, 900h; dwFlags
0x18000e42f  call    cs:__imp_FormatMessageW
0x18000e435  test    eax, eax
0x18000e437  jz      short loc_18000E461
0x18000e439  cmp     eax, 1
0x18000e43c  jbe     short loc_18000E4A3
0x18000e43e  mov     r13, [rbp+57h+Buffer]
0x18000e442  lea     ecx, [rax-2]
0x18000e445  cmp     word ptr [r13+rcx*2+0], 0Dh
0x18000e44c  jnz     short loc_18000E4A3
0x18000e44e  dec     eax
0x18000e450  cmp     word ptr [r13+rax*2+0], 0Ah
0x18000e457  jnz     short loc_18000E4A3
0x18000e459  mov     [r13+rcx*2+0], r15w
0x18000e45f  jmp     short loc_18000E4A3
0x18000e461  call    cs:__imp_GetLastError
0x18000e467  mov     r9d, esi
0x18000e46a  lea     rdx, aLoggerGetlocal; "Logger::GetLocalizedMessage"
0x18000e471  mov     r8d, eax
0x18000e474  lea     rcx, aSFormatmessage; "%s: FormatMessageW failed with error co"...
0x18000e47b  mov     ebx, eax
0x18000e47d  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18000e482  test    ebx, ebx
0x18000e484  jz      short loc_18000E4A3
0x18000e486  jle     short loc_18000E493
0x18000e488  movzx   ebx, bx
0x18000e48b  or      ebx, 80070000h
0x18000e491  test    ebx, ebx
0x18000e493  jns     short loc_18000E4A3
0x18000e495  mov     rcx, [rbp+57h+Buffer]; hMem
0x18000e499  call    cs:__imp_LocalFree
0x18000e49f  mov     [rbp+57h+Buffer], r15
0x18000e4a3  lea     r8, aHelloForBusine_0; "Hello for business enrollment will not "...
0x18000e4aa  test    edi, edi
0x18000e4ac  jz      loc_18000E701
0x18000e4b2  sub     edi, 1
0x18000e4b5  jz      short loc_18000E4C5
0x18000e4b7  cmp     edi, 1
0x18000e4ba  jz      loc_18000E598
0x18000e4c0  jmp     loc_18000E701
0x18000e4c5  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 4
0x18000e4cc  jz      loc_18000E598
0x18000e4d2  mov     ecx, [r12+30h]
0x18000e4d7  call    GetNgcCertEnrollmentName
0x18000e4dc  mov     ecx, [r12+10h]
0x18000e4e1  mov     r14, rax
0x18000e4e4  call    GetNgcPolicyStageResult
0x18000e4e9  mov     ecx, [r12+0Ch]
0x18000e4ee  mov     rsi, rax
0x18000e4f1  call    GetNgcPolicyStageResult
0x18000e4f6  mov     ecx, [r12+14h]
0x18000e4fb  mov     rdi, rax
0x18000e4fe  call    GetNgcPolicyStageResult
0x18000e503  mov     ecx, [r12+20h]
0x18000e508  mov     rbx, rax
0x18000e50b  call    GetNgcPolicyStageResult
0x18000e510  mov     ecx, [r12+1Ch]
0x18000e515  mov     r11, rax
0x18000e518  call    GetNgcPolicyStageResult
0x18000e51d  mov     ecx, [r12+18h]
0x18000e522  mov     r10, rax
0x18000e525  call    GetNgcPolicyStageResult
0x18000e52a  mov     ecx, [r12+4]
0x18000e52f  mov     r9, rax
0x18000e532  call    GetNgcPolicyStageResult
0x18000e537  mov     ecx, [r12]
0x18000e53b  mov     rdx, rax
0x18000e53e  call    GetNgcPolicyStageResult
0x18000e543  mov     r13, [rbp+57h+Buffer]
0x18000e547  mov     [rsp+0C0h+var_68], r14
0x18000e54c  test    r13, r13
0x18000e54f  mov     [rsp+0C0h+var_70], rsi
0x18000e554  mov     [rsp+0C0h+var_78], rdi
0x18000e559  cmovnz  r8, r13
0x18000e55d  mov     [rsp+0C0h+var_80], rbx
0x18000e562  mov     [rsp+0C0h+var_88], r11
0x18000e567  mov     [rsp+0C0h+Arguments], r10
0x18000e56c  mov     qword ptr [rsp+0C0h+nSize], r9
0x18000e571  mov     r9, rax
0x18000e574  mov     [rsp+0C0h+lpBuffer], rdx
0x18000e579  call    McTemplateU0zzzzzzzzzz_EventWriteTransfer
0x18000e57e  test    eax, eax
0x18000e580  jz      short loc_18000E598
0x18000e582  mov     r8d, eax
0x18000e585  lea     rdx, aLoggerWritengc_5; "Logger::WriteNgcPolicyEvaluationComplet"...
0x18000e58c  lea     rcx, aSEventwritengc_4; "%s: EventWriteNgcEnrollPolicyWillNotRun"...
0x18000e593  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e598  test    dword ptr [r12+28h], 0FFFFFFFDh
0x18000e5a1  mov     r14, r15
0x18000e5a4  mov     [rbp+57h+var_50], r15
0x18000e5a8  jnz     short loc_18000E5E0
0x18000e5aa  mov     r9d, [r12+2Ch]
0x18000e5af  mov     ecx, r9d
0x18000e5b2  call    ?GetLogonTemplateName@@YAPEBGW4LogonTemplateState@@@Z; GetLogonTemplateName(LogonTemplateState)
0x18000e5b7  mov     ecx, [r12+28h]
0x18000e5bc  mov     r10, rax
0x18000e5bf  call    GetNgcPolicyStageResult
0x18000e5c4  mov     r8, rax
0x18000e5c7  mov     [rsp+0C0h+lpBuffer], r10
0x18000e5cc  lea     rcx, [rbp+57h+var_50]; unsigned __int16 **
0x18000e5d0  lea     rdx, aSDS; "%s ( %d : %s ) "
0x18000e5d7  call    ?StringPrint@Logger@@SAJAEAPEAGPEBGZZ; Logger::StringPrint(ushort * &,ushort const *,...)
0x18000e5dc  mov     r14, [rbp+57h+var_50]
0x18000e5e0  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 4
0x18000e5e7  jz      loc_18000E6F2
0x18000e5ed  mov     ecx, [r12+30h]
0x18000e5f2  call    GetNgcCertEnrollmentName
0x18000e5f7  mov     ecx, [r12+8]
0x18000e5fc  mov     [rbp+57h+var_50], rax
0x18000e600  call    GetNgcPolicyStageResult
0x18000e605  mov     [rbp+57h+var_48], rax
0x18000e609  test    r14, r14
0x18000e60c  jz      short loc_18000E613
0x18000e60e  mov     r15, r14
0x18000e611  jmp     short loc_18000E620
0x18000e613  mov     ecx, [r12+28h]
0x18000e618  call    GetNgcPolicyStageResult
0x18000e61d  mov     r15, rax
0x18000e620  mov     ecx, [r12+24h]
0x18000e625  call    GetNgcPolicyStageResult
0x18000e62a  mov     ecx, [r12+0Ch]
0x18000e62f  mov     rsi, rax
0x18000e632  call    GetNgcPolicyStageResult
0x18000e637  mov     ecx, [r12+14h]
0x18000e63c  mov     rdi, rax
0x18000e63f  call    GetNgcPolicyStageResult
0x18000e644  mov     ecx, [r12+20h]
0x18000e649  mov     rbx, rax
0x18000e64c  call    GetNgcPolicyStageResult
0x18000e651  mov     ecx, [r12+1Ch]
0x18000e656  mov     r11, rax
0x18000e659  call    GetNgcPolicyStageResult
0x18000e65e  mov     ecx, [r12+18h]
0x18000e663  mov     r10, rax
0x18000e666  call    GetNgcPolicyStageResult
0x18000e66b  mov     ecx, [r12+4]
0x18000e670  mov     r9, rax
0x18000e673  call    GetNgcPolicyStageResult
0x18000e678  mov     ecx, [r12]
0x18000e67c  mov     rdx, rax
0x18000e67f  call    GetNgcPolicyStageResult
0x18000e684  mov     r13, [rbp+57h+Buffer]
0x18000e688  lea     r8, aHelloForBusine_0; "Hello for business enrollment will not "...
0x18000e68f  mov     rcx, [rbp+57h+var_50]
0x18000e693  test    r13, r13
0x18000e696  mov     [rsp+0C0h+var_58], rcx
0x18000e69b  mov     rcx, [rbp+57h+var_48]
0x18000e69f  cmovnz  r8, r13
0x18000e6a3  mov     [rsp+0C0h+var_60], rcx
0x18000e6a8  mov     [rsp+0C0h+var_68], r15
0x18000e6ad  mov     [rsp+0C0h+var_70], rsi
0x18000e6b2  mov     [rsp+0C0h+var_78], rdi
0x18000e6b7  mov     [rsp+0C0h+var_80], rbx
0x18000e6bc  mov     [rsp+0C0h+var_88], r11
0x18000e6c1  mov     [rsp+0C0h+Arguments], r10
0x18000e6c6  mov     qword ptr [rsp+0C0h+nSize], r9
0x18000e6cb  mov     r9, rax
0x18000e6ce  mov     [rsp+0C0h+lpBuffer], rdx
0x18000e6d3  call    McTemplateU0zzzzzzzzzzzz_EventWriteTransfer
0x18000e6d8  test    eax, eax
0x18000e6da  jz      short loc_18000E6F2
0x18000e6dc  mov     r8d, eax
0x18000e6df  lea     rdx, aLoggerWritengc_5; "Logger::WriteNgcPolicyEvaluationComplet"...
0x18000e6e6  lea     rcx, aSEventwritengc_6; "%s: EventWriteNgcEnrollPolicyWillNotRun"...
0x18000e6ed  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e6f2  mov     rcx, r14; lpMem
0x18000e6f5  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000e6fa  lea     r8, aHelloForBusine_0; "Hello for business enrollment will not "...
0x18000e701  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 4
0x18000e708  jz      loc_18000E7ED
0x18000e70e  mov     ecx, [r12+44h]
0x18000e713  call    GetNgcPolicyStageResult
0x18000e718  mov     ecx, [r12+40h]
0x18000e71d  mov     r15, rax
0x18000e720  call    GetNgcPolicyStageResult
0x18000e725  mov     ecx, [r12+30h]
0x18000e72a  mov     r14, rax
0x18000e72d  call    GetNgcCertEnrollmentName
0x18000e732  mov     ecx, [r12+0Ch]
0x18000e737  mov     rsi, rax
0x18000e73a  call    GetNgcPolicyStageResult
0x18000e73f  mov     ecx, [r12+14h]
0x18000e744  mov     rdi, rax
0x18000e747  call    GetNgcPolicyStageResult
0x18000e74c  mov     ecx, [r12+20h]
0x18000e751  mov     rbx, rax
0x18000e754  call    GetNgcPolicyStageResult
0x18000e759  mov     ecx, [r12+1Ch]
0x18000e75e  mov     r11, rax
0x18000e761  call    GetNgcPolicyStageResult
0x18000e766  mov     ecx, [r12+18h]
0x18000e76b  mov     r10, rax
0x18000e76e  call    GetNgcPolicyStageResult
0x18000e773  mov     ecx, [r12+4]
0x18000e778  mov     r9, rax
0x18000e77b  call    GetNgcPolicyStageResult
0x18000e780  mov     ecx, [r12]
0x18000e784  mov     rdx, rax
0x18000e787  call    GetNgcPolicyStageResult
0x18000e78c  mov     r13, [rbp+57h+Buffer]
0x18000e790  mov     [rsp+0C0h+var_60], r15
0x18000e795  test    r13, r13
0x18000e798  mov     [rsp+0C0h+var_68], r14
0x18000e79d  mov     [rsp+0C0h+var_70], rsi
0x18000e7a2  cmovnz  r8, r13
0x18000e7a6  mov     [rsp+0C0h+var_78], rdi
0x18000e7ab  mov     [rsp+0C0h+var_80], rbx
0x18000e7b0  mov     [rsp+0C0h+var_88], r11
0x18000e7b5  mov     [rsp+0C0h+Arguments], r10
0x18000e7ba  mov     qword ptr [rsp+0C0h+nSize], r9
0x18000e7bf  mov     r9, rax
0x18000e7c2  mov     [rsp+0C0h+lpBuffer], rdx
0x18000e7c7  lea     rdx, NgcEnrollPolicyWillNotRunNoCert
0x18000e7ce  call    McTemplateU0zzzzzzzzzzz_EventWriteTransfer
0x18000e7d3  test    eax, eax
0x18000e7d5  jz      short loc_18000E7ED
0x18000e7d7  lea     rcx, aSEventwritengc; "%s: EventWriteNgcEnrollPolicyWillNotRun"...
0x18000e7de  mov     r8d, eax
0x18000e7e1  lea     rdx, aLoggerWritengc_5; "Logger::WriteNgcPolicyEvaluationComplet"...
0x18000e7e8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e7ed  mov     rcx, [rbp+57h+Buffer]; hMem
0x18000e7f1  call    cs:__imp_LocalFree
  ... truncated ...
```
