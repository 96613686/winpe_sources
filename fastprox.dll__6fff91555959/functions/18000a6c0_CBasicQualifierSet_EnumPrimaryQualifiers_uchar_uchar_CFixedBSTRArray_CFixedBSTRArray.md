# CBasicQualifierSet::EnumPrimaryQualifiers(uchar,uchar,CFixedBSTRArray &,CFixedBSTRArray &)

- ea: `0x18000a6c0`
- end: `0x18000aacb`
- name: `?EnumPrimaryQualifiers@CBasicQualifierSet@@QEAAJEEAEAVCFixedBSTRArray@@0@Z`
- size: `1035`
- prototype: `int(CBasicQualifierSet *__hidden this, unsigned __int8, unsigned __int8, struct CFixedBSTRArray *, struct CFixedBSTRArray *)`
- caller_count: `6`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180001130`
- `0x1800097b0`
- `0x180066260`
- `0x1800693c0`
- `0x1800808b0`
- `0x180080bc0`

## callees

- `0x1800088d0`
- `0x180009610`
- `0x18000a6c0`
- `0x18000aae0`
- `0x18000ac60`
- `0x18000b360`
- `0x18000b900`
- `0x180035b08`
- `0x180037120`
- `0x18006fa4c`
- `0x180071c50`
- `0x180091972`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18000a95c`
- `wbemcomn!GetMemLogObject` at `0x18000a9f6`
- `wbemcomn!GetMemLogObject` at `0x18000aa56`
- `wbemcomn!GetMemLogObject` at `0x18000a95c`
- `wbemcomn!GetMemLogObject` at `0x18000a9f6`
- `wbemcomn!GetMemLogObject` at `0x18000aa56`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a967`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000aa04`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000aa64`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a967`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000aa04`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000aa64`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a721`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a787`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a721`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000a787`

## pseudocode

