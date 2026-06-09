# CDefragAsyncWorker::FinalRelease(void)

- ea: `0x1800118d8`
- end: `0x180011963`
- name: `?FinalRelease@CDefragAsyncWorker@@QEAAJXZ`
- size: `139`
- prototype: `__int64 __fastcall(CDefragAsyncWorker *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800117c0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800118d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001192f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001192f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011950`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011950`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x180011943`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x180011943`

## pseudocode

```c
__int64 __fastcall CDefragAsyncWorker::FinalRelease(CDefragAsyncWorker *this)
{
  char *v2; // rcx
  unsigned int v3; // ebx
  _DWORD v5[18]; // [rsp+20h] [rbp-48h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v5, "CDefragAsyncWorker::FinalRelease", 163, 1);
  if ( *((_DWORD *)this + 20) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
    *((_DWORD *)this + 20) = 0;
  }
  v2 = (char *)*((_QWORD *)this + 21);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    PowerClearRequest(v2, PowerRequestSystemRequired);
    CloseHandle(*((HANDLE *)this + 21));
    *((_QWORD *)this + 21) = 0;
  }
  v3 = v5[0];
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v5);
  return v3;
}

```

## disassembly

```asm
0x1800118d8  push    rbx
0x1800118da  sub     rsp, 60h
0x1800118de  mov     rbx, rcx
0x1800118e1  lea     rdx, aCdefragasyncwo_8; "CDefragAsyncWorker::FinalRelease"
0x1800118e8  lea     rcx, [rsp+68h+var_48]; this
0x1800118ed  mov     r9d, 1; unsigned __int16
0x1800118f3  mov     r8d, 0A3h; unsigned __int16
0x1800118f9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800118fe  cmp     dword ptr [rbx+50h], 0
0x180011902  jnz     short loc_18001192B
0x180011904  mov     rcx, [rbx+0A8h]; PowerRequest
0x18001190b  lea     rax, [rcx-1]
0x18001190f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011913  jbe     short loc_18001193E
0x180011915  mov     ebx, [rsp+68h+var_48]
0x180011919  lea     rcx, [rsp+68h+var_48]; this
0x18001191e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180011923  mov     eax, ebx
0x180011925  add     rsp, 60h
0x180011929  pop     rbx
0x18001192a  retn
0x18001192b  lea     rcx, [rbx+28h]; lpCriticalSection
0x18001192f  call    cs:__imp_DeleteCriticalSection
0x180011935  mov     dword ptr [rbx+50h], 0
0x18001193c  jmp     short loc_180011904
0x18001193e  mov     edx, 1; RequestType
0x180011943  call    cs:__imp_PowerClearRequest
0x180011949  mov     rcx, [rbx+0A8h]; hObject
0x180011950  call    cs:__imp_CloseHandle
0x180011956  mov     qword ptr [rbx+0A8h], 0
0x180011961  jmp     short loc_180011915
```
