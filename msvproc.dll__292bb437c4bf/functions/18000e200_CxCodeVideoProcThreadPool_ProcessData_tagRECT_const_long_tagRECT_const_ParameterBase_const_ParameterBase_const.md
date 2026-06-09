# CxCodeVideoProcThreadPool::ProcessData(tagRECT const &,long (*)(tagRECT const &,ParameterBase const *),ParameterBase const *)

- ea: `0x18000e200`
- end: `0x18000e932`
- name: `?ProcessData@CxCodeVideoProcThreadPool@@QEAAJAEBUtagRECT@@P6AJ0PEBUParameterBase@@@Z1@Z`
- size: `1842`
- prototype: `__int64 __fastcall(CxCodeVideoProcThreadPool *__hidden this, const struct tagRECT *, int (*)(const struct tagRECT *, const struct ParameterBase *), const struct ParameterBase *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18000b560`
- `0x18002a38c`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000e090`
- `0x18000e200`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18003639c`
- `0x180059cfc`
- `0x1800751c8`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e3b8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e3b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e8b9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e8b9`
- `MFPlat!MFPutWorkItem2` at `0x18000e35c`
- `MFPlat!MFPutWorkItem2` at `0x18000e35c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000e4d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000e5c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000e678`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000e722`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000e4d1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000e5c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000e678`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000e722`

## string_xrefs

