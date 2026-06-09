# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180020e0c`
- end: `0x180020edf`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d530`

## callees

- `0x18000183c`
- `0x180020be0`
- `0x180020e0c`
- `0x180027010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CWinSATEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CWinSATEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CWinSATEventTraceExtender *)operator new(0x68u);
    Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CWinSATEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CWinSATEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x180020e0c  mov     [rsp+arg_10], r8
0x180020e11  mov     [rsp+arg_8], rdx
0x180020e16  mov     [rsp+arg_0], rcx
0x180020e1b  push    rbx
0x180020e1c  push    rsi
0x180020e1d  push    rdi
0x180020e1e  sub     rsp, 20h
0x180020e22  mov     rdi, r8
0x180020e25  test    r8, r8
0x180020e28  jnz     short loc_180020E34
0x180020e2a  mov     eax, 80004003h
0x180020e2f  jmp     loc_180020ED6
0x180020e34  mov     qword ptr [r8], 0
0x180020e3b  mov     esi, 8007000Eh
0x180020e40  mov     dword ptr [rsp+38h+arg_8], esi
0x180020e44  mov     [rsp+38h+arg_0], 0
0x180020e4d  mov     ecx, 68h ; 'h'; Size
0x180020e52  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020e57  mov     rbx, rax
0x180020e5a  mov     [rsp+38h+arg_18], rax
0x180020e5f  mov     rcx, rax; this
0x180020e62  call    ??0CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(void)
0x180020e67  lea     rax, ??_7?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable'
0x180020e6e  mov     [rbx], rax
0x180020e71  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180020e78  mov     rax, [rcx]
0x180020e7b  mov     rax, [rax+8]
0x180020e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e84  nop
0x180020e85  mov     [rsp+38h+arg_0], rbx
0x180020e8a  jmp     short loc_180020E9A
0x180020e8c  mov     rdi, [rsp+38h+arg_10]
0x180020e91  mov     esi, dword ptr [rsp+38h+arg_8]
0x180020e95  mov     rbx, [rsp+38h+arg_0]
0x180020e9a  test    rbx, rbx
0x180020e9d  jz      short loc_180020ED4
0x180020e9f  mov     rax, [rbx]
0x180020ea2  mov     r8, rdi
0x180020ea5  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180020eac  mov     rcx, rbx
0x180020eaf  mov     rax, [rax]
0x180020eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020eb7  mov     esi, eax
0x180020eb9  test    eax, eax
0x180020ebb  jz      short loc_180020ED4
0x180020ebd  mov     rdx, [rbx]
0x180020ec0  mov     rax, [rdx+88h]
0x180020ec7  mov     edx, 1
0x180020ecc  mov     rcx, rbx
0x180020ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ed4  mov     eax, esi
0x180020ed6  add     rsp, 20h
0x180020eda  pop     rdi
0x180020edb  pop     rsi
0x180020edc  pop     rbx
0x180020edd  retn
```
