# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009cc8`
- end: `0x180009d90`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d024`

## callees

- `0x18000181c`
- `0x180009cc8`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  _DWORD *v5; // rbx
  unsigned int v6; // esi
  _DWORD *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = operator new(0x10u);
    v5[2] = 0;
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_ad66cb4b_7487_4f77_84cf_cc94f549eb5e,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v5 + 32LL))(v5, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180009cc8  mov     [rsp+arg_10], r8
0x180009ccd  mov     [rsp+arg_8], rdx
0x180009cd2  mov     [rsp+arg_0], rcx
0x180009cd7  push    rbx
0x180009cd8  push    rsi
0x180009cd9  push    rdi
0x180009cda  sub     rsp, 20h
0x180009cde  mov     rdi, r8
0x180009ce1  test    r8, r8
0x180009ce4  jnz     short loc_180009CF0
0x180009ce6  mov     eax, 80004003h
0x180009ceb  jmp     loc_180009D88
0x180009cf0  mov     qword ptr [r8], 0
0x180009cf7  mov     esi, 8007000Eh
0x180009cfc  mov     dword ptr [rsp+38h+arg_8], esi
0x180009d00  mov     [rsp+38h+arg_0], 0
0x180009d09  mov     ecx, 10h; Size
0x180009d0e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009d13  mov     rbx, rax
0x180009d16  mov     dword ptr [rax+8], 0
0x180009d1d  lea     rax, ??_7?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable'
0x180009d24  mov     [rbx], rax
0x180009d27  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009d2e  mov     rax, [rcx]
0x180009d31  mov     rax, [rax+8]
0x180009d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d3a  mov     [rsp+38h+arg_0], rbx
0x180009d3f  jmp     short loc_180009D4F
0x180009d41  mov     rdi, [rsp+38h+arg_10]
0x180009d46  mov     esi, dword ptr [rsp+38h+arg_8]
0x180009d4a  mov     rbx, [rsp+38h+arg_0]
0x180009d4f  test    rbx, rbx
0x180009d52  jz      short loc_180009D86
0x180009d54  mov     rax, [rbx]
0x180009d57  mov     r8, rdi
0x180009d5a  lea     rdx, _GUID_ad66cb4b_7487_4f77_84cf_cc94f549eb5e
0x180009d61  mov     rcx, rbx
0x180009d64  mov     rax, [rax]
0x180009d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d6c  mov     esi, eax
0x180009d6e  test    eax, eax
0x180009d70  jz      short loc_180009D86
0x180009d72  mov     rdx, [rbx]
0x180009d75  mov     rax, [rdx+20h]
0x180009d79  mov     edx, 1
0x180009d7e  mov     rcx, rbx
0x180009d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d86  mov     eax, esi
0x180009d88  add     rsp, 20h
0x180009d8c  pop     rdi
0x180009d8d  pop     rsi
0x180009d8e  pop     rbx
0x180009d8f  retn
```
