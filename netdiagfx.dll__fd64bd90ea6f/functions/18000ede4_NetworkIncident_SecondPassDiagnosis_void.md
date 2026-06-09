# NetworkIncident::SecondPassDiagnosis(void)

- ea: `0x18000ede4`
- end: `0x18000f1c4`
- name: `?SecondPassDiagnosis@NetworkIncident@@AEAAJXZ`
- size: `992`
- prototype: `__int64 __fastcall(NetworkIncident *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000a3e8`

## callees

- `0x1800035a8`
- `0x1800083a0`
- `0x1800083e0`
- `0x180008cf0`
- `0x180008d38`
- `0x18000ac48`
- `0x18000bfcc`
- `0x18000d634`
- `0x18000ede4`
- `0x18000f1cc`
- `0x18000f324`
- `0x180010254`
- `0x180013938`
- `0x18001421c`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## string_xrefs

- `0x18000ef1c`: `ReconfirmLowHealth skipped for '%s', DS_PASSTHROUGH status updated to DS_REJECTED.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NetworkIncident::SecondPassDiagnosis(NetworkIncident *this)
{
  int BaseHypothesisData; // esi
  __int64 v3; // r8
  struct ProblemNode *v4; // rdi
  __int64 *v5; // rbx
  int v6; // r14d
  __int64 v7; // r9
  unsigned __int64 v8; // rcx
  _QWORD *v9; // rbx
  unsigned int i; // r14d
  enum tagDIAGNOSIS_STATUS v11; // r9d
  struct tagHypothesisResult *v12; // r13
  unsigned int v13; // r15d
  __int64 *v14; // rbx
  unsigned int j; // ecx
  enum tagDIAGNOSIS_STATUS v16; // r9d
  int v17; // r14d
  _QWORD *v18; // rbx
  __int64 v19; // rcx
  unsigned int v21; // [rsp+30h] [rbp-D0h] BYREF
  struct tagHypothesisResult *v22; // [rsp+38h] [rbp-C8h] BYREF
  struct tagHypothesisResult *v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v25; // [rsp+50h] [rbp-B0h]
  _QWORD v26[3]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h]
  __int64 v28; // [rsp+78h] [rbp-88h]
  __int64 v29; // [rsp+80h] [rbp-80h] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h]
  struct ProblemNode *v31; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v32; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v33; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v34[128]; // [rsp+B0h] [rbp-50h] BYREF

  std::queue<int>::queue<int,std::deque<int>>(v26);
  v22 = (struct tagHypothesisResult *)v26;
  BaseHypothesisData = IterateOverNodes(0, *(_QWORD *)this, &v22, QueueLeafNodesCallback, 0);
  if ( BaseHypothesisData >= 0 )
  {
    while ( v28 && BaseHypothesisData >= 0 )
    {
      std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(
        (std::_Iterator_base12 *)&v32,
        v27,
        (const struct std::_Container_base12 *)v26);
      if ( v32 )
        v3 = *v32;
      else
        v3 = 0;
      v4 = *(struct ProblemNode **)(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 8 * ((v33 >> 1) & (*(_QWORD *)(v3 + 16) - 1LL)))
                                  + 8 * (v33 & 1));
      v31 = v4;
      if ( v28 )
      {
        if ( --v28 )
          ++v27;
        else
          v27 = 0;
      }
      v5 = *(__int64 **)v4;
      if ( *(_DWORD *)(*(_QWORD *)v4 + 236LL) == 5 )
      {
        if ( *((_QWORD *)v4 + 7) )
          goto LABEL_49;
        if ( !*((_QWORD *)this + 27) )
          goto LABEL_47;
        v6 = 2;
        memset_0(v34, 0, sizeof(v34));
        v7 = v5[2];
        if ( !*(_DWORD *)(v7 - 16) )
          v7 = *v5;
        StringCchPrintfW(
          v34,
          0x80u,
          L"ReconfirmLowHealth skipped for '%s', DS_PASSTHROUGH status updated to DS_REJECTED.",
          v7);
        (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, _QWORD))(**((_QWORD **)this + 27) + 112LL))(
          *((_QWORD *)this + 27),
          0,
          v34,
          *(_QWORD *)(*(_QWORD *)v4 + 40LL));
LABEL_45:
        v17 = v6 - 1;
        if ( !v17 )
        {
          _InterlockedCompareExchange((volatile signed __int32 *)this + 22, 1, 0);
          NetworkIncident::UpdateCoveredPathAnnotation(this, v4, 0);
          goto LABEL_49;
        }
        if ( v17 == 1 )
        {
LABEL_47:
          DisconnectNodeFromDiagGraph(v4);
          *((_DWORD *)v4 + 8) = 8;
        }
LABEL_49:
        v18 = (_QWORD *)*((_QWORD *)v4 + 8);
        while ( 1 )
        {
          v18 = (_QWORD *)*v18;
          if ( v18 == *((_QWORD **)v4 + 8) )
            break;
          v19 = v18[2];
          if ( (unsigned int)(*(_DWORD *)(v19 + 96) - 10) > 1 )
          {
            *(_DWORD *)(v19 + 96) = 10;
            std::deque<ProblemNode *>::push_back(v26, v18 + 2);
          }
        }
        *((_DWORD *)v4 + 24) = 11;
        ProblemInstance::ProcessDiagFiles(*(ProblemInstance **)v4, *((struct DiagnosticsClient **)this + 10));
      }
      else
      {
        v22 = 0;
        v21 = 0;
        v23 = 0;
        v24 = 0;
        v8 = *((_QWORD *)v4 + 7);
        v25 = v8;
        if ( !v8 )
          goto LABEL_30;
        v9 = (_QWORD *)*((_QWORD *)v4 + 6);
        for ( i = 0; ; ++i )
        {
          v9 = (_QWORD *)*v9;
          if ( v9 == *((_QWORD **)v4 + 6) || BaseHypothesisData < 0 || i >= v8 )
            break;
          if ( *(_DWORD *)(v9[2] + 96LL) != 11 )
          {
            v29 = v9[2];
            v30 = 0;
            BaseHypothesisData = IterateOverNodes(1, v4, &v29, SearchForNode, 1);
            if ( BaseHypothesisData >= 0 && !(_DWORD)v30 )
            {
              std::deque<ProblemNode *>::push_back(v26, &v31);
              v4 = 0;
              break;
            }
            v8 = v25;
          }
        }
        if ( v4 )
        {
LABEL_30:
          BaseHypothesisData = GetBaseHypothesisData(&v22, &v21, v4);
          if ( BaseHypothesisData < 0 )
          {
            TNDFDeallocator<tagHypothesisResult *,&void FreeHypothesisResults(tagHypothesisResult *,unsigned long,int)>::~TNDFDeallocator<tagHypothesisResult *,&void FreeHypothesisResults(tagHypothesisResult *,unsigned long,int)>(&v23);
            break;
          }
          v6 = 0;
          v12 = v22;
          v13 = v21;
          if ( v21 )
          {
            v23 = v22;
            v24 = v21 | 0x100000000LL;
            v14 = (__int64 *)*((_QWORD *)v4 + 6);
            for ( j = 0; ; j = v21 + 1 )
            {
              v21 = j;
              v14 = (__int64 *)*v14;
              if ( v14 == *((__int64 **)v4 + 6) )
                break;
              if ( BaseHypothesisData < 0 )
                goto LABEL_44;
              if ( j >= v25 )
                goto LABEL_38;
              BaseHypothesisData = SetHypothesisResult(v12, v13, (const struct ProblemNode *)v14[2]);
            }
            if ( BaseHypothesisData < 0 )
              goto LABEL_44;
LABEL_38:
            if ( v13 )
            {
              if ( *(int *)(*(_QWORD *)v4 + 228LL) >= 0 )
              {
                v6 = ProblemInstance::SecondPassDiagnose(*(ProblemInstance **)v4, v12, v13, v11);
              }
              else
              {
                BaseHypothesisData = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 56LL))(*((_QWORD *)this + 10));
                if ( BaseHypothesisData < 0 )
                {
                  v6 = 3;
                }
                else
                {
                  v6 = ProblemInstance::SecondPassDiagnose(*(ProblemInstance **)v4, v12, v13, v16);
                  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 64LL))(*((_QWORD *)this + 10));
                }
              }
            }
          }
LABEL_44:
          TNDFDeallocator<tagHypothesisResult *,&void FreeHypothesisResults(tagHypothesisResult *,unsigned long,int)>::~TNDFDeallocator<tagHypothesisResult *,&void FreeHypothesisResults(tagHypothesisResult *,unsigned long,int)>(&v23);
          if ( BaseHypothesisData >= 0 )
            goto LABEL_45;
        }
        else
        {
          TNDFDeallocator<tagHypothesisResult *,&void FreeHypothesisResults(tagHypothesisResult *,unsigned long,int)>::~TNDFDeallocator<tagHypothesisResult *,&void FreeHypothesisResults(tagHypothesisResult *,unsigned long,int)>(&v23);
        }
      }
    }
  }
  std::deque<ProblemNode *>::~deque<ProblemNode *>((__int64)v26);
  return (unsigned int)BaseHypothesisData;
}

```

