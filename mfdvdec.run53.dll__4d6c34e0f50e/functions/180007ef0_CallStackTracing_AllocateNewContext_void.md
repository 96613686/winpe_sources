# CallStackTracing::AllocateNewContext(void)

- ea: `0x180007ef0`
- end: `0x180008109`
- name: `?AllocateNewContext@CallStackTracing@@UEAAPEAVCallStackContext@@XZ`
- size: `537`
- prototype: `struct CallStackContext *__fastcall(CallStackTracing *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180001120`
- `0x180001178`
- `0x180001eb0`
- `0x180005fb0`
- `0x180007db0`
- `0x180007ef0`
- `0x1800082ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007fc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008047`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800080c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800080df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800080e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007fc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008047`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800080c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800080df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800080e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000806f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007f30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000806f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008002`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008002`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008062`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180008062`

## pseudocode

```c
struct CallStackContext *__fastcall CallStackTracing::AllocateNewContext(CallStackTracing *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  _QWORD *v3; // rbp
  _DWORD *v4; // r13
  __int64 v5; // r15
  CallStackInfo *v6; // r12
  __int64 v7; // rsi
  _DWORD *v8; // r12
  DWORD CurrentThreadId; // eax
  DWORD v10; // esi
  char *v11; // rsi
  DWORD v13; // [rsp+60h] [rbp+8h]
  _QWORD *v14; // [rsp+68h] [rbp+10h]

  v14 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 120);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 3);
  v3 = (_QWORD *)*((_QWORD *)this + 20);
  v4 = (_DWORD *)((char *)this + 172);
  if ( v3 )
  {
    v8 = (_DWORD *)((char *)this + 168);
    *((_QWORD *)this + 20) = v3[254];
    v3[254] = 0;
    --*((_DWORD *)this + 42);
    CurrentThreadId = GetCurrentThreadId();
    v5 = 124;
    *((_DWORD *)v3 + 498) = 124;
    v10 = CurrentThreadId;
    memset_0(v3, 0, 0x7C0u);
    CallStackContext::ClearState((CallStackContext *)v3);
    *((_DWORD *)v3 + 496) = v10;
    v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 120);
    v3[254] = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 3);
LABEL_10:
    v3[254] = *((_QWORD *)this + 22);
    if ( TlsSetValue(*((_DWORD *)this + 3), v3) )
    {
      *((_QWORD *)this + 22) = v3;
      v14 = v3;
    }
    else
    {
      EnterCriticalSection(v2);
      if ( *v8 >= *((_DWORD *)this + 28) )
      {
        --*v4;
        v11 = (char *)(v3 + 248);
        do
        {
          v11 -= 16;
          rgbtransYUY2FulloutRight(v11);
          --v5;
        }
        while ( v5 );
        operator delete(v3);
        v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 120);
      }
      else
      {
        v3[254] = *((_QWORD *)this + 20);
        ++*v8;
        *((_QWORD *)this + 20) = v3;
      }
      LeaveCriticalSection(v2);
    }
    goto LABEL_18;
  }
  ++*v4;
  v3 = operator new(0x7F8u);
  v5 = 124;
  if ( v3 )
  {
    v13 = GetCurrentThreadId();
    v6 = (CallStackInfo *)v3;
    v7 = 124;
    do
    {
      CallStackInfo::CallStackInfo(v6);
      v6 = (CallStackInfo *)((char *)v6 + 16);
      --v7;
    }
    while ( v7 );
    *((_DWORD *)v3 + 498) = 124;
    memset_0(v3, 0, 0x7C0u);
    CallStackContext::ClearState((CallStackContext *)v3);
    v3[254] = 0;
    v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 120);
    *((_DWORD *)v3 + 496) = v13;
  }
  else
  {
    v3 = 0;
  }
  LeaveCriticalSection(v2);
  if ( v3 )
  {
    v8 = (_DWORD *)((char *)this + 168);
    goto LABEL_10;
  }
LABEL_18:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (struct CallStackContext *)v14;
}

