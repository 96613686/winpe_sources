# ATL::CComCreator<ATL::CComObject<CFmIfsEngine>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003b08`
- end: `0x180003bf1`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCFmIfsEngine@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003ae0`

## callees

- `0x180003b08`
- `0x180003edc`
- `0x180007010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180003b45`
- `ntdll!RtlAllocateHeap` at `0x180003b45`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CFmIfsEngine>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v6; // edi
  _DWORD *Heap; // rax
  _DWORD *v8; // rbx
  struct ATL::CAtlModule *v9; // rcx
  int v10; // ecx
  int v11; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x50u);
  v8 = Heap;
  if ( Heap )
  {
    v9 = ATL::_pAtlModule;
    Heap[2] = 0;
    *((_OWORD *)Heap + 1) = 0;
    *((_OWORD *)Heap + 2) = 0;
    *((_QWORD *)Heap + 6) = 0;
    *((_BYTE *)Heap + 56) = 0;
    *((_QWORD *)Heap + 8) = 0;
    *(_QWORD *)Heap = &ATL::CComObject<CFmIfsEngine>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    v10 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v8 + 4));
    if ( v10 >= 0 )
      *((_BYTE *)v8 + 56) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 48LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180003b08  push    rbx
0x180003b0a  push    rbp
0x180003b0b  push    rsi
0x180003b0c  push    rdi
0x180003b0d  sub     rsp, 28h
0x180003b11  mov     rsi, r8
0x180003b14  mov     rbp, rdx
0x180003b17  test    r8, r8
0x180003b1a  jnz     short loc_180003B26
0x180003b1c  mov     eax, 80004003h
0x180003b21  jmp     loc_180003BE8
0x180003b26  mov     qword ptr [r8], 0
0x180003b2d  xor     edx, edx; Flags
0x180003b2f  mov     rcx, gs:60h
0x180003b38  mov     edi, 8007000Eh
0x180003b3d  lea     r8d, [rdx+50h]; Size
0x180003b41  mov     rcx, [rcx+30h]; HeapHandle
0x180003b45  call    cs:__imp_RtlAllocateHeap
0x180003b4b  mov     rbx, rax
0x180003b4e  test    rax, rax
0x180003b51  jz      loc_180003BE6
0x180003b57  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003b5e  xorps   xmm0, xmm0
0x180003b61  mov     dword ptr [rax+8], 0
0x180003b68  xor     eax, eax
0x180003b6a  movups  xmmword ptr [rbx+10h], xmm0
0x180003b6e  movups  xmmword ptr [rbx+20h], xmm0
0x180003b72  mov     [rbx+30h], rax
0x180003b76  mov     [rbx+38h], al
0x180003b79  mov     [rbx+40h], rax
0x180003b7d  lea     rax, ??_7?$CComObject@VCFmIfsEngine@@@ATL@@6B@; const ATL::CComObject<CFmIfsEngine>::`vftable'
0x180003b84  mov     [rbx], rax
0x180003b87  mov     rax, [rcx]
0x180003b8a  mov     rax, [rax+8]
0x180003b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b93  lea     rcx, [rbx+10h]; this
0x180003b97  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003b9c  mov     ecx, eax
0x180003b9e  test    eax, eax
0x180003ba0  js      short loc_180003BA6
0x180003ba2  mov     byte ptr [rbx+38h], 1
0x180003ba6  xor     eax, eax
0x180003ba8  test    ecx, ecx
0x180003baa  cmovs   eax, ecx
0x180003bad  xor     edi, edi
0x180003baf  test    eax, eax
0x180003bb1  cmovs   edi, eax
0x180003bb4  test    edi, edi
0x180003bb6  jnz     short loc_180003BD2
0x180003bb8  mov     rax, [rbx]
0x180003bbb  mov     r8, rsi
0x180003bbe  mov     rdx, rbp
0x180003bc1  mov     rcx, rbx
0x180003bc4  mov     rax, [rax]
0x180003bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bcc  mov     edi, eax
0x180003bce  test    eax, eax
0x180003bd0  jz      short loc_180003BE6
0x180003bd2  mov     rcx, [rbx]
0x180003bd5  mov     edx, 1
0x180003bda  mov     rax, [rcx+30h]
0x180003bde  mov     rcx, rbx
0x180003be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003be6  mov     eax, edi
0x180003be8  add     rsp, 28h
0x180003bec  pop     rdi
0x180003bed  pop     rsi
0x180003bee  pop     rbp
0x180003bef  pop     rbx
0x180003bf0  retn
```
