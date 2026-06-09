# ATL::CComCreator<ATL::CComObject<CDpUrlAccessor>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004628`
- end: `0x180004743`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCDpUrlAccessor@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `283`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004210`

## callees

- `0x1800011c4`
- `0x1800028fc`
- `0x180002e98`
- `0x180004628`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CDpUrlAccessor>>::CreateInstance(
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
    v7 = operator new(0xE0u);
    if ( v7 )
      v8 = ATL::CComObject<CDpUrlAccessor>::CComObject<CDpUrlAccessor>((__int64)v7);
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
      v9 = *(_DWORD *)(v8 + 8);
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 8), v9 + 1, v9) );
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 16));
    if ( v10 >= 0 )
      *(_BYTE *)(v8 + 56) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    do
      v12 = *(_DWORD *)(v8 + 8);
    while ( v12 != 0x7FFFFFFF && v12 != _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 8), v12 - 1, v12) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 152LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180004628  mov     [rsp+arg_10], r8
0x18000462d  mov     [rsp+arg_8], rdx
0x180004632  mov     [rsp+arg_0], rcx
0x180004637  push    rbx
0x180004638  push    rsi
0x180004639  push    rdi
0x18000463a  push    r14
0x18000463c  push    r15
0x18000463e  sub     rsp, 20h
0x180004642  mov     rsi, r8
0x180004645  mov     r14, rdx
0x180004648  test    r8, r8
0x18000464b  jnz     short loc_180004657
0x18000464d  mov     eax, 80004003h
0x180004652  jmp     loc_180004737
0x180004657  mov     qword ptr [r8], 0
0x18000465e  mov     edi, 8007000Eh
0x180004663  mov     dword ptr [rsp+48h+arg_0], edi
0x180004667  mov     [rsp+48h+arg_18], 0
0x180004670  mov     ecx, 0E0h; Size
0x180004675  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000467a  test    rax, rax
0x18000467d  jz      short loc_18000468C
0x18000467f  mov     rcx, rax
0x180004682  call    ??0?$CComObject@VCDpUrlAccessor@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CDpUrlAccessor>::CComObject<CDpUrlAccessor>(void *)
0x180004687  mov     rbx, rax
0x18000468a  jmp     short loc_18000468E
0x18000468c  xor     ebx, ebx
0x18000468e  mov     [rsp+48h+arg_18], rbx
0x180004693  jmp     short loc_1800046A8
0x180004695  mov     rsi, [rsp+48h+arg_10]
0x18000469a  mov     r14, [rsp+48h+arg_8]
0x18000469f  mov     edi, dword ptr [rsp+48h+arg_0]
0x1800046a3  mov     rbx, [rsp+48h+arg_18]
0x1800046a8  test    rbx, rbx
0x1800046ab  jz      loc_180004735
0x1800046b1  mov     r15d, 7FFFFFFFh
0x1800046b7  jmp     short loc_1800046C3
0x1800046b9  lea     ecx, [rax+1]
0x1800046bc  lock cmpxchg [rbx+8], ecx
0x1800046c1  jz      short loc_1800046CB
0x1800046c3  mov     eax, [rbx+8]
0x1800046c6  cmp     eax, r15d
0x1800046c9  jnz     short loc_1800046B9
0x1800046cb  lea     rcx, [rbx+10h]; this
0x1800046cf  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800046d4  mov     ecx, eax
0x1800046d6  test    eax, eax
0x1800046d8  js      short loc_1800046DE
0x1800046da  mov     byte ptr [rbx+38h], 1
0x1800046de  xor     eax, eax
0x1800046e0  test    ecx, ecx
0x1800046e2  cmovs   eax, ecx
0x1800046e5  xor     edi, edi
0x1800046e7  test    eax, eax
0x1800046e9  cmovs   edi, eax
0x1800046ec  jmp     short loc_1800046F8
0x1800046ee  lea     ecx, [rax-1]
0x1800046f1  lock cmpxchg [rbx+8], ecx
0x1800046f6  jz      short loc_180004700
0x1800046f8  mov     eax, [rbx+8]
0x1800046fb  cmp     eax, r15d
0x1800046fe  jnz     short loc_1800046EE
0x180004700  test    edi, edi
0x180004702  jnz     short loc_18000471E
0x180004704  mov     rax, [rbx]
0x180004707  mov     r8, rsi
0x18000470a  mov     rdx, r14
0x18000470d  mov     rcx, rbx
0x180004710  mov     rax, [rax]
0x180004713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004718  mov     edi, eax
0x18000471a  test    eax, eax
0x18000471c  jz      short loc_180004735
0x18000471e  mov     r8, [rbx]
0x180004721  mov     edx, 1
0x180004726  mov     rcx, rbx
0x180004729  mov     rax, [r8+98h]
0x180004730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004735  mov     eax, edi
0x180004737  add     rsp, 20h
0x18000473b  pop     r15
0x18000473d  pop     r14
0x18000473f  pop     rdi
0x180004740  pop     rsi
0x180004741  pop     rbx
0x180004742  retn
```
