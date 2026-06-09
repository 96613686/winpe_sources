# CNDFHelperClass::GetRepairsForRootCause(_GUID,__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 * *,ulong *)

- ea: `0x18000df80`
- end: `0x18000e11d`
- name: `?GetRepairsForRootCause@CNDFHelperClass@@UEAAJU_GUID@@PEAPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@PEAK@Z`
- size: `413`
- prototype: `__int64 __fastcall(CNDFHelperClass *__hidden this, struct _GUID *__struct_ptr, struct __MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18000bb4c`
- `0x18000ca20`
- `0x18000df80`
- `0x18000fe80`
- `0x1800113ac`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000dfa6`
- `KERNEL32!EnterCriticalSection` at `0x18000dfa6`
- `KERNEL32!LeaveCriticalSection` at `0x18000dfcc`
- `KERNEL32!LeaveCriticalSection` at `0x18000dfe0`
- `KERNEL32!LeaveCriticalSection` at `0x18000dfcc`
- `KERNEL32!LeaveCriticalSection` at `0x18000dfe0`

## pseudocode

```c
__int64 __fastcall CNDFHelperClass::GetRepairsForRootCause(
        struct _RTL_CRITICAL_SECTION *this,
        struct _GUID *a2,
        LPVOID **a3,
        unsigned int *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  int GUIDVar; // ebx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  struct _RTL_CRITICAL_SECTION *CriticalSection; // rcx
  unsigned int Data1; // r8d
  PRTL_CRITICAL_SECTION_DEBUG v13; // rbx
  unsigned int v14; // eax
  bool v15; // cf
  unsigned int v16; // eax
  DWORD ContentionCount; // eax
  bool v18; // cf
  DWORD Flags; // eax
  struct _RTL_CRITICAL_SECTION_DEBUG *Flink; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG *v21; // rcx
  __int128 v23; // [rsp+20h] [rbp-48h] BYREF
  __int64 v24; // [rsp+30h] [rbp-38h]

  v4 = this + 8;
  EnterCriticalSection(this + 8);
  if ( LODWORD(this[5].SpinCount) || (GUIDVar = CNDFHelperClass::InitializeRRMap((CNDFHelperClass *)this), GUIDVar >= 0) )
  {
    LeaveCriticalSection(v4);
    DebugInfo = this[6].DebugInfo;
    v23 = 0;
    v24 = 0;
    CriticalSection = DebugInfo->CriticalSection;
    if ( BYTE1(CriticalSection->LockSemaphore) )
      goto LABEL_23;
    Data1 = a2->Data1;
    v13 = DebugInfo;
    while ( 1 )
    {
      if ( LODWORD(CriticalSection->SpinCount) == Data1 )
      {
        v14 = *(_DWORD *)&a2->Data2;
        v15 = HIDWORD(CriticalSection->SpinCount) < v14;
        if ( HIDWORD(CriticalSection->SpinCount) == v14 )
        {
          v16 = *(_DWORD *)a2->Data4;
          v15 = LODWORD(CriticalSection[1].DebugInfo) < v16;
          if ( LODWORD(CriticalSection[1].DebugInfo) == v16 )
            v15 = HIDWORD(CriticalSection[1].DebugInfo) < *(_DWORD *)&a2->Data4[4];
        }
        if ( !v15 )
        {
LABEL_21:
          v13 = (PRTL_CRITICAL_SECTION_DEBUG)CriticalSection;
          CriticalSection = (struct _RTL_CRITICAL_SECTION *)CriticalSection->DebugInfo;
          goto LABEL_12;
        }
      }
      else if ( LODWORD(CriticalSection->SpinCount) >= Data1 )
      {
        goto LABEL_21;
      }
      CriticalSection = (struct _RTL_CRITICAL_SECTION *)CriticalSection->OwningThread;
LABEL_12:
      if ( BYTE1(CriticalSection->LockSemaphore) )
      {
        if ( v13 != DebugInfo )
        {
          if ( Data1 == v13->EntryCount )
          {
            ContentionCount = v13->ContentionCount;
            v18 = *(_DWORD *)&a2->Data2 < ContentionCount;
            if ( *(_DWORD *)&a2->Data2 == ContentionCount )
            {
              Flags = v13->Flags;
              v18 = *(_DWORD *)a2->Data4 < Flags;
              if ( *(_DWORD *)a2->Data4 == Flags )
                v18 = *(_DWORD *)&a2->Data4[4] < *(_DWORD *)&v13->CreatorBackTraceIndexHigh;
            }
            if ( !v18 )
            {
              while ( 1 )
              {
                do
                {
LABEL_24:
                  if ( v13 == this[6].DebugInfo
                    || *(_QWORD *)&a2->Data1 != *(_QWORD *)&v13->EntryCount
                    || *(_QWORD *)a2->Data4 != *(_QWORD *)&v13->Flags )
                  {
                    GUIDVar = TDataGetter<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004,GUIDVarInfo const,std::vector<GUIDVarInfo>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<GUIDVarInfo>>>,TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,&void FreeHelperBasicRootCauseInfos(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,unsigned long,int)>,&long TCopyAndAllocateGUIDVarInfo<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004>(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,GUIDVarInfo const *)>(
                                a3,
                                a4,
                                (__int64 *)&v23);
                    std::vector<GUIDVarInfo>::~vector<GUIDVarInfo>(&v23);
                    return (unsigned int)GUIDVar;
                  }
                  std::vector<GUIDVarInfo>::push_back(&v23, *(_QWORD *)&v13[1].Type);
                }
                while ( BYTE1(v13->ProcessLocksList.Blink) );
                Flink = (struct _RTL_CRITICAL_SECTION_DEBUG *)v13->ProcessLocksList.Flink;
                if ( BYTE1(Flink->ProcessLocksList.Blink) )
                {
                  for ( Flink = (struct _RTL_CRITICAL_SECTION_DEBUG *)v13->CriticalSection;
                        !BYTE1(Flink->ProcessLocksList.Blink)
                     && v13 == (PRTL_CRITICAL_SECTION_DEBUG)Flink->ProcessLocksList.Flink;
                        Flink = (struct _RTL_CRITICAL_SECTION_DEBUG *)Flink->CriticalSection )
                  {
                    v13 = Flink;
                  }
                }
                else
                {
                  v21 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&Flink->Type;
                  if ( !*(_BYTE *)(*(_QWORD *)&Flink->Type + 25LL) )
                  {
                    do
                    {
                      v13 = v21;
                      v21 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&v21->Type;
                    }
                    while ( !BYTE1(v21->ProcessLocksList.Blink) );
                    goto LABEL_24;
                  }
                }
                v13 = Flink;
              }
            }
          }
          else if ( Data1 >= v13->EntryCount )
          {
            goto LABEL_24;
          }
        }
LABEL_23:
        v13 = DebugInfo;
        goto LABEL_24;
      }
    }
  }
  LeaveCriticalSection(v4);
  return (unsigned int)GUIDVar;
}

