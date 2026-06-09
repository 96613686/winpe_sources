# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowsetUpdate>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b710`
- end: `0x18000b7e5`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIRowsetUpdate@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001dd4`
- `0x18000a404`
- `0x18000aa80`
- `0x18000b710`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowsetUpdate>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIRowsetUpdate>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b710  mov     [rsp+arg_0], rbx
0x18000b715  mov     [rsp+arg_8], rbp
0x18000b71a  push    rsi
0x18000b71b  push    rdi
0x18000b71c  push    r12
0x18000b71e  push    r14
0x18000b720  push    r15
0x18000b722  sub     rsp, 20h
0x18000b726  mov     r14, r8
0x18000b729  mov     r12, rdx
0x18000b72c  mov     r15, rcx
0x18000b72f  test    r8, r8
0x18000b732  jnz     short loc_18000B73E
0x18000b734  mov     eax, 80004003h
0x18000b739  jmp     loc_18000B7CD
0x18000b73e  mov     qword ptr [r8], 0
0x18000b745  mov     ebp, 8007000Eh
0x18000b74a  mov     ecx, 38h ; '8'; unsigned int
0x18000b74f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b754  mov     rsi, rax
0x18000b757  mov     [rsp+48h+arg_10], rax
0x18000b75c  test    rax, rax
0x18000b75f  jz      short loc_18000B7A2
0x18000b761  mov     dword ptr [rax+8], 0
0x18000b768  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIRowsetUpdate@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::`vftable'
0x18000b76f  mov     [rsi], rax
0x18000b772  mov     rax, [r15]
0x18000b775  mov     rcx, r15
0x18000b778  mov     rax, [rax+20h]
0x18000b77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b781  mov     rdi, rax
0x18000b784  lea     rcx, [rsi+20h]
0x18000b788  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b78d  lea     rax, ??_7?$CComContainedObject@VCImpIRowsetUpdate@@@ATL@@6B@; const ATL::CComContainedObject<CImpIRowsetUpdate>::`vftable'
0x18000b794  mov     [rsi+18h], rax
0x18000b798  mov     [rsi+20h], rdi
0x18000b79c  mov     [rsi+30h], r15
0x18000b7a0  jmp     short loc_18000B7A4
0x18000b7a2  xor     esi, esi
0x18000b7a4  test    rsi, rsi
0x18000b7a7  jz      short loc_18000B7CB
0x18000b7a9  mov     rax, [rsi]
0x18000b7ac  mov     r8, r14
0x18000b7af  mov     rdx, r12
0x18000b7b2  mov     rcx, rsi
0x18000b7b5  mov     rax, [rax]
0x18000b7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7bd  mov     ebp, eax
0x18000b7bf  test    eax, eax
0x18000b7c1  jz      short loc_18000B7CB
0x18000b7c3  mov     rcx, rsi; void *
0x18000b7c6  call    ??_G?$CComCachedTearOffObject@VCImpIRowsetUpdate@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIRowsetUpdate>::`scalar deleting destructor'(uint)
0x18000b7cb  mov     eax, ebp
0x18000b7cd  mov     rbx, [rsp+48h+arg_0]
0x18000b7d2  mov     rbp, [rsp+48h+arg_8]
0x18000b7d7  add     rsp, 20h
0x18000b7db  pop     r15
0x18000b7dd  pop     r14
0x18000b7df  pop     r12
0x18000b7e1  pop     rdi
0x18000b7e2  pop     rsi
0x18000b7e3  retn
```
