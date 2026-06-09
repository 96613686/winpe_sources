# _GetGlobalSchemaCache(ISchemaCache * *)

- ea: `0x180031280`
- end: `0x180031622`
- name: `?_GetGlobalSchemaCache@@YAJPEAPEAUISchemaCache@@@Z`
- size: `930`
- prototype: `__int64 __fastcall(struct ISchemaCache **)`
- caller_count: `14`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002f3e0`
- `0x18002fa10`
- `0x18002fb20`
- `0x180030130`
- `0x180030610`
- `0x1800309c0`
- `0x180030ac0`
- `0x180030d60`
- `0x180030eb0`
- `0x1800881e0`
- `0x180088270`
- `0x18009123c`
- `0x1800912e4`
- `0x180091378`

## callees

- `0x1800059cc`
- `0x1800062b0`
- `0x18001d514`
- `0x18002e164`
- `0x18002e200`
- `0x180031280`
- `0x18006bb14`
- `0x18006f1fc`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800315e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800315e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031395`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003148a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031497`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800315fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031612`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031395`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003148a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031497`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800315fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031612`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800312bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003143a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800312bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003143a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180031593`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180031593`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003132c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003132c`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180031428`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180031428`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180031404`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180031404`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800312ae`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800312ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800314f4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800314f4`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800312d5`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800312d5`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180031574`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180031574`

## pseudocode

