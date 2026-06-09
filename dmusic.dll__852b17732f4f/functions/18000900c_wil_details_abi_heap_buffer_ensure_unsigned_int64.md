# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x18000900c`
- end: `0x1800090de`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000617c`
- `0x180006a38`
- `0x180008218`
- `0x180008420`

## callees

- `0x18000603c`
- `0x18000900c`
- `0x180009458`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800090ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800090a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000904d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000904d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009071`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800090c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009071`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800090c9`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::ensure(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rcx
  DWORD LastError; // esi
  unsigned __int64 v6; // r14
  char *v7; // rax
  char *v8; // rbx
  rsize_t v10; // r15
  void *v11; // rbp
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
      v7 = (char *)wil::details::ProcessHeapAlloc(0, v6);
      v8 = v7;
      if ( !v7 )
      {
        SetLastError(LastError);
        return 0;
      }
      v10 = *((_QWORD *)this + 1) - *(_QWORD *)this;
      memcpy_s(v7, v6, *(const void *const *)this, v10);
      v11 = (void *)*((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = v8;
      if ( v11 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v11);
      }
      *(_QWORD *)this = v8;
      *((_QWORD *)this + 1) = &v8[v10];
      *((_QWORD *)this + 2) = &v8[v6];
      SetLastError(LastError);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000900c  push    rbx
0x18000900e  push    rbp
0x18000900f  push    rsi
0x180009010  push    rdi
0x180009011  push    r14
0x180009013  push    r15
0x180009015  sub     rsp, 28h
0x180009019  mov     rdi, rcx
0x18000901c  mov     rbx, rdx
0x18000901f  mov     rcx, [rcx+10h]
0x180009023  mov     rax, [rdi+8]
0x180009027  sub     rax, [rdi]
0x18000902a  sub     rcx, [rdi]
0x18000902d  add     rax, rdx
0x180009030  cmp     rax, rcx
0x180009033  jb      loc_1800090CF
0x180009039  lea     rax, [rcx+rcx]
0x18000903d  cmp     rdx, rax
0x180009040  cmovb   rbx, rax
0x180009044  cmp     rcx, rbx
0x180009047  jnb     loc_1800090CF
0x18000904d  call    cs:__imp_GetLastError
0x180009053  and     rbx, 0FFFFFFFFFFFFFFC0h
0x180009057  xor     ecx, ecx; dwFlags
0x180009059  mov     esi, eax
0x18000905b  lea     r14, [rbx+40h]
0x18000905f  mov     rdx, r14; dwBytes
0x180009062  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009067  mov     rbx, rax
0x18000906a  test    rax, rax
0x18000906d  jnz     short loc_18000907B
0x18000906f  mov     ecx, esi; dwErrCode
0x180009071  call    cs:__imp_SetLastError
0x180009077  xor     al, al
0x180009079  jmp     short loc_1800090D1
0x18000907b  mov     r15, [rdi+8]
0x18000907f  mov     rdx, r14; DestinationSize
0x180009082  sub     r15, [rdi]
0x180009085  mov     rcx, rbx; Destination
0x180009088  mov     r8, [rdi]; Source
0x18000908b  mov     r9, r15; SourceSize
0x18000908e  call    memcpy_s
0x180009093  mov     rbp, [rdi+18h]
0x180009097  mov     [rdi+18h], rbx
0x18000909b  test    rbp, rbp
0x18000909e  jz      short loc_1800090B4
0x1800090a0  call    cs:__imp_GetProcessHeap
0x1800090a6  mov     r8, rbp; lpMem
0x1800090a9  xor     edx, edx; dwFlags
0x1800090ab  mov     rcx, rax; hHeap
0x1800090ae  call    cs:__imp_HeapFree
0x1800090b4  lea     rax, [r15+rbx]
0x1800090b8  mov     [rdi], rbx
0x1800090bb  mov     [rdi+8], rax
0x1800090bf  mov     ecx, esi; dwErrCode
0x1800090c1  lea     rax, [r14+rbx]
0x1800090c5  mov     [rdi+10h], rax
0x1800090c9  call    cs:__imp_SetLastError
0x1800090cf  mov     al, 1
0x1800090d1  add     rsp, 28h
0x1800090d5  pop     r15
0x1800090d7  pop     r14
0x1800090d9  pop     rdi
0x1800090da  pop     rsi
0x1800090db  pop     rbp
0x1800090dc  pop     rbx
0x1800090dd  retn
```
