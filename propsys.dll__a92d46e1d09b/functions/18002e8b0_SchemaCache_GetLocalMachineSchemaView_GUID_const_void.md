# SchemaCache_GetLocalMachineSchemaView(_GUID const &,void * *)

- ea: `0x18002e8b0`
- end: `0x18002ecaf`
- name: `?SchemaCache_GetLocalMachineSchemaView@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `1023`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002e238`
- `0x18002e6e4`
- `0x18002e780`
- `0x18005cff4`
- `0x180067310`

## callees

- `0x1800059cc`
- `0x1800062b0`
- `0x18001d514`
- `0x18002e164`
- `0x18002e200`
- `0x18002e8b0`
- `0x18006bb14`
- `0x18006ed20`
- `0x18006f1fc`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002ec70`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002ec70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e9e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eb16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eb23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ec88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ec9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e9e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eb16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eb23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ec88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ec9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e901`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002eac4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e901`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002eac4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002ec24`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002ec24`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e970`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002e970`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18002eab2`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18002eab2`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18002ea8e`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18002ea8e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002e8f4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002e8f4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002eb80`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002eb80`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002e919`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002e919`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18002ec04`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18002ec04`

## pseudocode

```c
__int64 __fastcall SchemaCache_GetLocalMachineSchemaView(const struct _GUID *a1, void **a2)
{
  HRESULT ApartmentType; // ebx
  DWORD v5; // r15d
  volatile signed __int32 *Value; // rax
  volatile signed __int32 *v7; // rdi
  __int64 (__fastcall ***v8)(_QWORD, GUID *, void **); // rcx
  unsigned int v10; // edi
  LPVOID v11; // rcx
  DWORD v12; // ecx
  struct IUnknown *v13; // rbx
  CCachedSTAObject *v14; // rax
  CCachedSTAObject *v15; // rax
  CCachedSTAObject *v16; // r13
  APTTYPE pAptType; // [rsp+30h] [rbp-58h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+34h] [rbp-54h] BYREF
  void *v19; // [rsp+38h] [rbp-50h] BYREF

  *a2 = 0;
  v19 = 0;
  InitOnceExecuteOnce(&stru_1800F0EF0, _lambda_c12b5e827bbdb1597ce6a3af58750a50_::_lambda_invoker_cdecl_, &Parameter, 0);
  EnterCriticalSection(&Parameter);
  pAptType = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, &pAptQualifier);
  if ( ApartmentType < 0 )
    goto LABEL_11;
  if ( pAptType )
  {
    switch ( pAptType )
    {
      case APTTYPE_MTA:
        v10 = dword_1800F0EE4;
        v19 = 0;
        ApartmentType = 1;
        if ( !dword_1800F0EE4 )
          goto LABEL_11;
        v11 = g_pgit;
        if ( g_pgit )
          goto LABEL_18;
        break;
      case APTTYPE_NA:
        v10 = dword_1800F0EE8;
        v19 = 0;
        ApartmentType = 1;
        if ( !dword_1800F0EE8 )
          goto LABEL_11;
        v11 = g_pgit;
        if ( g_pgit )
        {
LABEL_18:
          ApartmentType = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, void **))(*(_QWORD *)v11 + 40LL))(
                            v11,
                            v10,
                            &GUID_e585ec73_e223_483c_80c9_fede58f5291e,
                            &v19);
          if ( ApartmentType < 0 )
            ApartmentType = 1;
          goto LABEL_11;
        }
        break;
      case APTTYPE_MAINSTA:
        goto LABEL_3;
      default:
        LeaveCriticalSection(&Parameter);
        return (unsigned int)-2147221008;
    }
    ApartmentType = CoCreateInstance(
                      &CLSID_StdGlobalInterfaceTable,
                      0,
                      1u,
                      &GUID_00000146_0000_0000_c000_000000000046,
                      &g_pgit);
    if ( ApartmentType < 0 )
      goto LABEL_11;
    v11 = g_pgit;
    goto LABEL_18;
  }
LABEL_3:
  if ( g_aloSchemaCache == -1 )
  {
    v12 = TlsAlloc();
    if ( v12 == -1 )
    {
      LeaveCriticalSection(&Parameter);
      return (unsigned int)-2147024882;
    }
    if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_aloSchemaCache, v12, -1) != -1 )
      TlsFree(v12);
  }
  v5 = g_aloSchemaCache;
  v19 = 0;
  ApartmentType = 1;
  if ( g_aloSchemaCache != -1 )
  {
    Value = (volatile signed __int32 *)TlsGetValue(g_aloSchemaCache);
    v7 = Value;
    if ( Value )
    {
      if ( *((_DWORD *)Value + 10) )
      {
        _InterlockedIncrement(Value + 2);
        v19 = 0;
        v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)Value + 4);
        if ( v8 )
          ApartmentType = (**v8)(v8, &GUID_e585ec73_e223_483c_80c9_fede58f5291e, &v19);
        else
          ApartmentType = 1;
LABEL_9:
        if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
          operator delete((void *)v7, (const struct std::nothrow_t *)0x30);
        goto LABEL_11;
      }
    }
    else
    {
      v14 = (CCachedSTAObject *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
      if ( v14 )
      {
        v15 = CCachedSTAObject::CCachedSTAObject(v14);
        v16 = v15;
        if ( v15 )
        {
          *((_DWORD *)v15 + 6) = v5;
          ApartmentType = CoRegisterInitializeSpy((IInitializeSpy *)v15, (ULARGE_INTEGER *)v15 + 2);
          if ( ApartmentType < 0 )
          {
            v7 = 0;
          }
          else
          {
            *((_DWORD *)v16 + 10) = 1;
            if ( !*(_QWORD *)&CCachedSTAObject::s_hmod )
              GetModuleHandleExW(4u, &CCachedSTAObject::s_hmod, (HMODULE *)&CCachedSTAObject::s_hmod);
            TlsSetValue(v5, v16);
            v7 = (volatile signed __int32 *)v16;
            _InterlockedIncrement((volatile signed __int32 *)v16 + 2);
            ApartmentType = 1;
          }
          CCachedSTAObject::Release(v16);
          if ( ApartmentType >= 0 )
            goto LABEL_9;
        }
      }
    }
    ApartmentType = 1;
  }
LABEL_11:
  LeaveCriticalSection(&Parameter);
  if ( ApartmentType != 1 )
    goto LABEL_12;
  EnterCriticalSection(&g_csDll);
  if ( g_pSchemaCache )
  {
    v19 = g_pSchemaCache;
    ((void (__fastcall *)(struct IUnknown *))g_pSchemaCache->lpVtbl->AddRef)(g_pSchemaCache);
    v13 = g_pSchemaCache;
  }
  else
  {
    ApartmentType = CSchemaCache_CreateInstance(0, &v19);
    if ( ApartmentType < 0 )
      goto LABEL_27;
    v13 = (struct IUnknown *)v19;
    g_pSchemaCache = (struct IUnknown *)v19;
  }
  CApartmentLocalObject::_EnterCriticalSection((CApartmentLocalObject *)&g_aloSchemaCache);
  ApartmentType = CApartmentLocalObject::_SetApartmentObject((CApartmentLocalObject *)&g_aloSchemaCache, v13);
  LeaveCriticalSection(&Parameter);
LABEL_27:
  LeaveCriticalSection(&g_csDll);
LABEL_12:
  if ( ApartmentType >= 0 )
  {
    ApartmentType = (*(__int64 (__fastcall **)(void *, const struct _GUID *, void **))(*(_QWORD *)v19 + 80LL))(
                      v19,
                      a1,
                      a2);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return (unsigned int)ApartmentType;
}

```

