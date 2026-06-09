# CVortexReader::OnReadCompleted(ulong,bool)

- ea: `0x18000c920`
- end: `0x18000d1e7`
- name: `?OnReadCompleted@CVortexReader@@MEAAXK_N@Z`
- size: `2247`
- prototype: `void __fastcall(CVortexReader *__hidden this, unsigned int, bool)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180008b70`
- `0x18000b8d0`
- `0x18000bca0`
- `0x18000c920`
- `0x18000e370`
- `0x18000f5f0`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800de26c`
- `0x1800de490`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ca4e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cb09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cc4c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cf22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ca4e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cb09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cc4c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cf22`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000cd6e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000cdef`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d080`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d101`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000cd6e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000cdef`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d080`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d101`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cbbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cdd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ced9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d11e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cbbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cdd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ce94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ced9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d0e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d11e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000ccf3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000cfc1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000ccf3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000cfc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CVortexReader::OnReadCompleted(CVortexReader *this, __int64 a2, _BOOL8 a3)
{
  __int64 v3; // r12
  unsigned int v5; // edi
  unsigned __int64 v6; // rax
  volatile signed __int32 *v7; // rax
  volatile signed __int32 *v8; // rdi
  __int64 v9; // r13
  volatile signed __int32 *v10; // rax
  volatile signed __int32 *v11; // rdi
  volatile signed __int32 **v12; // r14
  void *v13; // rcx
  __int64 v14; // r14
  _DWORD *v15; // rax
  void *v16; // r15
  signed int LastError; // eax
  unsigned int v18; // ecx
  int v19; // r13d
  volatile signed __int32 **v20; // r14
  void *v21; // rcx
  __int64 v22; // r14
  _DWORD *v23; // rax
  void *v24; // r15
  signed int v25; // eax
  unsigned int v26; // ecx
  __int64 v27; // rdx
  unsigned int v28; // eax
  unsigned int v29; // r13d
  unsigned int v30; // edx
  unsigned int v31; // eax
  unsigned int v32; // ebx
  void **pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v34; // [rsp+58h] [rbp-A8h]
  int v35; // [rsp+68h] [rbp-98h]
  int v36; // [rsp+6Ch] [rbp-94h]
  int v37; // [rsp+70h] [rbp-90h]
  void **v38; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v39; // [rsp+B8h] [rbp-48h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  _DWORD *v41; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  __int64 *v43; // [rsp+E0h] [rbp-20h]
  void *v44; // [rsp+168h] [rbp+68h] BYREF

  v3 = (unsigned int)a2;
  if ( !(_DWORD)a2 )
  {
    CHttpReader::OnReadCompleted(this, 0, a3);
    return;
  }
  if ( a3 )
    *((_DWORD *)this + 31) += a2;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_qqIDID(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      *((_QWORD *)this + 32918),
      *((_QWORD *)this + 32920),
      *((_QWORD *)this + 32919),
      a2,
      *((_QWORD *)this + 20),
      a3);
  v5 = 0;
  if ( !*((_QWORD *)this + 32920) )
  {
    v9 = *((_QWORD *)this + 32918);
    if ( v9 )
    {
      if ( *((_QWORD *)this + 32919) )
      {
        v5 = 1;
      }
      else
      {
        v10 = (volatile signed __int32 *)HeapAlloc(hBitsHeap, 8u, 0x10u);
        v11 = v10;
        if ( !v10 )
        {
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
          v39 = 0;
          v38 = &ComError::`vftable';
          v40 = 2147942414LL;
          LODWORD(v41) = 1;
          throw (ComError *)&v38;
        }
        v38 = (void **)v10;
        *((_DWORD *)v10 + 2) = 1;
        *(_QWORD *)v10 = 0;
        v12 = (volatile signed __int32 **)CopyThreadToken(&v44);
        if ( *(_QWORD *)v11 != *(_QWORD *)*v12 )
        {
          if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
          {
            if ( (unsigned __int64)(*(_QWORD *)v11 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              CloseHandle(*(HANDLE *)v11);
              *(_QWORD *)v11 = 0;
            }
            operator delete((void *)v11, 0x10u);
          }
          v11 = *v12;
          v38 = (void **)v11;
          _InterlockedIncrement(v11 + 2);
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v44 + 2, 0xFFFFFFFF) == 1 )
        {
          v13 = v44;
          if ( (unsigned __int64)(*(_QWORD *)v44 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            CloseHandle(*(HANDLE *)v44);
            *(_QWORD *)v44 = 0;
            v13 = v44;
          }
          operator delete(v13, 0x10u);
          v44 = 0;
        }
        LOBYTE(v39) = 0;
        v14 = *((_QWORD *)this + 32913);
        *((_QWORD *)&v39 + 1) = v14;
        _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
        v40 = 0;
        v15 = HeapAlloc(hBitsHeap, 8u, 4u);
        v16 = v15;
        if ( !v15 )
        {
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 4);
          v34 = 0;
          pExceptionObject = &ComError::`vftable';
          v35 = -2147024882;
          v36 = 0;
          v37 = 1;
          throw (ComError *)&pExceptionObject;
        }
        *v15 = 1;
        v41 = v15;
        v42 = 0;
        _InterlockedIncrement(&dword_180145058);
        v43 = &GenericStringHandle<unsigned short>::s_EmptyString;
        if ( !ImpersonateLoggedOnUser(*(HANDLE *)v14) )
        {
          LastError = GetLastError();
          v18 = LastError;
          if ( LastError > 0 )
            v18 = (unsigned __int16)LastError | 0x80070000;
          v34 = 0;
          pExceptionObject = &ComError::`vftable';
          v35 = v18;
          v36 = 0;
          v37 = 1;
          throw (ComError *)&pExceptionObject;
        }
        LOBYTE(v39) = 1;
        v19 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 32917) + 40LL))(
                *((_QWORD *)this + 32917),
                v9);
        SetThreadToken(0, *(HANDLE *)v11);
        if ( _InterlockedExchangeAdd(&dword_180145058, 0xFFFFFFFF) == 1 )
          operator delete(&GenericStringHandle<unsigned short>::s_EmptyString, 0x10u);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16, 0xFFFFFFFF) == 1 )
        {
          operator delete(v16, 4u);
          operator delete(0, 0);
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 8), 0xFFFFFFFF) == 1 )
        {
          if ( (unsigned __int64)(*(_QWORD *)v14 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            CloseHandle(*(HANDLE *)v14);
            *(_QWORD *)v14 = 0;
          }
          operator delete((void *)v14, 0x10u);
        }
        SetThreadToken(0, *(HANDLE *)v11);
        if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
        {
          if ( (unsigned __int64)(*(_QWORD *)v11 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            CloseHandle(*(HANDLE *)v11);
            *(_QWORD *)v11 = 0;
          }
          operator delete((void *)v11, 0x10u);
        }
        if ( v19 )
        {
          *((_QWORD *)this + 32926) += v3;
          v5 = 0;
        }
        else
        {
          v5 = 1;
          *((_QWORD *)this + 32925) += v3;
        }
      }
      goto LABEL_13;
    }
    goto LABEL_12;
  }
  v6 = *((_QWORD *)this + 20);
  if ( v6 >= *((_QWORD *)this + 32922) && v6 < *((_QWORD *)this + 32923) )
  {
    v5 = 2;
LABEL_12:
    *((_QWORD *)this + 32925) += v3;
    goto LABEL_13;
  }
  *((_QWORD *)this + 32926) += v3;
LABEL_13:
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids, v5);
  if ( v5 == 1 )
  {
    v7 = (volatile signed __int32 *)HeapAlloc(hBitsHeap, 8u, 0x10u);
    v8 = v7;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
      v34 = 0;
      pExceptionObject = &ComError::`vftable';
      v35 = -2147024882;
      v36 = 0;
      v37 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v38 = (void **)v7;
    *((_DWORD *)v7 + 2) = 1;
    *(_QWORD *)v7 = 0;
    v20 = (volatile signed __int32 **)CopyThreadToken(&v44);
    if ( *(_QWORD *)v8 != *(_QWORD *)*v20 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        if ( (unsigned __int64)(*(_QWORD *)v8 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(*(HANDLE *)v8);
          *(_QWORD *)v8 = 0;
        }
        operator delete((void *)v8, 0x10u);
      }
      v8 = *v20;
      v38 = (void **)v8;
      _InterlockedIncrement(v8 + 2);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v44 + 2, 0xFFFFFFFF) == 1 )
    {
      v21 = v44;
      if ( (unsigned __int64)(*(_QWORD *)v44 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v44);
        *(_QWORD *)v44 = 0;
        v21 = v44;
      }
      operator delete(v21, 0x10u);
      v44 = 0;
    }
    LOBYTE(v39) = 0;
    v22 = *((_QWORD *)this + 32913);
    *((_QWORD *)&v39 + 1) = v22;
    _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
    v40 = 0;
    v23 = HeapAlloc(hBitsHeap, 8u, 4u);
    v24 = v23;
    if ( !v23 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 4);
      v34 = 0;
      pExceptionObject = &ComError::`vftable';
      v35 = -2147024882;
      v36 = 0;
      v37 = 1;
      throw (ComError *)&pExceptionObject;
    }
    *v23 = 1;
    v41 = v23;
    v42 = 0;
    _InterlockedIncrement(&dword_180145058);
    v43 = &GenericStringHandle<unsigned short>::s_EmptyString;
    if ( !ImpersonateLoggedOnUser(*(HANDLE *)v22) )
    {
      v25 = GetLastError();
      v26 = v25;
      if ( v25 > 0 )
        v26 = (unsigned __int16)v25 | 0x80070000;
      v34 = 0;
      pExceptionObject = &ComError::`vftable';
      v35 = v26;
      v36 = 0;
      v37 = 1;
      throw (ComError *)&pExceptionObject;
    }
    LOBYTE(v39) = 1;
    v27 = *((_QWORD *)this + 32920);
    if ( !v27 )
      v27 = *((_QWORD *)this + 32918);
    v28 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 32917) + 48LL))(
            *((_QWORD *)this + 32917),
            v27,
            *((_QWORD *)this + 32881),
            (unsigned int)v3);
    v29 = v28;
    if ( v28 )
    {
      if ( !byte_180145A34 )
      {
        byte_180145A34 = 1;
        CVortexReader::ReportP2PFailure(this, v28, 1);
      }
    }
    else
    {
      byte_180145A34 = 0;
    }
    SetThreadToken(0, *(HANDLE *)v8);
    if ( _InterlockedExchangeAdd(&dword_180145058, 0xFFFFFFFF) == 1 )
      operator delete(&GenericStringHandle<unsigned short>::s_EmptyString, 0x10u);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24, 0xFFFFFFFF) == 1 )
    {
      operator delete(v24, 4u);
      operator delete(0, 0);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v22 + 8), 0xFFFFFFFF) == 1 )
    {
      if ( (unsigned __int64)(*(_QWORD *)v22 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v22);
        *(_QWORD *)v22 = 0;
      }
      operator delete((void *)v22, 0x10u);
    }
    SetThreadToken(0, *(HANDLE *)v8);
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( (unsigned __int64)(*(_QWORD *)v8 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v8);
        *(_QWORD *)v8 = 0;
      }
      operator delete((void *)v8, 0x10u);
    }
    v30 = v29;
  }
  else if ( v5 == 2 )
  {
    CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)&v38, (CVortexReader *)((char *)this + 263304));
    v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 32917) + 64LL))(
            *((_QWORD *)this + 32917),
            *((_QWORD *)this + 32920),
            *((_QWORD *)this + 32881),
            (unsigned int)v3,
            *((_QWORD *)this + 20));
    v32 = v31;
    if ( v31 )
    {
      if ( !byte_180145A33 )
      {
        byte_180145A33 = 1;
        CVortexReader::ReportP2PFailure(this, v31, 2);
      }
    }
    else
    {
      byte_180145A33 = 0;
    }
    CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)&v38);
    v30 = v32;
  }
  else
  {
    v30 = 0;
  }
  CVortexReader::OnP2pDataProcessed((const void **)this, v30, v3);
}

