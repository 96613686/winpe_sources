# Copy<TaskAllocator>(wchar_t * &,wchar_t * const &)

- ea: `0x1800039e0`
- end: `0x180003a43`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAPEA_WAEBQEA_W@Z`
- size: `99`
- prototype: `char __fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180003c40`

## callees

- `0x1800039e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180003a32`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180003a32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003a0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003a0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a1f`

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
0x1800039e0  push    rbx
0x1800039e2  push    rbp
0x1800039e3  push    rsi
0x1800039e4  push    rdi
0x1800039e5  sub     rsp, 28h
0x1800039e9  mov     r8, [rdx]
0x1800039ec  xor     ebp, ebp
0x1800039ee  mov     rbx, rdx
0x1800039f1  mov     rsi, rcx
0x1800039f4  test    r8, r8
0x1800039f7  jz      short loc_180003A38
0x1800039f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800039fd  inc     rax
0x180003a00  cmp     [r8+rax*2], bp
0x180003a05  jnz     short loc_1800039FD
0x180003a07  lea     rdi, [rax+1]
0x180003a0b  lea     rcx, [rdi+rdi]; cb
0x180003a0f  call    cs:__imp_CoTaskMemAlloc
0x180003a15  mov     [rsi], rax
0x180003a18  test    rax, rax
0x180003a1b  jnz     short loc_180003A29
0x180003a1d  xor     ecx, ecx; pv
0x180003a1f  call    cs:__imp_CoTaskMemFree
0x180003a25  xor     al, al
0x180003a27  jmp     short loc_180003A3A
0x180003a29  mov     r8, [rbx]
0x180003a2c  mov     rdx, rdi
0x180003a2f  mov     rcx, rax
0x180003a32  call    cs:__imp__o_wcscpy_s
0x180003a38  mov     al, 1
0x180003a3a  add     rsp, 28h
0x180003a3e  pop     rdi
0x180003a3f  pop     rsi
0x180003a40  pop     rbp
0x180003a41  pop     rbx
0x180003a42  retn
```
