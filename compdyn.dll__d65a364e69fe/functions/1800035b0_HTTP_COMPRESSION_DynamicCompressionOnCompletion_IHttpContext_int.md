# HTTP_COMPRESSION::DynamicCompressionOnCompletion(IHttpContext *,int *)

- ea: `0x1800035b0`
- end: `0x180003614`
- name: `?DynamicCompressionOnCompletion@HTTP_COMPRESSION@@SAJPEAVIHttpContext@@PEAH@Z`
- size: `100`
- prototype: `__int64 __fastcall(struct IHttpContext *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001a60`

## callees

- `0x180002820`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall HTTP_COMPRESSION::DynamicCompressionOnCompletion(struct IHttpContext *a1, int *a2)
{
  __int64 v4; // rax
  __int64 (__fastcall ***v5)(_QWORD, void *); // rax
  struct COMPRESSION_CONTEXT *v6; // rax

  v4 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 240LL))(a1);
  v5 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 56LL))(v4);
  v6 = (struct COMPRESSION_CONTEXT *)(**v5)(v5, g_pModuleContext);
  return HTTP_COMPRESSION::DoDynamicCompression(a1, v6, 1, a2);
}

```

## disassembly

```asm
0x1800035b0  mov     [rsp+arg_0], rbx
0x1800035b5  push    rdi
0x1800035b6  sub     rsp, 20h
0x1800035ba  mov     rax, [rcx]
0x1800035bd  mov     rbx, rdx
0x1800035c0  mov     rdi, rcx
0x1800035c3  mov     rax, [rax+0F0h]
0x1800035ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035cf  mov     rcx, rax
0x1800035d2  mov     r8, [rax]
0x1800035d5  mov     rax, [r8+38h]
0x1800035d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035de  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x1800035e5  mov     r8, rax
0x1800035e8  mov     rcx, [rax]
0x1800035eb  mov     rax, [rcx]
0x1800035ee  mov     rcx, r8
0x1800035f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f6  mov     r9, rbx; int *
0x1800035f9  mov     r8d, 1; int
0x1800035ff  mov     rdx, rax; struct COMPRESSION_CONTEXT *
0x180003602  mov     rcx, rdi; struct IHttpContext *
0x180003605  mov     rbx, [rsp+28h+arg_0]
0x18000360a  add     rsp, 20h
0x18000360e  pop     rdi
0x18000360f  jmp     ?DoDynamicCompression@HTTP_COMPRESSION@@CAJPEAVIHttpContext@@PEAVCOMPRESSION_CONTEXT@@HPEAH@Z; HTTP_COMPRESSION::DoDynamicCompression(IHttpContext *,COMPRESSION_CONTEXT *,int,int *)
```
