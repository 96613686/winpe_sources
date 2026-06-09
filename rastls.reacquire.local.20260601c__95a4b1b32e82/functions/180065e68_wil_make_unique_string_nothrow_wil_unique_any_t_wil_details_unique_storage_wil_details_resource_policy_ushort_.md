# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180065e68`
- end: `0x180065f51`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180029f18`
- `0x180067288`

## callees

- `0x18002bb8c`
- `0x18003b7a4`
- `0x180065e68`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065ee7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180065ee7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180065efe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180065efe`

## string_xrefs

- `0x180065e93`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rbx
  HANDLE ProcessHeap; // rax
  _WORD *v11; // rax
  _WORD *v12; // rsi
  rsize_t v13; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
  if ( a2 )
  {
    v8 = a3;
    v9 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v8 = 0x7FFFFFFF;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
    if ( a3 == -1 )
      v4 = v7;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v7 = a3;
  }
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, 2 * v4 + 2);
  v12 = v11;
  if ( v11 )
  {
    if ( a2 )
    {
      v13 = v7;
      memcpy_s_1(v11, 2 * v4 + 2, a2, v13 * 2);
      v12[v13] = 0;
    }
    else
    {
      *v11 = 0;
    }
    v12[v4] = 0;
  }
  *a1 = v12;
  return a1;
}

```

## disassembly

```asm
0x180065e68  push    rbx
0x180065e6a  push    rbp
0x180065e6b  push    rsi
0x180065e6c  push    rdi
0x180065e6d  push    r12
0x180065e6f  push    r14
0x180065e71  push    r15
0x180065e73  sub     rsp, 20h
0x180065e77  xor     r12d, r12d
0x180065e7a  mov     rdi, r8
0x180065e7d  mov     rbp, rdx
0x180065e80  mov     r14, rcx
0x180065e83  test    rdx, rdx
0x180065e86  jnz     short loc_180065EAA
0x180065e88  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180065e8c  jnz     short loc_180065EA5
0x180065e8e  mov     rcx, [rsp+58h]; this
0x180065e93  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180065e9a  mov     edx, 0F89h; void *
0x180065e9f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180065ea5  mov     rbx, rdi
0x180065ea8  jmp     short loc_180065EDF
0x180065eaa  mov     ecx, 7FFFFFFFh
0x180065eaf  mov     rax, rdi
0x180065eb2  cmp     rdi, rcx
0x180065eb5  mov     rbx, rbp
0x180065eb8  cmovnb  rax, rcx
0x180065ebc  test    rax, rax
0x180065ebf  jz      short loc_180065ED1
0x180065ec1  cmp     [rbx], r12w
0x180065ec5  jz      short loc_180065ED1
0x180065ec7  add     rbx, 2
0x180065ecb  sub     rax, 1
0x180065ecf  jnz     short loc_180065EC1
0x180065ed1  sub     rbx, rbp
0x180065ed4  sar     rbx, 1
0x180065ed7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180065edb  cmovz   rdi, rbx
0x180065edf  lea     r15, ds:2[rdi*2]
0x180065ee7  call    cs:__imp_GetProcessHeap
0x180065eee  nop     dword ptr [rax+rax+00h]
0x180065ef3  mov     r8, r15; dwBytes
0x180065ef6  mov     edx, 8; dwFlags
0x180065efb  mov     rcx, rax; hHeap
0x180065efe  call    cs:__imp_HeapAlloc
0x180065f05  nop     dword ptr [rax+rax+00h]
0x180065f0a  mov     rsi, rax
0x180065f0d  test    rax, rax
0x180065f10  jz      short loc_180065F3B
0x180065f12  test    rbp, rbp
0x180065f15  jz      short loc_180065F32
0x180065f17  add     rbx, rbx
0x180065f1a  mov     r8, rbp; Source
0x180065f1d  mov     r9, rbx; SourceSize
0x180065f20  mov     rdx, r15; DestinationSize
0x180065f23  mov     rcx, rax; Destination
0x180065f26  call    memcpy_s_1
0x180065f2b  mov     [rbx+rsi], r12w
0x180065f30  jmp     short loc_180065F36
0x180065f32  mov     [rax], r12w
0x180065f36  mov     [rsi+rdi*2], r12w
0x180065f3b  mov     [r14], rsi
0x180065f3e  mov     rax, r14
0x180065f41  add     rsp, 20h
0x180065f45  pop     r15
0x180065f47  pop     r14
0x180065f49  pop     r12
0x180065f4b  pop     rdi
0x180065f4c  pop     rsi
0x180065f4d  pop     rbp
0x180065f4e  pop     rbx
0x180065f4f  retn
```
