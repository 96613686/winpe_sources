# CClassPart::ValidateBuffer(uchar *,unsigned __int64)

- ea: `0x180019410`
- end: `0x180019c5d`
- name: `?ValidateBuffer@CClassPart@@SA_KPEAE_K@Z`
- size: `2125`
- prototype: `unsigned __int64 __fastcall(unsigned __int8 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180017eb0`
- `0x180018f50`
- `0x18007ab50`

## callees

- `0x180014360`
- `0x180019210`
- `0x180019410`
- `0x180019c70`
- `0x18001a5a0`
- `0x18001a7c0`
- `0x18001cb00`
- `0x18001d860`
- `0x180035b08`
- `0x18006fa4c`
- `0x1800919b0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180019798`
- `wbemcomn!GetMemLogObject` at `0x180019801`
- `wbemcomn!GetMemLogObject` at `0x18001986a`
- `wbemcomn!GetMemLogObject` at `0x1800198cf`
- `wbemcomn!GetMemLogObject` at `0x180019938`
- `wbemcomn!GetMemLogObject` at `0x18001999d`
- `wbemcomn!GetMemLogObject` at `0x180019a06`
- `wbemcomn!GetMemLogObject` at `0x180019a6b`
- `wbemcomn!GetMemLogObject` at `0x180019acd`
- `wbemcomn!GetMemLogObject` at `0x180019b32`
- `wbemcomn!GetMemLogObject` at `0x180019b97`
- `wbemcomn!GetMemLogObject` at `0x180019bfc`
- `wbemcomn!GetMemLogObject` at `0x180019798`
- `wbemcomn!GetMemLogObject` at `0x180019801`
- `wbemcomn!GetMemLogObject` at `0x18001986a`
- `wbemcomn!GetMemLogObject` at `0x1800198cf`
- `wbemcomn!GetMemLogObject` at `0x180019938`
- `wbemcomn!GetMemLogObject` at `0x18001999d`
- `wbemcomn!GetMemLogObject` at `0x180019a06`
- `wbemcomn!GetMemLogObject` at `0x180019a6b`
- `wbemcomn!GetMemLogObject` at `0x180019acd`
- `wbemcomn!GetMemLogObject` at `0x180019b32`
- `wbemcomn!GetMemLogObject` at `0x180019b97`
- `wbemcomn!GetMemLogObject` at `0x180019bfc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800197a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001980f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019878`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800198dd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019946`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800199ab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019a14`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019a79`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019adb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019b40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019ba5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019c0a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800197a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001980f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019878`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800198dd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019946`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800199ab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019a14`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019a79`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019adb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019b40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019ba5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180019c0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
unsigned __int64 __fastcall CClassPart::ValidateBuffer(unsigned __int8 *a1, unsigned __int64 a2)
{
  unsigned __int8 *v4; // r13
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rdx
  int v9; // r15d
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // r12
  unsigned __int64 v12; // rdi
  unsigned __int8 *v13; // r15
  unsigned __int64 v14; // r8
  __int64 v15; // rbx
  __int64 v16; // rax
  unsigned int v17; // esi
  unsigned int v18; // edi
  unsigned __int8 *v19; // rbx
  int *v20; // rdx
  unsigned int v21; // ebx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v24; // rax
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  CMemoryLog *v33; // rax
  CMemoryLog *v34; // rax
  int pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  char v36; // [rsp+28h] [rbp-D8h] BYREF
  void **v37; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 *v38; // [rsp+38h] [rbp-C8h]
  unsigned __int8 *v39; // [rsp+40h] [rbp-C0h]
  _DWORD v40[4]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h]
  __int64 (__fastcall **v42)(_QWORD); // [rsp+60h] [rbp-A0h] BYREF
  char v43; // [rsp+68h] [rbp-98h] BYREF
  char v44; // [rsp+70h] [rbp-90h] BYREF
  char v45; // [rsp+78h] [rbp-88h] BYREF
  void ***v46; // [rsp+80h] [rbp-80h]
  __int64 v47; // [rsp+88h] [rbp-78h]
  unsigned __int8 *v48; // [rsp+90h] [rbp-70h]
  unsigned __int8 *v49; // [rsp+98h] [rbp-68h]
  int v50; // [rsp+A0h] [rbp-60h]
  int v51; // [rsp+B0h] [rbp-50h]
  unsigned __int8 *v52; // [rsp+B8h] [rbp-48h]
  __int64 v53; // [rsp+C0h] [rbp-40h]
  __int64 v54; // [rsp+D0h] [rbp-30h]
  __int64 (__fastcall ***v55)(_QWORD); // [rsp+D8h] [rbp-28h]
  __int64 v56; // [rsp+E0h] [rbp-20h]
  unsigned __int8 *v57; // [rsp+F8h] [rbp-8h]
  char *v58; // [rsp+100h] [rbp+0h]
  unsigned __int8 *v59; // [rsp+108h] [rbp+8h]
  unsigned __int8 *v60; // [rsp+110h] [rbp+10h]
  unsigned int v61; // [rsp+118h] [rbp+18h]
  unsigned int v62; // [rsp+11Ch] [rbp+1Ch]
  char *v63; // [rsp+120h] [rbp+20h]
  _DWORD *v64; // [rsp+128h] [rbp+28h]
  unsigned __int8 *v65; // [rsp+130h] [rbp+30h]
  _DWORD v66[4]; // [rsp+138h] [rbp+38h] BYREF
  char *v67; // [rsp+148h] [rbp+48h]

  if ( &a1[a2] <= a1 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "SafeIntException(ERROR_INVALID_PARAMETER)");
    }
    pExceptionObject = 87;
    throw (SafeIntException *)&pExceptionObject;
  }
  if ( a2 < 0xD )
  {
    v24 = GetMemLogObject();
    CMemoryLog::Write(v24, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "SafeIntException(ERROR_INVALID_PARAMETER)");
    }
    pExceptionObject = 87;
    throw (SafeIntException *)&pExceptionObject;
  }
  if ( *(unsigned int *)a1 > a2 )
  {
    v25 = GetMemLogObject();
    CMemoryLog::Write(v25, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "SafeIntException(ERROR_INVALID_DATA)");
    }
    pExceptionObject = 13;
    throw (SafeIntException *)&pExceptionObject;
  }
  v4 = a1 + 13;
  v5 = CCompressedStringList::ValidateBuffer(a1 + 13, a2 - 13);
  v6 = *(_QWORD *)SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(&pExceptionObject, 13, v5);
  if ( a2 < v6 )
  {
    pExceptionObject = 534;
    throw (SafeIntException *)&pExceptionObject;
  }
  if ( a2 - v6 < 4 )
  {
    v26 = GetMemLogObject();
    CMemoryLog::Write(v26, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
        "SafeIntException(ERROR_INVALID_PARAMETER)");
    }
    pExceptionObject = 87;
    throw (SafeIntException *)&pExceptionObject;
  }
  v7 = *(unsigned int *)&a1[v6];
  if ( v7 > a2 - v6 )
  {
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids,
        "SafeIntException(ERROR_INVALID_DATA)");
    }
    pExceptionObject = 13;
    throw (SafeIntException *)&pExceptionObject;
  }
  v8 = *(_QWORD *)SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(&pExceptionObject, v6, v7);
  if ( a2 < v8 )
  {
    pExceptionObject = 534;
    throw (SafeIntException *)&pExceptionObject;
  }
  if ( a2 - v8 < 4 )
  {
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_8db10d0debd535326cee342840d89e0d_Traceguids,
        "SafeIntException(ERROR_INVALID_PARAMETER)");
    }
    pExceptionObject = 87;
    throw (SafeIntException *)&pExceptionObject;
  }
  v9 = *(_DWORD *)&a1[v8];
  if ( 8 * v9 + 4LL > a2 - v8 )
  {
    v29 = GetMemLogObject();
    CMemoryLog::Write(v29, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_8db10d0debd535326cee342840d89e0d_Traceguids,
        "SafeIntException(ERROR_INVALID_DATA)");
    }
    pExceptionObject = 13;
    throw (SafeIntException *)&pExceptionObject;
  }
  if ( v9 < 0 )
  {
    v30 = GetMemLogObject();
    CMemoryLog::Write(v30, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "SafeIntException(ERROR_INVALID_DATA)");
    }
    pExceptionObject = 13;
    throw (SafeIntException *)&pExceptionObject;
  }
  v10 = *(_QWORD *)SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(&pExceptionObject, v8, 8 * v9 + 4LL);
  if ( a2 < v10 )
  {
    pExceptionObject = 534;
    throw (SafeIntException *)&pExceptionObject;
  }
  _mm_lfence();
  v11 = *(unsigned int *)(a1 + 9);
  if ( v11 > a2 - v10 )
  {
    v31 = GetMemLogObject();
    CMemoryLog::Write(v31, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "SafeIntException(ERROR_INVALID_DATA)");
    }
    pExceptionObject = 13;
    throw (SafeIntException *)&pExceptionObject;
  }
  if ( (int)CBitBlockTable<2>::GetNecessaryBytes((unsigned int)v9) > v11 )
  {
    v32 = GetMemLogObject();
    CMemoryLog::Write(v32, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_8db10d0debd535326cee342840d89e0d_Traceguids,
        "SafeIntException(ERROR_INVALID_DATA)");
    }
    pExceptionObject = 13;
    throw (SafeIntException *)&pExceptionObject;
  }
  v12 = *(_QWORD *)SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(
                     &pExceptionObject,
                     v10,
                     (unsigned int)v11);
  if ( a2 < v12 )
  {
    pExceptionObject = 534;
    throw (SafeIntException *)&pExceptionObject;
  }
  v13 = &a1[v12];
  v14 = CFastHeap::ValidateBuffer(&a1[v12], a2 - v12);
  v41 = 0;
  if ( *(int *)&a1[v12] >= 0 )
  {
    v39 = &a1[v12];
    v38 = v13 + 12;
  }
  else
  {
    v38 = v13 + 4;
    v39 = (unsigned __int8 *)v40;
    v40[0] = *(_DWORD *)v13 & 0x7FFFFFFF;
    v40[1] = v40[0];
    v40[2] = 0;
  }
  if ( *(_QWORD *)SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(&pExceptionObject, v12, v14) > (unsigned __int64)*(unsigned int *)a1 )
  {
    v33 = GetMemLogObject();
    CMemoryLog::Write(v33, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "SafeIntException(ERROR_INVALID_DATA)");
    }
    pExceptionObject = 13;
    throw (SafeIntException *)&pExceptionObject;
  }
  v37 = &DummyClassPartContainer::`vftable';
  CClassPart::CClassPart((CClassPart *)&v42);
  v46 = &v37;
  v47 = 0;
  v48 = a1;
  v49 = v4;
  v50 = -1;
  v15 = *(unsigned int *)v4;
  v16 = (*v42)(&v42);
  v51 = *(_DWORD *)&v4[v15];
  v52 = &v4[v15 + 4];
  v53 = v16;
  v55 = &v42;
  v56 = 0;
  v54 = v42[1](&v42);
  v57 = &v52[v51 - 4];
  v58 = &v43;
  v17 = *(_DWORD *)(v48 + 9);
  v18 = *(_DWORD *)v57;
  v59 = &v57[8 * *(_DWORD *)v57 + 4];
  v19 = v59;
  v60 = &v19[(int)CBitBlockTable<2>::GetNecessaryBytes(v18)];
  v61 = v17;
  v62 = v18;
  v63 = &v44;
  v20 = (int *)&v59[v17];
  v67 = &v45;
  if ( *v20 >= 0 )
  {
    v65 = &v59[v17];
    v64 = v20 + 3;
  }
  else
  {
    v64 = v20 + 1;
    v65 = (unsigned __int8 *)v66;
    v66[0] = *v20 & 0x7FFFFFFF;
    v66[1] = v66[0];
    v66[2] = 0;
  }
  if ( (int)CClassPart::IsValidClassPart((CClassPart *)&v42) < 0 )
  {
    v34 = GetMemLogObject();
    CMemoryLog::Write(v34, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
        "CX_Exception()");
    }
    throw (CX_Exception *)&v36;
  }
  v21 = *(_DWORD *)a1;
  CClassPart::~CClassPart((CClassPart *)&v42);
  return v21;
}

