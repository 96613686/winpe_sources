# cdp::ActivityAssetUploadJob::TryMoveJobToNextStep(void)

- ea: `0x1802fac50`
- end: `0x1802fae81`
- name: `?TryMoveJobToNextStep@ActivityAssetUploadJob@cdp@@UEAAXXZ`
- size: `561`
- prototype: `void __fastcall(cdp::ActivityAssetUploadJob *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800110f8`
- `0x180013d6c`
- `0x180013da0`
- `0x18001ee70`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800f7944`
- `0x180143248`
- `0x1801fcb36`
- `0x1802b97ac`
- `0x1802fac50`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802facc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802fad68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802facc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802fad68`
- `msvcp_win!_Mtx_unlock` at `0x1802fae7a`

## string_xrefs

- `0x1802fae49`: `{"text":"ActivityAssetUploadJob::TryMoveJobToNextStep didn't move to next step, current step is %s"}`
- `0x1802fae40`: `{"text":"ActivityAssetUploadJob::TryMoveJobToNextStep moved to next step:%s"}`
- `0x1802fad8e`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu","text":"ActivityAssetUploadJob has not been set with any result yet"}`
- `0x1802face8`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu","text":"ActivityAssetUploadJob already completed"}`
- `0x1802fac8e`: `{"text":"ActivityAssetUploadJob try to move to  next step, current step is %s"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall cdp::ActivityAssetUploadJob::TryMoveJobToNextStep(cdp::ActivityAssetUploadJob *this)
{
  struct _Mtx_internal_imp_t *v2; // rsi
  _BYTE *v3; // rdi
  __int64 v4; // rcx
  int v5; // ecx
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  int v10; // ecx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rcx
  char v16; // bl
  const char *v17; // rdx
  const char *v18; // [rsp+30h] [rbp-29h] BYREF
  __int64 v19; // [rsp+38h] [rbp-21h] BYREF
  std::_Ref_count_base *v20; // [rsp+40h] [rbp-19h]
  _BYTE v21[24]; // [rsp+48h] [rbp-11h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+60h] [rbp+7h] BYREF
  __int64 v23; // [rsp+C0h] [rbp+67h] BYREF
  __int64 CurrentThreadId; // [rsp+C8h] [rbp+6Fh] BYREF
  char *v25; // [rsp+D0h] [rbp+77h]

  v2 = (cdp::ActivityAssetUploadJob *)((char *)this + 112);
  v25 = (char *)this + 112;
  std::_Mutex_base::lock((cdp::ActivityAssetUploadJob *)((char *)this + 112));
  v3 = (char *)this + 192;
  LOBYTE(v4) = *((_BYTE *)this + 192);
  v23 = EnumMapper::ToString(v4);
  Log<unsigned __int64 &>(
    3,
    "{\"text\":\"ActivityAssetUploadJob try to move to  next step, current step is %s\"}",
    (const char *)&v23);
  if ( *((_BYTE *)this + 192) == 2 )
  {
    v18 = "..\\activityassetuploadjob.cpp";
    LODWORD(v19) = 139;
    LODWORD(v23) = -2147020579;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v5,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"ActivityAssetUploadJob "
                    "already completed\"}",
      (unsigned int)&v23,
      (unsigned int)&v18,
      (__int64)&v19,
      (__int64)&CurrentThreadId);
    v6 = cdp::ExceptionStackFromSourceLocationInfo(v21, &v18);
    v9 = cdp::ErrorCodeToString(2147946717LL, v7, v8, v6);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147946717LL, v9);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  std::_Tree<std::_Tmap_traits<enum cdp::ActivityAssetDownloadJobStep,cdp::ActivityJobStepResult,std::less<enum cdp::ActivityAssetDownloadJobStep>,std::allocator<std::pair<enum cdp::ActivityAssetDownloadJobStep const,cdp::ActivityJobStepResult>>,0>>::find(
    (char *)this + 200,
    &v23,
    (char *)this + 192);
  if ( v23 == *((_QWORD *)this + 25) )
  {
    v18 = "..\\activityassetuploadjob.cpp";
    LODWORD(v19) = 142;
    LODWORD(v23) = -2147020579;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v10,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"ActivityAssetUploadJob "
                    "has not been set with any result yet\"}",
      (unsigned int)&v23,
      (unsigned int)&v18,
      (__int64)&v19,
      (__int64)&CurrentThreadId);
    v11 = cdp::ExceptionStackFromSourceLocationInfo(v21, &v18);
    v14 = cdp::ErrorCodeToString(2147946717LL, v12, v13, v11);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147946717LL, v14);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  LODWORD(v18) = *(_DWORD *)(v23 + 40);
  std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
    &v19,
    v23 + 48);
  v16 = 0;
  if ( !*v3 )
  {
    if ( (int)v18 < 0 )
    {
      if ( (_DWORD)v18 != -2147220726 )
        goto LABEL_15;
      *v3 = 1;
      goto LABEL_14;
    }
LABEL_13:
    *v3 = 2;
LABEL_14:
    v16 = 1;
    goto LABEL_15;
  }
  if ( *v3 == 1 )
  {
    if ( (int)v18 >= 0 )
      goto LABEL_13;
    v15 = v19;
    if ( v19 )
    {
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19) == 302 )
        goto LABEL_13;
    }
  }
LABEL_15:
  LOBYTE(v15) = *v3;
  v23 = EnumMapper::ToString(v15);
  v17 = "{\"text\":\"ActivityAssetUploadJob::TryMoveJobToNextStep moved to next step:%s\"}";
  if ( !v16 )
    v17 = "{\"text\":\"ActivityAssetUploadJob::TryMoveJobToNextStep didn't move to next step, current step is %s\"}";
  Log<unsigned __int64 &>(3, v17, &v23);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  _Mtx_unlock(v2);
}

```