## disassembly

```asm
0x18002e8b0  push    rbx
0x18002e8b2  push    rbp
0x18002e8b3  push    rsi
0x18002e8b4  push    rdi
0x18002e8b5  push    r12
0x18002e8b7  push    r14
0x18002e8b9  sub     rsp, 58h
0x18002e8bd  mov     rax, cs:__security_cookie
0x18002e8c4  xor     rax, rsp
0x18002e8c7  mov     [rsp+88h+var_48], rax
0x18002e8cc  xor     ebp, ebp
0x18002e8ce  lea     r8, Parameter; Parameter
0x18002e8d5  mov     [rdx], rbp
0x18002e8d8  mov     r14, rdx
0x18002e8db  mov     r12, rcx
0x18002e8de  mov     [rsp+88h+var_50], rbp
0x18002e8e3  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c12b5e827bbdb1597ce6a3af58750a50_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18002e8ea  xor     r9d, r9d; Context
0x18002e8ed  lea     rcx, stru_1800F0EF0; InitOnce
0x18002e8f4  call    cs:__imp_InitOnceExecuteOnce
0x18002e8fa  lea     rcx, Parameter; lpCriticalSection
0x18002e901  call    cs:__imp_EnterCriticalSection
0x18002e907  lea     rdx, [rsp+88h+pAptQualifier]; pAptQualifier
0x18002e90c  mov     [rsp+88h+pAptType], ebp
0x18002e910  lea     rcx, [rsp+88h+pAptType]; pAptType
0x18002e915  mov     [rsp+88h+pAptQualifier], ebp
0x18002e919  call    cs:__imp_CoGetApartmentType
0x18002e91f  mov     ebx, eax
0x18002e921  test    eax, eax
0x18002e923  js      loc_18002E9D9
0x18002e929  mov     edx, [rsp+88h+pAptType]
0x18002e92d  test    edx, edx
0x18002e92f  jnz     loc_18002EA39
0x18002e935  cmp     cs:?g_aloSchemaCache@@3VCApartmentLocalObject@@A, 0FFFFFFFFh; CApartmentLocalObject g_aloSchemaCache
0x18002e93c  mov     esi, 0FFFFFFFFh
0x18002e941  jz      loc_18002EA8E
0x18002e947  mov     [rsp+88h+var_38], r15
0x18002e94c  mov     r15d, cs:?g_aloSchemaCache@@3VCApartmentLocalObject@@A; CApartmentLocalObject g_aloSchemaCache
0x18002e953  mov     [rsp+88h+var_50], rbp
0x18002e958  mov     ebp, 1
0x18002e95d  mov     ebx, ebp
0x18002e95f  cmp     r15d, 0FFFFFFFFh
0x18002e963  jz      short loc_18002E9D4
0x18002e965  mov     ecx, r15d; dwTlsIndex
0x18002e968  mov     [rsp+88h+arg_10], r13
0x18002e970  call    cs:__imp_TlsGetValue
0x18002e976  mov     rdi, rax
0x18002e979  test    rax, rax
0x18002e97c  jz      loc_18002EBD3
0x18002e982  cmp     dword ptr [rax+28h], 0
0x18002e986  jz      loc_18002EC56
0x18002e98c  lock inc dword ptr [rax+8]
0x18002e990  mov     [rsp+88h+var_50], 0
0x18002e999  mov     rcx, [rdi+20h]
0x18002e99d  test    rcx, rcx
0x18002e9a0  jz      loc_18002EC4B
0x18002e9a6  mov     rax, [rcx]
0x18002e9a9  lea     r8, [rsp+88h+var_50]
0x18002e9ae  lea     rdx, _GUID_e585ec73_e223_483c_80c9_fede58f5291e
0x18002e9b5  mov     rax, [rax]
0x18002e9b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9bd  mov     ebx, eax
0x18002e9bf  lock xadd [rdi+8], esi
0x18002e9c4  cmp     esi, ebp
0x18002e9c6  jz      loc_18002EB9C
0x18002e9cc  mov     r13, [rsp+88h+arg_10]
0x18002e9d4  mov     r15, [rsp+88h+var_38]
0x18002e9d9  lea     rcx, Parameter; lpCriticalSection
0x18002e9e0  call    cs:__imp_LeaveCriticalSection
0x18002e9e6  cmp     ebx, 1
0x18002e9e9  jz      loc_18002EABD
0x18002e9ef  test    ebx, ebx
0x18002e9f1  js      short loc_18002EA1D
0x18002e9f3  mov     rcx, [rsp+88h+var_50]
0x18002e9f8  mov     r8, r14
0x18002e9fb  mov     rdx, r12
0x18002e9fe  mov     rax, [rcx]
0x18002ea01  mov     rax, [rax+50h]
0x18002ea05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea0a  mov     rcx, [rsp+88h+var_50]
0x18002ea0f  mov     ebx, eax
0x18002ea11  mov     rdx, [rcx]
0x18002ea14  mov     rax, [rdx+10h]
0x18002ea18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea1d  mov     eax, ebx
0x18002ea1f  mov     rcx, [rsp+88h+var_48]
0x18002ea24  xor     rcx, rsp; StackCookie
0x18002ea27  call    __security_check_cookie
0x18002ea2c  add     rsp, 58h
0x18002ea30  pop     r14
0x18002ea32  pop     r12
0x18002ea34  pop     rdi
0x18002ea35  pop     rsi
0x18002ea36  pop     rbp
0x18002ea37  pop     rbx
0x18002ea38  retn
0x18002ea39  sub     edx, 1
0x18002ea3c  jnz     loc_18002EB2E
0x18002ea42  mov     edi, cs:dword_1800F0EE4
0x18002ea48  mov     [rsp+88h+var_50], rbp
0x18002ea4d  mov     ebp, 1
0x18002ea52  mov     ebx, ebp
0x18002ea54  test    edi, edi
0x18002ea56  jz      short loc_18002E9D9
0x18002ea58  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x18002ea5f  test    rcx, rcx
0x18002ea62  jz      loc_18002EB61
0x18002ea68  mov     rax, [rcx]
0x18002ea6b  lea     r9, [rsp+88h+var_50]
0x18002ea70  lea     r8, _GUID_e585ec73_e223_483c_80c9_fede58f5291e
0x18002ea77  mov     edx, edi
0x18002ea79  mov     rax, [rax+28h]
0x18002ea7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea82  test    eax, eax
0x18002ea84  mov     ebx, eax
0x18002ea86  cmovs   ebx, ebp
0x18002ea89  jmp     loc_18002E9D9
0x18002ea8e  call    cs:__imp_TlsAlloc
0x18002ea94  mov     ecx, eax; dwTlsIndex
0x18002ea96  cmp     eax, 0FFFFFFFFh
0x18002ea99  jz      loc_18002EC98
0x18002ea9f  mov     eax, esi
0x18002eaa1  lock cmpxchg cs:?g_aloSchemaCache@@3VCApartmentLocalObject@@A, ecx; CApartmentLocalObject g_aloSchemaCache
0x18002eaa9  cmp     eax, 0FFFFFFFFh
0x18002eaac  jz      loc_18002E947
0x18002eab2  call    cs:__imp_TlsFree
0x18002eab8  jmp     loc_18002E947
0x18002eabd  lea     rcx, g_csDll; lpCriticalSection
0x18002eac4  call    cs:__imp_EnterCriticalSection
0x18002eaca  mov     rcx, cs:?g_pSchemaCache@@3PEAUISchemaCache@@EA; struct _GUID *
0x18002ead1  test    rcx, rcx
0x18002ead4  jz      loc_18002EBAE
0x18002eada  mov     [rsp+88h+var_50], rcx
0x18002eadf  mov     rax, [rcx]
0x18002eae2  mov     rax, [rax+8]
0x18002eae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eaeb  mov     rbx, cs:?g_pSchemaCache@@3PEAUISchemaCache@@EA; ISchemaCache * g_pSchemaCache
0x18002eaf2  lea     rcx, ?g_aloSchemaCache@@3VCApartmentLocalObject@@A; this
0x18002eaf9  call    ?_EnterCriticalSection@CApartmentLocalObject@@AEAAXXZ; CApartmentLocalObject::_EnterCriticalSection(void)
0x18002eafe  mov     rdx, rbx; struct IUnknown *
0x18002eb01  lea     rcx, ?g_aloSchemaCache@@3VCApartmentLocalObject@@A; this
0x18002eb08  call    ?_SetApartmentObject@CApartmentLocalObject@@AEAAJPEAUIUnknown@@@Z; CApartmentLocalObject::_SetApartmentObject(IUnknown *)
0x18002eb0d  lea     rcx, Parameter; lpCriticalSection
0x18002eb14  mov     ebx, eax
0x18002eb16  call    cs:__imp_LeaveCriticalSection
0x18002eb1c  lea     rcx, g_csDll; lpCriticalSection
0x18002eb23  call    cs:__imp_LeaveCriticalSection
0x18002eb29  jmp     loc_18002E9EF
0x18002eb2e  sub     edx, 1
0x18002eb31  jnz     loc_18002EC78
0x18002eb37  mov     edi, cs:dword_1800F0EE8
0x18002eb3d  mov     [rsp+88h+var_50], rbp
0x18002eb42  mov     ebp, 1
0x18002eb47  mov     ebx, ebp
0x18002eb49  test    edi, edi
0x18002eb4b  jz      loc_18002E9D9
0x18002eb51  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x18002eb58  test    rcx, rcx
0x18002eb5b  jnz     loc_18002EA68
0x18002eb61  lea     rax, ?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x18002eb68  mov     r8d, ebp; dwClsContext
0x18002eb6b  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18002eb72  mov     [rsp+88h+ppv], rax; ppv
0x18002eb77  xor     edx, edx; pUnkOuter
0x18002eb79  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18002eb80  call    cs:__imp_CoCreateInstance
0x18002eb86  mov     ebx, eax
0x18002eb88  test    eax, eax
0x18002eb8a  js      loc_18002E9D9
0x18002eb90  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x18002eb97  jmp     loc_18002EA68
0x18002eb9c  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x18002eba1  mov     rcx, rdi; void *
0x18002eba4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002eba9  jmp     loc_18002E9CC
0x18002ebae  lea     rdx, [rsp+88h+var_50]; void **
0x18002ebb3  call    ?CSchemaCache_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CSchemaCache_CreateInstance(_GUID const &,void * *)
0x18002ebb8  mov     ebx, eax
0x18002ebba  test    eax, eax
0x18002ebbc  js      loc_18002EB1C
0x18002ebc2  mov     rbx, [rsp+88h+var_50]
0x18002ebc7  mov     cs:?g_pSchemaCache@@3PEAUISchemaCache@@EA, rbx; ISchemaCache * g_pSchemaCache
0x18002ebce  jmp     loc_18002EAF2
0x18002ebd3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ebda  mov     ecx, 30h ; '0'; unsigned __int64
0x18002ebdf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002ebe4  test    rax, rax
0x18002ebe7  jz      short loc_18002EC56
0x18002ebe9  mov     rcx, rax; this
0x18002ebec  call    ??0CCachedSTAObject@@QEAA@XZ; CCachedSTAObject::CCachedSTAObject(void)
0x18002ebf1  mov     r13, rax
0x18002ebf4  test    rax, rax
0x18002ebf7  jz      short loc_18002EC56
0x18002ebf9  lea     rdx, [rax+10h]; puliCookie
0x18002ebfd  mov     [rax+18h], r15d
0x18002ec01  mov     rcx, rax; pSpy
0x18002ec04  call    cs:__imp_CoRegisterInitializeSpy
0x18002ec0a  mov     ebx, eax
0x18002ec0c  test    eax, eax
0x18002ec0e  js      short loc_18002EC52
0x18002ec10  mov     [r13+28h], ebp
0x18002ec14  cmp     cs:?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CCachedSTAObject::s_hmod
0x18002ec1c  jz      short loc_18002EC5D
0x18002ec1e  mov     rdx, r13; lpTlsValue
0x18002ec21  mov     ecx, r15d; dwTlsIndex
0x18002ec24  call    cs:__imp_TlsSetValue
0x18002ec2a  mov     rdi, r13
0x18002ec2d  lock inc dword ptr [r13+8]
0x18002ec32  mov     ebx, ebp
0x18002ec34  mov     rcx, r13; this
0x18002ec37  call    ?Release@CCachedSTAObject@@UEAAKXZ; CCachedSTAObject::Release(void)
0x18002ec3c  test    ebx, ebx
0x18002ec3e  js      short loc_18002EC56
0x18002ec40  jz      loc_18002E990
0x18002ec46  jmp     loc_18002E9BF
0x18002ec4b  mov     ebx, ebp
0x18002ec4d  jmp     loc_18002E9BF
0x18002ec52  xor     edi, edi
0x18002ec54  jmp     short loc_18002EC34
0x18002ec56  mov     ebx, ebp
0x18002ec58  jmp     loc_18002E9CC
0x18002ec5d  lea     r8, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; phModule
0x18002ec64  mov     ecx, 4; dwFlags
0x18002ec69  lea     rdx, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; lpModuleName
0x18002ec70  call    cs:__imp_GetModuleHandleExW
0x18002ec76  jmp     short loc_18002EC1E
0x18002ec78  cmp     edx, 1
0x18002ec7b  jz      loc_18002E935
0x18002ec81  lea     rcx, Parameter; lpCriticalSection
0x18002ec88  call    cs:__imp_LeaveCriticalSection
0x18002ec8e  mov     ebx, 800401F0h
0x18002ec93  jmp     loc_18002EA1D
0x18002ec98  lea     rcx, Parameter; lpCriticalSection
0x18002ec9f  call    cs:__imp_LeaveCriticalSection
0x18002eca5  mov     ebx, 8007000Eh
0x18002ecaa  jmp     loc_18002EA1D
```
