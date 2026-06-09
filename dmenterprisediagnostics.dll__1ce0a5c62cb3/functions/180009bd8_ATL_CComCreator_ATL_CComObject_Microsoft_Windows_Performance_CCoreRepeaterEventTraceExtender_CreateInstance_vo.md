# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009bd8`
- end: `0x180009cc1`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `233`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cedc`

## callees

- `0x18000181c`
- `0x180009bd8`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  _DWORD *v5; // rdi
  unsigned int v6; // r14d
  _DWORD *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = operator new(0x28u);
    v5[6] = 0;
    *((_QWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 2) = 0;
    v5[8] = 0;
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v7 = v5;
  }
  catch ( ... )
  {
    v3 = a3;
    v6 = -2147024882;
    v5 = v7;
  }
  if ( v5 )
  {
    v6 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))v5)(v5, &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33, v3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v5 + 136LL))(v5, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180009bd8  mov     [rsp+arg_10], r8
0x180009bdd  mov     [rsp+arg_8], rdx
0x180009be2  mov     [rsp+arg_0], rcx
0x180009be7  push    rsi
0x180009be8  push    rdi
0x180009be9  push    r14
0x180009beb  sub     rsp, 20h
0x180009bef  mov     rsi, r8
0x180009bf2  test    r8, r8
0x180009bf5  jnz     short loc_180009C01
0x180009bf7  mov     eax, 80004003h
0x180009bfc  jmp     loc_180009CB8
0x180009c01  mov     qword ptr [r8], 0
0x180009c08  mov     r14d, 8007000Eh
0x180009c0e  mov     dword ptr [rsp+38h+arg_8], r14d
0x180009c13  mov     [rsp+38h+arg_0], 0
0x180009c1c  mov     ecx, 28h ; '('; Size
0x180009c21  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009c26  mov     rdi, rax
0x180009c29  mov     dword ptr [rax+18h], 0
0x180009c30  mov     qword ptr [rax+8], 0
0x180009c38  mov     qword ptr [rax+10h], 0
0x180009c40  mov     dword ptr [rax+20h], 0
0x180009c47  lea     rax, ??_7?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable'
0x180009c4e  mov     [rdi], rax
0x180009c51  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009c58  mov     rax, [rcx]
0x180009c5b  mov     rax, [rax+8]
0x180009c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c64  mov     [rsp+38h+arg_0], rdi
0x180009c69  jmp     short loc_180009C7A
0x180009c6b  mov     rsi, [rsp+38h+arg_10]
0x180009c70  mov     r14d, dword ptr [rsp+38h+arg_8]
0x180009c75  mov     rdi, [rsp+38h+arg_0]
0x180009c7a  test    rdi, rdi
0x180009c7d  jz      short loc_180009CB5
0x180009c7f  mov     rax, [rdi]
0x180009c82  mov     r8, rsi
0x180009c85  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180009c8c  mov     rcx, rdi
0x180009c8f  mov     rax, [rax]
0x180009c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c97  mov     r14d, eax
0x180009c9a  test    eax, eax
0x180009c9c  jz      short loc_180009CB5
0x180009c9e  mov     rdx, [rdi]
0x180009ca1  mov     rax, [rdx+88h]
0x180009ca8  mov     edx, 1
0x180009cad  mov     rcx, rdi
0x180009cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cb5  mov     eax, r14d
0x180009cb8  add     rsp, 20h
0x180009cbc  pop     r14
0x180009cbe  pop     rdi
0x180009cbf  pop     rsi
0x180009cc0  retn
```
