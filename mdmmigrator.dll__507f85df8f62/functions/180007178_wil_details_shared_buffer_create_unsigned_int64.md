# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180007178`
- end: `0x18000723b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800065a4`
- `0x180007250`

## callees

- `0x180007178`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800071dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800071dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007207`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800071cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007207`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800071b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007215`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800071b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007215`

## pseudocode

```c
__int64 __fastcall wil::details::shared_buffer::create(volatile signed __int32 **this, volatile signed __int32 *a2)
{
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rbx
  HANDLE v6; // rax
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v9; // rsi
  volatile signed __int32 *v10; // rbx
  HANDLE v11; // rax

  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    result = (__int64)HeapAlloc(ProcessHeap, 0, (SIZE_T)(a2 + 1));
    v9 = (volatile signed __int32 *)result;
    if ( result )
    {
      *(_DWORD *)result = 0;
      if ( *this )
      {
        if ( _InterlockedExchangeAdd(*this, 0xFFFFFFFF) == 1 )
        {
          v10 = *this;
          v11 = GetProcessHeap();
          HeapFree(v11, 0, (LPVOID)v10);
        }
        this[1] = 0;
      }
      *this = v9;
      result = 1;
      this[1] = a2;
      _InterlockedAdd(v9, 1u);
    }
  }
  else
  {
    v4 = *this;
    if ( v4 )
    {
      if ( _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1 )
      {
        v5 = *this;
        v6 = GetProcessHeap();
        HeapFree(v6, 0, (LPVOID)v5);
      }
      *this = 0;
      this[1] = 0;
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180007178  push    rbx
0x18000717a  push    rbp
0x18000717b  push    rsi
0x18000717c  push    rdi
0x18000717d  sub     rsp, 28h
0x180007181  mov     rbp, rdx
0x180007184  mov     rdi, rcx
0x180007187  test    rdx, rdx
0x18000718a  jnz     short loc_1800071CD
0x18000718c  mov     rcx, [rcx]
0x18000718f  test    rcx, rcx
0x180007192  jz      short loc_1800071C6
0x180007194  or      eax, 0FFFFFFFFh
0x180007197  lock xadd [rcx], eax
0x18000719b  cmp     eax, 1
0x18000719e  jnz     short loc_1800071B7
0x1800071a0  mov     rbx, [rdi]
0x1800071a3  call    cs:__imp_GetProcessHeap
0x1800071a9  mov     r8, rbx; lpMem
0x1800071ac  xor     edx, edx; dwFlags
0x1800071ae  mov     rcx, rax; hHeap
0x1800071b1  call    cs:__imp_HeapFree
0x1800071b7  mov     qword ptr [rdi], 0
0x1800071be  mov     qword ptr [rdi+8], 0
0x1800071c6  mov     eax, 1
0x1800071cb  jmp     short loc_180007232
0x1800071cd  call    cs:__imp_GetProcessHeap
0x1800071d3  lea     r8, [rbp+4]; dwBytes
0x1800071d7  xor     edx, edx; dwFlags
0x1800071d9  mov     rcx, rax; hHeap
0x1800071dc  call    cs:__imp_HeapAlloc
0x1800071e2  mov     rsi, rax
0x1800071e5  test    rax, rax
0x1800071e8  jz      short loc_180007232
0x1800071ea  mov     dword ptr [rax], 0
0x1800071f0  mov     rcx, [rdi]
0x1800071f3  test    rcx, rcx
0x1800071f6  jz      short loc_180007223
0x1800071f8  or      eax, 0FFFFFFFFh
0x1800071fb  lock xadd [rcx], eax
0x1800071ff  cmp     eax, 1
0x180007202  jnz     short loc_18000721B
0x180007204  mov     rbx, [rdi]
0x180007207  call    cs:__imp_GetProcessHeap
0x18000720d  mov     r8, rbx; lpMem
0x180007210  xor     edx, edx; dwFlags
0x180007212  mov     rcx, rax; hHeap
0x180007215  call    cs:__imp_HeapFree
0x18000721b  mov     qword ptr [rdi+8], 0
0x180007223  mov     [rdi], rsi
0x180007226  mov     eax, 1
0x18000722b  mov     [rdi+8], rbp
0x18000722f  lock add [rsi], eax
0x180007232  add     rsp, 28h
0x180007236  pop     rdi
0x180007237  pop     rsi
0x180007238  pop     rbp
0x180007239  pop     rbx
0x18000723a  retn
```
