# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIConvertType>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b350`
- end: `0x18000b425`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIConvertType@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001dd4`
- `0x18000a404`
- `0x18000a9e0`
- `0x18000b350`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIConvertType>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIConvertType>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIConvertType>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIConvertType>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b350  mov     [rsp+arg_0], rbx
0x18000b355  mov     [rsp+arg_8], rbp
0x18000b35a  push    rsi
0x18000b35b  push    rdi
0x18000b35c  push    r12
0x18000b35e  push    r14
0x18000b360  push    r15
0x18000b362  sub     rsp, 20h
0x18000b366  mov     r14, r8
0x18000b369  mov     r12, rdx
0x18000b36c  mov     r15, rcx
0x18000b36f  test    r8, r8
0x18000b372  jnz     short loc_18000B37E
0x18000b374  mov     eax, 80004003h
0x18000b379  jmp     loc_18000B40D
0x18000b37e  mov     qword ptr [r8], 0
0x18000b385  mov     ebp, 8007000Eh
0x18000b38a  mov     ecx, 38h ; '8'; unsigned int
0x18000b38f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b394  mov     rsi, rax
0x18000b397  mov     [rsp+48h+arg_10], rax
0x18000b39c  test    rax, rax
0x18000b39f  jz      short loc_18000B3E2
0x18000b3a1  mov     dword ptr [rax+8], 0
0x18000b3a8  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIConvertType@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIConvertType>::`vftable'
0x18000b3af  mov     [rsi], rax
0x18000b3b2  mov     rax, [r15]
0x18000b3b5  mov     rcx, r15
0x18000b3b8  mov     rax, [rax+20h]
0x18000b3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3c1  mov     rdi, rax
0x18000b3c4  lea     rcx, [rsi+20h]
0x18000b3c8  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b3cd  lea     rax, ??_7?$CComContainedObject@VCImpIConvertType@@@ATL@@6B@; const ATL::CComContainedObject<CImpIConvertType>::`vftable'
0x18000b3d4  mov     [rsi+18h], rax
0x18000b3d8  mov     [rsi+20h], rdi
0x18000b3dc  mov     [rsi+30h], r15
0x18000b3e0  jmp     short loc_18000B3E4
0x18000b3e2  xor     esi, esi
0x18000b3e4  test    rsi, rsi
0x18000b3e7  jz      short loc_18000B40B
0x18000b3e9  mov     rax, [rsi]
0x18000b3ec  mov     r8, r14
0x18000b3ef  mov     rdx, r12
0x18000b3f2  mov     rcx, rsi
0x18000b3f5  mov     rax, [rax]
0x18000b3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3fd  mov     ebp, eax
0x18000b3ff  test    eax, eax
0x18000b401  jz      short loc_18000B40B
0x18000b403  mov     rcx, rsi; void *
0x18000b406  call    ??_G?$CComCachedTearOffObject@VCImpIConvertType@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIConvertType>::`scalar deleting destructor'(uint)
0x18000b40b  mov     eax, ebp
0x18000b40d  mov     rbx, [rsp+48h+arg_0]
0x18000b412  mov     rbp, [rsp+48h+arg_8]
0x18000b417  add     rsp, 20h
0x18000b41b  pop     r15
0x18000b41d  pop     r14
0x18000b41f  pop     r12
0x18000b421  pop     rdi
0x18000b422  pop     rsi
0x18000b423  retn
```
