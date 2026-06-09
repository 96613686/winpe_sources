# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x18001c468`
- end: `0x18001c522`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `186`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001bf80`

## callees

- `0x18001c468`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c4a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c4de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c4a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c4de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c4ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c4f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c4ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c4f2`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v1; // rdi
  __int64 v3; // rsi
  __int64 v4; // rdi
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  void *v7; // rbx
  HANDLE v8; // rax

  v1 = *((_QWORD *)this + 3);
  v3 = v1 + 80LL * *((unsigned __int16 *)this + 16);
  if ( v1 != v3 )
  {
    v4 = v1 + 64;
    do
    {
      v5 = *(void **)v4;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      *(_QWORD *)v4 = 0;
      *(_QWORD *)(v4 + 8) = 0;
      v4 += 80;
    }
    while ( v4 - 64 != v3 );
  }
  v7 = (void *)*((_QWORD *)this + 3);
  v8 = GetProcessHeap();
  HeapFree(v8, 0, v7);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x18001c468  mov     rax, rsp
0x18001c46b  mov     [rax+8], rbx
0x18001c46f  mov     [rax+10h], rbp
0x18001c473  mov     [rax+18h], rsi
0x18001c477  mov     [rax+20h], rdi
0x18001c47b  push    r14
0x18001c47d  sub     rsp, 20h
0x18001c481  mov     rdi, [rcx+18h]
0x18001c485  xor     r14d, r14d
0x18001c488  movzx   eax, word ptr [rcx+20h]
0x18001c48c  mov     rbp, rcx
0x18001c48f  lea     rsi, [rax+rax*4]
0x18001c493  shl     rsi, 4
0x18001c497  add     rsi, rdi
0x18001c49a  cmp     rdi, rsi
0x18001c49d  jz      short loc_18001C4DA
0x18001c49f  add     rdi, 40h ; '@'
0x18001c4a3  mov     rbx, [rdi]
0x18001c4a6  call    cs:__imp_GetProcessHeap
0x18001c4ad  nop     dword ptr [rax+rax+00h]
0x18001c4b2  mov     r8, rbx; lpMem
0x18001c4b5  xor     edx, edx; dwFlags
0x18001c4b7  mov     rcx, rax; hHeap
0x18001c4ba  call    cs:__imp_HeapFree
0x18001c4c1  nop     dword ptr [rax+rax+00h]
0x18001c4c6  mov     [rdi], r14
0x18001c4c9  mov     [rdi+8], r14
0x18001c4cd  lea     rdi, [rdi+50h]
0x18001c4d1  lea     rax, [rdi-40h]
0x18001c4d5  cmp     rax, rsi
0x18001c4d8  jnz     short loc_18001C4A3
0x18001c4da  mov     rbx, [rbp+18h]
0x18001c4de  call    cs:__imp_GetProcessHeap
0x18001c4e5  nop     dword ptr [rax+rax+00h]
0x18001c4ea  mov     r8, rbx; lpMem
0x18001c4ed  xor     edx, edx; dwFlags
0x18001c4ef  mov     rcx, rax; hHeap
0x18001c4f2  call    cs:__imp_HeapFree
0x18001c4f9  nop     dword ptr [rax+rax+00h]
0x18001c4fe  mov     rbx, [rsp+28h+arg_0]
0x18001c503  mov     rsi, [rsp+28h+arg_10]
0x18001c508  mov     rdi, [rsp+28h+arg_18]
0x18001c50d  mov     [rbp+20h], r14d
0x18001c511  mov     [rbp+18h], r14
0x18001c515  mov     rbp, [rsp+28h+arg_8]
0x18001c51a  add     rsp, 20h
0x18001c51e  pop     r14
0x18001c520  retn
```
