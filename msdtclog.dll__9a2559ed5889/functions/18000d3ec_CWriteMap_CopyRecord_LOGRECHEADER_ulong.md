# CWriteMap::CopyRecord(_LOGRECHEADER &,ulong)

- ea: `0x18000d3ec`
- end: `0x18000d61a`
- name: `?CopyRecord@CWriteMap@@QEAAXAEAU_LOGRECHEADER@@K@Z`
- size: `558`
- prototype: `void __fastcall(CWriteMap *this, struct _LOGRECHEADER *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800084c8`
- `0x180008768`

## callees

- `0x180005a7c`
- `0x18000a990`
- `0x18000b974`
- `0x18000d3ec`
- `0x18000d694`
- `0x18000d998`
- `0x18001266c`

## string_xrefs

- `0x18000d597`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000d5ce`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
void __fastcall CWriteMap::CopyRecord(CWriteMap *this, struct _LOGRECHEADER *a2, unsigned int a3, unsigned int a4)
{
  unsigned int v7; // edi
  __int64 v8; // rsi
  __int64 v9; // rcx
  unsigned int v10; // r8d
  unsigned int v11; // edx
  struct CBuffer *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rax
  BOOL v16; // r8d
  unsigned int v17; // edi
  unsigned int k; // edi
  int j; // ebx
  int i; // ebx
  ulong v21; // [rsp+30h] [rbp-38h] BYREF
  ulong v22; // [rsp+34h] [rbp-34h] BYREF
  int v23; // [rsp+38h] [rbp-30h] BYREF
  int pExceptionObject; // [rsp+3Ch] [rbp-2Ch] BYREF
  ulong v25; // [rsp+40h] [rbp-28h] BYREF
  int v26; // [rsp+44h] [rbp-24h] BYREF
  ulong v27; // [rsp+48h] [rbp-20h] BYREF
  int v28; // [rsp+4Ch] [rbp-1Ch] BYREF
  unsigned int v30; // [rsp+88h] [rbp+20h]

  v7 = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    while ( 1 )
    {
      v30 = v7;
      if ( v7 >= *((_DWORD *)this + 20) )
        break;
      v8 = 32LL * v7;
      *(_QWORD *)((char *)this + v8 + 104) = 0;
      v9 = *((_QWORD *)this + 4);
      v10 = *((_DWORD *)this + 8 * v7 + 24);
      v11 = *(_DWORD *)((char *)this + v8 + 92);
      v12 = *(struct CBuffer **)(v9 + 96);
      if ( v12 )
      {
        if ( *(_DWORD *)v12 != v11 || *((_DWORD *)v12 + 1) != v10 || v10 != *(_DWORD *)(v9 + 40) )
        {
          TraceFile(-2147024809, "E_INVALIDARG", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x422);
          v21 = -2147024809;
          throw &v21;
        }
        *(_QWORD *)(v9 + 96) = 0;
        *(_DWORD *)(v9 + 28) = 0;
      }
      else
      {
        if ( v11 >= *(_DWORD *)(v9 + 32) || !v10 )
        {
          TraceFile(-2147024809, "E_INVALIDARG", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x431);
          v22 = -2147024809;
          throw &v22;
        }
        v12 = CLogStorage::_MapBuffer((CLogStorage *)v9, v11, v10, 0, a3);
      }
      *(_QWORD *)((char *)this + v8 + 104) = v12;
      ++v7;
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v28) )
    {
      for ( i = v30 - 1; i >= 0; --i )
      {
        if ( *((_QWORD *)this + 4 * i + 13) )
          CLogStorage::PutWriteBuffer(*((CLogStorage **)this + 4), *((struct CBuffer **)this + 4 * i + 13));
      }
      v26 = v28;
      throw (long *)&v26;
    }
    if ( __eh34_catch_type(0, &unsigned long `RTTI Type Descriptor', &v27) )
    {
      for ( j = v30 - 1; j >= 0; --j )
      {
        if ( *((_QWORD *)this + 4 * j + 13) )
          CLogStorage::PutWriteBuffer(*((CLogStorage **)this + 4), *((struct CBuffer **)this + 4 * j + 13));
      }
      v25 = v27;
      throw &v25;
    }
  }
  v13 = *((_QWORD *)this + 13);
  if ( *(_DWORD *)(v13 + 64) || (v14 = *(_QWORD *)(v13 + 56)) == 0 )
  {
    pExceptionObject = -2147418113;
    throw (long *)&pExceptionObject;
  }
  v15 = *((unsigned int *)this + 21);
  *(_DWORD *)(v14 + 28) = v15;
  *(_OWORD *)(v15 + v14 + 32) = *(_OWORD *)a2;
  *(_QWORD *)(v15 + v14 + 48) = *((_QWORD *)a2 + 2);
  *((_DWORD *)this + 21) += 24;
  *((_DWORD *)this + 22) -= 24;
  *(_DWORD *)(v14 + 24) -= 24;
  if ( *(_DWORD *)(v14 + 24) > 0x2000u )
  {
    v23 = -2147418113;
    throw (long *)&v23;
  }
  v16 = !*((_DWORD *)this + 6) && *((_DWORD *)this + 28) || !*(_DWORD *)(v14 + 24);
  CBuffer::FreePage(*((struct _RECORDPAGE ***)this + 13), (struct _RECORDPAGE *)v14, v16, a4);
  v17 = *((_DWORD *)this + 22) == 0;
  if ( *((_DWORD *)this + 6) )
  {
    while ( v17 < *((_DWORD *)this + 20) )
      CWriteMap::_CopyBuffer(this, v17++);
  }
  for ( k = 0; k < *((_DWORD *)this + 20); ++k )
    CLogStorage::PutWriteBuffer(*((CLogStorage **)this + 4), *((struct CBuffer **)this + 4 * k + 13));
}

