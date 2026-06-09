# OutOfProcessExceptionEventGetWatsonBucket

- ea: `0x18000825c`
- end: `0x18000856f`
- name: `OutOfProcessExceptionEventGetWatsonBucket`
- size: `787`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180008570`
- `0x1800086e0`

## callees

- `0x18000307c`
- `0x1800032fc`
- `0x180006560`
- `0x18000825c`
- `0x180032580`
- `0x18003ef68`
- `0x18007262c`
- `0x180086bb4`
- `0x1800f0d40`
- `0x180106100`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000842c`
- `KERNEL32!EnterCriticalSection` at `0x1800084b0`
- `KERNEL32!EnterCriticalSection` at `0x18000842c`
- `KERNEL32!EnterCriticalSection` at `0x1800084b0`
- `KERNEL32!LeaveCriticalSection` at `0x180008486`
- `KERNEL32!LeaveCriticalSection` at `0x1800084f3`
- `KERNEL32!LeaveCriticalSection` at `0x180008486`
- `KERNEL32!LeaveCriticalSection` at `0x1800084f3`
- `KERNEL32!GetModuleHandleW` at `0x180008291`
- `KERNEL32!GetModuleHandleW` at `0x180008291`
- `KERNEL32!GetProcAddress` at `0x1800082ad`
- `KERNEL32!GetProcAddress` at `0x1800082c0`
- `KERNEL32!GetProcAddress` at `0x1800082ad`
- `KERNEL32!GetProcAddress` at `0x1800082c0`

## string_xrefs

- `0x18000828a`: `kernel32.dll`
- `0x1800082a3`: `GetProcessIdOfThread`
- `0x1800082b6`: `GetThreadId`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
__int64 __fastcall OutOfProcessExceptionEventGetWatsonBucket(__int64 a1, __int64 a2, struct _GenericModeBlock *a3)
{
  __int64 v5; // r12
  __int64 v6; // rsi
  HMODULE ModuleHandleW; // rax
  HMODULE v8; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v10; // rax
  __int64 (__fastcall *v11)(__int64); // rbx
  int v12; // r13d
  int v13; // esi
  const struct NoThrow *v14; // rdx
  struct ICLRDataTarget *v15; // rax
  const struct NoThrow *v16; // rdx
  struct ICLRDataTarget *v17; // rdi
  struct ICorDebugDataTarget *v18; // rax
  struct ICorDebugDataTarget *v19; // rbx
  const struct NoThrow *v20; // rdx
  ClrDataAccess *v21; // rax
  ClrDataAccess *v22; // rax
  ClrDataAccess *v23; // r14
  int ClrWatsonBucketsWorker; // ebx
  __int64 v25; // rbx
  ClrDataAccess *v26; // r15
  int v27; // r14d
  unsigned __int64 v28; // rcx
  ClrDataAccess *v29; // r15
  struct Thread *Thread; // rax
  ClrDataAccess *v32; // [rsp+28h] [rbp-28h]
  unsigned int v33; // [rsp+98h] [rbp+48h]

  v5 = *(_QWORD *)(a2 + 8);
  v6 = *(_QWORD *)(a2 + 16);
  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  v8 = ModuleHandleW;
  if ( !ModuleHandleW )
    return 2147500037LL;
  ProcAddress = GetProcAddress(ModuleHandleW, "GetProcessIdOfThread");
  v10 = GetProcAddress(v8, "GetThreadId");
  v11 = (__int64 (__fastcall *)(__int64))v10;
  if ( !ProcAddress || !v10 )
    return 2147500037LL;
  v12 = ((__int64 (__fastcall *)(__int64))ProcAddress)(v6);
  v33 = v11(v6);
  v13 = 0;
  v15 = (struct ICLRDataTarget *)operator new(0x20u, v14);
  v17 = v15;
  if ( v15 )
  {
    *(_QWORD *)v15 = &LiveProcDataTarget::`vftable';
    *((_QWORD *)v15 + 1) = v5;
    *((_DWORD *)v15 + 4) = v12;
    *((_QWORD *)v15 + 3) = a1;
    v13 = 1;
    v32 = 0;
    v18 = (struct ICorDebugDataTarget *)operator new(0x18u, v16);
    v19 = v18;
    if ( v18 )
    {
      *(_QWORD *)v18 = &DataTargetAdapter::`vftable';
      *((_DWORD *)v18 + 2) = 0;
      *((_QWORD *)v18 + 2) = v17;
      (*(void (__fastcall **)(struct ICLRDataTarget *))(*(_QWORD *)v17 + 8LL))(v17);
      v21 = (ClrDataAccess *)operator new(0x160u, v20);
      if ( v21 )
      {
        v22 = ClrDataAccess::ClrDataAccess(v21, v19, v17);
        v23 = v22;
        if ( v22 )
        {
          ClrWatsonBucketsWorker = ClrDataAccess::Initialize(v22);
          if ( ClrWatsonBucketsWorker >= 0 )
          {
            v32 = v23;
            ClrWatsonBucketsWorker = 0;
          }
          else
          {
            (*(void (__fastcall **)(ClrDataAccess *))(*(_QWORD *)v23 + 16LL))(v23);
          }
          goto LABEL_13;
        }
      }
      (*(void (__fastcall **)(struct ICorDebugDataTarget *, __int64))(*(_QWORD *)v19 + 72LL))(v19, 1);
    }
    ClrWatsonBucketsWorker = -2147024882;
LABEL_13:
    if ( !ClrWatsonBucketsWorker )
    {
      v25 = a2 + 24;
      EnterCriticalSection(&g_dacCritSec);
      v26 = g_dacImpl;
      g_dacImpl = v32;
      v27 = 0;
      if ( v25 )
      {
        if ( (v28 = *(_QWORD *)(v25 + 16), *(_DWORD *)v25 == -532462766)
          && *(_DWORD *)(v25 + 24) == 5
          && g_CoreClrCallbacks == *(_QWORD *)(v25 + 64)
          || v28 && (unsigned int)ExecutionManager::IsManagedCodeWorker(v28) )
        {
          v27 = 1;
        }
      }
      g_dacImpl = v26;
      LeaveCriticalSection(&g_dacCritSec);
      if ( v27 )
      {
        if ( v33 && a3 )
        {
          EnterCriticalSection(&g_dacCritSec);
          v29 = g_dacImpl;
          g_dacImpl = v32;
          Thread = DacGetThread(v33);
          ClrWatsonBucketsWorker = -2147418113;
          if ( Thread )
            ClrWatsonBucketsWorker = ClrDataAccess::GetClrWatsonBucketsWorker(v32, Thread, a3);
          g_dacImpl = v29;
          LeaveCriticalSection(&g_dacCritSec);
        }
        else
        {
          ClrWatsonBucketsWorker = -2147024809;
        }
      }
      else
      {
        ClrWatsonBucketsWorker = 1;
      }
    }
    if ( v32 )
    {
      ClrDataAccess::~ClrDataAccess(v32);
      operator delete(v32, 0x160u);
    }
    goto LABEL_32;
  }
  v17 = 0;
  ClrWatsonBucketsWorker = -2147024882;
