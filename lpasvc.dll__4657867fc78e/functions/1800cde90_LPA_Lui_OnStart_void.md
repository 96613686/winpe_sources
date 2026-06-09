# LPA::Lui::OnStart(void)

- ea: `0x1800cde90`
- end: `0x1800ce043`
- name: `?OnStart@Lui@LPA@@UEAAJXZ`
- size: `435`
- prototype: `__int64 __fastcall(LPA::Lui *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18006ba8c`
- `0x18006d8d0`
- `0x1800709e4`
- `0x180070a1c`
- `0x180071a34`
- `0x180071ac8`
- `0x180071b24`
- `0x180081640`
- `0x1800c4968`
- `0x1800cde90`
- `0x1800eb020`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cdf46`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cdf46`

## string_xrefs

- `0x1800cdec0`: `LpaServiceLui`
- `0x1800ce019`: `LpaServiceLui`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LPA::Lui::OnStart(LPA::Lui *this)
{
  char *v2; // r15
  int LastErrorToHResultAndForceFailure; // esi
  __int64 *v4; // rax
  volatile signed __int32 *v5; // rcx
  __int64 v6; // rax
  HANDLE EventW; // rax
  void *v8; // rdx
  CommonUtil *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdi
  void (__fastcall *v12)(__int64, __int64); // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdi
  void (__fastcall *v16)(__int64, __int64); // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  std::_Ref_count_base *v20[2]; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v21[8]; // [rsp+30h] [rbp-10h] BYREF
  std::_Ref_count_base *v22; // [rsp+38h] [rbp-8h]

  v2 = (char *)this + 56;
  if ( *((_DWORD *)this + 14) )
  {
    return (unsigned int)-2147019873;
  }
  else
  {
    LPA::Util::SetRunningState((char *)this + 56, 1, "LpaServiceLui");
    v4 = (__int64 *)std::enable_shared_from_this<LPA::ApduHelper::UiccOperation>::shared_from_this(
                      (char *)this + 40,
                      v21);
    *(_OWORD *)v20 = 0;
    v5 = (volatile signed __int32 *)v4[1];
    if ( v5 )
    {
      v6 = *v4;
      if ( v6 )
        v20[0] = (std::_Ref_count_base *)(v6 + 8);
      v20[1] = (std::_Ref_count_base *)v5;
      _InterlockedIncrement(v5 + 3);
    }
    std::shared_ptr<LPA::EnterpriseManager>::swap(v20, (char *)this + 80);
    if ( v20[1] )
      std::_Ref_count_base::_Decwref(v20[1]);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    EventW = CreateEventW(0, 1, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 96,
      EventW);
    if ( ((*((_QWORD *)this + 12) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0
      || (LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v9),
          LastErrorToHResultAndForceFailure >= 0) )
    {
      LastErrorToHResultAndForceFailure = LuiApiServer::LuiApiServerStart((LPA::Lui *)((char *)this + 64), v8);
      v11 = *((_QWORD *)this + 17);
      v12 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 104LL);
      v13 = std::enable_shared_from_this<LPA::ApduHelper::UiccOperation>::shared_from_this((char *)this + 40, v20);
      v14 = std::weak_ptr<LPA::EnterpriseManagerNotificationHandler>::weak_ptr<LPA::EnterpriseManagerNotificationHandler>(
              v21,
              v13);
      v12(v11, v14);
      if ( v20[1] )
        std::_Ref_count_base::_Decref(v20[1]);
      v15 = *((_QWORD *)this + 15);
      v16 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 184LL);
      v17 = std::enable_shared_from_this<LPA::ApduHelper::UiccOperation>::shared_from_this((char *)this + 40, v20);
      v18 = std::weak_ptr<LPA::EnterpriseManagerNotificationHandler>::weak_ptr<LPA::EnterpriseManagerNotificationHandler>(
              v21,
              v17);
      v16(v15, v18);
      if ( v20[1] )
        std::_Ref_count_base::_Decref(v20[1]);
      v10 = 2;
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 96,
        0);
      v10 = 0;
    }
    LPA::Util::SetRunningState(v2, v10, "LpaServiceLui");
  }
  return (unsigned int)LastErrorToHResultAndForceFailure;
}

