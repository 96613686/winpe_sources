# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIUpdateInfo>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b7f0`
- end: `0x18000b8d0`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIUpdateInfo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001dd4`
- `0x18000a404`
- `0x18000aaa8`
- `0x18000b7f0`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIUpdateInfo>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIUpdateInfo>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    *((_QWORD *)v9 + 3) = &IUpdateInfo::`vftable';
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIUpdateInfo>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIUpdateInfo>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b7f0  mov     [rsp+arg_0], rbx
0x18000b7f5  mov     [rsp+arg_8], rbp
0x18000b7fa  push    rsi
0x18000b7fb  push    rdi
0x18000b7fc  push    r12
0x18000b7fe  push    r14
0x18000b800  push    r15
0x18000b802  sub     rsp, 20h
0x18000b806  mov     r14, r8
0x18000b809  mov     r12, rdx
0x18000b80c  mov     r15, rcx
0x18000b80f  test    r8, r8
0x18000b812  jnz     short loc_18000B81E
0x18000b814  mov     eax, 80004003h
0x18000b819  jmp     loc_18000B8B8
0x18000b81e  mov     qword ptr [r8], 0
0x18000b825  mov     ebp, 8007000Eh
0x18000b82a  mov     ecx, 38h ; '8'; unsigned int
0x18000b82f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b834  mov     rsi, rax
0x18000b837  mov     [rsp+48h+arg_10], rax
0x18000b83c  test    rax, rax
0x18000b83f  jz      short loc_18000B88D
0x18000b841  mov     dword ptr [rax+8], 0
0x18000b848  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIUpdateInfo@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIUpdateInfo>::`vftable'
0x18000b84f  mov     [rsi], rax
0x18000b852  mov     rax, [r15]
0x18000b855  mov     rcx, r15
0x18000b858  mov     rax, [rax+20h]
0x18000b85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b861  mov     rdi, rax
0x18000b864  lea     rax, ??_7IUpdateInfo@@6B@; const IUpdateInfo::`vftable'
0x18000b86b  mov     [rsi+18h], rax
0x18000b86f  lea     rcx, [rsi+20h]
0x18000b873  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b878  lea     rax, ??_7?$CComContainedObject@VCImpIUpdateInfo@@@ATL@@6B@; const ATL::CComContainedObject<CImpIUpdateInfo>::`vftable'
0x18000b87f  mov     [rsi+18h], rax
0x18000b883  mov     [rsi+20h], rdi
0x18000b887  mov     [rsi+30h], r15
0x18000b88b  jmp     short loc_18000B88F
0x18000b88d  xor     esi, esi
0x18000b88f  test    rsi, rsi
0x18000b892  jz      short loc_18000B8B6
0x18000b894  mov     rax, [rsi]
0x18000b897  mov     r8, r14
0x18000b89a  mov     rdx, r12
0x18000b89d  mov     rcx, rsi
0x18000b8a0  mov     rax, [rax]
0x18000b8a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8a8  mov     ebp, eax
0x18000b8aa  test    eax, eax
0x18000b8ac  jz      short loc_18000B8B6
0x18000b8ae  mov     rcx, rsi; void *
0x18000b8b1  call    ??_G?$CComCachedTearOffObject@VCImpIUpdateInfo@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIUpdateInfo>::`scalar deleting destructor'(uint)
0x18000b8b6  mov     eax, ebp
0x18000b8b8  mov     rbx, [rsp+48h+arg_0]
0x18000b8bd  mov     rbp, [rsp+48h+arg_8]
0x18000b8c2  add     rsp, 20h
0x18000b8c6  pop     r15
0x18000b8c8  pop     r14
0x18000b8ca  pop     r12
0x18000b8cc  pop     rdi
0x18000b8cd  pop     rsi
0x18000b8ce  retn
```