```

## disassembly

```asm
0x18000df80  mov     [rsp+arg_8], rbx
0x18000df85  push    rbp
0x18000df86  push    rsi
0x18000df87  push    rdi
0x18000df88  push    r14
0x18000df8a  push    r15
0x18000df8c  sub     rsp, 40h
0x18000df90  lea     rdi, [rcx+140h]
0x18000df97  mov     rbp, rcx
0x18000df9a  mov     rcx, rdi; lpCriticalSection
0x18000df9d  mov     r15, r9
0x18000dfa0  mov     r14, r8
0x18000dfa3  mov     rsi, rdx
0x18000dfa6  call    cs:__imp_EnterCriticalSection
0x18000dfad  nop     dword ptr [rax+rax+00h]
0x18000dfb2  cmp     dword ptr [rbp+0E8h], 0
0x18000dfb9  jnz     short loc_18000DFDD
0x18000dfbb  mov     rcx, rbp; this
0x18000dfbe  call    ?InitializeRRMap@CNDFHelperClass@@AEAAJXZ; CNDFHelperClass::InitializeRRMap(void)
0x18000dfc3  mov     ebx, eax
0x18000dfc5  test    eax, eax
0x18000dfc7  jns     short loc_18000DFDD
0x18000dfc9  mov     rcx, rdi; lpCriticalSection
0x18000dfcc  call    cs:__imp_LeaveCriticalSection
0x18000dfd3  nop     dword ptr [rax+rax+00h]
0x18000dfd8  jmp     loc_18000E109
0x18000dfdd  mov     rcx, rdi; lpCriticalSection
0x18000dfe0  call    cs:__imp_LeaveCriticalSection
0x18000dfe7  nop     dword ptr [rax+rax+00h]
0x18000dfec  mov     rdx, [rbp+0F0h]
0x18000dff3  xorps   xmm0, xmm0
0x18000dff6  movdqu  [rsp+68h+var_48], xmm0
0x18000dffc  mov     [rsp+68h+var_38], 0
0x18000e005  mov     rcx, [rdx+8]
0x18000e009  cmp     byte ptr [rcx+19h], 0
0x18000e00d  jnz     short loc_18000E078
0x18000e00f  mov     r8d, [rsi]
0x18000e012  mov     rbx, rdx
0x18000e015  cmp     [rcx+20h], r8d
0x18000e019  jnz     short loc_18000E06C
0x18000e01b  mov     eax, [rsi+4]
0x18000e01e  cmp     [rcx+24h], eax
0x18000e021  jnz     short loc_18000E031
0x18000e023  mov     eax, [rsi+8]
0x18000e026  cmp     [rcx+28h], eax
0x18000e029  jnz     short loc_18000E031
0x18000e02b  mov     eax, [rsi+0Ch]
0x18000e02e  cmp     [rcx+2Ch], eax
0x18000e031  setb    al
0x18000e034  test    al, al
0x18000e036  jz      short loc_18000E06E
0x18000e038  mov     rcx, [rcx+10h]
0x18000e03c  cmp     byte ptr [rcx+19h], 0
0x18000e040  jz      short loc_18000E015
0x18000e042  cmp     rbx, rdx
0x18000e045  jz      short loc_18000E078
0x18000e047  cmp     r8d, [rbx+20h]
0x18000e04b  jnz     short loc_18000E076
0x18000e04d  mov     eax, [rbx+24h]
0x18000e050  cmp     [rsi+4], eax
0x18000e053  jnz     short loc_18000E063
0x18000e055  mov     eax, [rbx+28h]
0x18000e058  cmp     [rsi+8], eax
0x18000e05b  jnz     short loc_18000E063
0x18000e05d  mov     eax, [rbx+2Ch]
0x18000e060  cmp     [rsi+0Ch], eax
0x18000e063  setb    al
0x18000e066  test    al, al
0x18000e068  jnz     short loc_18000E078
0x18000e06a  jmp     short loc_18000E07B
0x18000e06c  jb      short loc_18000E038
0x18000e06e  mov     rbx, rcx
0x18000e071  mov     rcx, [rcx]
0x18000e074  jmp     short loc_18000E03C
0x18000e076  jnb     short loc_18000E07B
0x18000e078  mov     rbx, rdx
0x18000e07b  cmp     rbx, [rbp+0F0h]
0x18000e082  jz      short loc_18000E0ED
0x18000e084  mov     rax, [rsi]
0x18000e087  cmp     rax, [rbx+20h]
0x18000e08b  jnz     short loc_18000E0ED
0x18000e08d  mov     rax, [rsi+8]
0x18000e091  cmp     rax, [rbx+28h]
0x18000e095  jnz     short loc_18000E0ED
0x18000e097  mov     rdx, [rbx+30h]
0x18000e09b  lea     rcx, [rsp+68h+var_48]
0x18000e0a0  call    ?push_back@?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@QEAAXAEBUGUIDVarInfo@@@Z; std::vector<GUIDVarInfo>::push_back(GUIDVarInfo const &)
0x18000e0a5  cmp     byte ptr [rbx+19h], 0
0x18000e0a9  jnz     short loc_18000E07B
0x18000e0ab  mov     rax, [rbx+10h]
0x18000e0af  cmp     byte ptr [rax+19h], 0
0x18000e0b3  jnz     short loc_18000E0CF
0x18000e0b5  mov     rcx, [rax]
0x18000e0b8  cmp     byte ptr [rcx+19h], 0
0x18000e0bc  jnz     short loc_18000E0E8
0x18000e0be  mov     rax, [rcx]
0x18000e0c1  mov     rbx, rcx
0x18000e0c4  mov     rcx, rax
0x18000e0c7  cmp     byte ptr [rax+19h], 0
0x18000e0cb  jz      short loc_18000E0BE
0x18000e0cd  jmp     short loc_18000E07B
0x18000e0cf  mov     rax, [rbx+8]
0x18000e0d3  jmp     short loc_18000E0E2
0x18000e0d5  cmp     rbx, [rax+10h]
0x18000e0d9  jnz     short loc_18000E0E8
0x18000e0db  mov     rbx, rax
0x18000e0de  mov     rax, [rax+8]
0x18000e0e2  cmp     byte ptr [rax+19h], 0
0x18000e0e6  jz      short loc_18000E0D5
0x18000e0e8  mov     rbx, rax
0x18000e0eb  jmp     short loc_18000E07B
0x18000e0ed  lea     r8, [rsp+68h+var_48]
0x18000e0f2  mov     rdx, r15
0x18000e0f5  mov     rcx, r14
0x18000e0f8  call    ??$TDataGetter@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@$$CBUGUIDVarInfo@@V?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UGUIDVarInfo@@@std@@@std@@@4@V?$TNDFDeallocator@PEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@$1?FreeHelperBasicRootCauseInfos@@YAXPEAU1@KH@Z@@$1??$TCopyAndAllocateGUIDVarInfo@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@@@YAJPEAU1@PEBU2@@Z@@YAJPEAPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@PEAKAEAV?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@@Z; TDataGetter<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004,GUIDVarInfo const,std::vector<GUIDVarInfo>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<GUIDVarInfo>>>,TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,&FreeHelperBasicRootCauseInfos(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,ulong,int)>,&TCopyAndAllocateGUIDVarInfo<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004>(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,GUIDVarInfo const *)>(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 * *,ulong *,std::vector<GUIDVarInfo> &)
0x18000e0fd  lea     rcx, [rsp+68h+var_48]
0x18000e102  mov     ebx, eax
0x18000e104  call    ??1?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@QEAA@XZ; std::vector<GUIDVarInfo>::~vector<GUIDVarInfo>(void)
0x18000e109  mov     eax, ebx
0x18000e10b  mov     rbx, [rsp+68h+arg_8]
0x18000e110  add     rsp, 40h
0x18000e114  pop     r15
0x18000e116  pop     r14
0x18000e118  pop     rdi
0x18000e119  pop     rsi
0x18000e11a  pop     rbp
0x18000e11b  retn
```