```

## disassembly

```asm
0x1800cde90  mov     [rsp-28h+arg_8], rbx
0x1800cde95  mov     [rsp-28h+arg_10], rsi
0x1800cde9a  push    rbp
0x1800cde9b  push    rdi
0x1800cde9c  push    r12
0x1800cde9e  push    r14
0x1800cdea0  push    r15
0x1800cdea2  mov     rbp, rsp
0x1800cdea5  sub     rsp, 40h
0x1800cdea9  mov     r14, rcx
0x1800cdeac  lea     r15, [rcx+38h]
0x1800cdeb0  cmp     dword ptr [r15], 0
0x1800cdeb4  jz      short loc_1800CDEC0
0x1800cdeb6  mov     esi, 8007139Fh
0x1800cdebb  jmp     loc_1800CE028
0x1800cdec0  lea     r8, aLpaservicelui; "LpaServiceLui"
0x1800cdec7  mov     edx, 1
0x1800cdecc  mov     rcx, r15
0x1800cdecf  call    ?SetRunningState@Util@LPA@@YAXAEAW4RUNNING_STATE@@W43@PEBD@Z; LPA::Util::SetRunningState(RUNNING_STATE &,RUNNING_STATE,char const *)
0x1800cded4  lea     r12, [r14+28h]
0x1800cded8  lea     rdx, [rbp+var_10]
0x1800cdedc  mov     rcx, r12
0x1800cdedf  call    ?shared_from_this@?$enable_shared_from_this@VUiccOperation@ApduHelper@LPA@@@std@@QEAA?AV?$shared_ptr@VUiccOperation@ApduHelper@LPA@@@2@XZ; std::enable_shared_from_this<LPA::ApduHelper::UiccOperation>::shared_from_this(void)
0x1800cdee4  lea     rdx, [r14+50h]
0x1800cdee8  xorps   xmm0, xmm0
0x1800cdeeb  movdqu  xmmword ptr [rbp+var_20], xmm0
0x1800cdef0  mov     rcx, [rax+8]
0x1800cdef4  test    rcx, rcx
0x1800cdef7  jz      short loc_1800CDF11
0x1800cdef9  mov     rax, [rax]
0x1800cdefc  test    rax, rax
0x1800cdeff  jz      short loc_1800CDF09
0x1800cdf01  add     rax, 8
0x1800cdf05  mov     [rbp+var_20], rax
0x1800cdf09  mov     [rbp+var_20+8], rcx
0x1800cdf0d  lock inc dword ptr [rcx+0Ch]
0x1800cdf11  lea     rcx, [rbp+var_20]
0x1800cdf15  call    ?swap@?$shared_ptr@VEnterpriseManager@LPA@@@std@@QEAAXAEAV12@@Z; std::shared_ptr<LPA::EnterpriseManager>::swap(std::shared_ptr<LPA::EnterpriseManager> &)
0x1800cdf1a  mov     rcx, [rbp+var_20+8]; this
0x1800cdf1e  test    rcx, rcx
0x1800cdf21  jz      short loc_1800CDF28
0x1800cdf23  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800cdf28  mov     rcx, [rbp+var_8]; this
0x1800cdf2c  test    rcx, rcx
0x1800cdf2f  jz      short loc_1800CDF36
0x1800cdf31  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800cdf36  lea     rbx, [r14+60h]
0x1800cdf3a  xor     r9d, r9d; lpName
0x1800cdf3d  xor     r8d, r8d; bInitialState
0x1800cdf40  lea     edx, [r9+1]; bManualReset
0x1800cdf44  xor     ecx, ecx; lpEventAttributes
0x1800cdf46  call    cs:__imp_CreateEventW
0x1800cdf4c  mov     rdx, rax
0x1800cdf4f  mov     rcx, rbx
0x1800cdf52  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800cdf57  mov     rax, [rbx]
0x1800cdf5a  inc     rax
0x1800cdf5d  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800cdf63  jnz     short loc_1800CDF81
0x1800cdf65  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800cdf6a  mov     esi, eax
0x1800cdf6c  test    eax, eax
0x1800cdf6e  jns     short loc_1800CDF81
0x1800cdf70  xor     edx, edx
0x1800cdf72  mov     rcx, rbx
0x1800cdf75  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800cdf7a  xor     edx, edx
0x1800cdf7c  jmp     loc_1800CE019
0x1800cdf81  lea     rcx, [r14+40h]; this
0x1800cdf85  call    ?LuiApiServerStart@LuiApiServer@@YAJPEAX@Z; LuiApiServer::LuiApiServerStart(void *)
0x1800cdf8a  mov     esi, eax
0x1800cdf8c  mov     rdi, [r14+88h]
0x1800cdf93  mov     rax, [rdi]
0x1800cdf96  mov     rbx, [rax+68h]
0x1800cdf9a  lea     rdx, [rbp+var_20]
0x1800cdf9e  mov     rcx, r12
0x1800cdfa1  call    ?shared_from_this@?$enable_shared_from_this@VUiccOperation@ApduHelper@LPA@@@std@@QEAA?AV?$shared_ptr@VUiccOperation@ApduHelper@LPA@@@2@XZ; std::enable_shared_from_this<LPA::ApduHelper::UiccOperation>::shared_from_this(void)
0x1800cdfa6  nop
0x1800cdfa7  mov     rdx, rax
0x1800cdfaa  lea     rcx, [rbp+var_10]
0x1800cdfae  call    ??$?0VLui@LPA@@$0A@@?$weak_ptr@UEnterpriseManagerNotificationHandler@LPA@@@std@@QEAA@AEBV?$shared_ptr@VLui@LPA@@@1@@Z; std::weak_ptr<LPA::EnterpriseManagerNotificationHandler>::weak_ptr<LPA::EnterpriseManagerNotificationHandler>(std::shared_ptr<LPA::Lui> const &)
0x1800cdfb3  mov     rdx, rax
0x1800cdfb6  mov     rcx, rdi
0x1800cdfb9  mov     rax, rbx
0x1800cdfbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cdfc1  nop
0x1800cdfc2  mov     rcx, [rbp+var_20+8]; this
0x1800cdfc6  test    rcx, rcx
0x1800cdfc9  jz      short loc_1800CDFD0
0x1800cdfcb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800cdfd0  mov     rdi, [r14+78h]
0x1800cdfd4  mov     rax, [rdi]
0x1800cdfd7  mov     rbx, [rax+0B8h]
0x1800cdfde  lea     rdx, [rbp+var_20]
0x1800cdfe2  mov     rcx, r12
0x1800cdfe5  call    ?shared_from_this@?$enable_shared_from_this@VUiccOperation@ApduHelper@LPA@@@std@@QEAA?AV?$shared_ptr@VUiccOperation@ApduHelper@LPA@@@2@XZ; std::enable_shared_from_this<LPA::ApduHelper::UiccOperation>::shared_from_this(void)
0x1800cdfea  nop
0x1800cdfeb  mov     rdx, rax
0x1800cdfee  lea     rcx, [rbp+var_10]
0x1800cdff2  call    ??$?0VEsimManager@LPA@@$0A@@?$weak_ptr@UEnterpriseManagerNotificationHandler@LPA@@@std@@QEAA@AEBV?$shared_ptr@VEsimManager@LPA@@@1@@Z; std::weak_ptr<LPA::EnterpriseManagerNotificationHandler>::weak_ptr<LPA::EnterpriseManagerNotificationHandler>(std::shared_ptr<LPA::EsimManager> const &)
0x1800cdff7  mov     rdx, rax
0x1800cdffa  mov     rcx, rdi
0x1800cdffd  mov     rax, rbx
0x1800ce000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce005  nop
0x1800ce006  mov     rcx, [rbp+var_20+8]; this
0x1800ce00a  test    rcx, rcx
0x1800ce00d  jz      short loc_1800CE014
0x1800ce00f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ce014  mov     edx, 2
0x1800ce019  lea     r8, aLpaservicelui; "LpaServiceLui"
0x1800ce020  mov     rcx, r15
0x1800ce023  call    ?SetRunningState@Util@LPA@@YAXAEAW4RUNNING_STATE@@W43@PEBD@Z; LPA::Util::SetRunningState(RUNNING_STATE &,RUNNING_STATE,char const *)
0x1800ce028  mov     eax, esi
0x1800ce02a  lea     r11, [rsp+40h+var_s0]
0x1800ce02f  mov     rbx, [r11+38h]
0x1800ce033  mov     rsi, [r11+40h]
0x1800ce037  mov     rsp, r11
0x1800ce03a  pop     r15
0x1800ce03c  pop     r14
0x1800ce03e  pop     r12
0x1800ce040  pop     rdi
0x1800ce041  pop     rbp
0x1800ce042  retn
```