- `0x18000e337`: `CxCodeVideoProcThread::PutWorkItem`
- `0x18000e6ca`: `CxCodeVideoProcThread::PutWorkItem`
- `0x18000e219`: `CxCodeVideoProcThreadPool::ProcessData`
- `0x18000e59e`: `CxCodeVideoProcThreadPool::ProcessData`
- `0x18000e61d`: `CxCodeVideoProcThreadPool::ProcessData`
- `0x18000e64e`: `CxCodeVideoProcThreadPool::ProcessData`
- `0x18000e6f8`: `CxCodeVideoProcThreadPool::ProcessData`
- `0x18000e774`: `CxCodeVideoProcThreadPool::ProcessData`
- `0x18000e7a2`: `CxCodeVideoProcThreadPool::ProcessData`
- `0x18000e7eb`: `CxCodeVideoProcThreadPool::ProcessData`
- `0x18000e8e8`: `CxCodeVideoProcThreadPool::ProcessData`
- `0x18000e8dc`: `Some threads are still running`
- `0x18000e7e4`: `Thread pool state is invalid; At this point, the state has to be XVP_RUNNING`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcThreadPool::ProcessData(
        CxCodeVideoProcThreadPool *this,
        const struct tagRECT *a2,
        int (*a3)(const struct tagRECT *, const struct ParameterBase *),
        const struct ParameterBase *a4)
{
  __int64 v7; // rdx
  int (*v8)(const struct tagRECT *, const struct ParameterBase *); // r10
  HRESULT v9; // ebx
  unsigned int v10; // r8d
  LONG top; // r14d
  signed int v12; // r13d
  __int64 v13; // rbp
  int v14; // r15d
  DWORD v15; // ecx
  LONG bottom; // r8d
  __int64 v17; // rax
  LONG left; // ecx
  LONG right; // edx
  __int64 v20; // rsi
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rsi
  __int64 i; // rax
  CallStackTracing *v27; // rcx
  __int64 v29; // rcx
  CallStackTracing *v30; // rcx
  __int64 v31; // rdx
  __int64 *v32; // rax
  CallStackTracing *v33; // rax
  CallStackTracing *v34; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v36; // rax
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  struct CallStackContext *v43; // rax
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  struct CallStackContext *v47; // rax
  _BYTE v48[8]; // [rsp+30h] [rbp-58h] BYREF
  struct tagRECT v49; // [rsp+38h] [rbp-50h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v48, "CxCodeVideoProcThreadPool::ProcessData", 233);
  v8 = a3;
  if ( !a3 )
  {
    v30 = CallStackTracing::s_wpInstance;
    v9 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v30 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v30 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v30);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CxCodeVideoProcThreadPool::ProcessData",
          233,
          -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v31 = 17;
LABEL_48:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, WPP_31017d59e5fa36e4c5717ad5ebbdb595_Traceguids, this, v9);
    goto LABEL_31;
  }
  v9 = 0;
  if ( *((_DWORD *)this + 5) == 2 )
    goto LABEL_3;
  v9 = XvpOriginateError<77>(
         "CxCodeVideoProcThreadPool::ProcessData",
         v7,
         L"Thread pool state is invalid; At this point, the state has to be XVP_RUNNING");
  if ( v9 < 0 )
  {
    v36 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v37;
      if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
      {
        v36 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v36 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v36 + 8) )
    {
      v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
      if ( *((_DWORD *)v38 + 499) != v9 )
        CallStackContext::TraceFailure(v38, "CxCodeVideoProcThreadPool::ProcessData", 237, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v31 = 18;
    goto LABEL_48;
  }
  v8 = a3;
LABEL_3:
  v10 = *((_DWORD *)this + 4);
  if ( v10 == 1 )
  {
    v9 = ((__int64 (__fastcall *)(const struct tagRECT *, const struct ParameterBase *))v8)(a2, a4);
    if ( v9 >= 0 )
      goto LABEL_31;
    v32 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v33;
      if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
      {
        v32 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v32 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
      if ( *((_DWORD *)v39 + 499) != v9 )
        CallStackContext::TraceFailure(v39, "CxCodeVideoProcThreadPool::ProcessData", 243, v9);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v31 = 19;
    goto LABEL_48;
  }
  top = a2->top;
  v12 = ((v10 - top + a2->bottom - 1) / v10 + 1) & 0xFFFFFFFE;
  if ( v12 <= 32 )
    v12 = 32;
  v13 = 0;
  v14 = top + v12;
  while ( 1 )
  {
    v15 = *((_DWORD *)this + 4);
    if ( (unsigned int)v13 >= v15 )
      break;
    bottom = a2->bottom;
    if ( top >= bottom )
    {
      v29 = *(_QWORD *)this;
      v25 = 8 * v13;
      v49 = 0;
      v9 = CxCodeVideoProcThread::PutWorkItem(*(CxCodeVideoProcThread **)(8 * v13 + v29), &v49, 0, 0);
    }
    else
    {
      v17 = *(_QWORD *)this;
      left = a2->left;
      right = a2->right;
      if ( v14 < bottom )
        bottom = v14;
      *(_QWORD *)&v49.left = 8 * v13;
      v20 = *(_QWORD *)(8 * v13 + v17);
      *(_DWORD *)(v20 + 28) = bottom;
      *(_DWORD *)(v20 + 16) = left;
      v21 = CallStackTracing::s_wpInstance;
      *(_DWORD *)(v20 + 24) = right;
      *(_DWORD *)(v20 + 20) = top;
      *(_QWORD *)(v20 + 40) = v8;
      *(_QWORD *)(v20 + 32) = a4;
      if ( !v21 )
      {
        CallStackTracing::InitInstance();
        v21 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext(v21);
        v23 = *((unsigned int *)v22 + 497);
        if ( (unsigned int)v23 < *((_DWORD *)v22 + 498) )
        {
          v24 = 2 * v23;
          *((_QWORD *)v22 + v24) = "CxCodeVideoProcThread::PutWorkItem";
          *((_DWORD *)v22 + 2 * v24 + 2) = 208;
        }
        ++*((_DWORD *)v22 + 497);
      }
      v9 = MFPutWorkItem2(*(_DWORD *)(v20 + 56), 0, (IMFAsyncCallback *)(v20 + 8), 0);
      if ( v9 < 0 )
      {
        v40 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v41;
          if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
          {
            v40 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v40 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v40 + 8) )
        {
          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
          if ( *((_DWORD *)v42 + 499) != v9 )
            CallStackContext::TraceFailure(v42, "CxCodeVideoProcThread::PutWorkItem", 208, v9);
        }
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_cd0276237ea237e1200ead55a1fb02c7_Traceguids, v20, v9);
      }
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v48);
      v25 = *(_QWORD *)&v49.left;
    }
    if ( v9 == -1072873851 )
    {
      SetEvent(*(HANDLE *)(*((_QWORD *)this + 1) + v25));
      *(_DWORD *)(*(_QWORD *)(v25 + *(_QWORD *)this) + 48LL) = -1072873851;
    }
    else if ( v9 < 0 )
    {
      v27 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v27 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v27 + 8) )
      {
        v43 = CallStackTracing::GetThreadRelativeContext(v27);
        if ( *((_DWORD *)v43 + 499) != v9 )
          CallStackContext::TraceFailure(v43, "CxCodeVideoProcThreadPool::ProcessData", 281, v9);
      }
      if ( g_wppLevels )
      {
        v31 = 20;
        goto LABEL_48;
      }
      goto LABEL_31;
    }
    v8 = a3;
    top += v12;
    v14 += v12;
    v13 = (unsigned int)(v13 + 1);
  }
  if ( WaitForMultipleObjectsEx(v15, *((const HANDLE **)this + 1), 1, 0xFFFFFFFF, 0)
    && (v9 = XvpOriginateError<31>(
               "CxCodeVideoProcThreadPool::ProcessData",
               2147549183LL,
               L"Some threads are still running"),
        v9 < 0) )
  {
    v44 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v45;
      if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
      {
        v44 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v44 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v44 + 8) )
    {
      v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
      if ( *((_DWORD *)v46 + 499) != v9 )
        CallStackContext::TraceFailure(v46, "CxCodeVideoProcThreadPool::ProcessData", 292, v9);
    }
    if ( g_wppLevels )
    {
      v31 = 21;
      goto LABEL_48;
    }
  }
  else
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
    {
      v9 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 8 * i) + 48LL);
      if ( v9 < 0 )
      {
        v34 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v34 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v47 = CallStackTracing::GetThreadRelativeContext(v34);
          if ( *((_DWORD *)v47 + 499) != v9 )
            CallStackContext::TraceFailure(v47, "CxCodeVideoProcThreadPool::ProcessData", 298, v9);
        }
        if ( g_wppLevels )
        {
          v31 = 22;
          goto LABEL_48;
        }
        break;
      }
    }
  }
