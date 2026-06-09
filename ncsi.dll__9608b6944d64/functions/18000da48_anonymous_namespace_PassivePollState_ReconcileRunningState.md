# _anonymous_namespace_::PassivePollState::ReconcileRunningState

- ea: `0x18000da48`
- end: `0x18000ddca`
- name: `_anonymous_namespace_::PassivePollState::ReconcileRunningState`
- size: `898`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ef10`
- `0x180023294`
- `0x1800416ec`
- `0x18006d04c`
- `0x18006d224`
- `0x18006d2ac`

## callees

- `0x18000d250`
- `0x18000da48`
- `0x18000e384`
- `0x18000e59c`
- `0x180010200`
- `0x180011a58`
- `0x180018dd0`
- `0x18002c664`
- `0x18002db14`
- `0x18003f2d8`
- `0x180047240`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000dd2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000dd2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dc55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dc55`

## pseudocode

```c
void __fastcall anonymous_namespace_::PassivePollState::ReconcileRunningState(__int64 a1, __int64 a2)
{
  NcsiConfigData *v2; // rcx
  __int64 v3; // r8
  unsigned int v4; // ecx
  unsigned int v5; // r8d
  unsigned int v6; // eax
  unsigned __int8 v7; // bp
  __int64 v8; // rsi
  const char *v9; // rdi
  __int64 v10; // r8
  unsigned int v11; // eax
  unsigned int v12; // edi
  DWORD v13; // ebx
  struct _TP_TIMER *v14; // rsi
  PTP_TIMER *v15; // rcx
  _FILETIME pftDueTime; // [rsp+60h] [rbp-38h] BYREF

  if ( !byte_18009A1ED
    || !byte_18009A1EE
    || !(unsigned int)std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(&dword_18009B3AC, a2, 1)
    && !byte_18009A1EF
    && dword_18009A1F8 > NcsiConfigData::MaxDeadUserPollCount(v2)
    || !dword_18009A1E8 )
  {
    goto LABEL_33;
  }
  v4 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(&dword_18009B3A8, a2, v3);
  if ( v4 )
  {
    a2 = 0x1E % v4;
    v6 = 0x1E / v4;
    if ( 0x1E / v4 < v5 )
      v6 = v5;
  }
  else
  {
    v6 = -1;
  }
  if ( (unsigned int)qword_18009A1F0 <= v6
    || !(unsigned __int8)anonymous_namespace_::PassivePollState::IsV6DeadForMaxPollCount() )
  {
    v7 = v5;
  }
  else
  {
LABEL_33:
    v7 = 0;
  }
  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x40) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    v9 = "InStandby";
    if ( dword_18009A1E8 )
      v9 = "NotInStandby";
    WPP_SF_dddddsddd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      (unsigned __int8)byte_18009A1ED,
      (unsigned __int8)byte_18009A1EC,
      v7,
      byte_18009A1EC,
      byte_18009A1ED,
      byte_18009A1EE,
      byte_18009A1EF,
      (__int64)v9,
      dword_18009A1F8,
      qword_18009A1F0,
      SBYTE4(qword_18009A1F0));
    v8 = WPP_GLOBAL_Control;
  }
  v10 = (unsigned __int8)byte_18009A1EC;
  if ( v7 != byte_18009A1EC )
  {
    if ( (Microsoft_Windows_NCSIEnableBits & 0x1000) != 0 )
    {
      McTemplateU0ttttttqqq_EtwEventWriteTransfer(
        HIDWORD(qword_18009A1F0),
        (unsigned __int8)byte_18009A1EE,
        v7,
        (unsigned __int8)byte_18009A1EC,
        byte_18009A1ED,
        byte_18009A1EE,
        byte_18009A1EF,
        dword_18009A1E8 == 0,
        dword_18009A1F8,
        qword_18009A1F0,
        SBYTE4(qword_18009A1F0));
      v8 = WPP_GLOBAL_Control;
    }
    if ( v7 )
    {
      if ( *off_18009A200 )
      {
        v11 = std::_Atomic_storage<enum Ncsi::Power::PowerState,4>::load(&dword_18009B3A8, a2, v10);
        v12 = v11;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x40) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
        {
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_908899ae445231599b715923bce5511e_Traceguids, v11);
        }
        v13 = 300;
        pftDueTime = (_FILETIME)-10000000LL;
        byte_18009A1EC = 1;
        if ( 250 * v12 > 0x12C )
          v13 = 250 * v12;
        v14 = (struct _TP_TIMER *)*off_18009A200;
        EnterCriticalSection(&stru_18009D4B8);
        if ( byte_18009DAA0 )
          SetThreadpoolTimer(v14, &pftDueTime, 1000 * v12, v13);
        LeaveCriticalSection(&stru_18009D4B8);
      }
      else if ( (_UNKNOWN *)v8 != &WPP_GLOBAL_Control && (*(_BYTE *)(v8 + 28) & 0x40) != 0 && *(_BYTE *)(v8 + 25) >= 2u )
      {
        WPP_SF_(*(_QWORD *)(v8 + 16), 23, WPP_908899ae445231599b715923bce5511e_Traceguids);
      }
    }
    else
    {
      v15 = (PTP_TIMER *)off_18009A200;
      if ( !*off_18009A200 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(off_18009A200);
        v15 = (PTP_TIMER *)off_18009A200;
      }
      NcsiSetThreadpoolTimer(*v15, 0, 0, 0);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x40) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, WPP_908899ae445231599b715923bce5511e_Traceguids);
      }
      byte_18009A1EC = 0;
    }
  }
}

```