## disassembly

```asm
0x18000ede4  push    rbp
0x18000ede6  push    rbx
0x18000ede7  push    rsi
0x18000ede8  push    rdi
0x18000ede9  push    r12
0x18000edeb  push    r13
0x18000eded  push    r14
0x18000edef  push    r15
0x18000edf1  lea     rbp, [rsp-0C8h]
0x18000edf9  sub     rsp, 1C8h
0x18000ee00  mov     rax, cs:__security_cookie
0x18000ee07  xor     rax, rsp
0x18000ee0a  mov     [rbp+100h+var_50], rax
0x18000ee11  mov     r12, rcx
0x18000ee14  lea     rcx, [rsp+200h+var_1A8]
0x18000ee19  call    ??0?$queue@HV?$deque@HV?$allocator@H@std@@@std@@@std@@QEAA@XZ; std::queue<int>::queue<int,std::deque<int>>(void)
0x18000ee1e  nop
0x18000ee1f  lea     rax, [rsp+200h+var_1A8]
0x18000ee24  mov     [rsp+200h+var_1C8], rax
0x18000ee29  xor     r15d, r15d
0x18000ee2c  mov     [rsp+200h+var_1E0], r15d
0x18000ee31  lea     r9, ?QueueLeafNodesCallback@@YAJPEAVProblemNode@@PEAX@Z; QueueLeafNodesCallback(ProblemNode *,void *)
0x18000ee38  lea     r8, [rsp+200h+var_1C8]
0x18000ee3d  mov     rdx, [r12]
0x18000ee41  xor     ecx, ecx
0x18000ee43  call    ?IterateOverNodes@@YAJW4NodeIterateDirection@@PEAVProblemNode@@PEAXP6AJ12@ZH@Z; IterateOverNodes(NodeIterateDirection,ProblemNode *,void *,long (*)(ProblemNode *,void *),int)
0x18000ee48  mov     esi, eax
0x18000ee4a  test    eax, eax
0x18000ee4c  js      loc_18000F195
0x18000ee52  lea     r13d, [r15+1]
0x18000ee56  cmp     [rsp+200h+var_188], r15
0x18000ee5b  jz      loc_18000F195
0x18000ee61  test    esi, esi
0x18000ee63  js      loc_18000F195
0x18000ee69  lea     r8, [rsp+200h+var_1A8]
0x18000ee6e  mov     rdx, [rsp+200h+var_190]
0x18000ee73  lea     rcx, [rbp+100h+var_168]
0x18000ee77  call    ??0?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@PEAVProblemNode@@@std@@@std@@@std@@QEAA@_KPEBU_Container_base12@1@@Z; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(unsigned __int64,std::_Container_base12 const *)
0x18000ee7c  nop
0x18000ee7d  mov     r8, [rbp+100h+var_168]
0x18000ee81  test    r8, r8
0x18000ee84  jnz     short loc_18000EE8B
0x18000ee86  mov     r8, r15
0x18000ee89  jmp     short loc_18000EE8E
0x18000ee8b  mov     r8, [r8]
0x18000ee8e  mov     rdx, [rbp+100h+var_158]
0x18000ee92  mov     rcx, [r8+10h]
0x18000ee96  sub     rcx, r13
0x18000ee99  mov     rax, rdx
0x18000ee9c  shr     rax, 1
0x18000ee9f  and     rcx, rax
0x18000eea2  mov     rax, [r8+8]
0x18000eea6  and     rdx, r13
0x18000eea9  mov     rax, [rax+rcx*8]
0x18000eead  mov     rdi, [rax+rdx*8]
0x18000eeb1  mov     [rbp+100h+var_170], rdi
0x18000eeb5  mov     rax, [rsp+200h+var_188]
0x18000eeba  test    rax, rax
0x18000eebd  jz      short loc_18000EED6
0x18000eebf  sub     rax, 1
0x18000eec3  mov     [rsp+200h+var_188], rax
0x18000eec8  jnz     short loc_18000EED1
0x18000eeca  mov     [rsp+200h+var_190], r15
0x18000eecf  jmp     short loc_18000EED6
0x18000eed1  add     [rsp+200h+var_190], r13
0x18000eed6  mov     rbx, [rdi]
0x18000eed9  cmp     dword ptr [rbx+0ECh], 5
0x18000eee0  jnz     short loc_18000EF57
0x18000eee2  cmp     [rdi+38h], r15
0x18000eee6  jnz     loc_18000F13F
0x18000eeec  cmp     [r12+0D8h], r15
0x18000eef4  jz      loc_18000F117
0x18000eefa  xor     edx, edx; Val
0x18000eefc  lea     r14d, [rdx+2]
0x18000ef00  mov     r8d, 100h; Size
0x18000ef06  lea     rcx, [rbp+100h+var_150]; void *
0x18000ef0a  call    memset_0
0x18000ef0f  mov     r9, [rbx+10h]
0x18000ef13  cmp     [r9-10h], r15d
0x18000ef17  jnz     short loc_18000EF1C
0x18000ef19  mov     r9, [rbx]
0x18000ef1c  lea     r8, aReconfirmlowhe; "ReconfirmLowHealth skipped for '%s', DS"...
0x18000ef23  mov     edx, 80h; unsigned __int64
0x18000ef28  lea     rcx, [rbp+100h+var_150]; unsigned __int16 *
0x18000ef2c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ef31  mov     rcx, [r12+0D8h]
0x18000ef39  mov     rax, [rcx]
0x18000ef3c  mov     r9, [rdi]
0x18000ef3f  mov     r9, [r9+28h]
0x18000ef43  lea     r8, [rbp+100h+var_150]
0x18000ef47  xor     edx, edx
0x18000ef49  mov     rax, [rax+70h]
0x18000ef4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef52  jmp     loc_18000F10B
0x18000ef57  mov     [rsp+200h+var_1C8], r15
0x18000ef5c  mov     [rsp+200h+var_1D0], r15d
0x18000ef61  mov     [rsp+200h+var_1C0], r15
0x18000ef66  mov     [rsp+200h+var_1B8], 0
0x18000ef6f  mov     rcx, [rdi+38h]
0x18000ef73  mov     [rsp+200h+var_1B0], rcx
0x18000ef78  test    rcx, rcx
0x18000ef7b  jz      loc_18000F009
0x18000ef81  mov     rbx, [rdi+30h]
0x18000ef85  mov     r14d, r15d
0x18000ef88  mov     rbx, [rbx]
0x18000ef8b  cmp     rbx, [rdi+30h]
0x18000ef8f  jz      short loc_18000EFF5
0x18000ef91  test    esi, esi
0x18000ef93  js      short loc_18000EFF5
0x18000ef95  mov     eax, r14d
0x18000ef98  cmp     rax, rcx
0x18000ef9b  jnb     short loc_18000EFF5
0x18000ef9d  mov     rax, [rbx+10h]
0x18000efa1  cmp     dword ptr [rax+60h], 0Bh
0x18000efa5  jz      short loc_18000EFDF
0x18000efa7  mov     [rbp+100h+var_180], rax
0x18000efab  mov     [rbp+100h+var_178], 0
0x18000efb3  mov     [rsp+200h+var_1E0], r13d
0x18000efb8  lea     r9, ?SearchForNode@@YAJPEAVProblemNode@@PEAX@Z; SearchForNode(ProblemNode *,void *)
0x18000efbf  lea     r8, [rbp+100h+var_180]
0x18000efc3  mov     rdx, rdi
0x18000efc6  mov     ecx, r13d
0x18000efc9  call    ?IterateOverNodes@@YAJW4NodeIterateDirection@@PEAVProblemNode@@PEAXP6AJ12@ZH@Z; IterateOverNodes(NodeIterateDirection,ProblemNode *,void *,long (*)(ProblemNode *,void *),int)
0x18000efce  mov     esi, eax
0x18000efd0  test    eax, eax
0x18000efd2  js      short loc_18000EFDA
0x18000efd4  cmp     dword ptr [rbp+100h+var_178], r15d
0x18000efd8  jz      short loc_18000EFE4
0x18000efda  mov     rcx, [rsp+200h+var_1B0]
0x18000efdf  add     r14d, r13d
0x18000efe2  jmp     short loc_18000EF88
0x18000efe4  lea     rdx, [rbp+100h+var_170]
0x18000efe8  lea     rcx, [rsp+200h+var_1A8]
0x18000efed  call    ?push_back@?$deque@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXAEBQEAVProblemNode@@@Z; std::deque<ProblemNode *>::push_back(ProblemNode * const &)
0x18000eff2  mov     rdi, r15
0x18000eff5  test    rdi, rdi
0x18000eff8  jnz     short loc_18000F009
0x18000effa  lea     rcx, [rsp+200h+var_1C0]
0x18000efff  call    ??1?$TNDFDeallocator@PEAUtagHypothesisResult@@$1?FreeHypothesisResults@@YAXPEAU1@KH@Z@@QEAA@XZ; TNDFDeallocator<tagHypothesisResult *,&FreeHypothesisResults(tagHypothesisResult *,ulong,int)>::~TNDFDeallocator<tagHypothesisResult *,&FreeHypothesisResults(tagHypothesisResult *,ulong,int)>(void)
0x18000f004  jmp     loc_18000EE56
0x18000f009  mov     r8, rdi; struct ProblemNode *
0x18000f00c  lea     rdx, [rsp+200h+var_1D0]; unsigned int *
0x18000f011  lea     rcx, [rsp+200h+var_1C8]; struct tagHypothesisResult **
0x18000f016  call    ?GetBaseHypothesisData@@YAJPEAPEAUtagHypothesisResult@@PEAKPEBVProblemNode@@@Z; GetBaseHypothesisData(tagHypothesisResult * *,ulong *,ProblemNode const *)
0x18000f01b  mov     esi, eax
0x18000f01d  test    eax, eax
0x18000f01f  js      loc_18000F18A
0x18000f025  mov     r14d, r15d
0x18000f028  mov     r13, [rsp+200h+var_1C8]
0x18000f02d  mov     r15d, [rsp+200h+var_1D0]
0x18000f032  test    r15d, r15d
0x18000f035  jz      loc_18000F0F2
0x18000f03b  mov     [rsp+200h+var_1C0], r13
0x18000f040  mov     dword ptr [rsp+200h+var_1B8], r15d
0x18000f045  mov     dword ptr [rsp+200h+var_1B8+4], 1
0x18000f04d  mov     rbx, [rdi+30h]
0x18000f051  xor     ecx, ecx
0x18000f053  mov     [rsp+200h+var_1D0], ecx
0x18000f057  mov     rbx, [rbx]
0x18000f05a  mov     eax, esi
0x18000f05c  cmp     rbx, [rdi+30h]
0x18000f060  jz      short loc_18000F08C
0x18000f062  test    esi, esi
0x18000f064  js      loc_18000F0F2
0x18000f06a  mov     eax, ecx
0x18000f06c  cmp     rax, [rsp+200h+var_1B0]
0x18000f071  jnb     short loc_18000F090
0x18000f073  mov     r8, [rbx+10h]; struct ProblemNode *
0x18000f077  mov     edx, r15d; unsigned int
0x18000f07a  mov     rcx, r13; struct tagHypothesisResult *
0x18000f07d  call    ?SetHypothesisResult@@YAJPEAUtagHypothesisResult@@KPEBVProblemNode@@@Z; SetHypothesisResult(tagHypothesisResult *,ulong,ProblemNode const *)
0x18000f082  mov     esi, eax
0x18000f084  mov     ecx, [rsp+200h+var_1D0]
0x18000f088  inc     ecx
0x18000f08a  jmp     short loc_18000F053
0x18000f08c  test    eax, eax
0x18000f08e  js      short loc_18000F0F2
0x18000f090  test    r15d, r15d
0x18000f093  jz      short loc_18000F0F2
0x18000f095  mov     rcx, [rdi]; this
0x18000f098  cmp     dword ptr [rcx+0E4h], 0
0x18000f09f  jge     short loc_18000F0E4
0x18000f0a1  mov     rcx, [r12+50h]
0x18000f0a6  mov     rax, [rcx]
0x18000f0a9  mov     rax, [rax+38h]
0x18000f0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0b2  mov     esi, eax
0x18000f0b4  test    eax, eax
0x18000f0b6  js      short loc_18000F0DC
0x18000f0b8  mov     r8d, r15d; unsigned int
0x18000f0bb  mov     rdx, r13; struct tagHypothesisResult *
0x18000f0be  mov     rcx, [rdi]; this
0x18000f0c1  call    ?SecondPassDiagnose@ProblemInstance@@QEAA?AW4tagDIAGNOSIS_STATUS@@PEAUtagHypothesisResult@@KH@Z; ProblemInstance::SecondPassDiagnose(tagHypothesisResult *,ulong,int)
0x18000f0c6  mov     r14d, eax
0x18000f0c9  mov     rcx, [r12+50h]
0x18000f0ce  mov     rdx, [rcx]
0x18000f0d1  mov     rax, [rdx+40h]
0x18000f0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0da  jmp     short loc_18000F0F2
0x18000f0dc  mov     r14d, 3
0x18000f0e2  jmp     short loc_18000F0F2
0x18000f0e4  mov     r8d, r15d; unsigned int
0x18000f0e7  mov     rdx, r13; struct tagHypothesisResult *
0x18000f0ea  call    ?SecondPassDiagnose@ProblemInstance@@QEAA?AW4tagDIAGNOSIS_STATUS@@PEAUtagHypothesisResult@@KH@Z; ProblemInstance::SecondPassDiagnose(tagHypothesisResult *,ulong,int)
0x18000f0ef  mov     r14d, eax
0x18000f0f2  lea     rcx, [rsp+200h+var_1C0]
0x18000f0f7  call    ??1?$TNDFDeallocator@PEAUtagHypothesisResult@@$1?FreeHypothesisResults@@YAXPEAU1@KH@Z@@QEAA@XZ; TNDFDeallocator<tagHypothesisResult *,&FreeHypothesisResults(tagHypothesisResult *,ulong,int)>::~TNDFDeallocator<tagHypothesisResult *,&FreeHypothesisResults(tagHypothesisResult *,ulong,int)>(void)
0x18000f0fc  xor     r15d, r15d
0x18000f0ff  test    esi, esi
0x18000f101  lea     r13d, [r15+1]
0x18000f105  js      loc_18000EE56
0x18000f10b  sub     r14d, 1
0x18000f10f  jz      short loc_18000F128
0x18000f111  cmp     r14d, 1
0x18000f115  jnz     short loc_18000F13F
0x18000f117  mov     rcx, rdi; struct ProblemNode *
0x18000f11a  call    ?DisconnectNodeFromDiagGraph@@YAXPEAVProblemNode@@@Z; DisconnectNodeFromDiagGraph(ProblemNode *)
0x18000f11f  mov     dword ptr [rdi+20h], 8
0x18000f126  jmp     short loc_18000F13F
0x18000f128  xor     eax, eax
0x18000f12a  lock cmpxchg [r12+58h], r13d
0x18000f131  xor     r8d, r8d; int
0x18000f134  mov     rdx, rdi; struct ProblemNode *
0x18000f137  mov     rcx, r12; this
0x18000f13a  call    ?UpdateCoveredPathAnnotation@NetworkIncident@@AEAAXPEAVProblemNode@@H@Z; NetworkIncident::UpdateCoveredPathAnnotation(ProblemNode *,int)
0x18000f13f  mov     rbx, [rdi+40h]
0x18000f143  mov     rbx, [rbx]
0x18000f146  cmp     rbx, [rdi+40h]
0x18000f14a  jz      short loc_18000F171
0x18000f14c  lea     rdx, [rbx+10h]
0x18000f150  mov     rcx, [rdx]
0x18000f153  mov     eax, [rcx+60h]
0x18000f156  sub     eax, 0Ah
0x18000f159  cmp     eax, r13d
0x18000f15c  jbe     short loc_18000F143
0x18000f15e  mov     dword ptr [rcx+60h], 0Ah
0x18000f165  lea     rcx, [rsp+200h+var_1A8]
0x18000f16a  call    ?push_back@?$deque@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXAEBQEAVProblemNode@@@Z; std::deque<ProblemNode *>::push_back(ProblemNode * const &)
0x18000f16f  jmp     short loc_18000F143
0x18000f171  mov     dword ptr [rdi+60h], 0Bh
0x18000f178  mov     rdx, [r12+50h]; struct DiagnosticsClient *
0x18000f17d  mov     rcx, [rdi]; this
0x18000f180  call    ?ProcessDiagFiles@ProblemInstance@@QEAAJPEAVDiagnosticsClient@@@Z; ProblemInstance::ProcessDiagFiles(DiagnosticsClient *)
0x18000f185  jmp     loc_18000EE56
0x18000f18a  lea     rcx, [rsp+200h+var_1C0]
0x18000f18f  call    ??1?$TNDFDeallocator@PEAUtagHypothesisResult@@$1?FreeHypothesisResults@@YAXPEAU1@KH@Z@@QEAA@XZ; TNDFDeallocator<tagHypothesisResult *,&FreeHypothesisResults(tagHypothesisResult *,ulong,int)>::~TNDFDeallocator<tagHypothesisResult *,&FreeHypothesisResults(tagHypothesisResult *,ulong,int)>(void)
0x18000f194  nop
0x18000f195  lea     rcx, [rsp+200h+var_1A8]
0x18000f19a  call    ??1?$deque@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::deque<ProblemNode *>::~deque<ProblemNode *>(void)
0x18000f19f  mov     eax, esi
0x18000f1a1  mov     rcx, [rbp+100h+var_50]
0x18000f1a8  xor     rcx, rsp; StackCookie
0x18000f1ab  call    __security_check_cookie
0x18000f1b0  add     rsp, 1C8h
0x18000f1b7  pop     r15
0x18000f1b9  pop     r14
0x18000f1bb  pop     r13
0x18000f1bd  pop     r12
0x18000f1bf  pop     rdi
0x18000f1c0  pop     rsi
0x18000f1c1  pop     rbx
0x18000f1c2  pop     rbp
0x18000f1c3  retn
```
