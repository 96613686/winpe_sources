# ATL::CComCreator<ATL::CComObject<CFilteringPlatformHelperClass>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006368`
- end: `0x180006483`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006340`

## callees

- `0x180001250`
- `0x1800042bc`
- `0x180005c7c`
- `0x180006368`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CFilteringPlatformHelperClass>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  void *v7; // rax
  __int64 v8; // rbx
  signed __int32 v9; // eax
  int v10; // ecx
  int v11; // eax
  signed __int32 v12; // eax
  __int64 v15; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x230u);
    if ( v7 )
      v8 = ATL::CComObject<CFilteringPlatformHelperClass>::CComObject<CFilteringPlatformHelperClass>((__int64)v7);
    else
      v8 = 0;
    v15 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v15;
  }
  if ( v8 )
  {
    do
      v9 = *(_DWORD *)(v8 + 64);
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 64), v9 + 1, v9) );
    v10 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v8 + 72));
    if ( v10 >= 0 )
      *(_BYTE *)(v8 + 112) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    do
      v12 = *(_DWORD *)(v8 + 64);
    while ( v12 != 0x7FFFFFFF && v12 != _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 64), v12 - 1, v12) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 168LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180006368  mov     [rsp+arg_10], r8
0x18000636d  mov     [rsp+arg_8], rdx
0x180006372  mov     [rsp+arg_0], rcx
0x180006377  push    rbx
0x180006378  push    rsi
0x180006379  push    rdi
0x18000637a  push    r14
0x18000637c  push    r15
0x18000637e  sub     rsp, 20h
0x180006382  mov     rsi, r8
0x180006385  mov     r14, rdx
0x180006388  test    r8, r8
0x18000638b  jnz     short loc_180006397
0x18000638d  mov     eax, 80004003h
0x180006392  jmp     loc_180006477
0x180006397  mov     qword ptr [r8], 0
0x18000639e  mov     edi, 8007000Eh
0x1800063a3  mov     dword ptr [rsp+48h+arg_0], edi
0x1800063a7  mov     [rsp+48h+arg_18], 0
0x1800063b0  mov     ecx, 230h; Size
0x1800063b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800063ba  test    rax, rax
0x1800063bd  jz      short loc_1800063CC
0x1800063bf  mov     rcx, rax
0x1800063c2  call    ??0?$CComObject@VCFilteringPlatformHelperClass@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CFilteringPlatformHelperClass>::CComObject<CFilteringPlatformHelperClass>(void *)
0x1800063c7  mov     rbx, rax
0x1800063ca  jmp     short loc_1800063CE
0x1800063cc  xor     ebx, ebx
0x1800063ce  mov     [rsp+48h+arg_18], rbx
0x1800063d3  jmp     short loc_1800063E8
0x1800063d5  mov     rsi, [rsp+48h+arg_10]
0x1800063da  mov     r14, [rsp+48h+arg_8]
0x1800063df  mov     edi, dword ptr [rsp+48h+arg_0]
0x1800063e3  mov     rbx, [rsp+48h+arg_18]
0x1800063e8  test    rbx, rbx
0x1800063eb  jz      loc_180006475
0x1800063f1  mov     r15d, 7FFFFFFFh
0x1800063f7  jmp     short loc_180006403
0x1800063f9  lea     ecx, [rax+1]
0x1800063fc  lock cmpxchg [rbx+40h], ecx
0x180006401  jz      short loc_18000640B
0x180006403  mov     eax, [rbx+40h]
0x180006406  cmp     eax, r15d
0x180006409  jnz     short loc_1800063F9
0x18000640b  lea     rcx, [rbx+48h]; this
0x18000640f  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180006414  mov     ecx, eax
0x180006416  test    eax, eax
0x180006418  js      short loc_18000641E
0x18000641a  mov     byte ptr [rbx+70h], 1
0x18000641e  xor     eax, eax
0x180006420  test    ecx, ecx
0x180006422  cmovs   eax, ecx
0x180006425  xor     edi, edi
0x180006427  test    eax, eax
0x180006429  cmovs   edi, eax
0x18000642c  jmp     short loc_180006438
0x18000642e  lea     ecx, [rax-1]
0x180006431  lock cmpxchg [rbx+40h], ecx
0x180006436  jz      short loc_180006440
0x180006438  mov     eax, [rbx+40h]
0x18000643b  cmp     eax, r15d
0x18000643e  jnz     short loc_18000642E
0x180006440  test    edi, edi
0x180006442  jnz     short loc_18000645E
0x180006444  mov     rax, [rbx]
0x180006447  mov     r8, rsi
0x18000644a  mov     rdx, r14
0x18000644d  mov     rcx, rbx
0x180006450  mov     rax, [rax]
0x180006453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006458  mov     edi, eax
0x18000645a  test    eax, eax
0x18000645c  jz      short loc_180006475
0x18000645e  mov     r8, [rbx]
0x180006461  mov     edx, 1
0x180006466  mov     rcx, rbx
0x180006469  mov     rax, [r8+0A8h]
0x180006470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006475  mov     eax, edi
0x180006477  add     rsp, 20h
0x18000647b  pop     r15
0x18000647d  pop     r14
0x18000647f  pop     rdi
0x180006480  pop     rsi
0x180006481  pop     rbx
0x180006482  retn
```
