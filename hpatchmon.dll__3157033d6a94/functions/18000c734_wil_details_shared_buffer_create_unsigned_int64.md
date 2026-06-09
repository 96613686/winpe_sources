# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x18000c734`
- end: `0x18000c7f7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac64`
- `0x18000c8f0`

## callees

- `0x18000c734`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c76d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c7d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c76d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c7d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c798`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c798`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c75f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c789`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c75f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c789`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c7c3`

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
0x18000c734  push    rbx
0x18000c736  push    rbp
0x18000c737  push    rsi
0x18000c738  push    rdi
0x18000c739  sub     rsp, 28h
0x18000c73d  mov     rbp, rdx
0x18000c740  mov     rdi, rcx
0x18000c743  test    rdx, rdx
0x18000c746  jnz     short loc_18000C789
0x18000c748  mov     rcx, [rcx]
0x18000c74b  test    rcx, rcx
0x18000c74e  jz      short loc_18000C782
0x18000c750  or      eax, 0FFFFFFFFh
0x18000c753  lock xadd [rcx], eax
0x18000c757  cmp     eax, 1
0x18000c75a  jnz     short loc_18000C773
0x18000c75c  mov     rbx, [rdi]
0x18000c75f  call    cs:__imp_GetProcessHeap
0x18000c765  mov     r8, rbx; lpMem
0x18000c768  xor     edx, edx; dwFlags
0x18000c76a  mov     rcx, rax; hHeap
0x18000c76d  call    cs:__imp_HeapFree
0x18000c773  mov     qword ptr [rdi], 0
0x18000c77a  mov     qword ptr [rdi+8], 0
0x18000c782  mov     eax, 1
0x18000c787  jmp     short loc_18000C7EE
0x18000c789  call    cs:__imp_GetProcessHeap
0x18000c78f  lea     r8, [rbp+4]; dwBytes
0x18000c793  xor     edx, edx; dwFlags
0x18000c795  mov     rcx, rax; hHeap
0x18000c798  call    cs:__imp_HeapAlloc
0x18000c79e  mov     rsi, rax
0x18000c7a1  test    rax, rax
0x18000c7a4  jz      short loc_18000C7EE
0x18000c7a6  mov     dword ptr [rax], 0
0x18000c7ac  mov     rcx, [rdi]
0x18000c7af  test    rcx, rcx
0x18000c7b2  jz      short loc_18000C7DF
0x18000c7b4  or      eax, 0FFFFFFFFh
0x18000c7b7  lock xadd [rcx], eax
0x18000c7bb  cmp     eax, 1
0x18000c7be  jnz     short loc_18000C7D7
0x18000c7c0  mov     rbx, [rdi]
0x18000c7c3  call    cs:__imp_GetProcessHeap
0x18000c7c9  mov     r8, rbx; lpMem
0x18000c7cc  xor     edx, edx; dwFlags
0x18000c7ce  mov     rcx, rax; hHeap
0x18000c7d1  call    cs:__imp_HeapFree
0x18000c7d7  mov     qword ptr [rdi+8], 0
0x18000c7df  mov     [rdi], rsi
0x18000c7e2  mov     eax, 1
0x18000c7e7  mov     [rdi+8], rbp
0x18000c7eb  lock add [rsi], eax
0x18000c7ee  add     rsp, 28h
0x18000c7f2  pop     rdi
0x18000c7f3  pop     rsi
0x18000c7f4  pop     rbp
0x18000c7f5  pop     rbx
0x18000c7f6  retn
```
