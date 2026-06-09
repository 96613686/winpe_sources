# CWbemObject::WritePropertyValue(long,long,uchar const *)

- ea: `0x1800235d0`
- end: `0x180023bbe`
- name: `?WritePropertyValue@CWbemObject@@UEAAJJJPEBE@Z`
- size: `1518`
- prototype: `__int64 __fastcall(CWbemObject *this, int, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000e720`
- `0x180011e40`
- `0x180011ec0`
- `0x180013ae0`
- `0x1800235d0`
- `0x180023bd0`
- `0x180024390`
- `0x180037120`
- `0x18006fa66`
- `0x180071c50`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18002381f`
- `wbemcomn!GetMemLogObject` at `0x1800238c7`
- `wbemcomn!GetMemLogObject` at `0x180023912`
- `wbemcomn!GetMemLogObject` at `0x18002395d`
- `wbemcomn!GetMemLogObject` at `0x1800239a8`
- `wbemcomn!GetMemLogObject` at `0x180023a08`
- `wbemcomn!GetMemLogObject` at `0x180023a69`
- `wbemcomn!GetMemLogObject` at `0x180023aca`
- `wbemcomn!GetMemLogObject` at `0x180023b15`
- `wbemcomn!GetMemLogObject` at `0x180023b5d`
- `wbemcomn!GetMemLogObject` at `0x18002381f`
- `wbemcomn!GetMemLogObject` at `0x1800238c7`
- `wbemcomn!GetMemLogObject` at `0x180023912`
- `wbemcomn!GetMemLogObject` at `0x18002395d`
- `wbemcomn!GetMemLogObject` at `0x1800239a8`
- `wbemcomn!GetMemLogObject` at `0x180023a08`
- `wbemcomn!GetMemLogObject` at `0x180023a69`
- `wbemcomn!GetMemLogObject` at `0x180023aca`
- `wbemcomn!GetMemLogObject` at `0x180023b15`
- `wbemcomn!GetMemLogObject` at `0x180023b5d`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180023732`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180023732`
- `wbemcomn!?SetLPWSTR@CVar@@QEAAHPEAGH@Z` at `0x180023745`
- `wbemcomn!?SetLPWSTR@CVar@@QEAAHPEAGH@Z` at `0x180023745`
- `wbemcomn!?SetCanDelete@CVar@@QEAAXH@Z` at `0x180023751`
- `wbemcomn!?SetCanDelete@CVar@@QEAAXH@Z` at `0x180023751`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002382b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800238d7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023922`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002396d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800239b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023a18`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023a79`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023ada`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023b25`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023b6d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002382b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800238d7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023922`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002396d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800239b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023a18`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023a79`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023ada`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023b25`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180023b6d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800237ff`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18002384c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x1800237ff`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18002384c`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CWbemObject::WritePropertyValue(CWbemObject *this, int a2, unsigned int a3, unsigned __int16 *a4)
{
  unsigned __int64 v5; // r12
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rdi
  __int64 v11; // rdx
  unsigned int *v12; // rax
  unsigned int v13; // ebx
  CCompressedString *v14; // rdi
  unsigned int v15; // edx
  int v16; // edx
  unsigned int v17; // ebx
  CMemoryLog *v19; // rax
  CWbemRefreshingSvc *v20; // rcx
  __int64 v21; // rdx
  CMemoryLog *v22; // rax
  CWbemRefreshingSvc *v23; // rcx
  __int64 v24; // rdx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r9
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  CMemoryLog *v33; // rax
  CMemoryLog *v34; // rax
  unsigned int v35[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v36; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v37[2]; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v38; // [rsp+50h] [rbp-30h]
  _BYTE v39[40]; // [rsp+58h] [rbp-28h] BYREF
  int v41; // [rsp+C8h] [rbp+48h]

  v5 = a3;
  if ( !a4 )
  {
    MemLogObject = GetMemLogObject();
    v17 = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v17;
    }
    v24 = 74;
    goto LABEL_69;
  }
  v7 = (a2 >> 16) & 0x3FF;
  v8 = *((_QWORD *)this + 16);
  if ( (int)v7 > *(_DWORD *)(v8 + 20) )
  {
    v26 = GetMemLogObject();
    v17 = -2147217400;
    CMemoryLog::Write(v26, -2147217400);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v17;
    }
    v24 = 75;
    goto LABEL_69;
  }
  if ( (unsigned int)CBitBlockTable<2>::GetBit(*(_QWORD *)v8, (unsigned int)v7, 1)
    || (v41 = 1, (unsigned int)CBitBlockTable<2>::GetBit(**((_QWORD **)this + 16), (unsigned int)v7, 0)) )
  {
    v41 = 0;
  }
  v9 = **((_QWORD **)this + 16);
  SafeInt<unsigned __int64>::MixedSizeMultiply<int>(v35, v7, 2);
  SafeInt<unsigned __int64>::MixedSizeAddition<int>(v35, *(_QWORD *)v35, 0);
  *(_DWORD *)(v9 + 4LL * ((signed int)v35[0] / 32)) &= ~(1 << ((signed int)v35[0] % 32));
  v35[0] = a2 & 0x1FFF;
  v10 = **((_QWORD **)this + 16);
  SafeInt<unsigned __int64>::MixedSizeMultiply<int>(&v36, v7, 2);
  SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v36, v36, 1);
  *(_DWORD *)(v10 + 4LL * ((int)v36 / 32)) &= ~(1 << ((int)v36 % 32));
  if ( a2 < 0 )
  {
    v11 = *((_QWORD *)this + 16);
    if ( (unsigned __int64)v35[0] + 4 > *(unsigned int *)(v11 + 16) )
    {
      v22 = GetMemLogObject();
      v17 = -2147217400;
      CMemoryLog::Write(v22, -2147217400);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v17;
      }
      v24 = 76;
    }
    else
    {
      if ( (int)v5 >= 2 && (v5 & 1) == 0 && !a4[(v5 >> 1) - 1] )
      {
        v37[0] = &CDataTablePtr::`vftable';
        v37[1] = v11;
        v38 = v35[0];
        CVar::CVar((CVar *)v39);
        CVar::SetLPWSTR((CVar *)v39, a4, 1);
        CVar::SetCanDelete((CVar *)v39, 0);
        v12 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD *))v37[0])(v37);
        v13 = *v12;
        v14 = CFastHeap::ResolveString(*((CFastHeap **)this + 17), *v12);
        if ( v14 )
        {
          if ( CFastHeap::IsFakeAddress(v13)
            || (v15 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 17) + 8LL) + 4LL), v13 > v15) )
          {
            v16 = 0;
          }
          else
          {
            v16 = v15 - v13;
          }
          if ( CCompressedString::NValidateSize(v14, v16) )
          {
            v35[0] = 0;
            v17 = CUntypedValue::LoadFromCVar(
                    (struct CPtrSource *)v37,
                    (struct CVar *)v39,
                    8u,
                    *((struct CFastHeap **)this + 17),
                    v35,
                    v41);
            if ( (v17 & 0x80000000) != 0 )
            {
              v19 = GetMemLogObject();
              CMemoryLog::Write(v19, v17);
              v20 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_20;
              }
              v28 = 80;
              v29 = v17;
            }
            else
            {
              if ( v35[0] != 4095 )
              {
                CVar::~CVar((CVar *)v39);
                return 0;
              }
              v31 = GetMemLogObject();
              v17 = -2147217403;
              CMemoryLog::Write(v31, -2147217403);
              v20 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_20;
              }
              v28 = 81;
              v29 = 2147749893LL;
            }
LABEL_56:
            WPP_SF_d(*((_QWORD *)v20 + 2), v28, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, v29);
LABEL_20:
            CVar::~CVar((CVar *)v39);
            return v17;
          }
          v30 = GetMemLogObject();
          v17 = -2147217400;
          CMemoryLog::Write(v30, -2147217400);
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_20;
          }
          v28 = 79;
        }
        else
        {
          v27 = GetMemLogObject();
          v17 = -2147217400;
          CMemoryLog::Write(v27, -2147217400);
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_20;
          }
          v28 = 78;
        }
        v29 = 2147749896LL;
        goto LABEL_56;
      }
      v32 = GetMemLogObject();
      v17 = -2147217400;
      CMemoryLog::Write(v32, -2147217400);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v17;
      }
      v24 = 77;
    }
LABEL_69:
    WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids, 2147749896LL);
    return v17;
  }
  if ( (_DWORD)v5 != (((unsigned int)a2 >> 26) & 0xF) )
  {
    v33 = GetMemLogObject();
    v17 = -2147217400;
    CMemoryLog::Write(v33, -2147217400);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v17;
    }
    v24 = 82;
    goto LABEL_69;
  }
  v21 = *((_QWORD *)this + 16);
  if ( (unsigned int)(v5 + v35[0]) <= *(_DWORD *)(v21 + 16) )
  {
    memcpy_0((void *)(*(_QWORD *)(v21 + 8) + (a2 & 0x1FFF)), a4, ((unsigned __int64)a2 >> 26) & 0xF);
    return 0;
  }
  v34 = GetMemLogObject();
  v17 = -2147217400;
  CMemoryLog::Write(v34, -2147217400);
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v24 = 83;
    goto LABEL_69;
  }
  return v17;
}

```

## disassembly

```asm
0x1800235d0  mov     [rsp-28h+arg_0], rbx
0x1800235d5  mov     [rsp-28h+arg_8], edx
0x1800235d9  push    rbp
0x1800235da  push    rdi
0x1800235db  push    r12
0x1800235dd  push    r13
0x1800235df  push    r15
0x1800235e1  mov     rbp, rsp
0x1800235e4  sub     rsp, 80h
0x1800235eb  mov     r13, r9
0x1800235ee  mov     r12d, r8d
0x1800235f1  mov     r15, rcx
0x1800235f4  test    r9, r9
0x1800235f7  jz      loc_180023912
0x1800235fd  mov     ebx, edx
0x1800235ff  sar     ebx, 10h
0x180023602  and     ebx, 3FFh
0x180023608  mov     rcx, [rcx+80h]
0x18002360f  cmp     ebx, [rcx+14h]
0x180023612  jg      loc_18002395D
0x180023618  mov     r8d, 1
0x18002361e  mov     edx, ebx
0x180023620  mov     rcx, [rcx]
0x180023623  call    ?GetBit@?$CBitBlockTable@$01@@QEAAHHH@Z; CBitBlockTable<2>::GetBit(int,int)
0x180023628  test    eax, eax
0x18002362a  jz      loc_180023856
0x180023630  mov     [rbp+arg_18], 0
0x180023637  mov     rax, [r15+80h]
0x18002363e  mov     rdi, [rax]
0x180023641  mov     r8d, 2
0x180023647  mov     rdx, rbx
0x18002364a  lea     rcx, [rbp+var_50]
0x18002364e  call    ??$MixedSizeMultiply@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeMultiply<int>(SafeInt<unsigned __int64>,int)
0x180023653  xor     r8d, r8d
0x180023656  mov     rdx, qword ptr [rbp+var_50]
0x18002365a  lea     rcx, [rbp+var_50]
0x18002365e  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x180023663  mov     eax, [rbp+var_50]
0x180023666  cdq
0x180023667  mov     ecx, 20h ; ' '
0x18002366c  idiv    ecx
0x18002366e  movsxd  rcx, eax
0x180023671  mov     eax, [rdi+rcx*4]
0x180023674  btr     eax, edx
0x180023677  mov     [rdi+rcx*4], eax
0x18002367a  mov     eax, [rbp+arg_8]
0x18002367d  and     eax, 1FFFh
0x180023682  mov     [rbp+var_50], eax
0x180023685  mov     rax, [r15+80h]
0x18002368c  mov     rdi, [rax]
0x18002368f  mov     r8d, 2
0x180023695  mov     rdx, rbx
0x180023698  lea     rcx, [rbp+var_48]
0x18002369c  call    ??$MixedSizeMultiply@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeMultiply<int>(SafeInt<unsigned __int64>,int)
0x1800236a1  mov     r8d, 1
0x1800236a7  mov     rdx, [rbp+var_48]
0x1800236ab  lea     rcx, [rbp+var_48]
0x1800236af  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x1800236b4  mov     eax, dword ptr [rbp+var_48]
0x1800236b7  cdq
0x1800236b8  mov     ecx, 20h ; ' '
0x1800236bd  idiv    ecx
0x1800236bf  movsxd  rcx, eax
0x1800236c2  mov     eax, [rdi+rcx*4]
0x1800236c5  btr     eax, edx
0x1800236c8  mov     [rdi+rcx*4], eax
0x1800236cb  movsxd  rcx, [rbp+arg_8]
0x1800236cf  test    ecx, ecx
0x1800236d1  jns     loc_18002387E
0x1800236d7  mov     rdx, [r15+80h]
0x1800236de  mov     r8d, [rbp+var_50]
0x1800236e2  lea     rcx, [r8+4]
0x1800236e6  mov     eax, [rdx+10h]
0x1800236e9  cmp     rcx, rax
0x1800236ec  ja      loc_1800238C7
0x1800236f2  cmp     r12d, 2
0x1800236f6  jl      loc_180023ACA
0x1800236fc  test    r12b, 1
0x180023700  jnz     loc_180023ACA
0x180023706  mov     rax, r12
0x180023709  shr     rax, 1
0x18002370c  xor     r12d, r12d
0x18002370f  cmp     [r13+rax*2-2], r12w
0x180023715  jnz     loc_180023ACA
0x18002371b  lea     rax, ??_7CDataTablePtr@@6B@; const CDataTablePtr::`vftable'
0x180023722  mov     [rbp+var_40], rax
0x180023726  mov     [rbp+var_38], rdx
0x18002372a  mov     [rbp+var_30], r8d
0x18002372e  lea     rcx, [rbp+var_28]
0x180023732  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180023738  nop
0x180023739  lea     r8d, [r12+1]
0x18002373e  mov     rdx, r13
0x180023741  lea     rcx, [rbp+var_28]
0x180023745  call    cs:__imp_?SetLPWSTR@CVar@@QEAAHPEAGH@Z; CVar::SetLPWSTR(ushort *,int)
0x18002374b  xor     edx, edx
0x18002374d  lea     rcx, [rbp+var_28]
0x180023751  call    cs:__imp_?SetCanDelete@CVar@@QEAAXH@Z; CVar::SetCanDelete(int)
0x180023757  mov     rax, [rbp+var_40]
0x18002375b  lea     rcx, [rbp+var_40]
0x18002375f  mov     rax, [rax]
0x180023762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023767  mov     ebx, [rax]
0x180023769  mov     edx, ebx; unsigned int
0x18002376b  mov     rcx, [r15+88h]; this
0x180023772  call    ?ResolveString@CFastHeap@@QEAAPEAVCCompressedString@@K@Z; CFastHeap::ResolveString(ulong)
0x180023777  mov     rdi, rax
0x18002377a  test    rax, rax
0x18002377d  jz      loc_1800239A8
0x180023783  mov     ecx, ebx; unsigned int
0x180023785  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x18002378a  test    al, al
0x18002378c  jnz     loc_180023A00
0x180023792  mov     rax, [r15+88h]
0x180023799  mov     rcx, [rax+8]
0x18002379d  mov     edx, [rcx+4]
0x1800237a0  cmp     ebx, edx
0x1800237a2  ja      loc_180023A00
0x1800237a8  sub     edx, ebx; int
0x1800237aa  mov     rcx, rdi; this
0x1800237ad  call    ?NValidateSize@CCompressedString@@QEBA_NH@Z; CCompressedString::NValidateSize(int)
0x1800237b2  test    al, al
0x1800237b4  jz      loc_180023A08
0x1800237ba  mov     [rbp+var_50], r12d
0x1800237be  mov     eax, [rbp+arg_18]
0x1800237c1  mov     [rsp+80h+var_58], eax; int
0x1800237c5  lea     rax, [rbp+var_50]
0x1800237c9  mov     [rsp+80h+var_60], rax; unsigned int *
0x1800237ce  mov     r9, [r15+88h]; struct CFastHeap *
0x1800237d5  mov     r8d, 8; unsigned int
0x1800237db  lea     rdx, [rbp+var_28]; struct CVar *
0x1800237df  lea     rcx, [rbp+var_40]; struct CPtrSource *
0x1800237e3  call    ?LoadFromCVar@CUntypedValue@@SAJPEAVCPtrSource@@AEAVCVar@@KPEAVCFastHeap@@AEAKH@Z; CUntypedValue::LoadFromCVar(CPtrSource *,CVar &,ulong,CFastHeap *,ulong &,int)
0x1800237e8  mov     ebx, eax
0x1800237ea  test    eax, eax
0x1800237ec  js      short loc_18002381F
0x1800237ee  cmp     [rbp+var_50], 0FFFh
0x1800237f5  jz      loc_180023A69
0x1800237fb  lea     rcx, [rbp+var_28]
0x1800237ff  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180023805  xor     eax, eax
0x180023807  mov     rbx, [rsp+80h+arg_0]
0x18002380f  add     rsp, 80h
0x180023816  pop     r15
0x180023818  pop     r13
0x18002381a  pop     r12
0x18002381c  pop     rdi
0x18002381d  pop     rbp
0x18002381e  retn
0x18002381f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180023825  nop
0x180023826  mov     edx, ebx
0x180023828  mov     rcx, rax
0x18002382b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180023831  lea     rax, WPP_GLOBAL_Control
0x180023838  mov     rcx, cs:WPP_GLOBAL_Control
0x18002383f  cmp     rcx, rax
0x180023842  jnz     loc_180023A4B
0x180023848  lea     rcx, [rbp+var_28]
0x18002384c  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180023852  mov     eax, ebx
0x180023854  jmp     short loc_180023807
0x180023856  mov     rcx, [r15+80h]
0x18002385d  xor     r8d, r8d
0x180023860  mov     edx, ebx
0x180023862  mov     rcx, [rcx]
0x180023865  call    ?GetBit@?$CBitBlockTable@$01@@QEAAHHH@Z; CBitBlockTable<2>::GetBit(int,int)
0x18002386a  test    eax, eax
0x18002386c  mov     [rbp+arg_18], 1
0x180023873  jz      loc_180023637
0x180023879  jmp     loc_180023630
0x18002387e  mov     eax, ecx
0x180023880  shr     eax, 1Ah
0x180023883  and     eax, 0Fh
0x180023886  cmp     r12d, eax
0x180023889  jnz     loc_180023B15
0x18002388f  mov     rdx, [r15+80h]
0x180023896  mov     eax, [rbp+var_50]
0x180023899  add     eax, r12d
0x18002389c  cmp     eax, [rdx+10h]
0x18002389f  ja      loc_180023B5D
0x1800238a5  mov     r8, rcx
0x1800238a8  shr     r8, 1Ah
0x1800238ac  and     r8d, 0Fh; Size
0x1800238b0  and     ecx, 1FFFh
0x1800238b6  add     rcx, [rdx+8]; void *
0x1800238ba  mov     rdx, r13; Src
0x1800238bd  call    memcpy_0
0x1800238c2  jmp     loc_180023805
0x1800238c7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800238cd  mov     ebx, 80041008h
0x1800238d2  mov     edx, ebx
0x1800238d4  mov     rcx, rax
0x1800238d7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800238dd  lea     rax, WPP_GLOBAL_Control
0x1800238e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238eb  cmp     rcx, rax
0x1800238ee  jz      loc_180023852
0x1800238f4  test    byte ptr [rcx+1Ch], 1
0x1800238f8  jz      loc_180023852
0x1800238fe  cmp     byte ptr [rcx+19h], 2
0x180023902  jb      loc_180023852
0x180023908  mov     edx, 4Ch ; 'L'
0x18002390d  jmp     loc_180023BA3
0x180023912  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180023918  mov     ebx, 80041008h
0x18002391d  mov     edx, ebx
0x18002391f  mov     rcx, rax
0x180023922  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180023928  lea     rax, WPP_GLOBAL_Control
0x18002392f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023936  cmp     rcx, rax
0x180023939  jz      loc_180023852
0x18002393f  test    byte ptr [rcx+1Ch], 1
0x180023943  jz      loc_180023852
0x180023949  cmp     byte ptr [rcx+19h], 2
0x18002394d  jb      loc_180023852
0x180023953  mov     edx, 4Ah ; 'J'
0x180023958  jmp     loc_180023BA3
0x18002395d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180023963  mov     ebx, 80041008h
0x180023968  mov     edx, ebx
0x18002396a  mov     rcx, rax
0x18002396d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180023973  lea     rax, WPP_GLOBAL_Control
0x18002397a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023981  cmp     rcx, rax
0x180023984  jz      loc_180023852
0x18002398a  test    byte ptr [rcx+1Ch], 1
0x18002398e  jz      loc_180023852
0x180023994  cmp     byte ptr [rcx+19h], 2
0x180023998  jb      loc_180023852
0x18002399e  mov     edx, 4Bh ; 'K'
0x1800239a3  jmp     loc_180023BA3
0x1800239a8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800239ae  mov     ebx, 80041008h
0x1800239b3  mov     edx, ebx
0x1800239b5  mov     rcx, rax
0x1800239b8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800239be  lea     rax, WPP_GLOBAL_Control
0x1800239c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239cc  cmp     rcx, rax
0x1800239cf  jz      loc_180023848
0x1800239d5  test    byte ptr [rcx+1Ch], 1
0x1800239d9  jz      loc_180023848
0x1800239df  cmp     byte ptr [rcx+19h], 2
0x1800239e3  jb      loc_180023848
0x1800239e9  mov     edx, 4Eh ; 'N'
0x1800239ee  jmp     short loc_1800239F5
0x1800239f0  mov     edx, 4Fh ; 'O'
0x1800239f5  mov     r9d, 80041008h
0x1800239fb  jmp     loc_180023AB5
0x180023a00  mov     edx, r12d
0x180023a03  jmp     loc_1800237AA
0x180023a08  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180023a0e  mov     ebx, 80041008h
0x180023a13  mov     edx, ebx
0x180023a15  mov     rcx, rax
0x180023a18  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180023a1e  lea     rax, WPP_GLOBAL_Control
0x180023a25  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a2c  cmp     rcx, rax
0x180023a2f  jz      loc_180023848
0x180023a35  test    byte ptr [rcx+1Ch], 1
0x180023a39  jz      loc_180023848
0x180023a3f  cmp     byte ptr [rcx+19h], 2
0x180023a43  jb      loc_180023848
0x180023a49  jmp     short loc_1800239F0
0x180023a4b  test    byte ptr [rcx+1Ch], 1
0x180023a4f  jz      loc_180023848
0x180023a55  cmp     byte ptr [rcx+19h], 2
0x180023a59  jb      loc_180023848
0x180023a5f  mov     edx, 50h ; 'P'
0x180023a64  mov     r9d, ebx
0x180023a67  jmp     short loc_180023AB5
0x180023a69  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180023a6f  mov     ebx, 80041005h
0x180023a74  mov     edx, ebx
0x180023a76  mov     rcx, rax
0x180023a79  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180023a7f  lea     rax, WPP_GLOBAL_Control
0x180023a86  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a8d  cmp     rcx, rax
0x180023a90  jz      loc_180023848
0x180023a96  test    byte ptr [rcx+1Ch], 1
0x180023a9a  jz      loc_180023848
0x180023aa0  cmp     byte ptr [rcx+19h], 2
0x180023aa4  jb      loc_180023848
0x180023aaa  mov     edx, 51h ; 'Q'
0x180023aaf  mov     r9d, 80041005h
0x180023ab5  lea     r8, WPP_5339f717c07a3ead76e227cfe90ded68_Traceguids
0x180023abc  mov     rcx, [rcx+10h]
0x180023ac0  call    WPP_SF_d
0x180023ac5  jmp     loc_180023848
0x180023aca  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180023ad0  mov     ebx, 80041008h
0x180023ad5  mov     edx, ebx
0x180023ad7  mov     rcx, rax
0x180023ada  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180023ae0  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
