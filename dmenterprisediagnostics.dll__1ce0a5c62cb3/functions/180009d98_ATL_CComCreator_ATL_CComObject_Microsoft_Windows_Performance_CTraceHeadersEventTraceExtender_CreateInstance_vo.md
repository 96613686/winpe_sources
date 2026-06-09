# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009d98`
- end: `0x180009e7a`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cedc`

## callees

- `0x18000181c`
- `0x180009d98`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(
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
    v5 = operator new(0x20u);
    v5[6] = 0;
    *((_QWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 2) = 0;
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable';
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
0x180009d98  mov     [rsp+arg_10], r8
0x180009d9d  mov     [rsp+arg_8], rdx
0x180009da2  mov     [rsp+arg_0], rcx
0x180009da7  push    rsi
0x180009da8  push    rdi
0x180009da9  push    r14
0x180009dab  sub     rsp, 20h
0x180009daf  mov     rsi, r8
0x180009db2  test    r8, r8
0x180009db5  jnz     short loc_180009DC1
0x180009db7  mov     eax, 80004003h
0x180009dbc  jmp     loc_180009E71
0x180009dc1  mov     qword ptr [r8], 0
0x180009dc8  mov     r14d, 8007000Eh
0x180009dce  mov     dword ptr [rsp+38h+arg_8], r14d
0x180009dd3  mov     [rsp+38h+arg_0], 0
0x180009ddc  mov     ecx, 20h ; ' '; Size
0x180009de1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009de6  mov     rdi, rax
0x180009de9  mov     dword ptr [rax+18h], 0
0x180009df0  mov     qword ptr [rax+8], 0
0x180009df8  mov     qword ptr [rax+10h], 0
0x180009e00  lea     rax, ??_7?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable'
0x180009e07  mov     [rdi], rax
0x180009e0a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009e11  mov     rax, [rcx]
0x180009e14  mov     rax, [rax+8]
0x180009e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e1d  mov     [rsp+38h+arg_0], rdi
0x180009e22  jmp     short loc_180009E33
0x180009e24  mov     rsi, [rsp+38h+arg_10]
0x180009e29  mov     r14d, dword ptr [rsp+38h+arg_8]
0x180009e2e  mov     rdi, [rsp+38h+arg_0]
0x180009e33  test    rdi, rdi
0x180009e36  jz      short loc_180009E6E
0x180009e38  mov     rax, [rdi]
0x180009e3b  mov     r8, rsi
0x180009e3e  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180009e45  mov     rcx, rdi
0x180009e48  mov     rax, [rax]
0x180009e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e50  mov     r14d, eax
0x180009e53  test    eax, eax
0x180009e55  jz      short loc_180009E6E
0x180009e57  mov     rdx, [rdi]
0x180009e5a  mov     rax, [rdx+88h]
0x180009e61  mov     edx, 1
0x180009e66  mov     rcx, rdi
0x180009e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e6e  mov     eax, r14d
0x180009e71  add     rsp, 20h
0x180009e75  pop     r14
0x180009e77  pop     rdi
0x180009e78  pop     rsi
0x180009e79  retn
```
