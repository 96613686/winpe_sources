# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIAccessor>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000aee0`
- end: `0x18000afb5`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIAccessor@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001dd4`
- `0x18000a404`
- `0x18000a918`
- `0x18000aee0`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIAccessor>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIAccessor>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIAccessor>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIAccessor>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000aee0  mov     [rsp+arg_0], rbx
0x18000aee5  mov     [rsp+arg_8], rbp
0x18000aeea  push    rsi
0x18000aeeb  push    rdi
0x18000aeec  push    r12
0x18000aeee  push    r14
0x18000aef0  push    r15
0x18000aef2  sub     rsp, 20h
0x18000aef6  mov     r14, r8
0x18000aef9  mov     r12, rdx
0x18000aefc  mov     r15, rcx
0x18000aeff  test    r8, r8
0x18000af02  jnz     short loc_18000AF0E
0x18000af04  mov     eax, 80004003h
0x18000af09  jmp     loc_18000AF9D
0x18000af0e  mov     qword ptr [r8], 0
0x18000af15  mov     ebp, 8007000Eh
0x18000af1a  mov     ecx, 38h ; '8'; unsigned int
0x18000af1f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000af24  mov     rsi, rax
0x18000af27  mov     [rsp+48h+arg_10], rax
0x18000af2c  test    rax, rax
0x18000af2f  jz      short loc_18000AF72
0x18000af31  mov     dword ptr [rax+8], 0
0x18000af38  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIAccessor@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIAccessor>::`vftable'
0x18000af3f  mov     [rsi], rax
0x18000af42  mov     rax, [r15]
0x18000af45  mov     rcx, r15
0x18000af48  mov     rax, [rax+20h]
0x18000af4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af51  mov     rdi, rax
0x18000af54  lea     rcx, [rsi+20h]
0x18000af58  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000af5d  lea     rax, ??_7?$CComContainedObject@VCImpIAccessor@@@ATL@@6B@; const ATL::CComContainedObject<CImpIAccessor>::`vftable'
0x18000af64  mov     [rsi+18h], rax
0x18000af68  mov     [rsi+20h], rdi
0x18000af6c  mov     [rsi+30h], r15
0x18000af70  jmp     short loc_18000AF74
0x18000af72  xor     esi, esi
0x18000af74  test    rsi, rsi
0x18000af77  jz      short loc_18000AF9B
0x18000af79  mov     rax, [rsi]
0x18000af7c  mov     r8, r14
0x18000af7f  mov     rdx, r12
0x18000af82  mov     rcx, rsi
0x18000af85  mov     rax, [rax]
0x18000af88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af8d  mov     ebp, eax
0x18000af8f  test    eax, eax
0x18000af91  jz      short loc_18000AF9B
0x18000af93  mov     rcx, rsi; void *
0x18000af96  call    ??_G?$CComCachedTearOffObject@VCImpIAccessor@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIAccessor>::`scalar deleting destructor'(uint)
0x18000af9b  mov     eax, ebp
0x18000af9d  mov     rbx, [rsp+48h+arg_0]
0x18000afa2  mov     rbp, [rsp+48h+arg_8]
0x18000afa7  add     rsp, 20h
0x18000afab  pop     r15
0x18000afad  pop     r14
0x18000afaf  pop     r12
0x18000afb1  pop     rdi
0x18000afb2  pop     rsi
0x18000afb3  retn
```
