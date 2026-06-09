# ATL::CComCreator<ATL::CComObject<CMSDiscRecorderObj>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006320`
- end: `0x180006422`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMSDiscRecorderObj@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006210`

## callees

- `0x18000115c`
- `0x180002f5c`
- `0x180006320`
- `0x18000e850`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMSDiscRecorderObj>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // esi
  CMSDiscRecorderObj *v7; // rax
  CMSDiscRecorderObj *v8; // rbx
  ATL::CAtlModule *v9; // rcx
  volatile signed __int32 *v10; // rdi
  signed __int32 v11; // eax
  int v12; // eax
  int v13; // ecx
  signed __int32 v14; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CMSDiscRecorderObj *)operator new(0xE8u);
  v8 = v7;
  if ( v7 )
  {
    CMSDiscRecorderObj::CMSDiscRecorderObj(v7);
    v9 = ATL::_pAtlModule;
    *(_QWORD *)v8 = &ATL::CComObject<CMSDiscRecorderObj>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMSDiscRecorderObj>::`vftable'{for `IDiscRecorder'};
    (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
    v10 = (volatile signed __int32 *)((char *)v8 + 16);
    do
    {
      if ( *v10 == 0x7FFFFFFF )
        break;
      v11 = *v10;
    }
    while ( v11 != _InterlockedCompareExchange(v10, v11 + 1, v11) );
    v12 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)((char *)v8 + 24));
    if ( v12 >= 0 )
      *((_BYTE *)v8 + 64) = 1;
    v13 = 0;
    if ( v12 < 0 )
      v13 = v12;
    v6 = 0;
    if ( v13 < 0 )
      v6 = v13;
    do
    {
      if ( *v10 == 0x7FFFFFFF )
        break;
      v14 = *v10;
    }
    while ( v14 != _InterlockedCompareExchange(v10, v14 - 1, v14) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CMSDiscRecorderObj *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(CMSDiscRecorderObj *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180006320  push    rbx
0x180006322  push    rbp
0x180006323  push    rsi
0x180006324  push    rdi
0x180006325  push    r14
0x180006327  push    r15
0x180006329  sub     rsp, 28h
0x18000632d  mov     r14, r8
0x180006330  mov     rbp, rdx
0x180006333  test    r8, r8
0x180006336  jnz     short loc_180006342
0x180006338  mov     eax, 80004003h
0x18000633d  jmp     loc_180006415
0x180006342  mov     ecx, 0E8h; Size
0x180006347  mov     qword ptr [r8], 0
0x18000634e  mov     esi, 8007000Eh
0x180006353  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006358  mov     rbx, rax
0x18000635b  test    rax, rax
0x18000635e  jz      loc_180006413
0x180006364  mov     rcx, rax; this
0x180006367  call    ??0CMSDiscRecorderObj@@QEAA@XZ; CMSDiscRecorderObj::CMSDiscRecorderObj(void)
0x18000636c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006373  lea     rax, ??_7?$CComObject@VCMSDiscRecorderObj@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSDiscRecorderObj>::`vftable'{for `ISupportErrorInfo'}
0x18000637a  mov     [rbx], rax
0x18000637d  lea     rax, ??_7?$CComObject@VCMSDiscRecorderObj@@@ATL@@6BIDiscRecorder@@@; const ATL::CComObject<CMSDiscRecorderObj>::`vftable'{for `IDiscRecorder'}
0x180006384  mov     [rbx+8], rax
0x180006388  mov     rax, [rcx]
0x18000638b  mov     rax, [rax+8]
0x18000638f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006394  lea     rdi, [rbx+10h]
0x180006398  mov     r15d, 7FFFFFFFh
0x18000639e  jmp     short loc_1800063A9
0x1800063a0  lea     ecx, [rax+1]
0x1800063a3  lock cmpxchg [rdi], ecx
0x1800063a7  jz      short loc_1800063B0
0x1800063a9  mov     eax, [rdi]
0x1800063ab  cmp     eax, r15d
0x1800063ae  jnz     short loc_1800063A0
0x1800063b0  lea     rcx, [rdi+8]; this
0x1800063b4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800063b9  test    eax, eax
0x1800063bb  js      short loc_1800063C1
0x1800063bd  mov     byte ptr [rdi+30h], 1
0x1800063c1  xor     ecx, ecx
0x1800063c3  test    eax, eax
0x1800063c5  cmovs   ecx, eax
0x1800063c8  xor     esi, esi
0x1800063ca  test    ecx, ecx
0x1800063cc  cmovs   esi, ecx
0x1800063cf  jmp     short loc_1800063DA
0x1800063d1  lea     ecx, [rax-1]
0x1800063d4  lock cmpxchg [rdi], ecx
0x1800063d8  jz      short loc_1800063E1
0x1800063da  mov     eax, [rdi]
0x1800063dc  cmp     eax, r15d
0x1800063df  jnz     short loc_1800063D1
0x1800063e1  test    esi, esi
0x1800063e3  jnz     short loc_1800063FF
0x1800063e5  mov     rax, [rbx]
0x1800063e8  mov     r8, r14
0x1800063eb  mov     rdx, rbp
0x1800063ee  mov     rcx, rbx
0x1800063f1  mov     rax, [rax]
0x1800063f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063f9  mov     esi, eax
0x1800063fb  test    eax, eax
0x1800063fd  jz      short loc_180006413
0x1800063ff  mov     r8, [rbx]
0x180006402  mov     edx, 1
0x180006407  mov     rcx, rbx
0x18000640a  mov     rax, [r8+20h]
0x18000640e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006413  mov     eax, esi
0x180006415  add     rsp, 28h
0x180006419  pop     r15
0x18000641b  pop     r14
0x18000641d  pop     rdi
0x18000641e  pop     rsi
0x18000641f  pop     rbp
0x180006420  pop     rbx
0x180006421  retn
```
