# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18001d8a0`
- end: `0x18001d973`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d530`

## callees

- `0x18000183c`
- `0x18001d170`
- `0x18001d8a0`
- `0x180027010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18001d8a0  mov     [rsp+arg_10], r8
0x18001d8a5  mov     [rsp+arg_8], rdx
0x18001d8aa  mov     [rsp+arg_0], rcx
0x18001d8af  push    rbx
0x18001d8b0  push    rsi
0x18001d8b1  push    rdi
0x18001d8b2  sub     rsp, 20h
0x18001d8b6  mov     rdi, r8
0x18001d8b9  test    r8, r8
0x18001d8bc  jnz     short loc_18001D8C8
0x18001d8be  mov     eax, 80004003h
0x18001d8c3  jmp     loc_18001D96A
0x18001d8c8  mov     qword ptr [r8], 0
0x18001d8cf  mov     esi, 8007000Eh
0x18001d8d4  mov     dword ptr [rsp+38h+arg_8], esi
0x18001d8d8  mov     [rsp+38h+arg_0], 0
0x18001d8e1  mov     ecx, 180h; Size
0x18001d8e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d8eb  mov     rbx, rax
0x18001d8ee  mov     [rsp+38h+arg_18], rax
0x18001d8f3  mov     rcx, rax; this
0x18001d8f6  call    ??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)
0x18001d8fb  lea     rax, ??_7?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable'
0x18001d902  mov     [rbx], rax
0x18001d905  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001d90c  mov     rax, [rcx]
0x18001d90f  mov     rax, [rax+8]
0x18001d913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d918  nop
0x18001d919  mov     [rsp+38h+arg_0], rbx
0x18001d91e  jmp     short loc_18001D92E
0x18001d920  mov     rdi, [rsp+38h+arg_10]
0x18001d925  mov     esi, dword ptr [rsp+38h+arg_8]
0x18001d929  mov     rbx, [rsp+38h+arg_0]
0x18001d92e  test    rbx, rbx
0x18001d931  jz      short loc_18001D968
0x18001d933  mov     rax, [rbx]
0x18001d936  mov     r8, rdi
0x18001d939  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18001d940  mov     rcx, rbx
0x18001d943  mov     rax, [rax]
0x18001d946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d94b  mov     esi, eax
0x18001d94d  test    eax, eax
0x18001d94f  jz      short loc_18001D968
0x18001d951  mov     rdx, [rbx]
0x18001d954  mov     rax, [rdx+88h]
0x18001d95b  mov     edx, 1
0x18001d960  mov     rcx, rbx
0x18001d963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d968  mov     eax, esi
0x18001d96a  add     rsp, 20h
0x18001d96e  pop     rdi
0x18001d96f  pop     rsi
0x18001d970  pop     rbx
0x18001d971  retn
```
