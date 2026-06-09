# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180021960`
- end: `0x180021a32`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000cedc`

## callees

- `0x18000181c`
- `0x180021454`
- `0x180021960`
- `0x180026010`

## pseudocode

```c
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
0x180021960  mov     [rsp+arg_10], r8
0x180021965  mov     [rsp+arg_8], rdx
0x18002196a  mov     [rsp+arg_0], rcx
0x18002196f  push    rbx
0x180021970  push    rsi
0x180021971  push    rdi
0x180021972  sub     rsp, 20h
0x180021976  mov     rdi, r8
0x180021979  test    r8, r8
0x18002197c  jnz     short loc_180021988
0x18002197e  mov     eax, 80004003h
0x180021983  jmp     loc_180021A2A
0x180021988  mov     qword ptr [r8], 0
0x18002198f  mov     esi, 8007000Eh
0x180021994  mov     dword ptr [rsp+38h+arg_8], esi
0x180021998  mov     [rsp+38h+arg_0], 0
0x1800219a1  mov     ecx, 50h ; 'P'; Size
0x1800219a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800219ab  mov     rbx, rax
0x1800219ae  mov     [rsp+38h+arg_18], rax
0x1800219b3  mov     rcx, rax; this
0x1800219b6  call    ??0CElfImageEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CElfImageEventTraceExtender::CElfImageEventTraceExtender(void)
0x1800219bb  lea     rax, ??_7?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable'
0x1800219c2  mov     [rbx], rax
0x1800219c5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800219cc  mov     rax, [rcx]
0x1800219cf  mov     rax, [rax+8]
0x1800219d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219d8  nop
0x1800219d9  mov     [rsp+38h+arg_0], rbx
0x1800219de  jmp     short loc_1800219EE
0x1800219e0  mov     rdi, [rsp+38h+arg_10]
0x1800219e5  mov     esi, dword ptr [rsp+38h+arg_8]
0x1800219e9  mov     rbx, [rsp+38h+arg_0]
0x1800219ee  test    rbx, rbx
0x1800219f1  jz      short loc_180021A28
0x1800219f3  mov     rax, [rbx]
0x1800219f6  mov     r8, rdi
0x1800219f9  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180021a00  mov     rcx, rbx
0x180021a03  mov     rax, [rax]
0x180021a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a0b  mov     esi, eax
0x180021a0d  test    eax, eax
0x180021a0f  jz      short loc_180021A28
0x180021a11  mov     rdx, [rbx]
0x180021a14  mov     rax, [rdx+0A0h]
0x180021a1b  mov     edx, 1
0x180021a20  mov     rcx, rbx
0x180021a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a28  mov     eax, esi
0x180021a2a  add     rsp, 20h
0x180021a2e  pop     rdi
0x180021a2f  pop     rsi
0x180021a30  pop     rbx
0x180021a31  retn
```
