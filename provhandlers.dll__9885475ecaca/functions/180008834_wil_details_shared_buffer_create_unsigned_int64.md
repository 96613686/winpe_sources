# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180008834`
- end: `0x1800088f7`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007794`
- `0x180008ae0`

## callees

- `0x180008834`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008898`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008898`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000885f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008889`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000885f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008889`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000886d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000886d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088d1`

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
0x180008834  push    rbx
0x180008836  push    rbp
0x180008837  push    rsi
0x180008838  push    rdi
0x180008839  sub     rsp, 28h
0x18000883d  mov     rbp, rdx
0x180008840  mov     rdi, rcx
0x180008843  test    rdx, rdx
0x180008846  jnz     short loc_180008889
0x180008848  mov     rcx, [rcx]
0x18000884b  test    rcx, rcx
0x18000884e  jz      short loc_180008882
0x180008850  or      eax, 0FFFFFFFFh
0x180008853  lock xadd [rcx], eax
0x180008857  cmp     eax, 1
0x18000885a  jnz     short loc_180008873
0x18000885c  mov     rbx, [rdi]
0x18000885f  call    cs:__imp_GetProcessHeap
0x180008865  mov     r8, rbx; lpMem
0x180008868  xor     edx, edx; dwFlags
0x18000886a  mov     rcx, rax; hHeap
0x18000886d  call    cs:__imp_HeapFree
0x180008873  mov     qword ptr [rdi], 0
0x18000887a  mov     qword ptr [rdi+8], 0
0x180008882  mov     eax, 1
0x180008887  jmp     short loc_1800088EE
0x180008889  call    cs:__imp_GetProcessHeap
0x18000888f  lea     r8, [rbp+4]; dwBytes
0x180008893  xor     edx, edx; dwFlags
0x180008895  mov     rcx, rax; hHeap
0x180008898  call    cs:__imp_HeapAlloc
0x18000889e  mov     rsi, rax
0x1800088a1  test    rax, rax
0x1800088a4  jz      short loc_1800088EE
0x1800088a6  mov     dword ptr [rax], 0
0x1800088ac  mov     rcx, [rdi]
0x1800088af  test    rcx, rcx
0x1800088b2  jz      short loc_1800088DF
0x1800088b4  or      eax, 0FFFFFFFFh
0x1800088b7  lock xadd [rcx], eax
0x1800088bb  cmp     eax, 1
0x1800088be  jnz     short loc_1800088D7
0x1800088c0  mov     rbx, [rdi]
0x1800088c3  call    cs:__imp_GetProcessHeap
0x1800088c9  mov     r8, rbx; lpMem
0x1800088cc  xor     edx, edx; dwFlags
0x1800088ce  mov     rcx, rax; hHeap
0x1800088d1  call    cs:__imp_HeapFree
0x1800088d7  mov     qword ptr [rdi+8], 0
0x1800088df  mov     [rdi], rsi
0x1800088e2  mov     eax, 1
0x1800088e7  mov     [rdi+8], rbp
0x1800088eb  lock add [rsi], eax
0x1800088ee  add     rsp, 28h
0x1800088f2  pop     rdi
0x1800088f3  pop     rsi
0x1800088f4  pop     rbp
0x1800088f5  pop     rbx
0x1800088f6  retn
```
