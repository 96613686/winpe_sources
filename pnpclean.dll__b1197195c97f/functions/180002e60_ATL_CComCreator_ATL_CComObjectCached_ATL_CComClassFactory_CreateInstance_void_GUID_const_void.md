# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002e60`
- end: `0x180002f3a`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `218`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001160`
- `0x18000116c`
- `0x18000293c`
- `0x180002e60`
- `0x18000a010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002f1d`
- `KERNEL32!DeleteCriticalSection` at `0x180002f1d`

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
0x180002e60  push    rbx
0x180002e62  push    rbp
0x180002e63  push    rsi
0x180002e64  push    rdi
0x180002e65  push    r14
0x180002e67  push    r15
0x180002e69  sub     rsp, 28h
0x180002e6d  mov     r14, r8
0x180002e70  mov     r15, rdx
0x180002e73  mov     rdi, rcx
0x180002e76  test    r8, r8
0x180002e79  jnz     short loc_180002E85
0x180002e7b  mov     eax, 80004003h
0x180002e80  jmp     loc_180002F2D
0x180002e85  mov     ecx, 48h ; 'H'; Size
0x180002e8a  mov     qword ptr [r8], 0
0x180002e91  mov     esi, 8007000Eh
0x180002e96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e9b  mov     rbx, rax
0x180002e9e  test    rax, rax
0x180002ea1  jz      loc_180002F2B
0x180002ea7  mov     dword ptr [rax+8], 0
0x180002eae  lea     rcx, [rbx+10h]; this
0x180002eb2  xor     eax, eax
0x180002eb4  xorps   xmm0, xmm0
0x180002eb7  movups  xmmword ptr [rbx+10h], xmm0
0x180002ebb  movups  xmmword ptr [rbx+20h], xmm0
0x180002ebf  mov     [rbx+30h], rax
0x180002ec3  mov     [rbx+38h], al
0x180002ec6  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180002ecd  mov     [rbx], rax
0x180002ed0  mov     [rbx+40h], rdi
0x180002ed4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002ed9  lea     rdi, [rbx+38h]
0x180002edd  mov     esi, eax
0x180002edf  test    eax, eax
0x180002ee1  js      short loc_180002F00
0x180002ee3  mov     byte ptr [rdi], 1
0x180002ee6  mov     r8, r14
0x180002ee9  mov     rax, [rbx]
0x180002eec  mov     rdx, r15
0x180002eef  mov     rcx, rbx
0x180002ef2  mov     rax, [rax]
0x180002ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002efa  mov     esi, eax
0x180002efc  test    eax, eax
0x180002efe  jz      short loc_180002F2B
0x180002f00  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180002f07  mov     dword ptr [rbx+8], 0C0000001h
0x180002f0e  mov     [rbx], rax
0x180002f11  cmp     byte ptr [rdi], 0
0x180002f14  jz      short loc_180002F23
0x180002f16  lea     rcx, [rbx+10h]; lpCriticalSection
0x180002f1a  mov     byte ptr [rdi], 0
0x180002f1d  call    cs:__imp_DeleteCriticalSection
0x180002f23  mov     rcx, rbx; Block
0x180002f26  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002f2b  mov     eax, esi
0x180002f2d  add     rsp, 28h
0x180002f31  pop     r15
0x180002f33  pop     r14
0x180002f35  pop     rdi
0x180002f36  pop     rsi
0x180002f37  pop     rbp
0x180002f38  pop     rbx
0x180002f39  retn
```
