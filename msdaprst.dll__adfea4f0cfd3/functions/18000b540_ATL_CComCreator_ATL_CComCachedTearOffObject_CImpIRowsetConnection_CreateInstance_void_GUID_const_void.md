# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowsetConnection>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b540`
- end: `0x18000b620`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIRowsetConnection@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001dd4`
- `0x18000a404`
- `0x18000aa30`
- `0x18000b540`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIRowsetConnection>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIRowsetConnection>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    *((_QWORD *)v9 + 3) = &IRowsetConnection::`vftable';
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIRowsetConnection>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIRowsetConnection>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b540  mov     [rsp+arg_0], rbx
0x18000b545  mov     [rsp+arg_8], rbp
0x18000b54a  push    rsi
0x18000b54b  push    rdi
0x18000b54c  push    r12
0x18000b54e  push    r14
0x18000b550  push    r15
0x18000b552  sub     rsp, 20h
0x18000b556  mov     r14, r8
0x18000b559  mov     r12, rdx
0x18000b55c  mov     r15, rcx
0x18000b55f  test    r8, r8
0x18000b562  jnz     short loc_18000B56E
0x18000b564  mov     eax, 80004003h
0x18000b569  jmp     loc_18000B608
0x18000b56e  mov     qword ptr [r8], 0
0x18000b575  mov     ebp, 8007000Eh
0x18000b57a  mov     ecx, 38h ; '8'; unsigned int
0x18000b57f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b584  mov     rsi, rax
0x18000b587  mov     [rsp+48h+arg_10], rax
0x18000b58c  test    rax, rax
0x18000b58f  jz      short loc_18000B5DD
0x18000b591  mov     dword ptr [rax+8], 0
0x18000b598  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIRowsetConnection@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIRowsetConnection>::`vftable'
0x18000b59f  mov     [rsi], rax
0x18000b5a2  mov     rax, [r15]
0x18000b5a5  mov     rcx, r15
0x18000b5a8  mov     rax, [rax+20h]
0x18000b5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5b1  mov     rdi, rax
0x18000b5b4  lea     rax, ??_7IRowsetConnection@@6B@; const IRowsetConnection::`vftable'
0x18000b5bb  mov     [rsi+18h], rax
0x18000b5bf  lea     rcx, [rsi+20h]
0x18000b5c3  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b5c8  lea     rax, ??_7?$CComContainedObject@VCImpIRowsetConnection@@@ATL@@6B@; const ATL::CComContainedObject<CImpIRowsetConnection>::`vftable'
0x18000b5cf  mov     [rsi+18h], rax
0x18000b5d3  mov     [rsi+20h], rdi
0x18000b5d7  mov     [rsi+30h], r15
0x18000b5db  jmp     short loc_18000B5DF
0x18000b5dd  xor     esi, esi
0x18000b5df  test    rsi, rsi
0x18000b5e2  jz      short loc_18000B606
0x18000b5e4  mov     rax, [rsi]
0x18000b5e7  mov     r8, r14
0x18000b5ea  mov     rdx, r12
0x18000b5ed  mov     rcx, rsi
0x18000b5f0  mov     rax, [rax]
0x18000b5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5f8  mov     ebp, eax
0x18000b5fa  test    eax, eax
0x18000b5fc  jz      short loc_18000B606
0x18000b5fe  mov     rcx, rsi; void *
0x18000b601  call    ??_G?$CComCachedTearOffObject@VCImpIRowsetConnection@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIRowsetConnection>::`scalar deleting destructor'(uint)
0x18000b606  mov     eax, ebp
0x18000b608  mov     rbx, [rsp+48h+arg_0]
0x18000b60d  mov     rbp, [rsp+48h+arg_8]
0x18000b612  add     rsp, 20h
0x18000b616  pop     r15
0x18000b618  pop     r14
0x18000b61a  pop     r12
0x18000b61c  pop     rdi
0x18000b61d  pop     rsi
0x18000b61e  retn
```
