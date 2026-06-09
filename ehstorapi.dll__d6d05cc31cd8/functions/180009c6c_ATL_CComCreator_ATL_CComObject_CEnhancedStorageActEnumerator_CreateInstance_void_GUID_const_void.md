# ATL::CComCreator<ATL::CComObject<CEnhancedStorageActEnumerator>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009c6c`
- end: `0x180009d88`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEnhancedStorageActEnumerator@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009af0`

## callees

- `0x180001264`
- `0x180002d44`
- `0x180003894`
- `0x1800038bc`
- `0x1800042f4`
- `0x180009c6c`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CEnhancedStorageActEnumerator>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  unsigned int v6; // edi
  volatile int *v7; // rax
  volatile int *v8; // rbx
  int v9; // eax
  CEnhancedStorageActEnumerator *v10; // rcx
  volatile int *v13; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (volatile int *)operator new(0x40u);
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 2) = 0;
      *((_OWORD *)v7 + 1) = 0;
      *((_OWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 6) = 0;
      *((_BYTE *)v7 + 56) = 0;
      *(_QWORD *)v7 = &ATL::CComObject<CEnhancedStorageActEnumerator>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
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
    if ( v9 >= 0 )
      v9 = CEnhancedStorageActEnumerator::FinalConstruct(v10);
    v6 = 0;
    if ( v9 < 0 )
      v6 = v9;
    ATL::SafeDecrementReferenceMultiThread(v8 + 2);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(volatile int *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180009c6c  mov     [rsp+arg_10], r8
0x180009c71  mov     [rsp+arg_8], rdx
0x180009c76  mov     [rsp+arg_0], rcx
0x180009c7b  push    rbx
0x180009c7c  push    rsi
0x180009c7d  push    rdi
0x180009c7e  push    r14
0x180009c80  push    r15
0x180009c82  sub     rsp, 20h
0x180009c86  mov     rsi, r8
0x180009c89  mov     r15, rdx
0x180009c8c  test    r8, r8
0x180009c8f  jnz     short loc_180009C9B
0x180009c91  mov     eax, 80004003h
0x180009c96  jmp     loc_180009D7C
0x180009c9b  mov     qword ptr [r8], 0
0x180009ca2  mov     edi, 8007000Eh
0x180009ca7  mov     dword ptr [rsp+48h+arg_0], edi
0x180009cab  mov     [rsp+48h+arg_18], 0
0x180009cb4  mov     ecx, 40h ; '@'; Size
0x180009cb9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009cbe  mov     rbx, rax
0x180009cc1  test    rbx, rbx
0x180009cc4  jz      short loc_180009CFE
0x180009cc6  mov     dword ptr [rax+8], 0
0x180009ccd  xorps   xmm0, xmm0
0x180009cd0  xor     eax, eax
0x180009cd2  movups  xmmword ptr [rbx+10h], xmm0
0x180009cd6  movups  xmmword ptr [rbx+20h], xmm0
0x180009cda  mov     [rbx+30h], rax
0x180009cde  mov     [rbx+38h], al
0x180009ce1  lea     rax, ??_7?$CComObject@VCEnhancedStorageActEnumerator@@@ATL@@6B@; const ATL::CComObject<CEnhancedStorageActEnumerator>::`vftable'
0x180009ce8  mov     [rbx], rax
0x180009ceb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009cf2  mov     rax, [rcx]
0x180009cf5  mov     rax, [rax+8]
0x180009cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cfe  mov     [rsp+48h+arg_18], rbx
0x180009d03  jmp     short loc_180009D18
0x180009d05  mov     rsi, [rsp+48h+arg_10]
0x180009d0a  mov     r15, [rsp+48h+arg_8]
0x180009d0f  mov     edi, dword ptr [rsp+48h+arg_0]
0x180009d13  mov     rbx, [rsp+48h+arg_18]
0x180009d18  test    rbx, rbx
0x180009d1b  jz      short loc_180009D7A
0x180009d1d  lea     rcx, [rbx+8]; volatile int *
0x180009d21  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180009d26  lea     rcx, [rbx+10h]; this
0x180009d2a  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180009d2f  test    eax, eax
0x180009d31  js      short loc_180009D38
0x180009d33  call    ?FinalConstruct@CEnhancedStorageActEnumerator@@QEAAJXZ; CEnhancedStorageActEnumerator::FinalConstruct(void)
0x180009d38  xor     edi, edi
0x180009d3a  test    eax, eax
0x180009d3c  cmovs   edi, eax
0x180009d3f  lea     rcx, [rbx+8]; volatile int *
0x180009d43  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180009d48  test    edi, edi
0x180009d4a  jnz     short loc_180009D66
0x180009d4c  mov     rax, [rbx]
0x180009d4f  mov     r8, rsi
0x180009d52  mov     rdx, r15
0x180009d55  mov     rcx, rbx
0x180009d58  mov     rax, [rax]
0x180009d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d60  mov     edi, eax
0x180009d62  test    eax, eax
0x180009d64  jz      short loc_180009D7A
0x180009d66  mov     rdx, [rbx]
0x180009d69  mov     rax, [rdx+28h]
0x180009d6d  mov     edx, 1
0x180009d72  mov     rcx, rbx
0x180009d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d7a  mov     eax, edi
0x180009d7c  add     rsp, 20h
0x180009d80  pop     r15
0x180009d82  pop     r14
0x180009d84  pop     rdi
0x180009d85  pop     rsi
0x180009d86  pop     rbx
0x180009d87  retn
```
