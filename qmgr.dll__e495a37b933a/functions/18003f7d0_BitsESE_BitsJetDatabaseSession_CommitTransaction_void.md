# BitsESE::BitsJetDatabaseSession::CommitTransaction(void)

- ea: `0x18003f7d0`
- end: `0x18003faa4`
- name: `?CommitTransaction@BitsJetDatabaseSession@BitsESE@@UEAAJXZ`
- size: `724`
- prototype: `__int64 __fastcall(BitsESE::BitsJetDatabaseSession *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000e370`
- `0x18003f7d0`
- `0x1800407d0`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800df410`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f7f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003f7f8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003fa49`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003fa49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f94e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f94e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f956`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f8bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f914`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fa69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f8bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f914`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fa69`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003f93a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003f93a`
- `ESENT!JetCommitTransaction` at `0x18003f9b5`
- `ESENT!JetCommitTransaction` at `0x18003f9b5`

## string_xrefs

- `0x18003f9ec`: `BitsESE::BitsJetDatabaseSession::CommitTransaction`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BitsESE::BitsJetDatabaseSession::CommitTransaction(BitsESE::BitsJetDatabaseSession *this)
{
  volatile signed __int32 *v2; // rax
  volatile signed __int32 *v3; // rbx
  volatile signed __int32 **v4; // rdi
  void *v5; // rcx
  unsigned int LastError; // eax
  JET_ERR v7; // eax
  int v8; // r15d
  __int64 result; // rax
  const ComError *v10; // rbx
  const ComError *v11; // [rsp+30h] [rbp-148h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-138h] BYREF
  __int128 v13; // [rsp+48h] [rbp-130h]
  int v14; // [rsp+58h] [rbp-120h]
  int v15; // [rsp+5Ch] [rbp-11Ch]
  int v16; // [rsp+60h] [rbp-118h]
  void **v17; // [rsp+A0h] [rbp-D8h] BYREF
  __int128 v18; // [rsp+A8h] [rbp-D0h]
  unsigned int v19; // [rsp+B8h] [rbp-C0h]
  int v20; // [rsp+BCh] [rbp-BCh]
  int v21; // [rsp+C0h] [rbp-B8h]
  void **v22; // [rsp+100h] [rbp-78h] BYREF
  __int128 v23; // [rsp+108h] [rbp-70h]
  int v24; // [rsp+118h] [rbp-60h]
  int v25; // [rsp+11Ch] [rbp-5Ch]
  int v26; // [rsp+120h] [rbp-58h]
  void *v27; // [rsp+188h] [rbp+10h] BYREF
  int v28; // [rsp+190h] [rbp+18h] BYREF
  volatile signed __int32 *v29; // [rsp+198h] [rbp+20h]

  v2 = (volatile signed __int32 *)HeapAlloc(hBitsHeap, 8u, 0x10u);
  try
  {
    v3 = v2;
    if ( !v2 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
      v13 = 0;
      pExceptionObject = &ComError::`vftable';
      v14 = -2147024882;
      v15 = 0;
      v16 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v29 = v2;
    *((_DWORD *)v2 + 2) = 1;
    *(_QWORD *)v2 = 0;
    v4 = (volatile signed __int32 **)CopyThreadToken(&v27);
    if ( *(_QWORD *)v3 != *(_QWORD *)*v4 )
    {
      if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
      {
        if ( (unsigned __int64)(*(_QWORD *)v3 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(*(HANDLE *)v3);
          *(_QWORD *)v3 = 0;
        }
        operator delete((void *)v3, 0x10u);
      }
      v3 = *v4;
      v29 = v3;
      _InterlockedIncrement(v3 + 2);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27 + 2, 0xFFFFFFFF) == 1 )
    {
      v5 = v27;
      if ( (unsigned __int64)(*(_QWORD *)v27 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v27);
        *(_QWORD *)v27 = 0;
        v5 = v27;
      }
      operator delete(v5, 0x10u);
    }
    if ( !RevertToSelf() )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v18 = 0;
      v17 = &ComError::`vftable';
      v19 = LastError;
      v20 = 246;
      v21 = 1;
      throw (ComError *)&v17;
    }
    v7 = JetCommitTransaction(*((_QWORD *)this + 3), 0);
    v8 = BitsESE::BitsJetDatabaseSession::JetErrToHR(v7);
    LODWORD(v27) = v8;
    if ( v8 < 0 )
    {
      v28 = 249;
      CTelemetry::DatabaseFailure<char const (&)[60],int,long &,enum MANAGER_STATE &>(
        "BitsESE::BitsJetDatabaseSession::CommitTransaction",
        &v28,
        &v27);
      v23 = 0;
      v22 = &ComError::`vftable';
      v24 = v8;
      v25 = 249;
      v26 = 1;
      throw (ComError *)&v22;
    }
    --*((_DWORD *)this + 10);
    SetThreadToken(0, *(HANDLE *)v3);
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( (unsigned __int64)(*(_QWORD *)v3 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v3);
        *(_QWORD *)v3 = 0;
      }
      operator delete((void *)v3, 0x10u);
    }
    result = 0;
  }
  catch ( const ComError *v11 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v10 = v11;
    }
    else
    {
      v10 = v11;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_9bcb4a76df52358ff94507dd27b8597a_Traceguids,
        *((unsigned int *)v10 + 6),
        *((_DWORD *)v10 + 7));
    }
    LODWORD(v27) = *((_DWORD *)v10 + 6);
    return (unsigned int)v27;
  }
  return result;
}

