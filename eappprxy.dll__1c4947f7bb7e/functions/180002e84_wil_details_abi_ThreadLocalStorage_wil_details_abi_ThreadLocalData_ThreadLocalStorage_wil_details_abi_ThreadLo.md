# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180002e84`
- end: `0x180002ee9`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004a44`

## callees

- `0x180002e84`
- `0x18000305c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002eae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002eae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ec2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ec2`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rbp
  __int64 *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = *v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = *(_QWORD *)(v3 + 8);
      wil::details_abi::ThreadLocalData::~ThreadLocalData((wil::details_abi::ThreadLocalData *)(v4 + 16));
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x180002e84  push    rbx
0x180002e86  push    rbp
0x180002e87  push    rsi
0x180002e88  push    rdi
0x180002e89  sub     rsp, 28h
0x180002e8d  lea     rbp, [rcx+50h]
0x180002e91  mov     rdi, rcx
0x180002e94  cmp     rcx, rbp
0x180002e97  jz      short loc_180002EDF
0x180002e99  mov     rsi, [rdi]
0x180002e9c  jmp     short loc_180002ECE
0x180002e9e  mov     rbx, rsi
0x180002ea1  mov     rsi, [rsi+8]
0x180002ea5  lea     rcx, [rbx+10h]; this
0x180002ea9  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180002eae  call    cs:__imp_GetProcessHeap
0x180002eb5  nop     dword ptr [rax+rax+00h]
0x180002eba  mov     r8, rbx; lpMem
0x180002ebd  xor     edx, edx; dwFlags
0x180002ebf  mov     rcx, rax; hHeap
0x180002ec2  call    cs:__imp_HeapFree
0x180002ec9  nop     dword ptr [rax+rax+00h]
0x180002ece  test    rsi, rsi
0x180002ed1  jnz     short loc_180002E9E
0x180002ed3  mov     [rdi], rsi
0x180002ed6  add     rdi, 8
0x180002eda  cmp     rdi, rbp
0x180002edd  jnz     short loc_180002E99
0x180002edf  add     rsp, 28h
0x180002ee3  pop     rdi
0x180002ee4  pop     rsi
0x180002ee5  pop     rbp
0x180002ee6  pop     rbx
0x180002ee7  retn
```