LABEL_32:
  if ( v13 )
    operator delete(v17, 0x20u);
  return (unsigned int)ClrWatsonBucketsWorker;
}

```

## disassembly

```asm
0x18000825c  mov     [rsp-38h+arg_0], rbx
0x180008261  mov     [rsp-38h+arg_10], r8
0x180008266  push    rbp
0x180008267  push    rsi
0x180008268  push    rdi
0x180008269  push    r12
0x18000826b  push    r13
0x18000826d  push    r14
0x18000826f  push    r15
0x180008271  mov     rbp, rsp
0x180008274  sub     rsp, 50h
0x180008278  mov     r15, rdx
0x18000827b  mov     r14, rcx
0x18000827e  and     [rbp+var_30], 0
0x180008282  mov     r12, [rdx+8]
0x180008286  mov     rsi, [rdx+10h]
0x18000828a  lea     rcx, ModuleName; "kernel32.dll"
0x180008291  call    cs:__imp_GetModuleHandleW
0x180008297  mov     rbx, rax
0x18000829a  test    rax, rax
0x18000829d  jz      loc_180008552
0x1800082a3  lea     rdx, ProcName; "GetProcessIdOfThread"
0x1800082aa  mov     rcx, rax; hModule
0x1800082ad  call    cs:__imp_GetProcAddress
0x1800082b3  mov     rdi, rax
0x1800082b6  lea     rdx, aGetthreadid; "GetThreadId"
0x1800082bd  mov     rcx, rbx; hModule
0x1800082c0  call    cs:__imp_GetProcAddress
0x1800082c6  mov     rbx, rax
0x1800082c9  test    rdi, rdi
0x1800082cc  jz      loc_180008552
0x1800082d2  test    rax, rax
0x1800082d5  jz      loc_180008552
0x1800082db  mov     rcx, rsi
0x1800082de  mov     rax, rdi
0x1800082e1  call    cs:__guard_dispatch_icall_fptr
0x1800082e7  mov     r13d, eax
0x1800082ea  mov     rcx, rsi
0x1800082ed  mov     rax, rbx
0x1800082f0  call    cs:__guard_dispatch_icall_fptr
0x1800082f6  mov     [rbp+arg_8], eax
0x1800082f9  and     [rbp+var_18], 0
0x1800082fe  xor     esi, esi
0x180008300  mov     [rbp+var_10], esi
0x180008303  lea     ecx, [rsi+20h]; dwBytes
0x180008306  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18000830b  mov     rdi, rax
0x18000830e  test    rax, rax
0x180008311  jz      loc_18000852A
0x180008317  lea     rax, ??_7LiveProcDataTarget@@6B@; const LiveProcDataTarget::`vftable'
0x18000831e  mov     [rdi], rax
0x180008321  mov     [rdi+8], r12
0x180008325  mov     [rdi+10h], r13d
0x180008329  mov     [rdi+18h], r14
0x18000832d  mov     [rbp+var_18], rdi
0x180008331  mov     esi, 1
0x180008336  mov     [rbp+var_10], esi
0x180008339  xor     r13d, r13d
0x18000833c  mov     [rbp+var_28], r13
0x180008340  mov     [rbp+var_20], r13d
0x180008344  lea     rax, [rbp+var_28]
0x180008348  mov     [rbp+arg_18], rax
0x18000834c  mov     [rbp+var_28], r13
0x180008350  mov     [rbp+var_28], r13
0x180008354  mov     [rbp+var_30], esi
0x180008357  mov     [rbp+var_28], r13
0x18000835b  lea     ecx, [rsi+17h]; dwBytes
0x18000835e  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180008363  mov     rbx, rax
0x180008366  test    rax, rax
0x180008369  jz      loc_1800083F1
0x18000836f  lea     rax, ??_7DataTargetAdapter@@6B@; const DataTargetAdapter::`vftable'
0x180008376  mov     [rbx], rax
0x180008379  mov     [rbx+8], r13d
0x18000837d  mov     [rbx+10h], rdi
0x180008381  mov     rcx, [rdi]
0x180008384  mov     rax, [rcx+8]
0x180008388  mov     rcx, rdi
0x18000838b  call    cs:__guard_dispatch_icall_fptr
0x180008391  mov     ecx, 160h; dwBytes
0x180008396  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18000839b  test    rax, rax
0x18000839e  jz      short loc_1800083DF
0x1800083a0  mov     r8, rdi; struct ICLRDataTarget *
0x1800083a3  mov     rdx, rbx; struct ICorDebugDataTarget *
0x1800083a6  mov     rcx, rax; this
0x1800083a9  call    ??0ClrDataAccess@@QEAA@PEAUICorDebugDataTarget@@PEAUICLRDataTarget@@@Z; ClrDataAccess::ClrDataAccess(ICorDebugDataTarget *,ICLRDataTarget *)
0x1800083ae  mov     r14, rax
0x1800083b1  test    rax, rax
0x1800083b4  jz      short loc_1800083DF
0x1800083b6  mov     rcx, rax; this
0x1800083b9  call    ?Initialize@ClrDataAccess@@QEAAJXZ; ClrDataAccess::Initialize(void)
0x1800083be  mov     ebx, eax
0x1800083c0  test    eax, eax
0x1800083c2  jns     short loc_1800083D6
0x1800083c4  mov     rcx, [r14]
0x1800083c7  mov     rax, [rcx+10h]
0x1800083cb  mov     rcx, r14
0x1800083ce  call    cs:__guard_dispatch_icall_fptr
0x1800083d4  jmp     short loc_1800083F6
0x1800083d6  mov     [rbp+var_28], r14
0x1800083da  mov     ebx, r13d
0x1800083dd  jmp     short loc_1800083F6
0x1800083df  mov     rax, [rbx]
0x1800083e2  mov     edx, esi
0x1800083e4  mov     rcx, rbx
0x1800083e7  mov     rax, [rax+48h]
0x1800083eb  call    cs:__guard_dispatch_icall_fptr
0x1800083f1  mov     ebx, 8007000Eh
0x1800083f6  mov     eax, esi
0x1800083f8  and     eax, 0FFFFFFFEh
0x1800083fb  mov     [rbp+var_30], eax
0x1800083fe  mov     eax, [rbp+var_20]
0x180008401  mov     r14, [rbp+var_28]
0x180008405  test    r14, r14
0x180008408  cmovnz  eax, esi
0x18000840b  mov     [rbp+var_20], eax
0x18000840e  test    ebx, ebx
0x180008410  jz      short loc_180008421
0x180008412  mov     eax, 80004005h
0x180008417  cmp     ebx, esi
0x180008419  cmovz   ebx, eax
0x18000841c  jmp     loc_180008500
0x180008421  lea     rbx, [r15+18h]
0x180008425  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000842c  call    cs:__imp_EnterCriticalSection
0x180008432  mov     r15, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x180008439  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r14; ClrDataAccess * g_dacImpl
0x180008440  mov     r14d, r13d
0x180008443  test    rbx, rbx
0x180008446  jz      short loc_180008478
0x180008448  mov     rcx, [rbx+10h]; unsigned __int64
0x18000844c  cmp     dword ptr [rbx], 0E0434352h
0x180008452  jnz     short loc_180008467
0x180008454  cmp     dword ptr [rbx+18h], 5
0x180008458  jnz     short loc_180008467
0x18000845a  mov     rax, [rbx+40h]
0x18000845e  cmp     cs:?g_CoreClrCallbacks@@3UCoreClrCallbacks@@A, rax; CoreClrCallbacks g_CoreClrCallbacks
0x180008465  jz      short loc_180008475
0x180008467  test    rcx, rcx
0x18000846a  jz      short loc_180008478
0x18000846c  call    ?IsManagedCodeWorker@ExecutionManager@@CAH_K@Z; ExecutionManager::IsManagedCodeWorker(unsigned __int64)
0x180008471  test    eax, eax
0x180008473  jz      short loc_180008478
0x180008475  mov     r14d, esi
0x180008478  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r15; ClrDataAccess * g_dacImpl
0x18000847f  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180008486  call    cs:__imp_LeaveCriticalSection
0x18000848c  test    r14d, r14d
0x18000848f  jnz     short loc_180008495
0x180008491  mov     ebx, esi
0x180008493  jmp     short loc_180008500
0x180008495  mov     r14, [rbp+var_28]
0x180008499  mov     ebx, [rbp+arg_8]
0x18000849c  test    ebx, ebx
0x18000849e  jz      short loc_1800084FB
0x1800084a0  mov     r12, [rbp+arg_10]
0x1800084a4  test    r12, r12
0x1800084a7  jz      short loc_1800084FB
0x1800084a9  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800084b0  call    cs:__imp_EnterCriticalSection
0x1800084b6  mov     r15, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x1800084bd  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r14; ClrDataAccess * g_dacImpl
0x1800084c4  mov     ecx, ebx; unsigned int
0x1800084c6  call    ?DacGetThread@@YAPEAVThread@@I@Z; DacGetThread(uint)
0x1800084cb  mov     ebx, 8000FFFFh
0x1800084d0  test    rax, rax
0x1800084d3  jz      short loc_1800084E5
0x1800084d5  mov     r8, r12; struct _GenericModeBlock *
0x1800084d8  mov     rdx, rax; struct Thread *
0x1800084db  mov     rcx, r14; this
0x1800084de  call    ?GetClrWatsonBucketsWorker@ClrDataAccess@@QEAAJPEAVThread@@PEAU_GenericModeBlock@@@Z; ClrDataAccess::GetClrWatsonBucketsWorker(Thread *,_GenericModeBlock *)
0x1800084e3  mov     ebx, eax
0x1800084e5  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r15; ClrDataAccess * g_dacImpl
0x1800084ec  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800084f3  call    cs:__imp_LeaveCriticalSection
0x1800084f9  jmp     short loc_180008500
0x1800084fb  mov     ebx, 80070057h
0x180008500  cmp     [rbp+var_20], r13d
0x180008504  jz      short loc_180008539
0x180008506  mov     r14, [rbp+var_28]
0x18000850a  test    r14, r14
0x18000850d  jz      short loc_180008524
0x18000850f  mov     rcx, r14; this
0x180008512  call    ??1ClrDataAccess@@QEAA@XZ; ClrDataAccess::~ClrDataAccess(void)
0x180008517  mov     edx, 160h; unsigned __int64
0x18000851c  mov     rcx, r14; void *
0x18000851f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008524  mov     [rbp+var_20], r13d
0x180008528  jmp     short loc_180008539
0x18000852a  xor     r13d, r13d
0x18000852d  mov     edi, r13d
0x180008530  mov     [rbp+var_18], r13
0x180008534  mov     ebx, 8007000Eh
0x180008539  test    esi, esi
0x18000853b  jz      short loc_18000854E
0x18000853d  mov     edx, 20h ; ' '; unsigned __int64
0x180008542  mov     rcx, rdi; void *
0x180008545  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000854a  mov     [rbp+var_10], r13d
0x18000854e  mov     eax, ebx
0x180008550  jmp     short loc_180008557
0x180008552  mov     eax, 80004005h
0x180008557  mov     rbx, [rsp+50h+arg_0]
0x18000855f  add     rsp, 50h
0x180008563  pop     r15
0x180008565  pop     r14
0x180008567  pop     r13
0x180008569  pop     r12
0x18000856b  pop     rdi
0x18000856c  pop     rsi
0x18000856d  pop     rbp
0x18000856e  retn
```
