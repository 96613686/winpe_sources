# LuiContext::Initialize(void)

- ea: `0x1800ede84`
- end: `0x1800edf2e`
- name: `?Initialize@LuiContext@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(LuiContext *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800eff70`

## callees

- `0x18006ba8c`
- `0x1800cf300`
- `0x1800ede84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800eded6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800edf06`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800eded6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800edf06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800edef2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800edef2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800edea7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800edea7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LuiContext::Initialize(LuiContext *this)
{
  int LastErrorToHResultAndForceFailure; // ebx
  BOOL v3; // edx
  CommonUtil *v4; // rcx
  HANDLE EventW; // rax
  CommonUtil *v6; // rcx

  LastErrorToHResultAndForceFailure = 0;
  EnterCriticalSection(&LuiContext::_lockLuiContext);
  if ( !LuiContext::_hEventStop )
  {
    v3 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl'::`2'::impl) != 0;
    LuiContext::_hEventStop = CreateEventW(0, v3, 0, 0);
    if ( !LuiContext::_hEventStop )
      LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v4);
  }
  LeaveCriticalSection(&LuiContext::_lockLuiContext);
  if ( LastErrorToHResultAndForceFailure >= 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 4) = EventW;
    if ( !EventW )
      return (unsigned int)CommonUtil::GetLastErrorToHResultAndForceFailure(v6);
  }
  return (unsigned int)LastErrorToHResultAndForceFailure;
}

```

## disassembly

```asm
0x1800ede84  mov     [rsp+arg_0], rbx
0x1800ede89  mov     [rsp+arg_10], rsi
0x1800ede8e  push    rdi
0x1800ede8f  sub     rsp, 20h
0x1800ede93  mov     rdi, rcx
0x1800ede96  xor     ebx, ebx
0x1800ede98  lea     rsi, ?_lockLuiContext@LuiContext@@0VBasicLock@LockHelpers@@A; LockHelpers::BasicLock LuiContext::_lockLuiContext
0x1800ede9f  mov     [rsp+28h+arg_8], rsi
0x1800edea4  mov     rcx, rsi; lpCriticalSection
0x1800edea7  call    cs:__imp_EnterCriticalSection
0x1800edead  nop
0x1800edeae  cmp     cs:?_hEventStop@LuiContext@@0PEAXEA, rbx; void * LuiContext::_hEventStop
0x1800edeb5  jnz     short loc_1800EDEEF
0x1800edeb7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping> `wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl(void)'::`2'::impl
0x1800edebe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(void)
0x1800edec3  xor     r9d, r9d; lpName
0x1800edec6  xor     r8d, r8d; bInitialState
0x1800edec9  xor     ecx, ecx; lpEventAttributes
0x1800edecb  test    al, al
0x1800edecd  jz      short loc_1800EDED4
0x1800edecf  lea     edx, [rbx+1]
0x1800eded2  jmp     short loc_1800EDED6
0x1800eded4  xor     edx, edx; bManualReset
0x1800eded6  call    cs:__imp_CreateEventW
0x1800ededc  mov     cs:?_hEventStop@LuiContext@@0PEAXEA, rax; void * LuiContext::_hEventStop
0x1800edee3  test    rax, rax
0x1800edee6  jnz     short loc_1800EDEEF
0x1800edee8  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800edeed  mov     ebx, eax
0x1800edeef  mov     rcx, rsi; lpCriticalSection
0x1800edef2  call    cs:__imp_LeaveCriticalSection
0x1800edef8  test    ebx, ebx
0x1800edefa  js      short loc_1800EDF1C
0x1800edefc  xor     r9d, r9d; lpName
0x1800edeff  xor     r8d, r8d; bInitialState
0x1800edf02  xor     edx, edx; bManualReset
0x1800edf04  xor     ecx, ecx; lpEventAttributes
0x1800edf06  call    cs:__imp_CreateEventW
0x1800edf0c  mov     [rdi+20h], rax
0x1800edf10  test    rax, rax
0x1800edf13  jnz     short loc_1800EDF1C
0x1800edf15  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800edf1a  mov     ebx, eax
0x1800edf1c  mov     eax, ebx
0x1800edf1e  mov     rbx, [rsp+28h+arg_0]
0x1800edf23  mov     rsi, [rsp+28h+arg_10]
0x1800edf28  add     rsp, 20h
0x1800edf2c  pop     rdi
0x1800edf2d  retn
```
