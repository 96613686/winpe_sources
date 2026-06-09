# AutoThreadpool::QueueThreadpoolWork(void (*)(void *),void *)

- ea: `0x18000f1c0`
- end: `0x18000f5e6`
- name: `?QueueThreadpoolWork@AutoThreadpool@@QEAAJP6AXPEAX@Z0@Z`
- size: `1062`
- prototype: `__int64 __fastcall(AutoThreadpool *__hidden this, void (*)(void *), void *)`
- caller_count: `11`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010890`
- `0x180035db0`
- `0x1800657fc`
- `0x180078e70`
- `0x18009d9c0`
- `0x1800a1230`
- `0x1800b41a0`
- `0x1800f3350`
- `0x1800f39e0`
- `0x1800f3ba0`
- `0x1800f3d60`

## callees

- `0x180006640`
- `0x18000e370`
- `0x18000f1c0`
- `0x180033480`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800ab7fc`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f2e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f2e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f49c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f49c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f23a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f23a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f560`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f59d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f560`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f59d`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18000f280`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18000f280`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000f47a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000f47a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000f523`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000f523`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f445`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f445`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AutoThreadpool::QueueThreadpoolWork(AutoThreadpool *this, void (*a2)(void *), void *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  struct _RTL_CRITICAL_SECTION *v7; // r14
  void *v8; // rax
  void *v9; // rsi
  _DWORD *v10; // rax
  volatile signed __int32 **v11; // r12
  __int64 v12; // r8
  char *v13; // rcx
  volatile signed __int32 *v14; // rax
  void *v15; // rcx
  PTP_WORK ThreadpoolWork; // rax
  struct _TP_WORK *v17; // rdi
  unsigned int LastError; // ecx
  const ComError *v20; // rbx
  const ComError *v21; // [rsp+30h] [rbp-168h] BYREF
  char v22[8]; // [rsp+38h] [rbp-160h] BYREF
  char *v23; // [rsp+40h] [rbp-158h]
  void *v24; // [rsp+48h] [rbp-150h]
  void **pExceptionObject; // [rsp+50h] [rbp-148h] BYREF
  __int128 v26; // [rsp+58h] [rbp-140h]
  int v27; // [rsp+68h] [rbp-130h]
  int v28; // [rsp+6Ch] [rbp-12Ch]
  int v29; // [rsp+70h] [rbp-128h]
  void **v30; // [rsp+B0h] [rbp-E8h] BYREF
  __int128 v31; // [rsp+B8h] [rbp-E0h]
  int v32; // [rsp+C8h] [rbp-D0h]
  int v33; // [rsp+CCh] [rbp-CCh]
  int v34; // [rsp+D0h] [rbp-C8h]
  void **v35; // [rsp+110h] [rbp-88h] BYREF
  __int128 v36; // [rsp+118h] [rbp-80h]
  unsigned int v37; // [rsp+128h] [rbp-70h]
  int v38; // [rsp+12Ch] [rbp-6Ch]
  int v39; // [rsp+130h] [rbp-68h]
  unsigned int v41; // [rsp+1A0h] [rbp+8h]
  void *v42; // [rsp+1B8h] [rbp+20h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 144);
  v23 = (char *)this + 144;
  if ( *((_BYTE *)this + 184)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v6);
  }
  EnterCriticalSection(v6);
  v22[0] = 1;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  if ( *((_BYTE *)this + 48)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, (char *)this + 8);
  }
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8)) )
  {
    try
    {
      if ( !*((_QWORD *)this + 7) )
      {
        v26 = 0;
        pExceptionObject = &ComError::`vftable';
        v27 = -2147019873;
        v28 = 137;
        v29 = 1;
        throw (ComError *)&pExceptionObject;
      }
      v8 = HeapAlloc(hBitsHeap, 8u, 0x18u);
      v9 = v8;
      if ( !v8 )
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 24);
        v31 = 0;
        v30 = &ComError::`vftable';
        v32 = -2147024882;
        v33 = 0;
        v34 = 1;
        throw (ComError *)&v30;
      }
      v42 = v8;
      v10 = operator new(0x10u);
      *((_QWORD *)v9 + 2) = v10;
      v10[2] = 1;
      **((_QWORD **)v9 + 2) = 0;
      v24 = v9;
      *(_QWORD *)v9 = a2;
      *((_QWORD *)v9 + 1) = a3;
      v11 = (volatile signed __int32 **)CopyThreadToken(&v42);
      v12 = *((_QWORD *)v9 + 2);
      if ( *(_QWORD *)v12 != *(_QWORD *)*v11 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 8), 0xFFFFFFFF) == 1 )
        {
          v13 = (char *)**((_QWORD **)v9 + 2);
          if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            CloseHandle(v13);
            **((_QWORD **)v9 + 2) = 0;
          }
          operator delete(*((void **)v9 + 2), 0x10u);
          *((_QWORD *)v9 + 2) = 0;
        }
        v14 = *v11;
        *((_QWORD *)v9 + 2) = *v11;
        _InterlockedIncrement(v14 + 2);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v42 + 2, 0xFFFFFFFF) == 1 )
      {
        v15 = v42;
        if ( (unsigned __int64)(*(_QWORD *)v42 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          CloseHandle(*(HANDLE *)v42);
          *(_QWORD *)v42 = 0;
          v15 = v42;
        }
        operator delete(v15, 0x10u);
      }
      ThreadpoolWork = CreateThreadpoolWork(
                         (PTP_WORK_CALLBACK)AutoThreadpool::ThreadpoolWorkItemCallback,
                         v9,
                         (PTP_CALLBACK_ENVIRON)((char *)this + 64));
      v17 = ThreadpoolWork;
      if ( !ThreadpoolWork )
      {
        if ( (int)GetLastError() > 0 )
          LastError = (unsigned __int16)GetLastError() | 0x80070000;
        else
          LastError = GetLastError();
        v36 = 0;
        v35 = &ComError::`vftable';
        v37 = LastError;
        v38 = 151;
        v39 = 1;
        throw (ComError *)&v35;
      }
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_7a43e90641713c5942580354798d2ea8_Traceguids,
          ThreadpoolWork);
      SubmitThreadpoolWork(v17);
      if ( LOBYTE(v7[1].DebugInfo)
        && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v7);
      }
      LeaveCriticalSection(v7);
    }
    catch ( const ComError *v21 )
    {
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        v20 = v21;
      }
      else
      {
        v20 = v21;
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_7a43e90641713c5942580354798d2ea8_Traceguids,
          *((unsigned int *)v20 + 6),
          *((_DWORD *)v20 + 7));
      }
      CCritSec2::leave((AutoThreadpool *)((char *)this + 8));
      v41 = *((_DWORD *)v20 + 6);
      HoldCritSec::~HoldCritSec((HoldCritSec *)v22);
      return v41;
    }
    if ( LOBYTE(v6[1].DebugInfo)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v6);
    }
    LeaveCriticalSection(v6);
    return 0;
  }
  else
  {
    HoldCritSec::~HoldCritSec((HoldCritSec *)v22);
    return 2147500036LL;
  }
}

