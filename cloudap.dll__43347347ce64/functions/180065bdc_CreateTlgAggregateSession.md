# CreateTlgAggregateSession

- ea: `0x180065bdc`
- end: `0x180065c99`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180066214`

## callees

- `0x180065bdc`
- `0x180065ca0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180065c24`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180065c24`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180065c0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180065c0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065bf6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065bf6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180065c46`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180065c46`

## pseudocode

```c
RTL_SRWLOCK *__fastcall CreateTlgAggregateSession(char a1)
{
  char v2; // di
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 8u, 0x168u);
  v5 = v4;
  if ( v4 )
  {
    InitializeSRWLock(v4 + 33);
    if ( !a1 || !dword_18009AFA8 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
      v2 = 1;
  }
  if ( !v2 )
  {
    DestroyAggregateSession(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180065bdc  mov     [rsp+arg_0], rbx
0x180065be1  mov     [rsp+arg_18], rsi
0x180065be6  push    rdi
0x180065be7  sub     rsp, 20h
0x180065beb  mov     sil, cl
0x180065bee  xor     dil, dil
0x180065bf1  mov     [rsp+28h+arg_8], dil
0x180065bf6  call    cs:__imp_GetProcessHeap
0x180065bfc  mov     rcx, rax; hHeap
0x180065bff  mov     edx, 8; dwFlags
0x180065c04  mov     r8d, 168h; dwBytes
0x180065c0a  call    cs:__imp_HeapAlloc
0x180065c10  mov     rbx, rax
0x180065c13  mov     [rsp+28h+arg_10], rax
0x180065c18  test    rax, rax
0x180065c1b  jz      short loc_180065C77
0x180065c1d  lea     rcx, [rax+108h]; SRWLock
0x180065c24  call    cs:__imp_InitializeSRWLock
0x180065c2a  test    sil, sil
0x180065c2d  jz      short loc_180065C74
0x180065c2f  mov     ecx, cs:dword_18009AFA8
0x180065c35  test    ecx, ecx
0x180065c37  jnz     short loc_180065C77
0x180065c39  xor     r8d, r8d; pcbe
0x180065c3c  mov     rdx, rbx; pv
0x180065c3f  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180065c46  call    cs:__imp_CreateThreadpoolTimer
0x180065c4c  mov     [rbx+158h], rax
0x180065c53  jmp     short loc_180065C6A
0x180065c55  mov     eax, 1
0x180065c5a  xchg    eax, cs:dword_18009AFA8
0x180065c60  mov     dil, [rsp+28h+arg_8]
0x180065c65  mov     rbx, [rsp+28h+arg_10]
0x180065c6a  cmp     qword ptr [rbx+158h], 0
0x180065c72  jz      short loc_180065C77
0x180065c74  mov     dil, 1
0x180065c77  test    dil, dil
0x180065c7a  jnz     short loc_180065C86
0x180065c7c  mov     rcx, rbx; lpMem
0x180065c7f  call    DestroyAggregateSession
0x180065c84  xor     ebx, ebx
0x180065c86  mov     rax, rbx
0x180065c89  mov     rbx, [rsp+28h+arg_0]
0x180065c8e  mov     rsi, [rsp+28h+arg_18]
0x180065c93  add     rsp, 20h
0x180065c97  pop     rdi
0x180065c98  retn
0x18007fc1e  push    rbp
0x18007fc20  sub     rsp, 20h
0x18007fc24  mov     rbp, rdx
0x18007fc27  mov     rax, [rcx]
0x18007fc2a  xor     ecx, ecx
0x18007fc2c  cmp     dword ptr [rax], 0C000000Dh
0x18007fc32  setz    cl
0x18007fc35  mov     eax, ecx
0x18007fc37  add     rsp, 20h
0x18007fc3b  pop     rbp
0x18007fc3c  retn
```
