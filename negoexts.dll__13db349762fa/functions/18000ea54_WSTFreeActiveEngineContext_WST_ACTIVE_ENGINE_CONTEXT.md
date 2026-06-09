# WSTFreeActiveEngineContext(_WST_ACTIVE_ENGINE_CONTEXT *)

- ea: `0x18000ea54`
- end: `0x18000eb79`
- name: `?WSTFreeActiveEngineContext@@YAXPEAU_WST_ACTIVE_ENGINE_CONTEXT@@@Z`
- size: `293`
- prototype: `void __fastcall(struct _WST_ACTIVE_ENGINE_CONTEXT *, __int64, unsigned int)`
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x180001414`
- `0x180003500`
- `0x1800070d0`
- `0x180008e60`
- `0x18001a3b4`

## callees

- `0x1800028a0`
- `0x1800028f0`
- `0x180008544`
- `0x180008c58`
- `0x18000ea54`
- `0x18001a390`
- `0x18001e17c`
- `0x180020010`

## pseudocode

```c
void __fastcall WSTFreeActiveEngineContext(struct _WST_ACTIVE_ENGINE_CONTEXT *a1, __int64 a2, unsigned int a3)
{
  _QWORD *v4; // rsi
  struct _WST_SSP_PACKAGE *v5; // rax
  struct _WST_SSP_PACKAGE *v6; // rdi
  void (*v7)(void); // rax
  void (*v8)(void); // rax
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rdx

  if ( a1 )
  {
    v4 = (_QWORD *)((char *)a1 + 40);
    if ( *((_QWORD *)a1 + 5) || *((_QWORD *)a1 + 6) )
    {
      v5 = WSTLocatePackageByAuthScheme((struct _GUID *)((char *)a1 + 24));
      v6 = v5;
      if ( v5 )
      {
        v7 = (void (*)(void))*((_QWORD *)v5 + 24);
        if ( v7 && *v4 )
        {
          v7();
          *v4 = 0;
        }
        v8 = (void (*)(void))*((_QWORD *)v6 + 18);
        if ( v8 && *((_QWORD *)a1 + 6) )
        {
          v8();
          *((_QWORD *)a1 + 6) = 0;
        }
        WSTDereferencePackage(v6);
      }
    }
    v9 = (void *)*((_QWORD *)a1 + 13);
    if ( v9 )
      WSTFree(v9);
    *(_OWORD *)((char *)a1 + 88) = 0;
    *((_QWORD *)a1 + 13) = 0;
    v10 = (void *)*((_QWORD *)a1 + 16);
    if ( v10 )
      WSTFree(v10);
    *((_OWORD *)a1 + 7) = 0;
    *((_QWORD *)a1 + 16) = 0;
    v11 = (void *)*((_QWORD *)a1 + 8);
    if ( v11 )
    {
      basessp::BaseSSP::WSTFree2((basessp::BaseSSP *)v10, v11);
      *(_OWORD *)((char *)a1 + 56) = 0;
    }
    basessp::WSTLowerCase((struct _WST_ACTIVE_ENGINE_CONTEXT *)((char *)a1 + 16), (unsigned __int8 *)v11, a3);
    WSTFree(a1);
  }
}

