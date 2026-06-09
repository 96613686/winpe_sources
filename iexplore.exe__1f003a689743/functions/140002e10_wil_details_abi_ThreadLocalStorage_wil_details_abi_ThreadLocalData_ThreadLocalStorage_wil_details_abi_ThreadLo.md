# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140002e10`
- end: `0x140002eea`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002d88`

## callees

- `0x140002e10`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140002e5d`
- `KERNEL32!GetProcessHeap` at `0x140002e8e`
- `KERNEL32!GetProcessHeap` at `0x140002eac`
- `KERNEL32!GetProcessHeap` at `0x140002e5d`
- `KERNEL32!GetProcessHeap` at `0x140002e8e`
- `KERNEL32!GetProcessHeap` at `0x140002eac`
- `KERNEL32!HeapFree` at `0x140002e6b`
- `KERNEL32!HeapFree` at `0x140002e9c`
- `KERNEL32!HeapFree` at `0x140002eba`
- `KERNEL32!HeapFree` at `0x140002e6b`
- `KERNEL32!HeapFree` at `0x140002e9c`
- `KERNEL32!HeapFree` at `0x140002eba`

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
0x140002e10  push    rbx
0x140002e12  push    rbp
0x140002e13  push    rsi
0x140002e14  push    rdi
0x140002e15  push    r12
0x140002e17  push    r13
0x140002e19  push    r14
0x140002e1b  push    r15
0x140002e1d  sub     rsp, 28h
0x140002e21  lea     r15, [rcx+50h]
0x140002e25  mov     rdi, rcx
0x140002e28  cmp     rcx, r15
0x140002e2b  jz      loc_140002ED9
0x140002e31  mov     rsi, [rdi]
0x140002e34  jmp     loc_140002EC0
0x140002e39  mov     r13, rsi
0x140002e3c  mov     r12, rsi
0x140002e3f  mov     rsi, [rsi+8]
0x140002e43  movzx   eax, word ptr [r13+30h]
0x140002e48  mov     rbp, [r13+28h]
0x140002e4c  lea     r14, [rax+rax*4]
0x140002e50  shl     r14, 4
0x140002e54  add     r14, rbp
0x140002e57  jmp     short loc_140002E85
0x140002e59  mov     rbx, [rbp+40h]
0x140002e5d  call    cs:__imp_GetProcessHeap
0x140002e63  mov     r8, rbx; lpMem
0x140002e66  xor     edx, edx; dwFlags
0x140002e68  mov     rcx, rax; hHeap
0x140002e6b  call    cs:__imp_HeapFree
0x140002e71  mov     qword ptr [rbp+40h], 0
0x140002e79  mov     qword ptr [rbp+48h], 0
0x140002e81  add     rbp, 50h ; 'P'
0x140002e85  cmp     rbp, r14
0x140002e88  jnz     short loc_140002E59
0x140002e8a  mov     rbx, [r13+28h]
0x140002e8e  call    cs:__imp_GetProcessHeap
0x140002e94  mov     r8, rbx; lpMem
0x140002e97  xor     edx, edx; dwFlags
0x140002e99  mov     rcx, rax; hHeap
0x140002e9c  call    cs:__imp_HeapFree
0x140002ea2  xor     eax, eax
0x140002ea4  mov     [r13+30h], eax
0x140002ea8  mov     [r13+28h], rax
0x140002eac  call    cs:__imp_GetProcessHeap
0x140002eb2  mov     r8, r12; lpMem
0x140002eb5  xor     edx, edx; dwFlags
0x140002eb7  mov     rcx, rax; hHeap
0x140002eba  call    cs:__imp_HeapFree
0x140002ec0  test    rsi, rsi
0x140002ec3  jnz     loc_140002E39
0x140002ec9  mov     [rdi], rsi
0x140002ecc  add     rdi, 8
0x140002ed0  cmp     rdi, r15
0x140002ed3  jnz     loc_140002E31
0x140002ed9  add     rsp, 28h
0x140002edd  pop     r15
0x140002edf  pop     r14
0x140002ee1  pop     r13
0x140002ee3  pop     r12
0x140002ee5  pop     rdi
0x140002ee6  pop     rsi
0x140002ee7  pop     rbp
0x140002ee8  pop     rbx
0x140002ee9  retn
```
