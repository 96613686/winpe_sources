# ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140001cb0`
- end: `0x140001d7e`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001014`
- `0x140001054`
- `0x140001cb0`
- `0x14000232c`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140001d61`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140001d61`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v7; // esi
  char *v8; // rax
  _BYTE *v9; // rbx

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
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 16));
    if ( v7 < 0 || (v9[56] = 1, (v7 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0) )
    {
      *(_QWORD *)v9 = &ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable';
      *((_DWORD *)v9 + 2) = 1;
      if ( v9[56] )
      {
        v9[56] = 0;
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
0x140001cb0  push    rbx
0x140001cb2  push    rbp
0x140001cb3  push    rsi
0x140001cb4  push    rdi
0x140001cb5  push    r12
0x140001cb7  push    r14
0x140001cb9  sub     rsp, 28h
0x140001cbd  mov     r14, r8
0x140001cc0  mov     rbp, rdx
0x140001cc3  mov     rdi, rcx
0x140001cc6  test    r8, r8
0x140001cc9  jnz     short loc_140001CD5
0x140001ccb  mov     eax, 80004003h
0x140001cd0  jmp     loc_140001D71
0x140001cd5  mov     ecx, 48h ; 'H'; Size
0x140001cda  mov     qword ptr [r8], 0
0x140001ce1  mov     esi, 8007000Eh
0x140001ce6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001ceb  mov     rbx, rax
0x140001cee  test    rax, rax
0x140001cf1  jz      short loc_140001D6F
0x140001cf3  mov     dword ptr [rax+8], 0
0x140001cfa  lea     r12, ??_7?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable'
0x140001d01  xorps   xmm0, xmm0
0x140001d04  lea     rcx, [rbx+10h]; this
0x140001d08  movups  xmmword ptr [rbx+10h], xmm0
0x140001d0c  xor     eax, eax
0x140001d0e  movups  xmmword ptr [rbx+20h], xmm0
0x140001d12  mov     [rbx+30h], rax
0x140001d16  mov     [rbx+38h], al
0x140001d19  mov     [rbx], r12
0x140001d1c  mov     [rbx+40h], rdi
0x140001d20  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140001d25  mov     esi, eax
0x140001d27  test    eax, eax
0x140001d29  js      short loc_140001D49
0x140001d2b  mov     byte ptr [rbx+38h], 1
0x140001d2f  mov     r8, r14
0x140001d32  mov     rax, [rbx]
0x140001d35  mov     rdx, rbp
0x140001d38  mov     rcx, rbx
0x140001d3b  mov     rax, [rax]
0x140001d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001d43  mov     esi, eax
0x140001d45  test    eax, eax
0x140001d47  jz      short loc_140001D6F
0x140001d49  mov     [rbx], r12
0x140001d4c  mov     dword ptr [rbx+8], 1
0x140001d53  cmp     byte ptr [rbx+38h], 0
0x140001d57  jz      short loc_140001D67
0x140001d59  lea     rcx, [rbx+10h]; lpCriticalSection
0x140001d5d  mov     byte ptr [rbx+38h], 0
0x140001d61  call    cs:__imp_DeleteCriticalSection
0x140001d67  mov     rcx, rbx; Block
0x140001d6a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001d6f  mov     eax, esi
0x140001d71  add     rsp, 28h
0x140001d75  pop     r14
0x140001d77  pop     r12
0x140001d79  pop     rdi
0x140001d7a  pop     rsi
0x140001d7b  pop     rbp
0x140001d7c  pop     rbx
0x140001d7d  retn
```
