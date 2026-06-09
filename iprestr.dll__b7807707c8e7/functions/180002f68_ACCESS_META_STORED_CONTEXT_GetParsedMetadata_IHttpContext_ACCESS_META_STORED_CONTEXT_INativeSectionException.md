# ACCESS_META_STORED_CONTEXT::GetParsedMetadata(IHttpContext *,ACCESS_META_STORED_CONTEXT * *,INativeSectionException * *)

- ea: `0x180002f68`
- end: `0x180003098`
- name: `?GetParsedMetadata@ACCESS_META_STORED_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAV1@PEAPEAVINativeSectionException@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct ACCESS_META_STORED_CONTEXT **, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002acc`

## callees

- `0x180001088`
- `0x180002f68`
- `0x1800030a0`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall ACCESS_META_STORED_CONTEXT::GetParsedMetadata(
        struct IHttpContext *a1,
        struct ACCESS_META_STORED_CONTEXT **a2,
        struct INativeSectionException **a3)
{
  __int64 v6; // rax
  __int64 v7; // rsi
  struct ACCESS_META_STORED_CONTEXT *v8; // rax
  _DWORD *v10; // rbx
  int v11; // edi

  v6 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 160LL))(a1);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
  v8 = (struct ACCESS_META_STORED_CONTEXT *)(**(__int64 (__fastcall ***)(__int64, void *))v7)(
                                              v7,
                                              g_pIpRestrictionModuleContext);
  if ( v8 )
  {
    *a2 = v8;
    return 0;
  }
  v10 = operator new(0x38u);
  if ( v10 )
  {
    v10[2] = 1;
    *(_QWORD *)v10 = &ACCESS_META_STORED_CONTEXT::`vftable';
    *((_QWORD *)v10 + 2) = 0;
    *((_QWORD *)v10 + 3) = 0;
    v10[8] = 0;
    *((_QWORD *)v10 + 5) = 0;
    v10[12] = 0;
    v11 = ACCESS_META_STORED_CONTEXT::InitializeIpRestrictionList((ACCESS_META_STORED_CONTEXT *)v10, a1, a3);
    if ( v11 < 0 )
    {
      (**(void (__fastcall ***)(void *))v10)(v10);
      return (unsigned int)v11;
    }
    v11 = (*(__int64 (__fastcall **)(__int64, _DWORD *, void *))(*(_QWORD *)v7 + 8LL))(
            v7,
            v10,
            g_pIpRestrictionModuleContext);
    if ( v11 < 0 )
    {
      (**(void (__fastcall ***)(void *))v10)(v10);
      if ( v11 != -2147024811 )
        return (unsigned int)v11;
      v10 = (_DWORD *)(**(__int64 (__fastcall ***)(__int64, void *))v7)(v7, g_pIpRestrictionModuleContext);
      v11 = 0;
    }
    *a2 = (struct ACCESS_META_STORED_CONTEXT *)v10;
    return (unsigned int)v11;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180002f68  push    rbx
0x180002f6a  push    rbp
0x180002f6b  push    rsi
0x180002f6c  push    rdi
0x180002f6d  push    r14
0x180002f6f  sub     rsp, 20h
0x180002f73  mov     rax, [rcx]
0x180002f76  mov     rbp, r8
0x180002f79  mov     r14, rdx
0x180002f7c  mov     rdi, rcx
0x180002f7f  mov     rax, [rax+0A0h]
0x180002f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f8b  mov     rcx, rax
0x180002f8e  mov     r9, [rax]
0x180002f91  mov     rax, [r9+18h]
0x180002f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f9a  mov     rdx, cs:?g_pIpRestrictionModuleContext@@3PEAXEA; void * g_pIpRestrictionModuleContext
0x180002fa1  mov     rsi, rax
0x180002fa4  mov     rcx, [rax]
0x180002fa7  mov     rax, [rcx]
0x180002faa  mov     rcx, rsi
0x180002fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fb2  test    rax, rax
0x180002fb5  jz      short loc_180002FC1
0x180002fb7  mov     [r14], rax
0x180002fba  xor     eax, eax
0x180002fbc  jmp     loc_18000308D
0x180002fc1  mov     ecx, 38h ; '8'; Size
0x180002fc6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002fcb  mov     rbx, rax
0x180002fce  test    rax, rax
0x180002fd1  jz      loc_180003088
0x180002fd7  lea     rax, ??_7ACCESS_META_STORED_CONTEXT@@6B@; const ACCESS_META_STORED_CONTEXT::`vftable'
0x180002fde  mov     dword ptr [rbx+8], 1
0x180002fe5  mov     r8, rbp; struct INativeSectionException **
0x180002fe8  mov     [rbx], rax
0x180002feb  mov     rdx, rdi; struct IHttpContext *
0x180002fee  mov     qword ptr [rbx+10h], 0
0x180002ff6  mov     rcx, rbx; this
0x180002ff9  mov     qword ptr [rbx+18h], 0
0x180003001  mov     dword ptr [rbx+20h], 0
0x180003008  mov     qword ptr [rbx+28h], 0
0x180003010  mov     dword ptr [rbx+30h], 0
0x180003017  call    ?InitializeIpRestrictionList@ACCESS_META_STORED_CONTEXT@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z; ACCESS_META_STORED_CONTEXT::InitializeIpRestrictionList(IHttpContext *,INativeSectionException * *)
0x18000301c  mov     edi, eax
0x18000301e  test    eax, eax
0x180003020  jns     short loc_180003034
0x180003022  mov     rcx, [rbx]
0x180003025  mov     rax, [rcx]
0x180003028  mov     rcx, rbx
0x18000302b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003030  mov     eax, edi
0x180003032  jmp     short loc_18000308D
0x180003034  mov     rax, [rsi]
0x180003037  mov     rdx, rbx
0x18000303a  mov     r8, cs:?g_pIpRestrictionModuleContext@@3PEAXEA; void * g_pIpRestrictionModuleContext
0x180003041  mov     rcx, rsi
0x180003044  mov     rax, [rax+8]
0x180003048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000304d  mov     edi, eax
0x18000304f  test    eax, eax
0x180003051  jns     short loc_180003083
0x180003053  mov     rcx, [rbx]
0x180003056  mov     rax, [rcx]
0x180003059  mov     rcx, rbx
0x18000305c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003061  cmp     edi, 80070055h
0x180003067  jnz     short loc_180003030
0x180003069  mov     rax, [rsi]
0x18000306c  mov     rcx, rsi
0x18000306f  mov     rdx, cs:?g_pIpRestrictionModuleContext@@3PEAXEA; void * g_pIpRestrictionModuleContext
0x180003076  mov     rax, [rax]
0x180003079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000307e  mov     rbx, rax
0x180003081  xor     edi, edi
0x180003083  mov     [r14], rbx
0x180003086  jmp     short loc_180003030
0x180003088  mov     eax, 80070008h
0x18000308d  add     rsp, 20h
0x180003091  pop     r14
0x180003093  pop     rdi
0x180003094  pop     rsi
0x180003095  pop     rbp
0x180003096  pop     rbx
0x180003097  retn
```
