# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000a22c`
- end: `0x18000a2f5`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d67c`

## callees

- `0x18000183c`
- `0x18000a22c`
- `0x180027010`

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
0x18000a22c  mov     [rsp+arg_10], r8
0x18000a231  mov     [rsp+arg_8], rdx
0x18000a236  mov     [rsp+arg_0], rcx
0x18000a23b  push    rbx
0x18000a23c  push    rsi
0x18000a23d  push    rdi
0x18000a23e  sub     rsp, 20h
0x18000a242  mov     rdi, r8
0x18000a245  test    r8, r8
0x18000a248  jnz     short loc_18000A254
0x18000a24a  mov     eax, 80004003h
0x18000a24f  jmp     loc_18000A2EC
0x18000a254  mov     qword ptr [r8], 0
0x18000a25b  mov     esi, 8007000Eh
0x18000a260  mov     dword ptr [rsp+38h+arg_8], esi
0x18000a264  mov     [rsp+38h+arg_0], 0
0x18000a26d  mov     ecx, 10h; Size
0x18000a272  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a277  mov     rbx, rax
0x18000a27a  mov     dword ptr [rax+8], 0
0x18000a281  lea     rax, ??_7?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable'
0x18000a288  mov     [rbx], rax
0x18000a28b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a292  mov     rax, [rcx]
0x18000a295  mov     rax, [rax+8]
0x18000a299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a29e  mov     [rsp+38h+arg_0], rbx
0x18000a2a3  jmp     short loc_18000A2B3
0x18000a2a5  mov     rdi, [rsp+38h+arg_10]
0x18000a2aa  mov     esi, dword ptr [rsp+38h+arg_8]
0x18000a2ae  mov     rbx, [rsp+38h+arg_0]
0x18000a2b3  test    rbx, rbx
0x18000a2b6  jz      short loc_18000A2EA
0x18000a2b8  mov     rax, [rbx]
0x18000a2bb  mov     r8, rdi
0x18000a2be  lea     rdx, _GUID_ad66cb4b_7487_4f77_84cf_cc94f549eb5e
0x18000a2c5  mov     rcx, rbx
0x18000a2c8  mov     rax, [rax]
0x18000a2cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2d0  mov     esi, eax
0x18000a2d2  test    eax, eax
0x18000a2d4  jz      short loc_18000A2EA
0x18000a2d6  mov     rdx, [rbx]
0x18000a2d9  mov     rax, [rdx+20h]
0x18000a2dd  mov     edx, 1
0x18000a2e2  mov     rcx, rbx
0x18000a2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2ea  mov     eax, esi
0x18000a2ec  add     rsp, 20h
0x18000a2f0  pop     rdi
0x18000a2f1  pop     rsi
0x18000a2f2  pop     rbx
0x18000a2f3  retn
```
