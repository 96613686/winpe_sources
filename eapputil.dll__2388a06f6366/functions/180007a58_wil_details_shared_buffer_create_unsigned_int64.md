# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180007a58`
- end: `0x180007b1b`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006eb4`
- `0x180007b30`

## callees

- `0x180007a58`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007aad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ae7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007aad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ae7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007abc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007abc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007af5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007af5`

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
0x180007a58  push    rbx
0x180007a5a  push    rbp
0x180007a5b  push    rsi
0x180007a5c  push    rdi
0x180007a5d  sub     rsp, 28h
0x180007a61  mov     rbp, rdx
0x180007a64  mov     rdi, rcx
0x180007a67  test    rdx, rdx
0x180007a6a  jnz     short loc_180007AAD
0x180007a6c  mov     rcx, [rcx]
0x180007a6f  test    rcx, rcx
0x180007a72  jz      short loc_180007AA6
0x180007a74  or      eax, 0FFFFFFFFh
0x180007a77  lock xadd [rcx], eax
0x180007a7b  cmp     eax, 1
0x180007a7e  jnz     short loc_180007A97
0x180007a80  mov     rbx, [rdi]
0x180007a83  call    cs:__imp_GetProcessHeap
0x180007a89  mov     r8, rbx; lpMem
0x180007a8c  xor     edx, edx; dwFlags
0x180007a8e  mov     rcx, rax; hHeap
0x180007a91  call    cs:__imp_HeapFree
0x180007a97  mov     qword ptr [rdi], 0
0x180007a9e  mov     qword ptr [rdi+8], 0
0x180007aa6  mov     eax, 1
0x180007aab  jmp     short loc_180007B12
0x180007aad  call    cs:__imp_GetProcessHeap
0x180007ab3  lea     r8, [rbp+4]; dwBytes
0x180007ab7  xor     edx, edx; dwFlags
0x180007ab9  mov     rcx, rax; hHeap
0x180007abc  call    cs:__imp_HeapAlloc
0x180007ac2  mov     rsi, rax
0x180007ac5  test    rax, rax
0x180007ac8  jz      short loc_180007B12
0x180007aca  mov     dword ptr [rax], 0
0x180007ad0  mov     rcx, [rdi]
0x180007ad3  test    rcx, rcx
0x180007ad6  jz      short loc_180007B03
0x180007ad8  or      eax, 0FFFFFFFFh
0x180007adb  lock xadd [rcx], eax
0x180007adf  cmp     eax, 1
0x180007ae2  jnz     short loc_180007AFB
0x180007ae4  mov     rbx, [rdi]
0x180007ae7  call    cs:__imp_GetProcessHeap
0x180007aed  mov     r8, rbx; lpMem
0x180007af0  xor     edx, edx; dwFlags
0x180007af2  mov     rcx, rax; hHeap
0x180007af5  call    cs:__imp_HeapFree
0x180007afb  mov     qword ptr [rdi+8], 0
0x180007b03  mov     [rdi], rsi
0x180007b06  mov     eax, 1
0x180007b0b  mov     [rdi+8], rbp
0x180007b0f  lock add [rsi], eax
0x180007b12  add     rsp, 28h
0x180007b16  pop     rdi
0x180007b17  pop     rsi
0x180007b18  pop     rbp
0x180007b19  pop     rbx
0x180007b1a  retn
```
