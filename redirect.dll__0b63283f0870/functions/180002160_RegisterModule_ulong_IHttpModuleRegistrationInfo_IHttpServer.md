# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180002160`
- end: `0x1800021e6`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001008`
- `0x180002160`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  void *v5; // rax
  _QWORD *v6; // rax
  int v7; // eax
  unsigned int v8; // ecx

  v5 = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  g_pGlobalInfo = a3;
  g_pRedirectionModuleContext = v5;
  v6 = operator new(0x10u);
  if ( !v6 )
    return 2147942408LL;
  *v6 = &CIISModuleFactory::`vftable';
  v6[1] = &CIISHttpModule::`vftable';
  v7 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
         a2,
         v6,
         16,
         0);
  v8 = 0;
  if ( v7 < 0 )
    return (unsigned int)v7;
  return v8;
}

```

## disassembly

```asm
0x180002160  mov     [rsp+arg_0], rbx
0x180002165  push    rdi
0x180002166  sub     rsp, 30h
0x18000216a  mov     rax, [rdx]
0x18000216d  mov     rcx, rdx
0x180002170  mov     rbx, r8
0x180002173  mov     rdi, rdx
0x180002176  mov     rax, [rax+8]
0x18000217a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000217f  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * g_pGlobalInfo
0x180002186  mov     ebx, 10h
0x18000218b  mov     ecx, ebx; Size
0x18000218d  mov     cs:?g_pRedirectionModuleContext@@3PEAXEA, rax; void * g_pRedirectionModuleContext
0x180002194  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002199  mov     rdx, rax
0x18000219c  test    rax, rax
0x18000219f  jz      short loc_1800021D6
0x1800021a1  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x1800021a8  xor     r9d, r9d
0x1800021ab  mov     [rdx], rax
0x1800021ae  mov     r8d, ebx
0x1800021b1  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x1800021b8  mov     [rdx+8], rax
0x1800021bc  mov     rcx, [rdi]
0x1800021bf  mov     rax, [rcx+10h]
0x1800021c3  mov     rcx, rdi
0x1800021c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021cb  xor     ecx, ecx
0x1800021cd  test    eax, eax
0x1800021cf  cmovs   ecx, eax
0x1800021d2  mov     eax, ecx
0x1800021d4  jmp     short loc_1800021DB
0x1800021d6  mov     eax, 80070008h
0x1800021db  mov     rbx, [rsp+38h+arg_0]
0x1800021e0  add     rsp, 30h
0x1800021e4  pop     rdi
0x1800021e5  retn
```
