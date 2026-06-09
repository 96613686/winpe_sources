# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPnpDiskCleanupHandler>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002db0`
- end: `0x180002e5a`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCPnpDiskCleanupHandler@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000116c`
- `0x180002db0`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPnpDiskCleanupHandler>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
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
    *(_QWORD *)v6 = &ATL::CComObject<CPnpDiskCleanupHandler>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v8 + 8LL))(v8);
    v5 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v7)(v7, a2, a3);
    if ( v5 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 72LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x180002db0  push    rbx
0x180002db2  push    rbp
0x180002db3  push    rsi
0x180002db4  push    rdi
0x180002db5  sub     rsp, 28h
0x180002db9  mov     rdi, r8
0x180002dbc  mov     rbp, rdx
0x180002dbf  test    rcx, rcx
0x180002dc2  jnz     short loc_180002E37
0x180002dc4  test    r8, r8
0x180002dc7  jz      short loc_180002E3C
0x180002dc9  mov     [r8], rcx
0x180002dcc  mov     ebx, 8007000Eh
0x180002dd1  mov     ecx, 10h; Size
0x180002dd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002ddb  mov     rsi, rax
0x180002dde  test    rax, rax
0x180002de1  jz      short loc_180002E4F
0x180002de3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002dea  mov     dword ptr [rax+8], 0
0x180002df1  lea     rax, ??_7?$CComObject@VCPnpDiskCleanupHandler@@@ATL@@6B@; const ATL::CComObject<CPnpDiskCleanupHandler>::`vftable'
0x180002df8  mov     [rsi], rax
0x180002dfb  mov     rdx, [rcx]
0x180002dfe  mov     rax, [rdx+8]
0x180002e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e07  mov     rcx, [rsi]
0x180002e0a  mov     r8, rdi
0x180002e0d  mov     rdx, rbp
0x180002e10  mov     rax, [rcx]
0x180002e13  mov     rcx, rsi
0x180002e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e1b  mov     ebx, eax
0x180002e1d  test    eax, eax
0x180002e1f  jz      short loc_180002E4F
0x180002e21  mov     rcx, [rsi]
0x180002e24  mov     edx, 1
0x180002e29  mov     rax, [rcx+48h]
0x180002e2d  mov     rcx, rsi
0x180002e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e35  jmp     short loc_180002E4F
0x180002e37  test    rdi, rdi
0x180002e3a  jnz     short loc_180002E43
0x180002e3c  mov     ebx, 80004003h
0x180002e41  jmp     short loc_180002E4F
0x180002e43  mov     qword ptr [r8], 0
0x180002e4a  mov     ebx, 80040110h
0x180002e4f  mov     eax, ebx
0x180002e51  add     rsp, 28h
0x180002e55  pop     rdi
0x180002e56  pop     rsi
0x180002e57  pop     rbp
0x180002e58  pop     rbx
0x180002e59  retn
```
