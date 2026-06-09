# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180019318`
- end: `0x1800193ea`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000cedc`

## callees

- `0x18000181c`
- `0x1800185b0`
- `0x180019318`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CNGenEventTraceExtender *)operator new(0xB8u);
    Microsoft::Windows::Performance::CNGenEventTraceExtender::CNGenEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CNGenEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CNGenEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x180019318  mov     [rsp+arg_10], r8
0x18001931d  mov     [rsp+arg_8], rdx
0x180019322  mov     [rsp+arg_0], rcx
0x180019327  push    rbx
0x180019328  push    rsi
0x180019329  push    rdi
0x18001932a  sub     rsp, 20h
0x18001932e  mov     rdi, r8
0x180019331  test    r8, r8
0x180019334  jnz     short loc_180019340
0x180019336  mov     eax, 80004003h
0x18001933b  jmp     loc_1800193E2
0x180019340  mov     qword ptr [r8], 0
0x180019347  mov     esi, 8007000Eh
0x18001934c  mov     dword ptr [rsp+38h+arg_8], esi
0x180019350  mov     [rsp+38h+arg_0], 0
0x180019359  mov     ecx, 0B8h; Size
0x18001935e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019363  mov     rbx, rax
0x180019366  mov     [rsp+38h+arg_18], rax
0x18001936b  mov     rcx, rax; this
0x18001936e  call    ??0CNGenEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CNGenEventTraceExtender::CNGenEventTraceExtender(void)
0x180019373  lea     rax, ??_7?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable'
0x18001937a  mov     [rbx], rax
0x18001937d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180019384  mov     rax, [rcx]
0x180019387  mov     rax, [rax+8]
0x18001938b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019390  nop
0x180019391  mov     [rsp+38h+arg_0], rbx
0x180019396  jmp     short loc_1800193A6
0x180019398  mov     rdi, [rsp+38h+arg_10]
0x18001939d  mov     esi, dword ptr [rsp+38h+arg_8]
0x1800193a1  mov     rbx, [rsp+38h+arg_0]
0x1800193a6  test    rbx, rbx
0x1800193a9  jz      short loc_1800193E0
0x1800193ab  mov     rax, [rbx]
0x1800193ae  mov     r8, rdi
0x1800193b1  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x1800193b8  mov     rcx, rbx
0x1800193bb  mov     rax, [rax]
0x1800193be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193c3  mov     esi, eax
0x1800193c5  test    eax, eax
0x1800193c7  jz      short loc_1800193E0
0x1800193c9  mov     rdx, [rbx]
0x1800193cc  mov     rax, [rdx+88h]
0x1800193d3  mov     edx, 1
0x1800193d8  mov     rcx, rbx
0x1800193db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193e0  mov     eax, esi
0x1800193e2  add     rsp, 20h
0x1800193e6  pop     rdi
0x1800193e7  pop     rsi
0x1800193e8  pop     rbx
0x1800193e9  retn
```
