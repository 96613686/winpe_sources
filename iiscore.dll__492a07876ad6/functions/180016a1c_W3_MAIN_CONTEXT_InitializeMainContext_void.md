# W3_MAIN_CONTEXT::InitializeMainContext(void)

- ea: `0x180016a1c`
- end: `0x180016abe`
- name: `?InitializeMainContext@W3_MAIN_CONTEXT@@QEAAJXZ`
- size: `162`
- prototype: `__int64 __fastcall(W3_MAIN_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180034700`

## callees

- `0x180016a1c`

## import_xrefs

- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180016a83`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180016a83`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180016a4c`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180016a4c`

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
0x180016a1c  push    rbx
0x180016a1e  push    rbp
0x180016a1f  push    rsi
0x180016a20  push    rdi
0x180016a21  sub     rsp, 28h
0x180016a25  mov     rax, [rcx+30h]
0x180016a29  mov     rdi, rcx
0x180016a2c  mov     rsi, [rax+28h]
0x180016a30  mov     rax, [rsi+348h]
0x180016a37  test    rax, rax
0x180016a3a  jz      short loc_180016A9B
0x180016a3c  mov     rbp, [rax+20h]
0x180016a40  test    rbp, rbp
0x180016a43  jz      short loc_180016A9B
0x180016a45  mov     rcx, cs:?sm_pachCertContexts@CERTIFICATE_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CERTIFICATE_CONTEXT::sm_pachCertContexts
0x180016a4c  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180016a53  nop     dword ptr [rax+rax+00h]
0x180016a58  mov     rbx, rax
0x180016a5b  test    rax, rax
0x180016a5e  jz      short loc_180016AB3
0x180016a60  lea     rax, ??_7CERTIFICATE_CONTEXT@@6B@; const CERTIFICATE_CONTEXT::`vftable'
0x180016a67  mov     [rbx+8], rbp
0x180016a6b  lea     rdx, [rbx+48h]
0x180016a6f  mov     [rbx], rax
0x180016a72  lea     rcx, [rbx+18h]
0x180016a76  mov     dword ptr [rbx+10h], 0
0x180016a7d  mov     r8d, 0D0h
0x180016a83  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180016a8a  nop     dword ptr [rax+rax+00h]
0x180016a8f  mov     [rdi+2508h], rbx
0x180016a96  test    rbx, rbx
0x180016a99  jz      short loc_180016AB7
0x180016a9b  mov     eax, [rsi+328h]
0x180016aa1  mov     [rdi+2514h], eax
0x180016aa7  xor     eax, eax
0x180016aa9  add     rsp, 28h
0x180016aad  pop     rdi
0x180016aae  pop     rsi
0x180016aaf  pop     rbp
0x180016ab0  pop     rbx
0x180016ab1  retn
0x180016ab3  xor     ebx, ebx
0x180016ab5  jmp     short loc_180016A8F
0x180016ab7  mov     eax, 80070008h
0x180016abc  jmp     short loc_180016AA9
```
