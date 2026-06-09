# RdsDWMDirectUpdateProcessor::ProcessEndOfFrame(void)

- ea: `0x18001054c`
- end: `0x18001071e`
- name: `?ProcessEndOfFrame@RdsDWMDirectUpdateProcessor@@IEAAXXZ`
- size: `466`
- prototype: `void __fastcall(RdsDWMDirectUpdateProcessor *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180010a30`
- `0x180012950`

## callees

- `0x1800010f8`
- `0x180001724`
- `0x18000fcb8`
- `0x18001054c`
- `0x1800196a4`
- `0x180019c34`
- `0x18002c010`

## string_xrefs

- `0x1800105f4`: `clientcore\termsrv\rdsdwmdirect\rdsdwmdrupdateprocessor.cpp`
- `0x180010572`: `RdsDWMDirectUpdateProcessor::ProcessEndOfFrame`
- `0x1800106f3`: `RdsDWMDirectUpdateProcessor::ProcessEndOfFrame frame not started - skipping end frame.`

## pseudocode

```c
void __fastcall RdsDWMDirectUpdateProcessor::ProcessEndOfFrame(
        RdsDWMDirectUpdateProcessor *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  bool v9; // zf
  _QWORD *v10; // rdi
  __int64 *v11; // rsi
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // r9
  unsigned int v15; // [rsp+20h] [rbp-40h]
  const char *v16; // [rsp+50h] [rbp-10h] BYREF
  const char *v17; // [rsp+58h] [rbp-8h] BYREF
  const char *v18; // [rsp+90h] [rbp+30h] BYREF
  int v19; // [rsp+98h] [rbp+38h] BYREF
  const char *v20; // [rsp+A0h] [rbp+40h] BYREF
  const char *v21; // [rsp+A8h] [rbp+48h] BYREF

  if ( *((_DWORD *)this + 22) )
  {
    if ( (unsigned int)dword_180044008 > 5 )
    {
      v18 = "RdsDWMDirectUpdateProcessor::ProcessEndOfFrame";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)this,
        (__int64)byte_180039E41,
        a3,
        a4,
        (const unsigned __int16 **)&v18);
    }
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 5) + 32LL))(
           *((_QWORD *)this + 5),
           *((_QWORD *)this + 9),
           *((unsigned int *)this + 20),
           1);
    if ( v5 < 0 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v19 = v5;
        v20 = "Failed to send an end-of frame.";
        v17 = "Error HResult failed";
        v21 = "ProcessEndOfFrame";
        LODWORD(v18) = 1309;
        v16 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (__int64)"clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrupdateprocessor.cpp",
          (__int64)&dword_180039DF4,
          v7,
          v8,
          (const unsigned __int16 **)&v17,
          (__int64)&v19,
          (const unsigned __int16 **)&v16,
          (__int64)&v18,
          (const unsigned __int16 **)&v21,
          (const unsigned __int16 **)&v20);
      }
      return;
    }
    v9 = *((_DWORD *)this + 40) == 0;
    *((_DWORD *)this + 22) = 0;
    if ( v9 && *((_QWORD *)this + 17) )
    {
      v10 = (_QWORD *)((char *)this + 144);
      if ( !*((_QWORD *)this + 18) )
        *v10 = RDSDWMDirectTraceLogging::GetCurrentMsTime(*((RDSDWMDirectTraceLogging **)this + 16), v6);
      v11 = (__int64 *)((char *)this + 152);
      if ( RdsDWMDirectUpdateProcessor::IsHiDefProcessorReady(this) )
      {
        if ( *v11 || !*((_DWORD *)this + 30) )
          return;
        *v11 = RDSDWMDirectTraceLogging::GetCurrentMsTime(*((RDSDWMDirectTraceLogging **)this + 16), v12);
        v10 = (_QWORD *)((char *)this + 144);
      }
      v13 = *((_DWORD *)this + 34);
      v14 = *v11;
      if ( *v11 )
        LODWORD(v14) = v14 - v13;
      RDSDWMDirectTraceLogging::LogTimeToFirstFrame(
        (RdsDWMDirectUpdateProcessor *)((char *)this + 92),
        (struct _GUID *)*((unsigned int *)this + 29),
        *(_DWORD *)v10 - v13,
        v14,
        v15);
      *((_DWORD *)this + 40) = 1;
    }
  }
  else if ( (unsigned int)dword_180044008 > 5 )
  {
    v18 = "RdsDWMDirectUpdateProcessor::ProcessEndOfFrame frame not started - skipping end frame.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)this,
      (__int64)byte_180039DD3,
      a3,
      a4,
      (const unsigned __int16 **)&v18);
  }
}

```

## disassembly

