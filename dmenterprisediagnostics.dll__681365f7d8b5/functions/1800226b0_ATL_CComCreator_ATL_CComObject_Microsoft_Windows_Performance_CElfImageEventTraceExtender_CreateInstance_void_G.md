# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800226b0`
- end: `0x180022783`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d530`

## callees

- `0x18000183c`
- `0x180022170`
- `0x1800226b0`
- `0x180027010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CElfImageEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CElfImageEventTraceExtender *)operator new(0x50u);
    Microsoft::Windows::Performance::CElfImageEventTraceExtender::CElfImageEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CElfImageEventTraceExtender *, __int64))(*(_QWORD *)v5 + 160LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800226b0  mov     [rsp+arg_10], r8
0x1800226b5  mov     [rsp+arg_8], rdx
0x1800226ba  mov     [rsp+arg_0], rcx
0x1800226bf  push    rbx
0x1800226c0  push    rsi
0x1800226c1  push    rdi
0x1800226c2  sub     rsp, 20h
0x1800226c6  mov     rdi, r8
0x1800226c9  test    r8, r8
0x1800226cc  jnz     short loc_1800226D8
0x1800226ce  mov     eax, 80004003h
0x1800226d3  jmp     loc_18002277A
0x1800226d8  mov     qword ptr [r8], 0
0x1800226df  mov     esi, 8007000Eh
0x1800226e4  mov     dword ptr [rsp+38h+arg_8], esi
0x1800226e8  mov     [rsp+38h+arg_0], 0
0x1800226f1  mov     ecx, 50h ; 'P'; Size
0x1800226f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800226fb  mov     rbx, rax
0x1800226fe  mov     [rsp+38h+arg_18], rax
0x180022703  mov     rcx, rax; this
0x180022706  call    ??0CElfImageEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CElfImageEventTraceExtender::CElfImageEventTraceExtender(void)
0x18002270b  lea     rax, ??_7?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable'
0x180022712  mov     [rbx], rax
0x180022715  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002271c  mov     rax, [rcx]
0x18002271f  mov     rax, [rax+8]
0x180022723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022728  nop
0x180022729  mov     [rsp+38h+arg_0], rbx
0x18002272e  jmp     short loc_18002273E
0x180022730  mov     rdi, [rsp+38h+arg_10]
0x180022735  mov     esi, dword ptr [rsp+38h+arg_8]
0x180022739  mov     rbx, [rsp+38h+arg_0]
0x18002273e  test    rbx, rbx
0x180022741  jz      short loc_180022778
0x180022743  mov     rax, [rbx]
0x180022746  mov     r8, rdi
0x180022749  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180022750  mov     rcx, rbx
0x180022753  mov     rax, [rax]
0x180022756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002275b  mov     esi, eax
0x18002275d  test    eax, eax
0x18002275f  jz      short loc_180022778
0x180022761  mov     rdx, [rbx]
0x180022764  mov     rax, [rdx+0A0h]
0x18002276b  mov     edx, 1
0x180022770  mov     rcx, rbx
0x180022773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022778  mov     eax, esi
0x18002277a  add     rsp, 20h
0x18002277e  pop     rdi
0x18002277f  pop     rsi
0x180022780  pop     rbx
0x180022781  retn
```
