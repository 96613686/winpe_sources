# CflFreeBuffer

- ea: `0x180010700`
- end: `0x1800107d8`
- name: `CflFreeBuffer`
- size: `216`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `22`
- callee_count: `4`
- tags: ``

## callers

- `0x1800107e0`
- `0x18001aee4`
- `0x18001bf60`
- `0x18001c500`
- `0x18001cb44`
- `0x18001dae0`
- `0x18001e970`
- `0x18001ebd8`
- `0x18001f2d8`
- `0x18001fb28`
- `0x180020040`
- `0x180020a54`
- `0x1800286d4`
- `0x180028cc4`
- `0x180029614`
- `0x1800298d0`
- `0x18002a498`
- `0x18002a7cc`
- `0x18002aa34`
- `0x18002ad54`
- `0x18002aee8`
- `0x18002b264`

## callees

- `0x1800058b0`
- `0x1800092e4`
- `0x18000a31c`
- `0x180010700`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800107c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800107b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010789`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010789`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010796`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010796`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CflFreeBuffer(HLOCAL hMem)
{
  __int64 *Local; // rax
  void *v3; // rbx
  HANDLE ProcessHeap; // rax
  int v6; // [rsp+20h] [rbp-58h] BYREF
  const char *v7; // [rsp+28h] [rbp-50h]
  LPVOID lpMem; // [rsp+30h] [rbp-48h]
  char v9; // [rsp+38h] [rbp-40h]
  _QWORD v10[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v11; // [rsp+50h] [rbp-28h]
  DWORD CurrentThreadId; // [rsp+58h] [rbp-20h]
  int *v13; // [rsp+60h] [rbp-18h]
  char v14; // [rsp+68h] [rbp-10h]

  v9 = 0;
  v6 = 0;
  v7 = "CflFreeBuffer";
  lpMem = 0;
  v10[0] = 0;
  v10[1] = CflApiTraceProvider::Instance();
  v11 = 0;
  CurrentThreadId = 0;
  v13 = &v6;
  v14 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         (__int64)"CflFreeBuffer",
                         1);
    v10[0] = Local;
    if ( Local )
    {
      v11 = *Local;
      *Local = (__int64)v10;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  LocalFree(hMem);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v10);
  if ( v9 )
  {
    v3 = lpMem;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180010700  push    rbx
0x180010702  sub     rsp, 70h
0x180010706  mov     rbx, rcx
0x180010709  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18001070e  mov     [rsp+78h+var_40], 0
0x180010713  mov     [rsp+78h+var_58], 0
0x18001071b  lea     rcx, aCflfreebuffer_0; "CflFreeBuffer"
0x180010722  mov     [rsp+78h+var_50], rcx
0x180010727  mov     [rsp+78h+lpMem], 0
0x180010730  mov     [rsp+78h+var_38], 0
0x180010739  mov     [rsp+78h+var_30], rax
0x18001073e  mov     [rsp+78h+var_28], 0
0x180010747  mov     [rsp+78h+var_20], 0
0x18001074f  lea     rax, [rsp+78h+var_58]
0x180010754  mov     [rsp+78h+var_18], rax
0x180010759  mov     [rsp+78h+var_10], 0
0x18001075e  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180010766  jz      short loc_180010793
0x180010768  mov     dl, 1
0x18001076a  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001076f  mov     [rsp+78h+var_38], rax
0x180010774  test    rax, rax
0x180010777  jz      short loc_180010793
0x180010779  mov     rcx, [rax]
0x18001077c  mov     [rsp+78h+var_28], rcx
0x180010781  lea     rcx, [rsp+78h+var_38]
0x180010786  mov     [rax], rcx
0x180010789  call    cs:__imp_GetCurrentThreadId
0x18001078f  mov     [rsp+78h+var_20], eax
0x180010793  mov     rcx, rbx; hMem
0x180010796  call    cs:__imp_LocalFree
0x18001079c  lea     rcx, [rsp+78h+var_38]; this
0x1800107a1  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800107a6  cmp     [rsp+78h+var_40], 0
0x1800107ab  jz      short loc_1800107C6
0x1800107ad  mov     rbx, [rsp+78h+lpMem]
0x1800107b2  call    cs:__imp_GetProcessHeap
0x1800107b8  mov     r8, rbx; lpMem
0x1800107bb  xor     edx, edx; dwFlags
0x1800107bd  mov     rcx, rax; hHeap
0x1800107c0  call    cs:__imp_HeapFree
0x1800107c6  xor     eax, eax
0x1800107c8  jmp     short loc_1800107D1
0x1800107ca  mov     eax, [rsp+78h+arg_8]
0x1800107d1  add     rsp, 70h
0x1800107d5  pop     rbx
0x1800107d6  retn
```
