# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001ba0c`
- end: `0x18001bad9`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d530`

## callees

- `0x18000183c`
- `0x18001b49c`
- `0x18001ba0c`
- `0x180027010`

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
0x18001ba0c  mov     [rsp+arg_10], r8
0x18001ba11  mov     [rsp+arg_8], rdx
0x18001ba16  mov     [rsp+arg_0], rcx
0x18001ba1b  push    rbx
0x18001ba1c  push    rsi
0x18001ba1d  push    rdi
0x18001ba1e  sub     rsp, 20h
0x18001ba22  mov     rdi, r8
0x18001ba25  test    r8, r8
0x18001ba28  jnz     short loc_18001BA34
0x18001ba2a  mov     eax, 80004003h
0x18001ba2f  jmp     loc_18001BAD0
0x18001ba34  mov     qword ptr [r8], 0
0x18001ba3b  mov     esi, 8007000Eh
0x18001ba40  mov     dword ptr [rsp+38h+arg_8], esi
0x18001ba44  mov     [rsp+38h+arg_0], 0
0x18001ba4d  mov     ecx, 0B0h; Size
0x18001ba52  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ba57  mov     rbx, rax
0x18001ba5a  mov     rcx, rax; this
0x18001ba5d  call    ??0CVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender::CVolumeMappingEventTraceExtender(void)
0x18001ba62  lea     r11, ??_7?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable'
0x18001ba69  mov     [rbx], r11
0x18001ba6c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001ba73  mov     rax, [rcx]
0x18001ba76  mov     rax, [rax+8]
0x18001ba7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba7f  mov     [rsp+38h+arg_0], rbx
0x18001ba84  jmp     short loc_18001BA94
0x18001ba86  mov     rdi, [rsp+38h+arg_10]
0x18001ba8b  mov     esi, dword ptr [rsp+38h+arg_8]
0x18001ba8f  mov     rbx, [rsp+38h+arg_0]
0x18001ba94  test    rbx, rbx
0x18001ba97  jz      short loc_18001BACE
0x18001ba99  mov     rax, [rbx]
0x18001ba9c  mov     r8, rdi
0x18001ba9f  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18001baa6  mov     rcx, rbx
0x18001baa9  mov     rax, [rax]
0x18001baac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bab1  mov     esi, eax
0x18001bab3  test    eax, eax
0x18001bab5  jz      short loc_18001BACE
0x18001bab7  mov     rdx, [rbx]
0x18001baba  mov     rax, [rdx+88h]
0x18001bac1  mov     edx, 1
0x18001bac6  mov     rcx, rbx
0x18001bac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bace  mov     eax, esi
0x18001bad0  add     rsp, 20h
0x18001bad4  pop     rdi
0x18001bad5  pop     rsi
0x18001bad6  pop     rbx
0x18001bad7  retn
```
