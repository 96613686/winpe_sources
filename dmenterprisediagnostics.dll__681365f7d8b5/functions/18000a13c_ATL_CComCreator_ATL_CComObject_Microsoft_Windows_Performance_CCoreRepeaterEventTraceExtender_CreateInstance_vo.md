# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a13c`
- end: `0x18000a226`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d530`

## callees

- `0x18000183c`
- `0x18000a13c`
- `0x180027010`

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
0x18000a13c  mov     [rsp+arg_10], r8
0x18000a141  mov     [rsp+arg_8], rdx
0x18000a146  mov     [rsp+arg_0], rcx
0x18000a14b  push    rsi
0x18000a14c  push    rdi
0x18000a14d  push    r14
0x18000a14f  sub     rsp, 20h
0x18000a153  mov     rsi, r8
0x18000a156  test    r8, r8
0x18000a159  jnz     short loc_18000A165
0x18000a15b  mov     eax, 80004003h
0x18000a160  jmp     loc_18000A21C
0x18000a165  mov     qword ptr [r8], 0
0x18000a16c  mov     r14d, 8007000Eh
0x18000a172  mov     dword ptr [rsp+38h+arg_8], r14d
0x18000a177  mov     [rsp+38h+arg_0], 0
0x18000a180  mov     ecx, 28h ; '('; Size
0x18000a185  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a18a  mov     rdi, rax
0x18000a18d  mov     dword ptr [rax+18h], 0
0x18000a194  mov     qword ptr [rax+8], 0
0x18000a19c  mov     qword ptr [rax+10h], 0
0x18000a1a4  mov     dword ptr [rax+20h], 0
0x18000a1ab  lea     rax, ??_7?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable'
0x18000a1b2  mov     [rdi], rax
0x18000a1b5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a1bc  mov     rax, [rcx]
0x18000a1bf  mov     rax, [rax+8]
0x18000a1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1c8  mov     [rsp+38h+arg_0], rdi
0x18000a1cd  jmp     short loc_18000A1DE
0x18000a1cf  mov     rsi, [rsp+38h+arg_10]
0x18000a1d4  mov     r14d, dword ptr [rsp+38h+arg_8]
0x18000a1d9  mov     rdi, [rsp+38h+arg_0]
0x18000a1de  test    rdi, rdi
0x18000a1e1  jz      short loc_18000A219
0x18000a1e3  mov     rax, [rdi]
0x18000a1e6  mov     r8, rsi
0x18000a1e9  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18000a1f0  mov     rcx, rdi
0x18000a1f3  mov     rax, [rax]
0x18000a1f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1fb  mov     r14d, eax
0x18000a1fe  test    eax, eax
0x18000a200  jz      short loc_18000A219
0x18000a202  mov     rdx, [rdi]
0x18000a205  mov     rax, [rdx+88h]
0x18000a20c  mov     edx, 1
0x18000a211  mov     rcx, rdi
0x18000a214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a219  mov     eax, r14d
0x18000a21c  add     rsp, 20h
0x18000a220  pop     r14
0x18000a222  pop     rdi
0x18000a223  pop     rsi
0x18000a224  retn
```