```c
__int64 __fastcall _GetGlobalSchemaCache(struct ISchemaCache **a1)
{
  HRESULT ApartmentType; // ebx
  DWORD v3; // r15d
  volatile signed __int32 *Value; // rax
  volatile signed __int32 *v5; // rsi
  __int64 (__fastcall ***v6)(_QWORD, GUID *, struct ISchemaCache **); // rcx
  unsigned int v8; // esi
  LPVOID v9; // rcx
  DWORD v10; // ecx
  struct IUnknown *v11; // rcx
  struct IUnknown *v12; // rbx
  CCachedSTAObject *v13; // rax
  CCachedSTAObject *v14; // rax
  CCachedSTAObject *v15; // r13
  APTTYPE pAptType; // [rsp+70h] [rbp+8h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+78h] [rbp+10h] BYREF

  *a1 = 0;
  InitOnceExecuteOnce(&stru_1800F0EF0, _lambda_c12b5e827bbdb1597ce6a3af58750a50_::_lambda_invoker_cdecl_, &Parameter, 0);
  EnterCriticalSection(&Parameter);
  pAptType = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, &pAptQualifier);
  if ( ApartmentType < 0 )
    goto LABEL_11;
  switch ( pAptType )
  {
    case APTTYPE_STA:
      goto LABEL_3;
    case APTTYPE_MTA:
      v8 = dword_1800F0EE4;
      *a1 = 0;
      ApartmentType = 1;
      if ( !v8 )
        goto LABEL_11;
      v9 = g_pgit;
      if ( g_pgit )
      {
LABEL_16:
        ApartmentType = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, struct ISchemaCache **))(*(_QWORD *)v9 + 40LL))(
                          v9,
                          v8,
                          &GUID_e585ec73_e223_483c_80c9_fede58f5291e,
                          a1);
        if ( ApartmentType < 0 )
          ApartmentType = 1;
LABEL_11:
        LeaveCriticalSection(&Parameter);
        if ( ApartmentType != 1 )
          return (unsigned int)ApartmentType;
        EnterCriticalSection(&g_csDll);
        v11 = g_pSchemaCache;
        if ( g_pSchemaCache )
        {
          *a1 = (struct ISchemaCache *)g_pSchemaCache;
          ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->AddRef)(v11);
          v12 = g_pSchemaCache;
        }
        else
        {
          ApartmentType = CSchemaCache_CreateInstance(0, (void **)a1);
          if ( ApartmentType < 0 )
            goto LABEL_25;
          v12 = (struct IUnknown *)*a1;
          g_pSchemaCache = (struct IUnknown *)*a1;
        }
        CApartmentLocalObject::_EnterCriticalSection((CApartmentLocalObject *)&g_aloSchemaCache);
        ApartmentType = CApartmentLocalObject::_SetApartmentObject((CApartmentLocalObject *)&g_aloSchemaCache, v12);
        LeaveCriticalSection(&Parameter);
LABEL_25:
        LeaveCriticalSection(&g_csDll);
        return (unsigned int)ApartmentType;
      }
LABEL_29:
      ApartmentType = CoCreateInstance(
                        &CLSID_StdGlobalInterfaceTable,
                        0,
                        1u,
                        &GUID_00000146_0000_0000_c000_000000000046,
                        &g_pgit);
      if ( ApartmentType < 0 )
        goto LABEL_11;
      v9 = g_pgit;
      goto LABEL_16;
    case APTTYPE_NA:
      v8 = dword_1800F0EE8;
      *a1 = 0;
      ApartmentType = 1;
      if ( !v8 )
        goto LABEL_11;
      v9 = g_pgit;
      if ( g_pgit )
        goto LABEL_16;
      goto LABEL_29;
  }
  if ( pAptType != APTTYPE_MAINSTA )
  {
    LeaveCriticalSection(&Parameter);
    return 2147746288LL;
  }
LABEL_3:
  if ( g_aloSchemaCache != -1 )
    goto LABEL_4;
  v10 = TlsAlloc();
  if ( v10 != -1 )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_aloSchemaCache, v10, -1) != -1 )
      TlsFree(v10);
LABEL_4:
    v3 = g_aloSchemaCache;
    ApartmentType = 1;
    *a1 = 0;
    if ( v3 == -1 )
      goto LABEL_11;
    Value = (volatile signed __int32 *)TlsGetValue(v3);
    v5 = Value;
    if ( Value )
    {
      if ( *((_DWORD *)Value + 10) )
      {
        _InterlockedIncrement(Value + 2);
        *a1 = 0;
        v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct ISchemaCache **))*((_QWORD *)Value + 4);
        if ( v6 )
          ApartmentType = (**v6)(v6, &GUID_e585ec73_e223_483c_80c9_fede58f5291e, a1);
        else
          ApartmentType = 1;
LABEL_9:
        if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
          operator delete((void *)v5, (const struct std::nothrow_t *)0x30);
        goto LABEL_11;
      }
    }
    else
    {
      v13 = (CCachedSTAObject *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
      if ( v13 )
      {
        v14 = CCachedSTAObject::CCachedSTAObject(v13);
        v15 = v14;
        if ( v14 )
        {
          *((_DWORD *)v14 + 6) = v3;
          ApartmentType = CoRegisterInitializeSpy((IInitializeSpy *)v14, (ULARGE_INTEGER *)v14 + 2);
          if ( ApartmentType < 0 )
          {
            v5 = 0;
          }
          else
          {
            *((_DWORD *)v15 + 10) = 1;
            if ( !*(_QWORD *)&CCachedSTAObject::s_hmod )
              GetModuleHandleExW(4u, &CCachedSTAObject::s_hmod, (HMODULE *)&CCachedSTAObject::s_hmod);
            TlsSetValue(v3, v15);
            v5 = (volatile signed __int32 *)v15;
            _InterlockedIncrement((volatile signed __int32 *)v15 + 2);
            ApartmentType = 1;
          }
          CCachedSTAObject::Release(v15);
          if ( ApartmentType >= 0 )
            goto LABEL_9;
        }
      }
    }
    ApartmentType = 1;
    goto LABEL_11;
  }
  LeaveCriticalSection(&Parameter);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180031280  push    rbx
0x180031282  push    rbp
0x180031283  push    rsi
0x180031284  push    rdi
0x180031285  push    r12
0x180031287  push    r14
0x180031289  sub     rsp, 38h
0x18003128d  mov     rdi, rcx
0x180031290  lea     r8, Parameter; Parameter
0x180031297  xor     r12d, r12d
0x18003129a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c12b5e827bbdb1597ce6a3af58750a50_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800312a1  mov     [rcx], r12
0x1800312a4  xor     r9d, r9d; Context
0x1800312a7  lea     rcx, stru_1800F0EF0; InitOnce
0x1800312ae  call    cs:__imp_InitOnceExecuteOnce
0x1800312b4  lea     rcx, Parameter; lpCriticalSection
0x1800312bb  call    cs:__imp_EnterCriticalSection
0x1800312c1  lea     rdx, [rsp+68h+pAptQualifier]; pAptQualifier
0x1800312c6  mov     [rsp+68h+pAptType], r12d
0x1800312cb  lea     rcx, [rsp+68h+pAptType]; pAptType
0x1800312d0  mov     [rsp+68h+pAptQualifier], r12d
0x1800312d5  call    cs:__imp_CoGetApartmentType
0x1800312db  mov     ebx, eax
0x1800312dd  test    eax, eax
0x1800312df  js      loc_18003138E
0x1800312e5  mov     edx, [rsp+68h+pAptType]
0x1800312e9  test    edx, edx
0x1800312eb  jnz     loc_1800313B3
0x1800312f1  cmp     cs:?g_aloSchemaCache@@3VCApartmentLocalObject@@A, 0FFFFFFFFh; CApartmentLocalObject g_aloSchemaCache
0x1800312f8  mov     ebp, 0FFFFFFFFh
0x1800312fd  jz      loc_180031404
0x180031303  mov     [rsp+68h+var_38], r15
0x180031308  mov     r14d, 1
0x18003130e  mov     r15d, cs:?g_aloSchemaCache@@3VCApartmentLocalObject@@A; CApartmentLocalObject g_aloSchemaCache
0x180031315  mov     ebx, r14d
0x180031318  mov     [rdi], r12
0x18003131b  cmp     r15d, 0FFFFFFFFh
0x18003131f  jz      short loc_180031389
0x180031321  mov     ecx, r15d; dwTlsIndex
0x180031324  mov     [rsp+68h+arg_10], r13
0x18003132c  call    cs:__imp_TlsGetValue
0x180031332  mov     rsi, rax
0x180031335  test    rax, rax
0x180031338  jz      loc_180031543
0x18003133e  cmp     [rax+28h], r12d
0x180031342  jz      loc_1800315C8
0x180031348  lock inc dword ptr [rax+8]
0x18003134c  mov     [rdi], r12
0x18003134f  mov     rcx, [rsi+20h]
0x180031353  test    rcx, rcx
0x180031356  jz      loc_1800315BB
0x18003135c  mov     rax, [rcx]
0x18003135f  lea     rdx, _GUID_e585ec73_e223_483c_80c9_fede58f5291e
0x180031366  mov     r8, rdi
0x180031369  mov     rax, [rax]
0x18003136c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031371  mov     ebx, eax
0x180031373  lock xadd [rsi+8], ebp
0x180031378  cmp     ebp, r14d
0x18003137b  jz      loc_180031510
0x180031381  mov     r13, [rsp+68h+arg_10]
0x180031389  mov     r15, [rsp+68h+var_38]
0x18003138e  lea     rcx, Parameter; lpCriticalSection
0x180031395  call    cs:__imp_LeaveCriticalSection
0x18003139b  cmp     ebx, 1
0x18003139e  jz      loc_180031433
0x1800313a4  mov     eax, ebx
0x1800313a6  add     rsp, 38h
0x1800313aa  pop     r14
0x1800313ac  pop     r12
0x1800313ae  pop     rdi
0x1800313af  pop     rsi
0x1800313b0  pop     rbp
0x1800313b1  pop     rbx
0x1800313b2  retn
0x1800313b3  sub     edx, 1
0x1800313b6  jnz     loc_1800314A2
0x1800313bc  mov     esi, cs:dword_1800F0EE4
0x1800313c2  mov     r14d, 1
0x1800313c8  mov     [rdi], r12
0x1800313cb  mov     ebx, r14d
0x1800313ce  test    esi, esi
0x1800313d0  jz      short loc_18003138E
0x1800313d2  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x1800313d9  test    rcx, rcx
0x1800313dc  jz      loc_1800314D5
0x1800313e2  mov     rax, [rcx]
0x1800313e5  lea     r8, _GUID_e585ec73_e223_483c_80c9_fede58f5291e
0x1800313ec  mov     r9, rdi
0x1800313ef  mov     edx, esi
0x1800313f1  mov     rax, [rax+28h]
0x1800313f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313fa  test    eax, eax
0x1800313fc  mov     ebx, eax
0x1800313fe  cmovs   ebx, r14d
0x180031402  jmp     short loc_18003138E
0x180031404  call    cs:__imp_TlsAlloc
0x18003140a  mov     ecx, eax; dwTlsIndex
0x18003140c  cmp     eax, 0FFFFFFFFh
0x18003140f  jz      loc_18003160B
0x180031415  mov     eax, ebp
0x180031417  lock cmpxchg cs:?g_aloSchemaCache@@3VCApartmentLocalObject@@A, ecx; CApartmentLocalObject g_aloSchemaCache
0x18003141f  cmp     eax, 0FFFFFFFFh
0x180031422  jz      loc_180031303
0x180031428  call    cs:__imp_TlsFree
0x18003142e  jmp     loc_180031303
0x180031433  lea     rcx, g_csDll; lpCriticalSection
0x18003143a  call    cs:__imp_EnterCriticalSection
0x180031440  mov     rcx, cs:?g_pSchemaCache@@3PEAUISchemaCache@@EA; struct _GUID *
0x180031447  test    rcx, rcx
0x18003144a  jz      loc_180031522
0x180031450  mov     [rdi], rcx
0x180031453  mov     rax, [rcx]
0x180031456  mov     rax, [rax+8]
0x18003145a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003145f  mov     rbx, cs:?g_pSchemaCache@@3PEAUISchemaCache@@EA; ISchemaCache * g_pSchemaCache
0x180031466  lea     rcx, ?g_aloSchemaCache@@3VCApartmentLocalObject@@A; this
0x18003146d  call    ?_EnterCriticalSection@CApartmentLocalObject@@AEAAXXZ; CApartmentLocalObject::_EnterCriticalSection(void)
0x180031472  mov     rdx, rbx; struct IUnknown *
0x180031475  lea     rcx, ?g_aloSchemaCache@@3VCApartmentLocalObject@@A; this
0x18003147c  call    ?_SetApartmentObject@CApartmentLocalObject@@AEAAJPEAUIUnknown@@@Z; CApartmentLocalObject::_SetApartmentObject(IUnknown *)
0x180031481  lea     rcx, Parameter; lpCriticalSection
0x180031488  mov     ebx, eax
0x18003148a  call    cs:__imp_LeaveCriticalSection
0x180031490  lea     rcx, g_csDll; lpCriticalSection
0x180031497  call    cs:__imp_LeaveCriticalSection
0x18003149d  jmp     loc_1800313A4
0x1800314a2  sub     edx, 1
0x1800314a5  jnz     loc_1800315EB
0x1800314ab  mov     esi, cs:dword_1800F0EE8
0x1800314b1  mov     r14d, 1
0x1800314b7  mov     [rdi], r12
0x1800314ba  mov     ebx, r14d
0x1800314bd  test    esi, esi
0x1800314bf  jz      loc_18003138E
0x1800314c5  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x1800314cc  test    rcx, rcx
0x1800314cf  jnz     loc_1800313E2
0x1800314d5  lea     rax, ?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x1800314dc  mov     r8d, r14d; dwClsContext
0x1800314df  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800314e6  mov     [rsp+68h+ppv], rax; ppv
0x1800314eb  xor     edx, edx; pUnkOuter
0x1800314ed  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800314f4  call    cs:__imp_CoCreateInstance
0x1800314fa  mov     ebx, eax
0x1800314fc  test    eax, eax
0x1800314fe  js      loc_18003138E
0x180031504  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x18003150b  jmp     loc_1800313E2
0x180031510  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x180031515  mov     rcx, rsi; void *
0x180031518  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003151d  jmp     loc_180031381
0x180031522  mov     rdx, rdi; void **
0x180031525  call    ?CSchemaCache_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CSchemaCache_CreateInstance(_GUID const &,void * *)
0x18003152a  mov     ebx, eax
0x18003152c  test    eax, eax
0x18003152e  js      loc_180031490
0x180031534  mov     rbx, [rdi]
0x180031537  mov     cs:?g_pSchemaCache@@3PEAUISchemaCache@@EA, rbx; ISchemaCache * g_pSchemaCache
0x18003153e  jmp     loc_180031466
0x180031543  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003154a  mov     ecx, 30h ; '0'; unsigned __int64
0x18003154f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180031554  test    rax, rax
0x180031557  jz      short loc_1800315C8
0x180031559  mov     rcx, rax; this
0x18003155c  call    ??0CCachedSTAObject@@QEAA@XZ; CCachedSTAObject::CCachedSTAObject(void)
0x180031561  mov     r13, rax
0x180031564  test    rax, rax
0x180031567  jz      short loc_1800315C8
0x180031569  lea     rdx, [rax+10h]; puliCookie
0x18003156d  mov     [rax+18h], r15d
0x180031571  mov     rcx, rax; pSpy
0x180031574  call    cs:__imp_CoRegisterInitializeSpy
0x18003157a  mov     ebx, eax
0x18003157c  test    eax, eax
0x18003157e  js      short loc_1800315C3
0x180031580  mov     [r13+28h], r14d
0x180031584  cmp     cs:?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA, r12; HINSTANCE__ * CCachedSTAObject::s_hmod
0x18003158b  jz      short loc_1800315D0
0x18003158d  mov     rdx, r13; lpTlsValue
0x180031590  mov     ecx, r15d; dwTlsIndex
0x180031593  call    cs:__imp_TlsSetValue
0x180031599  mov     rsi, r13
0x18003159c  lock inc dword ptr [r13+8]
0x1800315a1  mov     ebx, r14d
0x1800315a4  mov     rcx, r13; this
0x1800315a7  call    ?Release@CCachedSTAObject@@UEAAKXZ; CCachedSTAObject::Release(void)
0x1800315ac  test    ebx, ebx
0x1800315ae  js      short loc_1800315C8
0x1800315b0  jz      loc_18003134C
0x1800315b6  jmp     loc_180031373
0x1800315bb  mov     ebx, r14d
0x1800315be  jmp     loc_180031373
0x1800315c3  mov     rsi, r12
0x1800315c6  jmp     short loc_1800315A4
0x1800315c8  mov     ebx, r14d
0x1800315cb  jmp     loc_180031381
0x1800315d0  lea     r8, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; phModule
0x1800315d7  mov     ecx, 4; dwFlags
0x1800315dc  lea     rdx, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; lpModuleName
0x1800315e3  call    cs:__imp_GetModuleHandleExW
0x1800315e9  jmp     short loc_18003158D
0x1800315eb  cmp     edx, 1
0x1800315ee  jz      loc_1800312F1
0x1800315f4  lea     rcx, Parameter; lpCriticalSection
0x1800315fb  call    cs:__imp_LeaveCriticalSection
0x180031601  mov     eax, 800401F0h
0x180031606  jmp     loc_1800313A6
0x18003160b  lea     rcx, Parameter; lpCriticalSection
0x180031612  call    cs:__imp_LeaveCriticalSection
0x180031618  mov     eax, 8007000Eh
0x18003161d  jmp     loc_1800313A6
```
