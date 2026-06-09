# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000b260`
- end: `0x18000b340`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIColumnsUpdateInfo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001dd4`
- `0x18000a404`
- `0x18000a9b8`
- `0x18000b260`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    *((_QWORD *)v9 + 3) = &CProviderDSO::`vftable'{for `IPersist'};
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIColumnsUpdateInfo>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000b260  mov     [rsp+arg_0], rbx
0x18000b265  mov     [rsp+arg_8], rbp
0x18000b26a  push    rsi
0x18000b26b  push    rdi
0x18000b26c  push    r12
0x18000b26e  push    r14
0x18000b270  push    r15
0x18000b272  sub     rsp, 20h
0x18000b276  mov     r14, r8
0x18000b279  mov     r12, rdx
0x18000b27c  mov     r15, rcx
0x18000b27f  test    r8, r8
0x18000b282  jnz     short loc_18000B28E
0x18000b284  mov     eax, 80004003h
0x18000b289  jmp     loc_18000B328
0x18000b28e  mov     qword ptr [r8], 0
0x18000b295  mov     ebp, 8007000Eh
0x18000b29a  mov     ecx, 38h ; '8'; unsigned int
0x18000b29f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b2a4  mov     rsi, rax
0x18000b2a7  mov     [rsp+48h+arg_10], rax
0x18000b2ac  test    rax, rax
0x18000b2af  jz      short loc_18000B2FD
0x18000b2b1  mov     dword ptr [rax+8], 0
0x18000b2b8  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIColumnsUpdateInfo@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::`vftable'
0x18000b2bf  mov     [rsi], rax
0x18000b2c2  mov     rax, [r15]
0x18000b2c5  mov     rcx, r15
0x18000b2c8  mov     rax, [rax+20h]
0x18000b2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2d1  mov     rdi, rax
0x18000b2d4  lea     rax, ??_7CProviderDSO@@6BIPersist@@@; const CProviderDSO::`vftable'{for `IPersist'}
0x18000b2db  mov     [rsi+18h], rax
0x18000b2df  lea     rcx, [rsi+20h]
0x18000b2e3  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b2e8  lea     rax, ??_7?$CComContainedObject@VCImpIColumnsUpdateInfo@@@ATL@@6B@; const ATL::CComContainedObject<CImpIColumnsUpdateInfo>::`vftable'
0x18000b2ef  mov     [rsi+18h], rax
0x18000b2f3  mov     [rsi+20h], rdi
0x18000b2f7  mov     [rsi+30h], r15
0x18000b2fb  jmp     short loc_18000B2FF
0x18000b2fd  xor     esi, esi
0x18000b2ff  test    rsi, rsi
0x18000b302  jz      short loc_18000B326
0x18000b304  mov     rax, [rsi]
0x18000b307  mov     r8, r14
0x18000b30a  mov     rdx, r12
0x18000b30d  mov     rcx, rsi
0x18000b310  mov     rax, [rax]
0x18000b313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b318  mov     ebp, eax
0x18000b31a  test    eax, eax
0x18000b31c  jz      short loc_18000B326
0x18000b31e  mov     rcx, rsi; void *
0x18000b321  call    ??_G?$CComCachedTearOffObject@VCImpIColumnsUpdateInfo@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIColumnsUpdateInfo>::`scalar deleting destructor'(uint)
0x18000b326  mov     eax, ebp
0x18000b328  mov     rbx, [rsp+48h+arg_0]
0x18000b32d  mov     rbp, [rsp+48h+arg_8]
0x18000b332  add     rsp, 20h
0x18000b336  pop     r15
0x18000b338  pop     r14
0x18000b33a  pop     r12
0x18000b33c  pop     rdi
0x18000b33d  pop     rsi
0x18000b33e  retn
```
