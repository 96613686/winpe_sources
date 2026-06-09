# LPA::Lpd::OnStart(void)

- ea: `0x1800b6c60`
- end: `0x1800b6d9c`
- name: `?OnStart@Lpd@LPA@@UEAAJXZ`
- size: `316`
- prototype: `__int64 __fastcall(LPA::Lpd *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18006ba8c`
- `0x18006d8d0`
- `0x1800709e4`
- `0x180071a34`
- `0x180071a8c`
- `0x180079550`
- `0x1800996f4`
- `0x1800b6c60`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b6c8f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b6c8f`

## string_xrefs

- `0x1800b6d1b`: `LpaServiceLpd`
- `0x1800b6d80`: `LpaServiceLpd`
- `0x1800b6ccc`: `disablesmdxextensionchecks`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LPA::Lpd::OnStart(LPA::Lpd *this)
{
  char *v2; // rdi
  int LastErrorToHResultAndForceFailure; // esi
  _QWORD *v4; // rbx
  HANDLE EventW; // rax
  CommonUtil *v6; // rcx
  unsigned int *v7; // r9
  unsigned int *v8; // r9
  __int64 v9; // rdi
  void (__fastcall *v10)(__int64, __int64 *); // rbx
  _QWORD *v11; // rax
  __int64 *v12; // rax
  __int64 v14; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v15[8]; // [rsp+30h] [rbp-38h] BYREF
  std::_Ref_count_base *v16; // [rsp+38h] [rbp-30h]
  int Data; // [rsp+70h] [rbp+8h] BYREF

  v2 = (char *)this + 72;
  if ( *((_DWORD *)this + 18) )
  {
    return (unsigned int)-2147019873;
  }
  else
  {
    v4 = (_QWORD *)((char *)this + 80);
    EventW = CreateEventW(0, 1, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v4,
      EventW);
    if ( (unsigned __int64)(*v4 - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v6);
      if ( LastErrorToHResultAndForceFailure < 0 )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          v4,
          0);
        LPA::Util::SetRunningState(v2, 0, "LpaServiceLpd");
        return (unsigned int)LastErrorToHResultAndForceFailure;
      }
    }
    else
    {
      LastErrorToHResultAndForceFailure = 0;
    }
    Data = 0;
    if ( (int)CommonUtil::GetDwordFromRegistry(
                L"Software\\Microsoft\\Wlpasvc",
                L"disablesmdxextensionchecks",
                (LPBYTE)&Data,
                v7) >= 0 )
      *((_BYTE *)this + 137) = Data == 0;
    if ( (int)CommonUtil::GetDwordFromRegistry(
                L"Software\\Microsoft\\Wlpasvc",
                L"allowanytrustedroot",
                (LPBYTE)&Data,
                v8) >= 0 )
      *((_BYTE *)this + 136) = Data != 0;
    LPA::Util::SetRunningState(v2, 2, "LpaServiceLpd");
    v9 = *((_QWORD *)this + 7);
    v10 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v9 + 24LL);
    v11 = (_QWORD *)std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this((char *)this + 24, v15);
    v12 = std::weak_ptr<LPA::EsimManagerCompletionHandler>::weak_ptr<LPA::EsimManagerCompletionHandler>(&v14, v11);
    v10(v9, v12);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
  }
  return (unsigned int)LastErrorToHResultAndForceFailure;
}

```

## disassembly

