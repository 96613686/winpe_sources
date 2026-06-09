# KeyManager::CheckContainerPolicy(bool *)

- ea: `0x180081698`
- end: `0x18008195e`
- name: `?CheckContainerPolicy@KeyManager@@QEAAJPEA_N@Z`
- size: `710`
- prototype: `__int64 __fastcall(KeyManager *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180080ca4`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x18000bac0`
- `0x1800307c4`
- `0x180081698`
- `0x180083004`
- `0x1800909fc`
- `0x180091dc8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800817af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800817ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800817af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800817ec`
- `cryptngc!NgcFreeEnumState` at `0x1800817b9`
- `cryptngc!NgcFreeEnumState` at `0x1800817b9`
- `cryptngc!NgcEnumContainers` at `0x180081805`
- `cryptngc!NgcEnumContainers` at `0x180081805`
- `cryptngc!NgcQueryHardwarePolicy` at `0x180081729`
- `cryptngc!NgcQueryHardwarePolicy` at `0x180081729`

## string_xrefs

- `0x180081904`: `Logger::WriteNgcEnumContainersFailureEvent`
- `0x1800818fd`: `EventWriteNgcEnumContainersFailureEvent`
- `0x18008176b`: `EventWriteNgcQueryPolicyFailureEvent`
- `0x180081772`: `Logger::WriteNgcQueryPolicyFailureEvent`
- `0x1800816dc`: `compliant`
- `0x1800816ef`: `compliant`
- `0x18008179b`: `%s: NgcQueryHardwarePolicy failed. SID: %s, IDP domain: %s, Tenant domain: %s, Error code: 0x%08x.`
- `0x18008191a`: `%s: NgcEnumContainers failed. SID: %s, Error code: 0x%08x.`
- `0x180081939`: `%s: NGC container is not found. SID: %s, IDP domain: %s, Tenant domain: %s, Error code: 0x%08x.`
- `0x18008182c`: `%s: NgcEnumContainers returns NULL pContainerInfo. SID: %s, HRESULT: 0x%08x.`
- `0x1800818c7`: `%s: NGC container is in a bad state. SID: %s, status: %d`
- `0x1800818a1`: `%s: NGC policy requires hardware container. Existing software container should be deleted.`

## pseudocode

```c
__int64 __fastcall KeyManager::CheckContainerPolicy(KeyManager *this, bool *a2)
{
  int UserSid; // ebx
  unsigned __int16 *v4; // rsi
  int v5; // eax
  int v6; // ecx
  unsigned int v7; // eax
  int v9; // eax
  __int64 v10; // rcx
  const unsigned __int16 **v11; // r8
  __int64 v12; // r8
  unsigned int v13; // eax
  __int64 v14; // [rsp+28h] [rbp-18h]
  __int64 v15; // [rsp+30h] [rbp-10h] BYREF
  int v16; // [rsp+78h] [rbp+38h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int16 *v18; // [rsp+88h] [rbp+48h] BYREF

  v18 = 0;
  hMem = 0;
  v15 = 0;
  v16 = 0;
  if ( !a2 )
  {
    UserSid = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"KeyManager::CheckContainerPolicy", L"compliant");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"KeyManager::CheckContainerPolicy", L"compliant");
    goto LABEL_10;
  }
  *a2 = 1;
  UserSid = KeyManager::GetUserSid(this, &v18);
  if ( UserSid < 0 )
  {
LABEL_9:
    *a2 = 0;
    goto LABEL_10;
  }
  v4 = v18;
  v5 = NgcQueryHardwarePolicy(v18, 0, 0, &v16);
  UserSid = v5;
  if ( v5 < 0 )
  {
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v7 = McTemplateU0zzzd_EventWriteTransfer(
             v6,
             (unsigned int)NgcQueryPolicyFailureEvent,
             (_DWORD)v4,
             (unsigned int)L"null",
             (__int64)L"null",
             v5);
      if ( v7 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNgcQueryPolicyFailureEvent",
          L"EventWriteNgcQueryPolicyFailureEvent",
          v7);
    }
    LODWORD(v14) = UserSid;
    Logger::TraceError(
      L"%s: NgcQueryHardwarePolicy failed. SID: %s, IDP domain: %s, Tenant domain: %s, Error code: 0x%08x.",
      L"KeyManager::CheckContainerPolicy",
      v4,
      L"null",
      L"null",
      v14);
    goto LABEL_9;
  }
  if ( v16 == 1 )
  {
    Logger::TraceVerbose((wchar_t *)L"%s: NGC policy requires hardware container", L"KeyManager::CheckContainerPolicy");
    while ( 1 )
    {
      LocalFree(hMem);
      hMem = 0;
      v9 = NgcEnumContainers(v4, &hMem, &v15);
      UserSid = v9;
      if ( v9 == -2146893782 )
      {
        Logger::TraceVerbose(
          (wchar_t *)L"%s: NGC container is not found. SID: %s, IDP domain: %s, Tenant domain: %s, Error code: 0x%08x.",
          L"KeyManager::CheckContainerPolicy",
          v4,
          0,
          0,
          -2146893782);
        UserSid = 0;
        goto LABEL_10;
      }
      if ( v9 < 0 )
      {
        if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
        {
          v13 = McTemplateU0zq_EventWriteTransfer(v10, NgcEnumContainersFailureEvent, v4, (unsigned int)v9);
          if ( v13 )
            Logger::TraceError(
              L"%s: %s failed with win32 error code: 0x%08x.",
              L"Logger::WriteNgcEnumContainersFailureEvent",
              L"EventWriteNgcEnumContainersFailureEvent",
              v13);
        }
        Logger::TraceError(
          L"%s: NgcEnumContainers failed. SID: %s, Error code: 0x%08x.",
          L"KeyManager::CheckContainerPolicy",
          v4,
          (unsigned int)UserSid);
        goto LABEL_9;
      }
      v11 = (const unsigned __int16 **)hMem;
      if ( !hMem )
      {
        Logger::TraceError(
          L"%s: NgcEnumContainers returns NULL pContainerInfo. SID: %s, HRESULT: 0x%08x.",
          L"KeyManager::CheckContainerPolicy",
          v4,
          (unsigned int)v9);
        v11 = (const unsigned __int16 **)hMem;
      }
      if ( (unsigned int)IsEmptyString(v11[4]) && (unsigned int)IsEmptyString(*(const unsigned __int16 **)(v12 + 40)) )
        break;
      Logger::TraceVerbose(
        (wchar_t *)L"%s: Found other container. IDP domain: %s, Tenant domain: %s, Friendly name: %s. Skipping...",
        L"KeyManager::CheckContainerPolicy",
        *(_QWORD *)(v12 + 32),
        *(_QWORD *)(v12 + 40),
        *(_QWORD *)(v12 + 48));
    }
    Logger::TraceVerbose(
      (wchar_t *)L"%s: Found AAD NGC container with name %s.",
      L"KeyManager::CheckContainerPolicy",
      *(_QWORD *)(v12 + 48));
    if ( (*((_BYTE *)hMem + 56) & 2) == 0 )
    {
      Logger::TraceVerbose(
        (wchar_t *)L"%s: NGC policy requires hardware container. Existing software container should be deleted.",
        L"KeyManager::CheckContainerPolicy");
      goto LABEL_9;
    }
    if ( *((_DWORD *)hMem + 4) != 2 )
    {
      Logger::TraceVerbose(
        (wchar_t *)L"%s: NGC container is in a bad state. SID: %s, status: %d",
        L"KeyManager::CheckContainerPolicy",
        v4);
      goto LABEL_9;
    }
  }
