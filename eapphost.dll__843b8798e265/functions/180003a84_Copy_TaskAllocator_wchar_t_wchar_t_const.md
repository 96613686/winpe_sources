# Copy<TaskAllocator>(wchar_t * &,wchar_t * const &)

- ea: `0x180003a84`
- end: `0x180003afa`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAPEA_WAEBQEA_W@Z`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180003d0c`

## callees

- `0x180003a84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180003ae2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180003ae2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003ab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003ab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ac9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ac9`

## pseudocode

```c
char __fastcall Copy<TaskAllocator>(_QWORD *a1, _QWORD *a2)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  LPVOID v6; // rax

  if ( *a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(*a2 + 2 * v4) );
    v5 = v4 + 1;
    v6 = CoTaskMemAlloc(2 * (v4 + 1));
    *a1 = v6;
    if ( !v6 )
    {
      CoTaskMemFree(0);
      return 0;
    }
    _o_wcscpy_s(v6, v5, *a2);
  }
  return 1;
}

```

## disassembly

```asm
0x180003a84  push    rbx
0x180003a86  push    rbp
0x180003a87  push    rsi
0x180003a88  push    rdi
0x180003a89  sub     rsp, 28h
0x180003a8d  mov     r8, [rdx]
0x180003a90  xor     ebp, ebp
0x180003a92  mov     rbx, rdx
0x180003a95  mov     rsi, rcx
0x180003a98  test    r8, r8
0x180003a9b  jz      short loc_180003AEE
0x180003a9d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003aa1  inc     rax
0x180003aa4  cmp     [r8+rax*2], bp
0x180003aa9  jnz     short loc_180003AA1
0x180003aab  lea     rdi, [rax+1]
0x180003aaf  lea     rcx, [rdi+rdi]; cb
0x180003ab3  call    cs:__imp_CoTaskMemAlloc
0x180003aba  nop     dword ptr [rax+rax+00h]
0x180003abf  mov     [rsi], rax
0x180003ac2  test    rax, rax
0x180003ac5  jnz     short loc_180003AD9
0x180003ac7  xor     ecx, ecx; pv
0x180003ac9  call    cs:__imp_CoTaskMemFree
0x180003ad0  nop     dword ptr [rax+rax+00h]
0x180003ad5  xor     al, al
0x180003ad7  jmp     short loc_180003AF0
0x180003ad9  mov     r8, [rbx]
0x180003adc  mov     rdx, rdi
0x180003adf  mov     rcx, rax
0x180003ae2  call    cs:__imp__o_wcscpy_s
0x180003ae9  nop     dword ptr [rax+rax+00h]
0x180003aee  mov     al, 1
0x180003af0  add     rsp, 28h
0x180003af4  pop     rdi
0x180003af5  pop     rsi
0x180003af6  pop     rbp
0x180003af7  pop     rbx
0x180003af8  retn
```