```

## disassembly

```asm
0x18000ea54  test    rcx, rcx
0x18000ea57  jz      locret_18000EB78
0x18000ea5d  mov     [rsp+arg_0], rcx
0x18000ea62  push    rbx
0x18000ea63  push    rsi
0x18000ea64  push    rdi
0x18000ea65  sub     rsp, 20h
0x18000ea69  mov     rbx, rcx
0x18000ea6c  lea     rsi, [rcx+28h]
0x18000ea70  mov     [rsp+38h+arg_10], rsi
0x18000ea75  cmp     qword ptr [rsi], 0
0x18000ea79  jnz     short loc_18000EA86
0x18000ea7b  cmp     qword ptr [rcx+30h], 0
0x18000ea80  jz      loc_18000EB0F
0x18000ea86  add     rcx, 18h; struct _GUID *
0x18000ea8a  call    ?WSTLocatePackageByAuthScheme@@YAPEAU_WST_SSP_PACKAGE@@PEAU_GUID@@@Z; WSTLocatePackageByAuthScheme(_GUID *)
0x18000ea8f  mov     rdi, rax
0x18000ea92  mov     [rsp+38h+arg_8], rax
0x18000ea97  test    rax, rax
0x18000ea9a  jz      short loc_18000EB0F
0x18000ea9c  mov     rax, [rax+0C0h]
0x18000eaa3  test    rax, rax
0x18000eaa6  jz      short loc_18000EACD
0x18000eaa8  mov     rcx, [rsi]
0x18000eaab  test    rcx, rcx
0x18000eaae  jz      short loc_18000EACD
0x18000eab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eab5  jmp     short loc_18000EAC6
0x18000eab7  mov     rbx, [rsp+38h+arg_0]
0x18000eabc  mov     rdi, [rsp+38h+arg_8]
0x18000eac1  mov     rsi, [rsp+38h+arg_10]
0x18000eac6  mov     qword ptr [rsi], 0
0x18000eacd  mov     rax, [rdi+90h]
0x18000ead4  test    rax, rax
0x18000ead7  jz      short loc_18000EB07
0x18000ead9  lea     rsi, [rbx+30h]
0x18000eadd  mov     [rsp+38h+arg_10], rsi
0x18000eae2  mov     rcx, [rsi]
0x18000eae5  test    rcx, rcx
0x18000eae8  jz      short loc_18000EB07
0x18000eaea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaef  jmp     short loc_18000EB00
0x18000eaf1  mov     rbx, [rsp+38h+arg_0]
0x18000eaf6  mov     rdi, [rsp+38h+arg_8]
0x18000eafb  mov     rsi, [rsp+38h+arg_10]
0x18000eb00  mov     qword ptr [rsi], 0
0x18000eb07  mov     rcx, rdi; struct _WST_SSP_PACKAGE *
0x18000eb0a  call    ?WSTDereferencePackage@@YAXPEAU_WST_SSP_PACKAGE@@@Z; WSTDereferencePackage(_WST_SSP_PACKAGE *)
0x18000eb0f  mov     rcx, [rbx+68h]; void *
0x18000eb13  test    rcx, rcx
0x18000eb16  jz      short loc_18000EB1D
0x18000eb18  call    ?WSTFree@@YAXPEAX@Z; WSTFree(void *)
0x18000eb1d  xorps   xmm0, xmm0
0x18000eb20  xor     eax, eax
0x18000eb22  movups  xmmword ptr [rbx+58h], xmm0
0x18000eb26  mov     [rbx+68h], rax
0x18000eb2a  mov     rcx, [rbx+80h]; void *
0x18000eb31  test    rcx, rcx
0x18000eb34  jz      short loc_18000EB3B
0x18000eb36  call    ?WSTFree@@YAXPEAX@Z; WSTFree(void *)
0x18000eb3b  xorps   xmm0, xmm0
0x18000eb3e  xor     eax, eax
0x18000eb40  movups  xmmword ptr [rbx+70h], xmm0
0x18000eb44  mov     [rbx+80h], rax
0x18000eb4b  mov     rdx, [rbx+40h]; void *
0x18000eb4f  test    rdx, rdx
0x18000eb52  jz      short loc_18000EB60
0x18000eb54  call    ?WSTFree2@BaseSSP@basessp@@QEAAXPEAX@Z; basessp::BaseSSP::WSTFree2(void *)
0x18000eb59  xorps   xmm0, xmm0
0x18000eb5c  movups  xmmword ptr [rbx+38h], xmm0
0x18000eb60  lea     rcx, [rbx+10h]; this
0x18000eb64  call    ?WSTLowerCase@basessp@@YAXPEAEK@Z; basessp::WSTLowerCase(uchar *,ulong)
0x18000eb69  mov     rcx, rbx; void *
0x18000eb6c  call    ?WSTFree@@YAXPEAX@Z; WSTFree(void *)
0x18000eb71  add     rsp, 20h
0x18000eb75  pop     rdi
0x18000eb76  pop     rsi
0x18000eb77  pop     rbx
0x18000eb78  retn
0x18001efdc  push    rbp
0x18001efde  sub     rsp, 20h
0x18001efe2  mov     rbp, rdx
0x18001efe5  call    ?WSTExceptionFilter@@YAKXZ; WSTExceptionFilter(void)
0x18001efea  nop
0x18001efeb  add     rsp, 20h
0x18001efef  pop     rbp
0x18001eff0  retn
0x18001eff2  push    rbp
0x18001eff4  sub     rsp, 20h
0x18001eff8  mov     rbp, rdx
0x18001effb  call    ?WSTExceptionFilter@@YAKXZ; WSTExceptionFilter(void)
0x18001f000  nop
0x18001f001  add     rsp, 20h
0x18001f005  pop     rbp
0x18001f006  retn
```
