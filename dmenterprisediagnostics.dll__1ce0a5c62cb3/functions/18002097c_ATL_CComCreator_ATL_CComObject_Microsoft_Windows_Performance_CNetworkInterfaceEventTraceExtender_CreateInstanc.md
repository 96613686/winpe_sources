# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002097c`
- end: `0x180020a5e`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cedc`

## callees

- `0x18000181c`
- `0x18002097c`
- `0x180026010`

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
0x18002097c  mov     [rsp+arg_10], r8
0x180020981  mov     [rsp+arg_8], rdx
0x180020986  mov     [rsp+arg_0], rcx
0x18002098b  push    rsi
0x18002098c  push    rdi
0x18002098d  push    r14
0x18002098f  sub     rsp, 20h
0x180020993  mov     rsi, r8
0x180020996  test    r8, r8
0x180020999  jnz     short loc_1800209A5
0x18002099b  mov     eax, 80004003h
0x1800209a0  jmp     loc_180020A55
0x1800209a5  mov     qword ptr [r8], 0
0x1800209ac  mov     r14d, 8007000Eh
0x1800209b2  mov     dword ptr [rsp+38h+arg_8], r14d
0x1800209b7  mov     [rsp+38h+arg_0], 0
0x1800209c0  mov     ecx, 20h ; ' '; Size
0x1800209c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800209ca  mov     rdi, rax
0x1800209cd  mov     dword ptr [rax+18h], 0
0x1800209d4  mov     qword ptr [rax+8], 0
0x1800209dc  mov     qword ptr [rax+10h], 0
0x1800209e4  lea     rax, ??_7?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable'
0x1800209eb  mov     [rdi], rax
0x1800209ee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800209f5  mov     rax, [rcx]
0x1800209f8  mov     rax, [rax+8]
0x1800209fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a01  mov     [rsp+38h+arg_0], rdi
0x180020a06  jmp     short loc_180020A17
0x180020a08  mov     rsi, [rsp+38h+arg_10]
0x180020a0d  mov     r14d, dword ptr [rsp+38h+arg_8]
0x180020a12  mov     rdi, [rsp+38h+arg_0]
0x180020a17  test    rdi, rdi
0x180020a1a  jz      short loc_180020A52
0x180020a1c  mov     rax, [rdi]
0x180020a1f  mov     r8, rsi
0x180020a22  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180020a29  mov     rcx, rdi
0x180020a2c  mov     rax, [rax]
0x180020a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a34  mov     r14d, eax
0x180020a37  test    eax, eax
0x180020a39  jz      short loc_180020A52
0x180020a3b  mov     rdx, [rdi]
0x180020a3e  mov     rax, [rdx+88h]
0x180020a45  mov     edx, 1
0x180020a4a  mov     rcx, rdi
0x180020a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a52  mov     eax, r14d
0x180020a55  add     rsp, 20h
0x180020a59  pop     r14
0x180020a5b  pop     rdi
0x180020a5c  pop     rsi
0x180020a5d  retn
```
