# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowsetInfo>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b630`
- end: `0x18000b705`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIRowsetInfo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001dd4`
- `0x18000a404`
- `0x18000aa58`
- `0x18000b630`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowsetInfo>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIRowsetInfo>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIRowsetInfo>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIRowsetInfo>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b630  mov     [rsp+arg_0], rbx
0x18000b635  mov     [rsp+arg_8], rbp
0x18000b63a  push    rsi
0x18000b63b  push    rdi
0x18000b63c  push    r12
0x18000b63e  push    r14
0x18000b640  push    r15
0x18000b642  sub     rsp, 20h
0x18000b646  mov     r14, r8
0x18000b649  mov     r12, rdx
0x18000b64c  mov     r15, rcx
0x18000b64f  test    r8, r8
0x18000b652  jnz     short loc_18000B65E
0x18000b654  mov     eax, 80004003h
0x18000b659  jmp     loc_18000B6ED
0x18000b65e  mov     qword ptr [r8], 0
0x18000b665  mov     ebp, 8007000Eh
0x18000b66a  mov     ecx, 38h ; '8'; unsigned int
0x18000b66f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b674  mov     rsi, rax
0x18000b677  mov     [rsp+48h+arg_10], rax
0x18000b67c  test    rax, rax
0x18000b67f  jz      short loc_18000B6C2
0x18000b681  mov     dword ptr [rax+8], 0
0x18000b688  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIRowsetInfo@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIRowsetInfo>::`vftable'
0x18000b68f  mov     [rsi], rax
0x18000b692  mov     rax, [r15]
0x18000b695  mov     rcx, r15
0x18000b698  mov     rax, [rax+20h]
0x18000b69c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6a1  mov     rdi, rax
0x18000b6a4  lea     rcx, [rsi+20h]
0x18000b6a8  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b6ad  lea     rax, ??_7?$CComContainedObject@VCImpIRowsetInfo@@@ATL@@6B@; const ATL::CComContainedObject<CImpIRowsetInfo>::`vftable'
0x18000b6b4  mov     [rsi+18h], rax
0x18000b6b8  mov     [rsi+20h], rdi
0x18000b6bc  mov     [rsi+30h], r15
0x18000b6c0  jmp     short loc_18000B6C4
0x18000b6c2  xor     esi, esi
0x18000b6c4  test    rsi, rsi
0x18000b6c7  jz      short loc_18000B6EB
0x18000b6c9  mov     rax, [rsi]
0x18000b6cc  mov     r8, r14
0x18000b6cf  mov     rdx, r12
0x18000b6d2  mov     rcx, rsi
0x18000b6d5  mov     rax, [rax]
0x18000b6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6dd  mov     ebp, eax
0x18000b6df  test    eax, eax
0x18000b6e1  jz      short loc_18000B6EB
0x18000b6e3  mov     rcx, rsi; void *
0x18000b6e6  call    ??_G?$CComCachedTearOffObject@VCImpIRowsetInfo@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIRowsetInfo>::`scalar deleting destructor'(uint)
0x18000b6eb  mov     eax, ebp
0x18000b6ed  mov     rbx, [rsp+48h+arg_0]
0x18000b6f2  mov     rbp, [rsp+48h+arg_8]
0x18000b6f7  add     rsp, 20h
0x18000b6fb  pop     r15
0x18000b6fd  pop     r14
0x18000b6ff  pop     r12
0x18000b701  pop     rdi
0x18000b702  pop     rsi
0x18000b703  retn
```
