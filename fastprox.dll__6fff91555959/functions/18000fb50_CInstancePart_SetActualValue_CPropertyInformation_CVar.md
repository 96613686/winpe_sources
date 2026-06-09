# CInstancePart::SetActualValue(CPropertyInformation *,CVar *)

- ea: `0x18000fb50`
- end: `0x180010143`
- name: `?SetActualValue@CInstancePart@@QEAAJPEAVCPropertyInformation@@PEAVCVar@@@Z`
- size: `1523`
- prototype: `__int64 __fastcall(CInstancePart *this, struct CPropertyInformation *, struct CVar *)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000de50`
- `0x180040a20`
- `0x180079620`

## callees

- `0x18000e720`
- `0x18000f500`
- `0x18000fb50`
- `0x180011e40`
- `0x180011ec0`
- `0x180037120`
- `0x180045140`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18000fde7`
- `wbemcomn!GetMemLogObject` at `0x18000ff79`
- `wbemcomn!GetMemLogObject` at `0x18000ffc5`
- `wbemcomn!GetMemLogObject` at `0x18001000e`
- `wbemcomn!GetMemLogObject` at `0x18000fde7`
- `wbemcomn!GetMemLogObject` at `0x18000ff79`
- `wbemcomn!GetMemLogObject` at `0x18000ffc5`
- `wbemcomn!GetMemLogObject` at `0x18001000e`
- `wbemcomn!?IsDataNull@CVar@@QEAAHXZ` at `0x18000fb86`
- `wbemcomn!?IsDataNull@CVar@@QEAAHXZ` at `0x18000fb86`
- `wbemcomn!?GetOleType@CVar@@QEAAHXZ` at `0x18000fba9`
- `wbemcomn!?GetOleType@CVar@@QEAAHXZ` at `0x18000fba9`
- `wbemcomn!?ChangeTypeTo@CVar@@QEAAHG@Z` at `0x18000fdd9`
- `wbemcomn!?ChangeTypeTo@CVar@@QEAAHG@Z` at `0x18000fdd9`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x18000fb75`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x18000fb75`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000fdf5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ff84`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ffd3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001001c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000fdf5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ff84`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ffd3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001001c`

## pseudocode

