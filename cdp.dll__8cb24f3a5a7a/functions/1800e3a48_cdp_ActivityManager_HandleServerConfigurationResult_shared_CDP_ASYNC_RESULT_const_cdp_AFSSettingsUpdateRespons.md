# cdp::ActivityManager::HandleServerConfigurationResult(shared::CDP_ASYNC_RESULT const &,cdp::AFSSettingsUpdateResponse &&)

- ea: `0x1800e3a48`
- end: `0x1800e3bbf`
- name: `?HandleServerConfigurationResult@ActivityManager@cdp@@AEAAXAEBUCDP_ASYNC_RESULT@shared@@$$QEAUAFSSettingsUpdateResponse@2@@Z`
- size: `375`
- prototype: `__int64 __fastcall(cdp::ActivityManager *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1802f3710`

## callees

- `0x1800110f8`
- `0x18004a444`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800e3a48`
- `0x1800e3bc8`
- `0x1800fdedc`
- `0x180143248`
- `0x180145cb8`
- `0x1801990e4`
- `0x1801fcb36`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e3ae8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e3ae8`
- `msvcp_win!_Xtime_get_ticks` at `0x1800e3b80`
- `msvcp_win!_Xtime_get_ticks` at `0x1800e3b80`
- `msvcp_win!_Mtx_unlock` at `0x1800e3b90`
- `msvcp_win!_Mtx_unlock` at `0x1800e3b90`

## string_xrefs

- `0x1800e3b16`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800e3aac`: `{"text":"Incrementing _pendingRefreshServerConfigurationCount, as AFS requested retry. Now %hhu, was %hhu."}`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall cdp::ActivityManager::HandleServerConfigurationResult(
        cdp::ActivityManager *this,
        __int64 a2,
        __int64 a3)
{
  int v5; // esi
  int v6; // ecx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  struct _Mtx_internal_imp_t *v11; // rsi
  __int64 v13; // rax
  _BYTE v14[32]; // [rsp+0h] [rbp-C8h] BYREF
  __int64 CurrentThreadId; // [rsp+30h] [rbp-98h] BYREF
  const char *v16; // [rsp+38h] [rbp-90h] BYREF
  int v17; // [rsp+40h] [rbp-88h] BYREF
  cdp::ActivityManager *v18; // [rsp+48h] [rbp-80h] BYREF
  cdp::ActivityManager **v19; // [rsp+50h] [rbp-78h] BYREF
  _BYTE v20[24]; // [rsp+58h] [rbp-70h] BYREF
  _BYTE pExceptionObject[88]; // [rsp+70h] [rbp-58h] BYREF
  char *v22; // [rsp+E0h] [rbp+18h] BYREF
  int v23; // [rsp+E8h] [rbp+20h]

  try
  {
    v23 = 0;
    v18 = this;
    v19 = &v18;
    if ( *(_BYTE *)a3 )
    {
      cdp::ActivityManager::HandleAFSRequestedAction(this, (const struct cdp::AFSRequestedAction *)a3);
      if ( (unsigned __int8)(*(_BYTE *)a3 - 1) <= 2u )
      {
        LODWORD(v22) = (unsigned __int8)++*((_BYTE *)this + 776) - 1;
        Log<unsigned char &,int>(
          4,
          "{\"text\":\"Incrementing _pendingRefreshServerConfigurationCount, as AFS requested retry. Now %hhu, was %hhu.\"}",
          (_DWORD)this + 776,
          (unsigned int)&v22);
      }
    }
    else
    {
      v5 = *(_DWORD *)(a2 + 4);
      if ( v5 < 0 )
      {
        v16 = "..\\activitymanager.cpp";
        v17 = 4108;
        LODWORD(v22) = v5;
        CurrentThreadId = GetCurrentThreadId();
        Log<long &,char const * &,int &,unsigned __int64>(
          v6,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v22,
          (unsigned int)&v16,
          (__int64)&v17,
          (__int64)&CurrentThreadId);
        v7 = cdp::ExceptionStackFromSourceLocationInfo(v20, &v16);
        v10 = cdp::ErrorCodeToString((unsigned int)v5, v8, v9, v7);
        ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v5, v10);
        throw (ConnectedDevices::Exception *)pExceptionObject;
      }
      v11 = (cdp::ActivityManager *)((char *)this + 296);
      v22 = (char *)this + 296;
      std::_Mutex_base::lock((cdp::ActivityManager *)((char *)this + 296));
      cdp::ActivityManager::HandleAFSConfigurationChangeInternal(this, (const struct cdp::AfsSettingDataMap *)(a3 + 64));
      *((_QWORD *)this + 98) = _Xtime_get_ticks();
      _Mtx_unlock(v11);
    }
  }
  catch ( ... )
  {
    LODWORD(v13) = GetCurrentThreadId();
    CurrentThreadId = v13;
    LODWORD(v22) = 4114;
    cdp::CatchAllToHR<char const (&)[29],int,unsigned __int64>(
      (unsigned int)v14 + 232,
      (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\""
                    ":\"Failed during HandleServerConfigurationResult\"}",
      (unsigned int)"..\\activitymanager.cpp",
      (unsigned int)v14 + 224,
      (__int64)&CurrentThreadId);
  }
  cdp::ActivityManager::CompleteAfsRequestCallback(this);
  return ScopeWarden__lambda_369b9fb568ffdab823abaa24afca6257___::_ScopeWarden__lambda_369b9fb568ffdab823abaa24afca6257___(&v19);
}

```

## disassembly

