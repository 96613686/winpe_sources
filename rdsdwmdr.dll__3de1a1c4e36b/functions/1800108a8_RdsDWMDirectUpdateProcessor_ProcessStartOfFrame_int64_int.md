# RdsDWMDirectUpdateProcessor::ProcessStartOfFrame(__int64,int *)

- ea: `0x1800108a8`
- end: `0x180010a1e`
- name: `?ProcessStartOfFrame@RdsDWMDirectUpdateProcessor@@IEAAJ_JPEAH@Z`
- size: `374`
- prototype: `__int64 __fastcall(RdsDWMDirectUpdateProcessor *__hidden this, __int64, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180010a30`
- `0x180012960`

## callees

- `0x1800010f8`
- `0x180001188`
- `0x1800108a8`
- `0x180012238`
- `0x18002c010`

## string_xrefs

- `0x1800108dd`: `RdsDWMDirectUpdateProcessor::ProcessStartOfFrame`
- `0x1800109c9`: `Failed to send the driver start frame. Gfx updates may stall.`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectUpdateProcessor::ProcessStartOfFrame(
        RdsDWMDirectUpdateProcessor *this,
        __int64 a2,
        int *a3,
        __int64 a4)
{
  int v4; // esi
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  const char *v16; // [rsp+40h] [rbp-10h] BYREF
  const char *v17; // [rsp+80h] [rbp+30h] BYREF
  const char *v18; // [rsp+90h] [rbp+40h] BYREF
  const char *v19; // [rsp+98h] [rbp+48h] BYREF

  v4 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !*((_DWORD *)this + 22) )
  {
    if ( (unsigned int)dword_180044008 > 5 )
    {
      v17 = "RdsDWMDirectUpdateProcessor::ProcessStartOfFrame";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (__int64)this,
        (__int64)&word_180039EBE,
        (__int64)a3,
        a4,
        (const unsigned __int16 **)&v17);
    }
    ++*((_DWORD *)this + 20);
    if ( *((_DWORD *)this + 28) )
      RdsDWMDirectUpdateProcessor::ResetStateOnSessionReconnect(this, a2, (__int64)a3, a4);
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int))(**((_QWORD **)this + 5) + 24LL))(
           *((_QWORD *)this + 5),
           *((_QWORD *)this + 9),
           *((unsigned int *)this + 20),
           a2,
           1);
    if ( v4 >= 0 )
      goto LABEL_16;
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v17 = "Driver start frame failed with reconnect probe - reset required.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v9,
        (__int64)byte_180039E9D,
        v10,
        v11,
        (const unsigned __int16 **)&v17);
    }
    if ( a3 )
      *a3 = 1;
    *((_QWORD *)this + 14) = 1;
    RdsDWMDirectUpdateProcessor::ResetStateOnSessionReconnect(this, v8, v10, v11);
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int))(**((_QWORD **)this + 5) + 24LL))(
           *((_QWORD *)this + 5),
           *((_QWORD *)this + 9),
           *((unsigned int *)this + 20),
           a2,
           2);
    if ( v4 >= 0 )
    {
LABEL_16:
      *((_DWORD *)this + 22) = 1;
    }
    else if ( (unsigned int)dword_180044008 > 3 )
    {
      LODWORD(v17) = v4;
      v18 = "ProcessStartOfFrame";
      v19 = "Failed to send the driver start frame. Gfx updates may stall.";
      v16 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v12,
        (__int64)word_180039E62,
        v13,
        v14,
        (const unsigned __int16 **)&v16,
        (const unsigned __int16 **)&v19,
        (__int64)&v17,
        (const unsigned __int16 **)&v18);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800108a8  push    rbp
