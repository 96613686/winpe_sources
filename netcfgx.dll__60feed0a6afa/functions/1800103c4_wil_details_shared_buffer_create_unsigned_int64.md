# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800103c4`
- end: `0x180010487`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f1e0`
- `0x180010490`

## callees

- `0x1800103c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010428`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010428`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800103fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010461`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800103fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010461`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010419`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010453`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800103ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010419`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010453`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
      this[1] = a2;
      result = 1;
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
0x1800103c4  push    rbx
0x1800103c6  push    rbp
0x1800103c7  push    rsi
0x1800103c8  push    rdi
0x1800103c9  sub     rsp, 28h
0x1800103cd  mov     rbp, rdx
0x1800103d0  mov     rdi, rcx
0x1800103d3  test    rdx, rdx
0x1800103d6  jnz     short loc_180010419
0x1800103d8  mov     rcx, [rcx]
0x1800103db  test    rcx, rcx
0x1800103de  jz      short loc_180010412
0x1800103e0  or      eax, 0FFFFFFFFh
0x1800103e3  lock xadd [rcx], eax
0x1800103e7  cmp     eax, 1
0x1800103ea  jnz     short loc_180010403
0x1800103ec  mov     rbx, [rdi]
0x1800103ef  call    cs:__imp_GetProcessHeap
0x1800103f5  mov     r8, rbx; lpMem
0x1800103f8  xor     edx, edx; dwFlags
0x1800103fa  mov     rcx, rax; hHeap
0x1800103fd  call    cs:__imp_HeapFree
0x180010403  mov     qword ptr [rdi], 0
0x18001040a  mov     qword ptr [rdi+8], 0
0x180010412  mov     eax, 1
0x180010417  jmp     short loc_18001047E
0x180010419  call    cs:__imp_GetProcessHeap
0x18001041f  mov     rcx, rax; hHeap
0x180010422  lea     r8, [rbp+4]; dwBytes
0x180010426  xor     edx, edx; dwFlags
0x180010428  call    cs:__imp_HeapAlloc
0x18001042e  mov     rsi, rax
0x180010431  test    rax, rax
0x180010434  jz      short loc_18001047E
0x180010436  mov     dword ptr [rax], 0
0x18001043c  mov     rcx, [rdi]
0x18001043f  test    rcx, rcx
0x180010442  jz      short loc_18001046F
0x180010444  or      eax, 0FFFFFFFFh
0x180010447  lock xadd [rcx], eax
0x18001044b  cmp     eax, 1
0x18001044e  jnz     short loc_180010467
0x180010450  mov     rbx, [rdi]
0x180010453  call    cs:__imp_GetProcessHeap
0x180010459  mov     r8, rbx; lpMem
0x18001045c  xor     edx, edx; dwFlags
0x18001045e  mov     rcx, rax; hHeap
0x180010461  call    cs:__imp_HeapFree
0x180010467  mov     qword ptr [rdi+8], 0
0x18001046f  mov     [rdi], rsi
0x180010472  mov     [rdi+8], rbp
0x180010476  mov     eax, 1
0x18001047b  lock add [rsi], eax
0x18001047e  add     rsp, 28h
0x180010482  pop     rdi
0x180010483  pop     rsi
0x180010484  pop     rbp
0x180010485  pop     rbx
0x180010486  retn
```