LABEL_10:
  LocalFree(hMem);
  NgcFreeEnumState(v15);
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x180081698  push    rbp
0x18008169a  push    rbx
0x18008169b  push    rsi
0x18008169c  push    rdi
0x18008169d  push    r14
0x18008169f  mov     rbp, rsp
0x1800816a2  sub     rsp, 40h
0x1800816a6  mov     [rbp+arg_18], 0
0x1800816ae  mov     r14, rdx
0x1800816b1  mov     [rbp+hMem], 0
0x1800816b9  mov     [rbp+var_10], 0
0x1800816c1  mov     [rbp+arg_8], 0
0x1800816c8  test    rdx, rdx
0x1800816cb  jnz     short loc_180081703
0x1800816cd  lea     rdi, aKeymanagerChec; "KeyManager::CheckContainerPolicy"
0x1800816d4  mov     ebx, 80070057h
0x1800816d9  mov     rdx, rdi
0x1800816dc  lea     r8, aCompliant; "compliant"
0x1800816e3  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800816ea  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800816ef  lea     rdx, aCompliant; "compliant"
0x1800816f6  mov     rcx, rdi; unsigned __int16 *
0x1800816f9  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800816fe  jmp     loc_1800817AB
0x180081703  mov     byte ptr [rdx], 1
0x180081706  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x18008170a  call    ?GetUserSid@KeyManager@@AEAAJPEAPEAG@Z; KeyManager::GetUserSid(ushort * *)
0x18008170f  mov     ebx, eax
0x180081711  test    eax, eax
0x180081713  js      loc_1800817A7
0x180081719  mov     rsi, [rbp+arg_18]
0x18008171d  lea     r9, [rbp+arg_8]
0x180081721  mov     rcx, rsi
0x180081724  xor     r8d, r8d
0x180081727  xor     edx, edx
0x180081729  call    cs:__imp_NgcQueryHardwarePolicy
0x18008172f  mov     ebx, eax
0x180081731  test    eax, eax
0x180081733  jns     loc_1800817CC
0x180081739  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180081740  lea     rdi, aNull; "null"
0x180081747  jz      short loc_180081785
0x180081749  mov     dword ptr [rsp+40h+var_18], eax
0x18008174d  lea     rdx, NgcQueryPolicyFailureEvent
0x180081754  mov     r9, rdi
0x180081757  mov     [rsp+40h+var_20], rdi
0x18008175c  mov     r8, rsi
0x18008175f  call    McTemplateU0zzzd_EventWriteTransfer
0x180081764  test    eax, eax
0x180081766  jz      short loc_180081785
0x180081768  mov     r9d, eax
0x18008176b  lea     r8, aEventwritengcq; "EventWriteNgcQueryPolicyFailureEvent"
0x180081772  lea     rdx, aLoggerWritengc_11; "Logger::WriteNgcQueryPolicyFailureEvent"
0x180081779  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180081780  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180081785  mov     dword ptr [rsp+40h+var_18], ebx
0x180081789  lea     rdx, aKeymanagerChec; "KeyManager::CheckContainerPolicy"
0x180081790  mov     r9, rdi
0x180081793  mov     [rsp+40h+var_20], rdi
0x180081798  mov     r8, rsi
0x18008179b  lea     rcx, aSNgcqueryhardw; "%s: NgcQueryHardwarePolicy failed. SID:"...
0x1800817a2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800817a7  mov     byte ptr [r14], 0
0x1800817ab  mov     rcx, [rbp+hMem]; hMem
0x1800817af  call    cs:__imp_LocalFree
0x1800817b5  mov     rcx, [rbp+var_10]
0x1800817b9  call    cs:__imp_NgcFreeEnumState
0x1800817bf  mov     eax, ebx
0x1800817c1  add     rsp, 40h
0x1800817c5  pop     r14
0x1800817c7  pop     rdi
0x1800817c8  pop     rsi
0x1800817c9  pop     rbx
0x1800817ca  pop     rbp
0x1800817cb  retn
0x1800817cc  cmp     [rbp+arg_8], 1
0x1800817d0  jnz     short loc_1800817AB
0x1800817d2  lea     rdi, aKeymanagerChec; "KeyManager::CheckContainerPolicy"
0x1800817d9  mov     rdx, rdi
0x1800817dc  lea     rcx, aSNgcPolicyRequ; "%s: NGC policy requires hardware contai"...
0x1800817e3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800817e8  mov     rcx, [rbp+hMem]; hMem
0x1800817ec  call    cs:__imp_LocalFree
0x1800817f2  lea     r8, [rbp+var_10]
0x1800817f6  mov     [rbp+hMem], 0
0x1800817fe  lea     rdx, [rbp+hMem]
0x180081802  mov     rcx, rsi
0x180081805  call    cs:__imp_NgcEnumContainers
0x18008180b  mov     ebx, eax
0x18008180d  cmp     eax, 8009002Ah
0x180081812  jz      loc_180081931
0x180081818  test    eax, eax
0x18008181a  js      loc_1800818DB
0x180081820  mov     r8, [rbp+hMem]
0x180081824  test    r8, r8
0x180081827  jnz     short loc_180081842
0x180081829  mov     r9d, eax
0x18008182c  lea     rcx, aSNgcenumcontai; "%s: NgcEnumContainers returns NULL pCon"...
0x180081833  mov     r8, rsi
0x180081836  mov     rdx, rdi
0x180081839  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008183e  mov     r8, [rbp+hMem]
0x180081842  mov     rcx, [r8+20h]; unsigned __int16 *
0x180081846  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18008184b  test    eax, eax
0x18008184d  jz      short loc_18008185C
0x18008184f  mov     rcx, [r8+28h]; unsigned __int16 *
0x180081853  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180081858  test    eax, eax
0x18008185a  jnz     short loc_180081881
0x18008185c  mov     rax, [r8+30h]
0x180081860  lea     rcx, aSFoundOtherCon; "%s: Found other container. IDP domain: "...
0x180081867  mov     r9, [r8+28h]
0x18008186b  mov     rdx, rdi
0x18008186e  mov     r8, [r8+20h]
0x180081872  mov     [rsp+40h+var_20], rax
0x180081877  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18008187c  jmp     loc_1800817E8
0x180081881  mov     r8, [r8+30h]
0x180081885  lea     rcx, aSFoundAadNgcCo; "%s: Found AAD NGC container with name %"...
0x18008188c  mov     rdx, rdi
0x18008188f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180081894  mov     rax, [rbp+hMem]
0x180081898  test    byte ptr [rax+38h], 2
0x18008189c  jnz     short loc_1800818B2
0x18008189e  mov     rdx, rdi
0x1800818a1  lea     rcx, aSNgcPolicyRequ_0; "%s: NGC policy requires hardware contai"...
0x1800818a8  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800818ad  jmp     loc_1800817A7
0x1800818b2  mov     rax, [rbp+hMem]
0x1800818b6  mov     r9d, [rax+10h]
0x1800818ba  cmp     r9d, 2
0x1800818be  jz      loc_1800817AB
0x1800818c4  mov     r8, rsi
0x1800818c7  lea     rcx, aSNgcContainerI; "%s: NGC container is in a bad state. SI"...
0x1800818ce  mov     rdx, rdi
0x1800818d1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800818d6  jmp     loc_1800817A7
0x1800818db  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x1800818e2  jz      short loc_180081917
0x1800818e4  mov     r9d, ebx
0x1800818e7  lea     rdx, NgcEnumContainersFailureEvent
0x1800818ee  mov     r8, rsi
0x1800818f1  call    McTemplateU0zq_EventWriteTransfer
0x1800818f6  test    eax, eax
0x1800818f8  jz      short loc_180081917
0x1800818fa  mov     r9d, eax
0x1800818fd  lea     r8, aEventwritengce_0; "EventWriteNgcEnumContainersFailureEvent"
0x180081904  lea     rdx, aLoggerWritengc_27; "Logger::WriteNgcEnumContainersFailureEv"...
0x18008190b  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180081912  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180081917  mov     r9d, ebx
0x18008191a  lea     rcx, aSNgcenumcontai_0; "%s: NgcEnumContainers failed. SID: %s, "...
0x180081921  mov     r8, rsi
0x180081924  mov     rdx, rdi
0x180081927  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008192c  jmp     loc_1800817A7
0x180081931  mov     dword ptr [rsp+40h+var_18], 8009002Ah
0x180081939  lea     rcx, aSNgcContainerI_0; "%s: NGC container is not found. SID: %s"...
0x180081940  xor     r9d, r9d
0x180081943  mov     [rsp+40h+var_20], 0
0x18008194c  mov     r8, rsi
0x18008194f  mov     rdx, rdi
0x180081952  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180081957  xor     ebx, ebx
0x180081959  jmp     loc_1800817AB
```
