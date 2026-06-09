# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDocWrap>>,ATL::CComCreator<ATL::CComAggObject<CDocWrap>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f5b0`
- end: `0x18000f692`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCDocWrap@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCDocWrap@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `226`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001370`
- `0x18000c200`
- `0x18000f5b0`
- `0x18000fc5c`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f67d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f67d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CDocWrap>>,ATL::CComCreator<ATL::CComAggObject<CDocWrap>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  _QWORD *v7; // rax
  _DWORD *v8; // rbx

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      v6 = -2147024882;
      v7 = operator new(0x40u);
      v8 = v7;
      if ( v7 )
      {
        *((_DWORD *)v7 + 2) = 0;
        *v7 = &ATL::CComAggObject<CDocWrap>::`vftable';
        v7[6] = 0;
        v7[7] = 0;
        v7[2] = &ATL::CComContainedObject<CDocWrap>::`vftable';
        v7[3] = a1;
        _InterlockedIncrement(&dword_180024B28);
        v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v7)(v7, a2, a3);
        if ( v6 )
        {
          *(_QWORD *)v8 = &ATL::CComAggObject<CDocWrap>::`vftable';
          v8[2] = 1;
          _InterlockedDecrement(&dword_180024B28);
          CDocWrap::_Clear((CDocWrap *)(v8 + 4));
          operator delete(v8);
        }
      }
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)ATL::CComCreator<ATL::CComObject<CDocWrap>>::CreateInstance();
  }
  return v6;
}

```

## disassembly

```asm
0x18000f5b0  push    rbx
0x18000f5b2  push    rbp
0x18000f5b3  push    rsi
0x18000f5b4  push    rdi
0x18000f5b5  push    r12
0x18000f5b7  push    r14
0x18000f5b9  sub     rsp, 28h
0x18000f5bd  mov     rsi, r8
0x18000f5c0  mov     r14, rdx
0x18000f5c3  mov     rbp, rcx
0x18000f5c6  test    rcx, rcx
0x18000f5c9  jnz     short loc_18000F5D7
0x18000f5cb  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCDocWrap@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CDocWrap>>::CreateInstance(void *,_GUID const &,void * *)
0x18000f5d0  mov     edi, eax
0x18000f5d2  jmp     loc_18000F683
0x18000f5d7  test    rsi, rsi
0x18000f5da  jnz     short loc_18000F5E6
0x18000f5dc  mov     edi, 80004003h
0x18000f5e1  jmp     loc_18000F683
0x18000f5e6  mov     qword ptr [r8], 0
0x18000f5ed  mov     edi, 8007000Eh
0x18000f5f2  mov     ecx, 40h ; '@'; Size
0x18000f5f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f5fc  mov     rbx, rax
0x18000f5ff  mov     [rsp+58h+arg_0], rax
0x18000f604  test    rax, rax
0x18000f607  jz      short loc_18000F683
0x18000f609  mov     dword ptr [rax+8], 0
0x18000f610  lea     r12, ??_7?$CComAggObject@VCDocWrap@@@ATL@@6B@; const ATL::CComAggObject<CDocWrap>::`vftable'
0x18000f617  mov     [rax], r12
0x18000f61a  mov     qword ptr [rax+30h], 0
0x18000f622  mov     qword ptr [rax+38h], 0
0x18000f62a  lea     rax, ??_7?$CComContainedObject@VCDocWrap@@@ATL@@6B@; const ATL::CComContainedObject<CDocWrap>::`vftable'
0x18000f631  mov     [rbx+10h], rax
0x18000f635  mov     [rbx+18h], rbp
0x18000f639  lock inc cs:dword_180024B28
0x18000f640  test    rbx, rbx
0x18000f643  jz      short loc_18000F683
0x18000f645  mov     rax, [rbx]
0x18000f648  mov     r8, rsi
0x18000f64b  mov     rdx, r14
0x18000f64e  mov     rcx, rbx
0x18000f651  mov     rax, [rax]
0x18000f654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f659  mov     edi, eax
0x18000f65b  test    eax, eax
0x18000f65d  jz      short loc_18000F683
0x18000f65f  mov     [rbx], r12
0x18000f662  mov     dword ptr [rbx+8], 1
0x18000f669  lock dec cs:dword_180024B28
0x18000f670  lea     rcx, [rbx+10h]; this
0x18000f674  call    ?_Clear@CDocWrap@@AEAAXXZ; CDocWrap::_Clear(void)
0x18000f679  nop
0x18000f67a  mov     rcx, rbx
0x18000f67d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f683  mov     eax, edi
0x18000f685  add     rsp, 28h
0x18000f689  pop     r14
0x18000f68b  pop     r12
0x18000f68d  pop     rdi
0x18000f68e  pop     rsi
0x18000f68f  pop     rbp
0x18000f690  pop     rbx
0x18000f691  retn
```
