# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180005848`
- end: `0x18000590b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ca0`
- `0x180005920`

## callees

- `0x180005848`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005881`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005881`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800058e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005873`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000589d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005873`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000589d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058d7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800058ac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800058ac`

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
0x180005848  push    rbx
0x18000584a  push    rbp
0x18000584b  push    rsi
0x18000584c  push    rdi
0x18000584d  sub     rsp, 28h
0x180005851  mov     rbp, rdx
0x180005854  mov     rdi, rcx
0x180005857  test    rdx, rdx
0x18000585a  jnz     short loc_18000589D
0x18000585c  mov     rcx, [rcx]
0x18000585f  test    rcx, rcx
0x180005862  jz      short loc_180005896
0x180005864  or      eax, 0FFFFFFFFh
0x180005867  lock xadd [rcx], eax
0x18000586b  cmp     eax, 1
0x18000586e  jnz     short loc_180005887
0x180005870  mov     rbx, [rdi]
0x180005873  call    cs:__imp_GetProcessHeap
0x180005879  mov     r8, rbx; lpMem
0x18000587c  xor     edx, edx; dwFlags
0x18000587e  mov     rcx, rax; hHeap
0x180005881  call    cs:__imp_HeapFree
0x180005887  mov     qword ptr [rdi], 0
0x18000588e  mov     qword ptr [rdi+8], 0
0x180005896  mov     eax, 1
0x18000589b  jmp     short loc_180005902
0x18000589d  call    cs:__imp_GetProcessHeap
0x1800058a3  lea     r8, [rbp+4]; dwBytes
0x1800058a7  xor     edx, edx; dwFlags
0x1800058a9  mov     rcx, rax; hHeap
0x1800058ac  call    cs:__imp_HeapAlloc
0x1800058b2  mov     rsi, rax
0x1800058b5  test    rax, rax
0x1800058b8  jz      short loc_180005902
0x1800058ba  mov     dword ptr [rax], 0
0x1800058c0  mov     rcx, [rdi]
0x1800058c3  test    rcx, rcx
0x1800058c6  jz      short loc_1800058F3
0x1800058c8  or      eax, 0FFFFFFFFh
0x1800058cb  lock xadd [rcx], eax
0x1800058cf  cmp     eax, 1
0x1800058d2  jnz     short loc_1800058EB
0x1800058d4  mov     rbx, [rdi]
0x1800058d7  call    cs:__imp_GetProcessHeap
0x1800058dd  mov     r8, rbx; lpMem
0x1800058e0  xor     edx, edx; dwFlags
0x1800058e2  mov     rcx, rax; hHeap
0x1800058e5  call    cs:__imp_HeapFree
0x1800058eb  mov     qword ptr [rdi+8], 0
0x1800058f3  mov     [rdi], rsi
0x1800058f6  mov     eax, 1
0x1800058fb  mov     [rdi+8], rbp
0x1800058ff  lock add [rsi], eax
0x180005902  add     rsp, 28h
0x180005906  pop     rdi
0x180005907  pop     rsi
0x180005908  pop     rbp
0x180005909  pop     rbx
0x18000590a  retn
```
