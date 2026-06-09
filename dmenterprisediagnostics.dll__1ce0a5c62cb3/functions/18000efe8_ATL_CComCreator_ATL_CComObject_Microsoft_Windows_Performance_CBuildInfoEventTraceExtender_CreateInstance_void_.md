# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000efe8`
- end: `0x18000f0ca`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `226`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cedc`

## callees

- `0x18000181c`
- `0x18000efe8`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(
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
  *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable';
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
0x18000efe8  mov     [rsp+arg_10], r8
0x18000efed  mov     [rsp+arg_8], rdx
0x18000eff2  mov     [rsp+arg_0], rcx
0x18000eff7  push    rsi
0x18000eff8  push    rdi
0x18000eff9  push    r14
0x18000effb  sub     rsp, 20h
0x18000efff  mov     rsi, r8
0x18000f002  test    r8, r8
0x18000f005  jnz     short loc_18000F011
0x18000f007  mov     eax, 80004003h
0x18000f00c  jmp     loc_18000F0C1
0x18000f011  mov     qword ptr [r8], 0
0x18000f018  mov     r14d, 8007000Eh
0x18000f01e  mov     dword ptr [rsp+38h+arg_8], r14d
0x18000f023  mov     [rsp+38h+arg_0], 0
0x18000f02c  mov     ecx, 20h ; ' '; Size
0x18000f031  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f036  mov     rdi, rax
0x18000f039  mov     dword ptr [rax+18h], 0
0x18000f040  mov     qword ptr [rax+8], 0
0x18000f048  mov     qword ptr [rax+10h], 0
0x18000f050  lea     rax, ??_7?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable'
0x18000f057  mov     [rdi], rax
0x18000f05a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000f061  mov     rax, [rcx]
0x18000f064  mov     rax, [rax+8]
0x18000f068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f06d  mov     [rsp+38h+arg_0], rdi
0x18000f072  jmp     short loc_18000F083
0x18000f074  mov     rsi, [rsp+38h+arg_10]
0x18000f079  mov     r14d, dword ptr [rsp+38h+arg_8]
0x18000f07e  mov     rdi, [rsp+38h+arg_0]
0x18000f083  test    rdi, rdi
0x18000f086  jz      short loc_18000F0BE
0x18000f088  mov     rax, [rdi]
0x18000f08b  mov     r8, rsi
0x18000f08e  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18000f095  mov     rcx, rdi
0x18000f098  mov     rax, [rax]
0x18000f09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0a0  mov     r14d, eax
0x18000f0a3  test    eax, eax
0x18000f0a5  jz      short loc_18000F0BE
0x18000f0a7  mov     rdx, [rdi]
0x18000f0aa  mov     rax, [rdx+88h]
0x18000f0b1  mov     edx, 1
0x18000f0b6  mov     rcx, rdi
0x18000f0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0be  mov     eax, r14d
0x18000f0c1  add     rsp, 20h
0x18000f0c5  pop     r14
0x18000f0c7  pop     rdi
0x18000f0c8  pop     rsi
0x18000f0c9  retn
```
