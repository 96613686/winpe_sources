# EidAsyncHelper::WaitForEnterpriseId(std::unique_ptr<ushort,std::default_delete<ushort>> &)

- ea: `0x180054ea0`
- end: `0x1800554a7`
- name: `?WaitForEnterpriseId@EidAsyncHelper@@QEAA_NAEAV?$unique_ptr@GU?$default_delete@G@std@@@std@@@Z`
- size: `1543`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180006b40`
- `0x1800548e4`
- `0x180054dd0`

## callees

- `0x18000e370`
- `0x18001d830`
- `0x180033480`
- `0x1800544a0`
- `0x180054ea0`
- `0x18005579c`
- `0x180091fe0`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a1114`
- `0x1800a3444`
- `0x1800ab7fc`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180054ee7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180054ee7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005545d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005545d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005503c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055032`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005503c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055046`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800550f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005524c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800550f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005524c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800551bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055451`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800551bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055451`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800551cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800551cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054fb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055004`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005547c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054fb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055004`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005547c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180055028`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180055028`
- `FirewallAPI!NetworkIsolationGetEnterpriseIdClose` at `0x18005520c`
- `FirewallAPI!NetworkIsolationGetEnterpriseIdClose` at `0x18005520c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall EidAsyncHelper::WaitForEnterpriseId(LPCRITICAL_SECTION lpCriticalSection, void **a2)
{
  LPCRITICAL_SECTION v3; // rdi
  void *v4; // rcx
  volatile signed __int32 *v5; // rax
  volatile signed __int32 *v6; // rbx
  volatile signed __int32 **v7; // rsi
  HANDLE v8; // rcx
  unsigned int LastError; // ecx
  struct _RTL_CRITICAL_SECTION *v10; // rsi
  EVENT_LOG *v11; // rcx
  __int64 v12; // rdx
  HANDLE OwningThread; // r13
  DWORD v15; // eax
  __int64 LockSemaphore_low; // r9
  EVENT_LOG *v17; // rcx
  int LockSemaphore; // edx
  ULONG_PTR *p_SpinCount; // r9
  const unsigned __int16 *v20; // rcx
  const ComError *v21; // rbx
  char v22[8]; // [rsp+20h] [rbp-178h] BYREF
  LPCRITICAL_SECTION v23; // [rsp+28h] [rbp-170h]
  const ComError *v24; // [rsp+30h] [rbp-168h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-158h] BYREF
  __int128 v26; // [rsp+48h] [rbp-150h]
  int v27; // [rsp+58h] [rbp-140h]
  int v28; // [rsp+5Ch] [rbp-13Ch]
  int v29; // [rsp+60h] [rbp-138h]
  void **v30; // [rsp+A0h] [rbp-F8h] BYREF
  __int128 v31; // [rsp+A8h] [rbp-F0h]
  unsigned int v32; // [rsp+B8h] [rbp-E0h]
  int v33; // [rsp+BCh] [rbp-DCh]
  int v34; // [rsp+C0h] [rbp-D8h]
  void **v35; // [rsp+100h] [rbp-98h] BYREF
  __int128 v36; // [rsp+108h] [rbp-90h]
  int v37; // [rsp+118h] [rbp-80h]
  int v38; // [rsp+11Ch] [rbp-7Ch]
  int v39; // [rsp+120h] [rbp-78h]
  HANDLE hOperation; // [rsp+1A8h] [rbp+10h] BYREF
  volatile signed __int32 *v42; // [rsp+1B0h] [rbp+18h] BYREF
  LPCRITICAL_SECTION v43; // [rsp+1B8h] [rbp+20h]

  v3 = lpCriticalSection;
  v4 = *a2;
  *a2 = 0;
  if ( v4 )
    operator delete(v4, 2u);
  v5 = (volatile signed __int32 *)HeapAlloc(hBitsHeap, 8u, 0x10u);
  v6 = v5;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 16);
    v26 = 0;
    pExceptionObject = &ComError::`vftable';
    v27 = -2147024882;
    v28 = 0;
    v29 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v42 = v5;
  *((_DWORD *)v5 + 2) = 1;
  *(_QWORD *)v5 = 0;
  v7 = (volatile signed __int32 **)CopyThreadToken(&hOperation);
  if ( *(_QWORD *)v6 != *(_QWORD *)*v7 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( (unsigned __int64)(*(_QWORD *)v6 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v6);
        *(_QWORD *)v6 = 0;
      }
      operator delete((void *)v6, 0x10u);
    }
    v6 = *v7;
    v42 = v6;
    _InterlockedIncrement(v6 + 2);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)hOperation + 2, 0xFFFFFFFF) == 1 )
  {
    v8 = hOperation;
    if ( (unsigned __int64)(*(_QWORD *)hOperation - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)hOperation);
      *(_QWORD *)hOperation = 0;
      v8 = hOperation;
    }
    operator delete(v8, 0x10u);
  }
  if ( !RevertToSelf() )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v31 = 0;
    v30 = &ComError::`vftable';
    v32 = LastError;
    v33 = 159;
    v34 = 1;
    throw (ComError *)&v30;
  }
  v23 = v3;
  v10 = v3 + 1;
  v43 = v3 + 1;
  if ( LOBYTE(v3[1].DebugInfo)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v3);
  }
  EnterCriticalSection(v3);
  v22[0] = 1;
  if ( !BYTE1(v3[1].LockSemaphore) )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_36;
    v12 = 15;
LABEL_35:
    WPP_SF_(*((_QWORD *)v11 + 2), v12, WPP_7bc6c97b7e50306a80f3d21b979f711d_Traceguids);
LABEL_36:
    HoldCritSec::~HoldCritSec((HoldCritSec *)v22);
    CSaveThreadToken::~CSaveThreadToken((CSaveThreadToken *)&v42);
    return 0;
  }
  if ( BYTE2(v3[1].LockSemaphore) )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_36;
    v12 = 16;
    goto LABEL_35;
  }
  BYTE2(v3[1].LockSemaphore) = 1;
  OwningThread = v3[1].OwningThread;
  hOperation = *(HANDLE *)&v3[1].LockCount;
  if ( LOBYTE(v10->DebugInfo)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v3);
  }
  LeaveCriticalSection(v3);
  v15 = WaitForSingleObject(OwningThread, 0xFFFFFFFF);
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_7bc6c97b7e50306a80f3d21b979f711d_Traceguids, v15);
  NetworkIsolationGetEnterpriseIdClose(hOperation, 0);
  v23 = v3;
  if ( LOBYTE(v10->DebugInfo)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v3);
  }
  EnterCriticalSection(v3);
  v22[0] = 1;
  *(_WORD *)((char *)&v3[1].LockSemaphore + 1) = 0;
  if ( LOBYTE(v3[1].LockSemaphore) )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_7bc6c97b7e50306a80f3d21b979f711d_Traceguids);
    LODWORD(v3[2].LockSemaphore) = -2147023673;
LABEL_73:
    v17 = WPP_GLOBAL_Control;
    goto LABEL_74;
  }
  LockSemaphore_low = LODWORD(v3[2].LockSemaphore);
  if ( (_DWORD)LockSemaphore_low )
  {
    if ( (_DWORD)LockSemaphore_low == -2147013895 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_7bc6c97b7e50306a80f3d21b979f711d_Traceguids);
      HoldCritSec::~HoldCritSec((HoldCritSec *)v22);
      CSaveThreadToken::~CSaveThreadToken((CSaveThreadToken *)&v42);
      return 1;
    }
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_7bc6c97b7e50306a80f3d21b979f711d_Traceguids,
        LockSemaphore_low);
      v17 = WPP_GLOBAL_Control;
    }
    LockSemaphore = (int)v3[2].LockSemaphore;
    if ( LockSemaphore < 0 )
    {
      v36 = 0;
      v35 = &ComError::`vftable';
      v37 = LockSemaphore;
      v38 = 211;
      v39 = 1;
      throw (ComError *)&v35;
    }
  }
  else
  {
    v17 = WPP_GLOBAL_Control;
  }
  if ( v17 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 )
  {
    p_SpinCount = &v3[1].SpinCount;
    if ( v3[2].OwningThread > HANDLE_FLAG_PROTECT_FROM_CLOSE|HANDLE_FLAG_INHERIT|0x4 )
      p_SpinCount = (ULONG_PTR *)*p_SpinCount;
    WPP_SF_S(*((_QWORD *)v17 + 2), 21, WPP_7bc6c97b7e50306a80f3d21b979f711d_Traceguids, p_SpinCount);
    v17 = WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)&v3[2].LockCount )
  {
    v20 = (const unsigned __int16 *)&v3[1].SpinCount;
    if ( v3[2].OwningThread > HANDLE_FLAG_PROTECT_FROM_CLOSE|HANDLE_FLAG_INHERIT|0x4 )
      v20 = *(const unsigned __int16 **)v20;
    try
    {
      hOperation = CopyString(v20, 0xFFFFFFFFFFFFFFFFuLL);
      std::unique_ptr<unsigned short>::operator=<std::default_delete<unsigned short>,0>(a2, &hOperation);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&hOperation);
    }
    catch ( const ComError *v24 )
    {
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        v21 = v24;
      }
      else
      {
        v21 = v24;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_7bc6c97b7e50306a80f3d21b979f711d_Traceguids,
          *((unsigned int *)v24 + 6));
      }
      LODWORD(lpCriticalSection[2].LockSemaphore) = *((_DWORD *)v21 + 6);
      v3 = lpCriticalSection;
      v6 = v42;
      v10 = v43;
      goto LABEL_73;
    }
    goto LABEL_73;
  }
