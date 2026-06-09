# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140011834`
- end: `0x14001190e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140011804`

## callees

- `0x140011834`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011881`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400118b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400118d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011881`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400118b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400118d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001188f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400118c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400118de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001188f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400118c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400118de`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        _QWORD *a1)
{
  _QWORD *v1; // r15
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  _QWORD *v4; // r13
  void *v5; // r12
  __int64 v6; // rbp
  __int64 v7; // r14
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  HANDLE v12; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v5 = v3;
      v3 = (_QWORD *)v3[1];
      v6 = v4[5];
      v7 = v6 + 80LL * *((unsigned __int16 *)v4 + 24);
      while ( v6 != v7 )
      {
        v8 = *(void **)(v6 + 64);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
        *(_QWORD *)(v6 + 64) = 0;
        *(_QWORD *)(v6 + 72) = 0;
        v6 += 80;
      }
      v10 = (void *)v4[5];
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
      *((_DWORD *)v4 + 12) = 0;
      v4[5] = 0;
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v5);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x140011834  push    rbx
0x140011836  push    rbp
0x140011837  push    rsi
0x140011838  push    rdi
0x140011839  push    r12
0x14001183b  push    r13
0x14001183d  push    r14
0x14001183f  push    r15
0x140011841  sub     rsp, 28h
0x140011845  lea     r15, [rcx+50h]
0x140011849  mov     rdi, rcx
0x14001184c  cmp     rcx, r15
0x14001184f  jz      loc_1400118FD
0x140011855  mov     rsi, [rdi]
0x140011858  jmp     loc_1400118E4
0x14001185d  mov     r13, rsi
0x140011860  mov     r12, rsi
0x140011863  mov     rsi, [rsi+8]
0x140011867  movzx   eax, word ptr [r13+30h]
0x14001186c  mov     rbp, [r13+28h]
0x140011870  lea     r14, [rax+rax*4]
0x140011874  shl     r14, 4
0x140011878  add     r14, rbp
0x14001187b  jmp     short loc_1400118A9
0x14001187d  mov     rbx, [rbp+40h]
0x140011881  call    cs:__imp_GetProcessHeap
0x140011887  mov     r8, rbx; lpMem
0x14001188a  xor     edx, edx; dwFlags
0x14001188c  mov     rcx, rax; hHeap
0x14001188f  call    cs:__imp_HeapFree
0x140011895  mov     qword ptr [rbp+40h], 0
0x14001189d  mov     qword ptr [rbp+48h], 0
0x1400118a5  add     rbp, 50h ; 'P'
0x1400118a9  cmp     rbp, r14
0x1400118ac  jnz     short loc_14001187D
0x1400118ae  mov     rbx, [r13+28h]
0x1400118b2  call    cs:__imp_GetProcessHeap
0x1400118b8  mov     r8, rbx; lpMem
0x1400118bb  xor     edx, edx; dwFlags
0x1400118bd  mov     rcx, rax; hHeap
0x1400118c0  call    cs:__imp_HeapFree
0x1400118c6  xor     eax, eax
0x1400118c8  mov     [r13+30h], eax
0x1400118cc  mov     [r13+28h], rax
0x1400118d0  call    cs:__imp_GetProcessHeap
0x1400118d6  mov     r8, r12; lpMem
0x1400118d9  xor     edx, edx; dwFlags
0x1400118db  mov     rcx, rax; hHeap
0x1400118de  call    cs:__imp_HeapFree
0x1400118e4  test    rsi, rsi
0x1400118e7  jnz     loc_14001185D
0x1400118ed  mov     [rdi], rsi
0x1400118f0  add     rdi, 8
0x1400118f4  cmp     rdi, r15
0x1400118f7  jnz     loc_140011855
0x1400118fd  add     rsp, 28h
0x140011901  pop     r15
0x140011903  pop     r14
0x140011905  pop     r13
0x140011907  pop     r12
0x140011909  pop     rdi
0x14001190a  pop     rsi
0x14001190b  pop     rbp
0x14001190c  pop     rbx
0x14001190d  retn
```
