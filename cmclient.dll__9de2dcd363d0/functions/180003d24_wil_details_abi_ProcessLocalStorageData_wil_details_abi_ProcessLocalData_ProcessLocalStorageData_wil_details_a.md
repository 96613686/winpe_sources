# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)

- ea: `0x180003d24`
- end: `0x180003db4`
- name: `??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006514`

## callees

- `0x180003d24`
- `0x180003ee4`
- `0x180003f4c`
- `0x18000700c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d88`

## string_xrefs

- `0x180003da2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
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
0x180003d24  push    rbx
0x180003d26  push    rbp
0x180003d27  push    rsi
0x180003d28  push    rdi
0x180003d29  push    r14
0x180003d2b  sub     rsp, 20h
0x180003d2f  lea     rdi, [rcx+28h]
0x180003d33  mov     rsi, rcx
0x180003d36  lea     r14, [rdi+50h]
0x180003d3a  jmp     short loc_180003D71
0x180003d3c  mov     rbp, [rdi]
0x180003d3f  jmp     short loc_180003D65
0x180003d41  mov     rbx, rbp
0x180003d44  mov     rbp, [rbp+8]
0x180003d48  lea     rcx, [rbx+10h]; this
0x180003d4c  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180003d51  call    cs:__imp_GetProcessHeap
0x180003d57  mov     r8, rbx; lpMem
0x180003d5a  xor     edx, edx; dwFlags
0x180003d5c  mov     rcx, rax; hHeap
0x180003d5f  call    cs:__imp_HeapFree
0x180003d65  test    rbp, rbp
0x180003d68  jnz     short loc_180003D41
0x180003d6a  mov     [rdi], rbp
0x180003d6d  add     rdi, 8
0x180003d71  cmp     rdi, r14
0x180003d74  jnz     short loc_180003D3C
0x180003d76  lea     rcx, [rsi+10h]; this
0x180003d7a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180003d7f  mov     rcx, [rsi+8]; hObject
0x180003d83  test    rcx, rcx
0x180003d86  jz      short loc_180003D92
0x180003d88  call    cs:__imp_CloseHandle
0x180003d8e  test    eax, eax
0x180003d90  jz      short loc_180003D9D
0x180003d92  add     rsp, 20h
0x180003d96  pop     r14
0x180003d98  pop     rdi
0x180003d99  pop     rsi
0x180003d9a  pop     rbp
0x180003d9b  pop     rbx
0x180003d9c  retn
0x180003d9d  mov     rcx, [rsp+48h]; this
0x180003da2  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003da9  mov     edx, 0A0Bh; void *
0x180003dae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
