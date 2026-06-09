# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIColumnsInfo>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b0a0`
- end: `0x18000b175`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIColumnsInfo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001dd4`
- `0x18000a404`
- `0x18000a968`
- `0x18000b0a0`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIColumnsInfo>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // ebp
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rsi
  __int64 v10; // rdi

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = MMMAlloc(0x38u, a2);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIColumnsInfo>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b0a0  mov     [rsp+arg_0], rbx
0x18000b0a5  mov     [rsp+arg_8], rbp
0x18000b0aa  push    rsi
0x18000b0ab  push    rdi
0x18000b0ac  push    r12
0x18000b0ae  push    r14
0x18000b0b0  push    r15
0x18000b0b2  sub     rsp, 20h
0x18000b0b6  mov     r14, r8
0x18000b0b9  mov     r12, rdx
0x18000b0bc  mov     r15, rcx
0x18000b0bf  test    r8, r8
0x18000b0c2  jnz     short loc_18000B0CE
0x18000b0c4  mov     eax, 80004003h
0x18000b0c9  jmp     loc_18000B15D
0x18000b0ce  mov     qword ptr [r8], 0
0x18000b0d5  mov     ebp, 8007000Eh
0x18000b0da  mov     ecx, 38h ; '8'; unsigned int
0x18000b0df  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b0e4  mov     rsi, rax
0x18000b0e7  mov     [rsp+48h+arg_10], rax
0x18000b0ec  test    rax, rax
0x18000b0ef  jz      short loc_18000B132
0x18000b0f1  mov     dword ptr [rax+8], 0
0x18000b0f8  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIColumnsInfo@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`vftable'
0x18000b0ff  mov     [rsi], rax
0x18000b102  mov     rax, [r15]
0x18000b105  mov     rcx, r15
0x18000b108  mov     rax, [rax+20h]
0x18000b10c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b111  mov     rdi, rax
0x18000b114  lea     rcx, [rsi+20h]
0x18000b118  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b11d  lea     rax, ??_7?$CComContainedObject@VCImpIColumnsInfo@@@ATL@@6B@; const ATL::CComContainedObject<CImpIColumnsInfo>::`vftable'
0x18000b124  mov     [rsi+18h], rax
0x18000b128  mov     [rsi+20h], rdi
0x18000b12c  mov     [rsi+30h], r15
0x18000b130  jmp     short loc_18000B134
0x18000b132  xor     esi, esi
0x18000b134  test    rsi, rsi
0x18000b137  jz      short loc_18000B15B
0x18000b139  mov     rax, [rsi]
0x18000b13c  mov     r8, r14
0x18000b13f  mov     rdx, r12
0x18000b142  mov     rcx, rsi
0x18000b145  mov     rax, [rax]
0x18000b148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b14d  mov     ebp, eax
0x18000b14f  test    eax, eax
0x18000b151  jz      short loc_18000B15B
0x18000b153  mov     rcx, rsi; void *
0x18000b156  call    ??_G?$CComCachedTearOffObject@VCImpIColumnsInfo@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIColumnsInfo>::`scalar deleting destructor'(uint)
0x18000b15b  mov     eax, ebp
0x18000b15d  mov     rbx, [rsp+48h+arg_0]
0x18000b162  mov     rbp, [rsp+48h+arg_8]
0x18000b167  add     rsp, 20h
0x18000b16b  pop     r15
0x18000b16d  pop     r14
0x18000b16f  pop     r12
0x18000b171  pop     rdi
0x18000b172  pop     rsi
0x18000b173  retn
```
