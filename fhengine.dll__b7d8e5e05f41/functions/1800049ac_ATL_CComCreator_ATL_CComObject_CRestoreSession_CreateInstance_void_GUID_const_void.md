# ATL::CComCreator<ATL::CComObject<CRestoreSession>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800049ac`
- end: `0x180004ab8`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCRestoreSession@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800044b0`

## callees

- `0x180001a5c`
- `0x180002d38`
- `0x1800049ac`
- `0x180004f34`
- `0x180006498`
- `0x1800064c0`
- `0x180023e70`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CRestoreSession>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  unsigned int v6; // edi
  CRestoreSession *v7; // rax
  volatile int *v8; // rbx
  int v9; // eax
  volatile int *v12; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CRestoreSession *)operator new(0x1B0u);
    v8 = (volatile int *)v7;
    if ( v7 )
    {
      CRestoreSession::CRestoreSession(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CRestoreSession>::`vftable';
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
    ATL::SafeIncrementReferenceMultiThread(v8 + 2);
    v9 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v8 + 4));
    if ( v9 >= 0 )
      v9 = CRestoreSession::FinalConstruct((CRestoreSession *)v8);
    v6 = 0;
    if ( v9 < 0 )
      v6 = v9;
    ATL::SafeDecrementReferenceMultiThread(v8 + 2);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(volatile int *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(volatile int *, __int64))(*(_QWORD *)v8 + 56LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800049ac  mov     [rsp+arg_10], r8
0x1800049b1  mov     [rsp+arg_8], rdx
0x1800049b6  mov     [rsp+arg_0], rcx
0x1800049bb  push    rbx
0x1800049bc  push    rsi
0x1800049bd  push    rdi
0x1800049be  push    r14
0x1800049c0  push    r15
0x1800049c2  sub     rsp, 20h
0x1800049c6  mov     rsi, r8
0x1800049c9  mov     r15, rdx
0x1800049cc  test    r8, r8
0x1800049cf  jnz     short loc_1800049DB
0x1800049d1  mov     eax, 80004003h
0x1800049d6  jmp     loc_180004AAC
0x1800049db  mov     qword ptr [r8], 0
0x1800049e2  mov     edi, 8007000Eh
0x1800049e7  mov     dword ptr [rsp+48h+arg_0], edi
0x1800049eb  mov     [rsp+48h+arg_18], 0
0x1800049f4  mov     ecx, 1B0h; Size
0x1800049f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800049fe  mov     rbx, rax
0x180004a01  test    rbx, rbx
0x180004a04  jz      short loc_180004A2B
0x180004a06  mov     rcx, rax; this
0x180004a09  call    ??0CRestoreSession@@QEAA@XZ; CRestoreSession::CRestoreSession(void)
0x180004a0e  lea     rax, ??_7?$CComObject@VCRestoreSession@@@ATL@@6B@; const ATL::CComObject<CRestoreSession>::`vftable'
0x180004a15  mov     [rbx], rax
0x180004a18  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004a1f  mov     rax, [rcx]
0x180004a22  mov     rax, [rax+8]
0x180004a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a2b  mov     [rsp+48h+arg_18], rbx
0x180004a30  jmp     short loc_180004A45
0x180004a32  mov     rsi, [rsp+48h+arg_10]
0x180004a37  mov     r15, [rsp+48h+arg_8]
0x180004a3c  mov     edi, dword ptr [rsp+48h+arg_0]
0x180004a40  mov     rbx, [rsp+48h+arg_18]
0x180004a45  test    rbx, rbx
0x180004a48  jz      short loc_180004AAA
0x180004a4a  lea     rcx, [rbx+8]; volatile int *
0x180004a4e  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x180004a53  lea     rcx, [rbx+10h]; this
0x180004a57  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180004a5c  test    eax, eax
0x180004a5e  js      short loc_180004A68
0x180004a60  mov     rcx, rbx; this
0x180004a63  call    ?FinalConstruct@CRestoreSession@@QEAAJXZ; CRestoreSession::FinalConstruct(void)
0x180004a68  xor     edi, edi
0x180004a6a  test    eax, eax
0x180004a6c  cmovs   edi, eax
0x180004a6f  lea     rcx, [rbx+8]; volatile int *
0x180004a73  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180004a78  test    edi, edi
0x180004a7a  jnz     short loc_180004A96
0x180004a7c  mov     rax, [rbx]
0x180004a7f  mov     r8, rsi
0x180004a82  mov     rdx, r15
0x180004a85  mov     rcx, rbx
0x180004a88  mov     rax, [rax]
0x180004a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a90  mov     edi, eax
0x180004a92  test    eax, eax
0x180004a94  jz      short loc_180004AAA
0x180004a96  mov     rdx, [rbx]
0x180004a99  mov     rax, [rdx+38h]
0x180004a9d  mov     edx, 1
0x180004aa2  mov     rcx, rbx
0x180004aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aaa  mov     eax, edi
0x180004aac  add     rsp, 20h
0x180004ab0  pop     r15
0x180004ab2  pop     r14
0x180004ab4  pop     rdi
0x180004ab5  pop     rsi
0x180004ab6  pop     rbx
0x180004ab7  retn
```
