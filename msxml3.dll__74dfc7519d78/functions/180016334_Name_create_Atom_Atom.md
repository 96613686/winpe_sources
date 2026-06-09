# Name::create(Atom *,Atom *)

- ea: `0x180016334`
- end: `0x180016697`
- name: `?create@Name@@SAPEAV1@PEAVAtom@@0@Z`
- size: `867`
- prototype: `struct Name *__fastcall(struct Atom *, struct Atom *)`
- caller_count: `23`
- callee_count: `15`
- tags: ``

## callers

- `0x18000de70`
- `0x18000ee74`
- `0x18001434c`
- `0x180015bbc`
- `0x180016a80`
- `0x1800181a0`
- `0x180018b60`
- `0x180019d60`
- `0x18002454c`
- `0x18003360c`
- `0x180033984`
- `0x180033ef0`
- `0x18003414c`
- `0x1800391f4`
- `0x18003d35c`
- `0x18003fa50`
- `0x18004bfd4`
- `0x18004c6f8`
- `0x180053c34`
- `0x180083748`
- `0x1800ec7c4`
- `0x1800ff0b0`
- `0x1800ff120`

## callees

- `0x180012000`
- `0x180016334`
- `0x180018940`
- `0x18001b690`
- `0x18001c310`
- `0x180021df8`
- `0x18003a2f4`
- `0x18004a948`
- `0x18004b488`
- `0x18004b50c`
- `0x180051928`
- `0x18005e9e8`
- `0x1800607e0`
- `0x180064034`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800165a7`
- `msvcrt!_resetstkoflw` at `0x1800165a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001654b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001654b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800165fa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800165fa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001635f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001636e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001647c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180016595`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001635f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001636e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001647c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180016595`

## pseudocode

```c
struct Name *__fastcall Name::create(struct Atom *a1, struct Atom *a2)
{
  LPVOID Value; // r14
  unsigned int v5; // edx
  _DWORD *v6; // rsi
  int v7; // r15d
  ShareMutex *v8; // rbx
  int v9; // ecx
  void *v10; // rcx
  struct IUnknown *v11; // rax
  __int64 v12; // rbx
  void *v13; // rcx
  struct String *v14; // r13
  Name *v15; // rax
  Name *v16; // rbx
  struct IUnknown **v17; // rdi
  __int64 v18; // r9
  ShareMutex *v19; // rbx
  unsigned __int16 Src[8]; // [rsp+40h] [rbp-38h] BYREF

  Value = TlsGetValue(g_dwTlsIndex);
  v6 = TlsGetValue(g_dwTlsIndex);
  v7 = v6[19];
  v6[19] = 1;
  *(_QWORD *)Src = a1;
  *(_QWORD *)&Src[4] = a2;
  v8 = g_pMutexName;
  if ( *((LPVOID *)g_pMutexName + 7) == Value )
  {
    _InterlockedAdd((volatile signed __int32 *)g_pMutexName + 8, 1u);
  }
  else
  {
    v9 = _InterlockedIncrement((volatile signed __int32 *)g_pMutexName + 8);
    if ( *((int *)v8 + 9) <= 0 && v9 <= 256 || (unsigned int)ShareMutex::WaitForShareLock(v8) )
    {
      v10 = (void *)*((_QWORD *)v8 + 6);
      if ( v10 )
        CaptureStackContext(v10, v5);
    }
  }
  v11 = StringHashtable::get(Name::s_pNames, Src, 8);
  v12 = (__int64)v11;
  if ( v11 )
    LODWORD(v11[3].lpVtbl) = Base::s_ulGCCycle;
  (*(void (__fastcall **)(ShareMutex *))(*(_QWORD *)g_pMutexName + 48LL))(g_pMutexName);
  if ( !v12 )
  {
    v14 = ArrayString::newString(Src, 8);
    if ( g_fUseMpHeap )
      v15 = (Name *)MpHeapAlloc(v13, 0x2000000Cu, 0x38u);
    else
      v15 = (Name *)HeapAlloc(g_hProcessHeap, 0x2000000Cu, 0x38u);
    v16 = v15;
    if ( !v15 )
    {
      failure_tracing::record();
      Exception::throw_E_OUTOFMEMORY();
    }
    *((_QWORD *)v15 + 1) = (-(__int64)(*((_DWORD *)TlsGetValue(g_dwTlsIndex) + 19) != 0) & 0xFFFFFFFFFFFFFFFBuLL) + 4;
    v17 = (struct IUnknown **)Name::Name(v16, a1, a2, v14);
    v19 = g_pMutexName;
    if ( *((LPVOID *)g_pMutexName + 7) == Value )
    {
      _InterlockedIncrement((volatile signed __int32 *)g_pMutexName + 9);
      _InterlockedIncrement((volatile signed __int32 *)v19 + 8);
    }
    else
    {
      ShareMutex::ClaimExclusiveLock(g_pMutexName);
      *((_QWORD *)v19 + 7) = Value;
    }
    ++*((_DWORD *)v19 + 16);
    LOBYTE(v18) = 1;
    v12 = (*(__int64 (__fastcall **)(StringHashtable *, struct String *, struct IUnknown **, __int64))(*(_QWORD *)Name::s_pNames + 128LL))(
            Name::s_pNames,
            v14,
            v17,
            v18);
    *(_DWORD *)(v12 + 24) = Base::s_ulGCCycle;
    (*(void (__fastcall **)(ShareMutex *))(*(_QWORD *)g_pMutexName + 32LL))(g_pMutexName);
    if ( (struct IUnknown **)v12 != v17 )
    {
      assign(v17 + 6, 0);
      HashtableBase::addToDeadList((HashtableBase *)v17);
    }
  }
  v6[19] = v7;
  return (struct Name *)v12;
}

```