0x1800108aa  push    rbx
0x1800108ab  push    rsi
0x1800108ac  push    rdi
0x1800108ad  push    r14
0x1800108af  mov     rbp, rsp
0x1800108b2  sub     rsp, 50h
0x1800108b6  xor     esi, esi
0x1800108b8  mov     rdi, r8
0x1800108bb  mov     r14, rdx
0x1800108be  mov     rbx, rcx
0x1800108c1  test    r8, r8
0x1800108c4  jz      short loc_1800108C9
0x1800108c6  mov     [r8], esi
0x1800108c9  cmp     [rcx+58h], esi
0x1800108cc  jnz     loc_180010A11
0x1800108d2  mov     eax, cs:dword_180044008
0x1800108d8  cmp     eax, 5
0x1800108db  jbe     short loc_1800108FD
0x1800108dd  lea     rax, aRdsdwmdirectup_9; "RdsDWMDirectUpdateProcessor::ProcessSta"...
0x1800108e4  mov     [rbp+arg_0], rax
0x1800108e8  lea     rdx, word_180039EBE
0x1800108ef  lea     rax, [rbp+arg_0]
0x1800108f3  mov     [rsp+50h+var_30], rax
0x1800108f8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800108fd  inc     dword ptr [rbx+50h]
0x180010900  cmp     [rbx+70h], esi
0x180010903  jz      short loc_18001090D
0x180010905  mov     rcx, rbx; this
0x180010908  call    ?ResetStateOnSessionReconnect@RdsDWMDirectUpdateProcessor@@IEAAXXZ; RdsDWMDirectUpdateProcessor::ResetStateOnSessionReconnect(void)
0x18001090d  mov     rcx, [rbx+28h]
0x180010911  mov     r9, r14
0x180010914  mov     r8d, [rbx+50h]
0x180010918  mov     rdx, [rbx+48h]
0x18001091c  mov     dword ptr [rsp+50h+var_30], 1
0x180010924  mov     rax, [rcx]
0x180010927  mov     rax, [rax+18h]
0x18001092b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010930  mov     esi, eax
0x180010932  test    eax, eax
0x180010934  jns     loc_180010A0A
0x18001093a  mov     eax, cs:dword_180044008
0x180010940  cmp     eax, 4
0x180010943  jbe     short loc_180010965
0x180010945  lea     rax, aDriverStartFra; "Driver start frame failed with reconnec"...
0x18001094c  mov     [rbp+arg_0], rax
0x180010950  lea     rdx, byte_180039E9D
0x180010957  lea     rax, [rbp+arg_0]
0x18001095b  mov     [rsp+50h+var_30], rax
0x180010960  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180010965  test    rdi, rdi
0x180010968  jz      short loc_180010970
0x18001096a  mov     dword ptr [rdi], 1
0x180010970  mov     rcx, rbx; this
0x180010973  mov     qword ptr [rbx+70h], 1
0x18001097b  call    ?ResetStateOnSessionReconnect@RdsDWMDirectUpdateProcessor@@IEAAXXZ; RdsDWMDirectUpdateProcessor::ResetStateOnSessionReconnect(void)
0x180010980  mov     rcx, [rbx+28h]
0x180010984  mov     r9, r14
0x180010987  mov     r8d, [rbx+50h]
0x18001098b  mov     rdx, [rbx+48h]
0x18001098f  mov     dword ptr [rsp+50h+var_30], 2
0x180010997  mov     rax, [rcx]
0x18001099a  mov     rax, [rax+18h]
0x18001099e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109a3  mov     esi, eax
0x1800109a5  test    eax, eax
0x1800109a7  jns     short loc_180010A0A
0x1800109a9  mov     eax, cs:dword_180044008
0x1800109af  cmp     eax, 3
0x1800109b2  jbe     short loc_180010A11
0x1800109b4  lea     rax, aProcessstartof; "ProcessStartOfFrame"
0x1800109bb  mov     dword ptr [rbp+arg_0], esi
0x1800109be  mov     [rbp+arg_10], rax
0x1800109c2  lea     rdx, word_180039E62
0x1800109c9  lea     rax, aFailedToSendTh_4; "Failed to send the driver start frame. "...
0x1800109d0  mov     [rbp+arg_18], rax
0x1800109d4  lea     rax, aHresultFailedB; "HResult failed but continue"
0x1800109db  mov     [rbp+var_10], rax
0x1800109df  lea     rax, [rbp+arg_10]
0x1800109e3  mov     [rsp+50h+var_18], rax
0x1800109e8  lea     rax, [rbp+arg_0]
0x1800109ec  mov     [rsp+50h+var_20], rax
0x1800109f1  lea     rax, [rbp+arg_18]
0x1800109f5  mov     [rsp+50h+var_28], rax
0x1800109fa  lea     rax, [rbp+var_10]
0x1800109fe  mov     [rsp+50h+var_30], rax
0x180010a03  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180010a08  jmp     short loc_180010A11
0x180010a0a  mov     dword ptr [rbx+58h], 1
0x180010a11  mov     eax, esi
0x180010a13  add     rsp, 50h
0x180010a17  pop     r14
0x180010a19  pop     rdi
0x180010a1a  pop     rsi
0x180010a1b  pop     rbx
0x180010a1c  pop     rbp
0x180010a1d  retn
```
