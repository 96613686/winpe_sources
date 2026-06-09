# ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIChapteredRowset>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000afc0`
- end: `0x18000b095`
- name: `?CreateInstance@?$CComCreator@V?$CComCachedTearOffObject@VCImpIChapteredRowset@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001dd4`
- `0x18000a404`
- `0x18000a940`
- `0x18000afc0`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComCachedTearOffObject<CImpIChapteredRowset>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`vftable';
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>((__int64)(v9 + 32));
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CImpIChapteredRowset>::`vftable';
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
      ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000afc0  mov     [rsp+arg_0], rbx
0x18000afc5  mov     [rsp+arg_8], rbp
0x18000afca  push    rsi
0x18000afcb  push    rdi
0x18000afcc  push    r12
0x18000afce  push    r14
0x18000afd0  push    r15
0x18000afd2  sub     rsp, 20h
0x18000afd6  mov     r14, r8
0x18000afd9  mov     r12, rdx
0x18000afdc  mov     r15, rcx
0x18000afdf  test    r8, r8
0x18000afe2  jnz     short loc_18000AFEE
0x18000afe4  mov     eax, 80004003h
0x18000afe9  jmp     loc_18000B07D
0x18000afee  mov     qword ptr [r8], 0
0x18000aff5  mov     ebp, 8007000Eh
0x18000affa  mov     ecx, 38h ; '8'; unsigned int
0x18000afff  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000b004  mov     rsi, rax
0x18000b007  mov     [rsp+48h+arg_10], rax
0x18000b00c  test    rax, rax
0x18000b00f  jz      short loc_18000B052
0x18000b011  mov     dword ptr [rax+8], 0
0x18000b018  lea     rax, ??_7?$CComCachedTearOffObject@VCImpIChapteredRowset@@@ATL@@6B@; const ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`vftable'
0x18000b01f  mov     [rsi], rax
0x18000b022  mov     rax, [r15]
0x18000b025  mov     rcx, r15
0x18000b028  mov     rax, [rax+20h]
0x18000b02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b031  mov     rdi, rax
0x18000b034  lea     rcx, [rsi+20h]
0x18000b038  call    ??0?$CComTearOffObjectBase@VCRowset@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>::CComTearOffObjectBase<CRowset,ATL::CComMultiThreadModel>(void)
0x18000b03d  lea     rax, ??_7?$CComContainedObject@VCImpIChapteredRowset@@@ATL@@6B@; const ATL::CComContainedObject<CImpIChapteredRowset>::`vftable'
0x18000b044  mov     [rsi+18h], rax
0x18000b048  mov     [rsi+20h], rdi
0x18000b04c  mov     [rsi+30h], r15
0x18000b050  jmp     short loc_18000B054
0x18000b052  xor     esi, esi
0x18000b054  test    rsi, rsi
0x18000b057  jz      short loc_18000B07B
0x18000b059  mov     rax, [rsi]
0x18000b05c  mov     r8, r14
0x18000b05f  mov     rdx, r12
0x18000b062  mov     rcx, rsi
0x18000b065  mov     rax, [rax]
0x18000b068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b06d  mov     ebp, eax
0x18000b06f  test    eax, eax
0x18000b071  jz      short loc_18000B07B
0x18000b073  mov     rcx, rsi; void *
0x18000b076  call    ??_G?$CComCachedTearOffObject@VCImpIChapteredRowset@@@ATL@@QEAAPEAXI@Z; ATL::CComCachedTearOffObject<CImpIChapteredRowset>::`scalar deleting destructor'(uint)
0x18000b07b  mov     eax, ebp
0x18000b07d  mov     rbx, [rsp+48h+arg_0]
0x18000b082  mov     rbp, [rsp+48h+arg_8]
0x18000b087  add     rsp, 20h
0x18000b08b  pop     r15
0x18000b08d  pop     r14
0x18000b08f  pop     r12
0x18000b091  pop     rdi
0x18000b092  pop     rsi
0x18000b093  retn
```
