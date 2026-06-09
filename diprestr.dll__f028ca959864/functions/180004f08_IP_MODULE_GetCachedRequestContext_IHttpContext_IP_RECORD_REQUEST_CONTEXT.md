# IP_MODULE::GetCachedRequestContext(IHttpContext *,IP_RECORD * *,REQUEST_CONTEXT * *)

- ea: `0x180004f08`
- end: `0x180004f83`
- name: `?GetCachedRequestContext@IP_MODULE@@CAJPEAVIHttpContext@@PEAPEAVIP_RECORD@@PEAPEAVREQUEST_CONTEXT@@@Z`
- size: `123`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct IP_RECORD **, struct REQUEST_CONTEXT **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004630`
- `0x180006460`

## callees

- `0x180004f08`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall IP_MODULE::GetCachedRequestContext(
        struct IHttpContext *a1,
        struct IP_RECORD **a2,
        struct REQUEST_CONTEXT **a3)
{
  __int64 (__fastcall ***v5)(_QWORD, void *); // rax
  struct REQUEST_CONTEXT *v6; // rcx
  __int64 result; // rax
  volatile signed __int32 *v8; // rcx

  *a3 = 0;
  if ( a2 )
    *a2 = 0;
  v5 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 56LL))(a1);
  v6 = (struct REQUEST_CONTEXT *)(**v5)(v5, g_pModuleID);
  if ( !v6 )
    return 2147942402LL;
  result = 0;
  *a3 = v6;
  if ( a2 )
  {
    v8 = (volatile signed __int32 *)*((_QWORD *)v6 + 2);
    if ( v8 )
    {
      _InterlockedIncrement(v8 + 6);
      *a2 = (struct IP_RECORD *)v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004f08  mov     [rsp+arg_0], rbx
0x180004f0d  push    rdi
0x180004f0e  sub     rsp, 20h
0x180004f12  mov     qword ptr [r8], 0
0x180004f19  mov     rdi, r8
0x180004f1c  mov     rbx, rdx
0x180004f1f  test    rdx, rdx
0x180004f22  jz      short loc_180004F2B
0x180004f24  mov     qword ptr [rdx], 0
0x180004f2b  mov     rax, [rcx]
0x180004f2e  mov     rax, [rax+38h]
0x180004f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f37  mov     rdx, cs:?g_pModuleID@@3PEAXEA; void * g_pModuleID
0x180004f3e  mov     r8, rax
0x180004f41  mov     rcx, [rax]
0x180004f44  mov     rax, [rcx]
0x180004f47  mov     rcx, r8
0x180004f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f4f  mov     rcx, rax
0x180004f52  test    rax, rax
0x180004f55  jnz     short loc_180004F5E
0x180004f57  mov     eax, 80070002h
0x180004f5c  jmp     short loc_180004F78
0x180004f5e  xor     eax, eax
0x180004f60  mov     [rdi], rcx
0x180004f63  test    rbx, rbx
0x180004f66  jz      short loc_180004F78
0x180004f68  mov     rcx, [rcx+10h]
0x180004f6c  test    rcx, rcx
0x180004f6f  jz      short loc_180004F78
0x180004f71  lock inc dword ptr [rcx+18h]
0x180004f75  mov     [rbx], rcx
0x180004f78  mov     rbx, [rsp+28h+arg_0]
0x180004f7d  add     rsp, 20h
0x180004f81  pop     rdi
0x180004f82  retn
```
