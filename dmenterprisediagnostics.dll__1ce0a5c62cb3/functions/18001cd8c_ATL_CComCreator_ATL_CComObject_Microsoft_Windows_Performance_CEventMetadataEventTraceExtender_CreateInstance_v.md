# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001cd8c`
- end: `0x18001ce5e`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000cedc`

## callees

- `0x18000181c`
- `0x18001c694`
- `0x18001cd8c`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *)operator new(0x180u);
    Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x18001cd8c  mov     [rsp+arg_10], r8
0x18001cd91  mov     [rsp+arg_8], rdx
0x18001cd96  mov     [rsp+arg_0], rcx
0x18001cd9b  push    rbx
0x18001cd9c  push    rsi
0x18001cd9d  push    rdi
0x18001cd9e  sub     rsp, 20h
0x18001cda2  mov     rdi, r8
0x18001cda5  test    r8, r8
0x18001cda8  jnz     short loc_18001CDB4
0x18001cdaa  mov     eax, 80004003h
0x18001cdaf  jmp     loc_18001CE56
0x18001cdb4  mov     qword ptr [r8], 0
0x18001cdbb  mov     esi, 8007000Eh
0x18001cdc0  mov     dword ptr [rsp+38h+arg_8], esi
0x18001cdc4  mov     [rsp+38h+arg_0], 0
0x18001cdcd  mov     ecx, 180h; Size
0x18001cdd2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cdd7  mov     rbx, rax
0x18001cdda  mov     [rsp+38h+arg_18], rax
0x18001cddf  mov     rcx, rax; this
0x18001cde2  call    ??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)
0x18001cde7  lea     rax, ??_7?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable'
0x18001cdee  mov     [rbx], rax
0x18001cdf1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001cdf8  mov     rax, [rcx]
0x18001cdfb  mov     rax, [rax+8]
0x18001cdff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce04  nop
0x18001ce05  mov     [rsp+38h+arg_0], rbx
0x18001ce0a  jmp     short loc_18001CE1A
0x18001ce0c  mov     rdi, [rsp+38h+arg_10]
0x18001ce11  mov     esi, dword ptr [rsp+38h+arg_8]
0x18001ce15  mov     rbx, [rsp+38h+arg_0]
0x18001ce1a  test    rbx, rbx
0x18001ce1d  jz      short loc_18001CE54
0x18001ce1f  mov     rax, [rbx]
0x18001ce22  mov     r8, rdi
0x18001ce25  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18001ce2c  mov     rcx, rbx
0x18001ce2f  mov     rax, [rax]
0x18001ce32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce37  mov     esi, eax
0x18001ce39  test    eax, eax
0x18001ce3b  jz      short loc_18001CE54
0x18001ce3d  mov     rdx, [rbx]
0x18001ce40  mov     rax, [rdx+88h]
0x18001ce47  mov     edx, 1
0x18001ce4c  mov     rcx, rbx
0x18001ce4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce54  mov     eax, esi
0x18001ce56  add     rsp, 20h
0x18001ce5a  pop     rdi
0x18001ce5b  pop     rsi
0x18001ce5c  pop     rbx
0x18001ce5d  retn
```
