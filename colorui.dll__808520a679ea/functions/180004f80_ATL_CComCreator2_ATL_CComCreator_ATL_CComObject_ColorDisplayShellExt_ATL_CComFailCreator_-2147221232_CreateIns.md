# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<ColorDisplayShellExt>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004f80`
- end: `0x180005054`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VColorDisplayShellExt@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `212`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000134c`
- `0x180004f80`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<ColorDisplayShellExt>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  _QWORD *v6; // rax
  _QWORD *v7; // rsi
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
  v6 = operator new(0x28u);
  v7 = v6;
  if ( v6 )
  {
    v6[2] = g_hInst;
    v8 = ATL::_pAtlModule;
    *((_DWORD *)v6 + 8) = 0;
    v6[3] = 0;
    *v6 = &ATL::CComObject<ColorDisplayShellExt>::`vftable'{for `IShellExtInit'};
    v6[1] = &ATL::CComObject<ColorDisplayShellExt>::`vftable'{for `IShellPropSheetExt'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v8 + 8LL))(v8);
    v5 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v7)(v7, a2, a3);
    if ( v5 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v7 + 32LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x180004f80  push    rbx
0x180004f82  push    rbp
0x180004f83  push    rsi
0x180004f84  push    rdi
0x180004f85  sub     rsp, 28h
0x180004f89  mov     rdi, r8
0x180004f8c  mov     rbp, rdx
0x180004f8f  test    rcx, rcx
0x180004f92  jnz     loc_180005031
0x180004f98  test    r8, r8
0x180004f9b  jz      loc_180005036
0x180004fa1  mov     [r8], rcx
0x180004fa4  mov     ebx, 8007000Eh
0x180004fa9  mov     ecx, 28h ; '('; Size
0x180004fae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004fb3  mov     rsi, rax
0x180004fb6  test    rax, rax
0x180004fb9  jz      loc_180005049
0x180004fbf  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180004fc6  mov     [rax+10h], rcx
0x180004fca  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004fd1  mov     dword ptr [rax+20h], 0
0x180004fd8  mov     qword ptr [rax+18h], 0
0x180004fe0  lea     rax, ??_7?$CComObject@VColorDisplayShellExt@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<ColorDisplayShellExt>::`vftable'{for `IShellExtInit'}
0x180004fe7  mov     [rsi], rax
0x180004fea  lea     rax, ??_7?$CComObject@VColorDisplayShellExt@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComObject<ColorDisplayShellExt>::`vftable'{for `IShellPropSheetExt'}
0x180004ff1  mov     [rsi+8], rax
0x180004ff5  mov     rdx, [rcx]
0x180004ff8  mov     rax, [rdx+8]
0x180004ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005001  mov     rax, [rsi]
0x180005004  mov     r8, rdi
0x180005007  mov     rdx, rbp
0x18000500a  mov     rcx, rsi
0x18000500d  mov     rax, [rax]
0x180005010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005015  mov     ebx, eax
0x180005017  test    eax, eax
0x180005019  jz      short loc_180005049
0x18000501b  mov     rcx, [rsi]
0x18000501e  mov     edx, 1
0x180005023  mov     rax, [rcx+20h]
0x180005027  mov     rcx, rsi
0x18000502a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000502f  jmp     short loc_180005049
0x180005031  test    rdi, rdi
0x180005034  jnz     short loc_18000503D
0x180005036  mov     ebx, 80004003h
0x18000503b  jmp     short loc_180005049
0x18000503d  mov     qword ptr [r8], 0
0x180005044  mov     ebx, 80040110h
0x180005049  mov     eax, ebx
0x18000504b  add     rsp, 28h
0x18000504f  pop     rdi
0x180005050  pop     rsi
0x180005051  pop     rbp
0x180005052  pop     rbx
0x180005053  retn
```