```

## disassembly

```asm
0x18000f1c0  mov     [rsp+arg_8], rbx
0x18000f1c5  mov     [rsp+arg_10], rsi
0x18000f1ca  mov     [rsp+arg_0], rcx
0x18000f1cf  push    rdi
0x18000f1d0  push    r12
0x18000f1d2  push    r13
0x18000f1d4  push    r14
0x18000f1d6  push    r15
0x18000f1d8  sub     rsp, 170h
0x18000f1df  mov     r15, r8
0x18000f1e2  mov     r12, rdx
0x18000f1e5  mov     rdi, rcx
0x18000f1e8  lea     rbx, [rcx+90h]
0x18000f1ef  mov     [rsp+198h+var_158], rbx
0x18000f1f4  cmp     byte ptr [rbx+28h], 0
0x18000f1f8  jz      short loc_18000F230
0x18000f1fa  lea     r13, WPP_GLOBAL_Control
0x18000f201  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f208  cmp     rcx, r13
0x18000f20b  jz      short loc_18000F237
0x18000f20d  test    dword ptr [rcx+1Ch], 100h
0x18000f214  jz      short loc_18000F237
0x18000f216  mov     edx, 0Fh
0x18000f21b  mov     r9, rbx
0x18000f21e  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18000f225  mov     rcx, [rcx+10h]
0x18000f229  call    WPP_SF_q
0x18000f22e  jmp     short loc_18000F237
0x18000f230  lea     r13, WPP_GLOBAL_Control
0x18000f237  mov     rcx, rbx; lpCriticalSection
0x18000f23a  call    cs:__imp_EnterCriticalSection
0x18000f240  mov     [rsp+198h+var_160], 1
0x18000f245  lea     r14, [rdi+8]
0x18000f249  cmp     byte ptr [r14+28h], 0
0x18000f24e  jz      short loc_18000F27D
0x18000f250  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f257  cmp     rcx, r13
0x18000f25a  jz      short loc_18000F27D
0x18000f25c  test    dword ptr [rcx+1Ch], 100h
0x18000f263  jz      short loc_18000F27D
0x18000f265  mov     edx, 11h
0x18000f26a  mov     r9, r14
0x18000f26d  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18000f274  mov     rcx, [rcx+10h]
0x18000f278  call    WPP_SF_q
0x18000f27d  mov     rcx, r14; lpCriticalSection
0x18000f280  call    cs:__imp_TryEnterCriticalSection
0x18000f286  test    eax, eax
0x18000f288  jz      loc_18000F5BA
0x18000f28e  cmp     qword ptr [rdi+38h], 0
0x18000f293  jnz     short loc_18000F2D2
0x18000f295  xorps   xmm0, xmm0
0x18000f298  movups  [rsp+198h+var_140], xmm0
0x18000f29d  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000f2a4  mov     [rsp+198h+pExceptionObject], rax
0x18000f2a9  mov     [rsp+198h+var_130], 8007139Fh
0x18000f2b1  mov     [rsp+198h+var_12C], 89h
0x18000f2b9  mov     [rsp+198h+var_128], 1
0x18000f2c1  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000f2c8  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x18000f2cd  call    _CxxThrowException_0
0x18000f2d2  mov     edx, 8; dwFlags
0x18000f2d7  mov     r8d, 18h; dwBytes
0x18000f2dd  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18000f2e4  call    cs:__imp_HeapAlloc
0x18000f2ea  mov     rsi, rax
0x18000f2ed  test    rax, rax
0x18000f2f0  jnz     short loc_18000F36E
0x18000f2f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2f9  cmp     rcx, r13
0x18000f2fc  jz      short loc_18000F31F
0x18000f2fe  test    byte ptr [rcx+1Ch], 4
0x18000f302  jz      short loc_18000F31F
0x18000f304  mov     edx, 0Ah
0x18000f309  mov     r9d, 18h
0x18000f30f  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x18000f316  mov     rcx, [rcx+10h]
0x18000f31a  call    WPP_SF_d
0x18000f31f  xorps   xmm0, xmm0
0x18000f322  movups  [rsp+198h+var_E0], xmm0
0x18000f32a  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000f331  mov     [rsp+198h+var_E8], rax
0x18000f339  mov     [rsp+198h+var_D0], 8007000Eh
0x18000f344  mov     [rsp+198h+var_CC], 0
0x18000f34f  mov     [rsp+198h+var_C8], 1
0x18000f35a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000f361  lea     rcx, [rsp+198h+var_E8]; pExceptionObject
0x18000f369  call    _CxxThrowException_0
0x18000f36e  mov     [rsp+198h+arg_18], rsi
0x18000f376  mov     ecx, 10h; dwBytes
0x18000f37b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f380  mov     [rsi+10h], rax
0x18000f384  mov     dword ptr [rax+8], 1
0x18000f38b  mov     rax, [rsi+10h]
0x18000f38f  mov     qword ptr [rax], 0
0x18000f396  mov     [rsp+198h+var_150], rsi
0x18000f39b  mov     [rsi], r12
0x18000f39e  mov     [rsi+8], r15
0x18000f3a2  lea     rcx, [rsp+198h+arg_18]
0x18000f3aa  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x18000f3af  mov     r12, rax
0x18000f3b2  mov     r8, [rsi+10h]
0x18000f3b6  mov     rcx, [rax]
0x18000f3b9  mov     rdx, [rcx]
0x18000f3bc  mov     r15d, 0FFFFFFFFh
0x18000f3c2  cmp     [r8], rdx
0x18000f3c5  jz      short loc_18000F419
0x18000f3c7  mov     ecx, r15d
0x18000f3ca  lock xadd [r8+8], ecx
0x18000f3d0  cmp     ecx, 1
0x18000f3d3  jnz     short loc_18000F40D
0x18000f3d5  mov     rax, [rsi+10h]
0x18000f3d9  mov     rcx, [rax]; hObject
0x18000f3dc  lea     rax, [rcx-1]
0x18000f3e0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f3e4  ja      short loc_18000F3F7
0x18000f3e6  call    cs:__imp_CloseHandle
0x18000f3ec  mov     rax, [rsi+10h]
0x18000f3f0  mov     qword ptr [rax], 0
0x18000f3f7  mov     edx, 10h; unsigned __int64
0x18000f3fc  mov     rcx, [rsi+10h]; void *
0x18000f400  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f405  mov     qword ptr [rsi+10h], 0
0x18000f40d  mov     rax, [r12]
0x18000f411  mov     [rsi+10h], rax
0x18000f415  lock inc dword ptr [rax+8]
0x18000f419  mov     rax, [rsp+198h+arg_18]
0x18000f421  lock xadd [rax+8], r15d
0x18000f427  cmp     r15d, 1
0x18000f42b  jnz     short loc_18000F46C
0x18000f42d  mov     rcx, [rsp+198h+arg_18]
0x18000f435  mov     rdx, [rcx]
0x18000f438  lea     rax, [rdx-1]
0x18000f43c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f440  ja      short loc_18000F462
0x18000f442  mov     rcx, rdx; hObject
0x18000f445  call    cs:__imp_CloseHandle
0x18000f44b  mov     rax, [rsp+198h+arg_18]
0x18000f453  mov     qword ptr [rax], 0
0x18000f45a  mov     rcx, [rsp+198h+arg_18]; void *
0x18000f462  mov     edx, 10h; unsigned __int64
0x18000f467  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f46c  lea     r8, [rdi+40h]; pcbe
0x18000f470  mov     rdx, rsi; pv
0x18000f473  lea     rcx, ?ThreadpoolWorkItemCallback@AutoThreadpool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000f47a  call    cs:__imp_CreateThreadpoolWork
0x18000f480  mov     rdi, rax
0x18000f483  test    rax, rax
0x18000f486  jnz     short loc_18000F4F6
0x18000f488  call    cs:__imp_GetLastError
0x18000f48e  test    eax, eax
0x18000f490  jg      short loc_18000F49C
0x18000f492  call    cs:__imp_GetLastError
0x18000f498  mov     ecx, eax
0x18000f49a  jmp     short loc_18000F4AB
0x18000f49c  call    cs:__imp_GetLastError
0x18000f4a2  movzx   ecx, ax
0x18000f4a5  or      ecx, 80070000h
0x18000f4ab  xorps   xmm0, xmm0
0x18000f4ae  movups  [rsp+198h+var_80], xmm0
0x18000f4b6  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18000f4bd  mov     [rsp+198h+var_88], rax
0x18000f4c5  mov     [rsp+198h+var_70], ecx
0x18000f4cc  mov     [rsp+198h+var_6C], 97h
0x18000f4d7  mov     [rsp+198h+var_68], 1
0x18000f4e2  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000f4e9  lea     rcx, [rsp+198h+var_88]; pExceptionObject
0x18000f4f1  call    _CxxThrowException_0
0x18000f4f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4fd  cmp     rcx, r13
0x18000f500  jz      short loc_18000F520
0x18000f502  test    byte ptr [rcx+1Ch], 1
0x18000f506  jz      short loc_18000F520
0x18000f508  mov     edx, 0Eh
0x18000f50d  mov     r9, rdi
0x18000f510  lea     r8, WPP_7a43e90641713c5942580354798d2ea8_Traceguids
0x18000f517  mov     rcx, [rcx+10h]
0x18000f51b  call    WPP_SF_q
0x18000f520  mov     rcx, rdi; pwk
0x18000f523  call    cs:__imp_SubmitThreadpoolWork
0x18000f529  cmp     byte ptr [r14+28h], 0
0x18000f52e  jz      short loc_18000F55D
0x18000f530  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f537  cmp     rcx, r13
0x18000f53a  jz      short loc_18000F55D
0x18000f53c  test    dword ptr [rcx+1Ch], 100h
0x18000f543  jz      short loc_18000F55D
0x18000f545  mov     edx, 10h
0x18000f54a  mov     r9, r14
0x18000f54d  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18000f554  mov     rcx, [rcx+10h]
0x18000f558  call    WPP_SF_q
0x18000f55d  mov     rcx, r14; lpCriticalSection
0x18000f560  call    cs:__imp_LeaveCriticalSection
0x18000f566  nop
0x18000f567  cmp     byte ptr [rbx+28h], 0
0x18000f56b  jz      short loc_18000F59A
0x18000f56d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f574  cmp     rcx, r13
0x18000f577  jz      short loc_18000F59A
0x18000f579  test    dword ptr [rcx+1Ch], 100h
0x18000f580  jz      short loc_18000F59A
0x18000f582  mov     edx, 10h
0x18000f587  mov     r9, rbx
0x18000f58a  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18000f591  mov     rcx, [rcx+10h]
0x18000f595  call    WPP_SF_q
0x18000f59a  mov     rcx, rbx; lpCriticalSection
0x18000f59d  call    cs:__imp_LeaveCriticalSection
0x18000f5a3  xor     eax, eax
0x18000f5a5  jmp     short loc_18000F5C9
0x18000f5a7  lea     rcx, [rsp+198h+var_160]; this
0x18000f5ac  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x18000f5b1  mov     eax, dword ptr [rsp+198h+arg_0]
0x18000f5b8  jmp     short loc_18000F5C9
0x18000f5ba  lea     rcx, [rsp+198h+var_160]; this
0x18000f5bf  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x18000f5c4  mov     eax, 80004004h
0x18000f5c9  lea     r11, [rsp+198h+var_28]
0x18000f5d1  mov     rbx, [r11+38h]
0x18000f5d5  mov     rsi, [r11+40h]
0x18000f5d9  mov     rsp, r11
0x18000f5dc  pop     r15
0x18000f5de  pop     r14
0x18000f5e0  pop     r13
0x18000f5e2  pop     r12
0x18000f5e4  pop     rdi
0x18000f5e5  retn
```
