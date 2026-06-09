# ATL::CComCreator<ATL::CComObject<CPPTPDiagHelper>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009b6c`
- end: `0x180009c88`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPPTPDiagHelper@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `284`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009b40`

## callees

- `0x1800011dc`
- `0x18000447c`
- `0x180009924`
- `0x180009b6c`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CPPTPDiagHelper>>::CreateInstance(
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
    v8 = ATL::CComObject<CPPTPDiagHelper>::CComObject<CPPTPDiagHelper>((__int64)v7);
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
0x180009b6c  mov     [rsp+arg_10], r8
0x180009b71  mov     [rsp+arg_8], rdx
0x180009b76  mov     [rsp+arg_0], rcx
0x180009b7b  push    rbx
0x180009b7c  push    rsi
0x180009b7d  push    rdi
0x180009b7e  push    r14
0x180009b80  push    r15
0x180009b82  sub     rsp, 20h
0x180009b86  mov     rsi, r8
0x180009b89  mov     r14, rdx
0x180009b8c  test    r8, r8
0x180009b8f  jnz     short loc_180009B9B
0x180009b91  mov     eax, 80004003h
0x180009b96  jmp     loc_180009C7B
0x180009b9b  mov     qword ptr [r8], 0
0x180009ba2  mov     edi, 8007000Eh
0x180009ba7  mov     dword ptr [rsp+48h+arg_0], edi
0x180009bab  mov     [rsp+48h+arg_18], 0
0x180009bb4  mov     ecx, 598h; Size
0x180009bb9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009bbe  test    rax, rax
0x180009bc1  jz      short loc_180009BD0
0x180009bc3  mov     rcx, rax
0x180009bc6  call    ??0?$CComObject@VCPPTPDiagHelper@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CPPTPDiagHelper>::CComObject<CPPTPDiagHelper>(void *)
0x180009bcb  mov     rbx, rax
0x180009bce  jmp     short loc_180009BD2
0x180009bd0  xor     ebx, ebx
0x180009bd2  mov     [rsp+48h+arg_18], rbx
0x180009bd7  jmp     short loc_180009BEC
0x180009bd9  mov     rsi, [rsp+48h+arg_10]
0x180009bde  mov     r14, [rsp+48h+arg_8]
0x180009be3  mov     edi, dword ptr [rsp+48h+arg_0]
0x180009be7  mov     rbx, [rsp+48h+arg_18]
0x180009bec  test    rbx, rbx
0x180009bef  jz      loc_180009C79
0x180009bf5  mov     r15d, 7FFFFFFFh
0x180009bfb  jmp     short loc_180009C07
0x180009bfd  lea     ecx, [rax+1]
0x180009c00  lock cmpxchg [rbx+38h], ecx
0x180009c05  jz      short loc_180009C0F
0x180009c07  mov     eax, [rbx+38h]
0x180009c0a  cmp     eax, r15d
0x180009c0d  jnz     short loc_180009BFD
0x180009c0f  lea     rcx, [rbx+40h]; this
0x180009c13  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180009c18  mov     ecx, eax
0x180009c1a  test    eax, eax
0x180009c1c  js      short loc_180009C22
0x180009c1e  mov     byte ptr [rbx+68h], 1
0x180009c22  xor     eax, eax
0x180009c24  test    ecx, ecx
0x180009c26  cmovs   eax, ecx
0x180009c29  xor     edi, edi
0x180009c2b  test    eax, eax
0x180009c2d  cmovs   edi, eax
0x180009c30  jmp     short loc_180009C3C
0x180009c32  lea     ecx, [rax-1]
0x180009c35  lock cmpxchg [rbx+38h], ecx
0x180009c3a  jz      short loc_180009C44
0x180009c3c  mov     eax, [rbx+38h]
0x180009c3f  cmp     eax, r15d
0x180009c42  jnz     short loc_180009C32
0x180009c44  test    edi, edi
0x180009c46  jnz     short loc_180009C62
0x180009c48  mov     rax, [rbx]
0x180009c4b  mov     r8, rsi
0x180009c4e  mov     rdx, r14
0x180009c51  mov     rcx, rbx
0x180009c54  mov     rax, [rax]
0x180009c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c5c  mov     edi, eax
0x180009c5e  test    eax, eax
0x180009c60  jz      short loc_180009C79
0x180009c62  mov     r8, [rbx]
0x180009c65  mov     edx, 1
0x180009c6a  mov     rcx, rbx
0x180009c6d  mov     rax, [r8+0A8h]
0x180009c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c79  mov     eax, edi
0x180009c7b  add     rsp, 20h
0x180009c7f  pop     r15
0x180009c81  pop     r14
0x180009c83  pop     rdi
0x180009c84  pop     rsi
0x180009c85  pop     rbx
0x180009c86  retn
```
