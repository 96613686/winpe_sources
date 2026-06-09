# CWbemObjectArrayPacket::IsValid(CWbemClassCache *)

- ea: `0x18001b8b0`
- end: `0x18001c112`
- name: `?IsValid@CWbemObjectArrayPacket@@QEAA_NPEAVCWbemClassCache@@@Z`
- size: `2146`
- prototype: `bool __fastcall(CWbemObjectArrayPacket *__hidden this, struct CWbemClassCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800158e0`

## callees

- `0x180017b28`
- `0x18001b8b0`
- `0x18001c118`
- `0x18001cb40`
- `0x180035b08`
- `0x180056320`
- `0x18006fa4c`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18001bc29`
- `wbemcomn!GetMemLogObject` at `0x18001bc91`
- `wbemcomn!GetMemLogObject` at `0x18001bd00`
- `wbemcomn!GetMemLogObject` at `0x18001bd68`
- `wbemcomn!GetMemLogObject` at `0x18001bdd0`
- `wbemcomn!GetMemLogObject` at `0x18001be38`
- `wbemcomn!GetMemLogObject` at `0x18001bea0`
- `wbemcomn!GetMemLogObject` at `0x18001bf08`
- `wbemcomn!GetMemLogObject` at `0x18001bf71`
- `wbemcomn!GetMemLogObject` at `0x18001bfd2`
- `wbemcomn!GetMemLogObject` at `0x18001c03a`
- `wbemcomn!GetMemLogObject` at `0x18001c0a2`
- `wbemcomn!GetMemLogObject` at `0x18001bc29`
- `wbemcomn!GetMemLogObject` at `0x18001bc91`
- `wbemcomn!GetMemLogObject` at `0x18001bd00`
- `wbemcomn!GetMemLogObject` at `0x18001bd68`
- `wbemcomn!GetMemLogObject` at `0x18001bdd0`
- `wbemcomn!GetMemLogObject` at `0x18001be38`
- `wbemcomn!GetMemLogObject` at `0x18001bea0`
- `wbemcomn!GetMemLogObject` at `0x18001bf08`
- `wbemcomn!GetMemLogObject` at `0x18001bf71`
- `wbemcomn!GetMemLogObject` at `0x18001bfd2`
- `wbemcomn!GetMemLogObject` at `0x18001c03a`
- `wbemcomn!GetMemLogObject` at `0x18001c0a2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bc37`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bc9f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bd0e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bd76`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bdde`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001be46`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001beae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bf16`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bf7f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bfe0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c048`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c0b0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bc37`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bc9f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bd0e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bd76`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bdde`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001be46`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001beae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bf16`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bf7f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001bfe0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c048`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c0b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
bool __fastcall CWbemObjectArrayPacket::IsValid(CWbemObjectArrayPacket *this, struct CWbemClassCache *a2)
{
  unsigned int v4; // edi
  unsigned __int64 v5; // rbx
  unsigned int v6; // eax
  unsigned int v7; // ecx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rcx
  int v11; // eax
  unsigned __int64 v12; // rdx
  __int64 v14; // r8
  unsigned __int64 v15; // rdx
  __int64 v16; // rdx
  unsigned int *v17; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  char v30; // [rsp+20h] [rbp-F8h] BYREF
  int pExceptionObject; // [rsp+24h] [rbp-F4h] BYREF
  int v32; // [rsp+28h] [rbp-F0h] BYREF
  int v33; // [rsp+2Ch] [rbp-ECh] BYREF
  int v34; // [rsp+30h] [rbp-E8h] BYREF
  int v35; // [rsp+34h] [rbp-E4h] BYREF
  int v36; // [rsp+38h] [rbp-E0h] BYREF
  int v37; // [rsp+3Ch] [rbp-DCh] BYREF
  int v38; // [rsp+40h] [rbp-D8h] BYREF
  int v39; // [rsp+44h] [rbp-D4h] BYREF
  int v40; // [rsp+48h] [rbp-D0h] BYREF
  int v41; // [rsp+4Ch] [rbp-CCh] BYREF
  void **v42; // [rsp+50h] [rbp-C8h]
  unsigned __int64 v43; // [rsp+58h] [rbp-C0h]
  unsigned int v44; // [rsp+60h] [rbp-B8h]
  unsigned __int64 v45; // [rsp+68h] [rbp-B0h]
  int v46; // [rsp+70h] [rbp-A8h]
  struct CWbemClassCache *v47; // [rsp+78h] [rbp-A0h]
  _BYTE v48[4]; // [rsp+80h] [rbp-98h] BYREF
  _BYTE v49[4]; // [rsp+84h] [rbp-94h] BYREF
  _BYTE v50[4]; // [rsp+88h] [rbp-90h] BYREF
  int v51; // [rsp+8Ch] [rbp-8Ch]
  unsigned __int64 v52; // [rsp+90h] [rbp-88h]
  unsigned __int64 v53; // [rsp+98h] [rbp-80h]
  int v54; // [rsp+A0h] [rbp-78h]
  unsigned __int64 v55; // [rsp+A8h] [rbp-70h]
  int v56; // [rsp+B0h] [rbp-68h]
  void **v57; // [rsp+B8h] [rbp-60h] BYREF
  _QWORD v58[5]; // [rsp+C0h] [rbp-58h] BYREF
  int v59; // [rsp+E8h] [rbp-30h]
  unsigned int v60; // [rsp+130h] [rbp+18h]

  v4 = 0;
  v60 = 12;
  v5 = *(_QWORD *)this + 12LL;
  v6 = 12;
  while ( 1 )
  {
    v7 = *((_DWORD *)this + 2);
    if ( v6 >= v7 || v4 >= *(_DWORD *)(*(_QWORD *)this + 8LL) )
      break;
    v8 = v7 - v6;
    v58[4] = v5;
    v59 = v8;
    if ( v5 )
    {
      if ( (unsigned int)v8 < 9 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
            "SafeIntException(ERROR_INVALID_PARAMETER)");
        }
        pExceptionObject = 87;
        throw (SafeIntException *)&pExceptionObject;
      }
      if ( *(_DWORD *)v5 != 9 || (v9 = (unsigned int)v8, *(unsigned int *)(v5 + 4) > (unsigned __int64)(v8 - 9)) )
      {
        v19 = GetMemLogObject();
        CMemoryLog::Write(v19, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
            "SafeIntException(ERROR_INVALID_DATA)");
        }
        v32 = 13;
        throw (SafeIntException *)&v32;
      }
    }
    else
    {
      v9 = (unsigned int)v8;
    }
    if ( (unsigned int)v8 <= 9 || !v5 || *(unsigned int *)(v5 + 4) > (unsigned __int64)(v9 - 9) )
      return 0;
    v10 = *(unsigned int *)SafeInt<unsigned long>::MixedSizeAddition<unsigned __int64>(v48);
    v11 = *(unsigned __int8 *)(v5 + 8);
    if ( (_BYTE)v11 == 3 )
    {
      v43 = 0;
      v44 = 0;
      v42 = &CWbemInstancePacket::`vftable';
      if ( v5 + 9 < v5 )
      {
        v24 = GetMemLogObject();
        CMemoryLog::Write(v24, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
            "SafeIntException(ERROR_INVALID_PARAMETER)");
        }
        v37 = 87;
        throw (SafeIntException *)&v37;
      }
      v45 = v5 + 9;
      if ( (unsigned int)v10 < 0x21 )
      {
        v25 = GetMemLogObject();
        CMemoryLog::Write(v25, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
            "SafeIntException(ERROR_INVALID_PARAMETER)");
        }
        v38 = 87;
        throw (SafeIntException *)&v38;
      }
      v46 = v10 - 9;
      if ( *(_DWORD *)(v5 + 9) != 24 || *(_DWORD *)(v5 + 13) > (unsigned int)(v10 - 9) )
      {
        v29 = GetMemLogObject();
        CMemoryLog::Write(v29, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
            "SafeIntException(ERROR_INVALID_DATA)");
        }
        v41 = 13;
        throw (SafeIntException *)&v41;
      }
      v43 = v5;
      v44 = v10;
      if ( *(_DWORD *)v5 != 9 || *(unsigned int *)(v5 + 4) > (unsigned __int64)(v10 - 9) )
      {
        v28 = GetMemLogObject();
        CMemoryLog::Write(v28, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
            "SafeIntException(ERROR_INVALID_DATA)");
        }
        v40 = 13;
        throw (SafeIntException *)&v40;
      }
      v42 = &CWbemClasslessInstancePacket::`vftable';
      if ( !a2 )
      {
        v26 = GetMemLogObject();
        CMemoryLog::Write(v26, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
            "CX_Exception()");
        }
        throw (CX_Exception *)&v30;
      }
      v47 = a2;
      v12 = *(unsigned int *)(v43 + 4);
      if ( (unsigned int)v12 < 0x18 || v12 > (unsigned __int64)v44 - 9 || v12 != *(unsigned int *)(v45 + 4) + 24LL )
      {
        v42 = &CWbemInstancePacket::`vftable';
        return 0;
      }
      v42 = &CWbemInstancePacket::`vftable';
    }
    else if ( v11 == 1 )
    {
      v53 = 0;
      v54 = 0;
      if ( v5 + 9 < v5 )
      {
        v20 = GetMemLogObject();
        CMemoryLog::Write(v20, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
            "SafeIntException(ERROR_INVALID_PARAMETER)");
        }
        v33 = 87;
        throw (SafeIntException *)&v33;
      }
      v55 = v5 + 9;
      if ( (unsigned int)v10 < 0x11 )
      {
        v21 = GetMemLogObject();
        CMemoryLog::Write(v21, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
            "SafeIntException(ERROR_INVALID_PARAMETER)");
        }
        v34 = 87;
        throw (SafeIntException *)&v34;
      }
      v56 = v10 - 9;
      if ( *(_DWORD *)(v5 + 9) != 8 || (v14 = *(unsigned int *)(v5 + 13), (unsigned int)v14 > (int)v10 - 9) )
      {
        v23 = GetMemLogObject();
        CMemoryLog::Write(v23, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
            "SafeIntException(ERROR_INVALID_DATA)");
        }
        v36 = 13;
        throw (SafeIntException *)&v36;
      }
      v53 = v5;
      v54 = v10;
      if ( *(_DWORD *)v5 != 9 || (v15 = *(unsigned int *)(v5 + 4), v15 > v10 - 9) )
      {
        v22 = GetMemLogObject();
        CMemoryLog::Write(v22, -2);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
            "SafeIntException(ERROR_INVALID_DATA)");
        }
        v35 = 13;
        throw (SafeIntException *)&v35;
      }
      if ( (unsigned int)v15 < 8 || v15 != v14 + 8 )
        return 0;
    }
    else
    {
      if ( v11 != 2 )
        return 0;
      CWbemInstancePacket::CWbemInstancePacket((CWbemInstancePacket *)&v57, (unsigned __int8 *)v5, v10, 1);
      if ( !CWbemObjectPacket::IsValid((CWbemObjectPacket *)v58)
        || !v58[0]
        || (v16 = *(unsigned int *)(v58[0] + 4LL), (unsigned int)v16 < 0x18)
        || v16 != *(unsigned int *)(v58[2] + 4LL) + 24LL )
      {
        v57 = &CWbemInstancePacket::`vftable';
        return 0;
      }
      v57 = &CWbemInstancePacket::`vftable';
    }
    v17 = (unsigned int *)SafeInt<unsigned long>::MixedSizeAddition<unsigned __int64>(v49);
    v6 = *(_DWORD *)SafeInt<unsigned long>::MixedSizeAddition<unsigned long>(v50, *v17, *(unsigned int *)(v5 + 4));
    v60 = v6;
    if ( v4 == -1 )
    {
      v27 = GetMemLogObject();
      CMemoryLog::Write(v27, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_6737080c1ee93bb283ad4d220f5cef4f_Traceguids,
          "SafeIntException(ERROR_INVALID_DATA)");
      }
      v39 = 13;
      throw (SafeIntException *)&v39;
    }
    v51 = ++v4;
    v52 = v5 + 9;
    v5 += 9LL + *(unsigned int *)(v5 + 4);
    v52 = v5;
  }
  return v4 == *(_DWORD *)(*(_QWORD *)this + 8LL) && v60 <= *((_DWORD *)this + 2);
}

