# ATL::CComCreator<ATL::CComObject<CEnhancedStorageAct>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009b78`
- end: `0x180009c66`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEnhancedStorageAct@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009ac0`

## callees

- `0x180001264`
- `0x180002d44`
- `0x180003894`
- `0x1800038bc`
- `0x180003d3c`
- `0x180009b78`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CEnhancedStorageAct>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  void *v7; // rax
  volatile int *v8; // rdi
  int v9; // eax
  int v10; // ecx
  volatile int *v13; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x280u);
    if ( v7 )
      v8 = (volatile int *)ATL::CComObject<CEnhancedStorageAct>::CComObject<CEnhancedStorageAct>(v7);
    else
      v8 = 0;
    v13 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v13;
  }
  if ( v8 )
  {
    ATL::SafeIncrementReferenceMultiThread(v8 + 2);
    v9 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v8 + 4));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    ATL::SafeDecrementReferenceMultiThread(v8 + 2);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(volatile int *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v8 + 112LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180009b78  mov     [rsp+arg_10], r8
0x180009b7d  mov     [rsp+arg_8], rdx
0x180009b82  mov     [rsp+arg_0], rcx
0x180009b87  push    rbx
0x180009b88  push    rsi
0x180009b89  push    rdi
0x180009b8a  push    r14
0x180009b8c  push    r15
0x180009b8e  sub     rsp, 20h
0x180009b92  mov     r14, r8
0x180009b95  mov     r15, rdx
0x180009b98  test    r8, r8
0x180009b9b  jnz     short loc_180009BA7
0x180009b9d  mov     eax, 80004003h
0x180009ba2  jmp     loc_180009C5A
0x180009ba7  mov     qword ptr [r8], 0
0x180009bae  mov     esi, 8007000Eh
0x180009bb3  mov     dword ptr [rsp+48h+arg_0], esi
0x180009bb7  mov     [rsp+48h+arg_18], 0
0x180009bc0  mov     ecx, 280h; Size
0x180009bc5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009bca  test    rax, rax
0x180009bcd  jz      short loc_180009BDC
0x180009bcf  mov     rcx, rax
0x180009bd2  call    ??0?$CComObject@VCEnhancedStorageAct@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CEnhancedStorageAct>::CComObject<CEnhancedStorageAct>(void *)
0x180009bd7  mov     rdi, rax
0x180009bda  jmp     short loc_180009BDE
0x180009bdc  xor     edi, edi
0x180009bde  mov     [rsp+48h+arg_18], rdi
0x180009be3  jmp     short loc_180009BF8
0x180009be5  mov     r14, [rsp+48h+arg_10]
0x180009bea  mov     r15, [rsp+48h+arg_8]
0x180009bef  mov     esi, dword ptr [rsp+48h+arg_0]
0x180009bf3  mov     rdi, [rsp+48h+arg_18]
0x180009bf8  test    rdi, rdi
0x180009bfb  jz      short loc_180009C58
0x180009bfd  lea     rcx, [rdi+8]; volatile int *
0x180009c01  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180009c06  lea     rcx, [rdi+10h]; this
0x180009c0a  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180009c0f  xor     ecx, ecx
0x180009c11  test    eax, eax
0x180009c13  cmovs   ecx, eax
0x180009c16  xor     esi, esi
0x180009c18  test    ecx, ecx
0x180009c1a  cmovs   esi, ecx
0x180009c1d  lea     rcx, [rdi+8]; volatile int *
0x180009c21  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180009c26  test    esi, esi
0x180009c28  jnz     short loc_180009C44
0x180009c2a  mov     rax, [rdi]
0x180009c2d  mov     r8, r14
0x180009c30  mov     rdx, r15
0x180009c33  mov     rcx, rdi
0x180009c36  mov     rax, [rax]
0x180009c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c3e  mov     esi, eax
0x180009c40  test    eax, eax
0x180009c42  jz      short loc_180009C58
0x180009c44  mov     rdx, [rdi]
0x180009c47  mov     rax, [rdx+70h]
0x180009c4b  mov     edx, 1
0x180009c50  mov     rcx, rdi
0x180009c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c58  mov     eax, esi
0x180009c5a  add     rsp, 20h
0x180009c5e  pop     r15
0x180009c60  pop     r14
0x180009c62  pop     rdi
0x180009c63  pop     rsi
0x180009c64  pop     rbx
0x180009c65  retn
```
