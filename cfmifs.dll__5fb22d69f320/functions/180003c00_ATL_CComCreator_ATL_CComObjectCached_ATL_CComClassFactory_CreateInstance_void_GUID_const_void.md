# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003c00`
- end: `0x180003cf9`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003c00`
- `0x180003edc`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ccc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003ccc`
- `ntdll!RtlFreeHeap` at `0x180003ce4`
- `ntdll!RtlFreeHeap` at `0x180003ce4`
- `ntdll!RtlAllocateHeap` at `0x180003c44`
- `ntdll!RtlAllocateHeap` at `0x180003c44`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v7; // esi
  char *Heap; // rax
  char *v9; // rbx
  _BYTE *v10; // rdi

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x48u);
  v9 = Heap;
  if ( Heap )
  {
    *((_DWORD *)Heap + 2) = 0;
    *((_OWORD *)Heap + 1) = 0;
    *((_OWORD *)Heap + 2) = 0;
    *((_QWORD *)Heap + 6) = 0;
    Heap[56] = 0;
    *(_QWORD *)Heap = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    *((_QWORD *)Heap + 8) = a1;
    v10 = Heap + 56;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(Heap + 16));
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactory::`vftable';
      if ( *v10 )
      {
        *v10 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003c00  push    rbx
0x180003c02  push    rbp
0x180003c03  push    rsi
0x180003c04  push    rdi
0x180003c05  push    r14
0x180003c07  push    r15
0x180003c09  sub     rsp, 28h
0x180003c0d  mov     r14, r8
0x180003c10  mov     r15, rdx
0x180003c13  mov     rdi, rcx
0x180003c16  test    r8, r8
0x180003c19  jnz     short loc_180003C25
0x180003c1b  mov     eax, 80004003h
0x180003c20  jmp     loc_180003CEC
0x180003c25  mov     qword ptr [r8], 0
0x180003c2c  xor     edx, edx; Flags
0x180003c2e  mov     rcx, gs:60h
0x180003c37  mov     esi, 8007000Eh
0x180003c3c  lea     r8d, [rdx+48h]; Size
0x180003c40  mov     rcx, [rcx+30h]; HeapHandle
0x180003c44  call    cs:__imp_RtlAllocateHeap
0x180003c4a  mov     rbx, rax
0x180003c4d  test    rax, rax
0x180003c50  jz      loc_180003CEA
0x180003c56  mov     dword ptr [rax+8], 0
0x180003c5d  lea     rcx, [rbx+10h]; this
0x180003c61  xor     eax, eax
0x180003c63  xorps   xmm0, xmm0
0x180003c66  movups  xmmword ptr [rbx+10h], xmm0
0x180003c6a  movups  xmmword ptr [rbx+20h], xmm0
0x180003c6e  mov     [rbx+30h], rax
0x180003c72  mov     [rbx+38h], al
0x180003c75  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180003c7c  mov     [rbx], rax
0x180003c7f  mov     [rbx+40h], rdi
0x180003c83  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003c88  lea     rdi, [rbx+38h]
0x180003c8c  mov     esi, eax
0x180003c8e  test    eax, eax
0x180003c90  js      short loc_180003CAF
0x180003c92  mov     byte ptr [rdi], 1
0x180003c95  mov     r8, r14
0x180003c98  mov     rax, [rbx]
0x180003c9b  mov     rdx, r15
0x180003c9e  mov     rcx, rbx
0x180003ca1  mov     rax, [rax]
0x180003ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ca9  mov     esi, eax
0x180003cab  test    eax, eax
0x180003cad  jz      short loc_180003CEA
0x180003caf  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180003cb6  mov     dword ptr [rbx+8], 0C0000001h
0x180003cbd  mov     [rbx], rax
0x180003cc0  cmp     byte ptr [rdi], 0
0x180003cc3  jz      short loc_180003CD2
0x180003cc5  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003cc9  mov     byte ptr [rdi], 0
0x180003ccc  call    cs:__imp_DeleteCriticalSection
0x180003cd2  mov     rcx, gs:60h
0x180003cdb  mov     r8, rbx; P
0x180003cde  xor     edx, edx; Flags
0x180003ce0  mov     rcx, [rcx+30h]; HeapHandle
0x180003ce4  call    cs:__imp_RtlFreeHeap
0x180003cea  mov     eax, esi
0x180003cec  add     rsp, 28h
0x180003cf0  pop     r15
0x180003cf2  pop     r14
0x180003cf4  pop     rdi
0x180003cf5  pop     rsi
0x180003cf6  pop     rbp
0x180003cf7  pop     rbx
0x180003cf8  retn
```
