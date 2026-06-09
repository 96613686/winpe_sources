# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180002a40`
- end: `0x180002ac5`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001088`
- `0x180002050`
- `0x180002a40`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  _QWORD *v5; // rax
  __int64 result; // rax

  g_pIpRestrictionModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  g_pGlobalInfo = a3;
  v5 = operator new(0x10u);
  if ( !v5 )
    return 2147942408LL;
  *v5 = &CIISModuleFactory::`vftable';
  v5[1] = &CIISHttpModule::`vftable';
  result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 16LL))(
             a2,
             v5,
             1);
  if ( (int)result >= 0 )
    return CHECK_ACCESS_HANDLER::Initialize();
  return result;
}

```

## disassembly

```asm
0x180002a40  mov     [rsp+arg_0], rbx
0x180002a45  push    rdi
0x180002a46  sub     rsp, 30h
0x180002a4a  mov     rax, [rdx]
0x180002a4d  mov     rcx, rdx
0x180002a50  mov     rbx, r8
0x180002a53  mov     rdi, rdx
0x180002a56  mov     rax, [rax+8]
0x180002a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a5f  mov     ecx, 10h; Size
0x180002a64  mov     cs:?g_pIpRestrictionModuleContext@@3PEAXEA, rax; void * g_pIpRestrictionModuleContext
0x180002a6b  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * g_pGlobalInfo
0x180002a72  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002a77  mov     rdx, rax
0x180002a7a  test    rax, rax
0x180002a7d  jz      short loc_180002AB5
0x180002a7f  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x180002a86  xor     r9d, r9d
0x180002a89  mov     [rdx], rax
0x180002a8c  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x180002a93  mov     [rdx+8], rax
0x180002a97  mov     rcx, [rdi]
0x180002a9a  lea     r8d, [r9+1]
0x180002a9e  mov     rax, [rcx+10h]
0x180002aa2  mov     rcx, rdi
0x180002aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aaa  test    eax, eax
0x180002aac  js      short loc_180002ABA
0x180002aae  call    ?Initialize@CHECK_ACCESS_HANDLER@@SAJXZ; CHECK_ACCESS_HANDLER::Initialize(void)
0x180002ab3  jmp     short loc_180002ABA
0x180002ab5  mov     eax, 80070008h
0x180002aba  mov     rbx, [rsp+38h+arg_0]
0x180002abf  add     rsp, 30h
0x180002ac3  pop     rdi
0x180002ac4  retn
```
