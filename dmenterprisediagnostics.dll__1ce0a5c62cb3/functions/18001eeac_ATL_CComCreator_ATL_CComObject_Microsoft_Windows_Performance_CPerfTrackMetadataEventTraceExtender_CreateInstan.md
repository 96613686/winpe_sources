# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001eeac`
- end: `0x18001ef7e`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000cedc`

## callees

- `0x18000181c`
- `0x18001e9f0`
- `0x18001eeac`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *)operator new(0x90u);
    Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x18001eeac  mov     [rsp+arg_10], r8
0x18001eeb1  mov     [rsp+arg_8], rdx
0x18001eeb6  mov     [rsp+arg_0], rcx
0x18001eebb  push    rbx
0x18001eebc  push    rsi
0x18001eebd  push    rdi
0x18001eebe  sub     rsp, 20h
0x18001eec2  mov     rdi, r8
0x18001eec5  test    r8, r8
0x18001eec8  jnz     short loc_18001EED4
0x18001eeca  mov     eax, 80004003h
0x18001eecf  jmp     loc_18001EF76
0x18001eed4  mov     qword ptr [r8], 0
0x18001eedb  mov     esi, 8007000Eh
0x18001eee0  mov     dword ptr [rsp+38h+arg_8], esi
0x18001eee4  mov     [rsp+38h+arg_0], 0
0x18001eeed  mov     ecx, 90h; Size
0x18001eef2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001eef7  mov     rbx, rax
0x18001eefa  mov     [rsp+38h+arg_18], rax
0x18001eeff  mov     rcx, rax; this
0x18001ef02  call    ??0CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(void)
0x18001ef07  lea     rax, ??_7?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable'
0x18001ef0e  mov     [rbx], rax
0x18001ef11  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001ef18  mov     rax, [rcx]
0x18001ef1b  mov     rax, [rax+8]
0x18001ef1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef24  nop
0x18001ef25  mov     [rsp+38h+arg_0], rbx
0x18001ef2a  jmp     short loc_18001EF3A
0x18001ef2c  mov     rdi, [rsp+38h+arg_10]
0x18001ef31  mov     esi, dword ptr [rsp+38h+arg_8]
0x18001ef35  mov     rbx, [rsp+38h+arg_0]
0x18001ef3a  test    rbx, rbx
0x18001ef3d  jz      short loc_18001EF74
0x18001ef3f  mov     rax, [rbx]
0x18001ef42  mov     r8, rdi
0x18001ef45  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18001ef4c  mov     rcx, rbx
0x18001ef4f  mov     rax, [rax]
0x18001ef52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef57  mov     esi, eax
0x18001ef59  test    eax, eax
0x18001ef5b  jz      short loc_18001EF74
0x18001ef5d  mov     rdx, [rbx]
0x18001ef60  mov     rax, [rdx+88h]
0x18001ef67  mov     edx, 1
0x18001ef6c  mov     rcx, rbx
0x18001ef6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef74  mov     eax, esi
0x18001ef76  add     rsp, 20h
0x18001ef7a  pop     rdi
0x18001ef7b  pop     rsi
0x18001ef7c  pop     rbx
0x18001ef7d  retn
```