```

## disassembly

```asm
0x18003f7d0  mov     [rsp+arg_0], rbx
0x18003f7d5  push    rdi
0x18003f7d6  push    r13
0x18003f7d8  push    r15
0x18003f7da  sub     rsp, 160h
0x18003f7e1  mov     r13, rcx
0x18003f7e4  mov     r15d, 10h
0x18003f7ea  mov     r8d, r15d; dwBytes
0x18003f7ed  lea     edx, [r15-8]; dwFlags
0x18003f7f1  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18003f7f8  call    cs:__imp_HeapAlloc
0x18003f7fe  mov     rbx, rax
0x18003f801  test    rax, rax
0x18003f804  jnz     short loc_18003F872
0x18003f806  lea     rax, WPP_GLOBAL_Control
0x18003f80d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f814  cmp     rcx, rax
0x18003f817  jz      short loc_18003F835
0x18003f819  test    byte ptr [rcx+1Ch], 4
0x18003f81d  jz      short loc_18003F835
0x18003f81f  lea     edx, [rbx+0Ah]
0x18003f822  mov     r9d, r15d
0x18003f825  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18003f82c  mov     rcx, [rcx+10h]
0x18003f830  call    WPP_SF_d
0x18003f835  xorps   xmm0, xmm0
0x18003f838  movups  [rsp+178h+var_130], xmm0
0x18003f83d  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003f844  mov     [rsp+178h+pExceptionObject], rcx
0x18003f849  mov     [rsp+178h+var_120], 8007000Eh
0x18003f851  mov     [rsp+178h+var_11C], 0
0x18003f859  mov     [rsp+178h+var_118], 1
0x18003f861  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003f868  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x18003f86d  call    _CxxThrowException_0
0x18003f872  mov     [rsp+178h+arg_18], rbx
0x18003f87a  mov     dword ptr [rax+8], 1
0x18003f881  mov     qword ptr [rax], 0
0x18003f888  lea     rcx, [rsp+178h+arg_8]
0x18003f890  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x18003f895  mov     rdi, rax
0x18003f898  mov     rcx, [rax]
0x18003f89b  mov     rdx, [rcx]
0x18003f89e  cmp     [rbx], rdx
0x18003f8a1  jz      short loc_18003F8E4
0x18003f8a3  or      ecx, 0FFFFFFFFh
0x18003f8a6  lock xadd [rbx+8], ecx
0x18003f8ab  cmp     ecx, 1
0x18003f8ae  jnz     short loc_18003F8D5
0x18003f8b0  mov     rcx, [rbx]; hObject
0x18003f8b3  lea     rax, [rcx-1]
0x18003f8b7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003f8bb  ja      short loc_18003F8CA
0x18003f8bd  call    cs:__imp_CloseHandle
0x18003f8c3  mov     qword ptr [rbx], 0
0x18003f8ca  mov     rdx, r15; unsigned __int64
0x18003f8cd  mov     rcx, rbx; void *
0x18003f8d0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003f8d5  mov     rbx, [rdi]
0x18003f8d8  mov     [rsp+178h+arg_18], rbx
0x18003f8e0  lock inc dword ptr [rbx+8]
0x18003f8e4  mov     rdi, rbx
0x18003f8e7  mov     rcx, [rsp+178h+arg_8]
0x18003f8ef  or      eax, 0FFFFFFFFh
0x18003f8f2  lock xadd [rcx+8], eax
0x18003f8f7  cmp     eax, 1
0x18003f8fa  jnz     short loc_18003F93A
0x18003f8fc  mov     rcx, [rsp+178h+arg_8]
0x18003f904  mov     rdx, [rcx]
0x18003f907  lea     rax, [rdx-1]
0x18003f90b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003f90f  ja      short loc_18003F931
0x18003f911  mov     rcx, rdx; hObject
0x18003f914  call    cs:__imp_CloseHandle
0x18003f91a  mov     rax, [rsp+178h+arg_8]
0x18003f922  mov     qword ptr [rax], 0
0x18003f929  mov     rcx, [rsp+178h+arg_8]; void *
0x18003f931  mov     rdx, r15; unsigned __int64
0x18003f934  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003f939  nop
0x18003f93a  call    cs:__imp_RevertToSelf
0x18003f940  test    eax, eax
0x18003f942  jnz     short loc_18003F9AF
0x18003f944  call    cs:__imp_GetLastError
0x18003f94a  test    eax, eax
0x18003f94c  jg      short loc_18003F956
0x18003f94e  call    cs:__imp_GetLastError
0x18003f954  jmp     short loc_18003F964
0x18003f956  call    cs:__imp_GetLastError
0x18003f95c  movzx   eax, ax
0x18003f95f  or      eax, 80070000h
0x18003f964  xorps   xmm0, xmm0
0x18003f967  movups  [rsp+178h+var_D0], xmm0
0x18003f96f  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003f976  mov     [rsp+178h+var_D8], rcx
0x18003f97e  mov     [rsp+178h+var_C0], eax
0x18003f985  mov     [rsp+178h+var_BC], 0F6h
0x18003f990  mov     [rsp+178h+var_B8], 1
0x18003f99b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003f9a2  lea     rcx, [rsp+178h+var_D8]; pExceptionObject
0x18003f9aa  call    _CxxThrowException_0
0x18003f9af  xor     edx, edx; grbit
0x18003f9b1  mov     rcx, [r13+18h]; sesid
0x18003f9b5  call    cs:__imp_JetCommitTransaction
0x18003f9bb  mov     ecx, eax; int
0x18003f9bd  call    ?JetErrToHR@BitsJetDatabaseSession@BitsESE@@SAJJ@Z; BitsESE::BitsJetDatabaseSession::JetErrToHR(long)
0x18003f9c2  mov     r15d, eax
0x18003f9c5  mov     dword ptr [rsp+178h+arg_8], eax
0x18003f9cc  test    eax, eax
0x18003f9ce  jns     short loc_18003FA40
0x18003f9d0  mov     ebx, 0F9h
0x18003f9d5  mov     [rsp+178h+arg_10], ebx
0x18003f9dc  lea     r8, [rsp+178h+arg_8]
0x18003f9e4  lea     rdx, [rsp+178h+arg_10]
0x18003f9ec  lea     rcx, aBitseseBitsjet_1; "BitsESE::BitsJetDatabaseSession::Commit"...
0x18003f9f3  call    ??$DatabaseFailure@AEAY0DM@$$CBDHAEAJAEAW4MANAGER_STATE@@@CTelemetry@@SAXAEAY0DM@$$CBD$$QEAHAEAJAEAW4MANAGER_STATE@@@Z; CTelemetry::DatabaseFailure<char const (&)[60],int,long &,MANAGER_STATE &>(char const (&)[60],int &&,long &,MANAGER_STATE &)
0x18003f9f8  xorps   xmm0, xmm0
0x18003f9fb  movups  [rsp+178h+var_70], xmm0
0x18003fa03  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003fa0a  mov     [rsp+178h+var_78], rcx
0x18003fa12  mov     [rsp+178h+var_60], r15d
0x18003fa1a  mov     [rsp+178h+var_5C], ebx
0x18003fa21  mov     [rsp+178h+var_58], 1
0x18003fa2c  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18003fa33  lea     rcx, [rsp+178h+var_78]; pExceptionObject
0x18003fa3b  call    _CxxThrowException_0
0x18003fa40  dec     dword ptr [r13+28h]
0x18003fa44  mov     rdx, [rbx]; Token
0x18003fa47  xor     ecx, ecx; Thread
0x18003fa49  call    cs:__imp_SetThreadToken
0x18003fa4f  or      eax, 0FFFFFFFFh
0x18003fa52  lock xadd [rdi+8], eax
0x18003fa57  cmp     eax, 1
0x18003fa5a  jnz     short loc_18003FA83
0x18003fa5c  mov     rcx, [rdi]; hObject
0x18003fa5f  lea     rax, [rcx-1]
0x18003fa63  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003fa67  ja      short loc_18003FA76
0x18003fa69  call    cs:__imp_CloseHandle
0x18003fa6f  mov     qword ptr [rdi], 0
0x18003fa76  mov     edx, 10h; unsigned __int64
0x18003fa7b  mov     rcx, rdi; void *
0x18003fa7e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003fa83  xor     eax, eax
0x18003fa85  jmp     short loc_18003FA8E
0x18003fa87  mov     eax, dword ptr [rsp+178h+arg_8]
0x18003fa8e  mov     rbx, [rsp+178h+arg_0]
0x18003fa96  add     rsp, 160h
0x18003fa9d  pop     r15
0x18003fa9f  pop     r13
0x18003faa1  pop     rdi
0x18003faa2  retn
```
