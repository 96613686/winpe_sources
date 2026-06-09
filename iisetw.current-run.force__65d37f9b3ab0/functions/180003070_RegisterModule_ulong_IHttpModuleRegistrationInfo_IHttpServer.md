# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180003070`
- end: `0x1800030e9`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001008`
- `0x180002c20`
- `0x180003070`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  _QWORD *v5; // rax
  __int64 result; // rax

  s_pModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  s_pGlobalInfo = a3;
  v5 = operator new(8u);
  if ( !v5 )
    return 2147942408LL;
  *v5 = &CIISGlobalModule::`vftable';
  result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 24LL))(
             a2,
             v5,
             8256);
  if ( (int)result >= 0 )
    return ETW_TRACE_HANDLER::Initialize();
  return result;
}

```

## disassembly

```asm
0x180003070  mov     [rsp+arg_0], rbx
0x180003075  push    rdi
0x180003076  sub     rsp, 20h
0x18000307a  mov     rax, [rdx]
0x18000307d  mov     rcx, rdx
0x180003080  mov     rbx, r8
0x180003083  mov     rdi, rdx
0x180003086  mov     rax, [rax+8]
0x18000308a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000308f  mov     ecx, 8; Size
0x180003094  mov     cs:?s_pModuleContext@@3PEAXEA, rax; void * s_pModuleContext
0x18000309b  mov     cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * s_pGlobalInfo
0x1800030a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800030a7  mov     rdx, rax
0x1800030aa  test    rax, rax
0x1800030ad  jz      short loc_1800030D9
0x1800030af  lea     rax, ??_7CIISGlobalModule@@6B@; const CIISGlobalModule::`vftable'
0x1800030b6  mov     r8d, 2040h
0x1800030bc  mov     [rdx], rax
0x1800030bf  mov     rcx, [rdi]
0x1800030c2  mov     rax, [rcx+18h]
0x1800030c6  mov     rcx, rdi
0x1800030c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ce  test    eax, eax
0x1800030d0  js      short loc_1800030DE
0x1800030d2  call    ?Initialize@ETW_TRACE_HANDLER@@SAJXZ; ETW_TRACE_HANDLER::Initialize(void)
0x1800030d7  jmp     short loc_1800030DE
0x1800030d9  mov     eax, 80070008h
0x1800030de  mov     rbx, [rsp+28h+arg_0]
0x1800030e3  add     rsp, 20h
0x1800030e7  pop     rdi
0x1800030e8  retn
```
