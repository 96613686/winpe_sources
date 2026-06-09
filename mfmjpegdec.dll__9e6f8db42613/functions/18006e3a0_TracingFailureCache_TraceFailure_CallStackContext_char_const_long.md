# TracingFailureCache::TraceFailure(CallStackContext *,char const *,long)

- ea: `0x18006e3a0`
- end: `0x18006e476`
- name: `?TraceFailure@TracingFailureCache@@QEAAXPEAVCallStackContext@@PEBDJ@Z`
- size: `214`
- prototype: `void __fastcall(TracingFailureCache *__hidden this, struct CallStackContext *, const char *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18006dd00`

## callees

- `0x180021444`
- `0x1800224f0`
- `0x1800225ec`
- `0x18006e064`
- `0x18006e3a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e3de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e3de`
- `MFPlat!MFGetSystemTime` at `0x18006e403`
- `MFPlat!MFGetSystemTime` at `0x18006e403`

## pseudocode

```c
void __fastcall TracingFailureCache::TraceFailure(
        TracingFailureCache *this,
        struct CallStackContext *a2,
        const char *a3,
        int a4)
{
  struct TracingFailureHash *v8; // rdx
  struct TracingFailureDetails *Match; // rbx
  MFTIME v10; // rax
  int v11; // eax
  _OWORD v12[2]; // [rsp+30h] [rbp-28h] BYREF
  TracingFailureCache *v13; // [rsp+60h] [rbp+8h] BYREF

  v12[0] = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 11);
  TracingFailureDetails::GenerateHashCodeForContext(a2, (struct TracingFailureHash *)v12);
  v13 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  Match = TracingFailureCache::FindMatch(this, (struct TracingFailureHash *)v12, a2, a3, a4);
  if ( Match )
  {
    v10 = MFGetSystemTime();
    ++*((_DWORD *)Match + 576);
    *((_QWORD *)Match + 287) = v10;
    *((_DWORD *)Match + 506) = *((_DWORD *)a2 + 506);
    *((_DWORD *)Match + 496) = *((_DWORD *)a2 + 496);
    v11 = *((_DWORD *)a2 + 505);
    if ( v11 )
      *((_DWORD *)Match + 505) = v11;
    *((_BYTE *)Match + 2308) = 0;
  }
  else
  {
    TracingFailureCache::Add(this, v8, a2, a3, a4);
  }
  CMFCSAutoLock::~CMFCSAutoLock((CMFCSAutoLock *)&v13);
}

```

## disassembly

```asm
0x18006e3a0  mov     rax, rsp
0x18006e3a3  mov     [rax+10h], rbx
0x18006e3a7  mov     [rax+18h], rbp
0x18006e3ab  push    rsi
0x18006e3ac  push    rdi
0x18006e3ad  push    r14
0x18006e3af  sub     rsp, 40h
0x18006e3b3  xorps   xmm0, xmm0
0x18006e3b6  mov     ebp, r9d
0x18006e3b9  movups  xmmword ptr [rax-28h], xmm0
0x18006e3bd  mov     r14, r8
0x18006e3c0  mov     rdi, rdx
0x18006e3c3  mov     rsi, rcx
0x18006e3c6  lock inc dword ptr [rcx+2Ch]
0x18006e3ca  lea     rdx, [rax-28h]; struct TracingFailureHash *
0x18006e3ce  mov     rcx, rdi; struct CallStackContext *
0x18006e3d1  call    ?GenerateHashCodeForContext@TracingFailureDetails@@SAXAEAVCallStackContext@@AEAVTracingFailureHash@@@Z; TracingFailureDetails::GenerateHashCodeForContext(CallStackContext &,TracingFailureHash &)
0x18006e3d6  mov     rcx, rsi; lpCriticalSection
0x18006e3d9  mov     [rsp+58h+arg_0], rsi
0x18006e3de  call    cs:__imp_EnterCriticalSection
0x18006e3e4  mov     r9, r14; char *
0x18006e3e7  mov     [rsp+58h+var_38], ebp; int
0x18006e3eb  mov     r8, rdi; struct CallStackContext *
0x18006e3ee  lea     rdx, [rsp+58h+var_28]; struct TracingFailureHash *
0x18006e3f3  mov     rcx, rsi; this
0x18006e3f6  call    ?FindMatch@TracingFailureCache@@IEAAPEAVTracingFailureDetails@@AEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z; TracingFailureCache::FindMatch(TracingFailureHash &,CallStackContext &,char const *,long)
0x18006e3fb  mov     rbx, rax
0x18006e3fe  test    rax, rax
0x18006e401  jz      short loc_18006E447
0x18006e403  call    cs:__imp_MFGetSystemTime
0x18006e409  inc     dword ptr [rbx+900h]
0x18006e40f  mov     [rbx+8F8h], rax
0x18006e416  mov     ecx, [rdi+7E8h]
0x18006e41c  mov     [rbx+7E8h], ecx
0x18006e422  mov     ecx, [rdi+7C0h]
0x18006e428  mov     [rbx+7C0h], ecx
0x18006e42e  mov     eax, [rdi+7E4h]
0x18006e434  test    eax, eax
0x18006e436  jz      short loc_18006E43E
0x18006e438  mov     [rbx+7E4h], eax
0x18006e43e  mov     byte ptr [rbx+904h], 0
0x18006e445  jmp     short loc_18006E459
0x18006e447  mov     r9, r14; char *
0x18006e44a  mov     [rsp+58h+var_38], ebp; int
0x18006e44e  mov     r8, rdi; struct CallStackContext *
0x18006e451  mov     rcx, rsi; this
0x18006e454  call    ?Add@TracingFailureCache@@IEAA_NAEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z; TracingFailureCache::Add(TracingFailureHash &,CallStackContext &,char const *,long)
0x18006e459  lea     rcx, [rsp+58h+arg_0]; this
0x18006e45e  call    ??1CMFCSAutoLock@@QEAA@XZ; CMFCSAutoLock::~CMFCSAutoLock(void)
0x18006e463  mov     rbx, [rsp+58h+arg_8]
0x18006e468  mov     rbp, [rsp+58h+arg_10]
0x18006e46d  add     rsp, 40h
0x18006e471  pop     r14
0x18006e473  pop     rdi
0x18006e474  pop     rsi
0x18006e475  retn
```
