# wil::details::shared_buffer::create(unsigned __int64)

- ea: `0x1800188a0`
- end: `0x180018926`
- name: `?create@shared_buffer@details@wil@@QEAA_N_K@Z`
- size: `134`
- prototype: `bool __fastcall(wil::details::shared_buffer *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180016580`
- `0x1800189a0`

## callees

- `0x180018810`
- `0x1800188a0`
- `0x180018930`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800188cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800188cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800188e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800188e2`

## pseudocode

```c
bool __fastcall wil::details::shared_buffer::create(wil::details::shared_buffer *this, unsigned __int64 a2)
{
  int *v4; // rax
  HANDLE ProcessHeap; // rax

  if ( a2 )
  {
    ProcessHeap = GetProcessHeap();
    v4 = (int *)HeapAlloc(ProcessHeap, 0, a2 + 4);
    if ( v4 )
    {
      *v4 = 0;
      wil::details::shared_buffer::assign(this, v4, a2);
      LOBYTE(v4) = 1;
    }
  }
  else
  {
    wil::details::shared_buffer::reset(this);
    LOBYTE(v4) = 1;
  }
  return (char)v4;
}

```

## disassembly

```asm
0x1800188a0  mov     [rsp+arg_8], rsi
0x1800188a5  push    rdi
0x1800188a6  sub     rsp, 20h
0x1800188aa  mov     rdi, rdx
0x1800188ad  mov     rsi, rcx
0x1800188b0  test    rdx, rdx
0x1800188b3  jnz     short loc_1800188C8
0x1800188b5  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x1800188ba  mov     al, 1
0x1800188bc  mov     rsi, [rsp+28h+arg_8]
0x1800188c1  add     rsp, 20h
0x1800188c5  pop     rdi
0x1800188c6  retn
0x1800188c8  mov     [rsp+28h+arg_0], rbx
0x1800188cd  call    cs:__imp_GetProcessHeap
0x1800188d4  nop     dword ptr [rax+rax+00h]
0x1800188d9  lea     r8, [rdi+4]; dwBytes
0x1800188dd  xor     edx, edx; dwFlags
0x1800188df  mov     rcx, rax; hHeap
0x1800188e2  call    cs:__imp_HeapAlloc
0x1800188e9  nop     dword ptr [rax+rax+00h]
0x1800188ee  mov     rbx, [rsp+28h+arg_0]
0x1800188f3  test    rax, rax
0x1800188f6  jnz     short loc_180018904
0x1800188f8  mov     rsi, [rsp+28h+arg_8]
0x1800188fd  add     rsp, 20h
0x180018901  pop     rdi
0x180018902  retn
0x180018904  mov     r8, rdi; unsigned __int64
0x180018907  mov     dword ptr [rax], 0
0x18001890d  mov     rdx, rax; int *
0x180018910  mov     rcx, rsi; this
0x180018913  call    ?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z; wil::details::shared_buffer::assign(long *,unsigned __int64)
0x180018918  mov     rsi, [rsp+28h+arg_8]
0x18001891d  mov     al, 1
0x18001891f  add     rsp, 20h
0x180018923  pop     rdi
0x180018924  retn
```
