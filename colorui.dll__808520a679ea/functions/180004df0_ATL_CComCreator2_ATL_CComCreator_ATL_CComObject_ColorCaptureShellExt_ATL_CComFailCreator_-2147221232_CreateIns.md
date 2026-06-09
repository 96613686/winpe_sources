# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<ColorCaptureShellExt>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004df0`
- end: `0x180004ec4`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VColorCaptureShellExt@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `212`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000134c`
- `0x180004df0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<ColorCaptureShellExt>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
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
    *v6 = &ATL::CComObject<ColorCaptureShellExt>::`vftable'{for `IShellExtInit'};
    v6[1] = &ATL::CComObject<ColorCaptureShellExt>::`vftable'{for `IShellPropSheetExt'};
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
0x180004df0  push    rbx
0x180004df2  push    rbp
0x180004df3  push    rsi
0x180004df4  push    rdi
0x180004df5  sub     rsp, 28h
0x180004df9  mov     rdi, r8
0x180004dfc  mov     rbp, rdx
0x180004dff  test    rcx, rcx
0x180004e02  jnz     loc_180004EA1
0x180004e08  test    r8, r8
0x180004e0b  jz      loc_180004EA6
0x180004e11  mov     [r8], rcx
0x180004e14  mov     ebx, 8007000Eh
0x180004e19  mov     ecx, 28h ; '('; Size
0x180004e1e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004e23  mov     rsi, rax
0x180004e26  test    rax, rax
0x180004e29  jz      loc_180004EB9
0x180004e2f  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180004e36  mov     [rax+10h], rcx
0x180004e3a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004e41  mov     dword ptr [rax+20h], 0
0x180004e48  mov     qword ptr [rax+18h], 0
0x180004e50  lea     rax, ??_7?$CComObject@VColorCaptureShellExt@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<ColorCaptureShellExt>::`vftable'{for `IShellExtInit'}
0x180004e57  mov     [rsi], rax
0x180004e5a  lea     rax, ??_7?$CComObject@VColorCaptureShellExt@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComObject<ColorCaptureShellExt>::`vftable'{for `IShellPropSheetExt'}
0x180004e61  mov     [rsi+8], rax
0x180004e65  mov     rdx, [rcx]
0x180004e68  mov     rax, [rdx+8]
0x180004e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e71  mov     rax, [rsi]
0x180004e74  mov     r8, rdi
0x180004e77  mov     rdx, rbp
0x180004e7a  mov     rcx, rsi
0x180004e7d  mov     rax, [rax]
0x180004e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e85  mov     ebx, eax
0x180004e87  test    eax, eax
0x180004e89  jz      short loc_180004EB9
0x180004e8b  mov     rcx, [rsi]
0x180004e8e  mov     edx, 1
0x180004e93  mov     rax, [rcx+20h]
0x180004e97  mov     rcx, rsi
0x180004e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e9f  jmp     short loc_180004EB9
0x180004ea1  test    rdi, rdi
0x180004ea4  jnz     short loc_180004EAD
0x180004ea6  mov     ebx, 80004003h
0x180004eab  jmp     short loc_180004EB9
0x180004ead  mov     qword ptr [r8], 0
0x180004eb4  mov     ebx, 80040110h
0x180004eb9  mov     eax, ebx
0x180004ebb  add     rsp, 28h
0x180004ebf  pop     rdi
0x180004ec0  pop     rsi
0x180004ec1  pop     rbp
0x180004ec2  pop     rbx
0x180004ec3  retn
```
