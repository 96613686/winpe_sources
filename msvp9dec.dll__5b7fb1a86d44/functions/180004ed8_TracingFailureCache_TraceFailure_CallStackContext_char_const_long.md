# TracingFailureCache::TraceFailure(CallStackContext *,char const *,long)

- ea: `0x180004ed8`
- end: `0x180004f9a`
- name: `?TraceFailure@TracingFailureCache@@QEAAXPEAVCallStackContext@@PEBDJ@Z`
- size: `194`
- prototype: `void __fastcall(TracingFailureCache *__hidden this, struct CallStackContext *, const char *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004800`

## callees

- `0x1800026d8`
- `0x1800027d4`
- `0x180004b3c`
- `0x180004ed8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f0b`
- `MFPlat!MFGetSystemTime` at `0x180004f30`
- `MFPlat!MFGetSystemTime` at `0x180004f30`

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
  _OWORD v12[3]; // [rsp+30h] [rbp-38h] BYREF

  v12[0] = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 11);
  TracingFailureDetails::GenerateHashCodeForContext(a2, (struct TracingFailureHash *)v12);
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
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x180004ed8  push    rbx
0x180004eda  push    rbp
0x180004edb  push    rsi
0x180004edc  push    rdi
0x180004edd  push    r14
0x180004edf  sub     rsp, 40h
0x180004ee3  xorps   xmm0, xmm0
0x180004ee6  mov     ebp, r9d
0x180004ee9  movups  [rsp+68h+var_38], xmm0
0x180004eee  mov     r14, r8
0x180004ef1  mov     rdi, rdx
0x180004ef4  mov     rsi, rcx
0x180004ef7  lock inc dword ptr [rcx+2Ch]
0x180004efb  lea     rdx, [rsp+68h+var_38]; struct TracingFailureHash *
0x180004f00  mov     rcx, rdi; struct CallStackContext *
0x180004f03  call    ?GenerateHashCodeForContext@TracingFailureDetails@@SAXAEAVCallStackContext@@AEAVTracingFailureHash@@@Z; TracingFailureDetails::GenerateHashCodeForContext(CallStackContext &,TracingFailureHash &)
0x180004f08  mov     rcx, rsi; lpCriticalSection
0x180004f0b  call    cs:__imp_EnterCriticalSection
0x180004f11  mov     r9, r14; char *
0x180004f14  mov     [rsp+68h+var_48], ebp; int
0x180004f18  mov     r8, rdi; struct CallStackContext *
0x180004f1b  lea     rdx, [rsp+68h+var_38]; struct TracingFailureHash *
0x180004f20  mov     rcx, rsi; this
0x180004f23  call    ?FindMatch@TracingFailureCache@@IEAAPEAVTracingFailureDetails@@AEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z; TracingFailureCache::FindMatch(TracingFailureHash &,CallStackContext &,char const *,long)
0x180004f28  mov     rbx, rax
0x180004f2b  test    rax, rax
0x180004f2e  jz      short loc_180004F74
0x180004f30  call    cs:__imp_MFGetSystemTime
0x180004f36  inc     dword ptr [rbx+900h]
0x180004f3c  mov     [rbx+8F8h], rax
0x180004f43  mov     ecx, [rdi+7E8h]
0x180004f49  mov     [rbx+7E8h], ecx
0x180004f4f  mov     ecx, [rdi+7C0h]
0x180004f55  mov     [rbx+7C0h], ecx
0x180004f5b  mov     eax, [rdi+7E4h]
0x180004f61  test    eax, eax
0x180004f63  jz      short loc_180004F6B
0x180004f65  mov     [rbx+7E4h], eax
0x180004f6b  mov     byte ptr [rbx+904h], 0
0x180004f72  jmp     short loc_180004F86
0x180004f74  mov     r9, r14; char *
0x180004f77  mov     [rsp+68h+var_48], ebp; int
0x180004f7b  mov     r8, rdi; struct CallStackContext *
0x180004f7e  mov     rcx, rsi; this
0x180004f81  call    ?Add@TracingFailureCache@@IEAA_NAEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z; TracingFailureCache::Add(TracingFailureHash &,CallStackContext &,char const *,long)
0x180004f86  mov     rcx, rsi
0x180004f89  add     rsp, 40h
0x180004f8d  pop     r14
0x180004f8f  pop     rdi
0x180004f90  pop     rsi
0x180004f91  pop     rbp
0x180004f92  pop     rbx
0x180004f93  jmp     cs:__imp_LeaveCriticalSection
```
