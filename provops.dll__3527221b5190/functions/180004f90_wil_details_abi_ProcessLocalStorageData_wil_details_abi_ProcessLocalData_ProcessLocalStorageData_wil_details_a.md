# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)

- ea: `0x180004f90`
- end: `0x180005020`
- name: `??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `144`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800070e4`

## callees

- `0x180004f90`
- `0x1800051f0`
- `0x1800052c0`
- `0x18000864c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004fcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004fcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004fbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004fbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ff4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ff4`

## string_xrefs

- `0x18000500e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rdi
  __int64 *v3; // r14
  __int64 v4; // rbp
  __int64 v5; // rbx
  HANDLE ProcessHeap; // rax
  void *v7; // rcx
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = a1 + 5;
  v3 = a1 + 15;
  while ( v1 != v3 )
  {
    v4 = *v1;
    while ( v4 )
    {
      v5 = v4;
      v4 = *(_QWORD *)(v4 + 8);
      wil::details_abi::ThreadLocalData::~ThreadLocalData((wil::details_abi::ThreadLocalData *)(v5 + 16));
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v5);
    }
    *v1++ = 0;
  }
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(a1 + 2));
  v7 = (void *)a1[1];
  if ( v7 )
  {
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
  }
}

```

## disassembly

```asm
0x180004f90  push    rbx
0x180004f92  push    rbp
0x180004f93  push    rsi
0x180004f94  push    rdi
0x180004f95  push    r14
0x180004f97  sub     rsp, 20h
0x180004f9b  lea     rdi, [rcx+28h]
0x180004f9f  mov     rsi, rcx
0x180004fa2  lea     r14, [rdi+50h]
0x180004fa6  jmp     short loc_180004FDD
0x180004fa8  mov     rbp, [rdi]
0x180004fab  jmp     short loc_180004FD1
0x180004fad  mov     rbx, rbp
0x180004fb0  mov     rbp, [rbp+8]
0x180004fb4  lea     rcx, [rbx+10h]; this
0x180004fb8  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180004fbd  call    cs:__imp_GetProcessHeap
0x180004fc3  mov     r8, rbx; lpMem
0x180004fc6  xor     edx, edx; dwFlags
0x180004fc8  mov     rcx, rax; hHeap
0x180004fcb  call    cs:__imp_HeapFree
0x180004fd1  test    rbp, rbp
0x180004fd4  jnz     short loc_180004FAD
0x180004fd6  mov     [rdi], rbp
0x180004fd9  add     rdi, 8
0x180004fdd  cmp     rdi, r14
0x180004fe0  jnz     short loc_180004FA8
0x180004fe2  lea     rcx, [rsi+10h]; this
0x180004fe6  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180004feb  mov     rcx, [rsi+8]; hObject
0x180004fef  test    rcx, rcx
0x180004ff2  jz      short loc_180004FFE
0x180004ff4  call    cs:__imp_CloseHandle
0x180004ffa  test    eax, eax
0x180004ffc  jz      short loc_180005009
0x180004ffe  add     rsp, 20h
0x180005002  pop     r14
0x180005004  pop     rdi
0x180005005  pop     rsi
0x180005006  pop     rbp
0x180005007  pop     rbx
0x180005008  retn
0x180005009  mov     rcx, [rsp+48h]; this
0x18000500e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005015  mov     edx, 0A0Bh; void *
0x18000501a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