```

## disassembly

```asm
0x18000c920  mov     [rsp-8+arg_0], rbx
0x18000c925  push    rbp
0x18000c926  push    rsi
0x18000c927  push    rdi
0x18000c928  push    r12
0x18000c92a  push    r13
0x18000c92c  push    r14
0x18000c92e  push    r15
0x18000c930  lea     rbp, [rsp-10h]
0x18000c935  sub     rsp, 110h
0x18000c93c  mov     r12d, edx
0x18000c93f  mov     rsi, rcx
0x18000c942  xor     r15d, r15d
0x18000c945  test    edx, edx
0x18000c947  jnz     short loc_18000C953
0x18000c949  call    ?OnReadCompleted@CHttpReader@@MEAAXK_N@Z; CHttpReader::OnReadCompleted(ulong,bool)
0x18000c94e  jmp     loc_18000D1CC
0x18000c953  test    r8b, r8b
0x18000c956  jz      short loc_18000C95C
0x18000c958  add     [rcx+7Ch], r12d
0x18000c95c  lea     rbx, WPP_GLOBAL_Control
0x18000c963  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c96a  cmp     rcx, rbx
0x18000c96d  jz      short loc_18000C9B9
0x18000c96f  test    dword ptr [rcx+1Ch], 1000h
0x18000c976  jz      short loc_18000C9B9
0x18000c978  movzx   eax, r8b
0x18000c97c  mov     [rsp+140h+var_100], eax
0x18000c980  mov     rax, [rsi+0A0h]
0x18000c987  mov     [rsp+140h+var_108], rax
0x18000c98c  mov     [rsp+140h+var_110], r12d
0x18000c991  mov     rax, [rsi+404B8h]
0x18000c998  mov     [rsp+140h+var_118], rax
0x18000c99d  mov     rax, [rsi+404C0h]
0x18000c9a4  mov     [rsp+140h+var_120], rax
0x18000c9a9  mov     r9, [rsi+404B0h]
0x18000c9b0  mov     rcx, [rcx+10h]
0x18000c9b4  call    WPP_SF_qqIDID
0x18000c9b9  mov     edi, r15d
0x18000c9bc  mov     [rbp+40h+arg_8], r15d
0x18000c9c0  mov     ebx, 0FFFFFFFFh
0x18000c9c5  cmp     [rsi+404C0h], rdi
0x18000c9cc  jz      loc_18000CAD4
0x18000c9d2  mov     rax, [rsi+0A0h]
0x18000c9d9  cmp     rax, [rsi+404D0h]
0x18000c9e0  jb      loc_18000CAC8
0x18000c9e6  cmp     rax, [rsi+404D8h]
0x18000c9ed  jnb     loc_18000CAC8
0x18000c9f3  mov     edi, 2
0x18000c9f8  add     [rsi+404E8h], r12
0x18000c9ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca06  lea     r13, WPP_GLOBAL_Control
0x18000ca0d  cmp     rcx, r13
0x18000ca10  jz      short loc_18000CA33
0x18000ca12  test    dword ptr [rcx+1Ch], 1000h
0x18000ca19  jz      short loc_18000CA33
0x18000ca1b  mov     edx, 38h ; '8'
0x18000ca20  mov     r9d, edi
0x18000ca23  lea     r8, WPP_4c947aaf6cc236f8020d4926759e0000_Traceguids
0x18000ca2a  mov     rcx, [rcx+10h]
0x18000ca2e  call    WPP_SF_d
0x18000ca33  cmp     edi, 1
0x18000ca36  jnz     loc_18000D140
0x18000ca3c  mov     edx, 8; dwFlags
0x18000ca41  mov     r8d, 10h; dwBytes
0x18000ca47  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18000ca4e  call    cs:__imp_HeapAlloc
0x18000ca54  mov     rdi, rax
0x18000ca57  test    rax, rax
0x18000ca5a  jnz     loc_18000CE56
0x18000ca60  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca67  cmp     rcx, r13
0x18000ca6a  jz      short loc_18000CA8D
0x18000ca6c  test    byte ptr [rcx+1Ch], 4
0x18000ca70  jz      short loc_18000CA8D
0x18000ca72  mov     edx, 0Ah
0x18000ca77  mov     r9d, 10h
0x18000ca7d  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18000ca84  mov     rcx, [rcx+10h]
0x18000ca88  call    WPP_SF_d
0x18000ca8d  xorps   xmm0, xmm0
0x18000ca90  movups  [rsp+140h+var_E8], xmm0
0x18000ca95  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000ca9c  mov     [rsp+140h+pExceptionObject], rax
0x18000caa1  mov     [rsp+140h+var_D8], 8007000Eh
0x18000caa9  mov     [rsp+140h+var_D4], r15d
0x18000caae  mov     [rsp+140h+var_D0], 1
0x18000cab6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000cabd  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18000cac2  call    _CxxThrowException_0
0x18000cac8  add     [rsi+404F0h], r12
0x18000cacf  jmp     loc_18000C9FF
0x18000cad4  mov     r13, [rsi+404B0h]
0x18000cadb  test    r13, r13
0x18000cade  jz      loc_18000C9F8
0x18000cae4  cmp     [rsi+404B8h], rdi
0x18000caeb  jbe     short loc_18000CAF7
0x18000caed  mov     edi, 1
0x18000caf2  jmp     loc_18000C9FF
0x18000caf7  mov     edx, 8; dwFlags
0x18000cafc  mov     r8d, 10h; dwBytes
0x18000cb02  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18000cb09  call    cs:__imp_HeapAlloc
0x18000cb0f  mov     rdi, rax
0x18000cb12  test    rax, rax
0x18000cb15  jnz     short loc_18000CB80
0x18000cb17  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb1e  lea     r13, WPP_GLOBAL_Control
0x18000cb25  cmp     rcx, r13
0x18000cb28  jz      short loc_18000CB4B
0x18000cb2a  test    byte ptr [rcx+1Ch], 4
0x18000cb2e  jz      short loc_18000CB4B
0x18000cb30  mov     edx, 0Ah
0x18000cb35  mov     r9d, 10h
0x18000cb3b  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18000cb42  mov     rcx, [rcx+10h]
0x18000cb46  call    WPP_SF_d
0x18000cb4b  xorps   xmm0, xmm0
0x18000cb4e  movups  [rbp+40h+var_88], xmm0
0x18000cb52  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000cb59  mov     [rbp+40h+var_90], rax
0x18000cb5d  mov     dword ptr [rbp+40h+var_78], 8007000Eh
0x18000cb64  mov     dword ptr [rbp+40h+var_78+4], r15d
0x18000cb68  mov     dword ptr [rbp+40h+var_70], 1
0x18000cb6f  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000cb76  lea     rcx, [rbp+40h+var_90]; pExceptionObject
0x18000cb7a  call    _CxxThrowException_0
0x18000cb80  mov     [rbp+40h+var_90], rdi
0x18000cb84  mov     dword ptr [rax+8], 1
0x18000cb8b  mov     [rax], r15
0x18000cb8e  lea     rcx, [rbp+40h+arg_18]
0x18000cb92  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x18000cb97  mov     r14, rax
0x18000cb9a  mov     rcx, [rax]
0x18000cb9d  mov     rdx, [rcx]
0x18000cba0  cmp     [rdi], rdx
0x18000cba3  jz      short loc_18000CBDF
0x18000cba5  mov     ecx, ebx
0x18000cba7  lock xadd [rdi+8], ecx
0x18000cbac  cmp     ecx, 1
0x18000cbaf  jnz     short loc_18000CBD4
0x18000cbb1  mov     rcx, [rdi]; hObject
0x18000cbb4  lea     rdx, [rcx-1]
0x18000cbb8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000cbbc  ja      short loc_18000CBC7
0x18000cbbe  call    cs:__imp_CloseHandle
0x18000cbc4  mov     [rdi], r15
0x18000cbc7  mov     edx, 10h; unsigned __int64
0x18000cbcc  mov     rcx, rdi; void *
0x18000cbcf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cbd4  mov     rdi, [r14]
0x18000cbd7  mov     [rbp+40h+var_90], rdi
0x18000cbdb  lock inc dword ptr [rdi+8]
0x18000cbdf  mov     rcx, [rbp+40h+arg_18]
0x18000cbe3  mov     eax, ebx
0x18000cbe5  lock xadd [rcx+8], eax
0x18000cbea  cmp     eax, 1
0x18000cbed  jnz     short loc_18000CC22
0x18000cbef  mov     rcx, [rbp+40h+arg_18]
0x18000cbf3  mov     rdx, [rcx]
0x18000cbf6  lea     rax, [rdx-1]
0x18000cbfa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000cbfe  ja      short loc_18000CC14
0x18000cc00  mov     rcx, rdx; hObject
0x18000cc03  call    cs:__imp_CloseHandle
0x18000cc09  mov     rax, [rbp+40h+arg_18]
0x18000cc0d  mov     [rax], r15
0x18000cc10  mov     rcx, [rbp+40h+arg_18]; void *
0x18000cc14  mov     edx, 10h; unsigned __int64
0x18000cc19  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cc1e  mov     [rbp+40h+arg_18], r15
0x18000cc22  mov     byte ptr [rbp+40h+var_88], 0
0x18000cc26  mov     r14, [rsi+40488h]
0x18000cc2d  mov     qword ptr [rbp+40h+var_88+8], r14
0x18000cc31  lock inc dword ptr [r14+8]
0x18000cc36  mov     [rbp+40h+var_78], r15
0x18000cc3a  mov     edx, 8; dwFlags
0x18000cc3f  mov     r8d, 4; dwBytes
0x18000cc45  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18000cc4c  call    cs:__imp_HeapAlloc
0x18000cc52  mov     r15, rax
0x18000cc55  test    rax, rax
0x18000cc58  jnz     short loc_18000CCCC
0x18000cc5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc61  lea     r13, WPP_GLOBAL_Control
0x18000cc68  cmp     rcx, r13
0x18000cc6b  jz      short loc_18000CC8E
0x18000cc6d  test    byte ptr [rcx+1Ch], 4
0x18000cc71  jz      short loc_18000CC8E
0x18000cc73  mov     edx, 0Ah
0x18000cc78  mov     r9d, 4
0x18000cc7e  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18000cc85  mov     rcx, [rcx+10h]
0x18000cc89  call    WPP_SF_d
0x18000cc8e  xorps   xmm0, xmm0
0x18000cc91  movups  [rsp+140h+var_E8], xmm0
0x18000cc96  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000cc9d  mov     [rsp+140h+pExceptionObject], rax
0x18000cca2  mov     [rsp+140h+var_D8], 8007000Eh
0x18000ccaa  mov     [rsp+140h+var_D4], 0
0x18000ccb2  mov     [rsp+140h+var_D0], 1
0x18000ccba  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000ccc1  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18000ccc6  call    _CxxThrowException_0
0x18000cccc  mov     dword ptr [rax], 1
0x18000ccd2  mov     [rbp+40h+var_70], r15
0x18000ccd6  mov     [rbp+40h+var_68], 0
0x18000ccde  lock inc cs:dword_180145058
0x18000cce5  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x18000ccec  mov     [rbp+40h+var_60], rax
0x18000ccf0  mov     rcx, [r14]; hToken
0x18000ccf3  call    cs:__imp_ImpersonateLoggedOnUser
0x18000ccf9  test    eax, eax
0x18000ccfb  jnz     short loc_18000CD4C
0x18000ccfd  call    cs:__imp_GetLastError
0x18000cd03  mov     ecx, eax
0x18000cd05  test    eax, eax
0x18000cd07  jle     short loc_18000CD12
0x18000cd09  movzx   ecx, ax
0x18000cd0c  or      ecx, 80070000h
0x18000cd12  xorps   xmm0, xmm0
0x18000cd15  movups  [rsp+140h+var_E8], xmm0
0x18000cd1a  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000cd21  mov     [rsp+140h+pExceptionObject], rax
0x18000cd26  mov     [rsp+140h+var_D8], ecx
0x18000cd2a  mov     [rsp+140h+var_D4], 0
0x18000cd32  mov     [rsp+140h+var_D0], 1
0x18000cd3a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000cd41  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18000cd46  call    _CxxThrowException_0
0x18000cd4c  mov     byte ptr [rbp+40h+var_88], 1
0x18000cd50  mov     rcx, [rsi+404A8h]
0x18000cd57  mov     rax, [rcx]
0x18000cd5a  mov     rdx, r13
0x18000cd5d  mov     rax, [rax+28h]
0x18000cd61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd66  mov     r13d, eax
0x18000cd69  mov     rdx, [rdi]; Token
0x18000cd6c  xor     ecx, ecx; Thread
0x18000cd6e  call    cs:__imp_SetThreadToken
0x18000cd74  mov     ecx, ebx
0x18000cd76  lock xadd cs:dword_180145058, ecx
0x18000cd7e  cmp     ecx, 1
0x18000cd81  jnz     short loc_18000CD94
0x18000cd83  mov     edx, 10h; unsigned __int64
0x18000cd88  lea     rcx, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; void *
0x18000cd8f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cd94  mov     eax, ebx
0x18000cd96  lock xadd [r15], eax
0x18000cd9b  cmp     eax, 1
0x18000cd9e  jnz     short loc_18000CDB6
0x18000cda0  mov     edx, 4; unsigned __int64
0x18000cda5  mov     rcx, r15; void *
0x18000cda8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cdad  xor     edx, edx; unsigned __int64
0x18000cdaf  xor     ecx, ecx; void *
0x18000cdb1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cdb6  mov     eax, ebx
0x18000cdb8  lock xadd [r14+8], eax
0x18000cdbe  cmp     eax, 1
0x18000cdc1  jnz     short loc_18000CDEA
0x18000cdc3  mov     rcx, [r14]; hObject
0x18000cdc6  lea     rax, [rcx-1]
0x18000cdca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000cdce  ja      short loc_18000CDDD
0x18000cdd0  call    cs:__imp_CloseHandle
0x18000cdd6  mov     qword ptr [r14], 0
0x18000cddd  mov     edx, 10h; unsigned __int64
0x18000cde2  mov     rcx, r14; void *
0x18000cde5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cdea  mov     rdx, [rdi]; Token
0x18000cded  xor     ecx, ecx; Thread
0x18000cdef  call    cs:__imp_SetThreadToken
0x18000cdf5  mov     eax, ebx
0x18000cdf7  lock xadd [rdi+8], eax
0x18000cdfc  cmp     eax, 1
0x18000cdff  jnz     short loc_18000CE28
0x18000ce01  mov     rcx, [rdi]; hObject
0x18000ce04  lea     rax, [rcx-1]
0x18000ce08  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ce0c  ja      short loc_18000CE1B
0x18000ce0e  call    cs:__imp_CloseHandle
0x18000ce14  mov     qword ptr [rdi], 0
0x18000ce1b  mov     edx, 10h; unsigned __int64
0x18000ce20  mov     rcx, rdi; void *
0x18000ce23  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ce28  mov     rax, r12
0x18000ce2b  test    r13d, r13d
0x18000ce2e  jz      short loc_18000CE42
0x18000ce30  add     [rsi+404F0h], rax
0x18000ce37  mov     edi, [rbp+40h+arg_8]
0x18000ce3a  xor     r15d, r15d
0x18000ce3d  jmp     loc_18000C9FF
0x18000ce42  mov     edi, 1
0x18000ce47  add     [rsi+404E8h], rax
0x18000ce4e  xor     r15d, r15d
0x18000ce51  jmp     loc_18000C9FF
0x18000ce56  mov     [rbp+40h+var_90], rdi
0x18000ce5a  mov     dword ptr [rax+8], 1
0x18000ce61  mov     [rax], r15
  ... truncated ...
```
