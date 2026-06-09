# ATL::CComCreator<ATL::CComAggObject<CBackupSession>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800044e4`
- end: `0x18000461a`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCBackupSession@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `310`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004490`

## callees

- `0x180001a5c`
- `0x180002c48`
- `0x1800044e4`
- `0x180004f34`
- `0x1800183cc`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CBackupSession>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  int v10; // eax
  int v11; // ecx
  _QWORD *v12; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x4A0u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *v8 = &ATL::CComAggObject<CBackupSession>::`vftable';
      CBackupSession::CBackupSession((CBackupSession *)(v8 + 3));
      v9[3] = &ATL::CComContainedObject<CBackupSession>::`vftable'{for `IFhEngineBackup'};
      v9[4] = &ATL::CComObject<CBackupSession>::`vftable'{for `CSessionBaseRW'};
      v9[39] = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v12 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v12;
  }
  if ( v9 )
  {
    v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 40));
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    if ( v11 >= 0 )
      v11 = CBackupSession::FinalConstruct((CBackupSession *)(v9 + 3));
    v7 = 0;
    if ( v11 < 0 )
      v7 = v11;
    if ( v7 || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x1800044e4  mov     [rsp+arg_0], rbx
0x1800044e9  mov     [rsp+arg_10], r8
0x1800044ee  mov     [rsp+arg_8], rdx
0x1800044f3  push    rsi
0x1800044f4  push    rdi
0x1800044f5  push    r12
0x1800044f7  push    r14
0x1800044f9  push    r15
0x1800044fb  sub     rsp, 30h
0x1800044ff  mov     r14, r8
0x180004502  mov     r15, rdx
0x180004505  mov     r12, rcx
0x180004508  test    r8, r8
0x18000450b  jnz     short loc_180004517
0x18000450d  mov     eax, 80004003h
0x180004512  jmp     loc_180004608
0x180004517  mov     qword ptr [r8], 0
0x18000451e  mov     esi, 8007000Eh
0x180004523  mov     [rsp+58h+arg_18], esi
0x180004527  mov     [rsp+58h+var_38], 0
0x180004530  mov     ecx, 4A0h; Size
0x180004535  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000453a  mov     rdi, rax
0x18000453d  test    rdi, rdi
0x180004540  jz      short loc_18000458C
0x180004542  mov     dword ptr [rax+8], 0
0x180004549  lea     rax, ??_7?$CComAggObject@VCBackupSession@@@ATL@@6B@; const ATL::CComAggObject<CBackupSession>::`vftable'
0x180004550  mov     [rdi], rax
0x180004553  lea     rcx, [rdi+18h]; this
0x180004557  call    ??0CBackupSession@@QEAA@XZ; CBackupSession::CBackupSession(void)
0x18000455c  lea     rax, ??_7?$CComContainedObject@VCBackupSession@@@ATL@@6BIFhEngineBackup@@@; const ATL::CComContainedObject<CBackupSession>::`vftable'{for `IFhEngineBackup'}
0x180004563  mov     [rdi+18h], rax
0x180004567  lea     rax, ??_7?$CComObject@VCBackupSession@@@ATL@@6BCSessionBaseRW@@@; const ATL::CComObject<CBackupSession>::`vftable'{for `CSessionBaseRW'}
0x18000456e  mov     [rdi+20h], rax
0x180004572  mov     [rdi+138h], r12
0x180004579  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004580  mov     rax, [rcx]
0x180004583  mov     rax, [rax+8]
0x180004587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000458c  mov     [rsp+58h+var_38], rdi
0x180004591  jmp     short loc_1800045A6
0x180004593  mov     r14, [rsp+58h+arg_10]
0x180004598  mov     r15, [rsp+58h+arg_8]
0x18000459d  mov     esi, [rsp+58h+arg_18]
0x1800045a1  mov     rdi, [rsp+58h+var_38]
0x1800045a6  test    rdi, rdi
0x1800045a9  jz      short loc_180004606
0x1800045ab  lea     rcx, [rdi+140h]; this
0x1800045b2  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800045b7  xor     ecx, ecx
0x1800045b9  test    eax, eax
0x1800045bb  cmovs   ecx, eax
0x1800045be  test    ecx, ecx
0x1800045c0  js      short loc_1800045CD
0x1800045c2  lea     rcx, [rdi+18h]; this
0x1800045c6  call    ?FinalConstruct@CBackupSession@@QEAAJXZ; CBackupSession::FinalConstruct(void)
0x1800045cb  mov     ecx, eax
0x1800045cd  xor     esi, esi
0x1800045cf  test    ecx, ecx
0x1800045d1  cmovs   esi, ecx
0x1800045d4  test    esi, esi
0x1800045d6  jnz     short loc_1800045F2
0x1800045d8  mov     rax, [rdi]
0x1800045db  mov     r8, r14
0x1800045de  mov     rdx, r15
0x1800045e1  mov     rcx, rdi
0x1800045e4  mov     rax, [rax]
0x1800045e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ec  mov     esi, eax
0x1800045ee  test    eax, eax
0x1800045f0  jz      short loc_180004606
0x1800045f2  mov     rdx, [rdi]
0x1800045f5  mov     rax, [rdx+18h]
0x1800045f9  mov     edx, 1
0x1800045fe  mov     rcx, rdi
0x180004601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004606  mov     eax, esi
0x180004608  mov     rbx, [rsp+58h+arg_0]
0x18000460d  add     rsp, 30h
0x180004611  pop     r15
0x180004613  pop     r14
0x180004615  pop     r12
0x180004617  pop     rdi
0x180004618  pop     rsi
0x180004619  retn
```
