# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180014198`
- end: `0x18001426a`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000cedc`

## callees

- `0x18000181c`
- `0x180010e80`
- `0x180014198`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)operator new(0x1A8u);
    Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CImageIdEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CImageIdEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x180014198  mov     [rsp+arg_10], r8
0x18001419d  mov     [rsp+arg_8], rdx
0x1800141a2  mov     [rsp+arg_0], rcx
0x1800141a7  push    rbx
0x1800141a8  push    rsi
0x1800141a9  push    rdi
0x1800141aa  sub     rsp, 20h
0x1800141ae  mov     rdi, r8
0x1800141b1  test    r8, r8
0x1800141b4  jnz     short loc_1800141C0
0x1800141b6  mov     eax, 80004003h
0x1800141bb  jmp     loc_180014262
0x1800141c0  mov     qword ptr [r8], 0
0x1800141c7  mov     esi, 8007000Eh
0x1800141cc  mov     dword ptr [rsp+38h+arg_8], esi
0x1800141d0  mov     [rsp+38h+arg_0], 0
0x1800141d9  mov     ecx, 1A8h; Size
0x1800141de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800141e3  mov     rbx, rax
0x1800141e6  mov     [rsp+38h+arg_18], rax
0x1800141eb  mov     rcx, rax; this
0x1800141ee  call    ??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)
0x1800141f3  lea     rax, ??_7?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable'
0x1800141fa  mov     [rbx], rax
0x1800141fd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180014204  mov     rax, [rcx]
0x180014207  mov     rax, [rax+8]
0x18001420b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014210  nop
0x180014211  mov     [rsp+38h+arg_0], rbx
0x180014216  jmp     short loc_180014226
0x180014218  mov     rdi, [rsp+38h+arg_10]
0x18001421d  mov     esi, dword ptr [rsp+38h+arg_8]
0x180014221  mov     rbx, [rsp+38h+arg_0]
0x180014226  test    rbx, rbx
0x180014229  jz      short loc_180014260
0x18001422b  mov     rax, [rbx]
0x18001422e  mov     r8, rdi
0x180014231  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180014238  mov     rcx, rbx
0x18001423b  mov     rax, [rax]
0x18001423e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014243  mov     esi, eax
0x180014245  test    eax, eax
0x180014247  jz      short loc_180014260
0x180014249  mov     rdx, [rbx]
0x18001424c  mov     rax, [rdx+88h]
0x180014253  mov     edx, 1
0x180014258  mov     rcx, rbx
0x18001425b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014260  mov     eax, esi
0x180014262  add     rsp, 20h
0x180014266  pop     rdi
0x180014267  pop     rsi
0x180014268  pop     rbx
0x180014269  retn
```
