# wil::make_process_heap_string_nothrow(ushort const *,unsigned __int64)

- ea: `0x18002e6f8`
- end: `0x18002e7d3`
- name: `?make_process_heap_string_nothrow@wil@@YA@PEBG_K@Z`
- size: `219`
- prototype: `_QWORD(wil *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18002dc24`
- `0x180045698`

## callees

- `0x18000312a`
- `0x1800031a0`
- `0x18000cc1c`
- `0x18002e6f8`
- `0x18004b988`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002e78c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002e78c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e754`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002e754`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e73d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002e73d`

## string_xrefs

- `0x18002e7c1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
wil *__fastcall wil::make_process_heap_string_nothrow(
        wil *this,
        const unsigned __int16 *a2,
        __int64 a3,
        const char *a4)
{
  __int64 v6; // rcx
  const unsigned __int16 *v7; // rax
  size_t v8; // rbx
  size_t v9; // rbp
  HANDLE ProcessHeap; // rax
  char *v11; // rax
  char *v12; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v6 = 0x7FFFFFFF;
  v7 = a2;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v8 = 2 * (v7 - a2);
  v9 = v8 + 2;
  ProcessHeap = GetProcessHeap();
  v11 = (char *)HeapAlloc(ProcessHeap, 8u, v8 + 2);
  v12 = v11;
  if ( v11 )
  {
    if ( v8 )
    {
      if ( v9 < v8 )
      {
        memset_0(v11, 0, v9);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v11, a2, v8);
      }
    }
    *(_WORD *)&v12[v8] = 0;
  }
  *(_QWORD *)this = v12;
  return this;
}

```

## disassembly

```asm
0x18002e6f8  push    rbx
0x18002e6fa  push    rbp
0x18002e6fb  push    rsi
0x18002e6fc  push    rdi
0x18002e6fd  push    r14
0x18002e6ff  push    r15
0x18002e701  sub     rsp, 28h
0x18002e705  xor     r15d, r15d
0x18002e708  mov     rsi, rdx
0x18002e70b  mov     r14, rcx
0x18002e70e  test    rdx, rdx
0x18002e711  jz      loc_18002E7BC
0x18002e717  mov     ecx, 7FFFFFFFh
0x18002e71c  mov     rax, rdx
0x18002e71f  cmp     [rax], r15w
0x18002e723  jz      short loc_18002E72F
0x18002e725  add     rax, 2
0x18002e729  sub     rcx, 1
0x18002e72d  jnz     short loc_18002E71F
0x18002e72f  sub     rax, rsi
0x18002e732  sar     rax, 1
0x18002e735  lea     rbx, [rax+rax]
0x18002e739  lea     rbp, [rbx+2]
0x18002e73d  call    cs:__imp_GetProcessHeap
0x18002e744  nop     dword ptr [rax+rax+00h]
0x18002e749  mov     r8, rbp; dwBytes
0x18002e74c  mov     edx, 8; dwFlags
0x18002e751  mov     rcx, rax; hHeap
0x18002e754  call    cs:__imp_HeapAlloc
0x18002e75b  nop     dword ptr [rax+rax+00h]
0x18002e760  mov     rdi, rax
0x18002e763  test    rax, rax
0x18002e766  jz      short loc_18002E7A8
0x18002e768  test    rbx, rbx
0x18002e76b  jz      short loc_18002E7A3
0x18002e76d  mov     rcx, rax; void *
0x18002e770  cmp     rbp, rbx
0x18002e773  jb      short loc_18002E782
0x18002e775  mov     r8, rbx; Size
0x18002e778  mov     rdx, rsi; Src
0x18002e77b  call    memcpy_0
0x18002e780  jmp     short loc_18002E7A3
0x18002e782  mov     r8, rbp; Size
0x18002e785  xor     edx, edx; Val
0x18002e787  call    memset_0
0x18002e78c  call    cs:__imp__o__errno
0x18002e793  nop     dword ptr [rax+rax+00h]
0x18002e798  mov     dword ptr [rax], 22h ; '"'
0x18002e79e  call    _invalid_parameter_noinfo
0x18002e7a3  mov     [rbx+rdi], r15w
0x18002e7a8  mov     [r14], rdi
0x18002e7ab  mov     rax, r14
0x18002e7ae  add     rsp, 28h
0x18002e7b2  pop     r15
0x18002e7b4  pop     r14
0x18002e7b6  pop     rdi
0x18002e7b7  pop     rsi
0x18002e7b8  pop     rbp
0x18002e7b9  pop     rbx
0x18002e7ba  retn
0x18002e7bc  mov     rcx, [rsp+58h]; this
0x18002e7c1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002e7c8  mov     edx, 0F89h; void *
0x18002e7cd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