```

## disassembly

```asm
0x18001b8b0  mov     rax, rsp
0x18001b8b3  mov     [rax+8], rbx
0x18001b8b7  mov     [rax+10h], rsi
0x18001b8bb  push    rdi
0x18001b8bc  push    r12
0x18001b8be  push    r13
0x18001b8c0  push    r14
0x18001b8c2  push    r15
0x18001b8c4  sub     rsp, 0F0h
0x18001b8cb  mov     r15, rdx
0x18001b8ce  mov     r14, rcx
0x18001b8d1  xor     edi, edi
0x18001b8d3  mov     dword ptr [rax+18h], 0Ch
0x18001b8da  mov     rbx, [rcx]
0x18001b8dd  add     rbx, 0Ch
0x18001b8e1  lea     r13, ??_7CWbemInstancePacket@@6B@; const CWbemInstancePacket::`vftable'
0x18001b8e8  lea     r12, ??_7CWbemClasslessInstancePacket@@6B@; const CWbemClasslessInstancePacket::`vftable'
0x18001b8ef  mov     eax, [rax+18h]
0x18001b8f2  mov     ecx, [r14+8]
0x18001b8f6  cmp     eax, ecx
0x18001b8f8  jnb     loc_18001BB16
0x18001b8fe  mov     rdx, [r14]
0x18001b901  cmp     edi, [rdx+8]
0x18001b904  jnb     loc_18001BB16
0x18001b90a  sub     ecx, eax
0x18001b90c  mov     rsi, rbx
0x18001b90f  mov     [rsp+118h+var_38], rbx
0x18001b917  mov     [rsp+118h+var_30], ecx
0x18001b91e  test    rbx, rbx
0x18001b921  jz      loc_18001BB0E
0x18001b927  cmp     ecx, 9
0x18001b92a  jb      loc_18001BC29
0x18001b930  cmp     dword ptr [rbx], 9
0x18001b933  jnz     loc_18001BC91
0x18001b939  mov     r8d, ecx
0x18001b93c  mov     edx, [rbx+4]
0x18001b93f  lea     rax, [rcx-9]
0x18001b943  cmp     rdx, rax
0x18001b946  ja      loc_18001BC91
0x18001b94c  cmp     ecx, 9
0x18001b94f  jbe     loc_18001BC18
0x18001b955  test    rbx, rbx
0x18001b958  jz      loc_18001BC18
0x18001b95e  mov     edx, [rbx+4]
0x18001b961  lea     rax, [r8-9]
0x18001b965  cmp     rdx, rax
0x18001b968  ja      loc_18001BC18
0x18001b96e  mov     [rsp+118h+arg_18], edx
0x18001b975  lea     rcx, [rsp+118h+var_98]
0x18001b97d  call    ??$MixedSizeAddition@_K@?$SafeInt@K@@CA?AV0@V0@_K@Z; SafeInt<ulong>::MixedSizeAddition<unsigned __int64>(SafeInt<ulong>,unsigned __int64)
0x18001b982  mov     ecx, [rax]
0x18001b984  mov     [rsp+118h+arg_18], ecx
0x18001b98b  movzx   eax, byte ptr [rbx+8]
0x18001b98f  cmp     al, 3
0x18001b991  jnz     loc_18001BA72
0x18001b997  xor     eax, eax
0x18001b999  mov     [rsp+118h+var_C0], rax
0x18001b99e  mov     [rsp+118h+var_B8], eax
0x18001b9a2  mov     [rsp+118h+var_C8], r13
0x18001b9a7  lea     rax, [rbx+9]
0x18001b9ab  cmp     rax, rbx
0x18001b9ae  jbe     loc_18001BEA0
0x18001b9b4  mov     [rsp+118h+var_B0], rax
0x18001b9b9  cmp     ecx, 21h ; '!'
0x18001b9bc  jb      loc_18001BF08
0x18001b9c2  lea     edx, [rcx-9]
0x18001b9c5  mov     [rsp+118h+var_A8], edx
0x18001b9c9  cmp     dword ptr [rax], 18h
0x18001b9cc  jnz     loc_18001C0A2
0x18001b9d2  cmp     [rax+4], edx
0x18001b9d5  ja      loc_18001C0A2
0x18001b9db  mov     [rsp+118h+var_C0], rbx
0x18001b9e0  mov     [rsp+118h+var_B8], ecx
0x18001b9e4  cmp     dword ptr [rbx], 9
0x18001b9e7  jnz     loc_18001C03A
0x18001b9ed  sub     rcx, 9
0x18001b9f1  mov     eax, [rbx+4]
0x18001b9f4  cmp     rax, rcx
0x18001b9f7  ja      loc_18001C03A
0x18001b9fd  mov     [rsp+118h+var_C8], r12
0x18001ba02  test    r15, r15
0x18001ba05  jz      loc_18001BF71
0x18001ba0b  mov     [rsp+118h+var_A0], r15
0x18001ba10  mov     eax, [rsp+118h+var_B8]
0x18001ba14  cmp     eax, 9
0x18001ba17  jbe     short loc_18001BA49
0x18001ba19  mov     rcx, [rsp+118h+var_C0]
0x18001ba1e  test    rcx, rcx
0x18001ba21  jz      short loc_18001BA49
0x18001ba23  mov     edx, [rcx+4]
0x18001ba26  sub     rax, 9
0x18001ba2a  cmp     edx, 18h
0x18001ba2d  jb      short loc_18001BA49
0x18001ba2f  cmp     rdx, rax
0x18001ba32  ja      short loc_18001BA49
0x18001ba34  mov     rax, [rsp+118h+var_B0]
0x18001ba39  mov     ecx, [rax+4]
0x18001ba3c  add     rcx, 18h
0x18001ba40  cmp     rdx, rcx
0x18001ba43  jz      loc_18001BBA3
0x18001ba49  mov     [rsp+118h+var_C8], r12
0x18001ba4e  mov     [rsp+118h+var_C8], r13
0x18001ba53  xor     al, al
0x18001ba55  lea     r11, [rsp+118h+var_28]
0x18001ba5d  mov     rbx, [r11+30h]
0x18001ba61  mov     rsi, [r11+38h]
0x18001ba65  mov     rsp, r11
0x18001ba68  pop     r15
0x18001ba6a  pop     r14
0x18001ba6c  pop     r13
0x18001ba6e  pop     r12
0x18001ba70  pop     rdi
0x18001ba71  retn
0x18001ba72  mov     edx, eax
0x18001ba74  sub     edx, 1
0x18001ba77  jnz     loc_18001BB35
0x18001ba7d  xor     eax, eax
0x18001ba7f  mov     [rsp+118h+var_80], rax
0x18001ba87  mov     [rsp+118h+var_78], eax
0x18001ba8e  lea     r8, [rbx+9]
0x18001ba92  cmp     r8, rbx
0x18001ba95  jbe     loc_18001BD00
0x18001ba9b  mov     [rsp+118h+var_70], r8
0x18001baa3  cmp     ecx, 11h
0x18001baa6  jb      loc_18001BD68
0x18001baac  lea     eax, [rcx-9]
0x18001baaf  mov     [rsp+118h+var_68], eax
0x18001bab6  cmp     dword ptr [r8], 8
0x18001baba  jnz     loc_18001BE38
0x18001bac0  mov     r8d, [r8+4]
0x18001bac4  cmp     r8d, eax
0x18001bac7  ja      loc_18001BE38
0x18001bacd  mov     [rsp+118h+var_80], rbx
0x18001bad5  mov     [rsp+118h+var_78], ecx
0x18001badc  cmp     dword ptr [rbx], 9
0x18001badf  jnz     loc_18001BDD0
0x18001bae5  mov     edx, [rbx+4]
0x18001bae8  lea     rax, [rcx-9]
0x18001baec  cmp     rdx, rax
0x18001baef  ja      loc_18001BDD0
0x18001baf5  cmp     edx, 8
0x18001baf8  jb      short loc_18001BB07
0x18001bafa  lea     rax, [r8+8]
0x18001bafe  cmp     rdx, rax
0x18001bb01  jz      loc_18001BBAD
0x18001bb07  xor     al, al
0x18001bb09  jmp     loc_18001BA55
0x18001bb0e  mov     r8d, ecx
0x18001bb11  jmp     loc_18001B94C
0x18001bb16  mov     rax, [r14]
0x18001bb19  cmp     edi, [rax+8]
0x18001bb1c  jnz     loc_18001C10B
0x18001bb22  mov     eax, [r14+8]
0x18001bb26  cmp     [rsp+118h+arg_10], eax
0x18001bb2d  setbe   al
0x18001bb30  jmp     loc_18001BA55
0x18001bb35  cmp     edx, 1
0x18001bb38  jnz     loc_18001BCF9
0x18001bb3e  movzx   r9d, dl; bool
0x18001bb42  mov     r8d, ecx; unsigned int
0x18001bb45  mov     rdx, rbx; unsigned __int8 *
0x18001bb48  lea     rcx, [rsp+118h+var_60]; this
0x18001bb50  call    ??0CWbemInstancePacket@@QEAA@PEAEK_N@Z; CWbemInstancePacket::CWbemInstancePacket(uchar *,ulong,bool)
0x18001bb55  nop
0x18001bb56  lea     rcx, [rsp+118h+var_58]; this
0x18001bb5e  call    ?IsValid@CWbemObjectPacket@@QEAA_NXZ; CWbemObjectPacket::IsValid(void)
0x18001bb63  test    al, al
0x18001bb65  jz      short loc_18001BB94
0x18001bb67  mov     rax, [rsp+118h+var_58]
0x18001bb6f  test    rax, rax
0x18001bb72  jz      short loc_18001BB94
0x18001bb74  mov     edx, [rax+4]
0x18001bb77  cmp     edx, 18h
0x18001bb7a  jb      short loc_18001BB94
0x18001bb7c  mov     rax, [rsp+118h+var_48]
0x18001bb84  mov     ecx, [rax+4]
0x18001bb87  add     rcx, 18h
0x18001bb8b  cmp     rdx, rcx
0x18001bb8e  jz      loc_18001BC1F
0x18001bb94  mov     [rsp+118h+var_60], r13
0x18001bb9c  xor     al, al
0x18001bb9e  jmp     loc_18001BA55
0x18001bba3  mov     [rsp+118h+var_C8], r12
0x18001bba8  mov     [rsp+118h+var_C8], r13
0x18001bbad  mov     edx, [rsp+118h+arg_10]
0x18001bbb4  lea     rcx, [rsp+118h+var_94]
0x18001bbbc  call    ??$MixedSizeAddition@_K@?$SafeInt@K@@CA?AV0@V0@_K@Z; SafeInt<ulong>::MixedSizeAddition<unsigned __int64>(SafeInt<ulong>,unsigned __int64)
0x18001bbc1  mov     edx, [rax]
0x18001bbc3  mov     [rsp+118h+arg_10], edx
0x18001bbca  mov     r8d, [rbx+4]
0x18001bbce  lea     rcx, [rsp+118h+var_90]
0x18001bbd6  call    ??$MixedSizeAddition@K@?$SafeInt@K@@CA?AV0@V0@K@Z; SafeInt<ulong>::MixedSizeAddition<ulong>(SafeInt<ulong>,ulong)
0x18001bbdb  mov     eax, [rax]
0x18001bbdd  mov     [rsp+118h+arg_10], eax
0x18001bbe4  cmp     edi, 0FFFFFFFFh
0x18001bbe7  jz      loc_18001BFD2
0x18001bbed  inc     edi
0x18001bbef  mov     [rsp+118h+var_8C], edi
0x18001bbf6  add     rbx, 9
0x18001bbfa  mov     [rsp+118h+var_88], rbx
0x18001bc02  mov     rcx, rbx
0x18001bc05  mov     ebx, [rsi+4]
0x18001bc08  add     rbx, rcx
0x18001bc0b  mov     [rsp+118h+var_88], rbx
0x18001bc13  jmp     loc_18001B8F2
0x18001bc18  xor     al, al
0x18001bc1a  jmp     loc_18001BA55
0x18001bc1f  mov     [rsp+118h+var_60], r13
0x18001bc27  jmp     short loc_18001BBAD
0x18001bc29  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001bc2f  mov     edx, 0FFFFFFFEh
0x18001bc34  mov     rcx, rax
0x18001bc37  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001bc3d  lea     rax, WPP_GLOBAL_Control
0x18001bc44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc4b  cmp     rcx, rax
0x18001bc4e  jz      short loc_18001BC78
0x18001bc50  test    byte ptr [rcx+1Ch], 1
0x18001bc54  jz      short loc_18001BC78
0x18001bc56  cmp     byte ptr [rcx+19h], 2
0x18001bc5a  jb      short loc_18001BC78
0x18001bc5c  mov     edx, 0Dh
0x18001bc61  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x18001bc68  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x18001bc6f  mov     rcx, [rcx+10h]
0x18001bc73  call    WPP_SF_s
0x18001bc78  mov     [rsp+118h+pExceptionObject], 57h ; 'W'
0x18001bc80  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001bc87  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18001bc8c  call    _CxxThrowException_0
0x18001bc91  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001bc97  mov     edx, 0FFFFFFFEh
0x18001bc9c  mov     rcx, rax
0x18001bc9f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001bca5  lea     rax, WPP_GLOBAL_Control
0x18001bcac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bcb3  cmp     rcx, rax
0x18001bcb6  jz      short loc_18001BCE0
0x18001bcb8  test    byte ptr [rcx+1Ch], 1
0x18001bcbc  jz      short loc_18001BCE0
0x18001bcbe  cmp     byte ptr [rcx+19h], 2
0x18001bcc2  jb      short loc_18001BCE0
0x18001bcc4  mov     edx, 0Eh
0x18001bcc9  lea     r9, aSafeintexcepti; "SafeIntException(ERROR_INVALID_DATA)"
0x18001bcd0  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x18001bcd7  mov     rcx, [rcx+10h]
0x18001bcdb  call    WPP_SF_s
0x18001bce0  mov     [rsp+118h+var_F0], 0Dh
0x18001bce8  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001bcef  lea     rcx, [rsp+118h+var_F0]; pExceptionObject
0x18001bcf4  call    _CxxThrowException_0
0x18001bcf9  xor     al, al
0x18001bcfb  jmp     loc_18001BA55
0x18001bd00  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001bd06  mov     edx, 0FFFFFFFEh
0x18001bd0b  mov     rcx, rax
0x18001bd0e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001bd14  lea     rax, WPP_GLOBAL_Control
0x18001bd1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd22  cmp     rcx, rax
0x18001bd25  jz      short loc_18001BD4F
0x18001bd27  test    byte ptr [rcx+1Ch], 1
0x18001bd2b  jz      short loc_18001BD4F
0x18001bd2d  cmp     byte ptr [rcx+19h], 2
0x18001bd31  jb      short loc_18001BD4F
0x18001bd33  mov     edx, 14h
0x18001bd38  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x18001bd3f  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x18001bd46  mov     rcx, [rcx+10h]
0x18001bd4a  call    WPP_SF_s
0x18001bd4f  mov     [rsp+118h+var_EC], 57h ; 'W'
0x18001bd57  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001bd5e  lea     rcx, [rsp+118h+var_EC]; pExceptionObject
0x18001bd63  call    _CxxThrowException_0
0x18001bd68  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001bd6e  mov     edx, 0FFFFFFFEh
0x18001bd73  mov     rcx, rax
0x18001bd76  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001bd7c  lea     rax, WPP_GLOBAL_Control
0x18001bd83  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd8a  cmp     rcx, rax
0x18001bd8d  jz      short loc_18001BDB7
0x18001bd8f  test    byte ptr [rcx+1Ch], 1
0x18001bd93  jz      short loc_18001BDB7
0x18001bd95  cmp     byte ptr [rcx+19h], 2
0x18001bd99  jb      short loc_18001BDB7
0x18001bd9b  mov     edx, 15h
0x18001bda0  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x18001bda7  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x18001bdae  mov     rcx, [rcx+10h]
0x18001bdb2  call    WPP_SF_s
0x18001bdb7  mov     [rsp+118h+var_E8], 57h ; 'W'
0x18001bdbf  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18001bdc6  lea     rcx, [rsp+118h+var_E8]; pExceptionObject
0x18001bdcb  call    _CxxThrowException_0
0x18001bdd0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001bdd6  mov     edx, 0FFFFFFFEh
0x18001bddb  mov     rcx, rax
0x18001bdde  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001bde4  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
