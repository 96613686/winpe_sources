# Microsoft::Diagnostics::GetAgentDiagnosticsActionDef::StartAgentActivity(bool)

- ea: `0x180086008`
- end: `0x18008626c`
- name: `?StartAgentActivity@GetAgentDiagnosticsActionDef@Diagnostics@Microsoft@@QEAAX_N@Z`
- size: `612`
- prototype: `void __fastcall(Microsoft::Diagnostics::GetAgentDiagnosticsActionDef *__hidden this, bool)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180085dd8`
- `0x1802812f0`
- `0x1802971ec`

## callees

- `0x180080da4`
- `0x180086008`
- `0x1800be65c`
- `0x1800d11c0`
- `0x1800d13c8`
- `0x18010e55c`
- `0x18010f9b8`
- `0x1801a9494`
- `0x1801e7514`
- `0x18020aac0`
- `0x1802a84f0`

## import_xrefs

- `api-ms-win-containers-cmclient-l1-2-0!CmsStartActivityAsync` at `0x1800861d5`
- `api-ms-win-containers-cmclient-l1-2-0!CmsStartActivityAsync` at `0x1800861d5`
- `api-ms-win-containers-cmclient-l1-2-0!CmsCreateActivity` at `0x1800861a5`
- `api-ms-win-containers-cmclient-l1-2-0!CmsCreateActivity` at `0x1800861a5`
- `api-ms-win-containers-cmclient-l1-2-0!CmsRegisterForContainerNotifications` at `0x18008611f`
- `api-ms-win-containers-cmclient-l1-2-0!CmsRegisterForContainerNotifications` at `0x18008611f`
- `api-ms-win-containers-cmclient-l1-5-0!CmsOpenContainer` at `0x1800860ef`
- `api-ms-win-containers-cmclient-l1-5-0!CmsOpenContainer` at `0x1800860ef`

## string_xrefs

- `0x18008609c`: `onecore\base\telemetry\utc\service\scenarios\actions\getagentdiagnostics.cpp`
- `0x180086100`: `onecore\base\telemetry\utc\service\scenarios\actions\getagentdiagnostics.cpp`
- `0x180086130`: `onecore\base\telemetry\utc\service\scenarios\actions\getagentdiagnostics.cpp`
- `0x1800861b6`: `onecore\base\telemetry\utc\service\scenarios\actions\getagentdiagnostics.cpp`
- `0x1800861e6`: `onecore\base\telemetry\utc\service\scenarios\actions\getagentdiagnostics.cpp`
- `0x180086213`: `onecore\base\telemetry\utc\service\scenarios\actions\getagentdiagnostics.cpp`
- `0x180086235`: `onecore\base\telemetry\utc\service\scenarios\actions\getagentdiagnostics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Diagnostics::GetAgentDiagnosticsActionDef::StartAgentActivity(
        Microsoft::Diagnostics::GetAgentDiagnosticsActionDef *this,
        unsigned __int8 a2)
{
  int v2; // r12d
  char *v4; // rcx
  int v5; // eax
  _QWORD *v6; // rdi
  wilp *v7; // rsi
  void *v8; // rdx
  int v9; // eax
  int v10; // eax
  _QWORD *v11; // rsi
  wilp *v12; // r14
  void *v13; // rdx
  int Activity; // eax
  int started; // eax
  const char *v16; // r9
  int v17; // [rsp+20h] [rbp-40h]
  int v18; // [rsp+20h] [rbp-40h]
  __int128 v19; // [rsp+30h] [rbp-30h] BYREF
  GUID v20; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v2 = a2;
  v19 = *(_OWORD *)&off_18036B588;
  if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(&v19) )
  {
    v20 = GUID_NULL;
    if ( *((_QWORD *)this + 23) <= 7u )
      v4 = (char *)this + 160;
    else
      v4 = (char *)*((_QWORD *)this + 20);
    *(_QWORD *)&v19 = v4;
    *((_QWORD *)&v19 + 1) = *((_QWORD *)this + 22);
    v5 = Microsoft::Diagnostics::Utils::String::GUIDFromString(&v19, &v20, 0);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getagentdiagnostics.cpp",
        (const char *)(unsigned int)v5,
        v17);
    v6 = (_QWORD *)((char *)this + 200);
    v7 = (wilp *)*((_QWORD *)this + 25);
    if ( v7 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v19);
      wilp::CloseCmsContainer(v7, v8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v19);
    }
    *v6 = 0;
    v9 = CmsOpenContainer(&v20, 8, 33, v6);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getagentdiagnostics.cpp",
        (const char *)(unsigned int)v9,
        v17);
    v10 = CmsRegisterForContainerNotifications(
            *v6,
            Microsoft::Diagnostics::GetAgentDiagnosticsActionDef::ContainerNotificationCallback,
            this);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getagentdiagnostics.cpp",
        (const char *)(unsigned int)v10,
        v17);
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      (_DWORD)this + 192,
      0,
      0,
      0,
      0);
    v11 = (_QWORD *)((char *)this + 208);
    v12 = (wilp *)*((_QWORD *)this + 26);
    if ( v12 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v19);
      wilp::CloseCmsActivity(v12, v13);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v19);
    }
    *v11 = 0;
    Activity = CmsCreateActivity(*v6, (v2 ^ 1u) + 8001, (char *)this + 208);
    if ( Activity < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getagentdiagnostics.cpp",
        (const char *)(unsigned int)Activity,
        v18);
    started = CmsStartActivityAsync(
                *v11,
                Microsoft::Diagnostics::GetAgentDiagnosticsActionDef::ContainerActivityNotificationCallback,
                this);
    if ( started < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getagentdiagnostics.cpp",
        (const char *)(unsigned int)started,
        v18);
    if ( !Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(*((void **)this + 24), 0x2710u) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getagentdiagnostics.cpp",
        (const char *)0x800705B4LL,
        v18);
    v16 = (const char *)*((unsigned int *)this + 54);
    if ( (int)v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getagentdiagnostics.cpp",
        v16,
        v18);
  }
}

```

