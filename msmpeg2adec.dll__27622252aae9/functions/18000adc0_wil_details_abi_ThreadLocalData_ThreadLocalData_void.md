# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x18000adc0`
- end: `0x18000ae5d`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `157`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a8f0`

## callees

- `0x18000adc0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000adf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000adf4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae29`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v1; // rdi
  __int64 i; // rsi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v1 = *((_QWORD *)this + 3);
  for ( i = v1 + 80LL * *((unsigned __int16 *)this + 16); v1 != i; v1 += 80 )
  {
    v4 = *(void **)(v1 + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(v1 + 64) = 0;
    *(_QWORD *)(v1 + 72) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x18000adc0  push    rbx
0x18000adc2  push    rbp
0x18000adc3  push    rsi
0x18000adc4  push    rdi
0x18000adc5  push    r14
0x18000adc7  sub     rsp, 20h
0x18000adcb  mov     rdi, [rcx+18h]
0x18000adcf  xor     r14d, r14d
0x18000add2  movzx   eax, word ptr [rcx+20h]
0x18000add6  mov     rbp, rcx
0x18000add9  lea     rsi, [rax+rax*4]
0x18000addd  shl     rsi, 4
0x18000ade1  add     rsi, rdi
0x18000ade4  cmp     rdi, rsi
0x18000ade7  jz      short loc_18000AE25
0x18000ade9  nop     dword ptr [rax+00000000h]
0x18000adf0  mov     rbx, [rdi+40h]
0x18000adf4  call    cs:__imp_GetProcessHeap
0x18000adfb  nop     dword ptr [rax+rax+00h]
0x18000ae00  mov     r8, rbx; lpMem
0x18000ae03  xor     edx, edx; dwFlags
0x18000ae05  mov     rcx, rax; hHeap
0x18000ae08  call    cs:__imp_HeapFree
0x18000ae0f  nop     dword ptr [rax+rax+00h]
0x18000ae14  mov     [rdi+40h], r14
0x18000ae18  mov     [rdi+48h], r14
0x18000ae1c  add     rdi, 50h ; 'P'
0x18000ae20  cmp     rdi, rsi
0x18000ae23  jnz     short loc_18000ADF0
0x18000ae25  mov     rbx, [rbp+18h]
0x18000ae29  call    cs:__imp_GetProcessHeap
0x18000ae30  nop     dword ptr [rax+rax+00h]
0x18000ae35  mov     r8, rbx; lpMem
0x18000ae38  xor     edx, edx; dwFlags
0x18000ae3a  mov     rcx, rax; hHeap
0x18000ae3d  call    cs:__imp_HeapFree
0x18000ae44  nop     dword ptr [rax+rax+00h]
0x18000ae49  mov     [rbp+20h], r14d
0x18000ae4d  mov     [rbp+18h], r14
0x18000ae51  add     rsp, 20h
0x18000ae55  pop     r14
0x18000ae57  pop     rdi
0x18000ae58  pop     rsi
0x18000ae59  pop     rbp
0x18000ae5a  pop     rbx
0x18000ae5b  retn
```
