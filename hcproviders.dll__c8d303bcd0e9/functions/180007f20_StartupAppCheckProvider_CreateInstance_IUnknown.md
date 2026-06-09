# StartupAppCheckProvider_CreateInstance(IUnknown * *)

- ea: `0x180007f20`
- end: `0x180007fba`
- name: `?StartupAppCheckProvider_CreateInstance@@YAJPEAPEAUIUnknown@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(struct IUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003450`
- `0x180004fc8`
- `0x1800063cc`
- `0x180007f20`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall StartupAppCheckProvider_CreateInstance(struct IUnknown **a1)
{
  _OWORD *v2; // rax
  LPOLESTR *v3; // rax
  LPOLESTR *v4; // rbx
  HRESULT v5; // edi

  *a1 = 0;
  v2 = operator new(0x20u);
  if ( v2
    && (*v2 = 0,
        v2[1] = 0,
        v3 = (LPOLESTR *)CObjectFactory<_GUID const &,CStartupAppCheckProvider>::CObjectFactory<_GUID const &,CStartupAppCheckProvider>(v2),
        (v4 = v3) != 0) )
  {
    v5 = CCheckProviderBase::_Initialize(v3, &stru_18000DAB8);
    if ( v5 >= 0 )
      v5 = (*(__int64 (__fastcall **)(LPOLESTR *, GUID *, struct IUnknown **))*v4)(
             v4,
             &GUID_00000000_0000_0000_c000_000000000046,
             a1);
    (*((void (__fastcall **)(LPOLESTR *))*v4 + 2))(v4);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007f20  mov     [rsp+arg_0], rbx
0x180007f25  mov     [rsp+arg_8], rsi
0x180007f2a  push    rdi
0x180007f2b  sub     rsp, 20h
0x180007f2f  mov     rsi, rcx
0x180007f32  mov     qword ptr [rcx], 0
0x180007f39  mov     ecx, 20h ; ' '; Size
0x180007f3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007f43  test    rax, rax
0x180007f46  jz      short loc_180007FA2
0x180007f48  xorps   xmm0, xmm0
0x180007f4b  mov     rcx, rax
0x180007f4e  movups  xmmword ptr [rax], xmm0
0x180007f51  movups  xmmword ptr [rax+10h], xmm0
0x180007f55  call    ??0?$CObjectFactory@AEBU_GUID@@VCStartupAppCheckProvider@@@@QEAA@XZ; CObjectFactory<_GUID const &,CStartupAppCheckProvider>::CObjectFactory<_GUID const &,CStartupAppCheckProvider>(void)
0x180007f5a  mov     rbx, rax
0x180007f5d  test    rax, rax
0x180007f60  jz      short loc_180007FA2
0x180007f62  lea     rdx, stru_18000DAB8; struct _GUID *
0x180007f69  mov     rcx, rax; this
0x180007f6c  call    ?_Initialize@CCheckProviderBase@@IEAAJAEBU_GUID@@@Z; CCheckProviderBase::_Initialize(_GUID const &)
0x180007f71  mov     edi, eax
0x180007f73  test    eax, eax
0x180007f75  js      short loc_180007F91
0x180007f77  mov     rax, [rbx]
0x180007f7a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180007f81  mov     r8, rsi
0x180007f84  mov     rcx, rbx
0x180007f87  mov     rax, [rax]
0x180007f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f8f  mov     edi, eax
0x180007f91  mov     rcx, [rbx]
0x180007f94  mov     rax, [rcx+10h]
0x180007f98  mov     rcx, rbx
0x180007f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fa0  jmp     short loc_180007FA7
0x180007fa2  mov     edi, 8007000Eh
0x180007fa7  mov     rbx, [rsp+28h+arg_0]
0x180007fac  mov     eax, edi
0x180007fae  mov     rsi, [rsp+28h+arg_8]
0x180007fb3  add     rsp, 20h
0x180007fb7  pop     rdi
0x180007fb8  retn
```
