# NgcRegController::SaveStatus(struct_ngc_reg_response const *,ulong)

- ea: `0x180080674`
- end: `0x180080bbd`
- name: `?SaveStatus@NgcRegController@@AEAAJPEBUstruct_ngc_reg_response@@K@Z`
- size: `1353`
- prototype: `__int64 __fastcall(NgcRegController *__hidden this, const struct struct_ngc_reg_response *, unsigned int)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18007e020`

## callees

- `0x1800012a4`
- `0x180002030`
- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180012948`
- `0x18001b560`
- `0x18001c02c`
- `0x1800204f0`
- `0x1800307c4`
- `0x180044300`
- `0x180051604`
- `0x180055174`
- `0x180055194`
- `0x180080674`
- `0x18008305c`
- `0x180083078`
- `0x180083094`
- `0x180094d24`
- `0x1800952b4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180080ac3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180080ac3`
- `RPCRT4!UuidCompare` at `0x180080899`
- `RPCRT4!UuidCompare` at `0x1800808e6`
- `RPCRT4!UuidCompare` at `0x180080899`
- `RPCRT4!UuidCompare` at `0x1800808e6`
- `RPCRT4!UuidFromStringW` at `0x18008081d`
- `RPCRT4!UuidFromStringW` at `0x18008081d`

## string_xrefs

- `0x1800809bd`: `StringCompare`
- `0x1800808a6`: `%s: The key ID to be deleted does not match the key ID in the registry.`
- `0x1800808f3`: `%s: The patched key ID does not match the key ID in the registry.`
- `0x1800808cd`: `NgcRegStorage::Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcRegController::SaveStatus(NgcRegController *this, const unsigned __int16 **a2, int a3)
{
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdx
  unsigned __int16 *v8; // rcx
  unsigned int v9; // eax
  UUID *Key; // rax
  NgcStatusStorage *v11; // rcx
  int v12; // eax
  const wchar_t *v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rcx
  const WCHAR *v16; // rcx
  const WCHAR *v17; // rcx
  __int64 v18; // r9
  __int64 *v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  RPC_STATUS Status; // [rsp+54h] [rbp-ACh] BYREF
  int v23; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v26; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v28[4]; // [rsp+80h] [rbp-80h] BYREF
  UUID Uuid1[4]; // [rsp+C0h] [rbp-40h] BYREF
  UUID Uuid; // [rsp+100h] [rbp+0h] BYREF
  int v31; // [rsp+110h] [rbp+10h] BYREF
  char v32; // [rsp+114h] [rbp+14h]
  _BYTE v33[16]; // [rsp+118h] [rbp+18h] BYREF
  GUID ActivityId; // [rsp+128h] [rbp+28h] BYREF

  v6 = 0;
  Status = 0;
  Uuid = 0;
  memset(Uuid1, 0, sizeof(Uuid1));
  v31 = 0;
  v32 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v31);
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
  {
    v25 = 0x1000000;
    if ( v32 )
      _tlgGuidIsZero(&ActivityId);
    v20 = &v25;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      (__int64)&dword_18013D150,
      (__int64)byte_18012A845);
  }
  if ( !*((_DWORD *)this + 4) )
  {
    Logger::TraceInformation(L"%s: no operation performed. Nothing to save...", L"NgcRegController::SaveStatus");
    goto LABEL_55;
  }
  if ( !*((_QWORD *)this + 1) )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"NgcRegController::SaveStatus", L"_pKeyManager");
    v7 = L"_pKeyManager";
