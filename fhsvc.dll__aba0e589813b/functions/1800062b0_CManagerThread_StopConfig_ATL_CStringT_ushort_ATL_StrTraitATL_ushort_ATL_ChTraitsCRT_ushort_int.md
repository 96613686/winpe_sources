# CManagerThread::StopConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int)

- ea: `0x1800062b0`
- end: `0x1800065ba`
- name: `?StopConfig@CManagerThread@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z`
- size: `778`
- prototype: `__int64 __fastcall(_QWORD **, _QWORD *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800096c0`
- `0x18000e8b0`

## callees

- `0x180004e30`
- `0x180004e50`
- `0x1800062b0`
- `0x180007300`
- `0x180009af0`
- `0x18000aa08`
- `0x18000bc98`
- `0x18000ca14`
- `0x18000d970`
- `0x1800109d4`
- `0x180013010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180006570`
- `KERNEL32!SetEvent` at `0x180006570`
- `KERNEL32!EnterCriticalSection` at `0x1800062d0`
- `KERNEL32!EnterCriticalSection` at `0x1800062d0`
- `KERNEL32!LeaveCriticalSection` at `0x18000657d`
- `KERNEL32!LeaveCriticalSection` at `0x18000657d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000644c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800064b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000651b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000644c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800064b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000651b`

## pseudocode

```c
__int64 __fastcall CManagerThread::StopConfig(_QWORD **a1, _QWORD *a2, int a3)
{
  _QWORD *v5; // rdi
  int ConfigDescriptor; // r15d
  __int64 v7; // r8
  __int64 v8; // r9
  _QWORD *v9; // rsi
  __int64 v10; // rdx
  __int64 i; // rcx
  bool v12; // zf
  _QWORD **v13; // rbx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  CWorkerThread **v16; // rdx
  CWorkerThread *v17; // rcx
  LPCWSTR *v18; // rax
  unsigned int v19; // edx
  _QWORD *v20; // rcx
  int v21; // edx
  unsigned int v22; // edx
  unsigned int v23; // edx
  volatile signed __int32 *v24; // rdx
  _QWORD **v26; // [rsp+70h] [rbp+8h] BYREF
  __int64 v27; // [rsp+78h] [rbp+10h] BYREF
  __int64 v28; // [rsp+88h] [rbp+20h] BYREF

  v26 = a1;
  EnterCriticalSection(&CriticalSection);
  v5 = (_QWORD *)xmmword_1800198F0;
  if ( (_QWORD)xmmword_1800198F0 && (_QWORD)xmmword_1800198F0 != qword_180019918 )
  {
    while ( v5[3] != qword_180019918 )
      v5 = (_QWORD *)v5[3];
    if ( v5 )
    {
      ConfigDescriptor = 0;
      while ( 1 )
      {
        SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v26);
        if ( *(_DWORD *)(*a2 - 16LL) )
        {
          v14 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                  &v27,
                  a2);
          ConfigDescriptor = CManagerThread::GetConfigDescriptor(v15, v14, &v26, 0);
          if ( ConfigDescriptor < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                61,
                (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
                0,
                ConfigDescriptor);
            SysFreeString(0);
            if ( v26 )
              SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs((__int64)v26, v23);
            goto LABEL_49;
          }
          v13 = v26;
        }
        else
        {
          v9 = v5;
          v10 = v5[4];
          if ( v10 == qword_180019918 )
          {
            for ( i = v5[5]; ; i = *(_QWORD *)(i + 40) )
            {
              v12 = i == qword_180019918;
              if ( i == qword_180019918 )
                break;
              if ( v5 != *(_QWORD **)(i + 32) )
              {
                v12 = i == qword_180019918;
                break;
              }
              v5 = (_QWORD *)i;
            }
            v5 = 0;
            if ( !v12 )
              v5 = (_QWORD *)i;
          }
          else
          {
            v5 = (_QWORD *)ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(
                             (__int64)&xmmword_1800198F0,
                             v10);
          }
          v13 = v26;
          if ( v26 != (_QWORD **)v9[1] )
          {
            if ( v26 )
              SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs((__int64)v26, v10);
            v13 = (_QWORD **)v9[1];
            v26 = v13;
            if ( v13 )
              ++*((_DWORD *)v13 + 2);
          }
        }
        *((_DWORD *)*v13 + 5) = 0;
        *((_DWORD *)*v13 + 6) = 0;
        v16 = (CWorkerThread **)(*v13)[17];
        if ( v16 )
        {
          v17 = *v16;
          if ( *v16 )
          {
            if ( !*((_DWORD *)v17 + 12) )
            {
              ConfigDescriptor = CWorkerThread::Stop(v17, 1, v7, v8);
              if ( ConfigDescriptor < 0 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v21 = 62;
                  goto LABEL_36;
                }
LABEL_37:
                SysFreeString(0);
                SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs((__int64)v13, v22);
                goto LABEL_49;
              }
            }
          }
        }
        if ( a3 )
        {
          *((_DWORD *)*v13 + 10) = 1;
          v18 = (LPCWSTR *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                             &v28,
                             *v13);
          ConfigDescriptor = CManagerThread::AddRemoveRegisteredConfig((__int64)&g_ManagerThread, v18, 0);
          if ( ConfigDescriptor < 0 )
          {
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v21 = 63;
LABEL_36:
              WPP_SF_Sd(
                v20[2],
                v21,
                (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
                **v13,
                ConfigDescriptor);
            }
            goto LABEL_37;
          }
        }
        SysFreeString(0);
        SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs((__int64)v13, v19);
        if ( *(_DWORD *)(*a2 - 16LL) || !v5 )
          goto LABEL_49;
      }
    }
  }
  ConfigDescriptor = -2147023728;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, 2147943568LL);
LABEL_49:
  SetEvent(hEvent);
  LeaveCriticalSection(&CriticalSection);
  v24 = (volatile signed __int32 *)(*a2 - 24LL);
  if ( _InterlockedExchangeAdd(v24 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24);
  return (unsigned int)ConfigDescriptor;
}

```

