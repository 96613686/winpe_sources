# ATL::CComCreator<ATL::CComObject<CRAHelperClass>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a0f8`
- end: `0x18000a218`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCRAHelperClass@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `288`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000a0d0`

## callees

- `0x180001394`
- `0x18000a0f8`
- `0x18000a970`
- `0x18000bb64`
- `0x18000bb8c`
- `0x18000c7f0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CRAHelperClass>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  CRAHelperClass *v7; // rax
  CRAHelperClass *v8; // rdi
  int v9; // eax
  int v10; // edx
  CRAHelperClass *v13; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CRAHelperClass *)operator new(0x158u);
    v8 = v7;
    if ( v7 )
    {
      CRAHelperClass::CRAHelperClass(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CRAHelperClass>::`vftable'{for `INetDiagHelper'};
      *((_QWORD *)v8 + 1) = &ATL::CComObject<CRAHelperClass>::`vftable'{for `INetDiagHelperInfo'};
      *((_QWORD *)v8 + 7) = &ATL::CComObject<CRAHelperClass>::`vftable';
      (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
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
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v8 + 16);
    v9 = ATL::CComSafeDeleteCriticalSection::Init((CRAHelperClass *)((char *)v8 + 72));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v8 + 16);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CRAHelperClass *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(CRAHelperClass *, __int64))(*(_QWORD *)v8 + 168LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000a0f8  mov     [rsp+arg_10], r8
0x18000a0fd  mov     [rsp+arg_8], rdx
0x18000a102  mov     [rsp+arg_0], rcx
0x18000a107  push    rbx
0x18000a108  push    rsi
0x18000a109  push    rdi
0x18000a10a  push    r14
0x18000a10c  push    r15
0x18000a10e  sub     rsp, 20h
0x18000a112  mov     r14, r8
0x18000a115  mov     r15, rdx
0x18000a118  test    r8, r8
0x18000a11b  jnz     short loc_18000A127
0x18000a11d  mov     eax, 80004003h
0x18000a122  jmp     loc_18000A20C
0x18000a127  mov     qword ptr [r8], 0
0x18000a12e  mov     esi, 8007000Eh
0x18000a133  mov     dword ptr [rsp+48h+arg_0], esi
0x18000a137  mov     [rsp+48h+arg_18], 0
0x18000a140  mov     ecx, 158h; Size
0x18000a145  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a14a  mov     rdi, rax
0x18000a14d  test    rdi, rdi
0x18000a150  jz      short loc_18000A18D
0x18000a152  mov     rcx, rax; this
0x18000a155  call    ??0CRAHelperClass@@QEAA@XZ; CRAHelperClass::CRAHelperClass(void)
0x18000a15a  lea     r9, ??_7?$CComObject@VCRAHelperClass@@@ATL@@6BINetDiagHelper@@@; const ATL::CComObject<CRAHelperClass>::`vftable'{for `INetDiagHelper'}
0x18000a161  mov     [rdi], r9
0x18000a164  lea     rax, ??_7?$CComObject@VCRAHelperClass@@@ATL@@6BINetDiagHelperInfo@@@; const ATL::CComObject<CRAHelperClass>::`vftable'{for `INetDiagHelperInfo'}
0x18000a16b  mov     [rdi+8], rax
0x18000a16f  lea     rax, ??_7?$CComObject@VCRAHelperClass@@@ATL@@6B@; const ATL::CComObject<CRAHelperClass>::`vftable'
0x18000a176  mov     [rdi+38h], rax
0x18000a17a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a181  mov     rax, [rcx]
0x18000a184  mov     rax, [rax+8]
0x18000a188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a18d  mov     [rsp+48h+arg_18], rdi
0x18000a192  jmp     short loc_18000A1A7
0x18000a194  mov     r14, [rsp+48h+arg_10]
0x18000a199  mov     r15, [rsp+48h+arg_8]
0x18000a19e  mov     esi, dword ptr [rsp+48h+arg_0]
0x18000a1a2  mov     rdi, [rsp+48h+arg_18]
0x18000a1a7  test    rdi, rdi
0x18000a1aa  jz      short loc_18000A20A
0x18000a1ac  lea     rcx, [rdi+40h]; volatile int *
0x18000a1b0  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18000a1b5  lea     rcx, [rdi+48h]; this
0x18000a1b9  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000a1be  xor     edx, edx
0x18000a1c0  test    eax, eax
0x18000a1c2  cmovs   edx, eax
0x18000a1c5  xor     esi, esi
0x18000a1c7  test    edx, edx
0x18000a1c9  cmovs   esi, edx
0x18000a1cc  lea     rcx, [rdi+40h]; volatile int *
0x18000a1d0  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000a1d5  test    esi, esi
0x18000a1d7  jnz     short loc_18000A1F3
0x18000a1d9  mov     rax, [rdi]
0x18000a1dc  mov     r8, r14
0x18000a1df  mov     rdx, r15
0x18000a1e2  mov     rcx, rdi
0x18000a1e5  mov     rax, [rax]
0x18000a1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1ed  mov     esi, eax
0x18000a1ef  test    eax, eax
0x18000a1f1  jz      short loc_18000A20A
0x18000a1f3  mov     rdx, [rdi]
0x18000a1f6  mov     rax, [rdx+0A8h]
0x18000a1fd  mov     edx, 1
0x18000a202  mov     rcx, rdi
0x18000a205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a20a  mov     eax, esi
0x18000a20c  add     rsp, 20h
0x18000a210  pop     r15
0x18000a212  pop     r14
0x18000a214  pop     rdi
0x18000a215  pop     rsi
0x18000a216  pop     rbx
0x18000a217  retn
```