```c
__int64 __fastcall CInstancePart::SetActualValue(CInstancePart *this, struct CPropertyInformation *a2, struct CVar *a3)
{
  __int16 OleType; // ax
  unsigned int v7; // r8d
  __int16 v8; // r9
  int v9; // edx
  __int64 *v10; // r14
  __int64 v11; // r12
  int v12; // ecx
  unsigned int v13; // r8d
  unsigned int v14; // r12d
  int v15; // ebx
  __int64 v16; // rdi
  __int64 v17; // rdi
  int *v18; // rdx
  int v19; // ecx
  __int16 v21; // dx
  __int16 v22; // ax
  unsigned __int16 VARTYPE; // ax
  CMemoryLog *v24; // rax
  CWbemRefreshingSvc *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdi
  __int64 v28; // rdi
  int *v29; // rdx
  int v30; // ecx
  __int64 v31; // r12
  CMemoryLog *v32; // rax
  CMemoryLog *v33; // rax
  CMemoryLog *MemLogObject; // rax
  __int64 v35; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v36[2]; // [rsp+38h] [rbp-18h] BYREF
  int v37; // [rsp+48h] [rbp-8h]
  __int64 v38; // [rsp+98h] [rbp+48h] BYREF

  if ( CVar::IsNull(a3) || CVar::IsDataNull(a3) )
  {
    v27 = *((_QWORD *)this + 6);
    SafeInt<unsigned __int64>::MixedSizeMultiply<int>(&v38, *((unsigned __int16 *)a2 + 2), 2);
    SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v38, v38, 0);
    *(_DWORD *)(v27 + 4LL * ((int)v38 / 32)) |= 1 << ((int)v38 % 32);
    v28 = *((_QWORD *)this + 6);
    SafeInt<unsigned __int64>::MixedSizeMultiply<int>(&v38, *((unsigned __int16 *)a2 + 2), 2);
    SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v38, v38, 1);
    v29 = (int *)(v28 + 4LL * ((int)v38 / 32));
    v30 = *v29;
    _bittestandreset(&v30, (int)v38 % 32);
    *v29 = v30;
    return 0;
  }
  if ( !(unsigned int)CUntypedValue::CheckCVar(a3, *(_DWORD *)a2) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217403);
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749893LL;
    }
    v26 = 95;
    goto LABEL_26;
  }
  OleType = CVar::GetOleType(a3);
  v7 = *(_DWORD *)a2;
  v8 = OleType;
  if ( ((*(_DWORD *)a2 & 0x2000) != 0) != ((OleType & 0x2000) != 0) )
    goto LABEL_59;
  if ( (v7 & 0xFFFFDFFF) != 0x13 || (OleType & 0xDFFF) != 8 )
  {
    if ( (v9 = *(_DWORD *)a2 & 0xFFF, v9 != 8) && (unsigned int)(v9 - 101) > 1 || (OleType & 0xDFFF) != 0x1F )
    {
      if ( (unsigned int)(v9 - 20) > 1 || (OleType & 0xDFFF) != 0x1F )
      {
        if ( (*(_DWORD *)a2 & 0xFFF) == 0x12 )
        {
LABEL_29:
          v21 = 3;
        }
        else
        {
          v21 = 0;
          switch ( v7 & 0xFFF )
          {
            case 2u:
            case 0x10u:
            case 0x67u:
              v21 = 2;
              break;
            case 3u:
            case 0x13u:
              goto LABEL_29;
            case 4u:
              v21 = 4;
              break;
            case 5u:
              v21 = 5;
              break;
            case 8u:
            case 0x14u:
            case 0x15u:
            case 0x65u:
            case 0x66u:
              v21 = 8;
              break;
            case 0xBu:
              v21 = 11;
              break;
            case 0xDu:
            case 0x68u:
              v21 = 13;
              break;
            case 0x11u:
              v21 = 17;
              break;
            default:
              break;
          }
        }
        v22 = v21 | 0x2000;
        if ( (v7 & 0x2000) == 0 )
          v22 = v21;
        if ( v8 != v22 )
        {
LABEL_59:
          VARTYPE = CType::GetVARTYPE(v7);
          if ( !CVar::ChangeTypeTo(a3, VARTYPE) )
          {
            v24 = GetMemLogObject();
            CMemoryLog::Write(v24, -2147217403);
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              return 2147749893LL;
            }
            v26 = 96;
            goto LABEL_26;
          }
        }
      }
    }
  }
  v10 = (__int64 *)((char *)this + 48);
  v11 = *((_QWORD *)this + 6);
  SafeInt<unsigned __int64>::MixedSizeMultiply<int>(&v35, *((unsigned __int16 *)a2 + 2), 2);
  SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v35, v35, 1);
  v12 = 0;
  if ( ((*(_DWORD *)(v11 + 4LL * ((int)v35 / 32)) >> ((int)v35 % 32)) & 1) == 0 )
  {
    v31 = *v10;
    SafeInt<unsigned __int64>::MixedSizeMultiply<int>(&v35, *((unsigned __int16 *)a2 + 2), 2);
    SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v35, v35, 0);
    if ( ((*(_DWORD *)(v31 + 4LL * ((int)v35 / 32)) >> ((int)v35 % 32)) & 1) == 0 )
      v12 = 1;
  }
  v13 = *(_DWORD *)a2;
  v14 = *((unsigned __int16 *)a2 + 2);
  v36[0] = &CDataTablePtr::`vftable';
  v37 = *(_DWORD *)((char *)a2 + 6);
  v36[1] = (char *)this + 48;
  LODWORD(v38) = 0;
  v15 = CUntypedValue::LoadFromCVar(
          (struct CPtrSource *)v36,
          a3,
          v13 & 0x2FFF,
          (CInstancePart *)((char *)this + 184),
          (unsigned int *)&v38,
          v12);
  if ( v15 >= 0 )
  {
    if ( (_DWORD)v38 != 4095 )
    {
      v16 = *v10;
      SafeInt<unsigned __int64>::MixedSizeMultiply<int>(&v35, v14, 2);
      SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v35, v35, 0);
      *(_DWORD *)(v16 + 4LL * ((int)v35 / 32)) &= ~(1 << ((int)v35 % 32));
      v17 = *v10;
      SafeInt<unsigned __int64>::MixedSizeMultiply<int>(&v35, v14, 2);
      SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v35, v35, 1);
      v18 = (int *)(v17 + 4LL * ((int)v35 / 32));
      v19 = *v18;
      _bittestandreset(&v19, (int)v35 % 32);
      *v18 = v19;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 24LL))(*((_QWORD *)this + 4));
      return 0;
    }
    v33 = GetMemLogObject();
    CMemoryLog::Write(v33, -2147217403);
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749893LL;
    }
    v26 = 98;
