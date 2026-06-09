# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x1800124ac`
- end: `0x18001257f`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `211`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ef24`
- `0x18000f0b4`
- `0x18000f878`
- `0x1800113c4`
- `0x180011594`

## callees

- `0x180005468`
- `0x1800124ac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001252e`
- `msvcrt!memcpy_s` at `0x18001252e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012511`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001256a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012511`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001256a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001254f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001254f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012541`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012541`

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
0x1800124ac  push    rbx
0x1800124ae  push    rbp
0x1800124af  push    rsi
0x1800124b0  push    rdi
0x1800124b1  push    r14
0x1800124b3  push    r15
0x1800124b5  sub     rsp, 28h
0x1800124b9  mov     rdi, rcx
0x1800124bc  mov     rbx, rdx
0x1800124bf  mov     rcx, [rcx+10h]
0x1800124c3  mov     rax, [rdi+8]
0x1800124c7  sub     rax, [rdi]
0x1800124ca  sub     rcx, [rdi]
0x1800124cd  add     rax, rdx
0x1800124d0  cmp     rax, rcx
0x1800124d3  jb      loc_180012570
0x1800124d9  lea     rax, [rcx+rcx]
0x1800124dd  cmp     rdx, rax
0x1800124e0  cmovb   rbx, rax
0x1800124e4  cmp     rcx, rbx
0x1800124e7  jnb     loc_180012570
0x1800124ed  call    cs:__imp_GetLastError
0x1800124f3  and     rbx, 0FFFFFFFFFFFFFFC0h
0x1800124f7  xor     ecx, ecx; dwFlags
0x1800124f9  mov     esi, eax
0x1800124fb  lea     r14, [rbx+40h]
0x1800124ff  mov     rdx, r14; dwBytes
0x180012502  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180012507  mov     rbx, rax
0x18001250a  test    rax, rax
0x18001250d  jnz     short loc_18001251B
0x18001250f  mov     ecx, esi; dwErrCode
0x180012511  call    cs:__imp_SetLastError
0x180012517  xor     al, al
0x180012519  jmp     short loc_180012572
0x18001251b  mov     r15, [rdi+8]
0x18001251f  mov     rdx, r14; DestinationSize
0x180012522  sub     r15, [rdi]
0x180012525  mov     rcx, rbx; Destination
0x180012528  mov     r8, [rdi]; Source
0x18001252b  mov     r9, r15; SourceSize
0x18001252e  call    cs:__imp_memcpy_s
0x180012534  mov     rbp, [rdi+18h]
0x180012538  mov     [rdi+18h], rbx
0x18001253c  test    rbp, rbp
0x18001253f  jz      short loc_180012555
0x180012541  call    cs:__imp_GetProcessHeap
0x180012547  mov     r8, rbp; lpMem
0x18001254a  xor     edx, edx; dwFlags
0x18001254c  mov     rcx, rax; hHeap
0x18001254f  call    cs:__imp_HeapFree
0x180012555  lea     rax, [r15+rbx]
0x180012559  mov     [rdi], rbx
0x18001255c  mov     [rdi+8], rax
0x180012560  mov     ecx, esi; dwErrCode
0x180012562  lea     rax, [r14+rbx]
0x180012566  mov     [rdi+10h], rax
0x18001256a  call    cs:__imp_SetLastError
0x180012570  mov     al, 1
0x180012572  add     rsp, 28h
0x180012576  pop     r15
0x180012578  pop     r14
0x18001257a  pop     rdi
0x18001257b  pop     rsi
0x18001257c  pop     rbp
0x18001257d  pop     rbx
0x18001257e  retn
```
