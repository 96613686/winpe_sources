# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)

- ea: `0x140002968`
- end: `0x140002a2e`
- name: `??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400042ac`

## callees

- `0x140002968`
- `0x140002a34`
- `0x140004c0c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400029c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400029d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400029e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400029c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400029d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400029e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400029a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400029a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002995`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002995`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(
        _QWORD *a1)
{
  __int64 *v1; // rdi
  __int64 *v3; // r14
  __int64 v4; // rbp
  __int64 v5; // rbx
  HANDLE ProcessHeap; // rax
  void *v7; // rcx
  __int64 v8; // r8
  const char *v9; // r9
  void *v10; // rcx
  __int64 v11; // r8
  const char *v12; // r9
  void *v13; // rcx
  __int64 v14; // r8
  const char *v15; // r9
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
  v7 = (void *)a1[3];
  if ( v7 && !CloseHandle(v7) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
  v10 = (void *)a1[2];
  if ( v10 && !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v11, v12);
  v13 = (void *)a1[1];
  if ( v13 )
  {
    if ( !CloseHandle(v13) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
  }
}

```

## disassembly

```asm
0x140002968  push    rbx
0x14000296a  push    rbp
0x14000296b  push    rsi
0x14000296c  push    rdi
0x14000296d  push    r14
0x14000296f  sub     rsp, 20h
0x140002973  lea     rdi, [rcx+28h]
0x140002977  mov     rsi, rcx
0x14000297a  lea     r14, [rdi+50h]
0x14000297e  jmp     short loc_1400029B5
0x140002980  mov     rbp, [rdi]
0x140002983  jmp     short loc_1400029A9
0x140002985  mov     rbx, rbp
0x140002988  mov     rbp, [rbp+8]
0x14000298c  lea     rcx, [rbx+10h]; this
0x140002990  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x140002995  call    cs:__imp_GetProcessHeap
0x14000299b  mov     r8, rbx; lpMem
0x14000299e  xor     edx, edx; dwFlags
0x1400029a0  mov     rcx, rax; hHeap
0x1400029a3  call    cs:__imp_HeapFree
0x1400029a9  test    rbp, rbp
0x1400029ac  jnz     short loc_140002985
0x1400029ae  mov     [rdi], rbp
0x1400029b1  add     rdi, 8
0x1400029b5  cmp     rdi, r14
0x1400029b8  jnz     short loc_140002980
0x1400029ba  mov     rcx, [rsi+18h]; hObject
0x1400029be  test    rcx, rcx
0x1400029c1  jz      short loc_1400029CD
0x1400029c3  call    cs:__imp_CloseHandle
0x1400029c9  test    eax, eax
0x1400029cb  jz      short loc_140002A0E
0x1400029cd  mov     rcx, [rsi+10h]; hObject
0x1400029d1  test    rcx, rcx
0x1400029d4  jz      short loc_1400029E0
0x1400029d6  call    cs:__imp_CloseHandle
0x1400029dc  test    eax, eax
0x1400029de  jz      short loc_140002A1E
0x1400029e0  mov     rcx, [rsi+8]; hObject
0x1400029e4  test    rcx, rcx
0x1400029e7  jz      short loc_1400029F3
0x1400029e9  call    cs:__imp_CloseHandle
0x1400029ef  test    eax, eax
0x1400029f1  jz      short loc_1400029FE
0x1400029f3  add     rsp, 20h
0x1400029f7  pop     r14
0x1400029f9  pop     rdi
0x1400029fa  pop     rsi
0x1400029fb  pop     rbp
0x1400029fc  pop     rbx
0x1400029fd  retn
0x1400029fe  mov     rcx, [rsp+48h]; this
0x140002a03  mov     edx, 0A0Bh; void *
0x140002a08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002a0e  mov     rcx, [rsp+48h]; this
0x140002a13  mov     edx, 0A0Bh; void *
0x140002a18  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140002a1e  mov     rcx, [rsp+48h]; this
0x140002a23  mov     edx, 0A0Bh; void *
0x140002a28  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
