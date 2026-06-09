# NgcTriggerTaskForOobe

- ea: `0x1800151a0`
- end: `0x1800152d5`
- name: `NgcTriggerTaskForOobe`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002e70`
- `0x180006330`
- `0x18000cc34`
- `0x18000ec2c`
- `0x18000fba0`
- `0x18000fe84`
- `0x180010178`
- `0x180011488`
- `0x180015060`
- `0x1800151a0`

## string_xrefs

- `0x180015283`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcTriggerTaskForOobe(int a1, __int64 a2, int a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int *v6; // [rsp+28h] [rbp-29h]
  int v7; // [rsp+38h] [rbp-19h] BYREF
  int v8; // [rsp+3Ch] [rbp-15h] BYREF
  int *v9; // [rsp+40h] [rbp-11h] BYREF
  int *v10; // [rsp+48h] [rbp-9h]
  int *v11; // [rsp+50h] [rbp-1h]
  _BYTE v12[24]; // [rsp+60h] [rbp+Fh] BYREF
  int v13; // [rsp+78h] [rbp+27h] BYREF
  char v14; // [rsp+7Ch] [rbp+2Bh]
  struct _GUID v15; // [rsp+90h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]
  int v17; // [rsp+B8h] [rbp+67h] BYREF
  __int64 v18; // [rsp+C0h] [rbp+6Fh] BYREF
  int v19; // [rsp+C8h] [rbp+77h] BYREF

  v19 = a3;
  v18 = a2;
  v17 = a1;
  v7 = 0;
  v13 = 0;
  v14 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180031038 > 5 )
  {
    v8 = v7;
    if ( v14 )
      _tlgGuidIsZero(&v15);
    v6 = &v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180031038,
      (__int64)&dword_1800299C4);
  }
  v9 = &v13;
  v10 = &v7;
  wil::ScopeExitIgnore__lambda_9a04ade32bc4c00cbc14cd3450be4e0d___(v12, &v9);
  v9 = &v17;
  v10 = (int *)&v18;
  v11 = &v19;
  v3 = HResultErrorContract__lambda_3497ebea56105ad8129ebad1a51ab630_(&v9);
  v4 = v3;
  v7 = v3;
  if ( v3 >= 0 )
  {
    wil::details::ScopeExitFnGuard__lambda_9a04ade32bc4c00cbc14cd3450be4e0d___::operator()(v12);
    v4 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x709,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)v3,
      (int)v6);
    wil::details::ScopeExitFnGuard__lambda_9a04ade32bc4c00cbc14cd3450be4e0d___::operator()(v12);
  }
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v13);
  return v4;
}

```

## disassembly

```asm
0x1800151a0  mov     rax, rsp
0x1800151a3  mov     [rax+20h], rbx
0x1800151a7  mov     [rax+18h], r8d
0x1800151ab  mov     [rax+10h], rdx
0x1800151af  mov     [rax+8], ecx
0x1800151b2  push    rbp
0x1800151b3  lea     rbp, [rax-5Fh]
0x1800151b7  sub     rsp, 0A0h
0x1800151be  mov     rax, cs:__security_cookie
0x1800151c5  xor     rax, rsp
0x1800151c8  mov     [rbp+57h+var_8], rax
0x1800151cc  mov     [rbp+57h+var_70], 0
0x1800151d3  mov     [rbp+57h+var_30], 0
0x1800151da  mov     [rbp+57h+var_2C], 0
0x1800151de  lea     rcx, [rbp+57h+var_30]
0x1800151e2  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x1800151e7  mov     eax, cs:dword_180031038
0x1800151ed  cmp     eax, 5
0x1800151f0  jbe     short loc_180015234
0x1800151f2  mov     eax, [rbp+57h+var_70]
0x1800151f5  mov     [rbp+57h+var_6C], eax
0x1800151f8  cmp     [rbp+57h+var_2C], 0
0x1800151fc  jz      short loc_180015211
0x1800151fe  lea     rcx, [rbp+57h+var_18]; struct _GUID *
0x180015202  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180015207  test    al, al
0x180015209  jnz     short loc_180015211
0x18001520b  lea     r9, [rbp+57h+var_18]
0x18001520f  jmp     short loc_180015214
0x180015211  xor     r9d, r9d
0x180015214  lea     rax, [rbp+57h+var_6C]
0x180015218  mov     [rsp+20h], rax; int
0x18001521d  lea     r8, [rbp+57h+var_28]
0x180015221  lea     rdx, dword_1800299C4
0x180015228  lea     rcx, dword_180031038
0x18001522f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180015234  lea     rax, [rbp+57h+var_30]
0x180015238  mov     [rbp+57h+var_68], rax
0x18001523c  lea     rax, [rbp+57h+var_70]
0x180015240  mov     [rbp+57h+var_60], rax
0x180015244  lea     rdx, [rbp+57h+var_68]
0x180015248  lea     rcx, [rbp+57h+var_48]
0x18001524c  call    wil__ScopeExitIgnore__lambda_9a04ade32bc4c00cbc14cd3450be4e0d___
0x180015251  nop
0x180015252  lea     rax, [rbp+57h+arg_0]
0x180015256  mov     [rbp+57h+var_68], rax
0x18001525a  lea     rax, [rbp+57h+arg_8]
0x18001525e  mov     [rbp+57h+var_60], rax
0x180015262  lea     rax, [rbp+57h+arg_10]
0x180015266  mov     [rbp+57h+var_58], rax
0x18001526a  lea     rcx, [rbp+57h+var_68]
0x18001526e  call    HResultErrorContract__lambda_3497ebea56105ad8129ebad1a51ab630___; HResultErrorContract__lambda_3497ebea56105ad8129ebad1a51ab630_
0x180015273  mov     ebx, eax
0x180015275  mov     [rbp+57h+var_70], eax
0x180015278  test    eax, eax
0x18001527a  jns     short loc_1800152A1
0x18001527c  mov     rcx, [rbp+5Fh]; this
0x180015280  mov     r9d, eax; char *
0x180015283  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001528a  mov     edx, 709h; void *
0x18001528f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015294  nop
0x180015295  lea     rcx, [rbp+57h+var_48]
0x180015299  call    wil__details__ScopeExitFnGuard__lambda_9a04ade32bc4c00cbc14cd3450be4e0d_____operator__
0x18001529e  nop
0x18001529f  jmp     short loc_1800152AD
0x1800152a1  lea     rcx, [rbp+57h+var_48]
0x1800152a5  call    wil__details__ScopeExitFnGuard__lambda_9a04ade32bc4c00cbc14cd3450be4e0d_____operator__
0x1800152aa  nop
0x1800152ab  xor     ebx, ebx
0x1800152ad  lea     rcx, [rbp+57h+var_30]
0x1800152b1  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x1800152b6  mov     eax, ebx
0x1800152b8  mov     rcx, [rbp+57h+var_8]
0x1800152bc  xor     rcx, rsp; StackCookie
0x1800152bf  call    __security_check_cookie
0x1800152c4  mov     rbx, [rsp+0A0h+arg_18]
0x1800152cc  add     rsp, 0A0h
0x1800152d3  pop     rbp
0x1800152d4  retn
```