LABEL_26:
    WPP_SF_d(*((_QWORD *)v25 + 2), v26, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749893LL);
    return 2147749893LL;
  }
  v32 = GetMemLogObject();
  CMemoryLog::Write(v32, v15);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      97,
      WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
      (unsigned int)v15);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000fb50  mov     [rsp-28h+arg_0], rbx
0x18000fb55  mov     [rsp-28h+arg_8], rsi
0x18000fb5a  push    rbp
0x18000fb5b  push    rdi
0x18000fb5c  push    r12
0x18000fb5e  push    r14
0x18000fb60  push    r15
0x18000fb62  mov     rbp, rsp
0x18000fb65  sub     rsp, 50h
0x18000fb69  mov     rsi, rcx
0x18000fb6c  mov     rdi, r8
0x18000fb6f  mov     rcx, r8
0x18000fb72  mov     rbx, rdx
0x18000fb75  call    cs:__imp_?IsNull@CVar@@QEAAHXZ; CVar::IsNull(void)
0x18000fb7b  test    eax, eax
0x18000fb7d  jnz     loc_18000FE3F
0x18000fb83  mov     rcx, rdi
0x18000fb86  call    cs:__imp_?IsDataNull@CVar@@QEAAHXZ; CVar::IsDataNull(void)
0x18000fb8c  test    eax, eax
0x18000fb8e  jnz     loc_18000FE3F
0x18000fb94  mov     edx, [rbx]; unsigned int
0x18000fb96  mov     rcx, rdi; struct CVar *
0x18000fb99  call    ?CheckCVar@CUntypedValue@@SAHAEAVCVar@@K@Z; CUntypedValue::CheckCVar(CVar &,ulong)
0x18000fb9e  test    eax, eax
0x18000fba0  jz      loc_18001000E
0x18000fba6  mov     rcx, rdi
0x18000fba9  call    cs:__imp_?GetOleType@CVar@@QEAAHXZ; CVar::GetOleType(void)
0x18000fbaf  mov     r8d, [rbx]
0x18000fbb2  mov     r15d, 2
0x18000fbb8  mov     edx, r8d
0x18000fbbb  mov     ecx, eax
0x18000fbbd  shr     edx, 0Dh
0x18000fbc0  mov     r9d, eax
0x18000fbc3  shr     ecx, 0Dh
0x18000fbc6  and     edx, 1
0x18000fbc9  and     ecx, 1
0x18000fbcc  cmp     dl, cl
0x18000fbce  jnz     loc_18000FDCB
0x18000fbd4  mov     eax, r8d
0x18000fbd7  movzx   ecx, r9w
0x18000fbdb  btr     eax, 0Dh
0x18000fbdf  cmp     eax, 13h
0x18000fbe2  jz      loc_18000FEE3
0x18000fbe8  mov     edx, r8d
0x18000fbeb  and     edx, 0FFFh
0x18000fbf1  cmp     edx, 8
0x18000fbf4  jnz     loc_180010057
0x18000fbfa  mov     eax, ecx
0x18000fbfc  btr     eax, 0Dh
0x18000fc00  cmp     eax, 1Fh
0x18000fc03  jz      short loc_18000FC1E
0x18000fc05  lea     eax, [rdx-14h]
0x18000fc08  cmp     eax, 1
0x18000fc0b  ja      loc_18000FD90
0x18000fc11  btr     ecx, 0Dh
0x18000fc15  cmp     ecx, 1Fh
0x18000fc18  jnz     loc_18000FD90
0x18000fc1e  movzx   edx, word ptr [rbx+4]
0x18000fc22  lea     r14, [rsi+30h]
0x18000fc26  mov     r12, [r14]
0x18000fc29  lea     rcx, [rbp+var_20]
0x18000fc2d  mov     r8d, r15d
0x18000fc30  call    ??$MixedSizeMultiply@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeMultiply<int>(SafeInt<unsigned __int64>,int)
0x18000fc35  mov     rdx, [rbp+var_20]
0x18000fc39  lea     rcx, [rbp+var_20]
0x18000fc3d  mov     r8d, 1
0x18000fc43  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x18000fc48  mov     rcx, [rbp+var_20]
0x18000fc4c  mov     eax, ecx
0x18000fc4e  cdq
0x18000fc4f  and     edx, 1Fh
0x18000fc52  add     eax, edx
0x18000fc54  sar     eax, 5
0x18000fc57  cdqe
0x18000fc59  and     ecx, 8000001Fh
0x18000fc5f  jge     short loc_18000FC68
0x18000fc61  dec     ecx
0x18000fc63  or      ecx, 0FFFFFFE0h
0x18000fc66  inc     ecx
0x18000fc68  mov     eax, [r12+rax*4]
0x18000fc6c  shr     eax, cl
0x18000fc6e  test    al, 1
0x18000fc70  jz      loc_18000FEF7
0x18000fc76  xor     ecx, ecx
0x18000fc78  mov     r8d, [rbx]
0x18000fc7b  lea     rax, ??_7CDataTablePtr@@6B@; const CDataTablePtr::`vftable'
0x18000fc82  movzx   r12d, word ptr [rbx+4]
0x18000fc87  lea     r9, [rsi+0B8h]; struct CFastHeap *
0x18000fc8e  mov     [rbp+var_18], rax
0x18000fc92  and     r8d, 2FFFh; unsigned int
0x18000fc99  mov     eax, [rbx+6]
0x18000fc9c  mov     rdx, rdi; struct CVar *
0x18000fc9f  mov     [rsp+50h+var_28], ecx; int
0x18000fca3  lea     rcx, [rbp+var_18]; struct CPtrSource *
0x18000fca7  mov     [rbp+var_8], eax
0x18000fcaa  lea     rax, [rbp+arg_18]
0x18000fcae  mov     [rsp+50h+var_30], rax; unsigned int *
0x18000fcb3  mov     [rbp+var_10], r14
0x18000fcb7  mov     dword ptr [rbp+arg_18], 0
0x18000fcbe  call    ?LoadFromCVar@CUntypedValue@@SAJPEAVCPtrSource@@AEAVCVar@@KPEAVCFastHeap@@AEAKH@Z; CUntypedValue::LoadFromCVar(CPtrSource *,CVar &,ulong,CFastHeap *,ulong &,int)
0x18000fcc3  mov     ebx, eax
0x18000fcc5  test    eax, eax
0x18000fcc7  js      loc_18000FF79
0x18000fccd  cmp     dword ptr [rbp+arg_18], 0FFFh
0x18000fcd4  jz      loc_18000FFC5
0x18000fcda  mov     rdi, [r14]
0x18000fcdd  lea     rcx, [rbp+var_20]
0x18000fce1  mov     r8d, r15d
0x18000fce4  mov     edx, r12d
0x18000fce7  call    ??$MixedSizeMultiply@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeMultiply<int>(SafeInt<unsigned __int64>,int)
0x18000fcec  mov     rdx, [rbp+var_20]
0x18000fcf0  lea     rcx, [rbp+var_20]
0x18000fcf4  xor     r8d, r8d
0x18000fcf7  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x18000fcfc  mov     eax, dword ptr [rbp+var_20]
0x18000fcff  mov     r8d, r15d
0x18000fd02  cdq
0x18000fd03  and     edx, 1Fh
0x18000fd06  add     eax, edx
0x18000fd08  mov     ecx, eax
0x18000fd0a  and     eax, 1Fh
0x18000fd0d  sar     ecx, 5
0x18000fd10  sub     eax, edx
0x18000fd12  movsxd  rcx, ecx
0x18000fd15  lea     rdx, [rdi+rcx*4]
0x18000fd19  mov     ecx, [rdi+rcx*4]
0x18000fd1c  btr     ecx, eax
0x18000fd1f  mov     [rdx], ecx
0x18000fd21  mov     edx, r12d
0x18000fd24  mov     rdi, [r14]
0x18000fd27  lea     rcx, [rbp+var_20]
0x18000fd2b  call    ??$MixedSizeMultiply@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeMultiply<int>(SafeInt<unsigned __int64>,int)
0x18000fd30  mov     rdx, [rbp+var_20]
0x18000fd34  lea     rcx, [rbp+var_20]
0x18000fd38  mov     r8d, 1
0x18000fd3e  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x18000fd43  mov     eax, dword ptr [rbp+var_20]
0x18000fd46  cdq
0x18000fd47  and     edx, 1Fh
0x18000fd4a  add     eax, edx
0x18000fd4c  mov     ecx, eax
0x18000fd4e  and     eax, 1Fh
0x18000fd51  sar     ecx, 5
0x18000fd54  sub     eax, edx
0x18000fd56  movsxd  rcx, ecx
0x18000fd59  lea     rdx, [rdi+rcx*4]
0x18000fd5d  mov     ecx, [rdi+rcx*4]
0x18000fd60  btr     ecx, eax
0x18000fd63  mov     [rdx], ecx
0x18000fd65  mov     rcx, [rsi+20h]
0x18000fd69  mov     rax, [rcx]
0x18000fd6c  mov     rax, [rax+18h]
0x18000fd70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd75  xor     eax, eax
0x18000fd77  lea     r11, [rsp+50h+var_s0]
0x18000fd7c  mov     rbx, [r11+30h]
0x18000fd80  mov     rsi, [r11+38h]
0x18000fd84  mov     rsp, r11
0x18000fd87  pop     r15
0x18000fd89  pop     r14
0x18000fd8b  pop     r12
0x18000fd8d  pop     rdi
0x18000fd8e  pop     rbp
0x18000fd8f  retn
0x18000fd90  mov     eax, r8d
0x18000fd93  and     eax, 0FFFh
0x18000fd98  cmp     eax, 12h
0x18000fd9b  jz      loc_18000FED9; jumptable 000000018000FF6D cases 3,19
0x18000fda1  xor     edx, edx
0x18000fda3  add     eax, 0FFFFFFFEh; switch 103 cases
0x18000fda6  cmp     eax, 66h
0x18000fda9  jbe     loc_18000FF52
0x18000fdaf  mov     ecx, 2000h; jumptable 000000018000FF6D default case, cases 6,7,9,10,12,14,15,18,22-100
0x18000fdb4  movzx   eax, dx
0x18000fdb7  or      ax, cx
0x18000fdba  test    ecx, r8d
0x18000fdbd  cmovz   ax, dx
0x18000fdc1  cmp     r9w, ax
0x18000fdc5  jz      loc_18000FC1E
0x18000fdcb  mov     ecx, r8d; unsigned int
0x18000fdce  call    ?GetVARTYPE@CType@@SAGK@Z; CType::GetVARTYPE(ulong)
0x18000fdd3  movzx   edx, ax
0x18000fdd6  mov     rcx, rdi
0x18000fdd9  call    cs:__imp_?ChangeTypeTo@CVar@@QEAAHG@Z; CVar::ChangeTypeTo(ushort)
0x18000fddf  test    eax, eax
0x18000fde1  jnz     loc_18000FC1E
0x18000fde7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000fded  mov     rcx, rax
0x18000fdf0  mov     edx, 80041005h
0x18000fdf5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000fdfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe02  lea     rax, WPP_GLOBAL_Control
0x18000fe09  cmp     rcx, rax
0x18000fe0c  jz      short loc_18000FE35
0x18000fe0e  test    byte ptr [rcx+1Ch], 1
0x18000fe12  jz      short loc_18000FE35
0x18000fe14  cmp     [rcx+19h], r15b
0x18000fe18  jb      short loc_18000FE35
0x18000fe1a  mov     edx, 60h ; '`'
0x18000fe1f  mov     rcx, [rcx+10h]
0x18000fe23  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18000fe2a  mov     r9d, 80041005h
0x18000fe30  call    WPP_SF_d
0x18000fe35  mov     eax, 80041005h
0x18000fe3a  jmp     loc_18000FD77
0x18000fe3f  movzx   edx, word ptr [rbx+4]
0x18000fe43  lea     rcx, [rbp+arg_18]
0x18000fe47  mov     rdi, [rsi+30h]
0x18000fe4b  mov     r15d, 2
0x18000fe51  mov     r8d, r15d
0x18000fe54  call    ??$MixedSizeMultiply@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeMultiply<int>(SafeInt<unsigned __int64>,int)
0x18000fe59  mov     rdx, [rbp+arg_18]
0x18000fe5d  lea     rcx, [rbp+arg_18]
0x18000fe61  xor     r8d, r8d
0x18000fe64  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x18000fe69  mov     eax, dword ptr [rbp+arg_18]
0x18000fe6c  mov     r8d, r15d
0x18000fe6f  cdq
0x18000fe70  and     edx, 1Fh
0x18000fe73  add     eax, edx
0x18000fe75  mov     ecx, eax
0x18000fe77  and     eax, 1Fh
0x18000fe7a  sar     ecx, 5
0x18000fe7d  sub     eax, edx
0x18000fe7f  movsxd  rcx, ecx
0x18000fe82  lea     rdx, [rdi+rcx*4]
0x18000fe86  mov     ecx, [rdi+rcx*4]
0x18000fe89  bts     ecx, eax
0x18000fe8c  mov     [rdx], ecx
0x18000fe8e  lea     rcx, [rbp+arg_18]
0x18000fe92  movzx   edx, word ptr [rbx+4]
0x18000fe96  mov     rdi, [rsi+30h]
0x18000fe9a  call    ??$MixedSizeMultiply@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeMultiply<int>(SafeInt<unsigned __int64>,int)
0x18000fe9f  mov     rdx, [rbp+arg_18]
0x18000fea3  lea     rcx, [rbp+arg_18]
0x18000fea7  mov     r8d, 1
0x18000fead  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x18000feb2  mov     eax, dword ptr [rbp+arg_18]
0x18000feb5  cdq
0x18000feb6  and     edx, 1Fh
0x18000feb9  add     eax, edx
0x18000febb  mov     ecx, eax
0x18000febd  and     eax, 1Fh
0x18000fec0  sar     ecx, 5
0x18000fec3  sub     eax, edx
0x18000fec5  movsxd  rcx, ecx
0x18000fec8  lea     rdx, [rdi+rcx*4]
0x18000fecc  mov     ecx, [rdi+rcx*4]
0x18000fecf  btr     ecx, eax
0x18000fed2  mov     [rdx], ecx
0x18000fed4  jmp     loc_18000FD75
0x18000fed9  mov     edx, 3; jumptable 000000018000FF6D cases 3,19
0x18000fede  jmp     def_18000FF6D; jumptable 000000018000FF6D default case, cases 6,7,9,10,12,14,15,18,22-100
0x18000fee3  mov     eax, ecx
0x18000fee5  btr     eax, 0Dh
0x18000fee9  cmp     eax, 8
0x18000feec  jnz     loc_18000FBE8
0x18000fef2  jmp     loc_18000FC1E
0x18000fef7  movzx   edx, word ptr [rbx+4]
0x18000fefb  lea     rcx, [rbp+var_20]
0x18000feff  mov     r12, [r14]
0x18000ff02  mov     r8d, r15d
0x18000ff05  call    ??$MixedSizeMultiply@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeMultiply<int>(SafeInt<unsigned __int64>,int)
0x18000ff0a  mov     rdx, [rbp+var_20]
0x18000ff0e  lea     rcx, [rbp+var_20]
0x18000ff12  xor     r8d, r8d
0x18000ff15  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x18000ff1a  mov     rcx, [rbp+var_20]
0x18000ff1e  mov     eax, ecx
0x18000ff20  cdq
0x18000ff21  and     edx, 1Fh
0x18000ff24  add     eax, edx
0x18000ff26  sar     eax, 5
0x18000ff29  cdqe
0x18000ff2b  and     ecx, 8000001Fh
0x18000ff31  jge     short loc_18000FF3A
0x18000ff33  dec     ecx
0x18000ff35  or      ecx, 0FFFFFFE0h
0x18000ff38  inc     ecx
0x18000ff3a  mov     eax, [r12+rax*4]
0x18000ff3e  shr     eax, cl
0x18000ff40  test    al, 1
0x18000ff42  jnz     loc_18000FC76
0x18000ff48  mov     ecx, 1
0x18000ff4d  jmp     loc_18000FC78
0x18000ff52  lea     r10, __ImageBase
0x18000ff59  movzx   eax, ds:(byte_1800100DC - 180000000h)[r10+rax]
0x18000ff62  mov     ecx, ds:(jpt_18000FF6D - 180000000h)[r10+rax*4]
0x18000ff6a  add     rcx, r10
0x18000ff6d  jmp     rcx; switch jump
0x18000ff6f  mov     edx, 0Bh; jumptable 000000018000FF6D case 11
0x18000ff74  jmp     def_18000FF6D; jumptable 000000018000FF6D default case, cases 6,7,9,10,12,14,15,18,22-100
0x18000ff79  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000ff7f  mov     rcx, rax
0x18000ff82  mov     edx, ebx
0x18000ff84  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000ff8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff91  lea     rax, WPP_GLOBAL_Control
0x18000ff98  cmp     rcx, rax
0x18000ff9b  jnz     loc_180010086
  ... truncated ...
```
