# W3_CONTEXT::CloneContext(ulong,IHttpContext * *)

- ea: `0x18001fa60`
- end: `0x18001fb8a`
- name: `?CloneContext@W3_CONTEXT@@UEAAJKPEAPEAVIHttpContext@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(W3_CONTEXT *__hidden this, unsigned int, struct IHttpContext **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x1800023e0`
- `0x18001fa60`
- `0x18001fb90`
- `0x18002488c`
- `0x18002701c`
- `0x18003439a`
- `0x180035010`

## import_xrefs

- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18001fa89`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18001fa89`

## pseudocode

```c
__int64 __fastcall W3_CONTEXT::CloneContext(struct W3_REQUEST **this, unsigned int a2, struct IHttpContext **a3)
{
  char *v7; // rax
  char *v8; // rdi
  void *v9; // rbx
  int v10; // ebx
  struct W3_RESPONSE *v11; // rdx

  if ( !a3 )
    return 2147942487LL;
  v7 = (char *)ALLOC_CACHE_HANDLER::Alloc(W3_CHILD_CONTEXT::sm_pachCloneContexts);
  v8 = v7;
  if ( v7 )
  {
    v9 = v7 + 9344;
    W3_CONTEXT::W3_CONTEXT(
      (W3_CONTEXT *)v7,
      (struct _HTTP_REQUEST_V2 *)(v7 + 9344),
      (struct W3_CONTEXT *)this,
      *((_DWORD *)this + 2020) + 1);
    *(_QWORD *)v8 = &W3_CHILD_CONTEXT::`vftable'{for `IHttpContext4'};
    *((_QWORD *)v8 + 1) = &W3_CHILD_CONTEXT::`vftable'{for `IHttpTraceContext'};
    *((_QWORD *)v8 + 2) = &W3_CHILD_CONTEXT::`vftable'{for `IMapHandlerProvider'};
    *((_QWORD *)v8 + 3) = &W3_CHILD_CONTEXT::`vftable'{for `IModuleAllocator'};
    *((_QWORD *)v8 + 4) = &W3_CHILD_CONTEXT::`vftable'{for `IAuthenticationProvider'};
    memset_0(v9, 0, 0x360u);
    v10 = W3_REQUEST::CloneFromRequest(*((W3_REQUEST **)v8 + 6), this[6], a2);
    if ( v10 >= 0 )
    {
      v11 = this[8];
      if ( v11 )
      {
        v10 = 0;
        if ( (a2 & 0x20) != 0 )
          v10 = W3_RESPONSE::CopyUserCachePolicyVaryBy(*((W3_RESPONSE **)v8 + 8), v11);
        if ( v10 >= 0 )
        {
          if ( (a2 & 0x40) == 0
            || (v10 = W3_CONTEXT::CloneServerVariable((W3_CONTEXT *)v8, (struct W3_CONTEXT *)this), v10 >= 0) )
          {
            *((_QWORD *)v8 + 10) = this[10];
            *a3 = (struct IHttpContext *)v8;
            return (unsigned int)v10;
          }
        }
      }
      else
      {
        v10 = -2147024809;
      }
    }
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v8 + 392LL))(v8, 1);
    return (unsigned int)v10;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x18001fa60  push    rbx
