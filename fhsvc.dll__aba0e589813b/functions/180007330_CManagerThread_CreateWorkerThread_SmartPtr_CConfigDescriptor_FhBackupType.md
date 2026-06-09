# CManagerThread::CreateWorkerThread(SmartPtr<CConfigDescriptor>,FhBackupType)

- ea: `0x180007330`
- end: `0x18000763b`
- name: `?CreateWorkerThread@CManagerThread@@AEAAJV?$SmartPtr@VCConfigDescriptor@@@@W4FhBackupType@@@Z`
- size: `779`
- prototype: `__int64 __fastcall(__int64, struct _FILETIME ***, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003f00`

## callees

- `0x180004e50`
- `0x180004e80`
- `0x180006dd0`
- `0x180007330`
- `0x180009af0`
- `0x18000bc98`
- `0x18000bcc4`
- `0x18000bd64`
- `0x18000cadc`
- `0x18000d910`
- `0x18000f670`
- `0x180010158`
- `0x1800101e0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000751f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000751f`

## pseudocode

```c
__int64 __fastcall CManagerThread::CreateWorkerThread(__int64 a1, struct _FILETIME ***a2, unsigned int a3)
{
  struct _FILETIME *v6; // rdx
  unsigned int dwLowDateTime; // eax
  struct _FILETIME **v8; // rax
  struct _FILETIME *v9; // rcx
  _QWORD *v10; // r10
  __int64 v11; // rdx
  CWorkerThread *v12; // rax
  CWorkerThread *v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // edi
  struct _FILETIME **v17; // rcx
  struct _FILETIME **v18; // rcx
  struct _FILETIME *v19; // rax
  struct _FILETIME **v20; // rax
  struct _FILETIME *v21; // rcx
  struct _FILETIME **v22; // rcx
  __int64 v23; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp+8h] BYREF
  struct _FILETIME **v26; // [rsp+58h] [rbp+10h] BYREF

  v6 = **a2;
  dwLowDateTime = v6[18].dwLowDateTime;
  if ( dwLowDateTime > 8 )
  {
    v6[18].dwLowDateTime = dwLowDateTime | 0x100;
    v8 = *a2;
    SystemTimeAsFileTime = (struct _FILETIME)v8;
    if ( v8 )
      ++*((_DWORD *)v8 + 2);
    CManagerThread::PublishProtectionState(a1, &SystemTimeAsFileTime);
  }
  v9 = **a2;
  v9[11].dwLowDateTime = a3;
  if ( a3 == 1 )
  {
    *(_QWORD *)&v9[11].dwHighDateTime = 2;
    v9[13] = (struct _FILETIME)-1LL;
    v9[14] = (struct _FILETIME)-1LL;
    v9[15] = (struct _FILETIME)-1LL;
    v9[16] = (struct _FILETIME)-1LL;
    if ( LOBYTE(v9[18].dwLowDateTime) == 0xF0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_19;
      v11 = 25;
    }
    else
    {
      if ( v9[19].dwLowDateTime || v9[18].dwHighDateTime )
      {
        v9[14] = v9[7];
        v9[15] = v9[8];
        v9[16] = v9[9];
        goto LABEL_19;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_19;
      v11 = 26;
    }
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_S)(
      v10[2],
      v11,
      &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
      *v9);
    goto LABEL_19;
  }
  if ( a3 - 2 <= 1 )
  {
    v9[11].dwHighDateTime = 2;
    v9[12].dwLowDateTime = v9[10].dwLowDateTime;
    v9[13] = (struct _FILETIME)-1LL;
    v9[14] = (struct _FILETIME)-1LL;
    v9[15] = (struct _FILETIME)-1LL;
    v9[16] = (struct _FILETIME)-1LL;
  }
LABEL_19:
  v12 = (CWorkerThread *)operator new(0x60u);
  if ( v12 )
    v13 = CWorkerThread::CWorkerThread(v12);
  else
    v13 = 0;
  SmartPtr<CWorkerThread>::operator=(&(**a2)[17], v13);
  if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))McTemplateU0zq_EventWriteTransfer)(v15, v14, ***a2, a3);
  v16 = CWorkerThread::Create(
          **(LPVOID ***)&(**a2)[17],
          *(HANDLE *)&(**a2)[1],
          a3,
          (**a2)[10].dwHighDateTime,
          (struct _TP_CALLBACK_ENVIRON_V3 *)(a1 + 136),
          *(void **)(a1 + 248));
  v17 = *a2;
  (**a2)[10].dwHighDateTime = 0;
  if ( v16 < 0 )
  {
    if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))McTemplateU0z_EventWriteTransfer)(v17, BackupCycleStop, ***a2);
    v21 = **a2;
    v21[18].dwLowDateTime &= ~0x100u;
    CManagerThread::MapHrToProtectionState((CManagerThread *)v21, v16, (unsigned int *)&(**a2)[18]);
    v22 = *a2;
    SystemTimeAsFileTime = (struct _FILETIME)v22;
    if ( v22 )
      ++*((_DWORD *)v22 + 2);
    CManagerThread::PublishProtectionState(v22, &SystemTimeAsFileTime);
    if ( (unsigned int)(v16 + 2147219967) <= 2 )
    {
      (**a2)[5].dwLowDateTime = 1;
      v23 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &SystemTimeAsFileTime,
              **a2);
      CManagerThread::AddRemoveRegisteredConfig(a1, v23, 0);
    }
    SmartPtr<CWorkerThread>::operator=(&(**a2)[17], 0);
    (**a2)[11].dwLowDateTime = 0;
  }
  else
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    (**a2)[4] = SystemTimeAsFileTime;
    v18 = *a2;
    v19 = **a2;
    if ( v19[18].dwLowDateTime <= 8 )
    {
      v19[18].dwLowDateTime = 511;
      v20 = *a2;
      v26 = v20;
      if ( v20 )
        ++*((_DWORD *)v20 + 2);
      CManagerThread::PublishProtectionState(v18, &v26);
    }
  }
  if ( *a2 )
    SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(*a2);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180007330  mov     [rsp+arg_10], rbx
0x180007335  push    rbp
0x180007336  push    rsi
0x180007337  push    rdi
0x180007338  sub     rsp, 30h
0x18000733c  mov     edi, r8d
0x18000733f  mov     rbx, rdx
0x180007342  mov     rsi, rcx
0x180007345  mov     rax, [rdx]
0x180007348  mov     rdx, [rax]
0x18000734b  mov     eax, [rdx+90h]
0x180007351  cmp     eax, 8
0x180007354  jbe     short loc_18000737A
0x180007356  bts     eax, 8
0x18000735a  mov     [rdx+90h], eax
0x180007360  mov     rax, [rbx]
0x180007363  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180007368  test    rax, rax
0x18000736b  jz      short loc_180007370
0x18000736d  inc     dword ptr [rax+8]
0x180007370  lea     rdx, [rsp+48h+SystemTimeAsFileTime]
0x180007375  call    ?PublishProtectionState@CManagerThread@@AEAAXV?$SmartPtr@VCConfigDescriptor@@@@@Z; CManagerThread::PublishProtectionState(SmartPtr<CConfigDescriptor>)
0x18000737a  mov     rax, [rbx]
0x18000737d  mov     rcx, [rax]
0x180007380  mov     [rcx+58h], edi
0x180007383  mov     eax, edi
0x180007385  xor     ebp, ebp
0x180007387  sub     eax, 1
0x18000738a  jz      short loc_1800073CF
0x18000738c  sub     eax, 1
0x18000738f  jz      short loc_18000739A
0x180007391  cmp     eax, 1
0x180007394  jnz     loc_180007483
0x18000739a  mov     dword ptr [rcx+5Ch], 2
0x1800073a1  mov     eax, [rcx+50h]
0x1800073a4  mov     [rcx+60h], eax
0x1800073a7  mov     qword ptr [rcx+68h], 0FFFFFFFFFFFFFFFFh
0x1800073af  mov     qword ptr [rcx+70h], 0FFFFFFFFFFFFFFFFh
0x1800073b7  mov     qword ptr [rcx+78h], 0FFFFFFFFFFFFFFFFh
0x1800073bf  mov     qword ptr [rcx+80h], 0FFFFFFFFFFFFFFFFh
0x1800073ca  jmp     loc_180007483
0x1800073cf  mov     qword ptr [rcx+5Ch], 2
0x1800073d7  mov     qword ptr [rcx+68h], 0FFFFFFFFFFFFFFFFh
0x1800073df  mov     qword ptr [rcx+70h], 0FFFFFFFFFFFFFFFFh
0x1800073e7  mov     qword ptr [rcx+78h], 0FFFFFFFFFFFFFFFFh
0x1800073ef  mov     qword ptr [rcx+80h], 0FFFFFFFFFFFFFFFFh
0x1800073fa  cmp     byte ptr [rcx+90h], 0F0h
0x180007401  jnz     short loc_180007424
0x180007403  lea     rax, WPP_GLOBAL_Control
0x18000740a  mov     r10, cs:WPP_GLOBAL_Control
0x180007411  cmp     r10, rax
0x180007414  jz      short loc_180007483
0x180007416  test    byte ptr [r10+1Ch], 2
0x18000741b  jz      short loc_180007483
0x18000741d  mov     edx, 19h
0x180007422  jmp     short loc_180007453
0x180007424  cmp     [rcx+98h], ebp
0x18000742a  jnz     short loc_180007468
0x18000742c  cmp     [rcx+94h], ebp
0x180007432  jnz     short loc_180007468
0x180007434  lea     rax, WPP_GLOBAL_Control
0x18000743b  mov     r10, cs:WPP_GLOBAL_Control
0x180007442  cmp     r10, rax
0x180007445  jz      short loc_180007483
0x180007447  test    byte ptr [r10+1Ch], 2
0x18000744c  jz      short loc_180007483
0x18000744e  mov     edx, 1Ah
0x180007453  mov     r9, [rcx]
0x180007456  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000745d  mov     rcx, [r10+10h]
0x180007461  call    WPP_SF_S
0x180007466  jmp     short loc_180007483
0x180007468  mov     rax, [rcx+38h]
0x18000746c  mov     [rcx+70h], rax
0x180007470  mov     rax, [rcx+40h]
0x180007474  mov     [rcx+78h], rax
0x180007478  mov     rax, [rcx+48h]
0x18000747c  mov     [rcx+80h], rax
0x180007483  mov     ecx, 60h ; '`'; Size
0x180007488  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000748d  test    rax, rax
0x180007490  jz      short loc_18000749F
0x180007492  mov     rcx, rax; this
0x180007495  call    ??0CWorkerThread@@QEAA@XZ; CWorkerThread::CWorkerThread(void)
0x18000749a  mov     rdx, rax
0x18000749d  jmp     short loc_1800074A2
0x18000749f  mov     rdx, rbp
0x1800074a2  mov     rax, [rbx]
0x1800074a5  mov     rcx, [rax]
0x1800074a8  add     rcx, 88h
0x1800074af  call    ??4?$SmartPtr@VCWorkerThread@@@@QEAAAEAV0@PEAVCWorkerThread@@@Z; SmartPtr<CWorkerThread>::operator=(CWorkerThread *)
0x1800074b4  test    cs:Microsoft_Windows_FileHistory_ServiceEnableBits, 1
0x1800074bb  jz      short loc_1800074CE
0x1800074bd  mov     rax, [rbx]
0x1800074c0  mov     r8, [rax]
0x1800074c3  mov     r9d, edi
0x1800074c6  mov     r8, [r8]
0x1800074c9  call    McTemplateU0zq_EventWriteTransfer
0x1800074ce  mov     rax, [rbx]
0x1800074d1  mov     rdx, [rax]
0x1800074d4  lea     r8, [rsi+88h]
0x1800074db  mov     rcx, [rdx+88h]
0x1800074e2  mov     rax, [rsi+0F8h]
0x1800074e9  mov     [rsp+48h+var_20], rax; void *
0x1800074ee  mov     [rsp+48h+var_28], r8; struct _TP_CALLBACK_ENVIRON_V3 *
0x1800074f3  mov     r9d, [rdx+54h]; unsigned int
0x1800074f7  mov     r8d, edi; unsigned int
0x1800074fa  mov     rdx, [rdx+8]; hSourceHandle
0x1800074fe  mov     rcx, [rcx]; ppv
0x180007501  call    ?Create@CWorkerThread@@QEAAJPEAXKKPEAU_TP_CALLBACK_ENVIRON_V3@@0@Z; CWorkerThread::Create(void *,ulong,ulong,_TP_CALLBACK_ENVIRON_V3 *,void *)
0x180007506  mov     edi, eax
0x180007508  mov     rcx, [rbx]
0x18000750b  mov     rdx, [rcx]
0x18000750e  mov     [rdx+54h], ebp
0x180007511  test    eax, eax
0x180007513  js      short loc_180007570
0x180007515  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], rbp
0x18000751a  lea     rcx, [rsp+48h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000751f  call    cs:__imp_GetSystemTimeAsFileTime
0x180007525  mov     rcx, qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime]
0x18000752a  mov     rdx, [rbx]
0x18000752d  mov     r8, [rdx]
0x180007530  mov     [r8+20h], rcx
0x180007534  mov     rcx, [rbx]
0x180007537  mov     rax, [rcx]
0x18000753a  cmp     dword ptr [rax+90h], 8
0x180007541  ja      loc_18000761F
0x180007547  mov     dword ptr [rax+90h], 1FFh
0x180007551  mov     rax, [rbx]
0x180007554  mov     [rsp+48h+arg_8], rax
0x180007559  test    rax, rax
0x18000755c  jz      short loc_180007561
0x18000755e  inc     dword ptr [rax+8]
0x180007561  lea     rdx, [rsp+48h+arg_8]
0x180007566  call    ?PublishProtectionState@CManagerThread@@AEAAXV?$SmartPtr@VCConfigDescriptor@@@@@Z; CManagerThread::PublishProtectionState(SmartPtr<CConfigDescriptor>)
0x18000756b  jmp     loc_18000761F
0x180007570  test    cs:Microsoft_Windows_FileHistory_ServiceEnableBits, 1
0x180007577  jz      short loc_18000758E
0x180007579  mov     rax, [rbx]
0x18000757c  mov     r8, [rax]
0x18000757f  mov     r8, [r8]
0x180007582  lea     rdx, BackupCycleStop
0x180007589  call    McTemplateU0z_EventWriteTransfer
0x18000758e  mov     rax, [rbx]
0x180007591  mov     rcx, [rax]; this
0x180007594  and     dword ptr [rcx+90h], 0FFFFFEFFh
0x18000759e  mov     rax, [rbx]
0x1800075a1  mov     r8, [rax]
0x1800075a4  add     r8, 90h; unsigned int *
0x1800075ab  mov     edx, edi; int
0x1800075ad  call    ?MapHrToProtectionState@CManagerThread@@AEAAHJPEAK@Z; CManagerThread::MapHrToProtectionState(long,ulong *)
0x1800075b2  mov     rcx, [rbx]
0x1800075b5  mov     qword ptr [rsp+48h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x1800075ba  test    rcx, rcx
0x1800075bd  jz      short loc_1800075C2
0x1800075bf  inc     dword ptr [rcx+8]
0x1800075c2  lea     rdx, [rsp+48h+SystemTimeAsFileTime]
0x1800075c7  call    ?PublishProtectionState@CManagerThread@@AEAAXV?$SmartPtr@VCConfigDescriptor@@@@@Z; CManagerThread::PublishProtectionState(SmartPtr<CConfigDescriptor>)
0x1800075cc  lea     eax, [rdi+7FFBF9FFh]
0x1800075d2  cmp     eax, 2
0x1800075d5  ja      short loc_180007602
0x1800075d7  mov     rax, [rbx]
0x1800075da  mov     rcx, [rax]
0x1800075dd  mov     dword ptr [rcx+28h], 1
0x1800075e4  mov     rdx, [rbx]
0x1800075e7  mov     rdx, [rdx]
0x1800075ea  lea     rcx, [rsp+48h+SystemTimeAsFileTime]
0x1800075ef  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800075f4  mov     rdx, rax
0x1800075f7  xor     r8d, r8d
0x1800075fa  mov     rcx, rsi
0x1800075fd  call    ?AddRemoveRegisteredConfig@CManagerThread@@AEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; CManagerThread::AddRemoveRegisteredConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int)
0x180007602  mov     rax, [rbx]
0x180007605  mov     rcx, [rax]
0x180007608  add     rcx, 88h
0x18000760f  xor     edx, edx
0x180007611  call    ??4?$SmartPtr@VCWorkerThread@@@@QEAAAEAV0@PEAVCWorkerThread@@@Z; SmartPtr<CWorkerThread>::operator=(CWorkerThread *)
0x180007616  mov     rax, [rbx]
0x180007619  mov     rcx, [rax]
0x18000761c  mov     [rcx+58h], ebp
0x18000761f  mov     rcx, [rbx]
0x180007622  test    rcx, rcx
0x180007625  jz      short loc_18000762C
0x180007627  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ; SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)
0x18000762c  mov     eax, edi
0x18000762e  mov     rbx, [rsp+48h+arg_10]
0x180007633  add     rsp, 30h
0x180007637  pop     rdi
0x180007638  pop     rsi
0x180007639  pop     rbp
0x18000763a  retn
```
