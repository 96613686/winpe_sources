# ATL::CComCreator<ATL::CComObject<CNetworkDiagnostics>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180012b70`
- end: `0x180012caf`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNetworkDiagnostics@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `319`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011f90`

## callees

- `0x1800018c0`
- `0x180012b70`
- `0x180021010`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180012c17`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180012c17`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CNetworkDiagnostics>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  unsigned int v6; // r14d
  char *v7; // rax
  char *v8; // rbx
  char *v11; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (char *)operator new(0xA8u);
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 2) = -1;
      *((_QWORD *)v7 + 3) = 0;
      *((_DWORD *)v7 + 8) = 0;
      *((_QWORD *)v7 + 5) = 0;
      *((_QWORD *)v7 + 6) = 0;
      *((_DWORD *)v7 + 14) = 0;
      *((_DWORD *)v7 + 30) = 0;
      InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v7 + 128), 0xFA0u);
      *((_OWORD *)v8 + 4) = 0;
      *((_OWORD *)v8 + 5) = 0;
      *((_OWORD *)v8 + 6) = 0;
      *((_QWORD *)v8 + 14) = 0;
      *(_QWORD *)v8 = &ATL::CComObject<CNetworkDiagnostics>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v11 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v11;
  }
  if ( v8 )
  {
    v6 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v8)(v8, v4, v3);
    if ( v6 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v8 + 224LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180012b70  mov     [rsp+arg_10], r8
0x180012b75  mov     [rsp+arg_8], rdx
0x180012b7a  mov     [rsp+arg_0], rcx
0x180012b7f  push    rbx
0x180012b80  push    rsi
0x180012b81  push    r14
0x180012b83  push    r15
0x180012b85  sub     rsp, 28h
0x180012b89  mov     rsi, r8
0x180012b8c  mov     r15, rdx
0x180012b8f  test    r8, r8
0x180012b92  jnz     short loc_180012B9E
0x180012b94  mov     eax, 80004003h
0x180012b99  jmp     loc_180012CA4
0x180012b9e  mov     qword ptr [r8], 0
0x180012ba5  mov     r14d, 8007000Eh
0x180012bab  mov     dword ptr [rsp+48h+arg_0], r14d
0x180012bb0  mov     [rsp+48h+arg_18], 0
0x180012bb9  mov     ecx, 0A8h; Size
0x180012bbe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012bc3  mov     rbx, rax
0x180012bc6  test    rbx, rbx
0x180012bc9  jz      loc_180012C4F
0x180012bcf  mov     dword ptr [rax+8], 0
0x180012bd6  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x180012bde  mov     qword ptr [rax+18h], 0
0x180012be6  mov     dword ptr [rax+20h], 0
0x180012bed  mov     qword ptr [rax+28h], 0
0x180012bf5  mov     qword ptr [rax+30h], 0
0x180012bfd  mov     dword ptr [rax+38h], 0
0x180012c04  mov     dword ptr [rax+78h], 0
0x180012c0b  lea     rcx, [rax+80h]; lpCriticalSection
0x180012c12  mov     edx, 0FA0h; dwSpinCount
0x180012c17  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180012c1d  xorps   xmm0, xmm0
0x180012c20  xor     eax, eax
0x180012c22  movups  xmmword ptr [rbx+40h], xmm0
0x180012c26  movups  xmmword ptr [rbx+50h], xmm0
0x180012c2a  movups  xmmword ptr [rbx+60h], xmm0
0x180012c2e  mov     [rbx+70h], rax
0x180012c32  lea     rax, ??_7?$CComObject@VCNetworkDiagnostics@@@ATL@@6B@; const ATL::CComObject<CNetworkDiagnostics>::`vftable'
0x180012c39  mov     [rbx], rax
0x180012c3c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012c43  mov     rax, [rcx]
0x180012c46  mov     rax, [rax+8]
0x180012c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c4f  mov     [rsp+48h+arg_18], rbx
0x180012c54  jmp     short loc_180012C6A
0x180012c56  mov     rsi, [rsp+48h+arg_10]
0x180012c5b  mov     r15, [rsp+48h+arg_8]
0x180012c60  mov     r14d, dword ptr [rsp+48h+arg_0]
0x180012c65  mov     rbx, [rsp+48h+arg_18]
0x180012c6a  test    rbx, rbx
0x180012c6d  jz      short loc_180012CA1
0x180012c6f  mov     rax, [rbx]
0x180012c72  mov     r8, rsi
0x180012c75  mov     rdx, r15
0x180012c78  mov     rcx, rbx
0x180012c7b  mov     rax, [rax]
0x180012c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c83  mov     r14d, eax
0x180012c86  test    eax, eax
0x180012c88  jz      short loc_180012CA1
0x180012c8a  mov     rdx, [rbx]
0x180012c8d  mov     rax, [rdx+0E0h]
0x180012c94  mov     edx, 1
0x180012c99  mov     rcx, rbx
0x180012c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ca1  mov     eax, r14d
0x180012ca4  add     rsp, 28h
0x180012ca8  pop     r15
0x180012caa  pop     r14
0x180012cac  pop     rsi
0x180012cad  pop     rbx
0x180012cae  retn
```
