# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002110`
- end: `0x1800021b3`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001170`
- `0x180001268`
- `0x180001b24`
- `0x180001d58`
- `0x180002110`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // ebx
  void *v8; // rax
  __int64 v9; // rax
  _BYTE *v10; // rdi
  int v11; // ecx
  int v12; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = operator new(0x48u);
  if ( v8 )
  {
    v9 = ATL::CComObjectCached<ATL::CComClassFactory>::CComObjectCached<ATL::CComClassFactory>(v8);
    v10 = (_BYTE *)v9;
    if ( v9 )
    {
      *(_QWORD *)(v9 + 64) = a1;
      v11 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 16));
      if ( v11 >= 0 )
        v10[56] = 1;
      v12 = 0;
      if ( v11 < 0 )
        v12 = v11;
      v7 = 0;
      if ( v12 < 0 )
        v7 = v12;
      if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v10)(v10, a2, a3)) != 0 )
        ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(v10);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180002110  push    rbx
0x180002112  push    rbp
0x180002113  push    rsi
0x180002114  push    rdi
0x180002115  push    r14
0x180002117  sub     rsp, 20h
0x18000211b  mov     rsi, r8
0x18000211e  mov     r14, rdx
0x180002121  mov     rbp, rcx
0x180002124  test    r8, r8
0x180002127  jnz     short loc_180002130
0x180002129  mov     eax, 80004003h
0x18000212e  jmp     short loc_1800021A8
0x180002130  mov     ecx, 48h ; 'H'; Size
0x180002135  mov     qword ptr [r8], 0
0x18000213c  mov     ebx, 8007000Eh
0x180002141  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002146  test    rax, rax
0x180002149  jz      short loc_1800021A6
0x18000214b  mov     rcx, rax
0x18000214e  call    ??0?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@PEAX@Z; ATL::CComObjectCached<ATL::CComClassFactory>::CComObjectCached<ATL::CComClassFactory>(void *)
0x180002153  mov     rdi, rax
0x180002156  test    rax, rax
0x180002159  jz      short loc_1800021A6
0x18000215b  lea     rcx, [rax+10h]; this
0x18000215f  mov     [rax+40h], rbp
0x180002163  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002168  mov     ecx, eax
0x18000216a  test    eax, eax
0x18000216c  js      short loc_180002172
0x18000216e  mov     byte ptr [rdi+38h], 1
0x180002172  xor     eax, eax
0x180002174  test    ecx, ecx
0x180002176  cmovs   eax, ecx
0x180002179  xor     ebx, ebx
0x18000217b  test    eax, eax
0x18000217d  cmovs   ebx, eax
0x180002180  test    ebx, ebx
0x180002182  jnz     short loc_18000219E
0x180002184  mov     rax, [rdi]
0x180002187  mov     r8, rsi
0x18000218a  mov     rdx, r14
0x18000218d  mov     rcx, rdi
0x180002190  mov     rax, [rax]
0x180002193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002198  mov     ebx, eax
0x18000219a  test    eax, eax
0x18000219c  jz      short loc_1800021A6
0x18000219e  mov     rcx, rdi; Block
0x1800021a1  call    ??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)
0x1800021a6  mov     eax, ebx
0x1800021a8  add     rsp, 20h
0x1800021ac  pop     r14
0x1800021ae  pop     rdi
0x1800021af  pop     rsi
0x1800021b0  pop     rbp
0x1800021b1  pop     rbx
0x1800021b2  retn
```
