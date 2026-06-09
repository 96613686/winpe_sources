# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003e50`
- end: `0x180003f90`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `320`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001140`
- `0x180003e50`
- `0x1800040dc`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003f71`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003f71`
- `KERNEL32!DeleteCriticalSection` at `0x180003f54`
- `KERNEL32!DeleteCriticalSection` at `0x180003f68`
- `KERNEL32!DeleteCriticalSection` at `0x180003f54`
- `KERNEL32!DeleteCriticalSection` at `0x180003f68`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  int v10; // eax
  _BYTE *v11; // r14

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x78u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *((_OWORD *)v8 + 1) = 0;
    *((_OWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 6) = 0;
    v8[56] = 0;
    *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    *(_OWORD *)(v8 + 72) = 0;
    *(_OWORD *)(v8 + 88) = 0;
    *((_QWORD *)v8 + 13) = 0;
    v8[112] = 0;
    *((_QWORD *)v8 + 8) = a1;
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 16));
    v11 = v9 + 56;
    if ( v10 >= 0 )
    {
      *v11 = 1;
      v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 72));
      if ( v10 >= 0 )
        v9[112] = 1;
    }
    v7 = 0;
    if ( v10 < 0 )
      v7 = v10;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0 )
    {
      *((_DWORD *)v9 + 2) = 1;
      *(_QWORD *)v9 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
      if ( v9[112] )
      {
        v9[112] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 72));
      }
      if ( *v11 )
      {
        *v11 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      operator delete(v9);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180003e50  mov     [rsp+arg_0], rbx
0x180003e55  mov     [rsp+arg_8], rbp
0x180003e5a  push    rsi
0x180003e5b  push    rdi
0x180003e5c  push    r12
0x180003e5e  push    r14
0x180003e60  push    r15
0x180003e62  sub     rsp, 20h
0x180003e66  mov     r15, r8
0x180003e69  mov     r12, rdx
0x180003e6c  mov     rdi, rcx
0x180003e6f  test    r8, r8
0x180003e72  jnz     short loc_180003E7E
0x180003e74  mov     eax, 80004003h
0x180003e79  jmp     loc_180003F79
0x180003e7e  mov     ecx, 78h ; 'x'; Size
0x180003e83  mov     qword ptr [r8], 0
0x180003e8a  mov     esi, 8007000Eh
0x180003e8f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003e94  mov     [rsp+48h+arg_10], rax
0x180003e99  mov     rbx, rax
0x180003e9c  test    rax, rax
0x180003e9f  jz      loc_180003F77
0x180003ea5  mov     dword ptr [rax+8], 0
0x180003eac  xorps   xmm0, xmm0
0x180003eaf  movups  xmmword ptr [rbx+10h], xmm0
0x180003eb3  xor     eax, eax
0x180003eb5  movups  xmmword ptr [rbx+20h], xmm0
0x180003eb9  mov     [rbx+30h], rax
0x180003ebd  mov     [rbx+38h], al
0x180003ec0  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180003ec7  mov     [rbx], rax
0x180003eca  xor     eax, eax
0x180003ecc  movups  xmmword ptr [rbx+48h], xmm0
0x180003ed0  movups  xmmword ptr [rbx+58h], xmm0
0x180003ed4  mov     [rbx+68h], rax
0x180003ed8  mov     [rbx+70h], al
0x180003edb  test    rbx, rbx
0x180003ede  jz      loc_180003F77
0x180003ee4  lea     rcx, [rbx+10h]; this
0x180003ee8  mov     [rbx+40h], rdi
0x180003eec  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003ef1  lea     r14, [rbx+38h]
0x180003ef5  lea     rdi, [rbx+48h]
0x180003ef9  test    eax, eax
0x180003efb  js      short loc_180003F11
0x180003efd  mov     rcx, rdi; this
0x180003f00  mov     byte ptr [r14], 1
0x180003f04  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003f09  test    eax, eax
0x180003f0b  js      short loc_180003F11
0x180003f0d  mov     byte ptr [rdi+28h], 1
0x180003f11  xor     esi, esi
0x180003f13  test    eax, eax
0x180003f15  cmovs   esi, eax
0x180003f18  test    esi, esi
0x180003f1a  jnz     short loc_180003F36
0x180003f1c  mov     rax, [rbx]
0x180003f1f  mov     r8, r15
0x180003f22  mov     rdx, r12
0x180003f25  mov     rcx, rbx
0x180003f28  mov     rax, [rax]
0x180003f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f30  mov     esi, eax
0x180003f32  test    eax, eax
0x180003f34  jz      short loc_180003F77
0x180003f36  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180003f3d  mov     dword ptr [rbx+8], 1
0x180003f44  mov     [rbx], rax
0x180003f47  cmp     byte ptr [rdi+28h], 0
0x180003f4b  jz      short loc_180003F5A
0x180003f4d  mov     rcx, rdi; lpCriticalSection
0x180003f50  mov     byte ptr [rdi+28h], 0
0x180003f54  call    cs:__imp_DeleteCriticalSection
0x180003f5a  cmp     byte ptr [r14], 0
0x180003f5e  jz      short loc_180003F6E
0x180003f60  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003f64  mov     byte ptr [r14], 0
0x180003f68  call    cs:__imp_DeleteCriticalSection
0x180003f6e  mov     rcx, rbx
0x180003f71  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003f77  mov     eax, esi
0x180003f79  mov     rbx, [rsp+48h+arg_0]
0x180003f7e  mov     rbp, [rsp+48h+arg_8]
0x180003f83  add     rsp, 20h
0x180003f87  pop     r15
0x180003f89  pop     r14
0x180003f8b  pop     r12
0x180003f8d  pop     rdi
0x180003f8e  pop     rsi
0x180003f8f  retn
```
