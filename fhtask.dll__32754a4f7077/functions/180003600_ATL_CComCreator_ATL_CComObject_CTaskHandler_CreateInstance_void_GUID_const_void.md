# ATL::CComCreator<ATL::CComObject<CTaskHandler>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003600`
- end: `0x180003749`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCTaskHandler@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `329`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180003200`

## callees

- `0x1800011d8`
- `0x180003600`
- `0x1800039cc`
- `0x18000612c`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CTaskHandler>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  struct _RTL_CRITICAL_SECTION *v7; // rax
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  signed __int32 LockCount; // eax
  int v10; // eax
  signed __int32 v11; // eax
  struct _RTL_CRITICAL_SECTION *v14; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (struct _RTL_CRITICAL_SECTION *)operator new(0x90u);
    v8 = v7;
    if ( v7 )
    {
      v7->LockCount = 0;
      *(_OWORD *)&v7->OwningThread = 0;
      *(_OWORD *)&v7->SpinCount = 0;
      *(_QWORD *)&v7[1].LockCount = 0;
      LOBYTE(v7[1].OwningThread) = 0;
      v7[1].LockSemaphore = 0;
      v7->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComObject<CTaskHandler>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v14 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v14;
  }
  if ( v8 )
  {
    do
      LockCount = v8->LockCount;
    while ( LockCount != 0x7FFFFFFF
         && LockCount != _InterlockedCompareExchange(&v8->LockCount, LockCount + 1, LockCount) );
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&v8->OwningThread);
    if ( v10 >= 0 )
    {
      LOBYTE(v8[1].OwningThread) = 1;
      v10 = CTaskHandler::FinalConstruct(v8);
    }
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    do
      v11 = v8->LockCount;
    while ( v11 != 0x7FFFFFFF && v11 != _InterlockedCompareExchange(&v8->LockCount, v11 - 1, v11) );
    if ( v6
      || (v6 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, _QWORD *))v8->DebugInfo->Type)(
                 v8,
                 v4,
                 v3)) != 0 )
    {
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v8->DebugInfo[1].CriticalSection)(v8, 1);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180003600  mov     [rsp+arg_10], r8
0x180003605  mov     [rsp+arg_8], rdx
0x18000360a  mov     [rsp+arg_0], rcx
0x18000360f  push    rbx
0x180003610  push    rsi
0x180003611  push    r12
0x180003613  push    r14
0x180003615  push    r15
0x180003617  sub     rsp, 20h
0x18000361b  mov     r14, r8
0x18000361e  mov     r15, rdx
0x180003621  test    r8, r8
0x180003624  jnz     short loc_180003630
0x180003626  mov     eax, 80004003h
0x18000362b  jmp     loc_18000373C
0x180003630  mov     qword ptr [r8], 0
0x180003637  mov     esi, 8007000Eh
0x18000363c  mov     dword ptr [rsp+48h+arg_0], esi
0x180003640  mov     [rsp+48h+arg_18], 0
0x180003649  mov     ecx, 90h; Size
0x18000364e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003653  mov     rbx, rax
0x180003656  test    rbx, rbx
0x180003659  jz      short loc_180003697
0x18000365b  mov     dword ptr [rax+8], 0
0x180003662  xorps   xmm0, xmm0
0x180003665  xor     eax, eax
0x180003667  movups  xmmword ptr [rbx+10h], xmm0
0x18000366b  movups  xmmword ptr [rbx+20h], xmm0
0x18000366f  mov     [rbx+30h], rax
0x180003673  mov     [rbx+38h], al
0x180003676  mov     [rbx+40h], rax
0x18000367a  lea     rax, ??_7?$CComObject@VCTaskHandler@@@ATL@@6B@; const ATL::CComObject<CTaskHandler>::`vftable'
0x180003681  mov     [rbx], rax
0x180003684  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000368b  mov     rax, [rcx]
0x18000368e  mov     rax, [rax+8]
0x180003692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003697  mov     [rsp+48h+arg_18], rbx
0x18000369c  jmp     short loc_1800036B1
0x18000369e  mov     r14, [rsp+48h+arg_10]
0x1800036a3  mov     r15, [rsp+48h+arg_8]
0x1800036a8  mov     esi, dword ptr [rsp+48h+arg_0]
0x1800036ac  mov     rbx, [rsp+48h+arg_18]
0x1800036b1  test    rbx, rbx
0x1800036b4  jz      loc_18000373A
0x1800036ba  mov     r12d, 7FFFFFFFh
0x1800036c0  jmp     short loc_1800036CC
0x1800036c2  lea     ecx, [rax+1]
0x1800036c5  lock cmpxchg [rbx+8], ecx
0x1800036ca  jz      short loc_1800036D4
0x1800036cc  mov     eax, [rbx+8]
0x1800036cf  cmp     eax, r12d
0x1800036d2  jnz     short loc_1800036C2
0x1800036d4  lea     rcx, [rbx+10h]; this
0x1800036d8  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800036dd  test    eax, eax
0x1800036df  js      short loc_1800036ED
0x1800036e1  mov     byte ptr [rbx+38h], 1
0x1800036e5  mov     rcx, rbx; this
0x1800036e8  call    ?FinalConstruct@CTaskHandler@@QEAAJXZ; CTaskHandler::FinalConstruct(void)
0x1800036ed  xor     esi, esi
0x1800036ef  test    eax, eax
0x1800036f1  cmovs   esi, eax
0x1800036f4  jmp     short loc_180003700
0x1800036f6  lea     ecx, [rax-1]
0x1800036f9  lock cmpxchg [rbx+8], ecx
0x1800036fe  jz      short loc_180003708
0x180003700  mov     eax, [rbx+8]
0x180003703  cmp     eax, r12d
0x180003706  jnz     short loc_1800036F6
0x180003708  test    esi, esi
0x18000370a  jnz     short loc_180003726
0x18000370c  mov     rax, [rbx]
0x18000370f  mov     r8, r14
0x180003712  mov     rdx, r15
0x180003715  mov     rcx, rbx
0x180003718  mov     rax, [rax]
0x18000371b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003720  mov     esi, eax
0x180003722  test    eax, eax
0x180003724  jz      short loc_18000373A
0x180003726  mov     r8, [rbx]
0x180003729  mov     edx, 1
0x18000372e  mov     rcx, rbx
0x180003731  mov     rax, [r8+38h]
0x180003735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000373a  mov     eax, esi
0x18000373c  add     rsp, 20h
0x180003740  pop     r15
0x180003742  pop     r14
0x180003744  pop     r12
0x180003746  pop     rsi
0x180003747  pop     rbx
0x180003748  retn
```
