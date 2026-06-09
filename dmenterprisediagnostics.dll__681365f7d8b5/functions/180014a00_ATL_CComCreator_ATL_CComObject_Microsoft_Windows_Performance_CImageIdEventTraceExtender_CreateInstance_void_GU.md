# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180014a00`
- end: `0x180014ad3`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d530`

## callees

- `0x18000183c`
- `0x180011618`
- `0x180014a00`
- `0x180027010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180014a00  mov     [rsp+arg_10], r8
0x180014a05  mov     [rsp+arg_8], rdx
0x180014a0a  mov     [rsp+arg_0], rcx
0x180014a0f  push    rbx
0x180014a10  push    rsi
0x180014a11  push    rdi
0x180014a12  sub     rsp, 20h
0x180014a16  mov     rdi, r8
0x180014a19  test    r8, r8
0x180014a1c  jnz     short loc_180014A28
0x180014a1e  mov     eax, 80004003h
0x180014a23  jmp     loc_180014ACA
0x180014a28  mov     qword ptr [r8], 0
0x180014a2f  mov     esi, 8007000Eh
0x180014a34  mov     dword ptr [rsp+38h+arg_8], esi
0x180014a38  mov     [rsp+38h+arg_0], 0
0x180014a41  mov     ecx, 1A8h; Size
0x180014a46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014a4b  mov     rbx, rax
0x180014a4e  mov     [rsp+38h+arg_18], rax
0x180014a53  mov     rcx, rax; this
0x180014a56  call    ??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)
0x180014a5b  lea     rax, ??_7?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable'
0x180014a62  mov     [rbx], rax
0x180014a65  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180014a6c  mov     rax, [rcx]
0x180014a6f  mov     rax, [rax+8]
0x180014a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a78  nop
0x180014a79  mov     [rsp+38h+arg_0], rbx
0x180014a7e  jmp     short loc_180014A8E
0x180014a80  mov     rdi, [rsp+38h+arg_10]
0x180014a85  mov     esi, dword ptr [rsp+38h+arg_8]
0x180014a89  mov     rbx, [rsp+38h+arg_0]
0x180014a8e  test    rbx, rbx
0x180014a91  jz      short loc_180014AC8
0x180014a93  mov     rax, [rbx]
0x180014a96  mov     r8, rdi
0x180014a99  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180014aa0  mov     rcx, rbx
0x180014aa3  mov     rax, [rax]
0x180014aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aab  mov     esi, eax
0x180014aad  test    eax, eax
0x180014aaf  jz      short loc_180014AC8
0x180014ab1  mov     rdx, [rbx]
0x180014ab4  mov     rax, [rdx+88h]
0x180014abb  mov     edx, 1
0x180014ac0  mov     rcx, rbx
0x180014ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ac8  mov     eax, esi
0x180014aca  add     rsp, 20h
0x180014ace  pop     rdi
0x180014acf  pop     rsi
0x180014ad0  pop     rbx
0x180014ad1  retn
```
