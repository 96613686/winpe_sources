# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x14000ba44`
- end: `0x14000bb07`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140009b78`
- `0x14000bc10`

## callees

- `0x14000ba44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ba6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ba99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bad3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ba6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ba99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bad3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ba7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bae1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ba7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bae1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000baa8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000baa8`

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
0x14000ba44  push    rbx
0x14000ba46  push    rbp
0x14000ba47  push    rsi
0x14000ba48  push    rdi
0x14000ba49  sub     rsp, 28h
0x14000ba4d  mov     rbp, rdx
0x14000ba50  mov     rdi, rcx
0x14000ba53  test    rdx, rdx
0x14000ba56  jnz     short loc_14000BA99
0x14000ba58  mov     rcx, [rcx]
0x14000ba5b  test    rcx, rcx
0x14000ba5e  jz      short loc_14000BA92
0x14000ba60  or      eax, 0FFFFFFFFh
0x14000ba63  lock xadd [rcx], eax
0x14000ba67  cmp     eax, 1
0x14000ba6a  jnz     short loc_14000BA83
0x14000ba6c  mov     rbx, [rdi]
0x14000ba6f  call    cs:__imp_GetProcessHeap
0x14000ba75  mov     r8, rbx; lpMem
0x14000ba78  xor     edx, edx; dwFlags
0x14000ba7a  mov     rcx, rax; hHeap
0x14000ba7d  call    cs:__imp_HeapFree
0x14000ba83  mov     qword ptr [rdi], 0
0x14000ba8a  mov     qword ptr [rdi+8], 0
0x14000ba92  mov     eax, 1
0x14000ba97  jmp     short loc_14000BAFE
0x14000ba99  call    cs:__imp_GetProcessHeap
0x14000ba9f  lea     r8, [rbp+4]; dwBytes
0x14000baa3  xor     edx, edx; dwFlags
0x14000baa5  mov     rcx, rax; hHeap
0x14000baa8  call    cs:__imp_HeapAlloc
0x14000baae  mov     rsi, rax
0x14000bab1  test    rax, rax
0x14000bab4  jz      short loc_14000BAFE
0x14000bab6  mov     dword ptr [rax], 0
0x14000babc  mov     rcx, [rdi]
0x14000babf  test    rcx, rcx
0x14000bac2  jz      short loc_14000BAEF
0x14000bac4  or      eax, 0FFFFFFFFh
0x14000bac7  lock xadd [rcx], eax
0x14000bacb  cmp     eax, 1
0x14000bace  jnz     short loc_14000BAE7
0x14000bad0  mov     rbx, [rdi]
0x14000bad3  call    cs:__imp_GetProcessHeap
0x14000bad9  mov     r8, rbx; lpMem
0x14000badc  xor     edx, edx; dwFlags
0x14000bade  mov     rcx, rax; hHeap
0x14000bae1  call    cs:__imp_HeapFree
0x14000bae7  mov     qword ptr [rdi+8], 0
0x14000baef  mov     [rdi], rsi
0x14000baf2  mov     eax, 1
0x14000baf7  mov     [rdi+8], rbp
0x14000bafb  lock add [rsi], eax
0x14000bafe  add     rsp, 28h
0x14000bb02  pop     rdi
0x14000bb03  pop     rsi
0x14000bb04  pop     rbp
0x14000bb05  pop     rbx
0x14000bb06  retn
```
