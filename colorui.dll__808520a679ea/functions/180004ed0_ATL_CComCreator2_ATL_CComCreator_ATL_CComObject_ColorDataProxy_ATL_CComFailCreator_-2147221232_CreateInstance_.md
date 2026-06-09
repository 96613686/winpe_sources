# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<ColorDataProxy>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004ed0`
- end: `0x180004f7a`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VColorDataProxy@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000134c`
- `0x180004ed0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<ColorDataProxy>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  _DWORD *v6; // rax
  _DWORD *v7; // rsi
  struct ATL::CAtlModule *v8; // rcx

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      return (unsigned int)-2147221232;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v5 = -2147024882;
  v6 = operator new(0x10u);
  v7 = v6;
  if ( v6 )
  {
    v8 = ATL::_pAtlModule;
    v6[2] = 0;
    *(_QWORD *)v6 = &ATL::CComObject<ColorDataProxy>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v8 + 8LL))(v8);
    v5 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v7)(v7, a2, a3);
    if ( v5 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 120LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x180004ed0  push    rbx
0x180004ed2  push    rbp
0x180004ed3  push    rsi
0x180004ed4  push    rdi
0x180004ed5  sub     rsp, 28h
0x180004ed9  mov     rdi, r8
0x180004edc  mov     rbp, rdx
0x180004edf  test    rcx, rcx
0x180004ee2  jnz     short loc_180004F57
0x180004ee4  test    r8, r8
0x180004ee7  jz      short loc_180004F5C
0x180004ee9  mov     [r8], rcx
0x180004eec  mov     ebx, 8007000Eh
0x180004ef1  mov     ecx, 10h; Size
0x180004ef6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004efb  mov     rsi, rax
0x180004efe  test    rax, rax
0x180004f01  jz      short loc_180004F6F
0x180004f03  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004f0a  mov     dword ptr [rax+8], 0
0x180004f11  lea     rax, ??_7?$CComObject@VColorDataProxy@@@ATL@@6B@; const ATL::CComObject<ColorDataProxy>::`vftable'
0x180004f18  mov     [rsi], rax
0x180004f1b  mov     rdx, [rcx]
0x180004f1e  mov     rax, [rdx+8]
0x180004f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f27  mov     rcx, [rsi]
0x180004f2a  mov     r8, rdi
0x180004f2d  mov     rdx, rbp
0x180004f30  mov     rax, [rcx]
0x180004f33  mov     rcx, rsi
0x180004f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f3b  mov     ebx, eax
0x180004f3d  test    eax, eax
0x180004f3f  jz      short loc_180004F6F
0x180004f41  mov     rcx, [rsi]
0x180004f44  mov     edx, 1
0x180004f49  mov     rax, [rcx+78h]
0x180004f4d  mov     rcx, rsi
0x180004f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f55  jmp     short loc_180004F6F
0x180004f57  test    rdi, rdi
0x180004f5a  jnz     short loc_180004F63
0x180004f5c  mov     ebx, 80004003h
0x180004f61  jmp     short loc_180004F6F
0x180004f63  mov     qword ptr [r8], 0
0x180004f6a  mov     ebx, 80040110h
0x180004f6f  mov     eax, ebx
0x180004f71  add     rsp, 28h
0x180004f75  pop     rdi
0x180004f76  pop     rsi
0x180004f77  pop     rbp
0x180004f78  pop     rbx
0x180004f79  retn
```