```

## disassembly

```asm
0x18000d3ec  mov     [rsp+arg_8], rbx
0x18000d3f1  mov     [rsp+arg_10], rsi
0x18000d3f6  mov     [rsp+arg_0], rcx
0x18000d3fb  push    rdi
0x18000d3fc  push    r14
0x18000d3fe  push    r15
0x18000d400  sub     rsp, 50h
0x18000d404  mov     r14d, r8d
0x18000d407  mov     r15, rdx
0x18000d40a  mov     rbx, rcx
0x18000d40d  xor     edi, edi
0x18000d40f  mov     [rsp+68h+arg_18], edi
0x18000d416  cmp     edi, [rbx+50h]
0x18000d419  jnb     loc_18000D4A5
0x18000d41f  mov     eax, edi
0x18000d421  mov     esi, edi
0x18000d423  shl     rsi, 5
0x18000d427  mov     qword ptr [rsi+rbx+68h], 0
0x18000d430  mov     rcx, [rbx+20h]; this
0x18000d434  add     rax, 3
0x18000d438  shl     rax, 5
0x18000d43c  mov     r8d, [rax+rbx]; unsigned int
0x18000d440  mov     edx, [rsi+rbx+5Ch]; unsigned int
0x18000d444  mov     rax, [rcx+60h]
0x18000d448  test    rax, rax
0x18000d44b  jz      short loc_18000D47A
0x18000d44d  cmp     [rax], edx
0x18000d44f  jnz     loc_18000D591
0x18000d455  cmp     [rax+4], r8d
0x18000d459  jnz     loc_18000D591
0x18000d45f  cmp     r8d, [rcx+28h]
0x18000d463  jnz     loc_18000D591
0x18000d469  mov     qword ptr [rcx+60h], 0
0x18000d471  mov     dword ptr [rcx+1Ch], 0
0x18000d478  jmp     short loc_18000D499
0x18000d47a  cmp     edx, [rcx+20h]
0x18000d47d  jnb     loc_18000D5C8
0x18000d483  test    r8d, r8d
0x18000d486  jz      loc_18000D5C8
0x18000d48c  mov     [rsp+68h+var_48], r14d; unsigned int
0x18000d491  xor     r9d, r9d; int
0x18000d494  call    ?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z; CLogStorage::_MapBuffer(ulong,ulong,int,ulong)
0x18000d499  mov     [rsi+rbx+68h], rax
0x18000d49e  inc     edi
0x18000d4a0  jmp     loc_18000D40F
0x18000d4a5  mov     rdx, [rbx+68h]
0x18000d4a9  cmp     dword ptr [rdx+40h], 0
0x18000d4ad  jnz     loc_18000D577
0x18000d4b3  mov     rdx, [rdx+38h]; struct _RECORDPAGE *
0x18000d4b7  test    rdx, rdx
0x18000d4ba  jz      loc_18000D577
0x18000d4c0  mov     eax, [rbx+54h]
0x18000d4c3  mov     [rdx+1Ch], eax
0x18000d4c6  movups  xmm0, xmmword ptr [r15]
0x18000d4ca  movups  xmmword ptr [rax+rdx+20h], xmm0
0x18000d4cf  movsd   xmm1, qword ptr [r15+10h]
0x18000d4d5  movsd   qword ptr [rax+rdx+30h], xmm1
0x18000d4db  add     dword ptr [rbx+54h], 18h
0x18000d4df  mov     eax, 0FFFFFFE8h
0x18000d4e4  add     [rbx+58h], eax
0x18000d4e7  add     [rdx+18h], eax
0x18000d4ea  cmp     dword ptr [rdx+18h], 2000h
0x18000d4f1  ja      loc_18000D600
0x18000d4f7  cmp     dword ptr [rbx+18h], 0
0x18000d4fb  jnz     short loc_18000D503
0x18000d4fd  cmp     dword ptr [rbx+70h], 0
0x18000d501  jnz     short loc_18000D50E
0x18000d503  cmp     dword ptr [rdx+18h], 0
0x18000d507  jz      short loc_18000D50E
0x18000d509  xor     r8d, r8d
0x18000d50c  jmp     short loc_18000D514
0x18000d50e  mov     r8d, 1; int
0x18000d514  mov     rcx, [rbx+68h]; this
0x18000d518  call    ?FreePage@CBuffer@@QEAAXPEAU_RECORDPAGE@@HK@Z; CBuffer::FreePage(_RECORDPAGE *,int,ulong)
0x18000d51d  xor     edi, edi
0x18000d51f  cmp     [rbx+58h], edi
0x18000d522  setz    dil
0x18000d526  cmp     dword ptr [rbx+18h], 0
0x18000d52a  jz      short loc_18000D53F
0x18000d52c  jmp     short loc_18000D53A
0x18000d52e  mov     edx, edi; unsigned int
0x18000d530  mov     rcx, rbx; this
0x18000d533  call    ?_CopyBuffer@CWriteMap@@AEAAXK@Z; CWriteMap::_CopyBuffer(ulong)
0x18000d538  inc     edi
0x18000d53a  cmp     edi, [rbx+50h]
0x18000d53d  jb      short loc_18000D52E
0x18000d53f  xor     edi, edi
0x18000d541  cmp     [rbx+50h], edi
0x18000d544  jbe     short loc_18000D561
0x18000d546  mov     edx, edi
0x18000d548  shl     rdx, 5
0x18000d54c  mov     rdx, [rdx+rbx+68h]; struct CBuffer *
0x18000d551  mov     rcx, [rbx+20h]; this
0x18000d555  call    ?PutWriteBuffer@CLogStorage@@QEAAXPEAVCBuffer@@@Z; CLogStorage::PutWriteBuffer(CBuffer *)
0x18000d55a  inc     edi
0x18000d55c  cmp     edi, [rbx+50h]
0x18000d55f  jb      short loc_18000D546
0x18000d561  lea     r11, [rsp+68h+var_18]
0x18000d566  mov     rbx, [r11+28h]
0x18000d56a  mov     rsi, [r11+30h]
0x18000d56e  mov     rsp, r11
0x18000d571  pop     r15
0x18000d573  pop     r14
0x18000d575  pop     rdi
0x18000d576  retn
0x18000d577  mov     [rsp+68h+pExceptionObject], 8000FFFFh
0x18000d57f  lea     rdx, _TI1J; pThrowInfo
0x18000d586  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000d58b  call    _CxxThrowException_0
0x18000d591  mov     r9d, 422h; unsigned int
0x18000d597  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000d59e  lea     rdx, aEInvalidarg; "E_INVALIDARG"
0x18000d5a5  mov     ecx, 80070057h; int
0x18000d5aa  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000d5af  mov     [rsp+68h+var_38], 80070057h
0x18000d5b7  lea     rdx, _TI1K; pThrowInfo
0x18000d5be  lea     rcx, [rsp+68h+var_38]; pExceptionObject
0x18000d5c3  call    _CxxThrowException_0
0x18000d5c8  mov     r9d, 431h; unsigned int
0x18000d5ce  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000d5d5  lea     rdx, aEInvalidarg; "E_INVALIDARG"
0x18000d5dc  mov     ecx, 80070057h; int
0x18000d5e1  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000d5e6  mov     [rsp+68h+var_34], 80070057h
0x18000d5ee  lea     rdx, _TI1K; pThrowInfo
0x18000d5f5  lea     rcx, [rsp+68h+var_34]; pExceptionObject
0x18000d5fa  call    _CxxThrowException_0
0x18000d600  mov     [rsp+68h+var_30], 8000FFFFh
0x18000d608  lea     rdx, _TI1J; pThrowInfo
0x18000d60f  lea     rcx, [rsp+68h+var_30]; pExceptionObject
0x18000d614  call    _CxxThrowException_0
```
