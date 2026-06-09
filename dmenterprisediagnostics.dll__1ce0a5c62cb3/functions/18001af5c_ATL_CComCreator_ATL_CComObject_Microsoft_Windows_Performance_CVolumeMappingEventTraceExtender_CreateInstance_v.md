# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001af5c`
- end: `0x18001b028`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `204`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000cedc`

## callees

- `0x18000181c`
- `0x18001a9e8`
- `0x18001af5c`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *)operator new(0xB0u);
    Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender::CVolumeMappingEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x18001af5c  mov     [rsp+arg_10], r8
0x18001af61  mov     [rsp+arg_8], rdx
0x18001af66  mov     [rsp+arg_0], rcx
0x18001af6b  push    rbx
0x18001af6c  push    rsi
0x18001af6d  push    rdi
0x18001af6e  sub     rsp, 20h
0x18001af72  mov     rdi, r8
0x18001af75  test    r8, r8
0x18001af78  jnz     short loc_18001AF84
0x18001af7a  mov     eax, 80004003h
0x18001af7f  jmp     loc_18001B020
0x18001af84  mov     qword ptr [r8], 0
0x18001af8b  mov     esi, 8007000Eh
0x18001af90  mov     dword ptr [rsp+38h+arg_8], esi
0x18001af94  mov     [rsp+38h+arg_0], 0
0x18001af9d  mov     ecx, 0B0h; Size
0x18001afa2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001afa7  mov     rbx, rax
0x18001afaa  mov     rcx, rax; this
0x18001afad  call    ??0CVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender::CVolumeMappingEventTraceExtender(void)
0x18001afb2  lea     r11, ??_7?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable'
0x18001afb9  mov     [rbx], r11
0x18001afbc  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001afc3  mov     rax, [rcx]
0x18001afc6  mov     rax, [rax+8]
0x18001afca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afcf  mov     [rsp+38h+arg_0], rbx
0x18001afd4  jmp     short loc_18001AFE4
0x18001afd6  mov     rdi, [rsp+38h+arg_10]
0x18001afdb  mov     esi, dword ptr [rsp+38h+arg_8]
0x18001afdf  mov     rbx, [rsp+38h+arg_0]
0x18001afe4  test    rbx, rbx
0x18001afe7  jz      short loc_18001B01E
0x18001afe9  mov     rax, [rbx]
0x18001afec  mov     r8, rdi
0x18001afef  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18001aff6  mov     rcx, rbx
0x18001aff9  mov     rax, [rax]
0x18001affc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b001  mov     esi, eax
0x18001b003  test    eax, eax
0x18001b005  jz      short loc_18001B01E
0x18001b007  mov     rdx, [rbx]
0x18001b00a  mov     rax, [rdx+88h]
0x18001b011  mov     edx, 1
0x18001b016  mov     rcx, rbx
0x18001b019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b01e  mov     eax, esi
0x18001b020  add     rsp, 20h
0x18001b024  pop     rdi
0x18001b025  pop     rsi
0x18001b026  pop     rbx
0x18001b027  retn
```
