# StartFactories(void)

- ea: `0x18000492c`
- end: `0x180004a42`
- name: `?StartFactories@@YAJXZ`
- size: `278`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006c10`

## callees

- `0x18000492c`
- `0x180005940`
- `0x18000bb10`
- `0x18000fca8`
- `0x180010af8`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1800049d1`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1800049d1`

## string_xrefs

- `0x1800049e7`: `clientcore\ds\security\gina\profile\roaming\classfactory.cpp`
- `0x180004a1a`: `clientcore\ds\security\gina\profile\roaming\classfactory.cpp`

## pseudocode

```c
__int64 StartFactories(void)
{
  int i; // edi
  int (*v1)(const struct _GUID *, void **); // rbx
  int v2; // esi
  CClassFactory *v3; // rax
  CClassFactory *v4; // r14
  HRESULT v5; // eax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  CClassFactory *v8; // [rsp+70h] [rbp+8h]

  for ( i = 0; !i; i = 1 )
  {
    v1 = off_18002B0F0;
    v2 = -2147024882;
    v8 = (CClassFactory *)operator new(0x18u);
    v3 = CClassFactory::CClassFactory(v8, v1);
    v4 = v3;
    if ( v3 )
    {
      v2 = (**(__int64 (__fastcall ***)(CClassFactory *, GUID *, __int64 *))v3)(v3, &IID_IUnknown, &qword_18002B0F8);
      (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v4 + 16LL))(v4);
    }
    if ( v2 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAB,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\classfactory.cpp",
        (const char *)(unsigned int)v2);
      goto LABEL_10;
    }
    v5 = CoRegisterClassObject((const IID *const)g_Classes, (LPUNKNOWN)qword_18002B0F8, 4u, 1u, &dwRegister);
    if ( v5 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB1,
        (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\classfactory.cpp",
        (const char *)(unsigned int)v5);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18002B0F8 + 16LL))(qword_18002B0F8);
      qword_18002B0F8 = 0;
LABEL_10:
      StopFactories();
      return 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000492c  push    rbx
0x18000492e  push    rbp
0x18000492f  push    rsi
0x180004930  push    rdi
0x180004931  push    r14
0x180004933  push    r15
0x180004935  sub     rsp, 38h
0x180004939  xor     edi, edi
0x18000493b  lea     r15, ?g_Classes@@3PAU_CLASS_INFO@@A; _CLASS_INFO near * g_Classes
0x180004942  movsxd  rax, edi
0x180004945  cmp     rax, 1
0x180004949  jnb     loc_180004A33
0x18000494f  lea     rbp, [rax+rax*4]
0x180004953  mov     ecx, 18h; Size
0x180004958  mov     rbx, [r15+rbp*8+10h]
0x18000495d  mov     esi, 8007000Eh
0x180004962  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004967  mov     rdx, rbx; int (*)(const struct _GUID *, void **)
0x18000496a  mov     [rsp+68h+arg_0], rax
0x18000496f  mov     rcx, rax; this
0x180004972  call    ??0CClassFactory@@QEAA@P6AJAEBU_GUID@@PEAPEAX@Z@Z; CClassFactory::CClassFactory(long (*)(_GUID const &,void * *))
0x180004977  lea     rbx, [r15+rbp*8]
0x18000497b  mov     r14, rax
0x18000497e  test    rax, rax
0x180004981  jz      short loc_1800049AD
0x180004983  mov     rax, [rax]
0x180004986  lea     r8, [rbx+18h]
0x18000498a  lea     rdx, IID_IUnknown
0x180004991  mov     rcx, r14
0x180004994  mov     rax, [rax]
0x180004997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000499c  mov     rcx, [r14]
0x18000499f  mov     esi, eax
0x1800049a1  mov     rax, [rcx+10h]
0x1800049a5  mov     rcx, r14
0x1800049a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ad  test    esi, esi
0x1800049af  js      short loc_180004A15
0x1800049b1  mov     rdx, [r15+rbp*8+18h]; pUnk
0x1800049b6  lea     rax, [r15+20h]
0x1800049ba  mov     rcx, [r15+rbp*8]; rclsid
0x1800049be  lea     rax, [rax+rbp*8]
0x1800049c2  mov     r9d, 1; flags
0x1800049c8  mov     [rsp+68h+lpdwRegister], rax; int
0x1800049cd  lea     r8d, [r9+3]; dwClsContext
0x1800049d1  call    cs:__imp_CoRegisterClassObject
0x1800049d7  test    eax, eax
0x1800049d9  js      short loc_1800049E2
0x1800049db  inc     edi
0x1800049dd  jmp     loc_180004942
0x1800049e2  mov     rcx, [rsp+68h]; this
0x1800049e7  lea     r8, aClientcoreDsSe_2; "clientcore\\ds\\security\\gina\\profile"...
0x1800049ee  mov     r9d, eax; char *
0x1800049f1  mov     edx, 0B1h; void *
0x1800049f6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800049fb  mov     rcx, [rbx+18h]
0x1800049ff  mov     rax, [rcx]
0x180004a02  mov     rax, [rax+10h]
0x180004a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a0b  mov     qword ptr [rbx+18h], 0
0x180004a13  jmp     short loc_180004A2E
0x180004a15  mov     rcx, [rsp+68h]; this
0x180004a1a  lea     r8, aClientcoreDsSe_2; "clientcore\\ds\\security\\gina\\profile"...
0x180004a21  mov     r9d, esi; char *
0x180004a24  mov     edx, 0ABh; void *
0x180004a29  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180004a2e  call    ?StopFactories@@YAJXZ; StopFactories(void)
0x180004a33  xor     eax, eax
0x180004a35  add     rsp, 38h
0x180004a39  pop     r15
0x180004a3b  pop     r14
0x180004a3d  pop     rdi
0x180004a3e  pop     rsi
0x180004a3f  pop     rbp
0x180004a40  pop     rbx
0x180004a41  retn
```