## disassembly

```asm
0x1800062b0  mov     [rsp+arg_0], rcx
0x1800062b5  push    rbx
0x1800062b6  push    rbp
0x1800062b7  push    rsi
0x1800062b8  push    rdi
0x1800062b9  push    r12
0x1800062bb  push    r14
0x1800062bd  push    r15
0x1800062bf  sub     rsp, 30h
0x1800062c3  mov     ebp, r8d
0x1800062c6  mov     r14, rdx
0x1800062c9  lea     rcx, CriticalSection; lpCriticalSection
0x1800062d0  call    cs:__imp_EnterCriticalSection
0x1800062d6  mov     rdi, qword ptr cs:xmmword_1800198F0
0x1800062dd  test    rdi, rdi
0x1800062e0  jz      loc_180006532
0x1800062e6  mov     rcx, cs:qword_180019918
0x1800062ed  cmp     rdi, rcx
0x1800062f0  jz      loc_180006532
0x1800062f6  mov     rax, [rdi+18h]
0x1800062fa  cmp     rax, rcx
0x1800062fd  jz      short loc_180006304
0x1800062ff  mov     rdi, rax
0x180006302  jmp     short loc_1800062F6
0x180006304  test    rdi, rdi
0x180006307  jz      loc_180006532
0x18000630d  xor     r12d, r12d
0x180006310  mov     r15d, r12d
0x180006313  lea     rcx, [rsp+68h+arg_0]
0x180006318  call    ??0?$SmartPtr@VCConfigDescriptor@@@@QEAA@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(CConfigDescriptor *)
0x18000631d  mov     rax, [r14]
0x180006320  cmp     [rax-10h], r12d
0x180006324  jnz     loc_1800063AA
0x18000632a  mov     rsi, rdi
0x18000632d  test    rdi, rdi
0x180006330  jnz     short loc_180006337
0x180006332  mov     rdi, r12
0x180006335  jmp     short loc_18000637F
0x180006337  mov     rax, cs:qword_180019918
0x18000633e  mov     rdx, [rdi+20h]
0x180006342  cmp     rdx, rax
0x180006345  jz      short loc_180006358
0x180006347  lea     rcx, xmmword_1800198F0
0x18000634e  call    ?Minimum@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$SmartPtr@VCConfigDescriptor@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$SmartPtr@VCConfigDescriptor@@@@@2@@ATL@@IEBAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::Minimum(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<SmartPtr<CConfigDescriptor>>>::CNode *)
0x180006353  mov     rdi, rax
0x180006356  jmp     short loc_18000637F
0x180006358  mov     rcx, [rdi+28h]
0x18000635c  cmp     rcx, rax
0x18000635f  jz      short loc_180006373
0x180006361  cmp     rdi, [rcx+20h]
0x180006365  jnz     short loc_180006370
0x180006367  mov     rdi, rcx
0x18000636a  mov     rcx, [rcx+28h]
0x18000636e  jmp     short loc_18000635C
0x180006370  cmp     rcx, rax
0x180006373  setz    al
0x180006376  mov     rdi, r12
0x180006379  test    al, al
0x18000637b  cmovz   rdi, rcx
0x18000637f  mov     rbx, [rsp+68h+arg_0]
0x180006384  cmp     rbx, [rsi+8]
0x180006388  jz      short loc_1800063D7
0x18000638a  test    rbx, rbx
0x18000638d  jz      short loc_180006397
0x18000638f  mov     rcx, rbx
0x180006392  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ; SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)
0x180006397  mov     rbx, [rsi+8]
0x18000639b  mov     [rsp+68h+arg_0], rbx
0x1800063a0  test    rbx, rbx
0x1800063a3  jz      short loc_1800063D7
0x1800063a5  inc     dword ptr [rbx+8]
0x1800063a8  jmp     short loc_1800063D7
0x1800063aa  mov     rdx, r14
0x1800063ad  lea     rcx, [rsp+68h+arg_8]
0x1800063b2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800063b7  mov     rdx, rax
0x1800063ba  xor     r9d, r9d
0x1800063bd  lea     r8, [rsp+68h+arg_0]
0x1800063c2  call    ?GetConfigDescriptor@CManagerThread@@AEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$SmartPtr@VCConfigDescriptor@@@@H@Z; CManagerThread::GetConfigDescriptor(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor> &,int)
0x1800063c7  mov     r15d, eax
0x1800063ca  test    eax, eax
0x1800063cc  js      loc_1800064E3
0x1800063d2  mov     rbx, [rsp+68h+arg_0]
0x1800063d7  mov     rcx, [rbx]
0x1800063da  mov     [rcx+14h], r12d
0x1800063de  mov     rcx, [rbx]
0x1800063e1  mov     [rcx+18h], r12d
0x1800063e5  mov     rcx, [rbx]
0x1800063e8  mov     rdx, [rcx+88h]
0x1800063ef  test    rdx, rdx
0x1800063f2  jz      short loc_180006413
0x1800063f4  mov     rcx, [rdx]; this
0x1800063f7  test    rcx, rcx
0x1800063fa  jz      short loc_180006413
0x1800063fc  cmp     [rcx+30h], r12d
0x180006400  jnz     short loc_180006413
0x180006402  mov     edx, 1; int
0x180006407  call    ?Stop@CWorkerThread@@QEAAJH@Z; CWorkerThread::Stop(int)
0x18000640c  mov     r15d, eax
0x18000640f  test    eax, eax
0x180006411  js      short loc_180006475
0x180006413  test    ebp, ebp
0x180006415  jz      short loc_18000644A
0x180006417  mov     rax, [rbx]
0x18000641a  mov     dword ptr [rax+28h], 1
0x180006421  mov     rdx, [rbx]
0x180006424  lea     rcx, [rsp+68h+arg_18]
0x18000642c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180006431  mov     rdx, rax
0x180006434  xor     r8d, r8d
0x180006437  lea     rcx, ?g_ManagerThread@@3VCManagerThread@@A; CManagerThread g_ManagerThread
0x18000643e  call    ?AddRemoveRegisteredConfig@CManagerThread@@AEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; CManagerThread::AddRemoveRegisteredConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int)
0x180006443  mov     r15d, eax
0x180006446  test    eax, eax
0x180006448  js      short loc_1800064C3
0x18000644a  xor     ecx, ecx; bstrString
0x18000644c  call    cs:__imp_SysFreeString
0x180006452  mov     rcx, rbx
0x180006455  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ; SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)
0x18000645a  mov     rax, [r14]
0x18000645d  cmp     [rax-10h], r12d
0x180006461  jnz     loc_180006569
0x180006467  test    rdi, rdi
0x18000646a  jnz     loc_180006313
0x180006470  jmp     loc_180006569
0x180006475  lea     rax, WPP_GLOBAL_Control
0x18000647c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006483  cmp     rcx, rax
0x180006486  jz      short loc_1800064AE
0x180006488  test    byte ptr [rcx+1Ch], 1
0x18000648c  jz      short loc_1800064AE
0x18000648e  mov     edx, 3Eh ; '>'
0x180006493  mov     r9, [rbx]
0x180006496  mov     [rsp+68h+var_48], r15d
0x18000649b  mov     r9, [r9]
0x18000649e  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800064a5  mov     rcx, [rcx+10h]
0x1800064a9  call    WPP_SF_Sd
0x1800064ae  xor     ecx, ecx; bstrString
0x1800064b0  call    cs:__imp_SysFreeString
0x1800064b6  mov     rcx, rbx
0x1800064b9  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ; SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)
0x1800064be  jmp     loc_180006569
0x1800064c3  lea     rax, WPP_GLOBAL_Control
0x1800064ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064d1  cmp     rcx, rax
0x1800064d4  jz      short loc_1800064AE
0x1800064d6  test    byte ptr [rcx+1Ch], 1
0x1800064da  jz      short loc_1800064AE
0x1800064dc  mov     edx, 3Fh ; '?'
0x1800064e1  jmp     short loc_180006493
0x1800064e3  lea     rax, WPP_GLOBAL_Control
0x1800064ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064f1  cmp     rcx, rax
0x1800064f4  jz      short loc_180006519
0x1800064f6  test    byte ptr [rcx+1Ch], 1
0x1800064fa  jz      short loc_180006519
0x1800064fc  mov     edx, 3Dh ; '='
0x180006501  mov     [rsp+68h+var_48], r15d
0x180006506  xor     r9d, r9d
0x180006509  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180006510  mov     rcx, [rcx+10h]
0x180006514  call    WPP_SF_Sd
0x180006519  xor     ecx, ecx; bstrString
0x18000651b  call    cs:__imp_SysFreeString
0x180006521  mov     rcx, [rsp+68h+arg_0]
0x180006526  test    rcx, rcx
0x180006529  jz      short loc_180006569
0x18000652b  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ; SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)
0x180006530  jmp     short loc_180006569
0x180006532  mov     r15d, 80070490h
0x180006538  lea     rax, WPP_GLOBAL_Control
0x18000653f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006546  cmp     rcx, rax
0x180006549  jz      short loc_180006569
0x18000654b  test    byte ptr [rcx+1Ch], 1
0x18000654f  jz      short loc_180006569
0x180006551  mov     edx, 3Ch ; '<'
0x180006556  mov     r9d, r15d
0x180006559  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180006560  mov     rcx, [rcx+10h]
0x180006564  call    WPP_SF_d
0x180006569  mov     rcx, cs:hEvent; hEvent
0x180006570  call    cs:__imp_SetEvent
0x180006576  lea     rcx, CriticalSection; lpCriticalSection
0x18000657d  call    cs:__imp_LeaveCriticalSection
0x180006583  mov     rdx, [r14]
0x180006586  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000658a  mov     eax, 0FFFFFFFFh
0x18000658f  lock xadd [rdx+10h], eax
0x180006594  sub     eax, 1
0x180006597  jg      short loc_1800065A8
0x180006599  mov     rcx, [rdx]
0x18000659c  mov     rax, [rcx]
0x18000659f  mov     rax, [rax+8]
0x1800065a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065a8  mov     eax, r15d
0x1800065ab  add     rsp, 30h
0x1800065af  pop     r15
0x1800065b1  pop     r14
0x1800065b3  pop     r12
0x1800065b5  pop     rdi
0x1800065b6  pop     rsi
0x1800065b7  pop     rbp
0x1800065b8  pop     rbx
0x1800065b9  retn
```
