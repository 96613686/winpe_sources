# W3_MAIN_CONTEXT::InitializeMainContext(void)

- ea: `0x180015858`
- end: `0x1800158ed`
- name: `?InitializeMainContext@W3_MAIN_CONTEXT@@QEAAJXZ`
- size: `149`
- prototype: `__int64 __fastcall(W3_MAIN_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800318e0`

## callees

- `0x180015858`

## import_xrefs

- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800158b9`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800158b9`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180015888`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180015888`

## pseudocode

```c
__int64 __fastcall W3_MAIN_CONTEXT::InitializeMainContext(W3_MAIN_CONTEXT *this)
{
  __int64 v2; // rsi
  __int64 v3; // rax
  __int64 v4; // rbp
  char *v5; // rbx

  v2 = *(_QWORD *)(*((_QWORD *)this + 6) + 40LL);
  v3 = *(_QWORD *)(v2 + 840);
  if ( v3 )
  {
    v4 = *(_QWORD *)(v3 + 32);
    if ( v4 )
    {
      v5 = (char *)ALLOC_CACHE_HANDLER::Alloc(CERTIFICATE_CONTEXT::sm_pachCertContexts);
      if ( v5 )
      {
        *((_QWORD *)v5 + 1) = v4;
        *(_QWORD *)v5 = &CERTIFICATE_CONTEXT::`vftable';
        *((_DWORD *)v5 + 4) = 0;
        BUFFER::BUFFER((BUFFER *)(v5 + 24), (unsigned __int8 *)v5 + 72, 0xD0u);
      }
      else
      {
        v5 = 0;
      }
      *((_QWORD *)this + 1185) = v5;
      if ( !v5 )
        return 2147942408LL;
    }
  }
  *((_DWORD *)this + 2373) = *(_DWORD *)(v2 + 808);
  return 0;
}

```

## disassembly

```asm
0x180015858  push    rbx
0x18001585a  push    rbp
0x18001585b  push    rsi
0x18001585c  push    rdi
0x18001585d  sub     rsp, 28h
0x180015861  mov     rax, [rcx+30h]
0x180015865  mov     rdi, rcx
0x180015868  mov     rsi, [rax+28h]
0x18001586c  mov     rax, [rsi+348h]
0x180015873  test    rax, rax
0x180015876  jz      short loc_1800158CB
0x180015878  mov     rbp, [rax+20h]
0x18001587c  test    rbp, rbp
0x18001587f  jz      short loc_1800158CB
0x180015881  mov     rcx, cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CERTIFICATE_CONTEXT::sm_pachCertContexts
0x180015888  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18001588e  mov     rbx, rax
0x180015891  test    rax, rax
0x180015894  jz      short loc_1800158E2
0x180015896  lea     rax, ??_7CERTIFICATE_CONTEXT@@6B@; const CERTIFICATE_CONTEXT::`vftable'
0x18001589d  mov     [rbx+8], rbp
0x1800158a1  lea     rdx, [rbx+48h]
0x1800158a5  mov     [rbx], rax
0x1800158a8  lea     rcx, [rbx+18h]
0x1800158ac  mov     dword ptr [rbx+10h], 0
0x1800158b3  mov     r8d, 0D0h
0x1800158b9  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x1800158bf  mov     [rdi+2508h], rbx
0x1800158c6  test    rbx, rbx
0x1800158c9  jz      short loc_1800158E6
0x1800158cb  mov     eax, [rsi+328h]
0x1800158d1  mov     [rdi+2514h], eax
0x1800158d7  xor     eax, eax
0x1800158d9  add     rsp, 28h
0x1800158dd  pop     rdi
0x1800158de  pop     rsi
0x1800158df  pop     rbp
0x1800158e0  pop     rbx
0x1800158e1  retn
0x1800158e2  xor     ebx, ebx
0x1800158e4  jmp     short loc_1800158BF
0x1800158e6  mov     eax, 80070008h
0x1800158eb  jmp     short loc_1800158D9
```
