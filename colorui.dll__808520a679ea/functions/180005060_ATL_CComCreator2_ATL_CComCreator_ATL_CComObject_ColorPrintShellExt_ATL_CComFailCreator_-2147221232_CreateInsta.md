# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<ColorPrintShellExt>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180005060`
- end: `0x180005134`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VColorPrintShellExt@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `212`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000134c`
- `0x180005060`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<ColorPrintShellExt>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
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
    *v6 = &ATL::CComObject<ColorPrintShellExt>::`vftable'{for `IShellExtInit'};
    v6[1] = &ATL::CComObject<ColorPrintShellExt>::`vftable'{for `IShellPropSheetExt'};
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
0x180005060  push    rbx
0x180005062  push    rbp
0x180005063  push    rsi
0x180005064  push    rdi
0x180005065  sub     rsp, 28h
0x180005069  mov     rdi, r8
0x18000506c  mov     rbp, rdx
0x18000506f  test    rcx, rcx
0x180005072  jnz     loc_180005111
0x180005078  test    r8, r8
0x18000507b  jz      loc_180005116
0x180005081  mov     [r8], rcx
0x180005084  mov     ebx, 8007000Eh
0x180005089  mov     ecx, 28h ; '('; Size
0x18000508e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005093  mov     rsi, rax
0x180005096  test    rax, rax
0x180005099  jz      loc_180005129
0x18000509f  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x1800050a6  mov     [rax+10h], rcx
0x1800050aa  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800050b1  mov     dword ptr [rax+20h], 0
0x1800050b8  mov     qword ptr [rax+18h], 0
0x1800050c0  lea     rax, ??_7?$CComObject@VColorPrintShellExt@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<ColorPrintShellExt>::`vftable'{for `IShellExtInit'}
0x1800050c7  mov     [rsi], rax
0x1800050ca  lea     rax, ??_7?$CComObject@VColorPrintShellExt@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComObject<ColorPrintShellExt>::`vftable'{for `IShellPropSheetExt'}
0x1800050d1  mov     [rsi+8], rax
0x1800050d5  mov     rdx, [rcx]
0x1800050d8  mov     rax, [rdx+8]
0x1800050dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050e1  mov     rax, [rsi]
0x1800050e4  mov     r8, rdi
0x1800050e7  mov     rdx, rbp
0x1800050ea  mov     rcx, rsi
0x1800050ed  mov     rax, [rax]
0x1800050f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050f5  mov     ebx, eax
0x1800050f7  test    eax, eax
0x1800050f9  jz      short loc_180005129
0x1800050fb  mov     rcx, [rsi]
0x1800050fe  mov     edx, 1
0x180005103  mov     rax, [rcx+20h]
0x180005107  mov     rcx, rsi
0x18000510a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000510f  jmp     short loc_180005129
0x180005111  test    rdi, rdi
0x180005114  jnz     short loc_18000511D
0x180005116  mov     ebx, 80004003h
0x18000511b  jmp     short loc_180005129
0x18000511d  mov     qword ptr [r8], 0
0x180005124  mov     ebx, 80040110h
0x180005129  mov     eax, ebx
0x18000512b  add     rsp, 28h
0x18000512f  pop     rdi
0x180005130  pop     rsi
0x180005131  pop     rbp
0x180005132  pop     rbx
0x180005133  retn
```
