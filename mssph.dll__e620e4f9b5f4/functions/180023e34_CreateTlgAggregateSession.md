# CreateTlgAggregateSession

- ea: `0x180023e34`
- end: `0x180023ef1`
- name: `CreateTlgAggregateSession`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180024a58`

## callees

- `0x180023e34`
- `0x180023ef8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180023e7c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180023e7c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023e62`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023e62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023e4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023e4e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180023e9e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180023e9e`

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
    if ( !a1 || !dword_180036600 && (v5[43].Ptr = CreateThreadpoolTimer(FlushTimerCallbackUserMode, v5, 0)) != 0 )
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
0x180023e34  mov     [rsp+arg_0], rbx
0x180023e39  mov     [rsp+arg_18], rsi
0x180023e3e  push    rdi
0x180023e3f  sub     rsp, 20h
0x180023e43  mov     sil, cl
0x180023e46  xor     dil, dil
0x180023e49  mov     [rsp+28h+arg_8], dil
0x180023e4e  call    cs:__imp_GetProcessHeap
0x180023e54  mov     rcx, rax; hHeap
0x180023e57  mov     edx, 8; dwFlags
0x180023e5c  mov     r8d, 168h; dwBytes
0x180023e62  call    cs:__imp_HeapAlloc
0x180023e68  mov     rbx, rax
0x180023e6b  mov     [rsp+28h+arg_10], rax
0x180023e70  test    rax, rax
0x180023e73  jz      short loc_180023ECF
0x180023e75  lea     rcx, [rax+108h]; SRWLock
0x180023e7c  call    cs:__imp_InitializeSRWLock
0x180023e82  test    sil, sil
0x180023e85  jz      short loc_180023ECC
0x180023e87  mov     ecx, cs:dword_180036600
0x180023e8d  test    ecx, ecx
0x180023e8f  jnz     short loc_180023ECF
0x180023e91  xor     r8d, r8d; pcbe
0x180023e94  mov     rdx, rbx; pv
0x180023e97  lea     rcx, FlushTimerCallbackUserMode; pfnti
0x180023e9e  call    cs:__imp_CreateThreadpoolTimer
0x180023ea4  mov     [rbx+158h], rax
0x180023eab  jmp     short loc_180023EC2
0x180023ead  mov     eax, 1
0x180023eb2  xchg    eax, cs:dword_180036600
0x180023eb8  mov     dil, [rsp+28h+arg_8]
0x180023ebd  mov     rbx, [rsp+28h+arg_10]
0x180023ec2  cmp     qword ptr [rbx+158h], 0
0x180023eca  jz      short loc_180023ECF
0x180023ecc  mov     dil, 1
0x180023ecf  test    dil, dil
0x180023ed2  jnz     short loc_180023EDE
0x180023ed4  mov     rcx, rbx; lpMem
0x180023ed7  call    DestroyAggregateSession
0x180023edc  xor     ebx, ebx
0x180023ede  mov     rax, rbx
0x180023ee1  mov     rbx, [rsp+28h+arg_0]
0x180023ee6  mov     rsi, [rsp+28h+arg_18]
0x180023eeb  add     rsp, 20h
0x180023eef  pop     rdi
0x180023ef0  retn
0x180026b86  push    rbp
0x180026b88  sub     rsp, 20h
0x180026b8c  mov     rbp, rdx
0x180026b8f  mov     rax, [rcx]
0x180026b92  xor     ecx, ecx
0x180026b94  cmp     dword ptr [rax], 0C000000Dh
0x180026b9a  setz    cl
0x180026b9d  mov     eax, ecx
0x180026b9f  add     rsp, 20h
0x180026ba3  pop     rbp
0x180026ba4  retn
```