LABEL_10:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"NgcRegController::SaveStatus", v7);
    goto LABEL_55;
  }
  if ( !*(_QWORD *)this )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"NgcRegController::SaveStatus", L"_pStorage");
    v7 = L"_pStorage";
    goto LABEL_10;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"NgcRegController::SaveStatus", L"pResponse");
    v7 = L"pResponse";
    goto LABEL_10;
  }
  if ( (unsigned int)IsEmptyString(*a2) )
  {
    v6 = -2145647639;
    Logger::TraceError(L"%s: Key ID is empty.", L"NgcRegController::SaveStatus");
    goto LABEL_55;
  }
  v9 = UuidFromStringW(v8, &Uuid);
  Status = v9;
  if ( v9 )
  {
    v6 = -2145647639;
    Logger::TraceError(L"%s: Key ID is not a valid GUID. Error code: 0x%08x.", L"NgcRegController::SaveStatus", v9);
    goto LABEL_55;
  }
  Key = (UUID *)NgcStatusStorage::GetKey(*(_QWORD *)this, v28);
  Uuid1[0] = *Key;
  Uuid1[1] = Key[1];
  Uuid1[2] = Key[2];
  Uuid1[3] = Key[3];
  switch ( *((_DWORD *)this + 4) )
  {
    case 1:
LABEL_29:
      if ( a3 == 200 )
      {
        Uuid1[0] = Uuid;
        if ( (unsigned int)KeyManager::HasUserKey(*((KeyManager **)this + 1)) )
        {
          Uuid1[2].Data1 = *(_DWORD *)(v14 + 104);
          *(_QWORD *)&Uuid1[1].Data1 = *(_QWORD *)(v14 + 64);
        }
        if ( (unsigned int)KeyManager::HasAikCert((KeyManager *)v14)
          && (unsigned int)KeyManager::HasUserKeyAtt((KeyManager *)v15) )
        {
          *(_QWORD *)Uuid1[1].Data4 = 0x100000002LL;
        }
        else
        {
          *(_QWORD *)Uuid1[1].Data4 = 1;
        }
        *(UUID *)Uuid1[2].Data4 = *(UUID *)(v15 + 16);
        *(_QWORD *)Uuid1[3].Data4 = *(_QWORD *)(v15 + 32);
        goto LABEL_52;
      }
      if ( a3 != 400 )
        break;
      v16 = a2[4];
      if ( !v16 )
        break;
      v21 = 0;
      v12 = StringCompare(v16, L"attestation_failure", 1u, &v21);
      v6 = v12;
      if ( v12 >= 0 )
      {
        if ( !v21 )
          break;
        v17 = a2[6];
        if ( !v17 )
          break;
        v12 = StringCompare(v17, L"ERROR_AIK_RENEW", 1u, &v21);
        v6 = v12;
        if ( v12 >= 0 )
        {
          if ( v21 )
          {
            *(_DWORD *)&Uuid1[1].Data4[4] = 3;
LABEL_52:
            v28[0] = Uuid1[0];
            v28[1] = Uuid1[1];
            v28[2] = Uuid1[2];
            v28[3] = Uuid1[3];
            v12 = NgcStatusStorage::Save(*(_QWORD *)this, v28);
            v6 = v12;
            if ( v12 >= 0 )
              break;
            v13 = L"NgcRegStorage::Save";
            goto LABEL_54;
          }
          v12 = StringCompare(a2[6], L"ERROR_RETRY", 1u, &v21);
          v6 = v12;
          if ( v12 >= 0 )
          {
            if ( v21 )
            {
              *(_DWORD *)&Uuid1[1].Data4[4] = 4;
              goto LABEL_52;
            }
            v12 = StringCompare(a2[6], L"ERROR_FAIL", 1u, &v21);
            v6 = v12;
            if ( v12 >= 0 )
            {
              if ( !v21 )
                break;
              *(_DWORD *)&Uuid1[1].Data4[4] = 2;
              goto LABEL_52;
            }
          }
        }
      }
      v13 = L"StringCompare";
      goto LABEL_54;
    case 2:
      if ( UuidCompare(Uuid1, &Uuid, &Status) )
        Logger::TraceWarning(
          (wchar_t *)L"%s: The patched key ID does not match the key ID in the registry.",
          L"NgcRegController::SaveStatus");
      goto LABEL_29;
    case 3:
      if ( UuidCompare(Uuid1, &Uuid, &Status) )
        Logger::TraceWarning(
          (wchar_t *)L"%s: The key ID to be deleted does not match the key ID in the registry.",
          L"NgcRegController::SaveStatus");
      if ( a3 == 200 )
      {
        v12 = NgcStatusStorage::Delete(v11);
        v6 = v12;
        if ( v12 < 0 )
        {
          v13 = L"NgcRegStorage::Delete";
LABEL_54:
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"NgcRegController::SaveStatus",
            v13,
            (unsigned int)v12,
            v20);
        }
      }
      break;
  }