```asm
0x1800e3a48  mov     rax, rsp
0x1800e3a4b  mov     [rax+8], rcx
0x1800e3a4f  push    rbx
0x1800e3a50  push    rsi
0x1800e3a51  push    rdi
0x1800e3a52  sub     rsp, 0B0h
0x1800e3a59  mov     rdi, r8
0x1800e3a5c  mov     rbx, rcx
0x1800e3a5f  mov     dword ptr [rax+20h], 0
0x1800e3a66  mov     [rax-80h], rcx
0x1800e3a6a  lea     rax, [rax-80h]
0x1800e3a6e  mov     [rsp+0C8h+var_78], rax
0x1800e3a73  cmp     byte ptr [r8], 0
0x1800e3a77  jz      short loc_1800E3AC2
0x1800e3a79  mov     rdx, r8; struct cdp::AFSRequestedAction *
0x1800e3a7c  call    ?HandleAFSRequestedAction@ActivityManager@cdp@@AEAAXAEBUAFSRequestedAction@2@@Z; cdp::ActivityManager::HandleAFSRequestedAction(cdp::AFSRequestedAction const &)
0x1800e3a81  mov     al, [rdi]
0x1800e3a83  dec     al
0x1800e3a85  cmp     al, 2
0x1800e3a87  ja      loc_1800E3B97
0x1800e3a8d  lea     r8, [rbx+308h]
0x1800e3a94  inc     byte ptr [r8]
0x1800e3a97  movzx   eax, byte ptr [r8]
0x1800e3a9b  dec     eax
0x1800e3a9d  mov     dword ptr [rsp+0C8h+arg_10], eax
0x1800e3aa4  lea     r9, [rsp+0C8h+arg_10]
0x1800e3aac  lea     rdx, aTextIncrementi_0; "{\"text\":\"Incrementing _pendingRefres"...
0x1800e3ab3  mov     ecx, 4
0x1800e3ab8  call    ??$Log@AEAEH@@YAXW4CDPLogLevel@@PEBDAEAE$$QEAH@Z; Log<uchar &,int>(CDPLogLevel,char const *,uchar &,int &&)
0x1800e3abd  jmp     loc_1800E3B97
0x1800e3ac2  mov     esi, [rdx+4]
0x1800e3ac5  test    esi, esi
0x1800e3ac7  jns     loc_1800E3B5C
0x1800e3acd  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x1800e3ad4  mov     [rsp+0C8h+var_90], rax
0x1800e3ad9  mov     [rsp+0C8h+var_88], 100Ch
0x1800e3ae1  mov     dword ptr [rsp+0C8h+arg_10], esi
0x1800e3ae8  call    cs:__imp_GetCurrentThreadId
0x1800e3aee  mov     eax, eax
0x1800e3af0  mov     [rsp+0C8h+var_98], rax
0x1800e3af5  lea     rax, [rsp+0C8h+var_98]
0x1800e3afa  mov     [rsp+0C8h+var_A0], rax
0x1800e3aff  lea     rax, [rsp+0C8h+var_88]
0x1800e3b04  mov     [rsp+0C8h+var_A8], rax
0x1800e3b09  lea     r9, [rsp+0C8h+var_90]
0x1800e3b0e  lea     r8, [rsp+0C8h+arg_10]
0x1800e3b16  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800e3b1d  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800e3b22  lea     rdx, [rsp+0C8h+var_90]
0x1800e3b27  lea     rcx, [rsp+0C8h+var_70]
0x1800e3b2c  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800e3b31  mov     r9, rax
0x1800e3b34  mov     ecx, esi
0x1800e3b36  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800e3b3b  mov     r8, rax
0x1800e3b3e  mov     edx, esi
0x1800e3b40  lea     rcx, [rsp+0C8h+pExceptionObject]
0x1800e3b45  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800e3b4a  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800e3b51  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x1800e3b56  call    _CxxThrowException_0
0x1800e3b5c  lea     rsi, [rcx+128h]
0x1800e3b63  mov     [rsp+0C8h+arg_10], rsi
0x1800e3b6b  mov     rcx, rsi; this
0x1800e3b6e  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800e3b73  nop
0x1800e3b74  lea     rdx, [rdi+40h]; struct cdp::AfsSettingDataMap *
0x1800e3b78  mov     rcx, rbx; this
0x1800e3b7b  call    ?HandleAFSConfigurationChangeInternal@ActivityManager@cdp@@AEAAXAEBVAfsSettingDataMap@2@@Z; cdp::ActivityManager::HandleAFSConfigurationChangeInternal(cdp::AfsSettingDataMap const &)
0x1800e3b80  call    cs:__imp__Xtime_get_ticks
0x1800e3b86  mov     [rbx+310h], rax
0x1800e3b8d  mov     rcx, rsi; _Mtx_t
0x1800e3b90  call    cs:__imp__Mtx_unlock
0x1800e3b96  nop
0x1800e3b97  jmp     short loc_1800E3BA1
0x1800e3b99  mov     rbx, [rsp+0C8h+arg_0]
0x1800e3ba1  mov     rcx, rbx; this
0x1800e3ba4  call    ?CompleteAfsRequestCallback@ActivityManager@cdp@@AEAAXXZ; cdp::ActivityManager::CompleteAfsRequestCallback(void)
0x1800e3ba9  nop
0x1800e3baa  lea     rcx, [rsp+0C8h+var_78]
0x1800e3baf  call    ScopeWarden__lambda_369b9fb568ffdab823abaa24afca6257______ScopeWarden__lambda_369b9fb568ffdab823abaa24afca6257___
0x1800e3bb4  add     rsp, 0B0h
0x1800e3bbb  pop     rdi
0x1800e3bbc  pop     rsi
0x1800e3bbd  pop     rbx
0x1800e3bbe  retn
```
