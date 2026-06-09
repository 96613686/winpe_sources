# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000c80c`
- end: `0x18000c8de`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180007fb8`
- `0x18000815c`
- `0x1800089b8`
- `0x18000b7c8`
- `0x18000b9d0`

## callees

- `0x180007e78`
- `0x18000c80c`
- `0x18000cdd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c84d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c84d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c871`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c871`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c8ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c8ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c8a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c8a0`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // r8
  char *v8; // rax
  char *v9; // rbx
  rsize_t v11; // r15
  void *v12; // rbp
  HANDLE ProcessHeap; // rax

  v3 = a2;
  v4 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( a2 + *((_QWORD *)this + 1) - *(_QWORD *)this >= v4 )
  {
    if ( a2 < 2 * v4 )
      v3 = 2 * v4;
    if ( v4 < v3 )
    {
      LastError = GetLastError();
      v6 = (v3 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
      v8 = (char *)wil::details::ProcessHeapAlloc(0, v6, v7);
      v9 = v8;
      if ( !v8 )
      {
        SetLastError(LastError);
        return 0;
      }
      v11 = *((_QWORD *)this + 1) - *(_QWORD *)this;
      memcpy_s(v8, v6, *(const void *const *)this, v11);
      v12 = (void *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = v9;
      if ( v12 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v12);
      }
      *(_QWORD *)this = v9;
      *((_QWORD *)this + 1) = &v9[v11];
      *((_QWORD *)this + 2) = &v9[v6];
      SetLastError(LastError);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000c80c  push    rbx
0x18000c80e  push    rbp
0x18000c80f  push    rsi
0x18000c810  push    rdi
0x18000c811  push    r14
0x18000c813  push    r15
0x18000c815  sub     rsp, 28h
0x18000c819  mov     rdi, rcx
0x18000c81c  mov     rbx, rdx
0x18000c81f  mov     rcx, [rcx+10h]
0x18000c823  mov     rax, [rdi+8]
0x18000c827  sub     rax, [rdi]
0x18000c82a  sub     rcx, [rdi]
0x18000c82d  add     rax, rdx
0x18000c830  cmp     rax, rcx
0x18000c833  jb      loc_18000C8CF
0x18000c839  lea     rax, [rcx+rcx]
0x18000c83d  cmp     rdx, rax
0x18000c840  cmovb   rbx, rax
0x18000c844  cmp     rcx, rbx
0x18000c847  jnb     loc_18000C8CF
0x18000c84d  call    cs:__imp_GetLastError
0x18000c853  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000c857  xor     ecx, ecx; dwFlags
0x18000c859  mov     esi, eax
0x18000c85b  lea     r14, [rbx+40h]
0x18000c85f  mov     rdx, r14; dwBytes
0x18000c862  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c867  mov     rbx, rax
0x18000c86a  test    rax, rax
0x18000c86d  jnz     short loc_18000C87B
0x18000c86f  mov     ecx, esi; dwErrCode
0x18000c871  call    cs:__imp_SetLastError
0x18000c877  xor     al, al
0x18000c879  jmp     short loc_18000C8D1
0x18000c87b  mov     r15, [rdi+8]
0x18000c87f  mov     rdx, r14; DestinationSize
0x18000c882  sub     r15, [rdi]
0x18000c885  mov     rcx, rbx; Destination
0x18000c888  mov     r8, [rdi]; Source
0x18000c88b  mov     r9, r15; SourceSize
0x18000c88e  call    memcpy_s
0x18000c893  mov     rbp, [rdi+18h]
0x18000c897  mov     [rdi+18h], rbx
0x18000c89b  test    rbp, rbp
0x18000c89e  jz      short loc_18000C8B4
0x18000c8a0  call    cs:__imp_GetProcessHeap
0x18000c8a6  mov     r8, rbp; lpMem
0x18000c8a9  xor     edx, edx; dwFlags
0x18000c8ab  mov     rcx, rax; hHeap
0x18000c8ae  call    cs:__imp_HeapFree
0x18000c8b4  lea     rax, [r15+rbx]
0x18000c8b8  mov     [rdi], rbx
0x18000c8bb  mov     [rdi+8], rax
0x18000c8bf  mov     ecx, esi; dwErrCode
0x18000c8c1  lea     rax, [r14+rbx]
0x18000c8c5  mov     [rdi+10h], rax
0x18000c8c9  call    cs:__imp_SetLastError
0x18000c8cf  mov     al, 1
0x18000c8d1  add     rsp, 28h
0x18000c8d5  pop     r15
0x18000c8d7  pop     r14
0x18000c8d9  pop     rdi
0x18000c8da  pop     rsi
0x18000c8db  pop     rbp
0x18000c8dc  pop     rbx
0x18000c8dd  retn
```
