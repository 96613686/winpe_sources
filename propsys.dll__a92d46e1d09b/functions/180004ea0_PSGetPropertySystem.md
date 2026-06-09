# PSGetPropertySystem

- ea: `0x180004ea0`
- end: `0x18000522f`
- name: `PSGetPropertySystem`
- size: `911`
- prototype: `HRESULT __stdcall(const IID *const riid, void **ppv)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180004d10`
- `0x180004db0`
- `0x180083e70`
- `0x180083ef0`
- `0x180084000`

## callees

- `0x180004ea0`
- `0x1800059cc`
- `0x180005bb0`
- `0x1800062b0`
- `0x18006bb14`
- `0x18006ed20`
- `0x18006f1fc`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800051ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800051ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004fbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000520d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005224`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004fbb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000520d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005224`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004eef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004eef`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005130`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005130`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004f5b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180004f5b`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000504b`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18000504b`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180005027`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180005027`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004ee2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004ee2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000509e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005182`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000509e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005182`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180004f09`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180004f09`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180005105`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180005105`

## pseudocode

```c
HRESULT __stdcall PSGetPropertySystem(const IID *const riid, void **ppv)
{
  int ApartmentType; // ebx
  DWORD v5; // r14d
  volatile signed __int32 *Value; // rax
  volatile signed __int32 *v7; // rdi
  __int64 (__fastcall ***v8)(_QWORD, const IID *const, void **); // rcx
  HRESULT result; // eax
  unsigned int v10; // edi
  LPVOID v11; // rcx
  DWORD v12; // ecx
  CCachedSTAObject *v13; // rax
  CCachedSTAObject *v14; // rax
  CCachedSTAObject *v15; // r13
  APTTYPE pAptType; // [rsp+30h] [rbp-58h] BYREF
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+38h] [rbp-50h] BYREF

  *ppv = 0;
  InitOnceExecuteOnce(&InitOnce, _lambda_c12b5e827bbdb1597ce6a3af58750a50_::_lambda_invoker_cdecl_, &CriticalSection, 0);
  EnterCriticalSection(&CriticalSection);
  pAptType = APTTYPE_STA;
  pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, pAptQualifier);
  if ( ApartmentType < 0 )
    goto LABEL_11;
  switch ( pAptType )
  {
    case APTTYPE_STA:
      goto LABEL_3;
    case APTTYPE_MTA:
      v10 = dword_1800F0E24;
      ApartmentType = 1;
      *ppv = 0;
      if ( !v10 )
        goto LABEL_11;
      v11 = g_pgit;
      if ( g_pgit )
      {
LABEL_17:
        ApartmentType = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const IID *const, void **))(*(_QWORD *)v11 + 40LL))(
                          v11,
                          v10,
                          riid,
                          ppv);
        if ( ApartmentType < 0 )
          ApartmentType = 1;
        goto LABEL_11;
      }
LABEL_26:
      ApartmentType = CoCreateInstance(
                        &CLSID_StdGlobalInterfaceTable,
                        0,
                        1u,
                        &GUID_00000146_0000_0000_c000_000000000046,
                        &g_pgit);
      if ( ApartmentType < 0 )
        goto LABEL_11;
      v11 = g_pgit;
      goto LABEL_17;
    case APTTYPE_NA:
      v10 = dword_1800F0E28;
      ApartmentType = 1;
      *ppv = 0;
      if ( !v10 )
        goto LABEL_11;
      v11 = g_pgit;
      if ( g_pgit )
        goto LABEL_17;
      goto LABEL_26;
  }
  if ( pAptType != APTTYPE_MAINSTA )
  {
    ApartmentType = -2147221008;
    LeaveCriticalSection(&CriticalSection);
    return ApartmentType;
  }
LABEL_3:
  if ( g_aloPropertySystem == -1 )
  {
    v12 = TlsAlloc();
    if ( v12 == -1 )
    {
      ApartmentType = -2147024882;
      LeaveCriticalSection(&CriticalSection);
      return ApartmentType;
    }
    if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_aloPropertySystem, v12, -1) != -1 )
      TlsFree(v12);
  }
  ApartmentType = 1;
  v5 = g_aloPropertySystem;
  *ppv = 0;
  if ( v5 != -1 )
  {
    Value = (volatile signed __int32 *)TlsGetValue(v5);
    v7 = Value;
    if ( Value )
    {
      if ( *((_DWORD *)Value + 10) )
      {
        _InterlockedIncrement(Value + 2);
        *ppv = 0;
        v8 = (__int64 (__fastcall ***)(_QWORD, const IID *const, void **))*((_QWORD *)Value + 4);
        if ( v8 )
          ApartmentType = (**v8)(v8, riid, ppv);
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
      v13 = (CCachedSTAObject *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
      if ( v13 )
      {
        v14 = CCachedSTAObject::CCachedSTAObject(v13);
        v15 = v14;
        if ( v14 )
        {
          *((_DWORD *)v14 + 6) = v5;
          ApartmentType = CoRegisterInitializeSpy((IInitializeSpy *)v14, (ULARGE_INTEGER *)v14 + 2);
          if ( ApartmentType < 0 )
          {
            v7 = 0;
          }
          else
          {
            *((_DWORD *)v15 + 10) = 1;
            if ( !*(_QWORD *)&CCachedSTAObject::s_hmod )
              GetModuleHandleExW(4u, &CCachedSTAObject::s_hmod, (HMODULE *)&CCachedSTAObject::s_hmod);
            TlsSetValue(v5, v15);
            v7 = (volatile signed __int32 *)v15;
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
  }
LABEL_11:
  LeaveCriticalSection(&CriticalSection);
  if ( ApartmentType != 1 )
    return ApartmentType;
  *(_QWORD *)pAptQualifier = 0;
  result = CoCreateInstance(
             &CLSID_PropertySystem,
             0,
             1u,
             &GUID_00000000_0000_0000_c000_000000000046,
             (LPVOID *)pAptQualifier);
  if ( result >= 0 )
  {
    ApartmentType = CApartmentLocalObject::TrySetApartmentObject(
                      (CApartmentLocalObject *)&g_aloPropertySystem,
                      *(struct IUnknown **)pAptQualifier,
                      riid,
                      ppv);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
    return ApartmentType;
  }
  return result;
}

```

