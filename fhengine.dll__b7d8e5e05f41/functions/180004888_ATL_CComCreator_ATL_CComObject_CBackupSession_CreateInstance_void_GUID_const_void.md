# ATL::CComCreator<ATL::CComObject<CBackupSession>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004888`
- end: `0x1800049a4`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCBackupSession@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `284`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180004490`

## callees

- `0x180001a5c`
- `0x180002c48`
- `0x180004888`
- `0x180004f34`
- `0x180006498`
- `0x1800064c0`
- `0x1800183cc`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CBackupSession>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  unsigned int v6; // edi
  CBackupSession *v7; // rax
  CBackupSession *v8; // rbx
  int v9; // eax
  CBackupSession *v12; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CBackupSession *)operator new(0x488u);
    v8 = v7;
    if ( v7 )
    {
      CBackupSession::CBackupSession(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CBackupSession>::`vftable'{for `IFhEngineBackup'};
      *((_QWORD *)v8 + 1) = &ATL::CComObject<CBackupSession>::`vftable'{for `CSessionBaseRW'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v12;
  }
  if ( v8 )
  {
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v8 + 72);
    v9 = ATL::CComSafeDeleteCriticalSection::Init((CBackupSession *)((char *)v8 + 296));
    if ( v9 >= 0 )
      v9 = CBackupSession::FinalConstruct(v8);
    v6 = 0;
    if ( v9 < 0 )
      v6 = v9;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v8 + 72);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CBackupSession *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(CBackupSession *, __int64))(*(_QWORD *)v8 + 112LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180004888  mov     [rsp+arg_10], r8
0x18000488d  mov     [rsp+arg_8], rdx
0x180004892  mov     [rsp+arg_0], rcx
0x180004897  push    rbx
0x180004898  push    rsi
0x180004899  push    rdi
0x18000489a  push    r14
0x18000489c  push    r15
0x18000489e  sub     rsp, 20h
0x1800048a2  mov     rsi, r8
0x1800048a5  mov     r15, rdx
0x1800048a8  test    r8, r8
0x1800048ab  jnz     short loc_1800048B7
0x1800048ad  mov     eax, 80004003h
0x1800048b2  jmp     loc_180004998
0x1800048b7  mov     qword ptr [r8], 0
0x1800048be  mov     edi, 8007000Eh
0x1800048c3  mov     dword ptr [rsp+48h+arg_0], edi
0x1800048c7  mov     [rsp+48h+arg_18], 0
0x1800048d0  mov     ecx, 488h; Size
0x1800048d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800048da  mov     rbx, rax
0x1800048dd  test    rbx, rbx
0x1800048e0  jz      short loc_180004912
0x1800048e2  mov     rcx, rax; this
0x1800048e5  call    ??0CBackupSession@@QEAA@XZ; CBackupSession::CBackupSession(void)
0x1800048ea  lea     rax, ??_7?$CComObject@VCBackupSession@@@ATL@@6BIFhEngineBackup@@@; const ATL::CComObject<CBackupSession>::`vftable'{for `IFhEngineBackup'}
0x1800048f1  mov     [rbx], rax
0x1800048f4  lea     rax, ??_7?$CComObject@VCBackupSession@@@ATL@@6BCSessionBaseRW@@@; const ATL::CComObject<CBackupSession>::`vftable'{for `CSessionBaseRW'}
0x1800048fb  mov     [rbx+8], rax
0x1800048ff  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004906  mov     rax, [rcx]
0x180004909  mov     rax, [rax+8]
0x18000490d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004912  mov     [rsp+48h+arg_18], rbx
0x180004917  jmp     short loc_18000492C
0x180004919  mov     rsi, [rsp+48h+arg_10]
0x18000491e  mov     r15, [rsp+48h+arg_8]
0x180004923  mov     edi, dword ptr [rsp+48h+arg_0]
0x180004927  mov     rbx, [rsp+48h+arg_18]
0x18000492c  test    rbx, rbx
0x18000492f  jz      short loc_180004996
0x180004931  lea     r14, [rbx+120h]
0x180004938  mov     rcx, r14; volatile int *
0x18000493b  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180004940  lea     rcx, [r14+8]; this
0x180004944  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180004949  test    eax, eax
0x18000494b  js      short loc_180004955
0x18000494d  mov     rcx, rbx; this
0x180004950  call    ?FinalConstruct@CBackupSession@@QEAAJXZ; CBackupSession::FinalConstruct(void)
0x180004955  xor     edi, edi
0x180004957  test    eax, eax
0x180004959  cmovs   edi, eax
0x18000495c  mov     rcx, r14; volatile int *
0x18000495f  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180004964  test    edi, edi
0x180004966  jnz     short loc_180004982
0x180004968  mov     rax, [rbx]
0x18000496b  mov     r8, rsi
0x18000496e  mov     rdx, r15
0x180004971  mov     rcx, rbx
0x180004974  mov     rax, [rax]
0x180004977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000497c  mov     edi, eax
0x18000497e  test    eax, eax
0x180004980  jz      short loc_180004996
0x180004982  mov     rdx, [rbx]
0x180004985  mov     rax, [rdx+70h]
0x180004989  mov     edx, 1
0x18000498e  mov     rcx, rbx
0x180004991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004996  mov     eax, edi
0x180004998  add     rsp, 20h
0x18000499c  pop     r15
0x18000499e  pop     r14
0x1800049a0  pop     rdi
0x1800049a1  pop     rsi
0x1800049a2  pop     rbx
0x1800049a3  retn
```
