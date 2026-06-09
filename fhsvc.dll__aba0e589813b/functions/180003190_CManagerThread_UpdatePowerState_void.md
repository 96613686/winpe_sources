# CManagerThread::UpdatePowerState(void)

- ea: `0x180003190`
- end: `0x180003387`
- name: `?UpdatePowerState@CManagerThread@@QEAAXXZ`
- size: `503`
- prototype: `void __fastcall(CManagerThread *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800026a0`
- `0x180008180`

## callees

- `0x180003190`
- `0x180004e30`
- `0x180004e50`
- `0x180007300`
- `0x180007f50`
- `0x18000ca14`
- `0x18000daf0`
- `0x180011980`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000333d`
- `KERNEL32!GetLastError` at `0x18000333d`
- `KERNEL32!SetEvent` at `0x18000330f`
- `KERNEL32!SetEvent` at `0x18000330f`
- `KERNEL32!EnterCriticalSection` at `0x1800031e6`
- `KERNEL32!EnterCriticalSection` at `0x1800031e6`
- `KERNEL32!LeaveCriticalSection` at `0x18000331c`
- `KERNEL32!LeaveCriticalSection` at `0x18000331c`
- `KERNEL32!GetSystemPowerStatus` at `0x1800031ba`
- `KERNEL32!GetSystemPowerStatus` at `0x1800031ba`

## pseudocode

```c
void __fastcall CManagerThread::UpdatePowerState(CManagerThread *this)
{
  int v1; // ebp
  const char *v2; // r9
  int v3; // r14d
  __int64 v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 i; // rcx
  bool v8; // zf
  CConfigDescriptor **v9; // rbx
  _QWORD *v10; // rax
  signed int LastError; // eax
  CConfigDescriptor **v12; // [rsp+20h] [rbp-48h] BYREF
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+28h] [rbp-40h] BYREF

  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  if ( GetSystemPowerStatus(&SystemPowerStatus) )
  {
    v1 = SystemPowerStatus.ACLineStatus == 0;
    if ( qword_1800199B8 != v1 )
    {
      EnterCriticalSection(&CriticalSection);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v2 = "DC";
        if ( !v1 )
          v2 = "AC";
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, v2);
      }
      qword_1800199B8 = v1;
      v3 = *(&qword_1800199B8 + 1);
      v4 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(
             (__int64)&xmmword_1800198F0,
             xmmword_1800198F0);
      while ( v4 )
      {
        SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v12);
        v5 = v4;
        v6 = *(_QWORD *)(v4 + 32);
        if ( v6 == qword_180019918 )
        {
          for ( i = *(_QWORD *)(v4 + 40); ; i = *(_QWORD *)(i + 40) )
          {
            v8 = i == qword_180019918;
            if ( i == qword_180019918 )
              break;
            if ( v4 != *(_QWORD *)(i + 32) )
            {
              v8 = i == qword_180019918;
              break;
            }
            v4 = i;
          }
          v4 = 0;
          if ( !v8 )
            v4 = i;
        }
        else
        {
          v4 = ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(
                 (__int64)&xmmword_1800198F0,
                 v6);
        }
        v9 = v12;
        if ( v12 != *(CConfigDescriptor ***)(v5 + 8) )
        {
          if ( v12 )
            SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs((__int64)v12, v6);
          v9 = *(CConfigDescriptor ***)(v5 + 8);
          v12 = v9;
          if ( v9 )
            ++*((_DWORD *)v9 + 2);
        }
        v10 = (_QWORD *)*((_QWORD *)*v9 + 17);
        if ( v10 )
        {
          if ( *v10 )
            CConfigDescriptor::RefreshPoliciesInEngine(*v9, v3, v1);
        }
        SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs((__int64)v9, v6);
      }
      SetEvent(hEvent);
      LeaveCriticalSection(&CriticalSection);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      89,
      &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
      (unsigned int)LastError);
  }
}

