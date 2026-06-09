# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x180006a44`
- end: `0x180006b07`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `195`
- prototype: `__int64 __fastcall(volatile signed __int32 **this, volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800057b4`
- `0x180006e20`

## callees

- `0x180006a44`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ae1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ae1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ad3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ad3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006aa8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006aa8`

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
0x180006a44  push    rbx
0x180006a46  push    rbp
0x180006a47  push    rsi
0x180006a48  push    rdi
0x180006a49  sub     rsp, 28h
0x180006a4d  mov     rbp, rdx
0x180006a50  mov     rdi, rcx
0x180006a53  test    rdx, rdx
0x180006a56  jnz     short loc_180006A99
0x180006a58  mov     rcx, [rcx]
0x180006a5b  test    rcx, rcx
0x180006a5e  jz      short loc_180006A92
0x180006a60  or      eax, 0FFFFFFFFh
0x180006a63  lock xadd [rcx], eax
0x180006a67  cmp     eax, 1
0x180006a6a  jnz     short loc_180006A83
0x180006a6c  mov     rbx, [rdi]
0x180006a6f  call    cs:__imp_GetProcessHeap
0x180006a75  mov     r8, rbx; lpMem
0x180006a78  xor     edx, edx; dwFlags
0x180006a7a  mov     rcx, rax; hHeap
0x180006a7d  call    cs:__imp_HeapFree
0x180006a83  mov     qword ptr [rdi], 0
0x180006a8a  mov     qword ptr [rdi+8], 0
0x180006a92  mov     eax, 1
0x180006a97  jmp     short loc_180006AFE
0x180006a99  call    cs:__imp_GetProcessHeap
0x180006a9f  lea     r8, [rbp+4]; dwBytes
0x180006aa3  xor     edx, edx; dwFlags
0x180006aa5  mov     rcx, rax; hHeap
0x180006aa8  call    cs:__imp_HeapAlloc
0x180006aae  mov     rsi, rax
0x180006ab1  test    rax, rax
0x180006ab4  jz      short loc_180006AFE
0x180006ab6  mov     dword ptr [rax], 0
0x180006abc  mov     rcx, [rdi]
0x180006abf  test    rcx, rcx
0x180006ac2  jz      short loc_180006AEF
0x180006ac4  or      eax, 0FFFFFFFFh
0x180006ac7  lock xadd [rcx], eax
0x180006acb  cmp     eax, 1
0x180006ace  jnz     short loc_180006AE7
0x180006ad0  mov     rbx, [rdi]
0x180006ad3  call    cs:__imp_GetProcessHeap
0x180006ad9  mov     r8, rbx; lpMem
0x180006adc  xor     edx, edx; dwFlags
0x180006ade  mov     rcx, rax; hHeap
0x180006ae1  call    cs:__imp_HeapFree
0x180006ae7  mov     qword ptr [rdi+8], 0
0x180006aef  mov     [rdi], rsi
0x180006af2  mov     eax, 1
0x180006af7  mov     [rdi+8], rbp
0x180006afb  lock add [rsi], eax
0x180006afe  add     rsp, 28h
0x180006b02  pop     rdi
0x180006b03  pop     rsi
0x180006b04  pop     rbp
0x180006b05  pop     rbx
0x180006b06  retn
```
