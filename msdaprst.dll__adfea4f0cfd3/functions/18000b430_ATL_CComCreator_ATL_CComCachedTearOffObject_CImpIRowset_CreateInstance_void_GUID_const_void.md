# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowset>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b430`
- end: `0x18000b531`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIRowset@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001dd4`
- `0x18000a404`
- `0x18000aa08`
- `0x18000b430`
- `0x18001ae88`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowset>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // ebp
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // r14
  __int64 v10; // rsi

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = MMMAlloc(0x48u, a2);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIRowset>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &CImpIRowset::`vftable';
    *((_DWORD *)v9 + 16) = 0;
    *((_QWORD *)v9 + 7) = &CImpIRowset::CNotUpdt_BidGeneric::`vftable';
    *((_DWORD *)v9 + 16) = bidObtainItemIDW(
                             `CImpIRowset::CNotUpdt_BidGeneric::BidObtainID'::`7'::_bidPtrSA_051_337[0],
                             v9 + 56);
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIRowset>::`vftable';
    *((_QWORD *)v9 + 4) = v10;
    *((_QWORD *)v9 + 6) = a1;
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3);
    if ( v7 )
      ATL::CComCachedTearOffObject<CImpIRowset>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b430  push    rbx
0x18000b432  push    rbp
0x18000b433  push    rsi
0x18000b434  push    rdi
0x18000b435  push    r12
0x18000b437  push    r13
0x18000b439  push    r14
0x18000b43b  push    r15
0x18000b43d  sub     rsp, 28h
0x18000b441  mov     r15, r8
0x18000b444  mov     r12, rdx
0x18000b447  mov     r13, rcx
0x18000b44a  test    r8, r8
0x18000b44d  jnz     short loc_18000B459
0x18000b44f  mov     eax, 80004003h
0x18000b454  jmp     loc_18000B51F
0x18000b459  mov     qword ptr [r8], 0
0x18000b460  mov     ebp, 8007000Eh
0x18000b465  mov     ecx, 48h ; 'H'; unsigned int
0x18000b46a  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b46f  mov     r14, rax
0x18000b472  mov     [rsp+68h+arg_10], rax
0x18000b47a  test    rax, rax
0x18000b47d  jz      short loc_18000B4F3
0x18000b47f  mov     dword ptr [rax+8], 0
0x18000b486  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIRowset@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIRowset>::`vftable'
0x18000b48d  mov     [r14], rax
0x18000b490  mov     rax, [r13+0]
0x18000b494  mov     rcx, r13
0x18000b497  mov     rax, [rax+20h]
0x18000b49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4a0  mov     rsi, rax
0x18000b4a3  lea     rcx, [r14+20h]
0x18000b4a7  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b4ac  lea     rax, ??_7CImpIRowset@@6B@; const CImpIRowset::`vftable'
0x18000b4b3  mov     [r14+18h], rax
0x18000b4b7  mov     dword ptr [r14+40h], 0
0x18000b4bf  lea     rax, ??_7CNotUpdt_BidGeneric@CImpIRowset@@6B@; const CImpIRowset::CNotUpdt_BidGeneric::`vftable'
0x18000b4c6  mov     [r14+38h], rax
0x18000b4ca  lea     rdx, [r14+38h]
0x18000b4ce  mov     rcx, cs:?_bidPtrSA_051_337@?6??BidObtainID@CNotUpdt_BidGeneric@CImpIRowset@@AEAAHPEBX@Z@4REBGEB; ushort const * const `CImpIRowset::CNotUpdt_BidGeneric::BidObtainID(void const *)'::`7'::_bidPtrSA_051_337
0x18000b4d5  call    _bidObtainItemIDW
0x18000b4da  mov     [r14+40h], eax
0x18000b4de  lea     rax, ??_7?$CComContainedObject@VCImpIRowset@@@ATL@@6B@; const ATL::CComContainedObject<CImpIRowset>::`vftable'
0x18000b4e5  mov     [r14+18h], rax
0x18000b4e9  mov     [r14+20h], rsi
0x18000b4ed  mov     [r14+30h], r13
0x18000b4f1  jmp     short loc_18000B4F6
0x18000b4f3  xor     r14d, r14d
0x18000b4f6  test    r14, r14
0x18000b4f9  jz      short loc_18000B51D
0x18000b4fb  mov     rax, [r14]
0x18000b4fe  mov     r8, r15
0x18000b501  mov     rdx, r12
0x18000b504  mov     rcx, r14
0x18000b507  mov     rax, [rax]
0x18000b50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b50f  mov     ebp, eax
0x18000b511  test    eax, eax
0x18000b513  jz      short loc_18000B51D
0x18000b515  mov     rcx, r14; void *
0x18000b518  call    ??_G?$CComCachedTearOffObject@VCImpIRowset@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIRowset>::`scalar deleting destructor'(uint)
0x18000b51d  mov     eax, ebp
0x18000b51f  add     rsp, 28h
0x18000b523  pop     r15
0x18000b525  pop     r14
0x18000b527  pop     r13
0x18000b529  pop     r12
0x18000b52b  pop     rdi
0x18000b52c  pop     rsi
0x18000b52d  pop     rbp
0x18000b52e  pop     rbx
0x18000b52f  retn
```
