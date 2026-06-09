# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002c50`
- end: `0x180002d8f`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001284`
- `0x1800012d0`
- `0x180002c50`
- `0x180002edc`
- `0x180017010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002d54`
- `KERNEL32!DeleteCriticalSection` at `0x180002d68`
- `KERNEL32!DeleteCriticalSection` at `0x180002d54`
- `KERNEL32!DeleteCriticalSection` at `0x180002d68`

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
0x180002c50  mov     [rsp+arg_0], rbx
0x180002c55  mov     [rsp+arg_8], rbp
0x180002c5a  push    rsi
0x180002c5b  push    rdi
0x180002c5c  push    r12
0x180002c5e  push    r14
0x180002c60  push    r15
0x180002c62  sub     rsp, 20h
0x180002c66  mov     r15, r8
0x180002c69  mov     r12, rdx
0x180002c6c  mov     rdi, rcx
0x180002c6f  test    r8, r8
0x180002c72  jnz     short loc_180002C7E
0x180002c74  mov     eax, 80004003h
0x180002c79  jmp     loc_180002D78
0x180002c7e  mov     ecx, 78h ; 'x'; Size
0x180002c83  mov     qword ptr [r8], 0
0x180002c8a  mov     esi, 8007000Eh
0x180002c8f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002c94  mov     [rsp+48h+arg_10], rax
0x180002c99  mov     rbx, rax
0x180002c9c  test    rax, rax
0x180002c9f  jz      loc_180002D76
0x180002ca5  mov     dword ptr [rax+8], 0
0x180002cac  xorps   xmm0, xmm0
0x180002caf  movups  xmmword ptr [rbx+10h], xmm0
0x180002cb3  xor     eax, eax
0x180002cb5  movups  xmmword ptr [rbx+20h], xmm0
0x180002cb9  mov     [rbx+30h], rax
0x180002cbd  mov     [rbx+38h], al
0x180002cc0  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180002cc7  mov     [rbx], rax
0x180002cca  xor     eax, eax
0x180002ccc  movups  xmmword ptr [rbx+48h], xmm0
0x180002cd0  movups  xmmword ptr [rbx+58h], xmm0
0x180002cd4  mov     [rbx+68h], rax
0x180002cd8  mov     [rbx+70h], al
0x180002cdb  test    rbx, rbx
0x180002cde  jz      loc_180002D76
0x180002ce4  lea     rcx, [rbx+10h]; this
0x180002ce8  mov     [rbx+40h], rdi
0x180002cec  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002cf1  lea     r14, [rbx+38h]
0x180002cf5  lea     rdi, [rbx+48h]
0x180002cf9  test    eax, eax
0x180002cfb  js      short loc_180002D11
0x180002cfd  mov     rcx, rdi; this
0x180002d00  mov     byte ptr [r14], 1
0x180002d04  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002d09  test    eax, eax
0x180002d0b  js      short loc_180002D11
0x180002d0d  mov     byte ptr [rdi+28h], 1
0x180002d11  xor     esi, esi
0x180002d13  test    eax, eax
0x180002d15  cmovs   esi, eax
0x180002d18  test    esi, esi
0x180002d1a  jnz     short loc_180002D36
0x180002d1c  mov     rax, [rbx]
0x180002d1f  mov     r8, r15
0x180002d22  mov     rdx, r12
0x180002d25  mov     rcx, rbx
0x180002d28  mov     rax, [rax]
0x180002d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d30  mov     esi, eax
0x180002d32  test    eax, eax
0x180002d34  jz      short loc_180002D76
0x180002d36  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180002d3d  mov     dword ptr [rbx+8], 1
0x180002d44  mov     [rbx], rax
0x180002d47  cmp     byte ptr [rdi+28h], 0
0x180002d4b  jz      short loc_180002D5A
0x180002d4d  mov     rcx, rdi; lpCriticalSection
0x180002d50  mov     byte ptr [rdi+28h], 0
0x180002d54  call    cs:__imp_DeleteCriticalSection
0x180002d5a  cmp     byte ptr [r14], 0
0x180002d5e  jz      short loc_180002D6E
0x180002d60  lea     rcx, [rbx+10h]; lpCriticalSection
0x180002d64  mov     byte ptr [r14], 0
0x180002d68  call    cs:__imp_DeleteCriticalSection
0x180002d6e  mov     rcx, rbx; Block
0x180002d71  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002d76  mov     eax, esi
0x180002d78  mov     rbx, [rsp+48h+arg_0]
0x180002d7d  mov     rbp, [rsp+48h+arg_8]
0x180002d82  add     rsp, 20h
0x180002d86  pop     r15
0x180002d88  pop     r14
0x180002d8a  pop     r12
0x180002d8c  pop     rdi
0x180002d8d  pop     rsi
0x180002d8e  retn
```