0x18001fa62  push    rbp
0x18001fa63  push    rsi
0x18001fa64  push    rdi
0x18001fa65  push    r14
0x18001fa67  sub     rsp, 20h
0x18001fa6b  mov     r14, r8
0x18001fa6e  mov     ebp, edx
0x18001fa70  mov     rsi, rcx
0x18001fa73  test    r8, r8
0x18001fa76  jnz     short loc_18001FA82
0x18001fa78  mov     eax, 80070057h
0x18001fa7d  jmp     loc_18001FB7F
0x18001fa82  mov     rcx, cs:?sm_pachCloneContexts@W3_CHILD_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_CHILD_CONTEXT::sm_pachCloneContexts
0x18001fa89  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18001fa8f  mov     rdi, rax
0x18001fa92  test    rax, rax
0x18001fa95  jz      loc_18001FB7A
0x18001fa9b  mov     r9d, [rsi+1F90h]
0x18001faa2  lea     rbx, [rax+2480h]
0x18001faa9  inc     r9d; unsigned int
0x18001faac  mov     rdx, rbx; struct _HTTP_REQUEST_V2 *
0x18001faaf  mov     r8, rsi; struct W3_CONTEXT *
0x18001fab2  mov     rcx, rax; this
0x18001fab5  call    ??0W3_CONTEXT@@QEAA@PEAU_HTTP_REQUEST_V2@@PEAV0@K@Z; W3_CONTEXT::W3_CONTEXT(_HTTP_REQUEST_V2 *,W3_CONTEXT *,ulong)
0x18001faba  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIHttpContext4@@@; const W3_CHILD_CONTEXT::`vftable'{for `IHttpContext4'}
0x18001fac1  xor     edx, edx; Val
0x18001fac3  mov     [rdi], rax
0x18001fac6  mov     r8d, 360h; Size
0x18001facc  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIHttpTraceContext@@@; const W3_CHILD_CONTEXT::`vftable'{for `IHttpTraceContext'}
0x18001fad3  mov     rcx, rbx; void *
0x18001fad6  mov     [rdi+8], rax
0x18001fada  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIMapHandlerProvider@@@; const W3_CHILD_CONTEXT::`vftable'{for `IMapHandlerProvider'}
0x18001fae1  mov     [rdi+10h], rax
0x18001fae5  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIModuleAllocator@@@; const W3_CHILD_CONTEXT::`vftable'{for `IModuleAllocator'}
0x18001faec  mov     [rdi+18h], rax
0x18001faf0  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIAuthenticationProvider@@@; const W3_CHILD_CONTEXT::`vftable'{for `IAuthenticationProvider'}
0x18001faf7  mov     [rdi+20h], rax
0x18001fafb  call    memset_0
0x18001fb00  mov     rdx, [rsi+30h]; struct W3_REQUEST *
0x18001fb04  mov     r8d, ebp; unsigned int
0x18001fb07  mov     rcx, [rdi+30h]; this
0x18001fb0b  call    ?CloneFromRequest@W3_REQUEST@@QEAAJPEAV1@K@Z; W3_REQUEST::CloneFromRequest(W3_REQUEST *,ulong)
0x18001fb10  mov     ebx, eax
0x18001fb12  test    eax, eax
0x18001fb14  js      short loc_18001FB24
0x18001fb16  mov     rdx, [rsi+40h]; struct W3_RESPONSE *
0x18001fb1a  test    rdx, rdx
0x18001fb1d  jnz     short loc_18001FB3F
0x18001fb1f  mov     ebx, 80070057h
0x18001fb24  mov     rax, [rdi]
0x18001fb27  mov     edx, 1
0x18001fb2c  mov     rcx, rdi
0x18001fb2f  mov     rax, [rax+188h]
0x18001fb36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb3b  mov     eax, ebx
0x18001fb3d  jmp     short loc_18001FB7F
0x18001fb3f  xor     ebx, ebx
0x18001fb41  test    bpl, 20h
0x18001fb45  jz      short loc_18001FB52
0x18001fb47  mov     rcx, [rdi+40h]; this
0x18001fb4b  call    ?CopyUserCachePolicyVaryBy@W3_RESPONSE@@QEAAJPEAV1@@Z; W3_RESPONSE::CopyUserCachePolicyVaryBy(W3_RESPONSE *)
0x18001fb50  mov     ebx, eax
0x18001fb52  test    ebx, ebx
0x18001fb54  js      short loc_18001FB24
0x18001fb56  test    bpl, 40h
0x18001fb5a  jz      short loc_18001FB6D
0x18001fb5c  mov     rdx, rsi; struct W3_CONTEXT *
0x18001fb5f  mov     rcx, rdi; this
0x18001fb62  call    ?CloneServerVariable@W3_CONTEXT@@AEAAJPEAV1@@Z; W3_CONTEXT::CloneServerVariable(W3_CONTEXT *)
0x18001fb67  mov     ebx, eax
0x18001fb69  test    eax, eax
0x18001fb6b  js      short loc_18001FB24
0x18001fb6d  mov     rax, [rsi+50h]
0x18001fb71  mov     [rdi+50h], rax
0x18001fb75  mov     [r14], rdi
0x18001fb78  jmp     short loc_18001FB3B
0x18001fb7a  mov     eax, 80070008h
0x18001fb7f  add     rsp, 20h
0x18001fb83  pop     r14
0x18001fb85  pop     rdi
0x18001fb86  pop     rsi
0x18001fb87  pop     rbp
0x18001fb88  pop     rbx
0x18001fb89  retn
```
