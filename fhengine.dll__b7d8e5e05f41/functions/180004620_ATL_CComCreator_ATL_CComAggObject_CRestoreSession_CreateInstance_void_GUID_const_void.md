# ATL::CComCreator<ATL::CComAggObject<CRestoreSession>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004620`
- end: `0x180004745`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCRestoreSession@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `293`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800044b0`

## callees

- `0x180001a5c`
- `0x180002d38`
- `0x180004620`
- `0x180004f34`
- `0x180023e70`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CRestoreSession>>::CreateInstance(
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
  int v11; // edx
  _QWORD *v12; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x1C8u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *v8 = &ATL::CComAggObject<CRestoreSession>::`vftable';
      CRestoreSession::CRestoreSession((CRestoreSession *)(v8 + 3));
      v9[3] = &ATL::CComContainedObject<CRestoreSession>::`vftable';
      v9[4] = a1;
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
    v10 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v9 + 5));
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    if ( v11 >= 0 )
      v11 = CRestoreSession::FinalConstruct((CRestoreSession *)(v9 + 3));
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
0x180004620  mov     [rsp+arg_0], rbx
0x180004625  mov     [rsp+arg_10], r8
0x18000462a  mov     [rsp+arg_8], rdx
0x18000462f  push    rsi
0x180004630  push    rdi
0x180004631  push    r12
0x180004633  push    r14
0x180004635  push    r15
0x180004637  sub     rsp, 30h
0x18000463b  mov     r14, r8
0x18000463e  mov     r15, rdx
0x180004641  mov     r12, rcx
0x180004644  test    r8, r8
0x180004647  jnz     short loc_180004653
0x180004649  mov     eax, 80004003h
0x18000464e  jmp     loc_180004733
0x180004653  mov     qword ptr [r8], 0
0x18000465a  mov     esi, 8007000Eh
0x18000465f  mov     [rsp+58h+arg_18], esi
0x180004663  mov     [rsp+58h+var_38], 0
0x18000466c  mov     ecx, 1C8h; Size
0x180004671  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004676  mov     rdi, rax
0x180004679  test    rdi, rdi
0x18000467c  jz      short loc_1800046BA
0x18000467e  mov     dword ptr [rax+8], 0
0x180004685  lea     rax, ??_7?$CComAggObject@VCRestoreSession@@@ATL@@6B@; const ATL::CComAggObject<CRestoreSession>::`vftable'
0x18000468c  mov     [rdi], rax
0x18000468f  lea     rcx, [rdi+18h]; this
0x180004693  call    ??0CRestoreSession@@QEAA@XZ; CRestoreSession::CRestoreSession(void)
0x180004698  lea     rax, ??_7?$CComContainedObject@VCRestoreSession@@@ATL@@6B@; const ATL::CComContainedObject<CRestoreSession>::`vftable'
0x18000469f  mov     [rdi+18h], rax
0x1800046a3  mov     [rdi+20h], r12
0x1800046a7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800046ae  mov     rax, [rcx]
0x1800046b1  mov     rax, [rax+8]
0x1800046b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ba  mov     [rsp+58h+var_38], rdi
0x1800046bf  jmp     short loc_1800046D4
0x1800046c1  mov     r14, [rsp+58h+arg_10]
0x1800046c6  mov     r15, [rsp+58h+arg_8]
0x1800046cb  mov     esi, [rsp+58h+arg_18]
0x1800046cf  mov     rdi, [rsp+58h+var_38]
0x1800046d4  test    rdi, rdi
0x1800046d7  jz      short loc_180004731
0x1800046d9  lea     rcx, [rdi+28h]; this
0x1800046dd  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800046e2  xor     edx, edx
0x1800046e4  test    eax, eax
0x1800046e6  cmovs   edx, eax
0x1800046e9  test    edx, edx
0x1800046eb  js      short loc_1800046F8
0x1800046ed  lea     rcx, [rdi+18h]; this
0x1800046f1  call    ?FinalConstruct@CRestoreSession@@QEAAJXZ; CRestoreSession::FinalConstruct(void)
0x1800046f6  mov     edx, eax
0x1800046f8  xor     esi, esi
0x1800046fa  test    edx, edx
0x1800046fc  cmovs   esi, edx
0x1800046ff  test    esi, esi
0x180004701  jnz     short loc_18000471D
0x180004703  mov     rax, [rdi]
0x180004706  mov     r8, r14
0x180004709  mov     rdx, r15
0x18000470c  mov     rcx, rdi
0x18000470f  mov     rax, [rax]
0x180004712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004717  mov     esi, eax
0x180004719  test    eax, eax
0x18000471b  jz      short loc_180004731
0x18000471d  mov     rdx, [rdi]
0x180004720  mov     rax, [rdx+18h]
0x180004724  mov     edx, 1
0x180004729  mov     rcx, rdi
0x18000472c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004731  mov     eax, esi
0x180004733  mov     rbx, [rsp+58h+arg_0]
0x180004738  add     rsp, 30h
0x18000473c  pop     r15
0x18000473e  pop     r14
0x180004740  pop     r12
0x180004742  pop     rdi
0x180004743  pop     rsi
0x180004744  retn
```