```

## disassembly

```asm
0x180019410  push    rbp
0x180019412  push    rbx
0x180019413  push    rsi
0x180019414  push    rdi
0x180019415  push    r12
0x180019417  push    r13
0x180019419  push    r14
0x18001941b  push    r15
0x18001941d  lea     rbp, [rsp-68h]
0x180019422  sub     rsp, 168h
0x180019429  mov     rax, cs:__security_cookie
0x180019430  xor     rax, rsp
0x180019433  mov     [rbp+0A0h+var_50], rax
0x180019437  mov     rsi, rdx
0x18001943a  mov     r14, rcx
0x18001943d  lea     rax, [rcx+rdx]
0x180019441  cmp     rax, rcx
0x180019444  jbe     loc_180019798
0x18001944a  mov     ebx, 0Dh
0x18001944f  cmp     rdx, rbx
0x180019452  jb      loc_180019801
0x180019458  mov     eax, [rcx]
0x18001945a  cmp     rax, rdx
0x18001945d  ja      loc_18001986A
0x180019463  lea     r13, [rcx+0Dh]
0x180019467  add     rdx, 0FFFFFFFFFFFFFFF3h; unsigned __int64
0x18001946b  mov     rcx, r13; unsigned __int8 *
0x18001946e  call    ?ValidateBuffer@CCompressedStringList@@SA_KPEAE_K@Z; CCompressedStringList::ValidateBuffer(uchar *,unsigned __int64)
0x180019473  mov     r8, rax
0x180019476  mov     edx, ebx
0x180019478  lea     rcx, [rsp+1A0h+pExceptionObject]
0x18001947d  call    ??$MixedSizeAddition@_K@?$SafeInt@_K@@CA?AV0@V0@_K@Z; SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(SafeInt<unsigned __int64>,unsigned __int64)
0x180019482  mov     rdx, [rax]
0x180019485  cmp     rsi, rdx
0x180019488  jb      loc_18001970C
0x18001948e  mov     rax, rsi
0x180019491  sub     rax, rdx
0x180019494  cmp     rax, 4
0x180019498  jb      loc_1800198CF
0x18001949e  mov     r8d, [rdx+r14]
0x1800194a2  cmp     r8, rax
0x1800194a5  ja      loc_180019938
0x1800194ab  lea     rcx, [rsp+1A0h+pExceptionObject]
0x1800194b0  call    ??$MixedSizeAddition@_K@?$SafeInt@_K@@CA?AV0@V0@_K@Z; SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(SafeInt<unsigned __int64>,unsigned __int64)
0x1800194b5  mov     rdx, [rax]
0x1800194b8  cmp     rsi, rdx
0x1800194bb  jb      loc_180019726
0x1800194c1  mov     r8, rsi
0x1800194c4  sub     r8, rdx
0x1800194c7  cmp     r8, 4
0x1800194cb  jb      loc_18001999D
0x1800194d1  mov     r15d, [rdx+r14]
0x1800194d5  lea     eax, ds:0[r15*8]
0x1800194dd  movsxd  rcx, eax
0x1800194e0  add     rcx, 4
0x1800194e4  cmp     rcx, r8
0x1800194e7  ja      loc_180019A06
0x1800194ed  test    r15d, r15d
0x1800194f0  js      loc_180019A6B
0x1800194f6  mov     r8, rcx
0x1800194f9  lea     rcx, [rsp+1A0h+pExceptionObject]
0x1800194fe  call    ??$MixedSizeAddition@_K@?$SafeInt@_K@@CA?AV0@V0@_K@Z; SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(SafeInt<unsigned __int64>,unsigned __int64)
0x180019503  mov     rdi, [rax]
0x180019506  cmp     rsi, rdi
0x180019509  jb      loc_180019740
0x18001950f  mov     rax, rsi
0x180019512  sub     rax, rdi
0x180019515  lfence
0x180019518  mov     r12d, [r14+9]
0x18001951c  cmp     r12, rax
0x18001951f  ja      loc_180019ACD
0x180019525  mov     ecx, r15d
0x180019528  call    ?GetNecessaryBytes@?$CBitBlockTable@$01@@SAHH@Z; CBitBlockTable<2>::GetNecessaryBytes(int)
0x18001952d  movsxd  rcx, eax
0x180019530  cmp     rcx, r12
0x180019533  ja      loc_180019B32
0x180019539  mov     r8d, r12d
0x18001953c  mov     rdx, rdi
0x18001953f  lea     rcx, [rsp+1A0h+pExceptionObject]
0x180019544  call    ??$MixedSizeAddition@_K@?$SafeInt@_K@@CA?AV0@V0@_K@Z; SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(SafeInt<unsigned __int64>,unsigned __int64)
0x180019549  mov     rdi, [rax]
0x18001954c  cmp     rsi, rdi
0x18001954f  jb      loc_18001975A
0x180019555  sub     rsi, rdi
0x180019558  lea     r15, [rdi+r14]
0x18001955c  mov     rdx, rsi; unsigned __int64
0x18001955f  mov     rcx, r15; unsigned __int8 *
0x180019562  call    ?ValidateBuffer@CFastHeap@@SA_KPEAE_K@Z; CFastHeap::ValidateBuffer(uchar *,unsigned __int64)
0x180019567  mov     r8, rax
0x18001956a  xor     r12d, r12d
0x18001956d  mov     [rsp+1A0h+var_148], r12
0x180019572  cmp     [r15], r12d
0x180019575  jge     loc_180019774
0x18001957b  lea     rcx, [r15+4]
0x18001957f  mov     [rsp+1A0h+var_168], rcx
0x180019584  lea     rax, [rsp+1A0h+var_158]
0x180019589  mov     [rsp+1A0h+var_160], rax
0x18001958e  mov     ecx, [r15]
0x180019591  btr     ecx, 1Fh
0x180019595  mov     [rsp+1A0h+var_158], ecx
0x180019599  mov     [rsp+1A0h+var_154], ecx
0x18001959d  mov     [rsp+1A0h+var_150], r12d
0x1800195a2  mov     rdx, rdi
0x1800195a5  lea     rcx, [rsp+1A0h+pExceptionObject]
0x1800195aa  call    ??$MixedSizeAddition@_K@?$SafeInt@_K@@CA?AV0@V0@_K@Z; SafeInt<unsigned __int64>::MixedSizeAddition<unsigned __int64>(SafeInt<unsigned __int64>,unsigned __int64)
0x1800195af  mov     ecx, [r14]
0x1800195b2  cmp     [rax], rcx
0x1800195b5  ja      loc_180019B97
0x1800195bb  lea     rax, ??_7DummyClassPartContainer@@6B@; const DummyClassPartContainer::`vftable'
0x1800195c2  mov     [rsp+1A0h+var_170], rax
0x1800195c7  lea     rcx, [rsp+1A0h+var_140]; this
0x1800195cc  call    ??0CClassPart@@QEAA@XZ; CClassPart::CClassPart(void)
0x1800195d1  nop
0x1800195d2  lea     rax, [rsp+1A0h+var_170]
0x1800195d7  mov     [rbp+0A0h+var_120], rax
0x1800195db  mov     [rbp+0A0h+var_118], r12
0x1800195df  mov     [rbp+0A0h+var_110], r14
0x1800195e3  mov     [rbp+0A0h+var_108], r13
0x1800195e7  mov     [rbp+0A0h+var_100], 0FFFFFFFFh
0x1800195ee  mov     ebx, [r13+0]
0x1800195f2  mov     rax, [rsp+1A0h+var_140]
0x1800195f7  lea     rcx, [rsp+1A0h+var_140]
0x1800195fc  mov     rax, [rax]
0x1800195ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019604  mov     ecx, [rbx+r13]
0x180019608  mov     [rbp+0A0h+var_F0], ecx
0x18001960b  lea     rcx, [rbx+4]
0x18001960f  add     rcx, r13
0x180019612  mov     [rbp+0A0h+var_E8], rcx
0x180019616  mov     [rbp+0A0h+var_E0], rax
0x18001961a  lea     rax, [rsp+1A0h+var_140]
0x18001961f  mov     [rbp+0A0h+var_C8], rax
0x180019623  mov     [rbp+0A0h+var_C0], r12
0x180019627  mov     rax, [rsp+1A0h+var_140]
0x18001962c  lea     rcx, [rsp+1A0h+var_140]
0x180019631  mov     rax, [rax+8]
0x180019635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001963a  mov     [rbp+0A0h+var_D0], rax
0x18001963e  mov     ecx, [rbp+0A0h+var_F0]
0x180019641  mov     rdx, [rbp+0A0h+var_E8]
0x180019645  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180019649  add     rdx, rcx
0x18001964c  mov     [rbp+0A0h+var_A8], rdx
0x180019650  lea     rax, [rsp+1A0h+var_138]
0x180019655  mov     [rbp+0A0h+var_A0], rax
0x180019659  mov     rax, [rbp+0A0h+var_110]
0x18001965d  mov     esi, [rax+9]
0x180019660  mov     edi, [rdx]
0x180019662  lea     eax, ds:4[rdi*8]
0x180019669  movsxd  rbx, eax
0x18001966c  add     rbx, rdx
0x18001966f  mov     [rbp+0A0h+var_98], rbx
0x180019673  mov     ecx, edi
0x180019675  call    ?GetNecessaryBytes@?$CBitBlockTable@$01@@SAHH@Z; CBitBlockTable<2>::GetNecessaryBytes(int)
0x18001967a  movsxd  rcx, eax
0x18001967d  add     rcx, rbx
0x180019680  mov     [rbp+0A0h+var_90], rcx
0x180019684  mov     [rbp+0A0h+var_88], esi
0x180019687  mov     [rbp+0A0h+var_84], edi
0x18001968a  lea     rax, [rsp+1A0h+var_130]
0x18001968f  mov     [rbp+0A0h+var_80], rax
0x180019693  mov     edx, esi
0x180019695  add     rdx, [rbp+0A0h+var_98]
0x180019699  lea     rax, [rsp+1A0h+var_128]
0x18001969e  mov     [rbp+0A0h+var_58], rax
0x1800196a2  cmp     [rdx], r12d
0x1800196a5  jge     loc_180019787
0x1800196ab  lea     rax, [rdx+4]
0x1800196af  mov     [rbp+0A0h+var_78], rax
0x1800196b3  lea     rax, [rbp+0A0h+var_68]
0x1800196b7  mov     [rbp+0A0h+var_70], rax
0x1800196bb  mov     eax, [rdx]
0x1800196bd  btr     eax, 1Fh
0x1800196c1  mov     [rbp+0A0h+var_68], eax
0x1800196c4  mov     [rbp+0A0h+var_64], eax
0x1800196c7  mov     [rbp+0A0h+var_60], r12d
0x1800196cb  lea     rcx, [rsp+1A0h+var_140]; this
0x1800196d0  call    ?IsValidClassPart@CClassPart@@QEAAJXZ; CClassPart::IsValidClassPart(void)
0x1800196d5  test    eax, eax
0x1800196d7  js      loc_180019BFC
0x1800196dd  mov     ebx, [r14]
0x1800196e0  lea     rcx, [rsp+1A0h+var_140]; this
0x1800196e5  call    ??1CClassPart@@QEAA@XZ; CClassPart::~CClassPart(void)
0x1800196ea  mov     eax, ebx
0x1800196ec  mov     rcx, [rbp+0A0h+var_50]
0x1800196f0  xor     rcx, rsp; StackCookie
0x1800196f3  call    __security_check_cookie
0x1800196f8  add     rsp, 168h
0x1800196ff  pop     r15
0x180019701  pop     r14
0x180019703  pop     r13
0x180019705  pop     r12
0x180019707  pop     rdi
0x180019708  pop     rsi
0x180019709  pop     rbx
0x18001970a  pop     rbp
0x18001970b  retn
0x18001970c  mov     [rsp+1A0h+pExceptionObject], 216h
0x180019714  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001971b  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x180019720  call    _CxxThrowException_0
0x180019726  mov     [rsp+1A0h+pExceptionObject], 216h
0x18001972e  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180019735  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18001973a  call    _CxxThrowException_0
0x180019740  mov     [rsp+1A0h+pExceptionObject], 216h
0x180019748  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001974f  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x180019754  call    _CxxThrowException_0
0x18001975a  mov     [rsp+1A0h+pExceptionObject], 216h
0x180019762  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180019769  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18001976e  call    _CxxThrowException_0
0x180019774  mov     [rsp+1A0h+var_160], r15
0x180019779  lea     rax, [r15+0Ch]
0x18001977d  mov     [rsp+1A0h+var_168], rax
0x180019782  jmp     loc_1800195A2
0x180019787  mov     [rbp+0A0h+var_70], rdx
0x18001978b  lea     rax, [rdx+0Ch]
0x18001978f  mov     [rbp+0A0h+var_78], rax
0x180019793  jmp     loc_1800196CB
0x180019798  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001979e  mov     edx, 0FFFFFFFEh
0x1800197a3  mov     rcx, rax
0x1800197a6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800197ac  lea     rax, WPP_GLOBAL_Control
0x1800197b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197ba  cmp     rcx, rax
0x1800197bd  jz      short loc_1800197E7
0x1800197bf  test    byte ptr [rcx+1Ch], 1
0x1800197c3  jz      short loc_1800197E7
0x1800197c5  cmp     byte ptr [rcx+19h], 2
0x1800197c9  jb      short loc_1800197E7
0x1800197cb  mov     edx, 0Ah
0x1800197d0  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x1800197d7  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800197de  mov     rcx, [rcx+10h]
0x1800197e2  call    WPP_SF_s
0x1800197e7  mov     [rsp+1A0h+pExceptionObject], 57h ; 'W'
0x1800197ef  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x1800197f6  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x1800197fb  call    _CxxThrowException_0
0x180019801  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180019807  mov     edx, 0FFFFFFFEh
0x18001980c  mov     rcx, rax
0x18001980f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180019815  lea     rax, WPP_GLOBAL_Control
0x18001981c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019823  cmp     rcx, rax
0x180019826  jz      short loc_180019850
0x180019828  test    byte ptr [rcx+1Ch], 1
0x18001982c  jz      short loc_180019850
0x18001982e  cmp     byte ptr [rcx+19h], 2
0x180019832  jb      short loc_180019850
0x180019834  mov     edx, 0Bh
0x180019839  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x180019840  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180019847  mov     rcx, [rcx+10h]
0x18001984b  call    WPP_SF_s
0x180019850  mov     [rsp+1A0h+pExceptionObject], 57h ; 'W'
0x180019858  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001985f  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x180019864  call    _CxxThrowException_0
0x18001986a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180019870  mov     edx, 0FFFFFFFEh
0x180019875  mov     rcx, rax
0x180019878  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001987e  lea     rax, WPP_GLOBAL_Control
0x180019885  mov     rcx, cs:WPP_GLOBAL_Control
0x18001988c  cmp     rcx, rax
0x18001988f  jz      short loc_1800198B9
0x180019891  test    byte ptr [rcx+1Ch], 1
0x180019895  jz      short loc_1800198B9
0x180019897  cmp     byte ptr [rcx+19h], 2
0x18001989b  jb      short loc_1800198B9
0x18001989d  mov     edx, 0Ch
0x1800198a2  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_DATA)"
0x1800198a9  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x1800198b0  mov     rcx, [rcx+10h]
0x1800198b4  call    WPP_SF_s
0x1800198b9  mov     [rsp+1A0h+pExceptionObject], ebx
0x1800198bd  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x1800198c4  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x1800198c9  call    _CxxThrowException_0
0x1800198cf  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800198d5  mov     edx, 0FFFFFFFEh
0x1800198da  mov     rcx, rax
0x1800198dd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800198e3  lea     rax, WPP_GLOBAL_Control
0x1800198ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198f1  cmp     rcx, rax
0x1800198f4  jz      short loc_18001991E
0x1800198f6  test    byte ptr [rcx+1Ch], 1
0x1800198fa  jz      short loc_18001991E
0x1800198fc  cmp     byte ptr [rcx+19h], 2
0x180019900  jb      short loc_18001991E
0x180019902  mov     edx, 0Ah
0x180019907  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x18001990e  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x180019915  mov     rcx, [rcx+10h]
  ... truncated ...
```
