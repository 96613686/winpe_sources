# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001fa9c`
- end: `0x18001fb6f`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d530`

## callees

- `0x18000183c`
- `0x18001f58c`
- `0x18001fa9c`
- `0x180027010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001fa9c  mov     [rsp+arg_10], r8
0x18001faa1  mov     [rsp+arg_8], rdx
0x18001faa6  mov     [rsp+arg_0], rcx
0x18001faab  push    rbx
0x18001faac  push    rsi
0x18001faad  push    rdi
0x18001faae  sub     rsp, 20h
0x18001fab2  mov     rdi, r8
0x18001fab5  test    r8, r8
0x18001fab8  jnz     short loc_18001FAC4
0x18001faba  mov     eax, 80004003h
0x18001fabf  jmp     loc_18001FB66
0x18001fac4  mov     qword ptr [r8], 0
0x18001facb  mov     esi, 8007000Eh
0x18001fad0  mov     dword ptr [rsp+38h+arg_8], esi
0x18001fad4  mov     [rsp+38h+arg_0], 0
0x18001fadd  mov     ecx, 90h; Size
0x18001fae2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fae7  mov     rbx, rax
0x18001faea  mov     [rsp+38h+arg_18], rax
0x18001faef  mov     rcx, rax; this
0x18001faf2  call    ??0CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(void)
0x18001faf7  lea     rax, ??_7?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable'
0x18001fafe  mov     [rbx], rax
0x18001fb01  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001fb08  mov     rax, [rcx]
0x18001fb0b  mov     rax, [rax+8]
0x18001fb0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb14  nop
0x18001fb15  mov     [rsp+38h+arg_0], rbx
0x18001fb1a  jmp     short loc_18001FB2A
0x18001fb1c  mov     rdi, [rsp+38h+arg_10]
0x18001fb21  mov     esi, dword ptr [rsp+38h+arg_8]
0x18001fb25  mov     rbx, [rsp+38h+arg_0]
0x18001fb2a  test    rbx, rbx
0x18001fb2d  jz      short loc_18001FB64
0x18001fb2f  mov     rax, [rbx]
0x18001fb32  mov     r8, rdi
0x18001fb35  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18001fb3c  mov     rcx, rbx
0x18001fb3f  mov     rax, [rax]
0x18001fb42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb47  mov     esi, eax
0x18001fb49  test    eax, eax
0x18001fb4b  jz      short loc_18001FB64
0x18001fb4d  mov     rdx, [rbx]
0x18001fb50  mov     rax, [rdx+88h]
0x18001fb57  mov     edx, 1
0x18001fb5c  mov     rcx, rbx
0x18001fb5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb64  mov     eax, esi
0x18001fb66  add     rsp, 20h
0x18001fb6a  pop     rdi
0x18001fb6b  pop     rsi
0x18001fb6c  pop     rbx
0x18001fb6d  retn
```
