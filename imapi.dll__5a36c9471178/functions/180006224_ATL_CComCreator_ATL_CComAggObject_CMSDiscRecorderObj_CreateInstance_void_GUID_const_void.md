# ATL::CComCreator<ATL::CComAggObject<CMSDiscRecorderObj>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006224`
- end: `0x180006317`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSDiscRecorderObj@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006210`

## callees

- `0x18000115c`
- `0x180002f5c`
- `0x180006224`
- `0x18000e850`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSDiscRecorderObj>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // ebx
  _DWORD *v8; // rax
  _DWORD *v9; // rdi
  ATL::CAtlModule *v10; // rcx
  int v11; // ecx
  int v12; // eax
  int v13; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = operator new(0x100u);
  v9 = v8;
  if ( v8 )
  {
    v8[2] = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<CMSDiscRecorderObj>::`vftable';
    CMSDiscRecorderObj::CMSDiscRecorderObj((CMSDiscRecorderObj *)(v8 + 6));
    v10 = ATL::_pAtlModule;
    *((_QWORD *)v9 + 3) = &ATL::CComContainedObject<CMSDiscRecorderObj>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v9 + 4) = &ATL::CComContainedObject<CMSDiscRecorderObj>::`vftable'{for `IDiscRecorder'};
    *((_QWORD *)v9 + 5) = a1;
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)v10 + 8LL))(v10);
    v11 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v9 + 12));
    if ( v11 >= 0 )
      *((_BYTE *)v9 + 88) = 1;
    v12 = 0;
    if ( v11 < 0 )
      v12 = v11;
    v13 = 0;
    if ( v12 < 0 )
      v13 = v12;
    v7 = 0;
    if ( v13 < 0 )
      v7 = v13;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180006224  push    rbx
0x180006226  push    rbp
0x180006227  push    rsi
0x180006228  push    rdi
0x180006229  push    r14
0x18000622b  sub     rsp, 20h
0x18000622f  mov     rsi, r8
0x180006232  mov     r14, rdx
0x180006235  mov     rbp, rcx
0x180006238  test    r8, r8
0x18000623b  jnz     short loc_180006247
0x18000623d  mov     eax, 80004003h
0x180006242  jmp     loc_18000630C
0x180006247  mov     ecx, 100h; Size
0x18000624c  mov     qword ptr [r8], 0
0x180006253  mov     ebx, 8007000Eh
0x180006258  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000625d  mov     rdi, rax
0x180006260  test    rax, rax
0x180006263  jz      loc_18000630A
0x180006269  mov     dword ptr [rax+8], 0
0x180006270  lea     rcx, [rdi+18h]; this
0x180006274  lea     rax, ??_7?$CComAggObject@VCMSDiscRecorderObj@@@ATL@@6B@; const ATL::CComAggObject<CMSDiscRecorderObj>::`vftable'
0x18000627b  mov     [rdi], rax
0x18000627e  call    ??0CMSDiscRecorderObj@@QEAA@XZ; CMSDiscRecorderObj::CMSDiscRecorderObj(void)
0x180006283  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000628a  lea     rax, ??_7?$CComContainedObject@VCMSDiscRecorderObj@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSDiscRecorderObj>::`vftable'{for `ISupportErrorInfo'}
0x180006291  mov     [rdi+18h], rax
0x180006295  lea     rax, ??_7?$CComContainedObject@VCMSDiscRecorderObj@@@ATL@@6BIDiscRecorder@@@; const ATL::CComContainedObject<CMSDiscRecorderObj>::`vftable'{for `IDiscRecorder'}
0x18000629c  mov     [rdi+20h], rax
0x1800062a0  mov     [rdi+28h], rbp
0x1800062a4  mov     rax, [rcx]
0x1800062a7  mov     rax, [rax+8]
0x1800062ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062b0  lea     rcx, [rdi+30h]; this
0x1800062b4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800062b9  mov     ecx, eax
0x1800062bb  test    eax, eax
0x1800062bd  js      short loc_1800062C3
0x1800062bf  mov     byte ptr [rdi+58h], 1
0x1800062c3  xor     eax, eax
0x1800062c5  test    ecx, ecx
0x1800062c7  cmovs   eax, ecx
0x1800062ca  xor     ecx, ecx
0x1800062cc  test    eax, eax
0x1800062ce  cmovs   ecx, eax
0x1800062d1  xor     ebx, ebx
0x1800062d3  test    ecx, ecx
0x1800062d5  cmovs   ebx, ecx
0x1800062d8  test    ebx, ebx
0x1800062da  jnz     short loc_1800062F6
0x1800062dc  mov     rax, [rdi]
0x1800062df  mov     r8, rsi
0x1800062e2  mov     rdx, r14
0x1800062e5  mov     rcx, rdi
0x1800062e8  mov     rax, [rax]
0x1800062eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062f0  mov     ebx, eax
0x1800062f2  test    eax, eax
0x1800062f4  jz      short loc_18000630A
0x1800062f6  mov     rcx, [rdi]
0x1800062f9  mov     edx, 1
0x1800062fe  mov     rax, [rcx+18h]
0x180006302  mov     rcx, rdi
0x180006305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000630a  mov     eax, ebx
0x18000630c  add     rsp, 20h
0x180006310  pop     r14
0x180006312  pop     rdi
0x180006313  pop     rsi
0x180006314  pop     rbp
0x180006315  pop     rbx
0x180006316  retn
```