## disassembly

```asm
0x180016334  mov     [rsp+arg_0], rbx
0x180016339  mov     [rsp+arg_8], rsi
0x18001633e  push    rdi
0x18001633f  push    r12
0x180016341  push    r13
0x180016343  push    r14
0x180016345  push    r15
0x180016347  sub     rsp, 50h
0x18001634b  mov     rdi, rdx
0x18001634e  mov     r12, rcx
0x180016351  mov     [rsp+78h+var_48], 0
0x180016359  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18001635f  call    cs:__imp_TlsGetValue
0x180016365  mov     r14, rax
0x180016368  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18001636e  call    cs:__imp_TlsGetValue
0x180016374  mov     rsi, rax
0x180016377  mov     [rsp+78h+arg_18], rax
0x18001637f  mov     r15d, [rax+4Ch]
0x180016383  mov     [rsp+78h+arg_10], r15d
0x18001638b  mov     r13d, 1
0x180016391  mov     [rax+4Ch], r13d
0x180016395  xorps   xmm0, xmm0
0x180016398  movups  xmmword ptr [rsp+78h+Src], xmm0
0x18001639d  mov     qword ptr [rsp+78h+Src], r12
0x1800163a2  mov     qword ptr [rsp+78h+Src+8], rdi
0x1800163a7  mov     rbx, cs:?g_pMutexName@@3PEAVApartmentMutex@@EA; ApartmentMutex * g_pMutexName
0x1800163ae  cmp     [rbx+38h], r14
0x1800163b2  jz      loc_180016556
0x1800163b8  mov     ecx, r13d
0x1800163bb  lock xadd [rbx+20h], ecx
0x1800163c0  add     ecx, r13d
0x1800163c3  mov     eax, [rbx+24h]
0x1800163c6  test    eax, eax
0x1800163c8  jg      loc_18001652F
0x1800163ce  cmp     ecx, 100h
0x1800163d4  jg      loc_18001652F
0x1800163da  mov     rcx, [rbx+30h]; void *
0x1800163de  test    rcx, rcx
0x1800163e1  jnz     loc_180016560
0x1800163e7  mov     [rsp+78h+var_48], r13d
0x1800163ec  mov     r13d, 8
0x1800163f2  mov     r8d, r13d; int
0x1800163f5  lea     rdx, [rsp+78h+Src]; unsigned __int16 *
0x1800163fa  mov     rcx, cs:?s_pNames@Name@@1PEAVStringHashtable@@EA; this
0x180016401  call    ?get@StringHashtable@@QEAAPEAUIUnknown@@PEBGH@Z; StringHashtable::get(ushort const *,int)
0x180016406  mov     rbx, rax
0x180016409  mov     [rsp+78h+var_40], rax
0x18001640e  test    rax, rax
0x180016411  jz      short loc_18001641C
0x180016413  mov     ecx, cs:?s_ulGCCycle@Base@@0KA; ulong Base::s_ulGCCycle
0x180016419  mov     [rax+18h], ecx
0x18001641c  mov     rcx, cs:?g_pMutexName@@3PEAVApartmentMutex@@EA; ApartmentMutex * g_pMutexName
0x180016423  mov     r8, [rcx]
0x180016426  mov     rax, [r8+30h]
0x18001642a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001642f  mov     [rsp+78h+var_48], 0
0x180016437  test    rbx, rbx
0x18001643a  jnz     loc_18001658A
0x180016440  mov     edx, r13d; int
0x180016443  lea     rcx, [rsp+78h+Src]; Src
0x180016448  call    ?newString@ArrayString@@SAPEAV1@PEBGH@Z; ArrayString::newString(ushort const *,int)
0x18001644d  mov     r13, rax
0x180016450  mov     edx, 2000000Ch; dwFlags
0x180016455  lea     r8d, [rbx+38h]; dwBytes
0x180016459  cmp     cs:g_fUseMpHeap, ebx
0x18001645f  jz      loc_180016544
0x180016465  call    ?MpHeapAlloc@@YAPEAXPEAXK_K@Z; MpHeapAlloc(void *,ulong,unsigned __int64)
0x18001646a  mov     rbx, rax
0x18001646d  test    rax, rax
0x180016470  jz      loc_18001656A
0x180016476  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x18001647c  call    cs:__imp_TlsGetValue
0x180016482  mov     ecx, [rax+4Ch]
0x180016485  neg     ecx
0x180016487  sbb     rax, rax
0x18001648a  and     rax, 0FFFFFFFFFFFFFFFBh
0x18001648e  add     rax, 4
0x180016492  mov     [rbx+8], rax
0x180016496  mov     r9, r13; struct String *
0x180016499  mov     r8, rdi; struct Atom *
0x18001649c  mov     rdx, r12; struct Atom *
0x18001649f  mov     rcx, rbx; this
0x1800164a2  call    ??0Name@@AEAA@PEAVAtom@@0PEAVString@@@Z; Name::Name(Atom *,Atom *,String *)
0x1800164a7  mov     rdi, rax
0x1800164aa  mov     [rsp+78h+var_40], rax
0x1800164af  mov     rbx, cs:?g_pMutexName@@3PEAVApartmentMutex@@EA; ApartmentMutex * g_pMutexName
0x1800164b6  cmp     [rbx+38h], r14
0x1800164ba  jz      short loc_180016525
0x1800164bc  mov     rcx, rbx; this
0x1800164bf  call    ?ClaimExclusiveLock@ShareMutex@@IEAAHXZ; ShareMutex::ClaimExclusiveLock(void)
0x1800164c4  mov     [rbx+38h], r14
0x1800164c8  inc     dword ptr [rbx+40h]
0x1800164cb  mov     [rsp+78h+var_48], 2
0x1800164d3  mov     rcx, cs:?s_pNames@Name@@1PEAVStringHashtable@@EA; StringHashtable * Name::s_pNames
0x1800164da  mov     rax, [rcx]
0x1800164dd  mov     r9b, 1
0x1800164e0  mov     r8, rdi
0x1800164e3  mov     rdx, r13
0x1800164e6  mov     rax, [rax+80h]
0x1800164ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164f2  mov     rbx, rax
0x1800164f5  mov     eax, cs:?s_ulGCCycle@Base@@0KA; ulong Base::s_ulGCCycle
0x1800164fb  mov     [rbx+18h], eax
0x1800164fe  mov     rcx, cs:?g_pMutexName@@3PEAVApartmentMutex@@EA; ApartmentMutex * g_pMutexName
0x180016505  mov     rax, [rcx]
0x180016508  mov     rax, [rax+20h]
0x18001650c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016511  mov     [rsp+78h+var_48], 0
0x180016519  cmp     rbx, rdi
0x18001651c  jnz     short loc_180016575
0x18001651e  mov     [rsp+78h+var_40], rbx
0x180016523  jmp     short loc_18001658A
0x180016525  lock inc dword ptr [rbx+24h]
0x180016529  lock inc dword ptr [rbx+20h]
0x18001652d  jmp     short loc_1800164C8
0x18001652f  mov     rcx, rbx; this
0x180016532  call    ?WaitForShareLock@ShareMutex@@IEAAHXZ; ShareMutex::WaitForShareLock(void)
0x180016537  test    eax, eax
0x180016539  jz      loc_1800163E7
0x18001653f  jmp     loc_1800163DA
0x180016544  mov     rcx, cs:g_hProcessHeap; hHeap
0x18001654b  call    cs:__imp_HeapAlloc
0x180016551  jmp     loc_18001646A
0x180016556  lock add [rbx+20h], r13d
0x18001655b  jmp     loc_1800163E7
0x180016560  call    ?CaptureStackContext@@YAXPEA_KK@Z; CaptureStackContext(unsigned __int64 *,ulong)
0x180016565  jmp     loc_1800163E7
0x18001656a  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x18001656f  call    ?throw_E_OUTOFMEMORY@Exception@@SAXXZ; Exception::throw_E_OUTOFMEMORY(void)
0x180016575  lea     rcx, [rdi+30h]; struct IUnknown **
0x180016579  xor     edx, edx; void *
0x18001657b  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180016580  mov     rcx, rdi; this
0x180016583  call    ?addToDeadList@HashtableBase@@IEAAXXZ; HashtableBase::addToDeadList(void)
0x180016588  jmp     short loc_18001651E
0x18001658a  jmp     loc_180016676
0x18001658f  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180016595  call    cs:__imp_TlsGetValue
0x18001659b  mov     rbx, rax
0x18001659e  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800165a5  jnz     short loc_180016620
0x1800165a7  call    cs:__imp__resetstkoflw
0x1800165ad  test    eax, eax
0x1800165af  jnz     short loc_180016602
0x1800165b1  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800165b8  test    rcx, rcx
0x1800165bb  jz      short loc_1800165CF
0x1800165bd  cmp     [rcx+50h], rbx
0x1800165c1  jnz     short loc_1800165CF
0x1800165c3  mov     rax, [rcx]
0x1800165c6  mov     rax, [rax+20h]
0x1800165ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165cf  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x1800165d6  test    rcx, rcx
0x1800165d9  jz      short loc_1800165ED
0x1800165db  cmp     [rcx+50h], rbx
0x1800165df  jnz     short loc_1800165ED
0x1800165e1  mov     rax, [rcx]
0x1800165e4  mov     rax, [rax+20h]
0x1800165e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165ed  xor     r9d, r9d; lpArguments
0x1800165f0  xor     r8d, r8d; nNumberOfArguments
0x1800165f3  xor     edx, edx; dwExceptionFlags
0x1800165f5  mov     ecx, 0C00000FDh; dwExceptionCode
0x1800165fa  call    cs:__imp_RaiseException
0x180016600  jmp     short loc_180016620
0x180016602  mov     rax, [rbx+60h]
0x180016606  mov     [rbx+68h], rax
0x18001660a  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x180016611  mov     [rbx+60h], rax
0x180016615  mov     dword ptr [rbx+54h], 800703E9h
0x18001661c  mov     byte ptr [rbx+78h], 0
0x180016620  mov     rcx, [rsp+78h+arg_18]
0x180016628  mov     eax, [rsp+78h+arg_10]
0x18001662f  mov     [rcx+4Ch], eax
0x180016632  mov     eax, [rsp+78h+var_48]
0x180016636  cmp     eax, 3
0x180016639  jnz     short loc_18001664B
0x18001663b  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180016642  mov     rax, [rcx]
0x180016645  mov     rax, [rax+20h]
0x180016649  jmp     short loc_18001666B
0x18001664b  cmp     eax, 2
0x18001664e  jnz     short loc_180016659
0x180016650  mov     rcx, cs:?g_pMutexName@@3PEAVApartmentMutex@@EA; ApartmentMutex * g_pMutexName
0x180016657  jmp     short loc_180016642
0x180016659  test    eax, eax
0x18001665b  jz      short loc_180016670
0x18001665d  mov     rcx, cs:?g_pMutexName@@3PEAVApartmentMutex@@EA; ApartmentMutex * g_pMutexName
0x180016664  mov     rax, [rcx]
0x180016667  mov     rax, [rax+30h]
0x18001666b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016670  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x180016676  mov     [rsi+4Ch], r15d
0x18001667a  mov     rax, rbx
0x18001667d  lea     r11, [rsp+78h+var_28]
0x180016682  mov     rbx, [r11+30h]
0x180016686  mov     rsi, [r11+38h]
0x18001668a  mov     rsp, r11
0x18001668d  pop     r15
0x18001668f  pop     r14
0x180016691  pop     r13
0x180016693  pop     r12
0x180016695  pop     rdi
0x180016696  retn
0x180103076  push    rbp
0x180103078  sub     rsp, 30h
0x18010307c  mov     rbp, rdx
0x18010307f  xor     edx, edx; bool
0x180103081  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z; Exception::fillException(_EXCEPTION_POINTERS *,bool)
0x180103086  nop
0x180103087  add     rsp, 30h
0x18010308b  pop     rbp
0x18010308c  retn
```