## disassembly

```asm
0x18000da48  push    rbx
0x18000da4a  push    rbp
0x18000da4b  push    rsi
0x18000da4c  push    rdi
0x18000da4d  push    r12
0x18000da4f  sub     rsp, 70h
0x18000da53  mov     rax, cs:__security_cookie
0x18000da5a  xor     rax, rsp
0x18000da5d  mov     [rsp+98h+var_30], rax
0x18000da62  cmp     cs:byte_18009A1ED, 0
0x18000da69  mov     r8d, 1
0x18000da6f  jz      loc_18000DC7A
0x18000da75  cmp     cs:byte_18009A1EE, 0
0x18000da7c  jz      loc_18000DC7A
0x18000da82  lea     rcx, dword_18009B3AC
0x18000da89  call    ?load@?$_Atomic_storage@W4PowerState@Power@Ncsi@@$03@std@@QEBA?AW4PowerState@Power@Ncsi@@W4memory_order@2@@Z; std::_Atomic_storage<Ncsi::Power::PowerState,4>::load(std::memory_order)
0x18000da8e  test    eax, eax
0x18000da90  jnz     short loc_18000DA9E
0x18000da92  cmp     cs:byte_18009A1EF, al
0x18000da98  jz      loc_18000DCF5
0x18000da9e  cmp     cs:dword_18009A1E8, 0
0x18000daa5  jz      loc_18000DC7A
0x18000daab  lea     rcx, dword_18009B3A8
0x18000dab2  call    ?load@?$_Atomic_storage@W4PowerState@Power@Ncsi@@$03@std@@QEBA?AW4PowerState@Power@Ncsi@@W4memory_order@2@@Z; std::_Atomic_storage<Ncsi::Power::PowerState,4>::load(std::memory_order)
0x18000dab7  mov     ecx, eax
0x18000dab9  test    eax, eax
0x18000dabb  jz      loc_18000DC82
0x18000dac1  xor     edx, edx
0x18000dac3  lea     eax, [rdx+1Eh]
0x18000dac6  div     ecx
0x18000dac8  cmp     eax, r8d
0x18000dacb  cmovb   eax, r8d
0x18000dacf  cmp     dword ptr cs:qword_18009A1F0, eax
0x18000dad5  ja      loc_18000DD0B
0x18000dadb  mov     bpl, r8b
0x18000dade  mov     rsi, cs:WPP_GLOBAL_Control
0x18000dae5  lea     r12, WPP_GLOBAL_Control
0x18000daec  cmp     rsi, r12
0x18000daef  jz      loc_18000DB8B
0x18000daf5  test    byte ptr [rsi+1Ch], 40h
0x18000daf9  jz      loc_18000DB8B
0x18000daff  cmp     byte ptr [rsi+19h], 5
0x18000db03  jb      loc_18000DB8B
0x18000db09  movzx   ecx, cs:byte_18009A1EE
0x18000db10  lea     rax, aNotinstandby; "NotInStandby"
0x18000db17  cmp     cs:dword_18009A1E8, 0
0x18000db1e  lea     rdi, aInstandby; "InStandby"
0x18000db25  mov     r10d, dword ptr cs:qword_18009A1F0+4
0x18000db2c  mov     r11d, dword ptr cs:qword_18009A1F0
0x18000db33  cmovnz  rdi, rax
0x18000db37  mov     ebx, cs:dword_18009A1F8
0x18000db3d  movzx   eax, cs:byte_18009A1EF
0x18000db44  movzx   edx, cs:byte_18009A1ED
0x18000db4b  movzx   r8d, cs:byte_18009A1EC
0x18000db53  mov     [rsp+98h+var_40], r10d
0x18000db58  mov     [rsp+98h+var_48], r11d
0x18000db5d  mov     [rsp+98h+var_50], ebx
0x18000db61  mov     [rsp+98h+var_58], rdi
0x18000db66  mov     [rsp+98h+var_60], eax
0x18000db6a  mov     [rsp+98h+var_68], ecx
0x18000db6e  mov     rcx, [rsi+10h]
0x18000db72  mov     [rsp+98h+var_70], edx
0x18000db76  movzx   r9d, bpl
0x18000db7a  mov     [rsp+98h+var_78], r8d
0x18000db7f  call    WPP_SF_dddddsddd
0x18000db84  mov     rsi, cs:WPP_GLOBAL_Control
0x18000db8b  movzx   r8d, cs:byte_18009A1EC
0x18000db93  cmp     bpl, r8b
0x18000db96  jz      short loc_18000DBC4
0x18000db98  test    byte ptr cs:Microsoft_Windows_NCSIEnableBits+1, 10h
0x18000db9f  jnz     loc_18000DC8A
0x18000dba5  test    bpl, bpl
0x18000dba8  jz      loc_18000DD68
0x18000dbae  mov     rax, cs:off_18009A200
0x18000dbb5  cmp     qword ptr [rax], 0
0x18000dbb9  jnz     short loc_18000DBDC
0x18000dbbb  cmp     rsi, r12
0x18000dbbe  jnz     loc_18000DD3A
0x18000dbc4  mov     rcx, [rsp+98h+var_30]
0x18000dbc9  xor     rcx, rsp; StackCookie
0x18000dbcc  call    __security_check_cookie
0x18000dbd1  add     rsp, 70h
0x18000dbd5  pop     r12
0x18000dbd7  pop     rdi
0x18000dbd8  pop     rsi
0x18000dbd9  pop     rbp
0x18000dbda  pop     rbx
0x18000dbdb  retn
0x18000dbdc  lea     rcx, dword_18009B3A8
0x18000dbe3  call    ?load@?$_Atomic_storage@W4PowerState@Power@Ncsi@@$03@std@@QEBA?AW4PowerState@Power@Ncsi@@W4memory_order@2@@Z; std::_Atomic_storage<Ncsi::Power::PowerState,4>::load(std::memory_order)
0x18000dbe8  mov     edi, eax
0x18000dbea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbf1  cmp     rcx, r12
0x18000dbf4  jz      short loc_18000DC1A
0x18000dbf6  test    byte ptr [rcx+1Ch], 40h
0x18000dbfa  jz      short loc_18000DC1A
0x18000dbfc  cmp     byte ptr [rcx+19h], 5
0x18000dc00  jb      short loc_18000DC1A
0x18000dc02  mov     rcx, [rcx+10h]
0x18000dc06  lea     r8, WPP_908899ae445231599b715923bce5511e_Traceguids
0x18000dc0d  mov     edx, 16h
0x18000dc12  mov     r9d, eax
0x18000dc15  call    WPP_SF_d
0x18000dc1a  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], 0FFFFFFFFFF676980h
0x18000dc23  lea     rcx, stru_18009D4B8; lpCriticalSection
0x18000dc2a  mov     rax, qword ptr [rsp+98h+pftDueTime.dwLowDateTime]
0x18000dc2f  mov     ebx, 12Ch
0x18000dc34  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], rax
0x18000dc39  imul    eax, edi, 0FAh
0x18000dc3f  mov     cs:byte_18009A1EC, 1
0x18000dc46  cmp     eax, ebx
0x18000dc48  cmova   ebx, eax
0x18000dc4b  mov     rax, cs:off_18009A200
0x18000dc52  mov     rsi, [rax]
0x18000dc55  call    cs:__imp_EnterCriticalSection
0x18000dc5b  cmp     cs:byte_18009DAA0, 0
0x18000dc62  jnz     loc_18000DD1D
0x18000dc68  lea     rcx, stru_18009D4B8; lpCriticalSection
0x18000dc6f  call    cs:__imp_LeaveCriticalSection
0x18000dc75  jmp     loc_18000DBC4
0x18000dc7a  xor     bpl, bpl
0x18000dc7d  jmp     loc_18000DADE
0x18000dc82  or      eax, 0FFFFFFFFh
0x18000dc85  jmp     loc_18000DACF
0x18000dc8a  mov     ecx, dword ptr cs:qword_18009A1F0+4
0x18000dc90  xor     edi, edi
0x18000dc92  cmp     cs:dword_18009A1E8, edi
0x18000dc98  mov     r9d, r8d
0x18000dc9b  mov     r11d, dword ptr cs:qword_18009A1F0
0x18000dca2  mov     ebx, cs:dword_18009A1F8
0x18000dca8  setz    dil
0x18000dcac  movzx   eax, cs:byte_18009A1EF
0x18000dcb3  movzx   edx, cs:byte_18009A1EE
0x18000dcba  movzx   r10d, cs:byte_18009A1ED
0x18000dcc2  mov     [rsp+98h+var_48], ecx
0x18000dcc6  mov     [rsp+98h+var_50], r11d
0x18000dccb  mov     dword ptr [rsp+98h+var_58], ebx
0x18000dccf  mov     [rsp+98h+var_60], edi
0x18000dcd3  mov     [rsp+98h+var_68], eax
0x18000dcd7  mov     [rsp+98h+var_70], edx
0x18000dcdb  movzx   r8d, bpl
0x18000dcdf  mov     [rsp+98h+var_78], r10d
0x18000dce4  call    McTemplateU0ttttttqqq_EtwEventWriteTransfer
0x18000dce9  mov     rsi, cs:WPP_GLOBAL_Control
0x18000dcf0  jmp     loc_18000DBA5
0x18000dcf5  call    ?MaxDeadUserPollCount@NcsiConfigData@@QEBAKXZ; NcsiConfigData::MaxDeadUserPollCount(void)
0x18000dcfa  cmp     cs:dword_18009A1F8, eax
0x18000dd00  ja      loc_18000DC7A
0x18000dd06  jmp     loc_18000DA9E
0x18000dd0b  call    _anonymous_namespace___PassivePollState__IsV6DeadForMaxPollCount
0x18000dd10  test    al, al
0x18000dd12  jnz     loc_18000DC7A
0x18000dd18  jmp     loc_18000DADB
0x18000dd1d  imul    r8d, edi, 3E8h; msPeriod
0x18000dd24  lea     rdx, [rsp+98h+pftDueTime]; pftDueTime
0x18000dd29  mov     r9d, ebx; msWindowLength
0x18000dd2c  mov     rcx, rsi; pti
0x18000dd2f  call    cs:__imp_SetThreadpoolTimer
0x18000dd35  jmp     loc_18000DC68
0x18000dd3a  test    byte ptr [rsi+1Ch], 40h
0x18000dd3e  jz      loc_18000DBC4
0x18000dd44  cmp     byte ptr [rsi+19h], 2
0x18000dd48  jb      loc_18000DBC4
0x18000dd4e  mov     rcx, [rsi+10h]
0x18000dd52  lea     r8, WPP_908899ae445231599b715923bce5511e_Traceguids
0x18000dd59  mov     edx, 17h
0x18000dd5e  call    WPP_SF_
0x18000dd63  jmp     loc_18000DBC4
0x18000dd68  mov     rcx, cs:off_18009A200
0x18000dd6f  cmp     qword ptr [rcx], 0
0x18000dd73  jnz     short loc_18000DD81
0x18000dd75  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000dd7a  mov     rcx, cs:off_18009A200
0x18000dd81  mov     rcx, [rcx]; pti
0x18000dd84  xor     r9d, r9d; msWindowLength
0x18000dd87  xor     r8d, r8d; msPeriod
0x18000dd8a  xor     edx, edx; pftDueTime
0x18000dd8c  call    ?NcsiSetThreadpoolTimer@@YAXPEAU_TP_TIMER@@PEAU_FILETIME@@KK@Z; NcsiSetThreadpoolTimer(_TP_TIMER *,_FILETIME *,ulong,ulong)
0x18000dd91  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd98  cmp     rcx, r12
0x18000dd9b  jz      short loc_18000DDBE
0x18000dd9d  test    byte ptr [rcx+1Ch], 40h
0x18000dda1  jz      short loc_18000DDBE
0x18000dda3  cmp     byte ptr [rcx+19h], 5
0x18000dda7  jb      short loc_18000DDBE
0x18000dda9  mov     rcx, [rcx+10h]
0x18000ddad  lea     r8, WPP_908899ae445231599b715923bce5511e_Traceguids
0x18000ddb4  mov     edx, 18h
0x18000ddb9  call    WPP_SF_
0x18000ddbe  mov     cs:byte_18009A1EC, 0
0x18000ddc5  jmp     loc_18000DBC4
```
