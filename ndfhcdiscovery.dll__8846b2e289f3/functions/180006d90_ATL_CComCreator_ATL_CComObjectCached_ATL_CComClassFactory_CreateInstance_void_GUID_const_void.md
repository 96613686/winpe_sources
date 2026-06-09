# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006d90`
- end: `0x180006ec3`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `307`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800012e0`
- `0x180006d90`
- `0x1800079f0`
- `0x180015010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006ea5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006ea5`
- `KERNEL32!DeleteCriticalSection` at `0x180006e96`
- `KERNEL32!DeleteCriticalSection` at `0x180006e96`

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
0x180006d90  mov     [rsp+arg_10], r8
0x180006d95  mov     [rsp+arg_8], rdx
0x180006d9a  mov     [rsp+arg_0], rcx
0x180006d9f  push    rbx
0x180006da0  push    rsi
0x180006da1  push    r12
0x180006da3  push    r13
0x180006da5  push    r14
0x180006da7  push    r15
0x180006da9  sub     rsp, 38h
0x180006dad  mov     r15, r8
0x180006db0  mov     r12, rdx
0x180006db3  mov     r14, rcx
0x180006db6  test    r8, r8
0x180006db9  jnz     short loc_180006DC5
0x180006dbb  mov     eax, 80004003h
0x180006dc0  jmp     loc_180006EB3
0x180006dc5  mov     qword ptr [r8], 0
0x180006dcc  mov     esi, 8007000Eh
0x180006dd1  mov     [rsp+68h+arg_18], esi
0x180006dd8  mov     [rsp+68h+var_48], 0
0x180006de1  mov     ecx, 48h ; 'H'; Size
0x180006de6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006deb  mov     rbx, rax
0x180006dee  test    rbx, rbx
0x180006df1  jz      short loc_180006E18
0x180006df3  mov     dword ptr [rax+8], 0
0x180006dfa  xorps   xmm0, xmm0
0x180006dfd  xor     eax, eax
0x180006dff  movups  xmmword ptr [rbx+10h], xmm0
0x180006e03  movups  xmmword ptr [rbx+20h], xmm0
0x180006e07  mov     [rbx+30h], rax
0x180006e0b  mov     [rbx+38h], al
0x180006e0e  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180006e15  mov     [rbx], rax
0x180006e18  mov     [rsp+68h+var_48], rbx
0x180006e1d  jmp     short loc_180006E3D
0x180006e1f  mov     r15, [rsp+68h+arg_10]
0x180006e27  mov     r12, [rsp+68h+arg_8]
0x180006e2c  mov     r14, [rsp+68h+arg_0]
0x180006e31  mov     esi, [rsp+68h+arg_18]
0x180006e38  mov     rbx, [rsp+68h+var_48]
0x180006e3d  test    rbx, rbx
0x180006e40  jz      short loc_180006EB1
0x180006e42  mov     [rbx+40h], r14
0x180006e46  lea     rcx, [rbx+10h]; this
0x180006e4a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006e4f  mov     esi, eax
0x180006e51  lea     r14, [rbx+38h]
0x180006e55  test    eax, eax
0x180006e57  js      short loc_180006E77
0x180006e59  mov     byte ptr [r14], 1
0x180006e5d  mov     rax, [rbx]
0x180006e60  mov     r8, r15
0x180006e63  mov     rdx, r12
0x180006e66  mov     rcx, rbx
0x180006e69  mov     rax, [rax]
0x180006e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e71  mov     esi, eax
0x180006e73  test    eax, eax
0x180006e75  jz      short loc_180006EB1
0x180006e77  mov     dword ptr [rbx+8], 0C0000001h
0x180006e7e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180006e85  mov     [rbx], rax
0x180006e88  cmp     byte ptr [r14], 0
0x180006e8c  jz      short loc_180006EA2
0x180006e8e  mov     byte ptr [r14], 0
0x180006e92  lea     rcx, [rbx+10h]; lpCriticalSection
0x180006e96  call    cs:__imp_DeleteCriticalSection
0x180006e9d  nop     dword ptr [rax+rax+00h]
0x180006ea2  mov     rcx, rbx
0x180006ea5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006eac  nop     dword ptr [rax+rax+00h]
0x180006eb1  mov     eax, esi
0x180006eb3  add     rsp, 38h
0x180006eb7  pop     r15
0x180006eb9  pop     r14
0x180006ebb  pop     r13
0x180006ebd  pop     r12
0x180006ebf  pop     rsi
0x180006ec0  pop     rbx
0x180006ec1  retn
```
