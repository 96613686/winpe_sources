# CflSecureFreeBuffer

- ea: `0x180011130`
- end: `0x180011225`
- name: `CflSecureFreeBuffer`
- size: `245`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180011b10`
- `0x18001af00`
- `0x18001dae0`
- `0x180020040`
- `0x180020a54`
- `0x1800298d0`

## callees

- `0x1800058b0`
- `0x1800092e4`
- `0x18000a31c`
- `0x180011130`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001120d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001120d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800111ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800111ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800111b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800111b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800111e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800111e3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800111c6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800111c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CflSecureFreeBuffer(HLOCAL hMem)
{
  __int64 *Local; // rax
  SIZE_T v3; // rax
  _BYTE *i; // rcx
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  int v8; // [rsp+20h] [rbp-58h] BYREF
  const char *v9; // [rsp+28h] [rbp-50h]
  LPVOID lpMem; // [rsp+30h] [rbp-48h]
  char v11; // [rsp+38h] [rbp-40h]
  _QWORD v12[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v13; // [rsp+50h] [rbp-28h]
  DWORD CurrentThreadId; // [rsp+58h] [rbp-20h]
  int *v15; // [rsp+60h] [rbp-18h]
  char v16; // [rsp+68h] [rbp-10h]

  v11 = 0;
  v8 = 0;
  v9 = "CflSecureFreeBuffer";
  lpMem = 0;
  v12[0] = 0;
  v12[1] = CflApiTraceProvider::Instance();
  v13 = 0;
  CurrentThreadId = 0;
  v15 = &v8;
  v16 = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = (__int64 *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                         (__int64)"CflSecureFreeBuffer",
                         1);
    v12[0] = Local;
    if ( Local )
    {
      v13 = *Local;
      *Local = (__int64)v12;
      CurrentThreadId = GetCurrentThreadId();
    }
  }
  v3 = LocalSize(hMem);
  for ( i = hMem; v3; --v3 )
    *i++ = 0;
  LocalFree(hMem);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v12);
  if ( v11 )
  {
    v5 = lpMem;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180011130  push    rbx
0x180011132  sub     rsp, 70h
0x180011136  mov     rbx, rcx
0x180011139  call    ?Instance@CflApiTraceProvider@@KAPEAV1@XZ; CflApiTraceProvider::Instance(void)
0x18001113e  mov     [rsp+78h+var_40], 0
0x180011143  mov     [rsp+78h+var_58], 0
0x18001114b  lea     rcx, aCflsecurefreeb_0; "CflSecureFreeBuffer"
0x180011152  mov     [rsp+78h+var_50], rcx
0x180011157  mov     [rsp+78h+lpMem], 0
0x180011160  mov     [rsp+78h+var_38], 0
0x180011169  mov     [rsp+78h+var_30], rax
0x18001116e  mov     [rsp+78h+var_28], 0
0x180011177  mov     [rsp+78h+var_20], 0
0x18001117f  lea     rax, [rsp+78h+var_58]
0x180011184  mov     [rsp+78h+var_18], rax
0x180011189  mov     [rsp+78h+var_10], 0
0x18001118e  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180011196  jz      short loc_1800111C3
0x180011198  mov     dl, 1
0x18001119a  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18001119f  mov     [rsp+78h+var_38], rax
0x1800111a4  test    rax, rax
0x1800111a7  jz      short loc_1800111C3
0x1800111a9  mov     rcx, [rax]
0x1800111ac  mov     [rsp+78h+var_28], rcx
0x1800111b1  lea     rcx, [rsp+78h+var_38]
0x1800111b6  mov     [rax], rcx
0x1800111b9  call    cs:__imp_GetCurrentThreadId
0x1800111bf  mov     [rsp+78h+var_20], eax
0x1800111c3  mov     rcx, rbx; hMem
0x1800111c6  call    cs:__imp_LocalSize
0x1800111cc  mov     rcx, rbx
0x1800111cf  test    rax, rax
0x1800111d2  jz      short loc_1800111E0
0x1800111d4  mov     byte ptr [rcx], 0
0x1800111d7  inc     rcx
0x1800111da  sub     rax, 1
0x1800111de  jnz     short loc_1800111D4
0x1800111e0  mov     rcx, rbx; hMem
0x1800111e3  call    cs:__imp_LocalFree
0x1800111e9  lea     rcx, [rsp+78h+var_38]; this
0x1800111ee  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800111f3  cmp     [rsp+78h+var_40], 0
0x1800111f8  jz      short loc_180011213
0x1800111fa  mov     rbx, [rsp+78h+lpMem]
0x1800111ff  call    cs:__imp_GetProcessHeap
0x180011205  mov     r8, rbx; lpMem
0x180011208  xor     edx, edx; dwFlags
0x18001120a  mov     rcx, rax; hHeap
0x18001120d  call    cs:__imp_HeapFree
0x180011213  xor     eax, eax
0x180011215  jmp     short loc_18001121E
0x180011217  mov     eax, [rsp+78h+arg_8]
0x18001121e  add     rsp, 70h
0x180011222  pop     rbx
0x180011223  retn
```
