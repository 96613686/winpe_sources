# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800624dc`
- end: `0x1800625b8`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180027fb4`
- `0x180063840`

## callees

- `0x180029700`
- `0x180038af0`
- `0x1800624dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006255b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006255b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006256c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006256c`

## string_xrefs

- `0x180062507`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800624dc  push    rbx
0x1800624de  push    rbp
0x1800624df  push    rsi
0x1800624e0  push    rdi
0x1800624e1  push    r12
0x1800624e3  push    r14
0x1800624e5  push    r15
0x1800624e7  sub     rsp, 20h
0x1800624eb  xor     r12d, r12d
0x1800624ee  mov     rdi, r8
0x1800624f1  mov     rbp, rdx
0x1800624f4  mov     r14, rcx
0x1800624f7  test    rdx, rdx
0x1800624fa  jnz     short loc_18006251E
0x1800624fc  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180062500  jnz     short loc_180062519
0x180062502  mov     rcx, [rsp+58h]; this
0x180062507  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18006250e  mov     edx, 0F89h; void *
0x180062513  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180062519  mov     rbx, rdi
0x18006251c  jmp     short loc_180062553
0x18006251e  mov     ecx, 7FFFFFFFh
0x180062523  mov     rax, rdi
0x180062526  cmp     rdi, rcx
0x180062529  mov     rbx, rbp
0x18006252c  cmovnb  rax, rcx
0x180062530  test    rax, rax
0x180062533  jz      short loc_180062545
0x180062535  cmp     [rbx], r12w
0x180062539  jz      short loc_180062545
0x18006253b  add     rbx, 2
0x18006253f  sub     rax, 1
0x180062543  jnz     short loc_180062535
0x180062545  sub     rbx, rbp
0x180062548  sar     rbx, 1
0x18006254b  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18006254f  cmovz   rdi, rbx
0x180062553  lea     r15, ds:2[rdi*2]
0x18006255b  call    cs:__imp_GetProcessHeap
0x180062561  mov     r8, r15; dwBytes
0x180062564  mov     edx, 8; dwFlags
0x180062569  mov     rcx, rax; hHeap
0x18006256c  call    cs:__imp_HeapAlloc
0x180062572  mov     rsi, rax
0x180062575  test    rax, rax
0x180062578  jz      short loc_1800625A3
0x18006257a  test    rbp, rbp
0x18006257d  jz      short loc_18006259A
0x18006257f  add     rbx, rbx
0x180062582  mov     r8, rbp; Source
0x180062585  mov     r9, rbx; SourceSize
0x180062588  mov     rdx, r15; DestinationSize
0x18006258b  mov     rcx, rax; Destination
0x18006258e  call    memcpy_s_1
0x180062593  mov     [rbx+rsi], r12w
0x180062598  jmp     short loc_18006259E
0x18006259a  mov     [rax], r12w
0x18006259e  mov     [rsi+rdi*2], r12w
0x1800625a3  mov     [r14], rsi
0x1800625a6  mov     rax, r14
0x1800625a9  add     rsp, 20h
0x1800625ad  pop     r15
0x1800625af  pop     r14
0x1800625b1  pop     r12
0x1800625b3  pop     rdi
0x1800625b4  pop     rsi
0x1800625b5  pop     rbp
0x1800625b6  pop     rbx
0x1800625b7  retn
```
