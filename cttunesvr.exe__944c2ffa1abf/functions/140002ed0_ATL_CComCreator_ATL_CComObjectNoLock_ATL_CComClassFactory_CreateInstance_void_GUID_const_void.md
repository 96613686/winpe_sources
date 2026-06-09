# ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140002ed0`
- end: `0x140002faa`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400011e0`
- `0x140001204`
- `0x140002ed0`
- `0x14000353c`
- `0x140007010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140002f8d`
- `KERNEL32!DeleteCriticalSection` at `0x140002f8d`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable';
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
0x140002ed0  push    rbx
0x140002ed2  push    rbp
0x140002ed3  push    rsi
0x140002ed4  push    rdi
0x140002ed5  push    r14
0x140002ed7  push    r15
0x140002ed9  sub     rsp, 28h
0x140002edd  mov     r14, r8
0x140002ee0  mov     r15, rdx
0x140002ee3  mov     rdi, rcx
0x140002ee6  test    r8, r8
0x140002ee9  jnz     short loc_140002EF5
0x140002eeb  mov     eax, 80004003h
0x140002ef0  jmp     loc_140002F9D
0x140002ef5  mov     ecx, 48h ; 'H'; Size
0x140002efa  mov     qword ptr [r8], 0
0x140002f01  mov     esi, 8007000Eh
0x140002f06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002f0b  mov     rbx, rax
0x140002f0e  test    rax, rax
0x140002f11  jz      loc_140002F9B
0x140002f17  mov     dword ptr [rax+8], 0
0x140002f1e  lea     rcx, [rbx+10h]; this
0x140002f22  xor     eax, eax
0x140002f24  xorps   xmm0, xmm0
0x140002f27  movups  xmmword ptr [rbx+10h], xmm0
0x140002f2b  movups  xmmword ptr [rbx+20h], xmm0
0x140002f2f  mov     [rbx+30h], rax
0x140002f33  mov     [rbx+38h], al
0x140002f36  lea     rax, ??_7?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable'
0x140002f3d  mov     [rbx], rax
0x140002f40  mov     [rbx+40h], rdi
0x140002f44  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140002f49  lea     rdi, [rbx+38h]
0x140002f4d  mov     esi, eax
0x140002f4f  test    eax, eax
0x140002f51  js      short loc_140002F70
0x140002f53  mov     byte ptr [rdi], 1
0x140002f56  mov     r8, r14
0x140002f59  mov     rax, [rbx]
0x140002f5c  mov     rdx, r15
0x140002f5f  mov     rcx, rbx
0x140002f62  mov     rax, [rax]
0x140002f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f6a  mov     esi, eax
0x140002f6c  test    eax, eax
0x140002f6e  jz      short loc_140002F9B
0x140002f70  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x140002f77  mov     dword ptr [rbx+8], 0C0000001h
0x140002f7e  mov     [rbx], rax
0x140002f81  cmp     byte ptr [rdi], 0
0x140002f84  jz      short loc_140002F93
0x140002f86  lea     rcx, [rbx+10h]; lpCriticalSection
0x140002f8a  mov     byte ptr [rdi], 0
0x140002f8d  call    cs:__imp_DeleteCriticalSection
0x140002f93  mov     rcx, rbx; Block
0x140002f96  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002f9b  mov     eax, esi
0x140002f9d  add     rsp, 28h
0x140002fa1  pop     r15
0x140002fa3  pop     r14
0x140002fa5  pop     rdi
0x140002fa6  pop     rsi
0x140002fa7  pop     rbp
0x140002fa8  pop     rbx
0x140002fa9  retn
```
