# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180001c10`
- end: `0x180001cb6`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(__int64, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180001c10`
- `0x180001cc0`
- `0x180001d80`
- `0x180005010`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  _QWORD *v5; // rax
  __int64 result; // rax

  s_pModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  s_pGlobalInfo = a3;
  v5 = operator new(0x10u);
  if ( !v5 )
    return 2147942408LL;
  *v5 = &CIISModuleFactory::`vftable';
  v5[1] = &CIISHttpModule::`vftable';
  result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
             a2,
             v5,
             134217857,
             0);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, __int64, const wchar_t *))(*(_QWORD *)a2 + 32LL))(
               a2,
               1,
               L"LOW");
    if ( (int)result >= 0 )
      return TRACE_VERB_HANDLER::Initialize();
  }
  return result;
}

```

## disassembly

```asm
0x180001c10  mov     [rsp+arg_0], rbx
0x180001c15  push    rdi
0x180001c16  sub     rsp, 30h
0x180001c1a  mov     rax, [rdx]
0x180001c1d  mov     rcx, rdx
0x180001c20  mov     rdi, r8
0x180001c23  mov     rbx, rdx
0x180001c26  mov     rax, [rax+8]
0x180001c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c2f  mov     ecx, 10h; Size
0x180001c34  mov     cs:?s_pModuleContext@@3PEAXEA, rax; void * s_pModuleContext
0x180001c3b  mov     cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA, rdi; IHttpServer * s_pGlobalInfo
0x180001c42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001c47  mov     rdx, rax
0x180001c4a  test    rax, rax
0x180001c4d  jz      short loc_180001CAF
0x180001c4f  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x180001c56  xor     r9d, r9d
0x180001c59  mov     [rdx], rax
0x180001c5c  mov     r8d, 8000081h
0x180001c62  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x180001c69  mov     [rdx+8], rax
0x180001c6d  mov     rcx, [rbx]
0x180001c70  mov     rax, [rcx+10h]
0x180001c74  mov     rcx, rbx
0x180001c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c7c  test    eax, eax
0x180001c7e  js      short loc_180001CA4
0x180001c80  mov     rax, [rbx]
0x180001c83  lea     r8, aLow; "LOW"
0x180001c8a  mov     edx, 1
0x180001c8f  mov     rcx, rbx
0x180001c92  mov     rax, [rax+20h]
0x180001c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c9b  test    eax, eax
0x180001c9d  js      short loc_180001CA4
0x180001c9f  call    ?Initialize@TRACE_VERB_HANDLER@@SAJXZ; TRACE_VERB_HANDLER::Initialize(void)
0x180001ca4  mov     rbx, [rsp+38h+arg_0]
0x180001ca9  add     rsp, 30h
0x180001cad  pop     rdi
0x180001cae  retn
0x180001caf  mov     eax, 80070008h
0x180001cb4  jmp     short loc_180001CA4
```
