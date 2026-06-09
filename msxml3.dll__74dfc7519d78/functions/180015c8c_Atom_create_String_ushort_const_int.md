# Atom::create(String *,ushort const *,int)

- ea: `0x180015c8c`
- end: `0x180016072`
- name: `?create@Atom@@KAPEAV1@PEAVString@@PEBGH@Z`
- size: `998`
- prototype: `struct Atom *__fastcall(struct String *, const unsigned __int16 *Src, int)`
- caller_count: `31`
- callee_count: `17`
- tags: ``

## callers

- `0x18001434c`
- `0x180014670`
- `0x180014f44`
- `0x180015130`
- `0x1800156f0`
- `0x1800166a0`
- `0x1800169b0`
- `0x180016a80`
- `0x1800181a0`
- `0x180018b60`
- `0x180019d60`
- `0x1800241a8`
- `0x18002454c`
- `0x180031ff4`
- `0x18003360c`
- `0x180033984`
- `0x18003414c`
- `0x18003c0a8`
- `0x18003fa50`
- `0x18004882c`
- `0x18004bfd4`
- `0x18004c6f8`
- `0x18004f5f4`
- `0x1800689e0`
- `0x18006e800`
- `0x180095a44`
- `0x180096d80`
- `0x1800a6938`
- `0x1800ec928`
- `0x1800eccac`
- `0x1800fd9e4`

## callees

- `0x180012000`
- `0x180014214`
- `0x180015c8c`
- `0x180016078`
- `0x180018940`
- `0x18001c310`
- `0x180021d54`
- `0x1800251a4`
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

- `msvcrt!_resetstkoflw` at `0x180015f85`
- `msvcrt!_resetstkoflw` at `0x180015f85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015eef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015eef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015fd8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015fd8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015cba`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015cc9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015dd9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015f73`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015cba`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015cc9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015dd9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015f73`

## pseudocode

```c
struct IUnknown *__fastcall Atom::create(struct String *a1, const unsigned __int16 *Src, int a3)
{
  LPVOID Value; // r15
  struct IUnknown *v7; // r14
  int lpVtbl_high; // r13d
  unsigned int v9; // edx
  ShareMutex *v10; // rbx
  int v11; // ecx
  void *v12; // rcx
  struct IUnknown *v13; // rbx
  void *v14; // rcx
  struct String *v15; // rsi
  Atom *v16; // rax
  Atom *v17; // rbx
  int v18; // eax
  struct IUnknown **v19; // rdi
  __int64 v20; // r9
  ShareMutex *v21; // rbx
  const unsigned __int16 *v22; // rdx
  struct IUnknown *v24[2]; // [rsp+40h] [rbp-38h] BYREF

