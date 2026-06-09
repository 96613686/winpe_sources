# Copy<TaskAllocator>(wchar_t * &,wchar_t * const &)

- ea: `0x1800131c0`
- end: `0x180013223`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAPEA_WAEBQEA_W@Z`
- size: `99`
- prototype: `char __fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001322c`

## callees

- `0x1800131c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180013212`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180013212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800131ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800131ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800131ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800131ff`

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
0x1800131c0  push    rbx
0x1800131c2  push    rbp
0x1800131c3  push    rsi
0x1800131c4  push    rdi
0x1800131c5  sub     rsp, 28h
0x1800131c9  mov     r8, [rdx]
0x1800131cc  xor     ebp, ebp
0x1800131ce  mov     rbx, rdx
0x1800131d1  mov     rsi, rcx
0x1800131d4  test    r8, r8
0x1800131d7  jz      short loc_180013218
0x1800131d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800131dd  inc     rax
0x1800131e0  cmp     [r8+rax*2], bp
0x1800131e5  jnz     short loc_1800131DD
0x1800131e7  lea     rdi, [rax+1]
0x1800131eb  lea     rcx, [rdi+rdi]; cb
0x1800131ef  call    cs:__imp_CoTaskMemAlloc
0x1800131f5  mov     [rsi], rax
0x1800131f8  test    rax, rax
0x1800131fb  jnz     short loc_180013209
0x1800131fd  xor     ecx, ecx; pv
0x1800131ff  call    cs:__imp_CoTaskMemFree
0x180013205  xor     al, al
0x180013207  jmp     short loc_18001321A
0x180013209  mov     r8, [rbx]
0x18001320c  mov     rdx, rdi
0x18001320f  mov     rcx, rax
0x180013212  call    cs:__imp__o_wcscpy_s
0x180013218  mov     al, 1
0x18001321a  add     rsp, 28h
0x18001321e  pop     rdi
0x18001321f  pop     rsi
0x180013220  pop     rbp
0x180013221  pop     rbx
0x180013222  retn
```
