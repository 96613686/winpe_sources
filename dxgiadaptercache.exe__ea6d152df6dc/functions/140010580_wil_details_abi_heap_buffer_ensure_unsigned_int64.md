# wil::details_abi::heap_buffer::ensure(unsigned __int64)

- ea: `0x140010580`
- end: `0x140010652`
- name: `?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `210`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ab34`
- `0x14000b558`
- `0x14000dc5c`

## callees

- `0x14000a910`
- `0x140010580`
- `0x140010f78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010614`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010614`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010622`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400105c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400105c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400105e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001063d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400105e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001063d`

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
0x140010580  push    rbx
0x140010582  push    rbp
0x140010583  push    rsi
0x140010584  push    rdi
0x140010585  push    r14
0x140010587  push    r15
0x140010589  sub     rsp, 28h
0x14001058d  mov     rdi, rcx
0x140010590  mov     rbx, rdx
0x140010593  mov     rcx, [rcx+10h]
0x140010597  mov     rax, [rdi+8]
0x14001059b  sub     rax, [rdi]
0x14001059e  sub     rcx, [rdi]
0x1400105a1  add     rax, rdx
0x1400105a4  cmp     rax, rcx
0x1400105a7  jb      loc_140010643
0x1400105ad  lea     rax, [rcx+rcx]
0x1400105b1  cmp     rdx, rax
0x1400105b4  cmovb   rbx, rax
0x1400105b8  cmp     rcx, rbx
0x1400105bb  jnb     loc_140010643
0x1400105c1  call    cs:__imp_GetLastError
0x1400105c7  and     rbx, 0FFFFFFFFFFFFFFC0h
0x1400105cb  xor     ecx, ecx; dwFlags
0x1400105cd  mov     esi, eax
0x1400105cf  lea     r14, [rbx+40h]
0x1400105d3  mov     rdx, r14; dwBytes
0x1400105d6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400105db  mov     rbx, rax
0x1400105de  test    rax, rax
0x1400105e1  jnz     short loc_1400105EF
0x1400105e3  mov     ecx, esi; dwErrCode
0x1400105e5  call    cs:__imp_SetLastError
0x1400105eb  xor     al, al
0x1400105ed  jmp     short loc_140010645
0x1400105ef  mov     r15, [rdi+8]
0x1400105f3  mov     rdx, r14; DestinationSize
0x1400105f6  sub     r15, [rdi]
0x1400105f9  mov     rcx, rbx; Destination
0x1400105fc  mov     r8, [rdi]; Source
0x1400105ff  mov     r9, r15; SourceSize
0x140010602  call    memcpy_s
0x140010607  mov     rbp, [rdi+18h]
0x14001060b  mov     [rdi+18h], rbx
0x14001060f  test    rbp, rbp
0x140010612  jz      short loc_140010628
0x140010614  call    cs:__imp_GetProcessHeap
0x14001061a  mov     r8, rbp; lpMem
0x14001061d  xor     edx, edx; dwFlags
0x14001061f  mov     rcx, rax; hHeap
0x140010622  call    cs:__imp_HeapFree
0x140010628  lea     rax, [r15+rbx]
0x14001062c  mov     [rdi], rbx
0x14001062f  mov     [rdi+8], rax
0x140010633  mov     ecx, esi; dwErrCode
0x140010635  lea     rax, [r14+rbx]
0x140010639  mov     [rdi+10h], rax
0x14001063d  call    cs:__imp_SetLastError
0x140010643  mov     al, 1
0x140010645  add     rsp, 28h
0x140010649  pop     r15
0x14001064b  pop     r14
0x14001064d  pop     rdi
0x14001064e  pop     rsi
0x14001064f  pop     rbp
0x140010650  pop     rbx
0x140010651  retn
```
