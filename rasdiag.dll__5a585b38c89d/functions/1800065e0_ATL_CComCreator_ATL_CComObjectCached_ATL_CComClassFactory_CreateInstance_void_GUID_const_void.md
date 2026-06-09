# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800065e0`
- end: `0x180006713`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `307`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800011dc`
- `0x18000447c`
- `0x1800065e0`
- `0x18000f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800066f5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800066f5`
- `KERNEL32!DeleteCriticalSection` at `0x1800066e6`
- `KERNEL32!DeleteCriticalSection` at `0x1800066e6`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r15
  __int64 v4; // r12
  __int64 v5; // r14
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // r14
  char *v11; // [rsp+20h] [rbp-48h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x48u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 6) = 0;
      v8[56] = 0;
      *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    }
    v11 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v7 = -2147024882;
    v9 = v11;
  }
  if ( v9 )
  {
    *((_QWORD *)v9 + 8) = v5;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 16));
    v10 = v9 + 56;
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactory::`vftable';
      if ( *v10 )
      {
        *v10 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      operator delete(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800065e0  mov     [rsp+arg_10], r8
0x1800065e5  mov     [rsp+arg_8], rdx
0x1800065ea  mov     [rsp+arg_0], rcx
0x1800065ef  push    rbx
0x1800065f0  push    rsi
0x1800065f1  push    r12
0x1800065f3  push    r13
0x1800065f5  push    r14
0x1800065f7  push    r15
0x1800065f9  sub     rsp, 38h
0x1800065fd  mov     r15, r8
0x180006600  mov     r12, rdx
0x180006603  mov     r14, rcx
0x180006606  test    r8, r8
0x180006609  jnz     short loc_180006615
0x18000660b  mov     eax, 80004003h
0x180006610  jmp     loc_180006703
0x180006615  mov     qword ptr [r8], 0
0x18000661c  mov     esi, 8007000Eh
0x180006621  mov     [rsp+68h+arg_18], esi
0x180006628  mov     [rsp+68h+var_48], 0
0x180006631  mov     ecx, 48h ; 'H'; Size
0x180006636  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000663b  mov     rbx, rax
0x18000663e  test    rbx, rbx
0x180006641  jz      short loc_180006668
0x180006643  mov     dword ptr [rax+8], 0
0x18000664a  xorps   xmm0, xmm0
0x18000664d  xor     eax, eax
0x18000664f  movups  xmmword ptr [rbx+10h], xmm0
0x180006653  movups  xmmword ptr [rbx+20h], xmm0
0x180006657  mov     [rbx+30h], rax
0x18000665b  mov     [rbx+38h], al
0x18000665e  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180006665  mov     [rbx], rax
0x180006668  mov     [rsp+68h+var_48], rbx
0x18000666d  jmp     short loc_18000668D
0x18000666f  mov     r15, [rsp+68h+arg_10]
0x180006677  mov     r12, [rsp+68h+arg_8]
0x18000667c  mov     r14, [rsp+68h+arg_0]
0x180006681  mov     esi, [rsp+68h+arg_18]
0x180006688  mov     rbx, [rsp+68h+var_48]
0x18000668d  test    rbx, rbx
0x180006690  jz      short loc_180006701
0x180006692  mov     [rbx+40h], r14
0x180006696  lea     rcx, [rbx+10h]; this
0x18000669a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000669f  mov     esi, eax
0x1800066a1  lea     r14, [rbx+38h]
0x1800066a5  test    eax, eax
0x1800066a7  js      short loc_1800066C7
0x1800066a9  mov     byte ptr [r14], 1
0x1800066ad  mov     rax, [rbx]
0x1800066b0  mov     r8, r15
0x1800066b3  mov     rdx, r12
0x1800066b6  mov     rcx, rbx
0x1800066b9  mov     rax, [rax]
0x1800066bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066c1  mov     esi, eax
0x1800066c3  test    eax, eax
0x1800066c5  jz      short loc_180006701
0x1800066c7  mov     dword ptr [rbx+8], 0C0000001h
0x1800066ce  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800066d5  mov     [rbx], rax
0x1800066d8  cmp     byte ptr [r14], 0
0x1800066dc  jz      short loc_1800066F2
0x1800066de  mov     byte ptr [r14], 0
0x1800066e2  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800066e6  call    cs:__imp_DeleteCriticalSection
0x1800066ed  nop     dword ptr [rax+rax+00h]
0x1800066f2  mov     rcx, rbx
0x1800066f5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800066fc  nop     dword ptr [rax+rax+00h]
0x180006701  mov     eax, esi
0x180006703  add     rsp, 38h
0x180006707  pop     r15
0x180006709  pop     r14
0x18000670b  pop     r13
0x18000670d  pop     r12
0x18000670f  pop     rsi
0x180006710  pop     rbx
0x180006711  retn
```
