# W3_CONTEXT::CloneContext(ulong,IHttpContext * *)

- ea: `0x180021660`
- end: `0x180021791`
- name: `?CloneContext@W3_CONTEXT@@UEAAJKPEAPEAVIHttpContext@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(W3_CONTEXT *__hidden this, unsigned int, struct IHttpContext **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x1800024c0`
- `0x180021660`
- `0x180021798`
- `0x18002676c`
- `0x18002910c`
- `0x18003773a`
- `0x180038010`

## import_xrefs

- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180021689`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180021689`

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
0x180021660  push    rbx
0x180021662  push    rbp
0x180021663  push    rsi
0x180021664  push    rdi
0x180021665  push    r14
0x180021667  sub     rsp, 20h
0x18002166b  mov     r14, r8
0x18002166e  mov     ebp, edx
0x180021670  mov     rsi, rcx
0x180021673  test    r8, r8
0x180021676  jnz     short loc_180021682
0x180021678  mov     eax, 80070057h
0x18002167d  jmp     loc_180021785
0x180021682  mov     rcx, cs:?sm_pachCloneContexts@W3_CHILD_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_CHILD_CONTEXT::sm_pachCloneContexts
0x180021689  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180021690  nop     dword ptr [rax+rax+00h]
0x180021695  mov     rdi, rax
0x180021698  test    rax, rax
0x18002169b  jz      loc_180021780
0x1800216a1  mov     r9d, [rsi+1F90h]
0x1800216a8  lea     rbx, [rax+2480h]
0x1800216af  inc     r9d; unsigned int
0x1800216b2  mov     rdx, rbx; struct _HTTP_REQUEST_V2 *
0x1800216b5  mov     r8, rsi; struct W3_CONTEXT *
0x1800216b8  mov     rcx, rax; this
0x1800216bb  call    ??0W3_CONTEXT@@QEAA@PEAU_HTTP_REQUEST_V2@@PEAV0@K@Z; W3_CONTEXT::W3_CONTEXT(_HTTP_REQUEST_V2 *,W3_CONTEXT *,ulong)
0x1800216c0  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIHttpContext4@@@; const W3_CHILD_CONTEXT::`vftable'{for `IHttpContext4'}
0x1800216c7  xor     edx, edx; Val
0x1800216c9  mov     [rdi], rax
0x1800216cc  mov     r8d, 360h; Size
0x1800216d2  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIHttpTraceContext@@@; const W3_CHILD_CONTEXT::`vftable'{for `IHttpTraceContext'}
0x1800216d9  mov     rcx, rbx; void *
0x1800216dc  mov     [rdi+8], rax
0x1800216e0  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIMapHandlerProvider@@@; const W3_CHILD_CONTEXT::`vftable'{for `IMapHandlerProvider'}
0x1800216e7  mov     [rdi+10h], rax
0x1800216eb  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIModuleAllocator@@@; const W3_CHILD_CONTEXT::`vftable'{for `IModuleAllocator'}
0x1800216f2  mov     [rdi+18h], rax
0x1800216f6  lea     rax, ??_7W3_CHILD_CONTEXT@@6BIAuthenticationProvider@@@; const W3_CHILD_CONTEXT::`vftable'{for `IAuthenticationProvider'}
0x1800216fd  mov     [rdi+20h], rax
0x180021701  call    memset_0
0x180021706  mov     rdx, [rsi+30h]; struct W3_REQUEST *
0x18002170a  mov     r8d, ebp; unsigned int
0x18002170d  mov     rcx, [rdi+30h]; this
0x180021711  call    ?CloneFromRequest@W3_REQUEST@@QEAAJPEAV1@K@Z; W3_REQUEST::CloneFromRequest(W3_REQUEST *,ulong)
0x180021716  mov     ebx, eax
0x180021718  test    eax, eax
0x18002171a  js      short loc_18002172A
0x18002171c  mov     rdx, [rsi+40h]; struct W3_RESPONSE *
0x180021720  test    rdx, rdx
0x180021723  jnz     short loc_180021745
0x180021725  mov     ebx, 80070057h
0x18002172a  mov     rax, [rdi]
0x18002172d  mov     edx, 1
0x180021732  mov     rcx, rdi
0x180021735  mov     rax, [rax+188h]
0x18002173c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021741  mov     eax, ebx
0x180021743  jmp     short loc_180021785
0x180021745  xor     ebx, ebx
0x180021747  test    bpl, 20h
0x18002174b  jz      short loc_180021758
0x18002174d  mov     rcx, [rdi+40h]; this
0x180021751  call    ?CopyUserCachePolicyVaryBy@W3_RESPONSE@@QEAAJPEAV1@@Z; W3_RESPONSE::CopyUserCachePolicyVaryBy(W3_RESPONSE *)
0x180021756  mov     ebx, eax
0x180021758  test    ebx, ebx
0x18002175a  js      short loc_18002172A
0x18002175c  test    bpl, 40h
0x180021760  jz      short loc_180021773
0x180021762  mov     rdx, rsi; struct W3_CONTEXT *
0x180021765  mov     rcx, rdi; this
0x180021768  call    ?CloneServerVariable@W3_CONTEXT@@AEAAJPEAV1@@Z; W3_CONTEXT::CloneServerVariable(W3_CONTEXT *)
0x18002176d  mov     ebx, eax
0x18002176f  test    eax, eax
0x180021771  js      short loc_18002172A
0x180021773  mov     rax, [rsi+50h]
0x180021777  mov     [rdi+50h], rax
0x18002177b  mov     [r14], rdi
0x18002177e  jmp     short loc_180021741
0x180021780  mov     eax, 80070008h
0x180021785  add     rsp, 20h
0x180021789  pop     r14
0x18002178b  pop     rdi
0x18002178c  pop     rsi
0x18002178d  pop     rbp
0x18002178e  pop     rbx
0x18002178f  retn
```
