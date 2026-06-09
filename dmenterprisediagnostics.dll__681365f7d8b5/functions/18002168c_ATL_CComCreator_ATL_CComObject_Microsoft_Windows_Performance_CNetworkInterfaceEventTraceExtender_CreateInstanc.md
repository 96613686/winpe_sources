# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002168c`
- end: `0x18002176f`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d530`

## callees

- `0x18000183c`
- `0x18002168c`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // r14d
  _DWORD *v6; // rdi

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  v6 = operator new(0x20u);
  v6[6] = 0;
  *((_QWORD *)v6 + 1) = 0;
  *((_QWORD *)v6 + 2) = 0;
  *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  if ( v6 )
  {
    v5 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))v6)(v6, &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33, a3);
    if ( v5 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v6 + 136LL))(v6, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x18002168c  mov     [rsp+arg_10], r8
0x180021691  mov     [rsp+arg_8], rdx
0x180021696  mov     [rsp+arg_0], rcx
0x18002169b  push    rsi
0x18002169c  push    rdi
0x18002169d  push    r14
0x18002169f  sub     rsp, 20h
0x1800216a3  mov     rsi, r8
0x1800216a6  test    r8, r8
0x1800216a9  jnz     short loc_1800216B5
0x1800216ab  mov     eax, 80004003h
0x1800216b0  jmp     loc_180021765
0x1800216b5  mov     qword ptr [r8], 0
0x1800216bc  mov     r14d, 8007000Eh
0x1800216c2  mov     dword ptr [rsp+38h+arg_8], r14d
0x1800216c7  mov     [rsp+38h+arg_0], 0
0x1800216d0  mov     ecx, 20h ; ' '; Size
0x1800216d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800216da  mov     rdi, rax
0x1800216dd  mov     dword ptr [rax+18h], 0
0x1800216e4  mov     qword ptr [rax+8], 0
0x1800216ec  mov     qword ptr [rax+10h], 0
0x1800216f4  lea     rax, ??_7?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable'
0x1800216fb  mov     [rdi], rax
0x1800216fe  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180021705  mov     rax, [rcx]
0x180021708  mov     rax, [rax+8]
0x18002170c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021711  mov     [rsp+38h+arg_0], rdi
0x180021716  jmp     short loc_180021727
0x180021718  mov     rsi, [rsp+38h+arg_10]
0x18002171d  mov     r14d, dword ptr [rsp+38h+arg_8]
0x180021722  mov     rdi, [rsp+38h+arg_0]
0x180021727  test    rdi, rdi
0x18002172a  jz      short loc_180021762
0x18002172c  mov     rax, [rdi]
0x18002172f  mov     r8, rsi
0x180021732  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180021739  mov     rcx, rdi
0x18002173c  mov     rax, [rax]
0x18002173f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021744  mov     r14d, eax
0x180021747  test    eax, eax
0x180021749  jz      short loc_180021762
0x18002174b  mov     rdx, [rdi]
0x18002174e  mov     rax, [rdx+88h]
0x180021755  mov     edx, 1
0x18002175a  mov     rcx, rdi
0x18002175d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021762  mov     eax, r14d
0x180021765  add     rsp, 20h
0x180021769  pop     r14
0x18002176b  pop     rdi
0x18002176c  pop     rsi
0x18002176d  retn
```