## disassembly

```asm
0x1802fac50  mov     [rsp-8+arg_18], rbx
0x1802fac55  push    rbp
0x1802fac56  push    rsi
0x1802fac57  push    rdi
0x1802fac58  lea     rbp, [rsp-47h]
0x1802fac5d  sub     rsp, 0A0h
0x1802fac64  mov     rbx, rcx
0x1802fac67  lea     rsi, [rcx+70h]
0x1802fac6b  mov     [rbp+57h+arg_10], rsi
0x1802fac6f  mov     rcx, rsi; this
0x1802fac72  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1802fac77  nop
0x1802fac78  lea     rdi, [rbx+0C0h]
0x1802fac7f  mov     cl, [rdi]
0x1802fac81  call    ?ToString@EnumMapper@@YAPEBDW4ActivityAssetUploadJobStep@cdp@@@Z; EnumMapper::ToString(cdp::ActivityAssetUploadJobStep)
0x1802fac86  mov     [rbp+57h+arg_0], rax
0x1802fac8a  lea     r8, [rbp+57h+arg_0]
0x1802fac8e  lea     rdx, aTextActivityas_35; "{\"text\":\"ActivityAssetUploadJob try "...
0x1802fac95  mov     ecx, 3
0x1802fac9a  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x1802fac9f  cmp     byte ptr [rdi], 2
0x1802faca2  jnz     loc_1802FAD2A
0x1802faca8  lea     rax, aActivityassetu_0; "..\\activityassetuploadjob.cpp"
0x1802facaf  mov     [rbp+57h+var_80], rax
0x1802facb3  mov     dword ptr [rbp+57h+var_78], 8Bh
0x1802facba  mov     ebx, 800710DDh
0x1802facbf  mov     dword ptr [rbp+57h+arg_0], ebx
0x1802facc2  call    cs:__imp_GetCurrentThreadId
0x1802facc8  mov     eax, eax
0x1802facca  mov     [rbp+57h+arg_8], rax
0x1802facce  lea     rax, [rbp+57h+arg_8]
0x1802facd2  mov     [rsp+0B0h+var_88], rax
0x1802facd7  lea     rax, [rbp+57h+var_78]
0x1802facdb  mov     [rsp+0B0h+var_90], rax
0x1802face0  lea     r9, [rbp+57h+var_80]
0x1802face4  lea     r8, [rbp+57h+arg_0]
0x1802face8  lea     rdx, aHr0x08xFileSLi_56; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1802facef  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1802facf4  lea     rdx, [rbp+57h+var_80]
0x1802facf8  lea     rcx, [rbp+57h+var_68]
0x1802facfc  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1802fad01  mov     r9, rax
0x1802fad04  mov     ecx, ebx
0x1802fad06  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1802fad0b  mov     r8, rax
0x1802fad0e  mov     edx, ebx
0x1802fad10  lea     rcx, [rbp+57h+pExceptionObject]
0x1802fad14  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1802fad19  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1802fad20  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1802fad24  call    _CxxThrowException_0
0x1802fad2a  mov     r8, rdi
0x1802fad2d  lea     rdx, [rbp+57h+arg_0]
0x1802fad31  lea     rcx, [rbx+0C8h]
0x1802fad38  call    ?find@?$_Tree@V?$_Tmap_traits@W4ActivityAssetDownloadJobStep@cdp@@UActivityJobStepResult@2@U?$less@W4ActivityAssetDownloadJobStep@cdp@@@std@@V?$allocator@U?$pair@$$CBW4ActivityAssetDownloadJobStep@cdp@@UActivityJobStepResult@2@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ActivityAssetDownloadJobStep@cdp@@UActivityJobStepResult@2@@std@@@std@@@std@@@2@AEBW4ActivityAssetDownloadJobStep@cdp@@@Z; std::_Tree<std::_Tmap_traits<cdp::ActivityAssetDownloadJobStep,cdp::ActivityJobStepResult,std::less<cdp::ActivityAssetDownloadJobStep>,std::allocator<std::pair<cdp::ActivityAssetDownloadJobStep const,cdp::ActivityJobStepResult>>,0>>::find(cdp::ActivityAssetDownloadJobStep const &)
0x1802fad3d  mov     rdx, [rbp+57h+arg_0]
0x1802fad41  cmp     rdx, [rbx+0C8h]
0x1802fad48  jnz     loc_1802FADD0
0x1802fad4e  lea     rax, aActivityassetu_0; "..\\activityassetuploadjob.cpp"
0x1802fad55  mov     [rbp+57h+var_80], rax
0x1802fad59  mov     dword ptr [rbp+57h+var_78], 8Eh
0x1802fad60  mov     ebx, 800710DDh
0x1802fad65  mov     dword ptr [rbp+57h+arg_0], ebx
0x1802fad68  call    cs:__imp_GetCurrentThreadId
0x1802fad6e  mov     eax, eax
0x1802fad70  mov     [rbp+57h+arg_8], rax
0x1802fad74  lea     rax, [rbp+57h+arg_8]
0x1802fad78  mov     [rsp+0B0h+var_88], rax
0x1802fad7d  lea     rax, [rbp+57h+var_78]
0x1802fad81  mov     [rsp+0B0h+var_90], rax
0x1802fad86  lea     r9, [rbp+57h+var_80]
0x1802fad8a  lea     r8, [rbp+57h+arg_0]
0x1802fad8e  lea     rdx, aHr0x08xFileSLi_21; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1802fad95  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1802fad9a  lea     rdx, [rbp+57h+var_80]
0x1802fad9e  lea     rcx, [rbp+57h+var_68]
0x1802fada2  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1802fada7  mov     r9, rax
0x1802fadaa  mov     ecx, ebx
0x1802fadac  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1802fadb1  mov     r8, rax
0x1802fadb4  mov     edx, ebx
0x1802fadb6  lea     rcx, [rbp+57h+pExceptionObject]
0x1802fadba  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1802fadbf  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1802fadc6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1802fadca  call    _CxxThrowException_0
0x1802fadd0  mov     eax, [rdx+28h]
0x1802fadd3  mov     dword ptr [rbp+57h+var_80], eax
0x1802fadd6  add     rdx, 30h ; '0'
0x1802fadda  lea     rcx, [rbp+57h+var_78]
0x1802fadde  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x1802fade3  nop
0x1802fade4  xor     bl, bl
0x1802fade6  mov     al, [rdi]
0x1802fade8  test    al, al
0x1802fadea  jnz     short loc_1802FADFF
0x1802fadec  mov     eax, dword ptr [rbp+57h+var_80]
0x1802fadef  test    eax, eax
0x1802fadf1  jns     short loc_1802FAE25
0x1802fadf3  cmp     eax, 8004030Ah
0x1802fadf8  jnz     short loc_1802FAE2A
0x1802fadfa  mov     byte ptr [rdi], 1
0x1802fadfd  jmp     short loc_1802FAE28
0x1802fadff  cmp     al, 1
0x1802fae01  jnz     short loc_1802FAE2A
0x1802fae03  cmp     dword ptr [rbp+57h+var_80], 0
0x1802fae07  jge     short loc_1802FAE25
0x1802fae09  mov     rcx, [rbp+57h+var_78]
0x1802fae0d  test    rcx, rcx
0x1802fae10  jz      short loc_1802FAE2A
0x1802fae12  mov     rax, [rcx]
0x1802fae15  mov     rax, [rax+10h]
0x1802fae19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802fae1e  cmp     eax, 12Eh
0x1802fae23  jnz     short loc_1802FAE2A
0x1802fae25  mov     byte ptr [rdi], 2
0x1802fae28  mov     bl, 1
0x1802fae2a  mov     cl, [rdi]
0x1802fae2c  call    ?ToString@EnumMapper@@YAPEBDW4ActivityAssetUploadJobStep@cdp@@@Z; EnumMapper::ToString(cdp::ActivityAssetUploadJobStep)
0x1802fae31  mov     [rbp+57h+arg_0], rax
0x1802fae35  lea     r8, [rbp+57h+arg_0]
0x1802fae39  mov     ecx, 3
0x1802fae3e  test    bl, bl
0x1802fae40  lea     rdx, aTextActivityas_2; "{\"text\":\"ActivityAssetUploadJob::Try"...
0x1802fae47  jnz     short loc_1802FAE50
0x1802fae49  lea     rdx, aTextActivityas_27; "{\"text\":\"ActivityAssetUploadJob::Try"...
0x1802fae50  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x1802fae55  nop
0x1802fae56  mov     rcx, [rbp+57h+var_70]; this
0x1802fae5a  test    rcx, rcx
0x1802fae5d  jz      short loc_1802FAE65
0x1802fae5f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1802fae64  nop
0x1802fae65  mov     rcx, rsi
0x1802fae68  mov     rbx, [rsp+0B0h+arg_18]
0x1802fae70  add     rsp, 0A0h
0x1802fae77  pop     rdi
0x1802fae78  pop     rsi
0x1802fae79  pop     rbp
0x1802fae7a  jmp     cs:__imp__Mtx_unlock
```
