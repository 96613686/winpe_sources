# ATL::CComCreator<ATL::CComObject<CL2TPDiagHelper>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000aafc`
- end: `0x18000ac18`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCL2TPDiagHelper@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `284`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000aad0`

## callees

- `0x1800011dc`
- `0x18000447c`
- `0x18000a918`
- `0x18000aafc`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CL2TPDiagHelper>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  void *v7; // rax
  __int64 v8; // rbx
  signed __int32 v9; // eax
  int v10; // ecx
  int v11; // eax
  signed __int32 v12; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = operator new(0x598u);
  if ( v7 )
    v8 = ATL::CComObject<CL2TPDiagHelper>::CComObject<CL2TPDiagHelper>((__int64)v7);
  else
    v8 = 0;
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
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 168LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000aafc  mov     [rsp+arg_10], r8
0x18000ab01  mov     [rsp+arg_8], rdx
0x18000ab06  mov     [rsp+arg_0], rcx
0x18000ab0b  push    rbx
0x18000ab0c  push    rsi
0x18000ab0d  push    rdi
0x18000ab0e  push    r14
0x18000ab10  push    r15
0x18000ab12  sub     rsp, 20h
0x18000ab16  mov     rsi, r8
0x18000ab19  mov     r14, rdx
0x18000ab1c  test    r8, r8
0x18000ab1f  jnz     short loc_18000AB2B
0x18000ab21  mov     eax, 80004003h
0x18000ab26  jmp     loc_18000AC0B
0x18000ab2b  mov     qword ptr [r8], 0
0x18000ab32  mov     edi, 8007000Eh
0x18000ab37  mov     dword ptr [rsp+48h+arg_0], edi
0x18000ab3b  mov     [rsp+48h+arg_18], 0
0x18000ab44  mov     ecx, 598h; Size
0x18000ab49  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ab4e  test    rax, rax
0x18000ab51  jz      short loc_18000AB60
0x18000ab53  mov     rcx, rax
0x18000ab56  call    ??0?$CComObject@VCL2TPDiagHelper@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CL2TPDiagHelper>::CComObject<CL2TPDiagHelper>(void *)
0x18000ab5b  mov     rbx, rax
0x18000ab5e  jmp     short loc_18000AB62
0x18000ab60  xor     ebx, ebx
0x18000ab62  mov     [rsp+48h+arg_18], rbx
0x18000ab67  jmp     short loc_18000AB7C
0x18000ab69  mov     rsi, [rsp+48h+arg_10]
0x18000ab6e  mov     r14, [rsp+48h+arg_8]
0x18000ab73  mov     edi, dword ptr [rsp+48h+arg_0]
0x18000ab77  mov     rbx, [rsp+48h+arg_18]
0x18000ab7c  test    rbx, rbx
0x18000ab7f  jz      loc_18000AC09
0x18000ab85  mov     r15d, 7FFFFFFFh
0x18000ab8b  jmp     short loc_18000AB97
0x18000ab8d  lea     ecx, [rax+1]
0x18000ab90  lock cmpxchg [rbx+38h], ecx
0x18000ab95  jz      short loc_18000AB9F
0x18000ab97  mov     eax, [rbx+38h]
0x18000ab9a  cmp     eax, r15d
0x18000ab9d  jnz     short loc_18000AB8D
0x18000ab9f  lea     rcx, [rbx+40h]; this
0x18000aba3  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000aba8  mov     ecx, eax
0x18000abaa  test    eax, eax
0x18000abac  js      short loc_18000ABB2
0x18000abae  mov     byte ptr [rbx+68h], 1
0x18000abb2  xor     eax, eax
0x18000abb4  test    ecx, ecx
0x18000abb6  cmovs   eax, ecx
0x18000abb9  xor     edi, edi
0x18000abbb  test    eax, eax
0x18000abbd  cmovs   edi, eax
0x18000abc0  jmp     short loc_18000ABCC
0x18000abc2  lea     ecx, [rax-1]
0x18000abc5  lock cmpxchg [rbx+38h], ecx
0x18000abca  jz      short loc_18000ABD4
0x18000abcc  mov     eax, [rbx+38h]
0x18000abcf  cmp     eax, r15d
0x18000abd2  jnz     short loc_18000ABC2
0x18000abd4  test    edi, edi
0x18000abd6  jnz     short loc_18000ABF2
0x18000abd8  mov     rax, [rbx]
0x18000abdb  mov     r8, rsi
0x18000abde  mov     rdx, r14
0x18000abe1  mov     rcx, rbx
0x18000abe4  mov     rax, [rax]
0x18000abe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abec  mov     edi, eax
0x18000abee  test    eax, eax
0x18000abf0  jz      short loc_18000AC09
0x18000abf2  mov     r8, [rbx]
0x18000abf5  mov     edx, 1
0x18000abfa  mov     rcx, rbx
0x18000abfd  mov     rax, [r8+0A8h]
0x18000ac04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac09  mov     eax, edi
0x18000ac0b  add     rsp, 20h
0x18000ac0f  pop     r15
0x18000ac11  pop     r14
0x18000ac13  pop     rdi
0x18000ac14  pop     rsi
0x18000ac15  pop     rbx
0x18000ac16  retn
```
