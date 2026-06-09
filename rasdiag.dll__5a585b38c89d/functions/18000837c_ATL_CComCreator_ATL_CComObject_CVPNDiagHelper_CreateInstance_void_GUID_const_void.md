# ATL::CComCreator<ATL::CComObject<CVPNDiagHelper>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000837c`
- end: `0x180008498`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCVPNDiagHelper@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `284`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008350`

## callees

- `0x1800011dc`
- `0x18000447c`
- `0x180008194`
- `0x18000837c`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CVPNDiagHelper>>::CreateInstance(
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
    v7 = operator new(0x5B0u);
    if ( v7 )
      v8 = ATL::CComObject<CVPNDiagHelper>::CComObject<CVPNDiagHelper>((__int64)v7);
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
      v9 = *(_DWORD *)(v8 + 56);
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 56), v9 + 1, v9) );
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 64));
    if ( v10 >= 0 )
      *(_BYTE *)(v8 + 104) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    do
      v12 = *(_DWORD *)(v8 + 56);
    while ( v12 != 0x7FFFFFFF && v12 != _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 56), v12 - 1, v12) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 168LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000837c  mov     [rsp+arg_10], r8
0x180008381  mov     [rsp+arg_8], rdx
0x180008386  mov     [rsp+arg_0], rcx
0x18000838b  push    rbx
0x18000838c  push    rsi
0x18000838d  push    rdi
0x18000838e  push    r14
0x180008390  push    r15
0x180008392  sub     rsp, 20h
0x180008396  mov     rsi, r8
0x180008399  mov     r14, rdx
0x18000839c  test    r8, r8
0x18000839f  jnz     short loc_1800083AB
0x1800083a1  mov     eax, 80004003h
0x1800083a6  jmp     loc_18000848B
0x1800083ab  mov     qword ptr [r8], 0
0x1800083b2  mov     edi, 8007000Eh
0x1800083b7  mov     dword ptr [rsp+48h+arg_0], edi
0x1800083bb  mov     [rsp+48h+arg_18], 0
0x1800083c4  mov     ecx, 5B0h; Size
0x1800083c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800083ce  test    rax, rax
0x1800083d1  jz      short loc_1800083E0
0x1800083d3  mov     rcx, rax
0x1800083d6  call    ??0?$CComObject@VCVPNDiagHelper@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CVPNDiagHelper>::CComObject<CVPNDiagHelper>(void *)
0x1800083db  mov     rbx, rax
0x1800083de  jmp     short loc_1800083E2
0x1800083e0  xor     ebx, ebx
0x1800083e2  mov     [rsp+48h+arg_18], rbx
0x1800083e7  jmp     short loc_1800083FC
0x1800083e9  mov     rsi, [rsp+48h+arg_10]
0x1800083ee  mov     r14, [rsp+48h+arg_8]
0x1800083f3  mov     edi, dword ptr [rsp+48h+arg_0]
0x1800083f7  mov     rbx, [rsp+48h+arg_18]
0x1800083fc  test    rbx, rbx
0x1800083ff  jz      loc_180008489
0x180008405  mov     r15d, 7FFFFFFFh
0x18000840b  jmp     short loc_180008417
0x18000840d  lea     ecx, [rax+1]
0x180008410  lock cmpxchg [rbx+38h], ecx
0x180008415  jz      short loc_18000841F
0x180008417  mov     eax, [rbx+38h]
0x18000841a  cmp     eax, r15d
0x18000841d  jnz     short loc_18000840D
0x18000841f  lea     rcx, [rbx+40h]; this
0x180008423  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180008428  mov     ecx, eax
0x18000842a  test    eax, eax
0x18000842c  js      short loc_180008432
0x18000842e  mov     byte ptr [rbx+68h], 1
0x180008432  xor     eax, eax
0x180008434  test    ecx, ecx
0x180008436  cmovs   eax, ecx
0x180008439  xor     edi, edi
0x18000843b  test    eax, eax
0x18000843d  cmovs   edi, eax
0x180008440  jmp     short loc_18000844C
0x180008442  lea     ecx, [rax-1]
0x180008445  lock cmpxchg [rbx+38h], ecx
0x18000844a  jz      short loc_180008454
0x18000844c  mov     eax, [rbx+38h]
0x18000844f  cmp     eax, r15d
0x180008452  jnz     short loc_180008442
0x180008454  test    edi, edi
0x180008456  jnz     short loc_180008472
0x180008458  mov     rax, [rbx]
0x18000845b  mov     r8, rsi
0x18000845e  mov     rdx, r14
0x180008461  mov     rcx, rbx
0x180008464  mov     rax, [rax]
0x180008467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000846c  mov     edi, eax
0x18000846e  test    eax, eax
0x180008470  jz      short loc_180008489
0x180008472  mov     r8, [rbx]
0x180008475  mov     edx, 1
0x18000847a  mov     rcx, rbx
0x18000847d  mov     rax, [r8+0A8h]
0x180008484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008489  mov     eax, edi
0x18000848b  add     rsp, 20h
0x18000848f  pop     r15
0x180008491  pop     r14
0x180008493  pop     rdi
0x180008494  pop     rsi
0x180008495  pop     rbx
0x180008496  retn
```
