# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)

- ea: `0x140002b08`
- end: `0x140002b98`
- name: `??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000473c`

## callees

- `0x140002b08`
- `0x140002c44`
- `0x140002d14`
- `0x1400057ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002b43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002b43`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002b35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002b35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002b6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002b6c`

## string_xrefs

- `0x140002b86`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x140002b08  push    rbx
0x140002b0a  push    rbp
0x140002b0b  push    rsi
0x140002b0c  push    rdi
0x140002b0d  push    r14
0x140002b0f  sub     rsp, 20h
0x140002b13  lea     rdi, [rcx+28h]
0x140002b17  mov     rsi, rcx
0x140002b1a  lea     r14, [rdi+50h]
0x140002b1e  jmp     short loc_140002B55
0x140002b20  mov     rbp, [rdi]
0x140002b23  jmp     short loc_140002B49
0x140002b25  mov     rbx, rbp
0x140002b28  mov     rbp, [rbp+8]
0x140002b2c  lea     rcx, [rbx+10h]; this
0x140002b30  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x140002b35  call    cs:__imp_GetProcessHeap
0x140002b3b  mov     r8, rbx; lpMem
0x140002b3e  xor     edx, edx; dwFlags
0x140002b40  mov     rcx, rax; hHeap
0x140002b43  call    cs:__imp_HeapFree
0x140002b49  test    rbp, rbp
0x140002b4c  jnz     short loc_140002B25
0x140002b4e  mov     [rdi], rbp
0x140002b51  add     rdi, 8
0x140002b55  cmp     rdi, r14
0x140002b58  jnz     short loc_140002B20
0x140002b5a  lea     rcx, [rsi+10h]; this
0x140002b5e  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140002b63  mov     rcx, [rsi+8]; hObject
0x140002b67  test    rcx, rcx
0x140002b6a  jz      short loc_140002B76
0x140002b6c  call    cs:__imp_CloseHandle
0x140002b72  test    eax, eax
0x140002b74  jz      short loc_140002B81
0x140002b76  add     rsp, 20h
0x140002b7a  pop     r14
0x140002b7c  pop     rdi
0x140002b7d  pop     rsi
0x140002b7e  pop     rbp
0x140002b7f  pop     rbx
0x140002b80  retn
0x140002b81  mov     rcx, [rsp+48h]; this
0x140002b86  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140002b8d  mov     edx, 0A0Bh; void *
0x140002b92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