```

## disassembly

```asm
0x180003190  push    rbx
0x180003192  push    rbp
0x180003193  push    rsi
0x180003194  push    rdi
0x180003195  push    r14
0x180003197  sub     rsp, 40h
0x18000319b  mov     rax, cs:__security_cookie
0x1800031a2  xor     rax, rsp
0x1800031a5  mov     [rsp+68h+var_30], rax
0x1800031aa  xor     eax, eax
0x1800031ac  mov     qword ptr [rsp+68h+SystemPowerStatus.ACLineStatus], rax
0x1800031b1  mov     [rsp+68h+SystemPowerStatus.BatteryFullLifeTime], eax
0x1800031b5  lea     rcx, [rsp+68h+SystemPowerStatus]; lpSystemPowerStatus
0x1800031ba  call    cs:__imp_GetSystemPowerStatus
0x1800031c0  test    eax, eax
0x1800031c2  jz      loc_180003324
0x1800031c8  xor     ebp, ebp
0x1800031ca  cmp     [rsp+68h+SystemPowerStatus.ACLineStatus], bpl
0x1800031cf  setz    bpl
0x1800031d3  cmp     dword ptr cs:qword_1800199B8, ebp
0x1800031d9  jz      loc_18000336F
0x1800031df  lea     rcx, CriticalSection; lpCriticalSection
0x1800031e6  call    cs:__imp_EnterCriticalSection
0x1800031ec  lea     rax, WPP_GLOBAL_Control
0x1800031f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031fa  cmp     rcx, rax
0x1800031fd  jz      short loc_18000322E
0x1800031ff  test    byte ptr [rcx+1Ch], 8
0x180003203  jz      short loc_18000322E
0x180003205  lea     rax, aAc; "AC"
0x18000320c  lea     r9, aDc; "DC"
0x180003213  test    ebp, ebp
0x180003215  cmovz   r9, rax
0x180003219  mov     edx, 58h ; 'X'
0x18000321e  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180003225  mov     rcx, [rcx+10h]
0x180003229  call    WPP_SF_s
0x18000322e  mov     dword ptr cs:qword_1800199B8, ebp
0x180003234  mov     r14d, dword ptr cs:qword_1800199B8+4
0x18000323b  mov     rdx, qword ptr cs:xmmword_1800198F0
0x180003242  lea     rcx, xmmword_1800198F0
0x180003249  call    ?Minimum@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x18000324e  mov     rsi, rax
0x180003251  test    rax, rax
0x180003254  jz      loc_180003308
0x18000325a  lea     rcx, [rsp+68h+var_48]
0x18000325f  call    ??0?$SmartPtr@VCConfigDescriptor@@@@QEAA@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(CConfigDescriptor *)
0x180003264  mov     rdi, rsi
0x180003267  mov     rax, cs:qword_180019918
0x18000326e  mov     rdx, [rsi+20h]
0x180003272  cmp     rdx, rax
0x180003275  jz      short loc_180003288
0x180003277  lea     rcx, xmmword_1800198F0
0x18000327e  call    ?Minimum@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x180003283  mov     rsi, rax
0x180003286  jmp     short loc_1800032AE
0x180003288  mov     rcx, [rsi+28h]
0x18000328c  cmp     rcx, rax
0x18000328f  jz      short loc_1800032A3
0x180003291  cmp     rsi, [rcx+20h]
0x180003295  jnz     short loc_1800032A0
0x180003297  mov     rsi, rcx
0x18000329a  mov     rcx, [rcx+28h]
0x18000329e  jmp     short loc_18000328C
0x1800032a0  cmp     rcx, rax
0x1800032a3  setz    al
0x1800032a6  xor     esi, esi
0x1800032a8  test    al, al
0x1800032aa  cmovz   rsi, rcx
0x1800032ae  mov     rbx, [rsp+68h+var_48]
0x1800032b3  cmp     rbx, [rdi+8]
0x1800032b7  jz      short loc_1800032D7
0x1800032b9  test    rbx, rbx
0x1800032bc  jz      short loc_1800032C6
0x1800032be  mov     rcx, rbx
0x1800032c1  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ; SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)
0x1800032c6  mov     rbx, [rdi+8]
0x1800032ca  mov     [rsp+68h+var_48], rbx
0x1800032cf  test    rbx, rbx
0x1800032d2  jz      short loc_1800032D7
0x1800032d4  inc     dword ptr [rbx+8]
0x1800032d7  mov     rcx, [rbx]; this
0x1800032da  mov     rax, [rcx+88h]
0x1800032e1  test    rax, rax
0x1800032e4  jz      short loc_1800032F7
0x1800032e6  cmp     qword ptr [rax], 0
0x1800032ea  jz      short loc_1800032F7
0x1800032ec  mov     r8d, ebp; int
0x1800032ef  mov     edx, r14d; int
0x1800032f2  call    ?RefreshPoliciesInEngine@CConfigDescriptor@@QEAAXHH@Z; CConfigDescriptor::RefreshPoliciesInEngine(int,int)
0x1800032f7  mov     rcx, rbx
0x1800032fa  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ; SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)
0x1800032ff  test    rsi, rsi
0x180003302  jnz     loc_18000325A
0x180003308  mov     rcx, cs:hEvent; hEvent
0x18000330f  call    cs:__imp_SetEvent
0x180003315  lea     rcx, CriticalSection; lpCriticalSection
0x18000331c  call    cs:__imp_LeaveCriticalSection
0x180003322  jmp     short loc_18000336F
0x180003324  lea     rax, WPP_GLOBAL_Control
0x18000332b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003332  cmp     rcx, rax
0x180003335  jz      short loc_18000336F
0x180003337  test    byte ptr [rcx+1Ch], 1
0x18000333b  jz      short loc_18000336F
0x18000333d  call    cs:__imp_GetLastError
0x180003343  test    eax, eax
0x180003345  jle     short loc_18000334F
0x180003347  movzx   eax, ax
0x18000334a  or      eax, 80070000h
0x18000334f  mov     edx, 59h ; 'Y'
0x180003354  mov     r9d, eax
0x180003357  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000335e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003365  mov     rcx, [rcx+10h]
0x180003369  call    WPP_SF_d
0x18000336e  nop
0x18000336f  mov     rcx, [rsp+68h+var_30]
0x180003374  xor     rcx, rsp; StackCookie
0x180003377  call    __security_check_cookie
0x18000337c  add     rsp, 40h
0x180003380  pop     r14
0x180003382  pop     rdi
0x180003383  pop     rsi
0x180003384  pop     rbp
0x180003385  pop     rbx
0x180003386  retn
```
