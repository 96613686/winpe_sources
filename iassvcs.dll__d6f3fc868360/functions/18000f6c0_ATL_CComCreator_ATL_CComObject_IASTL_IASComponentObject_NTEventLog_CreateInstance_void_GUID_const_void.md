# ATL::CComCreator<ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f6c0`
- end: `0x18000f820`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@V?$IASComponentObject@VNTEventLog@@@IASTL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `352`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000f4e0`

## callees

- `0x18000d98c`
- `0x18000f6c0`
- `0x18001033c`
- `0x180014cc0`
- `0x180019010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000f753`
- `KERNEL32!InitializeCriticalSection` at `0x18000f753`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r15
  __int64 v4; // r12
  unsigned int v6; // r14d
  _DWORD *v7; // rax
  _DWORD *v8; // rsi
  int v9; // ecx
  int v10; // eax
  _DWORD *v13; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x2A0u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      *((_OWORD *)v7 + 1) = 0;
      *((_OWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 6) = 0;
      *((_BYTE *)v7 + 56) = 0;
      IASTraceInitializeEx(0);
      v8[16] = 0;
      *((_QWORD *)v8 + 10) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v8 + 26));
      *((_QWORD *)v8 + 18) = 0;
      v8[166] = 0;
      *(_QWORD *)v8 = &ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::`vftable'{for `IASTL::IASComponent'};
      *((_QWORD *)v8 + 9) = &ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::`vftable'{for `IAuditSink'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v13 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v13;
  }
  if ( v8 )
  {
    v9 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 4));
    if ( v9 >= 0 )
      *((_BYTE *)v8 + 56) = 1;
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 128LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000f6c0  mov     [rsp+arg_10], r8
0x18000f6c5  mov     [rsp+arg_8], rdx
0x18000f6ca  mov     [rsp+arg_0], rcx
0x18000f6cf  push    rbx
0x18000f6d0  push    rsi
0x18000f6d1  push    r12
0x18000f6d3  push    r14
0x18000f6d5  push    r15
0x18000f6d7  sub     rsp, 20h
0x18000f6db  mov     r15, r8
0x18000f6de  mov     r12, rdx
0x18000f6e1  test    r8, r8
0x18000f6e4  jnz     short loc_18000F6F0
0x18000f6e6  mov     eax, 80004003h
0x18000f6eb  jmp     loc_18000F813
0x18000f6f0  mov     qword ptr [r8], 0
0x18000f6f7  mov     r14d, 8007000Eh
0x18000f6fd  mov     dword ptr [rsp+48h+arg_0], r14d
0x18000f702  mov     [rsp+48h+arg_18], 0
0x18000f70b  mov     ecx, 2A0h; Size
0x18000f710  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f715  mov     rsi, rax
0x18000f718  test    rsi, rsi
0x18000f71b  jz      short loc_18000F796
0x18000f71d  mov     dword ptr [rax+8], 0
0x18000f724  xorps   xmm0, xmm0
0x18000f727  xor     eax, eax
0x18000f729  movups  xmmword ptr [rsi+10h], xmm0
0x18000f72d  movups  xmmword ptr [rsi+20h], xmm0
0x18000f731  mov     [rsi+30h], rax
0x18000f735  mov     [rsi+38h], al
0x18000f738  xor     ecx, ecx; Source
0x18000f73a  call    IASTraceInitializeEx
0x18000f73f  nop
0x18000f740  mov     dword ptr [rsi+40h], 0
0x18000f747  mov     qword ptr [rsi+50h], 0
0x18000f74f  lea     rcx, [rsi+68h]; lpCriticalSection
0x18000f753  call    cs:__imp_InitializeCriticalSection
0x18000f759  mov     qword ptr [rsi+90h], 0
0x18000f764  mov     dword ptr [rsi+298h], 0
0x18000f76e  lea     rax, ??_7?$CComObject@V?$IASComponentObject@VNTEventLog@@@IASTL@@@ATL@@6BIASComponent@IASTL@@@; const ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::`vftable'{for `IASTL::IASComponent'}
0x18000f775  mov     [rsi], rax
0x18000f778  lea     rax, ??_7?$CComObject@V?$IASComponentObject@VNTEventLog@@@IASTL@@@ATL@@6BIAuditSink@@@; const ATL::CComObject<IASTL::IASComponentObject<NTEventLog>>::`vftable'{for `IAuditSink'}
0x18000f77f  mov     [rsi+48h], rax
0x18000f783  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000f78a  mov     rax, [rcx]
0x18000f78d  mov     rax, [rax+8]
0x18000f791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f796  mov     [rsp+48h+arg_18], rsi
0x18000f79b  jmp     short loc_18000F7B1
0x18000f79d  mov     r15, [rsp+48h+arg_10]
0x18000f7a2  mov     r12, [rsp+48h+arg_8]
0x18000f7a7  mov     r14d, dword ptr [rsp+48h+arg_0]
0x18000f7ac  mov     rsi, [rsp+48h+arg_18]
0x18000f7b1  test    rsi, rsi
0x18000f7b4  jz      short loc_18000F810
0x18000f7b6  lea     rcx, [rsi+10h]; this
0x18000f7ba  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000f7bf  mov     ecx, eax
0x18000f7c1  test    eax, eax
0x18000f7c3  js      short loc_18000F7C9
0x18000f7c5  mov     byte ptr [rsi+38h], 1
0x18000f7c9  xor     eax, eax
0x18000f7cb  test    ecx, ecx
0x18000f7cd  cmovs   eax, ecx
0x18000f7d0  xor     r14d, r14d
0x18000f7d3  test    eax, eax
0x18000f7d5  cmovs   r14d, eax
0x18000f7d9  test    r14d, r14d
0x18000f7dc  jnz     short loc_18000F7F9
0x18000f7de  mov     rax, [rsi]
0x18000f7e1  mov     r8, r15
0x18000f7e4  mov     rdx, r12
0x18000f7e7  mov     rcx, rsi
0x18000f7ea  mov     rax, [rax]
0x18000f7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7f2  mov     r14d, eax
0x18000f7f5  test    eax, eax
0x18000f7f7  jz      short loc_18000F810
0x18000f7f9  mov     r8, [rsi]
0x18000f7fc  mov     edx, 1
0x18000f801  mov     rcx, rsi
0x18000f804  mov     rax, [r8+80h]
0x18000f80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f810  mov     eax, r14d
0x18000f813  add     rsp, 20h
0x18000f817  pop     r15
0x18000f819  pop     r14
0x18000f81b  pop     r12
0x18000f81d  pop     rsi
0x18000f81e  pop     rbx
0x18000f81f  retn
```
