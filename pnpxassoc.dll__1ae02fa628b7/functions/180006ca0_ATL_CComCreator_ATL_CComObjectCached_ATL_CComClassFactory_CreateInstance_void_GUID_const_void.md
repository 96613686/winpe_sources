# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006ca0`
- end: `0x180006d7a`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800019b0`
- `0x1800019d4`
- `0x180006ca0`
- `0x180006f6c`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180006d5d`
- `KERNEL32!DeleteCriticalSection` at `0x180006d5d`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // rdi

  if ( !a3 )
    return 2147500035LL;
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
    *((_QWORD *)v8 + 8) = a1;
    v10 = v8 + 56;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 16));
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0) )
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
0x180006ca0  push    rbx
0x180006ca2  push    rbp
0x180006ca3  push    rsi
0x180006ca4  push    rdi
0x180006ca5  push    r14
0x180006ca7  push    r15
0x180006ca9  sub     rsp, 28h
0x180006cad  mov     r14, r8
0x180006cb0  mov     r15, rdx
0x180006cb3  mov     rdi, rcx
0x180006cb6  test    r8, r8
0x180006cb9  jnz     short loc_180006CC5
0x180006cbb  mov     eax, 80004003h
0x180006cc0  jmp     loc_180006D6D
0x180006cc5  mov     ecx, 48h ; 'H'; Size
0x180006cca  mov     qword ptr [r8], 0
0x180006cd1  mov     esi, 8007000Eh
0x180006cd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006cdb  mov     rbx, rax
0x180006cde  test    rax, rax
0x180006ce1  jz      loc_180006D6B
0x180006ce7  mov     dword ptr [rax+8], 0
0x180006cee  lea     rcx, [rbx+10h]; this
0x180006cf2  xor     eax, eax
0x180006cf4  xorps   xmm0, xmm0
0x180006cf7  movups  xmmword ptr [rbx+10h], xmm0
0x180006cfb  movups  xmmword ptr [rbx+20h], xmm0
0x180006cff  mov     [rbx+30h], rax
0x180006d03  mov     [rbx+38h], al
0x180006d06  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180006d0d  mov     [rbx], rax
0x180006d10  mov     [rbx+40h], rdi
0x180006d14  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006d19  lea     rdi, [rbx+38h]
0x180006d1d  mov     esi, eax
0x180006d1f  test    eax, eax
0x180006d21  js      short loc_180006D40
0x180006d23  mov     byte ptr [rdi], 1
0x180006d26  mov     r8, r14
0x180006d29  mov     rax, [rbx]
0x180006d2c  mov     rdx, r15
0x180006d2f  mov     rcx, rbx
0x180006d32  mov     rax, [rax]
0x180006d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d3a  mov     esi, eax
0x180006d3c  test    eax, eax
0x180006d3e  jz      short loc_180006D6B
0x180006d40  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180006d47  mov     dword ptr [rbx+8], 0C0000001h
0x180006d4e  mov     [rbx], rax
0x180006d51  cmp     byte ptr [rdi], 0
0x180006d54  jz      short loc_180006D63
0x180006d56  lea     rcx, [rbx+10h]; lpCriticalSection
0x180006d5a  mov     byte ptr [rdi], 0
0x180006d5d  call    cs:__imp_DeleteCriticalSection
0x180006d63  mov     rcx, rbx; Block
0x180006d66  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006d6b  mov     eax, esi
0x180006d6d  add     rsp, 28h
0x180006d71  pop     r15
0x180006d73  pop     r14
0x180006d75  pop     rdi
0x180006d76  pop     rsi
0x180006d77  pop     rbp
0x180006d78  pop     rbx
0x180006d79  retn
```