```c
__int64 __fastcall CBasicQualifierSet::EnumPrimaryQualifiers(
        CBasicQualifierSet *this,
        char a2,
        unsigned __int8 a3,
        struct CFixedBSTRArray *a4,
        struct CFixedBSTRArray *a5)
{
  unsigned int v8; // ebx
  void *v9; // rax
  unsigned int v10; // ebx
  void *v11; // rax
  int v12; // r13d
  int v13; // ebx
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // r15
  unsigned int v16; // ebx
  _QWORD *v17; // rcx
  CCompressedString *KnownString; // rdx
  unsigned __int16 *BSTRCopy; // rax
  __int64 v20; // rdx
  int v21; // ecx
  __int64 v22; // rax
  int v23; // eax
  unsigned __int16 *v24; // rdx
  __int64 v25; // rax
  unsigned int v26; // ebx
  __int64 result; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  int v33; // [rsp+24h] [rbp-54h]
  char v34; // [rsp+28h] [rbp-50h] BYREF
  char v35; // [rsp+29h] [rbp-4Fh] BYREF
  char pExceptionObject; // [rsp+2Ah] [rbp-4Eh] BYREF
  signed int v37; // [rsp+2Ch] [rbp-4Ch] BYREF
  signed int v38; // [rsp+30h] [rbp-48h] BYREF
  int v39; // [rsp+34h] [rbp-44h]
  unsigned int v40; // [rsp+38h] [rbp-40h]

  v40 = 0;
  try
  {
    v8 = *(_DWORD *)this / 5u;
    CFixedBSTRArray::Free(a4);
    v9 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v8, 8u));
    *(_QWORD *)((char *)a4 + 4) = v9;
    if ( !v9 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&v34;
    }
    v37 = v8;
    v37 = *(_DWORD *)SafeInt<int>::MixedSizeMultiply<unsigned __int64>(&v38, v8, 8);
    memset_0(*(void **)((char *)a4 + 4), 0, v37);
    *(_DWORD *)a4 = v8;
    v10 = *(_DWORD *)this / 5u;
    CFixedBSTRArray::Free(a5);
    v11 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(v10, 8u));
    *(_QWORD *)((char *)a5 + 4) = v11;
    if ( !v11 )
    {
      v30 = GetMemLogObject();
      CMemoryLog::Write(v30, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids,
          "CX_MemoryException()");
      }
      throw (CX_MemoryException *)&v35;
    }
    v38 = v10;
    v38 = *(_DWORD *)SafeInt<int>::MixedSizeMultiply<unsigned __int64>(&v37, v10, 8);
    memset_0(*(void **)((char *)a5 + 4), 0, v38);
    *(_DWORD *)a5 = v10;
    v12 = 0;
    v39 = 0;
    v13 = 0;
    v33 = 0;
    v14 = *((_QWORD *)this + 1);
    v15 = *(unsigned int *)this + v14 - 4;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v14 >= v15 )
        {
          *(_DWORD *)a4 = v12;
          CFixedBSTRArray::SortInPlace(a4);
          *(_DWORD *)a5 = v13;
          CFixedBSTRArray::SortInPlace(a5);
          v26 = v40;
          goto LABEL_22;
        }
        v16 = *(_DWORD *)v14;
        if ( *(_DWORD *)v14 != -1 )
          break;
        v14 += CType::GetLength(*(_DWORD *)(v14 + 5)) + 4 + 5LL;
        v13 = v33;
      }
      if ( CFastHeap::IsFakeAddress(v16) )
      {
        KnownString = CKnownStringTable::GetKnownString(v16 & 0x7FFFFFFF);
      }
      else
      {
        v17 = (_QWORD *)*((_QWORD *)this + 2);
        if ( v16 > *(_DWORD *)(v17[1] + 4LL) )
          throw (CX_Exception *)&pExceptionObject;
        KnownString = (CCompressedString *)(*v17 + v16);
      }
      if ( (a3 & *(_BYTE *)(v14 + 4)) != a3 )
        goto LABEL_11;
      if ( a2 != 16 )
        break;
      if ( (*(_BYTE *)(v14 + 4) & 0x60) == 0 )
        goto LABEL_18;
LABEL_11:
      BSTRCopy = CCompressedString::CreateBSTRCopy(KnownString);
      v20 = 8LL * v33;
      v13 = ++v33;
      *(_QWORD *)(v20 + *(_QWORD *)((char *)a5 + 4)) = BSTRCopy;
      if ( !*(_QWORD *)(v20 + *(_QWORD *)((char *)a5 + 4)) )
        goto LABEL_25;
LABEL_12:
      v21 = *(_DWORD *)(v14 + 5);
      v22 = v21 & 0xFFF;
      if ( (unsigned int)v22 > 0x7F )
      {
        v23 = 0;
      }
      else if ( (v21 & 0x2000) != 0 )
      {
        v23 = 4;
      }
      else
      {
        v23 = *((_DWORD *)&m_staticLengths + v22);
      }
      v14 += 5LL + (unsigned int)(v23 + 4);
    }
    if ( a2 == 32 && (*(_BYTE *)(v14 + 4) & 0x60) == 0 )
      goto LABEL_11;
LABEL_18:
    v24 = CCompressedString::CreateBSTRCopy(KnownString);
    v25 = v12++;
    v39 = v12;
    *(_QWORD *)(8 * v25 + *(_QWORD *)((char *)a4 + 4)) = v24;
    if ( *(_QWORD *)(8 * v25 + *(_QWORD *)((char *)a4 + 4)) )
    {
      v13 = v33;
      goto LABEL_12;
    }
LABEL_25:
    v26 = -2147217402;
    CFixedBSTRArray::Free(a4);
    CFixedBSTRArray::Free(a5);
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, -2147217402);
LABEL_22:
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, v26);
    }
    result = v26;
  }
  catch ( CX_MemoryException )
  {
    CFixedBSTRArray::Free(a4);
    CFixedBSTRArray::Free(a5);
    v31 = GetMemLogObject();
    CMemoryLog::Write(v31, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    CFixedBSTRArray::Free(a4);
    CFixedBSTRArray::Free(a5);
    v32 = GetMemLogObject();
    CMemoryLog::Write(v32, -2147217407);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids, 2147749889LL);
    }
    return 2147749889LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000a6c0  mov     [rsp+arg_18], r9
0x18000a6c5  mov     [rsp+arg_8], dl
0x18000a6c9  mov     [rsp+arg_0], rcx
0x18000a6ce  push    rbx
0x18000a6cf  push    rsi
0x18000a6d0  push    rdi
0x18000a6d1  push    r12
0x18000a6d3  push    r13
0x18000a6d5  push    r14
0x18000a6d7  push    r15
0x18000a6d9  sub     rsp, 40h
0x18000a6dd  mov     rsi, r9
0x18000a6e0  movzx   r14d, r8b
0x18000a6e4  mov     r15, rcx
0x18000a6e7  mov     r12, [rsp+78h+arg_20]
0x18000a6ef  xor     eax, eax
0x18000a6f1  mov     [rsp+78h+var_40], eax
0x18000a6f5  mov     eax, 0CCCCCCCDh
0x18000a6fa  mul     dword ptr [rcx]
0x18000a6fc  mov     ebx, edx
0x18000a6fe  shr     ebx, 2
0x18000a701  mov     rcx, r9; this
0x18000a704  call    ?Free@CFixedBSTRArray@@QEAAXXZ; CFixedBSTRArray::Free(void)
0x18000a709  mov     ecx, ebx
0x18000a70b  mov     eax, 8
0x18000a710  mul     rcx
0x18000a713  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000a71a  cmovb   rax, rdi
0x18000a71e  mov     rcx, rax
0x18000a721  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a727  mov     [rsi+4], rax
0x18000a72b  test    rax, rax
0x18000a72e  jz      loc_18000A9F6
0x18000a734  mov     [rsp+78h+var_4C], ebx
0x18000a738  mov     r8d, 8
0x18000a73e  mov     edx, ebx
0x18000a740  lea     rcx, [rsp+78h+var_48]
0x18000a745  call    ??$MixedSizeMultiply@_K@?$SafeInt@H@@CA?AV0@V0@_K@Z; SafeInt<int>::MixedSizeMultiply<unsigned __int64>(SafeInt<int>,unsigned __int64)
0x18000a74a  movsxd  rcx, dword ptr [rax]
0x18000a74d  mov     [rsp+78h+var_4C], ecx
0x18000a751  mov     r8, rcx; Size
0x18000a754  xor     edx, edx; Val
0x18000a756  mov     rcx, [rsi+4]; void *
0x18000a75a  call    memset_0
0x18000a75f  mov     [rsi], ebx
0x18000a761  mov     eax, 0CCCCCCCDh
0x18000a766  mul     dword ptr [r15]
0x18000a769  mov     ebx, edx
0x18000a76b  shr     ebx, 2
0x18000a76e  mov     rcx, r12; this
0x18000a771  call    ?Free@CFixedBSTRArray@@QEAAXXZ; CFixedBSTRArray::Free(void)
0x18000a776  mov     ecx, ebx
0x18000a778  mov     eax, 8
0x18000a77d  mul     rcx
0x18000a780  cmovb   rax, rdi
0x18000a784  mov     rcx, rax
0x18000a787  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000a78d  mov     [r12+4], rax
0x18000a792  test    rax, rax
0x18000a795  jz      loc_18000AA56
0x18000a79b  mov     [rsp+78h+var_48], ebx
0x18000a79f  mov     r8d, 8
0x18000a7a5  mov     edx, ebx
0x18000a7a7  lea     rcx, [rsp+78h+var_4C]
0x18000a7ac  call    ??$MixedSizeMultiply@_K@?$SafeInt@H@@CA?AV0@V0@_K@Z; SafeInt<int>::MixedSizeMultiply<unsigned __int64>(SafeInt<int>,unsigned __int64)
0x18000a7b1  movsxd  rcx, dword ptr [rax]
0x18000a7b4  mov     [rsp+78h+var_48], ecx
0x18000a7b8  mov     r8, rcx; Size
0x18000a7bb  xor     edx, edx; Val
0x18000a7bd  mov     rcx, [r12+4]; void *
0x18000a7c2  call    memset_0
0x18000a7c7  mov     [r12], ebx
0x18000a7cb  xor     r13d, r13d
0x18000a7ce  mov     [rsp+78h+var_44], r13d
0x18000a7d3  xor     ebx, ebx
0x18000a7d5  mov     [rsp+78h+var_54], ebx
0x18000a7d9  mov     rdi, [r15+8]
0x18000a7dd  mov     eax, [r15]
0x18000a7e0  lea     r15, [rdi-4]
0x18000a7e4  add     r15, rax
0x18000a7e7  cmp     rdi, r15
0x18000a7ea  jnb     loc_18000A8FD
0x18000a7f0  mov     ebx, [rdi]
0x18000a7f2  cmp     ebx, 0FFFFFFFFh
0x18000a7f5  jz      loc_18000A9AD
0x18000a7fb  mov     ecx, ebx; unsigned int
0x18000a7fd  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x18000a802  test    al, al
0x18000a804  jnz     loc_18000A8EA
0x18000a80a  mov     rax, [rsp+78h+arg_0]
0x18000a812  mov     rcx, [rax+10h]
0x18000a816  mov     rax, [rcx+8]
0x18000a81a  cmp     ebx, [rax+4]
0x18000a81d  ja      loc_18000A98D
0x18000a823  mov     edx, ebx
0x18000a825  add     rdx, [rcx]
0x18000a828  movzx   ecx, byte ptr [rdi+4]
0x18000a82c  and     cl, r14b
0x18000a82f  cmp     cl, r14b
0x18000a832  jz      short loc_18000A89B
0x18000a834  mov     rcx, rdx; this
0x18000a837  call    ?CreateBSTRCopy@CCompressedString@@QEBAPEAGXZ; CCompressedString::CreateBSTRCopy(void)
0x18000a83c  mov     r8, rax
0x18000a83f  movsxd  rbx, [rsp+78h+var_54]
0x18000a844  lea     rdx, ds:0[rbx*8]
0x18000a84c  inc     ebx
0x18000a84e  mov     [rsp+78h+var_54], ebx
0x18000a852  mov     rax, [r12+4]
0x18000a857  mov     [rdx+rax], r8
0x18000a85b  mov     rax, [r12+4]
0x18000a860  cmp     qword ptr [rdx+rax], 0
0x18000a865  jz      loc_18000A947
0x18000a86b  lea     rdx, [rdi+5]
0x18000a86f  mov     ecx, [rdx]
0x18000a871  mov     eax, ecx
0x18000a873  and     eax, 0FFFh
0x18000a878  cmp     eax, 7Fh
0x18000a87b  ja      loc_18000A9C8
0x18000a881  bt      ecx, 0Dh
0x18000a885  jnb     loc_18000A96F
0x18000a88b  mov     eax, 4
0x18000a890  lea     edi, [rax+4]
0x18000a893  add     rdi, rdx
0x18000a896  jmp     loc_18000A7E7
0x18000a89b  movzx   eax, [rsp+78h+arg_8]
0x18000a8a3  cmp     al, 10h
0x18000a8a5  jz      loc_18000A97E
0x18000a8ab  cmp     al, 20h ; ' '
0x18000a8ad  jz      loc_18000A99E
0x18000a8b3  mov     rcx, rdx; this
0x18000a8b6  call    ?CreateBSTRCopy@CCompressedString@@QEBAPEAGXZ; CCompressedString::CreateBSTRCopy(void)
0x18000a8bb  mov     rdx, rax
0x18000a8be  movsxd  rax, r13d
0x18000a8c1  inc     r13d
0x18000a8c4  mov     [rsp+78h+var_44], r13d
0x18000a8c9  lea     rcx, ds:0[rax*8]
0x18000a8d1  mov     rax, [rsi+4]
0x18000a8d5  mov     [rcx+rax], rdx
0x18000a8d9  mov     rax, [rsi+4]
0x18000a8dd  cmp     qword ptr [rcx+rax], 0
0x18000a8e2  jz      short loc_18000A947
0x18000a8e4  mov     ebx, [rsp+78h+var_54]
0x18000a8e8  jmp     short loc_18000A86B
0x18000a8ea  btr     ebx, 1Fh
0x18000a8ee  mov     ecx, ebx; int
0x18000a8f0  call    ?GetKnownString@CKnownStringTable@@SAAEAVCCompressedString@@H@Z; CKnownStringTable::GetKnownString(int)
0x18000a8f5  mov     rdx, rax
0x18000a8f8  jmp     loc_18000A828
0x18000a8fd  mov     [rsi], r13d
0x18000a900  mov     rcx, rsi; this
0x18000a903  call    ?SortInPlace@CFixedBSTRArray@@QEAAXXZ; CFixedBSTRArray::SortInPlace(void)
0x18000a908  mov     [r12], ebx
0x18000a90c  mov     rcx, r12; this
0x18000a90f  call    ?SortInPlace@CFixedBSTRArray@@QEAAXXZ; CFixedBSTRArray::SortInPlace(void)
0x18000a914  mov     ebx, [rsp+78h+var_40]
0x18000a918  lea     rax, WPP_GLOBAL_Control
0x18000a91f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a926  cmp     rcx, rax
0x18000a929  jz      short loc_18000A935
0x18000a92b  test    byte ptr [rcx+1Ch], 1
0x18000a92f  jnz     loc_18000A9CF
0x18000a935  mov     eax, ebx
0x18000a937  add     rsp, 40h
0x18000a93b  pop     r15
0x18000a93d  pop     r14
0x18000a93f  pop     r13
0x18000a941  pop     r12
0x18000a943  pop     rdi
0x18000a944  pop     rsi
0x18000a945  pop     rbx
0x18000a946  retn
0x18000a947  mov     ebx, 80041006h
0x18000a94c  mov     rcx, rsi; this
0x18000a94f  call    ?Free@CFixedBSTRArray@@QEAAXXZ; CFixedBSTRArray::Free(void)
0x18000a954  mov     rcx, r12; this
0x18000a957  call    ?Free@CFixedBSTRArray@@QEAAXXZ; CFixedBSTRArray::Free(void)
0x18000a95c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000a962  mov     edx, ebx
0x18000a964  mov     rcx, rax
0x18000a967  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000a96d  jmp     short loc_18000A918
0x18000a96f  lea     rcx, ?m_staticLengths@@3PAKA; ulong near * m_staticLengths
0x18000a976  mov     eax, [rcx+rax*4]
0x18000a979  jmp     loc_18000A890
0x18000a97e  test    byte ptr [rdi+4], 60h
0x18000a982  jnz     loc_18000A834
0x18000a988  jmp     loc_18000A8B3
0x18000a98d  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18000a994  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000a999  call    _CxxThrowException_0
0x18000a99e  test    byte ptr [rdi+4], 60h
0x18000a9a2  jnz     loc_18000A8B3
0x18000a9a8  jmp     loc_18000A834
0x18000a9ad  mov     ecx, [rdi+5]; unsigned int
0x18000a9b0  call    ?GetLength@CType@@SAKK@Z; CType::GetLength(ulong)
0x18000a9b5  add     eax, 4
0x18000a9b8  add     rdi, 5
0x18000a9bc  add     rdi, rax
0x18000a9bf  mov     ebx, [rsp+78h+var_54]
0x18000a9c3  jmp     loc_18000A7E7
0x18000a9c8  xor     eax, eax
0x18000a9ca  jmp     loc_18000A890
0x18000a9cf  cmp     byte ptr [rcx+19h], 2
0x18000a9d3  jb      loc_18000A935
0x18000a9d9  mov     edx, 0Ch
0x18000a9de  mov     r9d, ebx
0x18000a9e1  lea     r8, WPP_dc700481ea5c3e2cf79b4b18dc082c98_Traceguids
0x18000a9e8  mov     rcx, [rcx+10h]
0x18000a9ec  call    WPP_SF_d
0x18000a9f1  jmp     loc_18000A935
0x18000a9f6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000a9fc  mov     edx, 0FFFFFFFEh
0x18000aa01  mov     rcx, rax
0x18000aa04  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000aa0a  lea     rax, WPP_GLOBAL_Control
0x18000aa11  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa18  cmp     rcx, rax
0x18000aa1b  jz      short loc_18000AA45
0x18000aa1d  test    byte ptr [rcx+1Ch], 1
0x18000aa21  jz      short loc_18000AA45
0x18000aa23  cmp     byte ptr [rcx+19h], 2
0x18000aa27  jb      short loc_18000AA45
0x18000aa29  mov     edx, 0Bh
0x18000aa2e  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18000aa35  lea     r8, WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids
0x18000aa3c  mov     rcx, [rcx+10h]
0x18000aa40  call    WPP_SF_s
0x18000aa45  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18000aa4c  lea     rcx, [rsp+78h+var_50]; pExceptionObject
0x18000aa51  call    _CxxThrowException_0
0x18000aa56  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000aa5c  mov     edx, 0FFFFFFFEh
0x18000aa61  mov     rcx, rax
0x18000aa64  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000aa6a  lea     rax, WPP_GLOBAL_Control
0x18000aa71  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa78  cmp     rcx, rax
0x18000aa7b  jz      short loc_18000AAA5
0x18000aa7d  test    byte ptr [rcx+1Ch], 1
0x18000aa81  jz      short loc_18000AAA5
0x18000aa83  cmp     byte ptr [rcx+19h], 2
0x18000aa87  jb      short loc_18000AAA5
0x18000aa89  mov     edx, 0Bh
0x18000aa8e  lea     r9, aCxMemoryexcept; "CX_MemoryException()"
0x18000aa95  lea     r8, WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids
0x18000aa9c  mov     rcx, [rcx+10h]
0x18000aaa0  call    WPP_SF_s
0x18000aaa5  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x18000aaac  lea     rcx, [rsp+78h+var_4F]; pExceptionObject
0x18000aab1  call    _CxxThrowException_0
0x18000aab7  mov     eax, 80041006h
0x18000aabc  jmp     loc_18000A937
0x18000aac1  mov     eax, 80041001h
0x18000aac6  jmp     loc_18000A937
```