## disassembly

```asm
0x180086008  mov     [rsp-28h+arg_8], rbx
0x18008600d  mov     [rsp-28h+arg_10], rsi
0x180086012  push    rbp
0x180086013  push    rdi
0x180086014  push    r12
0x180086016  push    r14
0x180086018  push    r15
0x18008601a  mov     rbp, rsp
0x18008601d  sub     rsp, 60h
0x180086021  mov     rax, cs:__security_cookie
0x180086028  xor     rax, rsp
0x18008602b  mov     [rbp+var_10], rax
0x18008602f  movzx   r12d, dl
0x180086033  mov     rbx, rcx
0x180086036  movups  xmm0, xmmword ptr cs:off_18036B588; "AgentSocketTestMode"
0x18008603d  movdqu  [rbp+var_30], xmm0
0x180086042  lea     rcx, [rbp+var_30]
0x180086046  call    ?IsTestHookEnabled@General@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(std::wstring_view)
0x18008604b  test    al, al
0x18008604d  jnz     loc_180086247
0x180086053  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18008605a  movdqu  [rbp+var_20], xmm0
0x18008605f  lea     rax, [rbx+0A0h]
0x180086066  cmp     qword ptr [rax+18h], 7
0x18008606b  jbe     short loc_180086072
0x18008606d  mov     rcx, [rax]
0x180086070  jmp     short loc_180086075
0x180086072  mov     rcx, rax
0x180086075  mov     qword ptr [rbp+var_30], rcx
0x180086079  mov     rax, [rax+10h]
0x18008607d  mov     qword ptr [rbp+var_30+8], rax
0x180086081  xor     r8d, r8d
0x180086084  lea     rdx, [rbp+var_20]
0x180086088  lea     rcx, [rbp+var_30]
0x18008608c  call    ?GUIDFromString@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAU_GUID@@_N@Z; Microsoft::Diagnostics::Utils::String::GUIDFromString(std::wstring_view,_GUID &,bool)
0x180086091  mov     rcx, [rbp+28h]; this
0x180086095  test    eax, eax
0x180086097  jns     short loc_1800860AE
0x180086099  mov     r9d, eax; char *
0x18008609c  lea     r8, aOnecoreBaseTel_117; "onecore\\base\\telemetry\\utc\\service"...
0x1800860a3  mov     edx, 59h ; 'Y'; void *
0x1800860a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800860ae  lea     rdi, [rbx+0C8h]
0x1800860b5  mov     rsi, [rdi]
0x1800860b8  test    rsi, rsi
0x1800860bb  jz      short loc_1800860D8
0x1800860bd  lea     rcx, [rbp+var_30]; this
0x1800860c1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800860c6  mov     rcx, rsi; this
0x1800860c9  call    ?CloseCmsContainer@wilp@@YAXPEAX@Z; wilp::CloseCmsContainer(void *)
0x1800860ce  lea     rcx, [rbp+var_30]; this
0x1800860d2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800860d7  nop
0x1800860d8  mov     qword ptr [rdi], 0
0x1800860df  mov     r9, rdi
0x1800860e2  mov     edx, 8
0x1800860e7  lea     r8d, [rdx+19h]
0x1800860eb  lea     rcx, [rbp+var_20]
0x1800860ef  call    cs:__imp_CmsOpenContainer
0x1800860f5  mov     rcx, [rbp+28h]; this
0x1800860f9  test    eax, eax
0x1800860fb  jns     short loc_180086112
0x1800860fd  mov     r9d, eax; char *
0x180086100  lea     r8, aOnecoreBaseTel_117; "onecore\\base\\telemetry\\utc\\service"...
0x180086107  mov     edx, 5Eh ; '^'; void *
0x18008610c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180086112  mov     r8, rbx
0x180086115  lea     rdx, ?ContainerNotificationCallback@GetAgentDiagnosticsActionDef@Diagnostics@Microsoft@@SAXPEAU_CMS_CONTAINER_NOTIFICATION@@PEAX@Z; Microsoft::Diagnostics::GetAgentDiagnosticsActionDef::ContainerNotificationCallback(_CMS_CONTAINER_NOTIFICATION *,void *)
0x18008611c  mov     rcx, [rdi]
0x18008611f  call    cs:__imp_CmsRegisterForContainerNotifications
0x180086125  mov     rcx, [rbp+28h]; this
0x180086129  test    eax, eax
0x18008612b  jns     short loc_180086142
0x18008612d  mov     r9d, eax; char *
0x180086130  lea     r8, aOnecoreBaseTel_117; "onecore\\base\\telemetry\\utc\\service"...
0x180086137  mov     edx, 62h ; 'b'; void *
0x18008613c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180086142  lea     r15, [rbx+0C0h]
0x180086149  mov     qword ptr [rsp+60h+var_40], 0; int
0x180086152  xor     r9d, r9d
0x180086155  xor     r8d, r8d
0x180086158  xor     edx, edx
0x18008615a  mov     rcx, r15
0x18008615d  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180086162  lea     rsi, [rbx+0D0h]
0x180086169  mov     r14, [rsi]
0x18008616c  test    r14, r14
0x18008616f  jz      short loc_18008618C
0x180086171  lea     rcx, [rbp+var_30]; this
0x180086175  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18008617a  mov     rcx, r14; this
0x18008617d  call    ?CloseCmsActivity@wilp@@YAXPEAX@Z; wilp::CloseCmsActivity(void *)
0x180086182  lea     rcx, [rbp+var_30]; this
0x180086186  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18008618b  nop
0x18008618c  mov     qword ptr [rsi], 0
0x180086193  mov     edx, r12d
0x180086196  xor     edx, 1
0x180086199  add     edx, 1F41h
0x18008619f  mov     r8, rsi
0x1800861a2  mov     rcx, [rdi]
0x1800861a5  call    cs:__imp_CmsCreateActivity
0x1800861ab  test    eax, eax
0x1800861ad  jns     short loc_1800861C8
0x1800861af  mov     rcx, [rbp+28h]; this
0x1800861b3  mov     r9d, eax; char *
0x1800861b6  lea     r8, aOnecoreBaseTel_117; "onecore\\base\\telemetry\\utc\\service"...
0x1800861bd  mov     edx, 67h ; 'g'; void *
0x1800861c2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800861c8  mov     r8, rbx
0x1800861cb  lea     rdx, ?ContainerActivityNotificationCallback@GetAgentDiagnosticsActionDef@Diagnostics@Microsoft@@SAXPEAU_CMS_ACTIVITY_NOTIFICATION@@PEAX@Z; Microsoft::Diagnostics::GetAgentDiagnosticsActionDef::ContainerActivityNotificationCallback(_CMS_ACTIVITY_NOTIFICATION *,void *)
0x1800861d2  mov     rcx, [rsi]
0x1800861d5  call    cs:__imp_CmsStartActivityAsync
0x1800861db  test    eax, eax
0x1800861dd  jns     short loc_1800861F8
0x1800861df  mov     rcx, [rbp+28h]; this
0x1800861e3  mov     r9d, eax; char *
0x1800861e6  lea     r8, aOnecoreBaseTel_117; "onecore\\base\\telemetry\\utc\\service"...
0x1800861ed  mov     edx, 6Bh ; 'k'; void *
0x1800861f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800861f8  mov     edx, 2710h; unsigned int
0x1800861fd  mov     rcx, [r15]; void *
0x180086200  call    ?WaitOrTimeout@Os@Utils@Diagnostics@Microsoft@@SA_NPEAXK@Z; Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(void *,ulong)
0x180086205  test    al, al
0x180086207  jnz     short loc_180086225
0x180086209  mov     rcx, [rbp+28h]; this
0x18008620d  mov     r9d, 800705B4h; char *
0x180086213  lea     r8, aOnecoreBaseTel_117; "onecore\\base\\telemetry\\utc\\service"...
0x18008621a  mov     edx, 6Eh ; 'n'; void *
0x18008621f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180086225  mov     r9d, [rbx+0D8h]; char *
0x18008622c  test    r9d, r9d
0x18008622f  jns     short loc_180086247
0x180086231  mov     rcx, [rbp+28h]; this
0x180086235  lea     r8, aOnecoreBaseTel_117; "onecore\\base\\telemetry\\utc\\service"...
0x18008623c  mov     edx, 70h ; 'p'; void *
0x180086241  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180086247  mov     rcx, [rbp+var_10]
0x18008624b  xor     rcx, rsp; StackCookie
0x18008624e  call    __security_check_cookie
0x180086253  lea     r11, [rsp+60h+var_s0]
0x180086258  mov     rbx, [r11+38h]
0x18008625c  mov     rsi, [r11+40h]
0x180086260  mov     rsp, r11
0x180086263  pop     r15
0x180086265  pop     r14
0x180086267  pop     r12
0x180086269  pop     rdi
0x18008626a  pop     rbp
0x18008626b  retn
```