```asm
0x1800b6c60  push    rbx
0x1800b6c62  push    rbp
0x1800b6c63  push    rsi
0x1800b6c64  push    rdi
0x1800b6c65  sub     rsp, 48h
0x1800b6c69  mov     rbp, rcx
0x1800b6c6c  lea     rdi, [rcx+48h]
0x1800b6c70  cmp     dword ptr [rdi], 0
0x1800b6c73  jz      short loc_1800B6C7F
0x1800b6c75  mov     esi, 8007139Fh
0x1800b6c7a  jmp     loc_1800B6D91
0x1800b6c7f  lea     rbx, [rcx+50h]
0x1800b6c83  xor     r9d, r9d; lpName
0x1800b6c86  xor     r8d, r8d; bInitialState
0x1800b6c89  lea     edx, [r9+1]; bManualReset
0x1800b6c8d  xor     ecx, ecx; lpEventAttributes
0x1800b6c8f  call    cs:__imp_CreateEventW
0x1800b6c95  mov     rdx, rax
0x1800b6c98  mov     rcx, rbx
0x1800b6c9b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b6ca0  mov     rax, [rbx]
0x1800b6ca3  dec     rax
0x1800b6ca6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800b6caa  ja      short loc_1800B6CB0
0x1800b6cac  xor     esi, esi
0x1800b6cae  jmp     short loc_1800B6CBF
0x1800b6cb0  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800b6cb5  mov     esi, eax
0x1800b6cb7  test    eax, eax
0x1800b6cb9  js      loc_1800B6D76
0x1800b6cbf  mov     [rsp+68h+Data], 0
0x1800b6cc7  lea     r8, [rsp+68h+Data]; lpData
0x1800b6ccc  lea     rdx, aDisablesmdxext; "disablesmdxextensionchecks"
0x1800b6cd3  lea     rcx, SubKey; "Software\\Microsoft\\Wlpasvc"
0x1800b6cda  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x1800b6cdf  test    eax, eax
0x1800b6ce1  js      short loc_1800B6CF1
0x1800b6ce3  cmp     [rsp+68h+Data], 0
0x1800b6ce8  setz    al
0x1800b6ceb  mov     [rbp+89h], al
0x1800b6cf1  lea     r8, [rsp+68h+Data]; lpData
0x1800b6cf6  lea     rdx, aAllowanytruste; "allowanytrustedroot"
0x1800b6cfd  lea     rcx, SubKey; "Software\\Microsoft\\Wlpasvc"
0x1800b6d04  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x1800b6d09  test    eax, eax
0x1800b6d0b  js      short loc_1800B6D1B
0x1800b6d0d  cmp     [rsp+68h+Data], 0
0x1800b6d12  setnz   al
0x1800b6d15  mov     [rbp+88h], al
0x1800b6d1b  lea     r8, aLpaservicelpd; "LpaServiceLpd"
0x1800b6d22  mov     edx, 2
0x1800b6d27  mov     rcx, rdi
0x1800b6d2a  call    ?SetRunningState@Util@LPA@@YAXAEAW4RUNNING_STATE@@W43@PEBD@Z; LPA::Util::SetRunningState(RUNNING_STATE &,RUNNING_STATE,char const *)
0x1800b6d2f  mov     rdi, [rbp+38h]
0x1800b6d33  mov     rax, [rdi]
0x1800b6d36  mov     rbx, [rax+18h]
0x1800b6d3a  lea     rcx, [rbp+18h]
0x1800b6d3e  lea     rdx, [rsp+68h+var_38]
0x1800b6d43  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x1800b6d48  nop
0x1800b6d49  mov     rdx, rax
0x1800b6d4c  lea     rcx, [rsp+68h+var_48]
0x1800b6d51  call    ??$?0VLui@LPA@@$0A@@?$weak_ptr@UEsimManagerCompletionHandler@LPA@@@std@@QEAA@AEBV?$shared_ptr@VLui@LPA@@@1@@Z; std::weak_ptr<LPA::EsimManagerCompletionHandler>::weak_ptr<LPA::EsimManagerCompletionHandler>(std::shared_ptr<LPA::Lui> const &)
0x1800b6d56  mov     rdx, rax
0x1800b6d59  mov     rcx, rdi
0x1800b6d5c  mov     rax, rbx
0x1800b6d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6d64  nop
0x1800b6d65  mov     rcx, [rsp+68h+var_30]; this
0x1800b6d6a  test    rcx, rcx
0x1800b6d6d  jz      short loc_1800B6D91
0x1800b6d6f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b6d74  jmp     short loc_1800B6D91
0x1800b6d76  xor     edx, edx
0x1800b6d78  mov     rcx, rbx
0x1800b6d7b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b6d80  lea     r8, aLpaservicelpd; "LpaServiceLpd"
0x1800b6d87  xor     edx, edx
0x1800b6d89  mov     rcx, rdi
0x1800b6d8c  call    ?SetRunningState@Util@LPA@@YAXAEAW4RUNNING_STATE@@W43@PEBD@Z; LPA::Util::SetRunningState(RUNNING_STATE &,RUNNING_STATE,char const *)
0x1800b6d91  mov     eax, esi
0x1800b6d93  add     rsp, 48h
0x1800b6d97  pop     rdi
0x1800b6d98  pop     rsi
0x1800b6d99  pop     rbp
0x1800b6d9a  pop     rbx
0x1800b6d9b  retn
```
