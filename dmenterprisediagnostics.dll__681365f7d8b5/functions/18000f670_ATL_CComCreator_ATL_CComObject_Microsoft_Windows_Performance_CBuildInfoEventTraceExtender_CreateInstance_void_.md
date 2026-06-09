# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f670`
- end: `0x18000f753`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d530`

## callees

- `0x18000183c`
- `0x18000f670`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // r14d
  _DWORD *v6; // rdi

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  v6 = operator new(0x20u);
  v6[6] = 0;
  *((_QWORD *)v6 + 1) = 0;
  *((_QWORD *)v6 + 2) = 0;
  *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  if ( v6 )
  {
    v5 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))v6)(v6, &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33, a3);
    if ( v5 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v6 + 136LL))(v6, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x18000f670  mov     [rsp+arg_10], r8
0x18000f675  mov     [rsp+arg_8], rdx
0x18000f67a  mov     [rsp+arg_0], rcx
0x18000f67f  push    rsi
0x18000f680  push    rdi
0x18000f681  push    r14
0x18000f683  sub     rsp, 20h
0x18000f687  mov     rsi, r8
0x18000f68a  test    r8, r8
0x18000f68d  jnz     short loc_18000F699
0x18000f68f  mov     eax, 80004003h
0x18000f694  jmp     loc_18000F749
0x18000f699  mov     qword ptr [r8], 0
0x18000f6a0  mov     r14d, 8007000Eh
0x18000f6a6  mov     dword ptr [rsp+38h+arg_8], r14d
0x18000f6ab  mov     [rsp+38h+arg_0], 0
0x18000f6b4  mov     ecx, 20h ; ' '; Size
0x18000f6b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f6be  mov     rdi, rax
0x18000f6c1  mov     dword ptr [rax+18h], 0
0x18000f6c8  mov     qword ptr [rax+8], 0
0x18000f6d0  mov     qword ptr [rax+10h], 0
0x18000f6d8  lea     rax, ??_7?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable'
0x18000f6df  mov     [rdi], rax
0x18000f6e2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000f6e9  mov     rax, [rcx]
0x18000f6ec  mov     rax, [rax+8]
0x18000f6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6f5  mov     [rsp+38h+arg_0], rdi
0x18000f6fa  jmp     short loc_18000F70B
0x18000f6fc  mov     rsi, [rsp+38h+arg_10]
0x18000f701  mov     r14d, dword ptr [rsp+38h+arg_8]
0x18000f706  mov     rdi, [rsp+38h+arg_0]
0x18000f70b  test    rdi, rdi
0x18000f70e  jz      short loc_18000F746
0x18000f710  mov     rax, [rdi]
0x18000f713  mov     r8, rsi
0x18000f716  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18000f71d  mov     rcx, rdi
0x18000f720  mov     rax, [rax]
0x18000f723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f728  mov     r14d, eax
0x18000f72b  test    eax, eax
0x18000f72d  jz      short loc_18000F746
0x18000f72f  mov     rdx, [rdi]
0x18000f732  mov     rax, [rdx+88h]
0x18000f739  mov     edx, 1
0x18000f73e  mov     rcx, rdi
0x18000f741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f746  mov     eax, r14d
0x18000f749  add     rsp, 20h
0x18000f74d  pop     r14
0x18000f74f  pop     rdi
0x18000f750  pop     rsi
0x18000f751  retn
```
