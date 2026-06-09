# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002012c`
- end: `0x1800201fe`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000cedc`

## callees

- `0x18000181c`
- `0x18001ff20`
- `0x18002012c`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  Microsoft::Windows::Performance::CWinSATEventTraceExtender *v5; // rbx
  unsigned int v6; // esi
  Microsoft::Windows::Performance::CWinSATEventTraceExtender *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = (Microsoft::Windows::Performance::CWinSATEventTraceExtender *)operator new(0x68u);
    Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(v5);
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable';
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
    v6 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CWinSATEventTraceExtender *, GUID *, _QWORD *))v5)(
           v5,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v6 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CWinSATEventTraceExtender *, __int64))(*(_QWORD *)v5 + 136LL))(
        v5,
        1);
  }
  return v6;
}

```

## disassembly

```asm
0x18002012c  mov     [rsp+arg_10], r8
0x180020131  mov     [rsp+arg_8], rdx
0x180020136  mov     [rsp+arg_0], rcx
0x18002013b  push    rbx
0x18002013c  push    rsi
0x18002013d  push    rdi
0x18002013e  sub     rsp, 20h
0x180020142  mov     rdi, r8
0x180020145  test    r8, r8
0x180020148  jnz     short loc_180020154
0x18002014a  mov     eax, 80004003h
0x18002014f  jmp     loc_1800201F6
0x180020154  mov     qword ptr [r8], 0
0x18002015b  mov     esi, 8007000Eh
0x180020160  mov     dword ptr [rsp+38h+arg_8], esi
0x180020164  mov     [rsp+38h+arg_0], 0
0x18002016d  mov     ecx, 68h ; 'h'; Size
0x180020172  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020177  mov     rbx, rax
0x18002017a  mov     [rsp+38h+arg_18], rax
0x18002017f  mov     rcx, rax; this
0x180020182  call    ??0CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CWinSATEventTraceExtender::CWinSATEventTraceExtender(void)
0x180020187  lea     rax, ??_7?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable'
0x18002018e  mov     [rbx], rax
0x180020191  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180020198  mov     rax, [rcx]
0x18002019b  mov     rax, [rax+8]
0x18002019f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201a4  nop
0x1800201a5  mov     [rsp+38h+arg_0], rbx
0x1800201aa  jmp     short loc_1800201BA
0x1800201ac  mov     rdi, [rsp+38h+arg_10]
0x1800201b1  mov     esi, dword ptr [rsp+38h+arg_8]
0x1800201b5  mov     rbx, [rsp+38h+arg_0]
0x1800201ba  test    rbx, rbx
0x1800201bd  jz      short loc_1800201F4
0x1800201bf  mov     rax, [rbx]
0x1800201c2  mov     r8, rdi
0x1800201c5  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x1800201cc  mov     rcx, rbx
0x1800201cf  mov     rax, [rax]
0x1800201d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201d7  mov     esi, eax
0x1800201d9  test    eax, eax
0x1800201db  jz      short loc_1800201F4
0x1800201dd  mov     rdx, [rbx]
0x1800201e0  mov     rax, [rdx+88h]
0x1800201e7  mov     edx, 1
0x1800201ec  mov     rcx, rbx
0x1800201ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201f4  mov     eax, esi
0x1800201f6  add     rsp, 20h
0x1800201fa  pop     rdi
0x1800201fb  pop     rsi
0x1800201fc  pop     rbx
0x1800201fd  retn
```