  Value = TlsGetValue(g_dwTlsIndex);
  v7 = (struct IUnknown *)TlsGetValue(g_dwTlsIndex);
  v24[1] = v7;
  lpVtbl_high = HIDWORD(v7[9].lpVtbl);
  v9 = 1;
  HIDWORD(v7[9].lpVtbl) = 1;
  v10 = g_pMutexAtom;
  if ( *((LPVOID *)g_pMutexAtom + 7) == Value )
  {
    _InterlockedAdd((volatile signed __int32 *)g_pMutexAtom + 8, 1u);
  }
  else
  {
    v11 = _InterlockedIncrement((volatile signed __int32 *)g_pMutexAtom + 8);
    if ( *((int *)v10 + 9) <= 0 && v11 <= 256 || (unsigned int)ShareMutex::WaitForShareLock(v10) )
    {
      v12 = (void *)*((_QWORD *)v10 + 6);
      if ( v12 )
        CaptureStackContext(v12, v9);
    }
  }
  if ( a1 )
  {
    v24[0] = 0;
    Hashtable::_get(Atom::atoms, a1, v24);
    v13 = v24[0];
  }
  else
  {
    v22 = Src;
    if ( !Src )
      v22 = &word_18012A048;
    v13 = StringHashtable::get(Atom::atoms, v22, a3);
  }
  if ( v13 )
    LODWORD(v13[3].lpVtbl) = Base::s_ulGCCycle;
  (*(void (__fastcall **)(ShareMutex *))(*(_QWORD *)g_pMutexAtom + 48LL))(g_pMutexAtom);
  if ( !v13 )
  {
    if ( a1 )
    {
      if ( (unsigned int)Base::model(a1) == 1 )
      {
        v15 = a1;
      }
      else
      {
        v15 = String::newString(*((const unsigned __int16 **)a1 + 3), *((_DWORD *)a1 + 4));
        (*(void (__fastcall **)(struct String *))(*(_QWORD *)a1 + 104LL))(a1);
      }
    }
    else
    {
      v15 = String::newString(Src, a3);
    }
    if ( g_fUseMpHeap )
      v16 = (Atom *)MpHeapAlloc(v14, 0x2000000Cu, 0x30u);
    else
      v16 = (Atom *)HeapAlloc(g_hProcessHeap, 0x2000000Cu, 0x30u);
    v17 = v16;
    if ( !v16 )
    {
      failure_tracing::record();
      Exception::throw_E_OUTOFMEMORY();
    }
    *((_QWORD *)v16 + 1) = (-(__int64)(*((_DWORD *)TlsGetValue(g_dwTlsIndex) + 19) != 0) & 0xFFFFFFFFFFFFFFFBuLL) + 4;
    v18 = (*(__int64 (__fastcall **)(struct String *))(*(_QWORD *)v15 + 64LL))(v15);
    v19 = (struct IUnknown **)Atom::Atom(v17, v15, v18);
    v21 = g_pMutexAtom;
    if ( *((LPVOID *)g_pMutexAtom + 7) == Value )
    {
      _InterlockedIncrement((volatile signed __int32 *)g_pMutexAtom + 9);
      _InterlockedIncrement((volatile signed __int32 *)v21 + 8);
    }
    else
    {
      ShareMutex::ClaimExclusiveLock(g_pMutexAtom);
      *((_QWORD *)v21 + 7) = Value;
    }
    ++*((_DWORD *)v21 + 16);
    LOBYTE(v20) = 1;
    v13 = (struct IUnknown *)(*(__int64 (__fastcall **)(Hashtable *, struct String *, struct IUnknown **, __int64))(*(_QWORD *)Atom::atoms + 128LL))(
                               Atom::atoms,
                               v15,
                               v19,
                               v20);
    LODWORD(v13[3].lpVtbl) = Base::s_ulGCCycle;
    (*(void (__fastcall **)(ShareMutex *))(*(_QWORD *)g_pMutexAtom + 32LL))(g_pMutexAtom);
    if ( v13 != (struct IUnknown *)v19 )
    {
      assign(v19 + 4, 0);
      HashtableBase::addToDeadList((HashtableBase *)v19);
    }
  }
  HIDWORD(v7[9].lpVtbl) = lpVtbl_high;
  return v13;
}

