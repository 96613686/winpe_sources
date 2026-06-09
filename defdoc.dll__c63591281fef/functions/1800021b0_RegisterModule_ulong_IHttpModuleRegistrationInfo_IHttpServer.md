# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x1800021b0`
- end: `0x180002237`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(__int64, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001008`
- `0x1800021b0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  _QWORD *v5; // rax
  int v6; // eax
  unsigned int v7; // ecx

  g_pDefaultDocModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  g_pGlobalInfo = a3;
  v5 = operator new(0x10u);
  if ( !v5 )
    return 2147942408LL;
  *v5 = &CIISModuleFactory::`vftable';
  v5[1] = &CIISHttpModule::`vftable';
  v6 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
         a2,
         v5,
         128,
         0);
  v7 = 0;
  if ( v6 < 0 )
    return (unsigned int)v6;
  return v7;
}

```

## disassembly

```asm
0x1800021b0  mov     [rsp+arg_0], rbx
0x1800021b5  push    rdi
0x1800021b6  sub     rsp, 30h
0x1800021ba  mov     rax, [rdx]
0x1800021bd  mov     rcx, rdx
0x1800021c0  mov     rbx, r8
0x1800021c3  mov     rdi, rdx
0x1800021c6  mov     rax, [rax+8]
0x1800021ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021cf  mov     ecx, 10h; Size
0x1800021d4  mov     cs:?g_pDefaultDocModuleContext@@3PEAXEA, rax; void * g_pDefaultDocModuleContext
0x1800021db  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * g_pGlobalInfo
0x1800021e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800021e7  mov     rdx, rax
0x1800021ea  test    rax, rax
0x1800021ed  jz      short loc_180002227
0x1800021ef  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x1800021f6  xor     r9d, r9d
0x1800021f9  mov     [rdx], rax
0x1800021fc  mov     r8d, 80h
0x180002202  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x180002209  mov     [rdx+8], rax
0x18000220d  mov     rcx, [rdi]
0x180002210  mov     rax, [rcx+10h]
0x180002214  mov     rcx, rdi
0x180002217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000221c  xor     ecx, ecx
0x18000221e  test    eax, eax
0x180002220  cmovs   ecx, eax
0x180002223  mov     eax, ecx
0x180002225  jmp     short loc_18000222C
0x180002227  mov     eax, 80070008h
0x18000222c  mov     rbx, [rsp+38h+arg_0]
0x180002231  add     rsp, 30h
0x180002235  pop     rdi
0x180002236  retn
```
