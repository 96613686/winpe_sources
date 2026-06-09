# TracingFailureCache::TraceFailure(CallStackContext *,char const *,long)

- ea: `0x180008ce8`
- end: `0x180008dfd`
- name: `?TraceFailure@TracingFailureCache@@QEAAXPEAVCallStackContext@@PEBDJ@Z`
- size: `277`
- prototype: `void __fastcall(TracingFailureCache *__hidden this, struct CallStackContext *, const char *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180008460`

## callees

- `0x180008618`
- `0x18000872c`
- `0x1800088ec`
- `0x180008b64`
- `0x180008ce8`
- `0x18001d35d`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008df6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008d1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008d1b`
- `MFPlat!MFGetSystemTime` at `0x180008d40`
- `MFPlat!MFGetSystemTime` at `0x180008d40`

## pseudocode

```c
void __fastcall TracingFailureCache::TraceFailure(
        TracingFailureCache *this,
        struct CallStackContext *a2,
        const char *a3,
        int a4)
{
  unsigned int v8; // edx
  struct TracingFailureDetails *Match; // rdi
  MFTIME v10; // rax
  int v11; // eax
  bool v12; // cf
  _OWORD Buf1[3]; // [rsp+30h] [rbp-38h] BYREF

  Buf1[0] = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 11);
  TracingFailureDetails::GenerateHashCodeForContext(a2, (struct TracingFailureHash *)Buf1);
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  Match = TracingFailureCache::FindMatch(this, (struct TracingFailureHash *)Buf1, a2, a3, a4);
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
    v12 = *((_DWORD *)this + 10) < 0x1Cu;
    if ( *((_DWORD *)this + 10) == 28 )
    {
      TracingFailureCache::EvictOldest(this, v8);
      v12 = *((_DWORD *)this + 10) < 0x1Cu;
    }
    if ( v12 )
    {
      if ( *((_QWORD *)this + 11) )
      {
        TracingFailureDetails::Initialize(
          (TracingFailureDetails *)(*((_QWORD *)this + 11) + 2328LL * *((unsigned int *)this + 10)),
          a2,
          a3,
          a4);
        ++*((_DWORD *)this + 10);
        Buf1[0] = *((_OWORD *)a2 + 125);
        if ( !memcmp_0(Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
          ++*((_DWORD *)this + 12);
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180008ce8  push    rbx
0x180008cea  push    rbp
0x180008ceb  push    rsi
0x180008cec  push    rdi
0x180008ced  push    r14
0x180008cef  sub     rsp, 40h
0x180008cf3  xorps   xmm0, xmm0
0x180008cf6  mov     ebp, r9d
0x180008cf9  movups  [rsp+68h+Buf1], xmm0
0x180008cfe  mov     r14, r8
0x180008d01  mov     rsi, rdx
0x180008d04  mov     rbx, rcx
0x180008d07  lock inc dword ptr [rcx+2Ch]
0x180008d0b  lea     rdx, [rsp+68h+Buf1]; struct TracingFailureHash *
0x180008d10  mov     rcx, rsi; struct CallStackContext *
0x180008d13  call    ?GenerateHashCodeForContext@TracingFailureDetails@@SAXAEAVCallStackContext@@AEAVTracingFailureHash@@@Z; TracingFailureDetails::GenerateHashCodeForContext(CallStackContext &,TracingFailureHash &)
0x180008d18  mov     rcx, rbx; lpCriticalSection
0x180008d1b  call    cs:__imp_EnterCriticalSection
0x180008d21  mov     r9, r14; char *
0x180008d24  mov     [rsp+68h+var_48], ebp; int
0x180008d28  mov     r8, rsi; struct CallStackContext *
0x180008d2b  lea     rdx, [rsp+68h+Buf1]; struct TracingFailureHash *
0x180008d30  mov     rcx, rbx; this
0x180008d33  call    ?FindMatch@TracingFailureCache@@IEAAPEAVTracingFailureDetails@@AEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z; TracingFailureCache::FindMatch(TracingFailureHash &,CallStackContext &,char const *,long)
0x180008d38  mov     rdi, rax
0x180008d3b  test    rax, rax
0x180008d3e  jz      short loc_180008D84
0x180008d40  call    cs:__imp_MFGetSystemTime
0x180008d46  inc     dword ptr [rdi+900h]
0x180008d4c  mov     [rdi+8F8h], rax
0x180008d53  mov     ecx, [rsi+7E8h]
0x180008d59  mov     [rdi+7E8h], ecx
0x180008d5f  mov     ecx, [rsi+7C0h]
0x180008d65  mov     [rdi+7C0h], ecx
0x180008d6b  mov     eax, [rsi+7E4h]
0x180008d71  test    eax, eax
0x180008d73  jz      short loc_180008D7B
0x180008d75  mov     [rdi+7E4h], eax
0x180008d7b  mov     byte ptr [rdi+904h], 0
0x180008d82  jmp     short loc_180008DE9
0x180008d84  cmp     dword ptr [rbx+28h], 1Ch
0x180008d88  jnz     short loc_180008D96
0x180008d8a  mov     rcx, rbx; this
0x180008d8d  call    ?EvictOldest@TracingFailureCache@@IEAAXK@Z; TracingFailureCache::EvictOldest(ulong)
0x180008d92  cmp     dword ptr [rbx+28h], 1Ch
0x180008d96  jnb     short loc_180008DE9
0x180008d98  cmp     qword ptr [rbx+58h], 0
0x180008d9d  jz      short loc_180008DE9
0x180008d9f  mov     eax, [rbx+28h]
0x180008da2  mov     r9d, ebp; int
0x180008da5  imul    rcx, rax, 918h
0x180008dac  mov     r8, r14; char *
0x180008daf  mov     rdx, rsi; struct CallStackContext *
0x180008db2  add     rcx, [rbx+58h]; this
0x180008db6  call    ?Initialize@TracingFailureDetails@@QEAAXAEAVCallStackContext@@PEBDJ@Z; TracingFailureDetails::Initialize(CallStackContext &,char const *,long)
0x180008dbb  inc     dword ptr [rbx+28h]
0x180008dbe  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180008dc5  movups  xmm0, xmmword ptr [rsi+7D0h]
0x180008dcc  mov     r8d, 10h; Size
0x180008dd2  lea     rcx, [rsp+68h+Buf1]; Buf1
0x180008dd7  movdqu  [rsp+68h+Buf1], xmm0
0x180008ddd  call    memcmp_0
0x180008de2  test    eax, eax
0x180008de4  jnz     short loc_180008DE9
0x180008de6  inc     dword ptr [rbx+30h]
0x180008de9  mov     rcx, rbx
0x180008dec  add     rsp, 40h
0x180008df0  pop     r14
0x180008df2  pop     rdi
0x180008df3  pop     rsi
0x180008df4  pop     rbp
0x180008df5  pop     rbx
0x180008df6  jmp     cs:__imp_LeaveCriticalSection
```