LABEL_55:
  if ( v32 )
    EventActivityIdControl(4u, &ActivityId);
  v31 = 2;
  if ( (unsigned int)dword_18013D150 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18013D150, 0x400000000000LL) )
  {
    v26 = a2[4];
    v21 = v6;
    v23 = *(_DWORD *)&Uuid1[1].Data4[4];
    v24 = *(_DWORD *)Uuid1[1].Data4;
    LODWORD(v25) = Uuid1[2].Data1;
    v27 = 16779264;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (__int64)&dword_18013D150,
      (__int64)&word_18012AA5E,
      (__int64)v33,
      v18,
      (__int64)&v27,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v21,
      &v26);
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"NgcRegController::SaveStatus", v6);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>((__int64)&v31);
  return v6;
}

```

## disassembly

```asm
0x180080674  mov     [rsp-8+arg_10], rbx
0x180080679  mov     [rsp-8+arg_18], rsi
0x18008067e  push    rbp
0x18008067f  push    rdi
0x180080680  push    r12
0x180080682  push    r14
0x180080684  push    r15
0x180080686  lea     rbp, [rsp-40h]
0x18008068b  sub     rsp, 140h
0x180080692  mov     rax, cs:__security_cookie
0x180080699  xor     rax, rsp
0x18008069c  mov     [rbp+60h+var_28], rax
0x1800806a0  mov     edi, r8d
0x1800806a3  mov     r14, rdx
0x1800806a6  mov     rsi, rcx
0x1800806a9  xor     r15d, r15d
0x1800806ac  mov     ebx, r15d
0x1800806af  mov     [rsp+160h+Status], r15d
0x1800806b4  xorps   xmm0, xmm0
0x1800806b7  movups  xmmword ptr [rbp+60h+Uuid.Data1], xmm0
0x1800806bb  mov     [rbp+60h+Uuid1.Data1], r15d
0x1800806bf  xorps   xmm1, xmm1
0x1800806c2  movups  xmmword ptr [rbp+60h+Uuid1.Data2], xmm1
0x1800806c6  movups  [rbp+60h+var_8C], xmm1
0x1800806ca  movups  xmmword ptr [rbp+60h+var_7C], xmm1
0x1800806ce  movups  xmmword ptr [rbp+60h+var_7C+0Ch], xmm1
0x1800806d2  mov     [rbp+60h+var_50], r15d
0x1800806d6  mov     [rbp+60h+var_4C], r15b
0x1800806da  lea     rcx, [rbp+60h+var_50]
0x1800806de  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_hcdjTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x1800806e3  mov     eax, cs:dword_18013D150
0x1800806e9  cmp     eax, 5
0x1800806ec  jbe     short loc_18008074C
0x1800806ee  mov     rdx, 400000000000h
0x1800806f8  lea     rcx, dword_18013D150
0x1800806ff  call    _tlgKeywordOn
0x180080704  test    al, al
0x180080706  jz      short loc_18008074C
0x180080708  mov     [rsp+160h+var_100], 1000000h
0x180080711  cmp     [rbp+60h+var_4C], r15b
0x180080715  jz      short loc_180080728
0x180080717  lea     rcx, [rbp+60h+ActivityId]; struct _GUID *
0x18008071b  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180080720  test    al, al
0x180080722  lea     r9, [rbp+60h+ActivityId]
0x180080726  jz      short loc_18008072B
0x180080728  mov     r9, r15
0x18008072b  lea     rax, [rsp+160h+var_100]
0x180080730  mov     [rsp+160h+var_140], rax
0x180080735  lea     r8, [rbp+60h+var_48]
0x180080739  lea     rdx, byte_18012A845
0x180080740  lea     rcx, dword_18013D150
0x180080747  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18008074c  lea     r12, aNgcregcontroll_10; "NgcRegController::SaveStatus"
0x180080753  cmp     [rsi+10h], r15d
0x180080757  jnz     short loc_18008076D
0x180080759  mov     rdx, r12
0x18008075c  lea     rcx, aSNoOperationPe; "%s: no operation performed. Nothing to "...
0x180080763  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180080768  jmp     loc_180080AB4
0x18008076d  cmp     [rsi+8], r15
0x180080771  jnz     short loc_1800807A2
0x180080773  mov     ebx, 80070057h
0x180080778  lea     r8, aPkeymanager; "_pKeyManager"
0x18008077f  mov     rdx, r12
0x180080782  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180080789  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008078e  lea     rdx, aPkeymanager; "_pKeyManager"
0x180080795  mov     rcx, r12; unsigned __int16 *
0x180080798  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18008079d  jmp     loc_180080AB4
0x1800807a2  cmp     [rsi], r15
0x1800807a5  jnz     short loc_1800807CB
0x1800807a7  mov     ebx, 80070057h
0x1800807ac  lea     r8, aPstorage; "_pStorage"
0x1800807b3  mov     rdx, r12
0x1800807b6  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800807bd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800807c2  lea     rdx, aPstorage; "_pStorage"
0x1800807c9  jmp     short loc_180080795
0x1800807cb  test    r14, r14
0x1800807ce  jnz     short loc_1800807F4
0x1800807d0  mov     ebx, 80070057h
0x1800807d5  lea     r8, aPresponse; "pResponse"
0x1800807dc  mov     rdx, r12
0x1800807df  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800807e6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800807eb  lea     rdx, aPresponse; "pResponse"
0x1800807f2  jmp     short loc_180080795
0x1800807f4  mov     rcx, [r14]; unsigned __int16 *
0x1800807f7  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800807fc  test    eax, eax
0x1800807fe  jz      short loc_180080819
0x180080800  mov     ebx, 801C03E9h
0x180080805  mov     rdx, r12
0x180080808  lea     rcx, aSKeyIdIsEmpty; "%s: Key ID is empty."
0x18008080f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080814  jmp     loc_180080AB4
0x180080819  lea     rdx, [rbp+60h+Uuid]; Uuid
0x18008081d  call    cs:__imp_UuidFromStringW
0x180080823  mov     [rsp+160h+Status], eax
0x180080827  test    eax, eax
0x180080829  jz      short loc_180080847
0x18008082b  mov     ebx, 801C03E9h
0x180080830  mov     r8d, eax
0x180080833  mov     rdx, r12
0x180080836  lea     rcx, aSKeyIdIsNotAVa; "%s: Key ID is not a valid GUID. Error c"...
0x18008083d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080842  jmp     loc_180080AB4
0x180080847  lea     rdx, [rbp+60h+var_E0]
0x18008084b  mov     rcx, [rsi]
0x18008084e  call    ?GetKey@NgcStatusStorage@@QEAA?AUSTRUCT_NGC_REG_KEY@@XZ; NgcStatusStorage::GetKey(void)
0x180080853  movups  xmm3, xmmword ptr [rax]
0x180080856  movaps  xmmword ptr [rbp+60h+Uuid1.Data1], xmm3
0x18008085a  movups  xmm0, xmmword ptr [rax+10h]
0x18008085e  movaps  xmmword ptr [rbp-30h], xmm0
0x180080862  movups  xmm1, xmmword ptr [rax+20h]
0x180080866  movaps  [rbp+60h+var_8C+0Ch], xmm1
0x18008086a  movups  xmm0, xmmword ptr [rax+30h]
0x18008086e  movaps  xmmword ptr [rbp+60h+var_7C+0Ch], xmm0
0x180080872  mov     ecx, [rsi+10h]
0x180080875  sub     ecx, 1
0x180080878  jz      loc_1800808FF
0x18008087e  sub     ecx, 1
0x180080881  jz      short loc_1800808D9
0x180080883  cmp     ecx, 1
0x180080886  jnz     loc_180080AB4
0x18008088c  lea     r8, [rsp+160h+Status]; Status
0x180080891  lea     rdx, [rbp+60h+Uuid]; Uuid2
0x180080895  lea     rcx, [rbp+60h+Uuid1]; Uuid1
0x180080899  call    cs:__imp_UuidCompare
0x18008089f  test    eax, eax
0x1800808a1  jz      short loc_1800808B2
0x1800808a3  mov     rdx, r12
0x1800808a6  lea     rcx, aSTheKeyIdToBeD; "%s: The key ID to be deleted does not m"...
0x1800808ad  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800808b2  cmp     edi, 0C8h
0x1800808b8  jnz     loc_180080AB4
0x1800808be  call    ?Delete@NgcStatusStorage@@QEAAJXZ; NgcStatusStorage::Delete(void)
0x1800808c3  mov     ebx, eax
0x1800808c5  test    eax, eax
0x1800808c7  jns     loc_180080AB4
0x1800808cd  lea     r8, aNgcregstorageD; "NgcRegStorage::Delete"
0x1800808d4  jmp     loc_180080AA2
0x1800808d9  lea     r8, [rsp+160h+Status]; Status
0x1800808de  lea     rdx, [rbp+60h+Uuid]; Uuid2
0x1800808e2  lea     rcx, [rbp+60h+Uuid1]; Uuid1
0x1800808e6  call    cs:__imp_UuidCompare
0x1800808ec  test    eax, eax
0x1800808ee  jz      short loc_1800808FF
0x1800808f0  mov     rdx, r12
0x1800808f3  lea     rcx, aSThePatchedKey; "%s: The patched key ID does not match t"...
0x1800808fa  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800808ff  cmp     edi, 0C8h
0x180080905  jnz     short loc_180080980
0x180080907  mov     eax, [rbp+60h+Uuid.Data1]
0x18008090a  mov     [rbp+60h+Uuid1.Data1], eax
0x18008090d  movsd   xmm0, qword ptr [rbp+60h+Uuid.Data2]
0x180080912  movsd   qword ptr [rbp+60h+Uuid1.Data2], xmm0
0x180080917  mov     eax, dword ptr [rbp+60h+Uuid.Data4+4]
0x18008091a  mov     dword ptr [rbp+60h+Uuid1.Data4+4], eax
0x18008091d  mov     rcx, [rsi+8]; this
0x180080921  call    ?HasUserKey@KeyManager@@QEAAHXZ; KeyManager::HasUserKey(void)
0x180080926  test    eax, eax
0x180080928  jz      short loc_180080938
0x18008092a  mov     eax, [rcx+68h]
0x18008092d  mov     dword ptr [rbp+60h+var_8C+0Ch], eax
0x180080930  mov     rax, [rcx+40h]
0x180080934  mov     [rbp-30h], rax
0x180080938  call    ?HasAikCert@KeyManager@@QEAAHXZ; KeyManager::HasAikCert(void)
0x18008093d  test    eax, eax
0x18008093f  jz      short loc_18008095B
0x180080941  call    ?HasUserKeyAtt@KeyManager@@QEAAHXZ; KeyManager::HasUserKeyAtt(void)
0x180080946  test    eax, eax
0x180080948  jz      short loc_18008095B
0x18008094a  mov     dword ptr [rbp+60h+var_8C+4], 2
0x180080951  mov     edi, 1
0x180080956  mov     dword ptr [rbp+60h+var_8C+8], edi
0x180080959  jmp     short loc_180080963
0x18008095b  mov     qword ptr [rbp+60h+var_8C+4], 1
0x180080963  mov     rax, [rcx+10h]
0x180080967  mov     qword ptr [rbp+60h+var_7C+4], rax
0x18008096b  mov     rax, [rcx+18h]
0x18008096f  mov     qword ptr [rbp+60h+var_7C+0Ch], rax
0x180080973  mov     rax, [rcx+20h]
0x180080977  mov     [rbp+60h+var_68], rax
0x18008097b  jmp     loc_180080A69
0x180080980  cmp     edi, 190h
0x180080986  jnz     loc_180080AB4
0x18008098c  mov     rcx, [r14+20h]; lpString1
0x180080990  test    rcx, rcx
0x180080993  jz      loc_180080AB4
0x180080999  mov     [rsp+160h+var_110], r15d
0x18008099e  lea     r9, [rsp+160h+var_110]; int *
0x1800809a3  mov     edi, 1
0x1800809a8  mov     r8d, edi; unsigned int
0x1800809ab  lea     rdx, aAttestationFai; "attestation_failure"
0x1800809b2  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x1800809b7  mov     ebx, eax
0x1800809b9  test    eax, eax
0x1800809bb  jns     short loc_1800809C9
0x1800809bd  lea     r8, aStringcompare; "StringCompare"
0x1800809c4  jmp     loc_180080AA2
0x1800809c9  cmp     [rsp+160h+var_110], r15d
0x1800809ce  jz      loc_180080AB4
0x1800809d4  mov     rcx, [r14+30h]; lpString1
0x1800809d8  test    rcx, rcx
0x1800809db  jz      loc_180080AB4
0x1800809e1  lea     r9, [rsp+160h+var_110]; int *
0x1800809e6  mov     r8d, edi; unsigned int
0x1800809e9  lea     rdx, aErrorAikRenew_0; "ERROR_AIK_RENEW"
0x1800809f0  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x1800809f5  mov     ebx, eax
0x1800809f7  test    eax, eax
0x1800809f9  js      short loc_1800809BD
0x1800809fb  cmp     [rsp+160h+var_110], r15d
0x180080a00  jz      short loc_180080A0B
0x180080a02  mov     dword ptr [rbp+60h+var_8C+8], 3
0x180080a09  jmp     short loc_180080A69
0x180080a0b  lea     r9, [rsp+160h+var_110]; int *
0x180080a10  mov     r8d, edi; unsigned int
0x180080a13  lea     rdx, aErrorRetry_0; "ERROR_RETRY"
0x180080a1a  mov     rcx, [r14+30h]; lpString1
0x180080a1e  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x180080a23  mov     ebx, eax
0x180080a25  test    eax, eax
0x180080a27  js      short loc_1800809BD
0x180080a29  cmp     [rsp+160h+var_110], r15d
0x180080a2e  jz      short loc_180080A39
0x180080a30  mov     dword ptr [rbp+60h+var_8C+8], 4
0x180080a37  jmp     short loc_180080A69
0x180080a39  lea     r9, [rsp+160h+var_110]; int *
0x180080a3e  mov     r8d, edi; unsigned int
0x180080a41  lea     rdx, aErrorFail; "ERROR_FAIL"
0x180080a48  mov     rcx, [r14+30h]; lpString1
0x180080a4c  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x180080a51  mov     ebx, eax
0x180080a53  test    eax, eax
0x180080a55  js      loc_1800809BD
0x180080a5b  cmp     [rsp+160h+var_110], r15d
0x180080a60  jz      short loc_180080AB4
0x180080a62  mov     dword ptr [rbp+60h+var_8C+8], 2
0x180080a69  movaps  xmm0, xmmword ptr [rbp+60h+Uuid1.Data1]
0x180080a6d  movaps  xmm1, xmmword ptr [rbp-30h]
0x180080a71  movaps  [rbp+60h+var_E0], xmm0
0x180080a75  movaps  [rbp+60h+var_D0], xmm1
0x180080a79  movaps  xmm0, [rbp+60h+var_8C+0Ch]
0x180080a7d  movaps  xmm1, xmmword ptr [rbp+60h+var_7C+0Ch]
0x180080a81  movaps  [rbp+60h+var_C0], xmm0
0x180080a85  movaps  [rbp+60h+var_B0], xmm1
0x180080a89  lea     rdx, [rbp+60h+var_E0]
0x180080a8d  mov     rcx, [rsi]
0x180080a90  call    ?Save@NgcStatusStorage@@QEAAJUSTRUCT_NGC_REG_KEY@@@Z; NgcStatusStorage::Save(STRUCT_NGC_REG_KEY)
0x180080a95  test    eax, eax
0x180080a97  mov     ebx, eax
0x180080a99  jns     short loc_180080AB4
0x180080a9b  lea     r8, aNgcregstorageS; "NgcRegStorage::Save"
0x180080aa2  mov     r9d, eax
0x180080aa5  mov     rdx, r12
0x180080aa8  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180080aaf  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080ab4  cmp     [rbp+60h+var_4C], r15b
0x180080ab8  jz      short loc_180080AC9
0x180080aba  lea     rdx, [rbp+60h+ActivityId]; ActivityId
0x180080abe  mov     ecx, 4; ControlCode
0x180080ac3  call    cs:__imp_EventActivityIdControl
0x180080ac9  mov     [rbp+60h+var_50], 2
0x180080ad0  mov     eax, cs:dword_18013D150
0x180080ad6  cmp     eax, 5
0x180080ad9  jbe     loc_180080B77
0x180080adf  mov     rdx, 400000000000h
0x180080ae9  lea     rcx, dword_18013D150
0x180080af0  call    _tlgKeywordOn
0x180080af5  test    al, al
0x180080af7  jz      short loc_180080B77
0x180080af9  mov     rax, [r14+20h]
0x180080afd  mov     [rsp+160h+var_F8], rax
0x180080b02  mov     [rsp+160h+var_110], ebx
0x180080b06  mov     eax, dword ptr [rbp+60h+var_8C+8]
0x180080b09  mov     [rsp+160h+var_108], eax
0x180080b0d  mov     eax, dword ptr [rbp+60h+var_8C+4]
0x180080b10  mov     [rsp+160h+var_104], eax
0x180080b14  mov     eax, dword ptr [rbp+60h+var_8C+0Ch]
0x180080b17  mov     dword ptr [rsp+160h+var_100], eax
0x180080b1b  mov     [rsp+160h+var_F0], 1000800h
0x180080b24  lea     rax, [rsp+160h+var_F8]
0x180080b29  mov     [rsp+160h+var_118], rax
0x180080b2e  lea     rax, [rsp+160h+var_110]
0x180080b33  mov     [rsp+160h+var_120], rax
0x180080b38  lea     rax, [rsp+160h+var_108]
0x180080b3d  mov     [rsp+160h+var_128], rax
0x180080b42  lea     rax, [rsp+160h+var_104]
0x180080b47  mov     [rsp+160h+var_130], rax
0x180080b4c  lea     rax, [rsp+160h+var_100]
0x180080b51  mov     [rsp+160h+var_138], rax
0x180080b56  lea     rax, [rsp+160h+var_F0]
0x180080b5b  mov     [rsp+160h+var_140], rax
0x180080b60  lea     r8, [rbp+60h+var_48]
0x180080b64  lea     rdx, word_18012AA5E
0x180080b6b  lea     rcx, dword_18013D150
  ... truncated ...
```