LABEL_31:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v48);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000e200  mov     [rsp+arg_18], r9
0x18000e205  mov     [rsp+arg_10], r8
0x18000e20a  push    rbx
0x18000e20b  push    rsi
0x18000e20c  push    rdi
0x18000e20d  push    r12
0x18000e20f  sub     rsp, 68h
0x18000e213  mov     r12, rdx
0x18000e216  mov     rdi, rcx
0x18000e219  lea     rdx, aCxcodevideopro_89; "CxCodeVideoProcThreadPool::ProcessData"
0x18000e220  mov     r8d, 0E9h; int
0x18000e226  lea     rcx, [rsp+88h+var_58]; this
0x18000e22b  mov     rsi, r9
0x18000e22e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18000e233  mov     r10, [rsp+88h+arg_10]
0x18000e23b  test    r10, r10
0x18000e23e  jz      loc_18000E466
0x18000e244  xor     ebx, ebx
0x18000e246  cmp     dword ptr [rdi+14h], 2
0x18000e24a  jnz     loc_18000E7E4
0x18000e250  mov     r8d, [rdi+10h]
0x18000e254  cmp     r8d, 1
0x18000e258  jz      loc_18000E4A9
0x18000e25e  mov     eax, [r12+0Ch]
0x18000e263  xor     edx, edx
0x18000e265  dec     eax
0x18000e267  mov     [rsp+88h+arg_0], rbp
0x18000e26f  mov     [rsp+88h+var_28], r13
0x18000e274  mov     ecx, r8d
0x18000e277  mov     [rsp+88h+var_30], r14
0x18000e27c  mov     r14d, [r12+4]
0x18000e281  sub     ecx, r14d
0x18000e284  add     eax, ecx
0x18000e286  mov     [rsp+88h+var_38], r15
0x18000e28b  div     r8d
0x18000e28e  lea     r13d, [rax+1]
0x18000e292  mov     eax, 20h ; ' '
0x18000e297  and     r13d, 0FFFFFFFEh
0x18000e29b  cmp     r13d, eax
0x18000e29e  cmovle  r13d, eax
0x18000e2a2  xor     ebp, ebp
0x18000e2a4  lea     r15d, [r14+r13]
0x18000e2a8  nop     dword ptr [rax+rax+00000000h]
0x18000e2b0  mov     ecx, [rdi+10h]; nCount
0x18000e2b3  cmp     ebp, ecx
0x18000e2b5  jnb     loc_18000E3A0
0x18000e2bb  mov     r8d, [r12+0Ch]
0x18000e2c0  cmp     r14d, r8d
0x18000e2c3  jge     loc_18000E437
0x18000e2c9  mov     rax, [rdi]
0x18000e2cc  lea     r9, ds:0[rbp*8]
0x18000e2d4  mov     ecx, [r12]
0x18000e2d8  cmp     r15d, r8d
0x18000e2db  mov     edx, [r12+8]
0x18000e2e0  cmovl   r8d, r15d
0x18000e2e4  mov     qword ptr [rsp+88h+var_50.left], r9
0x18000e2e9  mov     rsi, [r9+rax]
0x18000e2ed  mov     rax, [rsp+88h+arg_18]
0x18000e2f5  mov     [rsi+1Ch], r8d
0x18000e2f9  mov     [rsi+10h], ecx
0x18000e2fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18000e303  mov     [rsi+18h], edx
0x18000e306  mov     [rsi+14h], r14d
0x18000e30a  mov     [rsi+28h], r10
0x18000e30e  mov     [rsi+20h], rax
0x18000e312  test    rcx, rcx
0x18000e315  jz      loc_18000E498
0x18000e31b  cmp     byte ptr [rcx+8], 0
0x18000e31f  jz      short loc_18000E350
0x18000e321  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000e326  mov     ecx, [rax+7C4h]
0x18000e32c  cmp     ecx, [rax+7C8h]
0x18000e332  jnb     short loc_18000E34A
0x18000e334  add     rcx, rcx
0x18000e337  lea     rdx, aCxcodevideopro_115; "CxCodeVideoProcThread::PutWorkItem"
0x18000e33e  mov     [rax+rcx*8], rdx
0x18000e342  mov     dword ptr [rax+rcx*8+8], 0D0h
0x18000e34a  inc     dword ptr [rax+7C4h]
0x18000e350  mov     ecx, [rsi+38h]; dwQueue
0x18000e353  lea     r8, [rsi+8]; pCallback
0x18000e357  xor     r9d, r9d; pState
0x18000e35a  xor     edx, edx; Priority
0x18000e35c  call    cs:__imp_MFPutWorkItem2
0x18000e362  mov     ebx, eax
0x18000e364  test    eax, eax
0x18000e366  js      loc_18000E668
0x18000e36c  lea     rcx, [rsp+88h+var_58]; this
0x18000e371  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000e376  mov     rsi, qword ptr [rsp+88h+var_50.left]
0x18000e37b  cmp     ebx, 0C00D3E85h
0x18000e381  jz      loc_18000E8B1
0x18000e387  test    ebx, ebx
0x18000e389  js      short loc_18000E3E3
0x18000e38b  mov     r10, [rsp+88h+arg_10]
0x18000e393  add     r14d, r13d
0x18000e396  add     r15d, r13d
0x18000e399  inc     ebp
0x18000e39b  jmp     loc_18000E2B0
0x18000e3a0  mov     rdx, [rdi+8]; lpHandles
0x18000e3a4  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000e3aa  mov     r8d, 1; bWaitAll
0x18000e3b0  mov     [rsp+88h+bAlertable], 0; bAlertable
0x18000e3b8  call    cs:__imp_WaitForMultipleObjectsEx
0x18000e3be  test    eax, eax
0x18000e3c0  jnz     loc_18000E8DC
0x18000e3c6  xor     eax, eax
0x18000e3c8  cmp     eax, [rdi+10h]
0x18000e3cb  jnb     short loc_18000E40A
0x18000e3cd  mov     rcx, [rdi]
0x18000e3d0  mov     rdx, [rcx+rax*8]
0x18000e3d4  mov     ebx, [rdx+30h]
0x18000e3d7  test    ebx, ebx
0x18000e3d9  js      loc_18000E50F
0x18000e3df  inc     eax
0x18000e3e1  jmp     short loc_18000E3C8
0x18000e3e3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18000e3ea  test    rcx, rcx
0x18000e3ed  jz      loc_18000E56B
0x18000e3f3  cmp     byte ptr [rcx+8], 0
0x18000e3f7  jnz     loc_18000E6E4
0x18000e3fd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000e404  jnb     loc_18000E8D2
0x18000e40a  mov     r14, [rsp+88h+var_30]
0x18000e40f  mov     r13, [rsp+88h+var_28]
0x18000e414  mov     rbp, [rsp+88h+arg_0]
0x18000e41c  mov     r15, [rsp+88h+var_38]
0x18000e421  lea     rcx, [rsp+88h+var_58]; this
0x18000e426  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18000e42b  mov     eax, ebx
0x18000e42d  add     rsp, 68h
0x18000e431  pop     r12
0x18000e433  pop     rdi
0x18000e434  pop     rsi
0x18000e435  pop     rbx
0x18000e436  retn
0x18000e437  mov     rcx, [rdi]
0x18000e43a  lea     rsi, ds:0[rbp*8]
0x18000e442  xorps   xmm0, xmm0
0x18000e445  lea     rdx, [rsp+88h+var_50]; struct tagRECT *
0x18000e44a  xor     r9d, r9d; struct ParameterBase *
0x18000e44d  xor     r8d, r8d; int (*)(const struct tagRECT *, const struct ParameterBase *)
0x18000e450  movdqu  xmmword ptr [rsp+88h+var_50.left], xmm0
0x18000e456  mov     rcx, [rsi+rcx]; this
0x18000e45a  call    ?PutWorkItem@CxCodeVideoProcThread@@QEAAJAEBUtagRECT@@P6AJ0PEBUParameterBase@@@Z1@Z; CxCodeVideoProcThread::PutWorkItem(tagRECT const &,long (*)(tagRECT const &,ParameterBase const *),ParameterBase const *)
0x18000e45f  mov     ebx, eax
0x18000e461  jmp     loc_18000E37B
0x18000e466  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18000e46d  mov     ebx, 80004003h
0x18000e472  test    rcx, rcx
0x18000e475  jz      loc_18000E55A
0x18000e47b  cmp     byte ptr [rcx+8], 0
0x18000e47f  jnz     loc_18000E58A
0x18000e485  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000e48c  jb      short loc_18000E421
0x18000e48e  mov     edx, 11h
0x18000e493  jmp     loc_18000E7C1
0x18000e498  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18000e49d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e4a4  jmp     loc_18000E31B
0x18000e4a9  mov     rdx, rsi
0x18000e4ac  mov     rcx, r12
0x18000e4af  mov     rax, r10
0x18000e4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4b7  mov     ebx, eax
0x18000e4b9  test    eax, eax
0x18000e4bb  jns     loc_18000E421
0x18000e4c1  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e4c8  test    rax, rax
0x18000e4cb  jnz     loc_18000E848
0x18000e4d1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000e4d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e4de  mov     rcx, rax
0x18000e4e1  test    rax, rax
0x18000e4e4  jz      loc_18000E83A
0x18000e4ea  mov     rax, [rax]
0x18000e4ed  mov     edx, 7F0h
0x18000e4f2  mov     rax, [rax+8]
0x18000e4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4fb  test    eax, eax
0x18000e4fd  jz      loc_18000E83A
0x18000e503  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e50a  jmp     loc_18000E848
0x18000e50f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18000e516  test    rcx, rcx
0x18000e519  jz      short loc_18000E57C
0x18000e51b  cmp     byte ptr [rcx+8], 0
0x18000e51f  jnz     loc_18000E78E
0x18000e525  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000e52c  jb      loc_18000E40A
0x18000e532  mov     edx, 16h
0x18000e537  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e53e  lea     r8, WPP_31017d59e5fa36e4c5717ad5ebbdb595_Traceguids
0x18000e545  mov     r9, rdi
0x18000e548  mov     [rsp+88h+bAlertable], ebx
0x18000e54c  mov     rcx, [rcx+10h]
0x18000e550  call    WPP_SF_qD
0x18000e555  jmp     loc_18000E40A
0x18000e55a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18000e55f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e566  jmp     loc_18000E47B
0x18000e56b  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18000e570  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e577  jmp     loc_18000E3F3
0x18000e57c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18000e581  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e588  jmp     short loc_18000E51B
0x18000e58a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000e58f  cmp     [rax+7CCh], ebx
0x18000e595  jz      loc_18000E485
0x18000e59b  mov     r9d, ebx; int
0x18000e59e  lea     rdx, aCxcodevideopro_89; "CxCodeVideoProcThreadPool::ProcessData"
0x18000e5a5  mov     r8d, 0E9h; int
0x18000e5ab  mov     rcx, rax; this
0x18000e5ae  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000e5b3  jmp     loc_18000E485
0x18000e5b8  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e5bf  test    rax, rax
0x18000e5c2  jnz     loc_18000E81C
0x18000e5c8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000e5ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e5d5  mov     rcx, rax
0x18000e5d8  test    rax, rax
0x18000e5db  jz      loc_18000E80E
0x18000e5e1  mov     rax, [rax]
0x18000e5e4  mov     edx, 7F0h
0x18000e5e9  mov     rax, [rax+8]
0x18000e5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5f2  test    eax, eax
0x18000e5f4  jz      loc_18000E80E
0x18000e5fa  mov     rax, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e601  jmp     loc_18000E81C
0x18000e606  mov     rcx, rax; this
0x18000e609  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000e60e  cmp     [rax+7CCh], ebx
0x18000e614  jz      loc_18000E826
0x18000e61a  mov     r9d, ebx; int
0x18000e61d  lea     rdx, aCxcodevideopro_89; "CxCodeVideoProcThreadPool::ProcessData"
0x18000e624  mov     r8d, 0EDh; int
0x18000e62a  mov     rcx, rax; this
0x18000e62d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000e632  jmp     loc_18000E826
0x18000e637  mov     rcx, rax; this
0x18000e63a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000e63f  cmp     [rax+7CCh], ebx
0x18000e645  jz      loc_18000E852
0x18000e64b  mov     r9d, ebx; int
0x18000e64e  lea     rdx, aCxcodevideopro_89; "CxCodeVideoProcThreadPool::ProcessData"
0x18000e655  mov     r8d, 0F3h; int
0x18000e65b  mov     rcx, rax; this
0x18000e65e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000e663  jmp     loc_18000E852
0x18000e668  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e66f  test    rcx, rcx
0x18000e672  jnz     loc_18000E872
0x18000e678  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000e67e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e685  mov     rcx, rax
0x18000e688  test    rax, rax
0x18000e68b  jz      loc_18000E864
0x18000e691  mov     rax, [rax]
0x18000e694  mov     edx, 7F0h
0x18000e699  mov     rax, [rax+8]
0x18000e69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6a2  test    eax, eax
0x18000e6a4  jz      loc_18000E864
0x18000e6aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e6b1  jmp     loc_18000E872
0x18000e6b6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000e6bb  cmp     [rax+7CCh], ebx
0x18000e6c1  jz      loc_18000E87C
0x18000e6c7  mov     r9d, ebx; int
0x18000e6ca  lea     rdx, aCxcodevideopro_115; "CxCodeVideoProcThread::PutWorkItem"
0x18000e6d1  mov     r8d, 0D0h; int
0x18000e6d7  mov     rcx, rax; this
0x18000e6da  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000e6df  jmp     loc_18000E87C
0x18000e6e4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000e6e9  cmp     [rax+7CCh], ebx
0x18000e6ef  jz      loc_18000E3FD
0x18000e6f5  mov     r9d, ebx; int
0x18000e6f8  lea     rdx, aCxcodevideopro_89; "CxCodeVideoProcThreadPool::ProcessData"
0x18000e6ff  mov     r8d, 119h; int
0x18000e705  mov     rcx, rax; this
0x18000e708  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000e70d  jmp     loc_18000E3FD
0x18000e712  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e719  test    rcx, rcx
0x18000e71c  jnz     loc_18000E911
0x18000e722  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000e728  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000e72f  mov     rcx, rax
0x18000e732  test    rax, rax
0x18000e735  jz      loc_18000E903
0x18000e73b  mov     rax, [rax]
0x18000e73e  mov     edx, 7F0h
0x18000e743  mov     rax, [rax+8]
0x18000e747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e74c  test    eax, eax
0x18000e74e  jz      loc_18000E903
0x18000e754  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