```

## disassembly

```asm
0x180015c8c  mov     [rsp+arg_0], rbx
0x180015c91  mov     [rsp+arg_8], rsi
0x180015c96  push    rdi
0x180015c97  push    r12
0x180015c99  push    r13
0x180015c9b  push    r14
0x180015c9d  push    r15
0x180015c9f  sub     rsp, 50h
0x180015ca3  mov     r12d, r8d
0x180015ca6  mov     rsi, rdx
0x180015ca9  mov     rdi, rcx
0x180015cac  mov     [rsp+78h+var_48], 0
0x180015cb4  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180015cba  call    cs:__imp_TlsGetValue
0x180015cc0  mov     r15, rax
0x180015cc3  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180015cc9  call    cs:__imp_TlsGetValue
0x180015ccf  mov     r14, rax
0x180015cd2  mov     [rsp+78h+var_30], rax
0x180015cd7  mov     r13d, [rax+4Ch]
0x180015cdb  mov     [rsp+78h+arg_18], r13d
0x180015ce3  mov     edx, 1; unsigned int
0x180015ce8  mov     [rax+4Ch], edx
0x180015ceb  mov     rbx, cs:?g_pMutexAtom@@3PEAVApartmentMutex@@EA; ApartmentMutex * g_pMutexAtom
0x180015cf2  cmp     [rbx+38h], r15
0x180015cf6  jz      loc_180015EFA
0x180015cfc  mov     ecx, edx
0x180015cfe  lock xadd [rbx+20h], ecx
0x180015d03  add     ecx, edx
0x180015d05  mov     eax, [rbx+24h]
0x180015d08  test    eax, eax
0x180015d0a  jg      loc_180015ED3
0x180015d10  cmp     ecx, 100h
0x180015d16  jg      loc_180015ED3
0x180015d1c  mov     rcx, [rbx+30h]; void *
0x180015d20  test    rcx, rcx
0x180015d23  jnz     loc_180015F03
0x180015d29  mov     [rsp+78h+var_48], 1
0x180015d31  test    rdi, rdi
0x180015d34  jz      loc_180015E99
0x180015d3a  mov     [rsp+78h+var_38], 0
0x180015d43  lea     r8, [rsp+78h+var_38]; struct IUnknown **
0x180015d48  mov     rdx, rdi; struct Object *
0x180015d4b  mov     rcx, cs:?atoms@Atom@@0PEAVStringHashtable@@EA; this
0x180015d52  call    ?_get@Hashtable@@IEAA_NPEAVObject@@PEAPEAUIUnknown@@@Z; Hashtable::_get(Object *,IUnknown * *)
0x180015d57  mov     rbx, [rsp+78h+var_38]
0x180015d5c  mov     [rsp+78h+var_40], rbx
0x180015d61  test    rbx, rbx
0x180015d64  jz      short loc_180015D6F
0x180015d66  mov     ecx, cs:?s_ulGCCycle@Base@@0KA; ulong Base::s_ulGCCycle
0x180015d6c  mov     [rbx+18h], ecx
0x180015d6f  mov     rcx, cs:?g_pMutexAtom@@3PEAVApartmentMutex@@EA; ApartmentMutex * g_pMutexAtom
0x180015d76  mov     rdx, [rcx]
0x180015d79  mov     rax, [rdx+30h]
0x180015d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d82  mov     [rsp+78h+var_48], 0
0x180015d8a  test    rbx, rbx
0x180015d8d  jnz     loc_180015F68
0x180015d93  test    rdi, rdi
0x180015d96  jnz     loc_180015F0D
0x180015d9c  mov     edx, r12d; int
0x180015d9f  mov     rcx, rsi; Src
0x180015da2  call    ?newString@String@@SAPEAV1@PEBGH@Z; String::newString(ushort const *,int)
0x180015da7  mov     rsi, rax
0x180015daa  mov     edx, 2000000Ch; dwFlags
0x180015daf  mov     r8d, 30h ; '0'; dwBytes
0x180015db5  cmp     cs:g_fUseMpHeap, 0
0x180015dbc  jz      loc_180015EE8
0x180015dc2  call    ?MpHeapAlloc@@YAPEAXPEAXK_K@Z; MpHeapAlloc(void *,ulong,unsigned __int64)
0x180015dc7  mov     rbx, rax
0x180015dca  test    rax, rax
0x180015dcd  jz      loc_180015F45
0x180015dd3  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180015dd9  call    cs:__imp_TlsGetValue
0x180015ddf  mov     ecx, [rax+4Ch]
0x180015de2  neg     ecx
0x180015de4  sbb     rax, rax
0x180015de7  and     rax, 0FFFFFFFFFFFFFFFBh
0x180015deb  add     rax, 4
0x180015def  mov     [rbx+8], rax
0x180015df3  mov     rax, [rsi]
0x180015df6  mov     rcx, rsi
0x180015df9  mov     rax, [rax+40h]
0x180015dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e02  mov     r8d, eax; int
0x180015e05  mov     rdx, rsi; struct String *
0x180015e08  mov     rcx, rbx; this
0x180015e0b  call    ??0Atom@@AEAA@PEAVString@@H@Z; Atom::Atom(String *,int)
0x180015e10  mov     rdi, rax
0x180015e13  mov     [rsp+78h+var_40], rax
0x180015e18  mov     rbx, cs:?g_pMutexAtom@@3PEAVApartmentMutex@@EA; ApartmentMutex * g_pMutexAtom
0x180015e1f  cmp     [rbx+38h], r15
0x180015e23  jz      loc_180015EC6
0x180015e29  mov     rcx, rbx; this
0x180015e2c  call    ?ClaimExclusiveLock@ShareMutex@@IEAAHXZ; ShareMutex::ClaimExclusiveLock(void)
0x180015e31  mov     [rbx+38h], r15
0x180015e35  inc     dword ptr [rbx+40h]
0x180015e38  mov     [rsp+78h+var_48], 2
0x180015e40  mov     rcx, cs:?atoms@Atom@@0PEAVStringHashtable@@EA; StringHashtable * Atom::atoms
0x180015e47  mov     rax, [rcx]
0x180015e4a  mov     r9b, 1
0x180015e4d  mov     r8, rdi
0x180015e50  mov     rdx, rsi
0x180015e53  mov     rax, [rax+80h]
0x180015e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e5f  mov     rbx, rax
0x180015e62  mov     eax, cs:?s_ulGCCycle@Base@@0KA; ulong Base::s_ulGCCycle
0x180015e68  mov     [rbx+18h], eax
0x180015e6b  mov     rcx, cs:?g_pMutexAtom@@3PEAVApartmentMutex@@EA; ApartmentMutex * g_pMutexAtom
0x180015e72  mov     rax, [rcx]
0x180015e75  mov     rax, [rax+20h]
0x180015e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e7e  mov     [rsp+78h+var_48], 0
0x180015e86  cmp     rbx, rdi
0x180015e89  jnz     loc_180015F50
0x180015e8f  mov     [rsp+78h+var_40], rbx
0x180015e94  jmp     loc_180015F68
0x180015e99  lea     rax, word_18012A048
0x180015ea0  mov     rdx, rsi
0x180015ea3  test    rsi, rsi
0x180015ea6  cmovz   rdx, rax; unsigned __int16 *
0x180015eaa  mov     r8d, r12d; int
0x180015ead  mov     rcx, cs:?atoms@Atom@@0PEAVStringHashtable@@EA; this
0x180015eb4  call    ?get@StringHashtable@@QEAAPEAUIUnknown@@PEBGH@Z; StringHashtable::get(ushort const *,int)
0x180015eb9  mov     rbx, rax
0x180015ebc  mov     [rsp+78h+var_40], rax
0x180015ec1  jmp     loc_180015D61
0x180015ec6  lock inc dword ptr [rbx+24h]
0x180015eca  lock inc dword ptr [rbx+20h]
0x180015ece  jmp     loc_180015E35
0x180015ed3  mov     rcx, rbx; this
0x180015ed6  call    ?WaitForShareLock@ShareMutex@@IEAAHXZ; ShareMutex::WaitForShareLock(void)
0x180015edb  test    eax, eax
0x180015edd  jz      loc_180015D29
0x180015ee3  jmp     loc_180015D1C
0x180015ee8  mov     rcx, cs:g_hProcessHeap; hHeap
0x180015eef  call    cs:__imp_HeapAlloc
0x180015ef5  jmp     loc_180015DC7
0x180015efa  lock add [rbx+20h], edx
0x180015efe  jmp     loc_180015D29
0x180015f03  call    ?CaptureStackContext@@YAXPEA_KK@Z; CaptureStackContext(unsigned __int64 *,ulong)
0x180015f08  jmp     loc_180015D29
0x180015f0d  mov     rcx, rdi
0x180015f10  call    ?model@Base@@QEAA?AW4RentalEnum@@XZ; Base::model(void)
0x180015f15  cmp     eax, 1
0x180015f18  jz      short loc_180015F3D
0x180015f1a  mov     edx, [rdi+10h]; int
0x180015f1d  mov     rcx, [rdi+18h]; Src
0x180015f21  call    ?newString@String@@SAPEAV1@PEBGH@Z; String::newString(ushort const *,int)
0x180015f26  mov     rsi, rax
0x180015f29  mov     rcx, [rdi]
0x180015f2c  mov     rax, [rcx+68h]
0x180015f30  mov     rcx, rdi
0x180015f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f38  jmp     loc_180015DAA
0x180015f3d  mov     rsi, rdi
0x180015f40  jmp     loc_180015DAA
0x180015f45  call    ?record@failure_tracing@@SAXXZ; failure_tracing::record(void)
0x180015f4a  call    ?throw_E_OUTOFMEMORY@Exception@@SAXXZ; Exception::throw_E_OUTOFMEMORY(void)
0x180015f50  lea     rcx, [rdi+20h]; struct IUnknown **
0x180015f54  xor     edx, edx; void *
0x180015f56  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180015f5b  mov     rcx, rdi; this
0x180015f5e  call    ?addToDeadList@HashtableBase@@IEAAXXZ; HashtableBase::addToDeadList(void)
0x180015f63  jmp     loc_180015E8F
0x180015f68  jmp     loc_180016051
0x180015f6d  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180015f73  call    cs:__imp_TlsGetValue
0x180015f79  mov     rbx, rax
0x180015f7c  cmp     dword ptr [rax+54h], 0C00000FDh
0x180015f83  jnz     short loc_180015FFE
0x180015f85  call    cs:__imp__resetstkoflw
0x180015f8b  test    eax, eax
0x180015f8d  jnz     short loc_180015FE0
0x180015f8f  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x180015f96  test    rcx, rcx
0x180015f99  jz      short loc_180015FAD
0x180015f9b  cmp     [rcx+50h], rbx
0x180015f9f  jnz     short loc_180015FAD
0x180015fa1  mov     rax, [rcx]
0x180015fa4  mov     rax, [rax+20h]
0x180015fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fad  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x180015fb4  test    rcx, rcx
0x180015fb7  jz      short loc_180015FCB
0x180015fb9  cmp     [rcx+50h], rbx
0x180015fbd  jnz     short loc_180015FCB
0x180015fbf  mov     rax, [rcx]
0x180015fc2  mov     rax, [rax+20h]
0x180015fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fcb  xor     r9d, r9d; lpArguments
0x180015fce  xor     r8d, r8d; nNumberOfArguments
0x180015fd1  xor     edx, edx; dwExceptionFlags
0x180015fd3  mov     ecx, 0C00000FDh; dwExceptionCode
0x180015fd8  call    cs:__imp_RaiseException
0x180015fde  jmp     short loc_180015FFE
0x180015fe0  mov     rax, [rbx+60h]
0x180015fe4  mov     [rbx+68h], rax
0x180015fe8  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x180015fef  mov     [rbx+60h], rax
0x180015ff3  mov     dword ptr [rbx+54h], 800703E9h
0x180015ffa  mov     byte ptr [rbx+78h], 0
0x180015ffe  mov     rcx, [rsp+78h+var_30]
0x180016003  mov     eax, [rsp+78h+arg_18]
0x18001600a  mov     [rcx+4Ch], eax
0x18001600d  mov     eax, [rsp+78h+var_48]
0x180016011  cmp     eax, 3
0x180016014  jnz     short loc_180016026
0x180016016  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x18001601d  mov     rax, [rcx]
0x180016020  mov     rax, [rax+20h]
0x180016024  jmp     short loc_180016046
0x180016026  cmp     eax, 2
0x180016029  jnz     short loc_180016034
0x18001602b  mov     rcx, cs:?g_pMutexAtom@@3PEAVApartmentMutex@@EA; ApartmentMutex * g_pMutexAtom
0x180016032  jmp     short loc_18001601D
0x180016034  test    eax, eax
0x180016036  jz      short loc_18001604B
0x180016038  mov     rcx, cs:?g_pMutexAtom@@3PEAVApartmentMutex@@EA; ApartmentMutex * g_pMutexAtom
0x18001603f  mov     rax, [rcx]
0x180016042  mov     rax, [rax+30h]
0x180016046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001604b  call    ?throwAgain@Exception@@SAXXZ; Exception::throwAgain(void)
0x180016051  mov     [r14+4Ch], r13d
0x180016055  mov     rax, rbx
0x180016058  lea     r11, [rsp+78h+var_28]
0x18001605d  mov     rbx, [r11+30h]
0x180016061  mov     rsi, [r11+38h]
0x180016065  mov     rsp, r11
0x180016068  pop     r15
0x18001606a  pop     r14
0x18001606c  pop     r13
0x18001606e  pop     r12
0x180016070  pop     rdi
0x180016071  retn
0x18010303a  push    rbp
0x18010303c  sub     rsp, 30h
0x180103040  mov     rbp, rdx
0x180103043  xor     edx, edx; bool
0x180103045  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z; Exception::fillException(_EXCEPTION_POINTERS *,bool)
0x18010304a  nop
0x18010304b  add     rsp, 30h
0x18010304f  pop     rbp
0x180103050  retn
```