LABEL_74:
  if ( LOBYTE(v10->DebugInfo) && v17 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x100) != 0 )
    WPP_SF_q(*((_QWORD *)v17 + 2), 16, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v3);
  LeaveCriticalSection(v3);
  SetThreadToken(0, *(HANDLE *)v6);
  if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
  {
    if ( (unsigned __int64)(*(_QWORD *)v6 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v6);
      *(_QWORD *)v6 = 0;
    }
    operator delete((void *)v6, 0x10u);
  }
  return 1;
}

```

## disassembly

```asm
0x180054ea0  mov     [rsp+arg_0], rcx
0x180054ea5  push    rbx
0x180054ea6  push    rsi
0x180054ea7  push    rdi
0x180054ea8  push    r12
0x180054eaa  push    r13
0x180054eac  push    r14
0x180054eae  push    r15
0x180054eb0  sub     rsp, 160h
0x180054eb7  mov     r15, rdx
0x180054eba  mov     rdi, rcx
0x180054ebd  mov     rcx, [rdx]; void *
0x180054ec0  xor     r12d, r12d
0x180054ec3  mov     [rdx], r12
0x180054ec6  test    rcx, rcx
0x180054ec9  jz      short loc_180054ED5
0x180054ecb  mov     edx, 2; unsigned __int64
0x180054ed0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180054ed5  mov     edx, 8; dwFlags
0x180054eda  mov     r8d, 10h; dwBytes
0x180054ee0  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x180054ee7  call    cs:__imp_HeapAlloc
0x180054eed  mov     rbx, rax
0x180054ef0  test    rax, rax
0x180054ef3  jnz     short loc_180054F64
0x180054ef5  lea     rax, WPP_GLOBAL_Control
0x180054efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180054f03  cmp     rcx, rax
0x180054f06  jz      short loc_180054F29
0x180054f08  test    byte ptr [rcx+1Ch], 4
0x180054f0c  jz      short loc_180054F29
0x180054f0e  mov     edx, 0Ah
0x180054f13  mov     r9d, 10h
0x180054f19  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x180054f20  mov     rcx, [rcx+10h]
0x180054f24  call    WPP_SF_d
0x180054f29  xorps   xmm0, xmm0
0x180054f2c  movups  [rsp+198h+var_150], xmm0
0x180054f31  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180054f38  mov     [rsp+198h+pExceptionObject], rax
0x180054f3d  mov     [rsp+198h+var_140], 8007000Eh
0x180054f45  mov     [rsp+198h+var_13C], r12d
0x180054f4a  mov     [rsp+198h+var_138], 1
0x180054f52  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180054f59  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x180054f5e  call    _CxxThrowException_0
0x180054f64  mov     [rsp+198h+arg_10], rbx
0x180054f6c  mov     dword ptr [rax+8], 1
0x180054f73  mov     [rax], r12
0x180054f76  lea     rcx, [rsp+198h+hOperation]
0x180054f7e  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x180054f83  mov     rsi, rax
0x180054f86  mov     rcx, [rax]
0x180054f89  mov     rdx, [rcx]
0x180054f8c  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180054f93  cmp     [rbx], rdx
0x180054f96  jz      short loc_180054FD7
0x180054f98  mov     ecx, r14d
0x180054f9b  lock xadd [rbx+8], ecx
0x180054fa0  cmp     ecx, 1
0x180054fa3  jnz     short loc_180054FC8
0x180054fa5  mov     rcx, [rbx]; hObject
0x180054fa8  lea     rdx, [rcx-1]
0x180054fac  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180054fb0  ja      short loc_180054FBB
0x180054fb2  call    cs:__imp_CloseHandle
0x180054fb8  mov     [rbx], r12
0x180054fbb  mov     edx, 10h; unsigned __int64
0x180054fc0  mov     rcx, rbx; void *
0x180054fc3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180054fc8  mov     rbx, [rsi]
0x180054fcb  mov     [rsp+198h+arg_10], rbx
0x180054fd3  lock inc dword ptr [rbx+8]
0x180054fd7  mov     rcx, [rsp+198h+hOperation]
0x180054fdf  mov     eax, r14d
0x180054fe2  lock xadd [rcx+8], eax
0x180054fe7  cmp     eax, 1
0x180054fea  jnz     short loc_180055028
0x180054fec  mov     rcx, [rsp+198h+hOperation]
0x180054ff4  mov     rdx, [rcx]
0x180054ff7  lea     rax, [rdx-1]
0x180054ffb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180054fff  ja      short loc_18005501D
0x180055001  mov     rcx, rdx; hObject
0x180055004  call    cs:__imp_CloseHandle
0x18005500a  mov     rax, [rsp+198h+hOperation]
0x180055012  mov     [rax], r12
0x180055015  mov     rcx, [rsp+198h+hOperation]; void *
0x18005501d  mov     edx, 10h; unsigned __int64
0x180055022  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180055027  nop
0x180055028  call    cs:__imp_RevertToSelf
0x18005502e  test    eax, eax
0x180055030  jnz     short loc_1800550A1
0x180055032  call    cs:__imp_GetLastError
0x180055038  test    eax, eax
0x18005503a  jg      short loc_180055046
0x18005503c  call    cs:__imp_GetLastError
0x180055042  mov     ecx, eax
0x180055044  jmp     short loc_180055055
0x180055046  call    cs:__imp_GetLastError
0x18005504c  movzx   ecx, ax
0x18005504f  or      ecx, 80070000h
0x180055055  xorps   xmm0, xmm0
0x180055058  movups  [rsp+198h+var_F0], xmm0
0x180055060  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180055067  mov     [rsp+198h+var_F8], rax
0x18005506f  mov     [rsp+198h+var_E0], ecx
0x180055076  mov     [rsp+198h+var_DC], 9Fh
0x180055081  mov     [rsp+198h+var_D8], 1
0x18005508c  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180055093  lea     rcx, [rsp+198h+var_F8]; pExceptionObject
0x18005509b  call    _CxxThrowException_0
0x1800550a1  mov     [rsp+198h+var_170], rdi
0x1800550a6  lea     rsi, [rdi+28h]
0x1800550aa  mov     [rsp+198h+arg_18], rsi
0x1800550b2  cmp     byte ptr [rsi], 0
0x1800550b5  jz      short loc_1800550ED
0x1800550b7  lea     r13, WPP_GLOBAL_Control
0x1800550be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800550c5  cmp     rcx, r13
0x1800550c8  jz      short loc_1800550F4
0x1800550ca  test    dword ptr [rcx+1Ch], 100h
0x1800550d1  jz      short loc_1800550F4
0x1800550d3  mov     edx, 0Fh
0x1800550d8  mov     r9, rdi
0x1800550db  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x1800550e2  mov     rcx, [rcx+10h]
0x1800550e6  call    WPP_SF_q
0x1800550eb  jmp     short loc_1800550F4
0x1800550ed  lea     r13, WPP_GLOBAL_Control
0x1800550f4  mov     rcx, rdi; lpCriticalSection
0x1800550f7  call    cs:__imp_EnterCriticalSection
0x1800550fd  mov     [rsp+198h+var_178], 1
0x180055102  cmp     byte ptr [rdi+41h], 0
0x180055106  jnz     short loc_180055121
0x180055108  mov     rcx, cs:WPP_GLOBAL_Control
0x18005510f  cmp     rcx, r13
0x180055112  jz      short loc_18005514E
0x180055114  test    byte ptr [rcx+1Ch], 2
0x180055118  jz      short loc_18005514E
0x18005511a  mov     edx, 0Fh
0x18005511f  jmp     short loc_18005513E
0x180055121  cmp     byte ptr [rdi+42h], 0
0x180055125  jz      short loc_18005516D
0x180055127  mov     rcx, cs:WPP_GLOBAL_Control
0x18005512e  cmp     rcx, r13
0x180055131  jz      short loc_18005514E
0x180055133  test    byte ptr [rcx+1Ch], 2
0x180055137  jz      short loc_18005514E
0x180055139  mov     edx, 10h
0x18005513e  lea     r8, WPP_7bc6c97b7e50306a80f3d21b979f711d_Traceguids
0x180055145  mov     rcx, [rcx+10h]
0x180055149  call    WPP_SF_
0x18005514e  lea     rcx, [rsp+198h+var_178]; this
0x180055153  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x180055158  nop
0x180055159  lea     rcx, [rsp+198h+arg_10]; this
0x180055161  call    ??1CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::~CSaveThreadToken(void)
0x180055166  xor     al, al
0x180055168  jmp     loc_180055494
0x18005516d  mov     byte ptr [rdi+42h], 1
0x180055171  mov     r13, [rdi+38h]
0x180055175  mov     rax, [rdi+30h]
0x180055179  mov     [rsp+198h+hOperation], rax
0x180055181  cmp     byte ptr [rsi], 0
0x180055184  jz      short loc_1800551BA
0x180055186  mov     rcx, cs:WPP_GLOBAL_Control
0x18005518d  lea     rax, WPP_GLOBAL_Control
0x180055194  cmp     rcx, rax
0x180055197  jz      short loc_1800551BA
0x180055199  test    dword ptr [rcx+1Ch], 100h
0x1800551a0  jz      short loc_1800551BA
0x1800551a2  mov     edx, 10h
0x1800551a7  mov     r9, rdi
0x1800551aa  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x1800551b1  mov     rcx, [rcx+10h]
0x1800551b5  call    WPP_SF_q
0x1800551ba  mov     rcx, rdi; lpCriticalSection
0x1800551bd  call    cs:__imp_LeaveCriticalSection
0x1800551c3  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800551c8  mov     rcx, r13; hHandle
0x1800551cb  call    cs:__imp_WaitForSingleObject
0x1800551d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800551d8  lea     r13, WPP_GLOBAL_Control
0x1800551df  cmp     rcx, r13
0x1800551e2  jz      short loc_180055202
0x1800551e4  test    byte ptr [rcx+1Ch], 1
0x1800551e8  jz      short loc_180055202
0x1800551ea  mov     edx, 11h
0x1800551ef  mov     r9d, eax
0x1800551f2  lea     r8, WPP_7bc6c97b7e50306a80f3d21b979f711d_Traceguids
0x1800551f9  mov     rcx, [rcx+10h]
0x1800551fd  call    WPP_SF_d
0x180055202  xor     edx, edx; bWaitForOperation
0x180055204  mov     rcx, [rsp+198h+hOperation]; hOperation
0x18005520c  call    cs:__imp_NetworkIsolationGetEnterpriseIdClose
0x180055212  mov     [rsp+198h+var_170], rdi
0x180055217  cmp     byte ptr [rsi], 0
0x18005521a  jz      short loc_180055249
0x18005521c  mov     rcx, cs:WPP_GLOBAL_Control
0x180055223  cmp     rcx, r13
0x180055226  jz      short loc_180055249
0x180055228  test    dword ptr [rcx+1Ch], 100h
0x18005522f  jz      short loc_180055249
0x180055231  mov     edx, 0Fh
0x180055236  mov     r9, rdi
0x180055239  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x180055240  mov     rcx, [rcx+10h]
0x180055244  call    WPP_SF_q
0x180055249  mov     rcx, rdi; lpCriticalSection
0x18005524c  call    cs:__imp_EnterCriticalSection
0x180055252  mov     [rsp+198h+var_178], 1
0x180055257  mov     word ptr [rdi+41h], 0
0x18005525d  cmp     byte ptr [rdi+40h], 0
0x180055261  jz      short loc_180055296
0x180055263  mov     rcx, cs:WPP_GLOBAL_Control
0x18005526a  cmp     rcx, r13
0x18005526d  jz      short loc_18005528A
0x18005526f  test    byte ptr [rcx+1Ch], 2
0x180055273  jz      short loc_18005528A
0x180055275  mov     edx, 12h
0x18005527a  lea     r8, WPP_7bc6c97b7e50306a80f3d21b979f711d_Traceguids
0x180055281  mov     rcx, [rcx+10h]
0x180055285  call    WPP_SF_
0x18005528a  mov     dword ptr [rdi+68h], 800704C7h
0x180055291  jmp     loc_18005541C
0x180055296  mov     r9d, [rdi+68h]
0x18005529a  test    r9d, r9d
0x18005529d  jz      loc_180055372
0x1800552a3  cmp     r9d, 80072AF9h
0x1800552aa  jnz     short loc_1800552F1
0x1800552ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800552b3  cmp     rcx, r13
0x1800552b6  jz      short loc_1800552D4
0x1800552b8  test    byte ptr [rcx+1Ch], 2
0x1800552bc  jz      short loc_1800552D4
0x1800552be  mov     edx, 13h
0x1800552c3  lea     r8, WPP_7bc6c97b7e50306a80f3d21b979f711d_Traceguids
0x1800552ca  mov     rcx, [rcx+10h]
0x1800552ce  call    WPP_SF_
0x1800552d3  nop
0x1800552d4  lea     rcx, [rsp+198h+var_178]; this
0x1800552d9  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x1800552de  nop
0x1800552df  lea     rcx, [rsp+198h+arg_10]; this
0x1800552e7  call    ??1CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::~CSaveThreadToken(void)
0x1800552ec  jmp     loc_180055492
0x1800552f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800552f8  cmp     rcx, r13
0x1800552fb  jz      short loc_18005531F
0x1800552fd  test    byte ptr [rcx+1Ch], 4
0x180055301  jz      short loc_18005531F
0x180055303  mov     edx, 14h
0x180055308  lea     r8, WPP_7bc6c97b7e50306a80f3d21b979f711d_Traceguids
0x18005530f  mov     rcx, [rcx+10h]
0x180055313  call    WPP_SF_d
0x180055318  mov     rcx, cs:WPP_GLOBAL_Control
0x18005531f  mov     edx, [rdi+68h]
0x180055322  test    edx, edx
0x180055324  jns     short loc_180055379
0x180055326  xorps   xmm0, xmm0
0x180055329  movups  [rsp+198h+var_90], xmm0
0x180055331  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180055338  mov     [rsp+198h+var_98], rax
0x180055340  mov     [rsp+198h+var_80], edx
0x180055347  mov     [rsp+198h+var_7C], 0D3h
0x180055352  mov     [rsp+198h+var_78], 1
0x18005535d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180055364  lea     rcx, [rsp+198h+var_98]; pExceptionObject
0x18005536c  call    _CxxThrowException_0
0x180055372  mov     rcx, cs:WPP_GLOBAL_Control
0x180055379  cmp     rcx, r13
0x18005537c  jz      short loc_1800553AE
0x18005537e  test    byte ptr [rcx+1Ch], 1
0x180055382  jz      short loc_1800553AE
0x180055384  lea     r9, [rdi+48h]
0x180055388  cmp     qword ptr [r9+18h], 7
0x18005538d  jbe     short loc_180055392
0x18005538f  mov     r9, [r9]
0x180055392  mov     edx, 15h
0x180055397  lea     r8, WPP_7bc6c97b7e50306a80f3d21b979f711d_Traceguids
0x18005539e  mov     rcx, [rcx+10h]
0x1800553a2  call    WPP_SF_S
0x1800553a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800553ae  cmp     qword ptr [rdi+58h], 0
0x1800553b3  jz      short loc_180055423
0x1800553b5  lea     rcx, [rdi+48h]
0x1800553b9  cmp     qword ptr [rcx+18h], 7
0x1800553be  jbe     short loc_1800553C3
0x1800553c0  mov     rcx, [rcx]; unsigned __int16 *
0x1800553c3  mov     rdx, r14; unsigned __int64
0x1800553c6  call    ?CopyString@@YAPEAGPEBG_K@Z; CopyString(ushort const *,unsigned __int64)
0x1800553cb  mov     [rsp+198h+hOperation], rax
0x1800553d3  lea     rdx, [rsp+198h+hOperation]
0x1800553db  mov     rcx, r15
0x1800553de  call    ??$?4U?$default_delete@G@std@@$0A@@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<ushort>::operator=<std::default_delete<ushort>,0>(std::unique_ptr<ushort> &&)
0x1800553e3  lea     rcx, [rsp+198h+hOperation]; void *
0x1800553eb  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800553f0  nop
  ... truncated ...
```