## disassembly

```asm
0x180004ea0  push    rbx
0x180004ea2  push    rbp
0x180004ea3  push    rsi
0x180004ea4  push    rdi
0x180004ea5  push    r12
0x180004ea7  push    r13
0x180004ea9  push    r15
0x180004eab  sub     rsp, 50h
0x180004eaf  mov     rax, cs:__security_cookie
0x180004eb6  xor     rax, rsp
0x180004eb9  mov     [rsp+88h+var_48], rax
0x180004ebe  mov     rsi, rdx
0x180004ec1  lea     r8, CriticalSection; Parameter
0x180004ec8  mov     r15, rcx
0x180004ecb  xor     r12d, r12d
0x180004ece  mov     [rdx], r12
0x180004ed1  lea     rcx, InitOnce; InitOnce
0x180004ed8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c12b5e827bbdb1597ce6a3af58750a50_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180004edf  xor     r9d, r9d; Context
0x180004ee2  call    cs:__imp_InitOnceExecuteOnce
0x180004ee8  lea     rcx, CriticalSection; lpCriticalSection
0x180004eef  call    cs:__imp_EnterCriticalSection
0x180004ef5  lea     rdx, [rsp+88h+pAptQualifier]; pAptQualifier
0x180004efa  mov     [rsp+88h+pAptType], r12d
0x180004eff  lea     rcx, [rsp+88h+pAptType]; pAptType
0x180004f04  mov     [rsp+88h+pAptQualifier], r12d
0x180004f09  call    cs:__imp_CoGetApartmentType
0x180004f0f  mov     ebx, eax
0x180004f11  mov     r13d, 1
0x180004f17  test    eax, eax
0x180004f19  js      loc_180004FB4
0x180004f1f  mov     edx, [rsp+88h+pAptType]
0x180004f23  test    edx, edx
0x180004f25  jnz     loc_180004FE8
0x180004f2b  cmp     cs:?g_aloPropertySystem@@3VCApartmentLocalObject@@A, 0FFFFFFFFh; CApartmentLocalObject g_aloPropertySystem
0x180004f32  mov     ebp, 0FFFFFFFFh
0x180004f37  jz      loc_180005027
0x180004f3d  mov     [rsp+88h+arg_10], r14
0x180004f45  mov     ebx, r13d
0x180004f48  mov     r14d, cs:?g_aloPropertySystem@@3VCApartmentLocalObject@@A; CApartmentLocalObject g_aloPropertySystem
0x180004f4f  mov     [rsi], r12
0x180004f52  cmp     r14d, 0FFFFFFFFh
0x180004f56  jz      short loc_180004FAC
0x180004f58  mov     ecx, r14d; dwTlsIndex
0x180004f5b  call    cs:__imp_TlsGetValue
0x180004f61  mov     rdi, rax
0x180004f64  test    rax, rax
0x180004f67  jz      loc_1800050CC
0x180004f6d  cmp     [rax+28h], r12d
0x180004f71  jz      loc_1800051D2
0x180004f77  lock inc dword ptr [rax+8]
0x180004f7b  mov     [rsi], r12
0x180004f7e  mov     rcx, [rdi+20h]
0x180004f82  test    rcx, rcx
0x180004f85  jz      loc_1800051BF
0x180004f8b  mov     rax, [rcx]
0x180004f8e  mov     r8, rsi
0x180004f91  mov     rdx, r15
0x180004f94  mov     rax, [rax]
0x180004f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f9c  mov     ebx, eax
0x180004f9e  lock xadd [rdi+8], ebp
0x180004fa3  cmp     ebp, 1
0x180004fa6  jz      loc_1800050BA
0x180004fac  mov     r14, [rsp+88h+arg_10]
0x180004fb4  lea     rcx, CriticalSection; lpCriticalSection
0x180004fbb  call    cs:__imp_LeaveCriticalSection
0x180004fc1  cmp     ebx, 1
0x180004fc4  jz      loc_180005160
0x180004fca  mov     eax, ebx
0x180004fcc  mov     rcx, [rsp+88h+var_48]
0x180004fd1  xor     rcx, rsp; StackCookie
0x180004fd4  call    __security_check_cookie
0x180004fd9  add     rsp, 50h
0x180004fdd  pop     r15
0x180004fdf  pop     r13
0x180004fe1  pop     r12
0x180004fe3  pop     rdi
0x180004fe4  pop     rsi
0x180004fe5  pop     rbp
0x180004fe6  pop     rbx
0x180004fe7  retn
0x180004fe8  sub     edx, r13d
0x180004feb  jnz     short loc_180005056
0x180004fed  mov     edi, cs:dword_1800F0E24
0x180004ff3  mov     ebx, r13d
0x180004ff6  mov     [rsi], r12
0x180004ff9  test    edi, edi
0x180004ffb  jz      short loc_180004FB4
0x180004ffd  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180005004  test    rcx, rcx
0x180005007  jz      short loc_18000507F
0x180005009  mov     rax, [rcx]
0x18000500c  mov     r9, rsi
0x18000500f  mov     r8, r15
0x180005012  mov     edx, edi
0x180005014  mov     rax, [rax+28h]
0x180005018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000501d  test    eax, eax
0x18000501f  mov     ebx, eax
0x180005021  cmovs   ebx, r13d
0x180005025  jmp     short loc_180004FB4
0x180005027  call    cs:__imp_TlsAlloc
0x18000502d  mov     ecx, eax; dwTlsIndex
0x18000502f  cmp     eax, 0FFFFFFFFh
0x180005032  jz      loc_180005218
0x180005038  mov     eax, ebp
0x18000503a  lock cmpxchg cs:?g_aloPropertySystem@@3VCApartmentLocalObject@@A, ecx; CApartmentLocalObject g_aloPropertySystem
0x180005042  cmp     eax, 0FFFFFFFFh
0x180005045  jz      loc_180004F3D
0x18000504b  call    cs:__imp_TlsFree
0x180005051  jmp     loc_180004F3D
0x180005056  sub     edx, r13d
0x180005059  jnz     loc_1800051F8
0x18000505f  mov     edi, cs:dword_1800F0E28
0x180005065  mov     ebx, r13d
0x180005068  mov     [rsi], r12
0x18000506b  test    edi, edi
0x18000506d  jz      loc_180004FB4
0x180005073  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x18000507a  test    rcx, rcx
0x18000507d  jnz     short loc_180005009
0x18000507f  lea     rax, ?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x180005086  mov     r8d, r13d; dwClsContext
0x180005089  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180005090  mov     [rsp+88h+ppv], rax; ppv
0x180005095  xor     edx, edx; pUnkOuter
0x180005097  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000509e  call    cs:__imp_CoCreateInstance
0x1800050a4  mov     ebx, eax
0x1800050a6  test    eax, eax
0x1800050a8  js      loc_180004FB4
0x1800050ae  mov     rcx, cs:?g_pgit@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pgit
0x1800050b5  jmp     loc_180005009
0x1800050ba  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x1800050bf  mov     rcx, rdi; void *
0x1800050c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800050c7  jmp     loc_180004FAC
0x1800050cc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800050d3  mov     ecx, 30h ; '0'; unsigned __int64
0x1800050d8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800050dd  test    rax, rax
0x1800050e0  jz      loc_1800051D2
0x1800050e6  mov     rcx, rax; this
0x1800050e9  call    ??0CCachedSTAObject@@QEAA@XZ; CCachedSTAObject::CCachedSTAObject(void)
0x1800050ee  mov     r13, rax
0x1800050f1  test    rax, rax
0x1800050f4  jz      loc_1800051CF
0x1800050fa  lea     rdx, [rax+10h]; puliCookie
0x1800050fe  mov     [rax+18h], r14d
0x180005102  mov     rcx, rax; pSpy
0x180005105  call    cs:__imp_CoRegisterInitializeSpy
0x18000510b  mov     ebx, eax
0x18000510d  test    eax, eax
0x18000510f  js      loc_1800051C7
0x180005115  mov     dword ptr [r13+28h], 1
0x18000511d  cmp     cs:?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA, r12; HINSTANCE__ * CCachedSTAObject::s_hmod
0x180005124  jz      loc_1800051DA
0x18000512a  mov     rdx, r13; lpTlsValue
0x18000512d  mov     ecx, r14d; dwTlsIndex
0x180005130  call    cs:__imp_TlsSetValue
0x180005136  mov     rdi, r13
0x180005139  lock inc dword ptr [r13+8]
0x18000513e  mov     ebx, 1
0x180005143  mov     rcx, r13; this
0x180005146  call    ?Release@CCachedSTAObject@@UEAAKXZ; CCachedSTAObject::Release(void)
0x18000514b  mov     r13d, 1
0x180005151  test    ebx, ebx
0x180005153  js      short loc_1800051D2
0x180005155  jz      loc_180004F7B
0x18000515b  jmp     loc_180004F9E
0x180005160  lea     rax, [rsp+88h+pAptQualifier]
0x180005165  mov     qword ptr [rsp+88h+pAptQualifier], r12
0x18000516a  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180005171  mov     [rsp+88h+ppv], rax; ppv
0x180005176  mov     r8d, r13d; dwClsContext
0x180005179  lea     rcx, CLSID_PropertySystem; rclsid
0x180005180  xor     edx, edx; pUnkOuter
0x180005182  call    cs:__imp_CoCreateInstance
0x180005188  test    eax, eax
0x18000518a  js      loc_180004FCC
0x180005190  mov     rdx, qword ptr [rsp+88h+pAptQualifier]; struct IUnknown *
0x180005195  lea     rcx, ?g_aloPropertySystem@@3VCApartmentLocalObject@@A; this
0x18000519c  mov     r9, rsi; void **
0x18000519f  mov     r8, r15; struct _GUID *
0x1800051a2  call    ?TrySetApartmentObject@CApartmentLocalObject@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CApartmentLocalObject::TrySetApartmentObject(IUnknown *,_GUID const &,void * *)
0x1800051a7  mov     rcx, qword ptr [rsp+88h+pAptQualifier]
0x1800051ac  mov     ebx, eax
0x1800051ae  mov     rdx, [rcx]
0x1800051b1  mov     rax, [rdx+10h]
0x1800051b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051ba  jmp     loc_180004FCA
0x1800051bf  mov     ebx, r13d
0x1800051c2  jmp     loc_180004F9E
0x1800051c7  mov     rdi, r12
0x1800051ca  jmp     loc_180005143
0x1800051cf  mov     r13d, ebx
0x1800051d2  mov     ebx, r13d
0x1800051d5  jmp     loc_180004FAC
0x1800051da  lea     r8, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; phModule
0x1800051e1  mov     ecx, 4; dwFlags
0x1800051e6  lea     rdx, ?s_hmod@CCachedSTAObject@@0PEAUHINSTANCE__@@EA; lpModuleName
0x1800051ed  call    cs:__imp_GetModuleHandleExW
0x1800051f3  jmp     loc_18000512A
0x1800051f8  cmp     edx, r13d
0x1800051fb  jz      loc_180004F2B
0x180005201  lea     rcx, CriticalSection; lpCriticalSection
0x180005208  mov     ebx, 800401F0h
0x18000520d  call    cs:__imp_LeaveCriticalSection
0x180005213  jmp     loc_180004FCA
0x180005218  lea     rcx, CriticalSection; lpCriticalSection
0x18000521f  mov     ebx, 8007000Eh
0x180005224  call    cs:__imp_LeaveCriticalSection
0x18000522a  jmp     loc_180004FCA
```
