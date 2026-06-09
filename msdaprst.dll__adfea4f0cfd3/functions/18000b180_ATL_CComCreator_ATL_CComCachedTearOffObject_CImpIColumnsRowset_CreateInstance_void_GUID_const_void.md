# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIColumnsRowset>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b180`
- end: `0x18000b255`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIColumnsRowset@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001dd4`
- `0x18000a404`
- `0x18000a990`
- `0x18000b180`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIColumnsRowset>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIColumnsRowset>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIColumnsRowset>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIColumnsRowset>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b180  mov     [rsp+arg_0], rbx
0x18000b185  mov     [rsp+arg_8], rbp
0x18000b18a  push    rsi
0x18000b18b  push    rdi
0x18000b18c  push    r12
0x18000b18e  push    r14
0x18000b190  push    r15
0x18000b192  sub     rsp, 20h
0x18000b196  mov     r14, r8
0x18000b199  mov     r12, rdx
0x18000b19c  mov     r15, rcx
0x18000b19f  test    r8, r8
0x18000b1a2  jnz     short loc_18000B1AE
0x18000b1a4  mov     eax, 80004003h
0x18000b1a9  jmp     loc_18000B23D
0x18000b1ae  mov     qword ptr [r8], 0
0x18000b1b5  mov     ebp, 8007000Eh
0x18000b1ba  mov     ecx, 38h ; '8'; unsigned int
0x18000b1bf  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b1c4  mov     rsi, rax
0x18000b1c7  mov     [rsp+48h+arg_10], rax
0x18000b1cc  test    rax, rax
0x18000b1cf  jz      short loc_18000B212
0x18000b1d1  mov     dword ptr [rax+8], 0
0x18000b1d8  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIColumnsRowset@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIColumnsRowset>::`vftable'
0x18000b1df  mov     [rsi], rax
0x18000b1e2  mov     rax, [r15]
0x18000b1e5  mov     rcx, r15
0x18000b1e8  mov     rax, [rax+20h]
0x18000b1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1f1  mov     rdi, rax
0x18000b1f4  lea     rcx, [rsi+20h]
0x18000b1f8  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b1fd  lea     rax, ??_7?$CComContainedObject@VCImpIColumnsRowset@@@ATL@@6B@; const ATL::CComContainedObject<CImpIColumnsRowset>::`vftable'
0x18000b204  mov     [rsi+18h], rax
0x18000b208  mov     [rsi+20h], rdi
0x18000b20c  mov     [rsi+30h], r15
0x18000b210  jmp     short loc_18000B214
0x18000b212  xor     esi, esi
0x18000b214  test    rsi, rsi
0x18000b217  jz      short loc_18000B23B
0x18000b219  mov     rax, [rsi]
0x18000b21c  mov     r8, r14
0x18000b21f  mov     rdx, r12
0x18000b222  mov     rcx, rsi
0x18000b225  mov     rax, [rax]
0x18000b228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b22d  mov     ebp, eax
0x18000b22f  test    eax, eax
0x18000b231  jz      short loc_18000B23B
0x18000b233  mov     rcx, rsi; void *
0x18000b236  call    ??_G?$CComCachedTearOffObject@VCImpIColumnsRowset@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIColumnsRowset>::`scalar deleting destructor'(uint)
0x18000b23b  mov     eax, ebp
0x18000b23d  mov     rbx, [rsp+48h+arg_0]
0x18000b242  mov     rbp, [rsp+48h+arg_8]
0x18000b247  add     rsp, 20h
0x18000b24b  pop     r15
0x18000b24d  pop     r14
0x18000b24f  pop     r12
0x18000b251  pop     rdi
0x18000b252  pop     rsi
0x18000b253  retn
```