```

## disassembly

```asm
0x180007ef0  mov     [rsp+arg_18], rbx
0x180007ef5  push    rbp
0x180007ef6  push    rsi
0x180007ef7  push    rdi
0x180007ef8  push    r12
0x180007efa  push    r13
0x180007efc  push    r14
0x180007efe  push    r15
0x180007f00  sub     rsp, 20h
0x180007f04  mov     r14, rcx
0x180007f07  mov     [rsp+58h+arg_8], 0
0x180007f10  add     rcx, 10h; lpCriticalSection
0x180007f14  call    cs:__imp_EnterCriticalSection
0x180007f1a  lea     rcx, [r14+38h]; lpCriticalSection
0x180007f1e  call    cs:__imp_EnterCriticalSection
0x180007f24  lea     rsi, [r14+78h]
0x180007f28  mov     rcx, rsi; lpCriticalSection
0x180007f2b  mov     [rsp+58h+arg_10], rsi
0x180007f30  call    cs:__imp_EnterCriticalSection
0x180007f36  mov     rbp, [r14+0A0h]
0x180007f3d  lea     r13, [r14+0ACh]
0x180007f44  test    rbp, rbp
0x180007f47  jnz     loc_180007FDE
0x180007f4d  inc     dword ptr [r13+0]
0x180007f51  mov     ecx, 7F8h; Size
0x180007f56  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007f5b  mov     rbp, rax
0x180007f5e  mov     r15d, 7Ch ; '|'
0x180007f64  test    rax, rax
0x180007f67  jz      short loc_180007FC1
0x180007f69  call    cs:__imp_GetCurrentThreadId
0x180007f6f  mov     [rsp+58h+arg_0], eax
0x180007f73  mov     r12, rbp
0x180007f76  mov     esi, r15d
0x180007f79  mov     rcx, r12; this
0x180007f7c  call    ??0CallStackInfo@@QEAA@XZ; CallStackInfo::CallStackInfo(void)
0x180007f81  add     r12, 10h
0x180007f85  sub     rsi, 1
0x180007f89  jnz     short loc_180007F79
0x180007f8b  xor     edx, edx; Val
0x180007f8d  mov     [rbp+7C8h], r15d
0x180007f94  mov     r8d, 7C0h; Size
0x180007f9a  mov     rcx, rbp; void *
0x180007f9d  call    memset_0
0x180007fa2  mov     rcx, rbp; this
0x180007fa5  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x180007faa  mov     eax, [rsp+58h+arg_0]
0x180007fae  mov     [rbp+7F0h], rsi
0x180007fb5  lea     rsi, [r14+78h]
0x180007fb9  mov     [rbp+7C0h], eax
0x180007fbf  jmp     short loc_180007FC3
0x180007fc1  xor     ebp, ebp
0x180007fc3  mov     rcx, rsi; lpCriticalSection
0x180007fc6  call    cs:__imp_LeaveCriticalSection
0x180007fcc  test    rbp, rbp
0x180007fcf  jz      loc_1800080DB
0x180007fd5  lea     r12, [r14+0A8h]
0x180007fdc  jmp     short loc_18000804D
0x180007fde  mov     rax, [rbp+7F0h]
0x180007fe5  lea     r12, [r14+0A8h]
0x180007fec  mov     [r14+0A0h], rax
0x180007ff3  mov     qword ptr [rbp+7F0h], 0
0x180007ffe  dec     dword ptr [r12]
0x180008002  call    cs:__imp_GetCurrentThreadId
0x180008008  mov     r15d, 7Ch ; '|'
0x18000800e  xor     edx, edx; Val
0x180008010  mov     r8d, 7C0h; Size
0x180008016  mov     [rbp+7C8h], r15d
0x18000801d  mov     rcx, rbp; void *
0x180008020  mov     esi, eax
0x180008022  call    memset_0
0x180008027  mov     rcx, rbp; this
0x18000802a  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x18000802f  mov     [rbp+7C0h], esi
0x180008035  lea     rsi, [r14+78h]
0x180008039  mov     rcx, rsi; lpCriticalSection
0x18000803c  mov     qword ptr [rbp+7F0h], 0
0x180008047  call    cs:__imp_LeaveCriticalSection
0x18000804d  mov     rax, [r14+0B0h]
0x180008054  mov     rdx, rbp; lpTlsValue
0x180008057  mov     [rbp+7F0h], rax
0x18000805e  mov     ecx, [r14+0Ch]; dwTlsIndex
0x180008062  call    cs:__imp_TlsSetValue
0x180008068  test    eax, eax
0x18000806a  jnz     short loc_1800080CF
0x18000806c  mov     rcx, rsi; lpCriticalSection
0x18000806f  call    cs:__imp_EnterCriticalSection
0x180008075  mov     eax, [r14+70h]
0x180008079  cmp     [r12], eax
0x18000807d  jge     short loc_18000809A
0x18000807f  mov     rax, [r14+0A0h]
0x180008086  mov     [rbp+7F0h], rax
0x18000808d  inc     dword ptr [r12]
0x180008091  mov     [r14+0A0h], rbp
0x180008098  jmp     short loc_1800080C4
0x18000809a  dec     dword ptr [r13+0]
0x18000809e  lea     rsi, [rbp+7C0h]
0x1800080a5  sub     rsi, 10h
0x1800080a9  mov     rcx, rsi
0x1800080ac  call    rgbtransYUY2FulloutRight
0x1800080b1  sub     r15, 1
0x1800080b5  jnz     short loc_1800080A5
0x1800080b7  mov     rcx, rbp; Block
0x1800080ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800080bf  mov     rsi, [rsp+58h+arg_10]
0x1800080c4  mov     rcx, rsi; lpCriticalSection
0x1800080c7  call    cs:__imp_LeaveCriticalSection
0x1800080cd  jmp     short loc_1800080DB
0x1800080cf  mov     [r14+0B0h], rbp
0x1800080d6  mov     [rsp+58h+arg_8], rbp
0x1800080db  lea     rcx, [r14+38h]; lpCriticalSection
0x1800080df  call    cs:__imp_LeaveCriticalSection
0x1800080e5  lea     rcx, [r14+10h]; lpCriticalSection
0x1800080e9  call    cs:__imp_LeaveCriticalSection
0x1800080ef  mov     rax, [rsp+58h+arg_8]
0x1800080f4  mov     rbx, [rsp+58h+arg_18]
0x1800080f9  add     rsp, 20h
0x1800080fd  pop     r15
0x1800080ff  pop     r14
0x180008101  pop     r13
0x180008103  pop     r12
0x180008105  pop     rdi
0x180008106  pop     rsi
0x180008107  pop     rbp
0x180008108  retn
```