```asm
0x18001054c  push    rbp
0x18001054e  push    rbx
0x18001054f  push    rsi
0x180010550  push    rdi
0x180010551  push    r14
0x180010553  mov     rbp, rsp
0x180010556  sub     rsp, 60h
0x18001055a  cmp     dword ptr [rcx+58h], 0
0x18001055e  mov     rbx, rcx
0x180010561  mov     eax, cs:dword_180044008
0x180010567  jz      loc_1800106EE
0x18001056d  cmp     eax, 5
0x180010570  jbe     short loc_180010592
0x180010572  lea     rax, aRdsdwmdirectup_1; "RdsDWMDirectUpdateProcessor::ProcessEnd"...
0x180010579  mov     [rbp+arg_0], rax
0x18001057d  lea     rdx, byte_180039E41
0x180010584  lea     rax, [rbp+arg_0]
0x180010588  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x18001058d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180010592  mov     rcx, [rbx+28h]
0x180010596  mov     r9d, 1
0x18001059c  mov     r8d, [rbx+50h]
0x1800105a0  mov     rdx, [rbx+48h]
0x1800105a4  mov     rax, [rcx]
0x1800105a7  mov     rax, [rax+20h]
0x1800105ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105b0  test    eax, eax
0x1800105b2  jns     loc_180010644
0x1800105b8  mov     ecx, cs:dword_180044008
0x1800105be  cmp     ecx, 2
0x1800105c1  jbe     loc_180010713
0x1800105c7  mov     [rbp+arg_8], eax
0x1800105ca  lea     rcx, aFailedToSendAn; "Failed to send an end-of frame."
0x1800105d1  mov     [rbp+arg_10], rcx
0x1800105d5  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800105dc  mov     [rbp+var_8], rax
0x1800105e0  lea     rcx, aProcessendoffr; "ProcessEndOfFrame"
0x1800105e7  lea     rax, [rbp+arg_10]
0x1800105eb  mov     [rbp+arg_18], rcx
0x1800105ef  mov     [rsp+60h+var_18], rax
0x1800105f4  lea     rcx, aClientcoreTerm_2; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x1800105fb  lea     rax, [rbp+arg_18]
0x1800105ff  mov     dword ptr [rbp+arg_0], 51Dh
0x180010606  mov     [rsp+60h+var_20], rax
0x18001060b  lea     rdx, dword_180039DF4
0x180010612  lea     rax, [rbp+arg_0]
0x180010616  mov     [rbp+var_10], rcx
0x18001061a  mov     [rsp+60h+var_28], rax
0x18001061f  lea     rax, [rbp+var_10]
0x180010623  mov     [rsp+60h+var_30], rax
0x180010628  lea     rax, [rbp+arg_8]
0x18001062c  mov     [rsp+60h+var_38], rax
0x180010631  lea     rax, [rbp+var_8]
0x180010635  mov     qword ptr [rsp+60h+var_40], rax
0x18001063a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001063f  jmp     loc_180010713
0x180010644  cmp     dword ptr [rbx+0A0h], 0
0x18001064b  mov     dword ptr [rbx+58h], 0
0x180010652  jnz     loc_180010713
0x180010658  cmp     qword ptr [rbx+88h], 0
0x180010660  jz      loc_180010713
0x180010666  lea     rdi, [rbx+90h]
0x18001066d  cmp     qword ptr [rdi], 0
0x180010671  jnz     short loc_18001068B
0x180010673  mov     rcx, [rbx+80h]; this
0x18001067a  call    ?GetCurrentMsTime@RDSDWMDirectTraceLogging@@YA_J_J@Z; RDSDWMDirectTraceLogging::GetCurrentMsTime(__int64)
0x18001067f  mov     [rdi], rax
0x180010682  lea     r14, [rbx+90h]
0x180010689  jmp     short loc_18001068E
0x18001068b  mov     r14, rdi
0x18001068e  mov     rcx, rbx; this
0x180010691  lea     rsi, [rbx+98h]
0x180010698  call    ?IsHiDefProcessorReady@RdsDWMDirectUpdateProcessor@@IEAAHXZ; RdsDWMDirectUpdateProcessor::IsHiDefProcessorReady(void)
0x18001069d  test    eax, eax
0x18001069f  jz      short loc_1800106BF
0x1800106a1  cmp     qword ptr [rsi], 0
0x1800106a5  jnz     short loc_180010713
0x1800106a7  cmp     dword ptr [rbx+78h], 0
0x1800106ab  jz      short loc_180010713
0x1800106ad  mov     rcx, [rbx+80h]; this
0x1800106b4  call    ?GetCurrentMsTime@RDSDWMDirectTraceLogging@@YA_J_J@Z; RDSDWMDirectTraceLogging::GetCurrentMsTime(__int64)
0x1800106b9  mov     [rsi], rax
0x1800106bc  mov     rdi, r14
0x1800106bf  mov     r8d, [rdi]
0x1800106c2  mov     eax, [rbx+88h]
0x1800106c8  sub     r8d, eax; unsigned int
0x1800106cb  mov     r9, [rsi]
0x1800106ce  test    r9, r9
0x1800106d1  jz      short loc_1800106D6
0x1800106d3  sub     r9d, eax; unsigned int
0x1800106d6  mov     edx, [rbx+74h]; struct _GUID *
0x1800106d9  lea     rcx, [rbx+5Ch]; this
0x1800106dd  call    ?LogTimeToFirstFrame@RDSDWMDirectTraceLogging@@YAXPEAU_GUID@@III@Z; RDSDWMDirectTraceLogging::LogTimeToFirstFrame(_GUID *,uint,uint,uint)
0x1800106e2  mov     dword ptr [rbx+0A0h], 1
0x1800106ec  jmp     short loc_180010713
0x1800106ee  cmp     eax, 5
0x1800106f1  jbe     short loc_180010713
0x1800106f3  lea     rax, aRdsdwmdirectup_4; "RdsDWMDirectUpdateProcessor::ProcessEnd"...
0x1800106fa  mov     [rbp+arg_0], rax
0x1800106fe  lea     rdx, byte_180039DD3
0x180010705  lea     rax, [rbp+arg_0]
0x180010709  mov     qword ptr [rsp+60h+var_40], rax
0x18001070e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180010713  add     rsp, 60h
0x180010717  pop     r14
0x180010719  pop     rdi
0x18001071a  pop     rsi
0x18001071b  pop     rbx
0x18001071c  pop     rbp
0x18001071d  retn
```
