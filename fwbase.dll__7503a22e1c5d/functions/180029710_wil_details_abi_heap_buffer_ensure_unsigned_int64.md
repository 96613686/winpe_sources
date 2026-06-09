# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x180029710`
- end: `0x180029812`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `258`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180025fe0`
- `0x180026a40`
- `0x180028210`
- `0x180028330`
- `0x180028b30`

## callees

- `0x180025d20`
- `0x180029710`
- `0x180029fd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002977e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800297ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002977e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800297ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002975a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002975a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800297d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800297d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800297c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800297c6`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v7; // r14
  char *v8; // rax
  char *v9; // rbx
  rsize_t v10; // r15
  void *v11; // rbp
  HANDLE ProcessHeap; // rax

  v3 = a2;
  v4 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( a2 + *((_QWORD *)this + 1) - *(_QWORD *)this < v4 )
    return 1;
  if ( a2 < 2 * v4 )
    v3 = 2 * v4;
  if ( v4 < v3 )
  {
    LastError = GetLastError();
    v7 = (v3 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
    v8 = (char *)wil::details::ProcessHeapAlloc(0, v7);
    v9 = v8;
    if ( !v8 )
    {
      SetLastError(LastError);
      return 0;
    }
    v10 = *((_QWORD *)this + 1) - *(_QWORD *)this;
    memcpy_s(v8, v7, *(const void *const *)this, v10);
    v11 = (void *)*((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v9;
    if ( v11 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
    }
    *(_QWORD *)this = v9;
    *((_QWORD *)this + 1) = &v9[v10];
    *((_QWORD *)this + 2) = &v9[v7];
    SetLastError(LastError);
  }
  return 1;
}

```

## disassembly

```asm
0x180029710  push    rbx
0x180029712  push    rdi
0x180029713  sub     rsp, 28h
0x180029717  mov     rdi, rcx
0x18002971a  mov     rbx, rdx
0x18002971d  mov     rcx, [rcx+10h]
0x180029721  mov     rax, [rdi+8]
0x180029725  sub     rax, [rdi]
0x180029728  sub     rcx, [rdi]
0x18002972b  add     rax, rdx
0x18002972e  cmp     rax, rcx
0x180029731  jnb     short loc_18002973C
0x180029733  mov     al, 1
0x180029735  add     rsp, 28h
0x180029739  pop     rdi
0x18002973a  pop     rbx
0x18002973b  retn
0x18002973c  lea     rax, [rcx+rcx]
0x180029740  mov     [rsp+38h+arg_8], rsi
0x180029745  cmp     rbx, rax
0x180029748  mov     [rsp+38h+arg_10], r14
0x18002974d  cmovb   rbx, rax
0x180029751  cmp     rcx, rbx
0x180029754  jnb     loc_1800297FF
0x18002975a  call    cs:__imp_GetLastError
0x180029760  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180029764  xor     ecx, ecx; dwFlags
0x180029766  mov     esi, eax
0x180029768  lea     r14, [rbx+40h]
0x18002976c  mov     rdx, r14; dwBytes
0x18002976f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180029774  mov     rbx, rax
0x180029777  test    rax, rax
0x18002977a  jnz     short loc_180029797
0x18002977c  mov     ecx, esi; dwErrCode
0x18002977e  call    cs:__imp_SetLastError
0x180029784  mov     r14, [rsp+38h+arg_10]
0x180029789  xor     al, al
0x18002978b  mov     rsi, [rsp+38h+arg_8]
0x180029790  add     rsp, 28h
0x180029794  pop     rdi
0x180029795  pop     rbx
0x180029796  retn
0x180029797  mov     r8, [rdi]; Source
0x18002979a  mov     rdx, r14; DestinationSize
0x18002979d  mov     [rsp+38h+arg_0], rbp
0x1800297a2  mov     rcx, rbx; Destination
0x1800297a5  mov     [rsp+38h+var_18], r15
0x1800297aa  mov     r15, [rdi+8]
0x1800297ae  sub     r15, r8
0x1800297b1  mov     r9, r15; SourceSize
0x1800297b4  call    memcpy_s
0x1800297b9  mov     rbp, [rdi+18h]
0x1800297bd  mov     [rdi+18h], rbx
0x1800297c1  test    rbp, rbp
0x1800297c4  jz      short loc_1800297DA
0x1800297c6  call    cs:__imp_GetProcessHeap
0x1800297cc  mov     r8, rbp; lpMem
0x1800297cf  xor     edx, edx; dwFlags
0x1800297d1  mov     rcx, rax; hHeap
0x1800297d4  call    cs:__imp_HeapFree
0x1800297da  lea     rax, [r15+rbx]
0x1800297de  mov     [rdi], rbx
0x1800297e1  mov     [rdi+8], rax
0x1800297e5  mov     ecx, esi; dwErrCode
0x1800297e7  lea     rax, [r14+rbx]
0x1800297eb  mov     [rdi+10h], rax
0x1800297ef  call    cs:__imp_SetLastError
0x1800297f5  mov     r15, [rsp+38h+var_18]
0x1800297fa  mov     rbp, [rsp+38h+arg_0]
0x1800297ff  mov     r14, [rsp+38h+arg_10]
0x180029804  mov     al, 1
0x180029806  mov     rsi, [rsp+38h+arg_8]
0x18002980b  add     rsp, 28h
0x18002980f  pop     rdi
0x180029810  pop     rbx
0x180029811  retn
```
