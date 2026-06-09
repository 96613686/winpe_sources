# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180019d4c`
- end: `0x180019e1f`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d530`

## callees

- `0x18000183c`
- `0x180018eb4`
- `0x180019d4c`
- `0x180027010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CNGenEventTraceExtender *)operator new(0xB8u);
    Microsoft::Windows::Performance::CNGenEventTraceExtender::CNGenEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CNGenEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CNGenEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x180019d4c  mov     [rsp+arg_10], r8
0x180019d51  mov     [rsp+arg_8], rdx
0x180019d56  mov     [rsp+arg_0], rcx
0x180019d5b  push    rbx
0x180019d5c  push    rsi
0x180019d5d  push    rdi
0x180019d5e  sub     rsp, 20h
0x180019d62  mov     rdi, r8
0x180019d65  test    r8, r8
0x180019d68  jnz     short loc_180019D74
0x180019d6a  mov     eax, 80004003h
0x180019d6f  jmp     loc_180019E16
0x180019d74  mov     qword ptr [r8], 0
0x180019d7b  mov     esi, 8007000Eh
0x180019d80  mov     dword ptr [rsp+38h+arg_8], esi
0x180019d84  mov     [rsp+38h+arg_0], 0
0x180019d8d  mov     ecx, 0B8h; Size
0x180019d92  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019d97  mov     rbx, rax
0x180019d9a  mov     [rsp+38h+arg_18], rax
0x180019d9f  mov     rcx, rax; this
0x180019da2  call    ??0CNGenEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CNGenEventTraceExtender::CNGenEventTraceExtender(void)
0x180019da7  lea     rax, ??_7?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable'
0x180019dae  mov     [rbx], rax
0x180019db1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180019db8  mov     rax, [rcx]
0x180019dbb  mov     rax, [rax+8]
0x180019dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dc4  nop
0x180019dc5  mov     [rsp+38h+arg_0], rbx
0x180019dca  jmp     short loc_180019DDA
0x180019dcc  mov     rdi, [rsp+38h+arg_10]
0x180019dd1  mov     esi, dword ptr [rsp+38h+arg_8]
0x180019dd5  mov     rbx, [rsp+38h+arg_0]
0x180019dda  test    rbx, rbx
0x180019ddd  jz      short loc_180019E14
0x180019ddf  mov     rax, [rbx]
0x180019de2  mov     r8, rdi
0x180019de5  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180019dec  mov     rcx, rbx
0x180019def  mov     rax, [rax]
0x180019df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019df7  mov     esi, eax
0x180019df9  test    eax, eax
0x180019dfb  jz      short loc_180019E14
0x180019dfd  mov     rdx, [rbx]
0x180019e00  mov     rax, [rdx+88h]
0x180019e07  mov     edx, 1
0x180019e0c  mov     rcx, rbx
0x180019e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e14  mov     eax, esi
0x180019e16  add     rsp, 20h
0x180019e1a  pop     rdi
0x180019e1b  pop     rsi
0x180019e1c  pop     rbx
0x180019e1d  retn
```
