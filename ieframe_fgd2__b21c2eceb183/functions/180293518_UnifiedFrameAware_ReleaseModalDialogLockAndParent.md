# UnifiedFrameAware_ReleaseModalDialogLockAndParent

- ea: `0x180293518`
- end: `0x18029398f`
- name: `UnifiedFrameAware_ReleaseModalDialogLockAndParent`
- size: `1143`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180247b70`

## callees

- `0x1800cc2e4`
- `0x180292c3c`
- `0x180293518`
- `0x1804e7a7c`
- `0x180550010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180293538`
- `KERNEL32!GetCurrentThreadId` at `0x180293538`
- `USER32!DestroyWindow` at `0x180293780`
- `USER32!DestroyWindow` at `0x180293780`
- `USER32!GetPropW` at `0x18029357b`
- `USER32!GetPropW` at `0x180293651`
- `USER32!GetPropW` at `0x18029357b`
- `USER32!GetPropW` at `0x180293651`
- `USER32!SetPropW` at `0x1802937a0`
- `USER32!SetPropW` at `0x1802937a0`
- `USER32!GetWindowThreadProcessId` at `0x18029367e`
- `USER32!GetWindowThreadProcessId` at `0x18029367e`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802936dd`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802937c1`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802938d3`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802936dd`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802937c1`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802938d3`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802935aa`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x180293692`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x180293888`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802935aa`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x180293692`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x180293888`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180293862`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180293862`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180293971`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180293971`

## pseudocode

```c
void __fastcall UnifiedFrameAware_ReleaseModalDialogLockAndParent(__int64 a1, HWND a2, char a3)
{
  DWORD CurrentThreadId; // eax
  DWORD v7; // esi
  int TabThreadFromAssociatedThread; // r14d
  char *PropW; // rax
  int v10; // edi
  struct IEUserBroker *v11; // rcx
  HWND v12; // rax
  HWND v13; // rdi
  int v14; // eax
  DWORD WindowThreadProcessId; // eax
  int v16; // edi
  GUID *v17; // rdx
  int v18; // ebx
  int v19; // ebx
  GUID *v20; // rdx
  struct IEUserBroker *v21; // [rsp+30h] [rbp-10h] BYREF
  struct IEUserBroker *v22; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v23; // [rsp+80h] [rbp+40h] BYREF
  int v24; // [rsp+90h] [rbp+50h] BYREF
  __int64 v25; // [rsp+98h] [rbp+58h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  v24 = -1;
  v23 = 0;
  v7 = CurrentThreadId;
  TabThreadFromAssociatedThread = FindTabThreadFromAssociatedThread(CurrentThreadId, &v23, &v24);
  if ( a1 == 1 )
  {
    PropW = (char *)GetPropW(a2, L"FakeModalRefCount");
    if ( PropW == (char *)1 )
    {
      if ( TabThreadFromAssociatedThread >= 0 && v7 != v23 )
      {
        v22 = 0;
        v21 = 0;
        if ( (int)CoCreateUserBrokerForThread(v23, &v21) < 0 )
          goto LABEL_23;
        v25 = 0;
        v10 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v21 + 48LL))(
                v21,
                &CLSID_CShdocvwBroker,
                &IID_IUnknown,
                &v25);
        if ( v10 >= 0 )
        {
          v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IEUserBroker **))v25)(
                  v25,
                  &IID_IShdocvwBroker,
                  &v22);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v21 + 16LL))(v21);
        if ( v10 < 0 )
          goto LABEL_23;
        (*(void (__fastcall **)(struct IEUserBroker *, HWND, _QWORD))(*(_QWORD *)v22 + 792LL))(
          v22,
          a2,
          (unsigned int)v24);
        v11 = v22;
        goto LABEL_22;
      }
      v12 = (HWND)GetPropW(a2, L"FakeModalEffectiveParent");
      v25 = 0;
      v13 = v12;
      v14 = IsFrameOrFrameDescendant(v12);
      if ( v13 && v14 >= 0 && v25 )
      {
        WindowThreadProcessId = GetWindowThreadProcessId(v13, 0);
        v21 = 0;
        v22 = 0;
        if ( (int)CoCreateUserBrokerForThread(WindowThreadProcessId, &v22) < 0 )
          goto LABEL_23;
        v25 = 0;
        v16 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v22 + 48LL))(
                v22,
                &CLSID_CShdocvwBroker,
                &IID_IUnknown,
                &v25);
        if ( v16 < 0 )
        {
LABEL_20:
          (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v22 + 16LL))(v22);
          if ( v16 >= 0 )
          {
            (*(void (__fastcall **)(struct IEUserBroker *, HWND, _QWORD))(*(_QWORD *)v21 + 792LL))(
              v21,
              a2,
              (unsigned int)v24);
            v11 = v21;
LABEL_22:
            (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v11 + 16LL))(v11);
          }
LABEL_23:
          DestroyWindow(a2);
          TLSSetFakeModalWindow(0);
          goto LABEL_31;
        }
        v17 = &IID_IShdocvwBroker;
      }
      else
      {
        v21 = 0;
        v22 = 0;
        if ( (int)CoCreateUserBroker(&v22) < 0 )
          goto LABEL_23;
        v25 = 0;
        v16 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v22 + 48LL))(
                v22,
                &CLSID_CShdocvwBroker,
                &IID_IUnknown,
                &v25);
        if ( v16 < 0 )
          goto LABEL_20;
        v17 = &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42;
      }
      v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IEUserBroker **))v25)(v25, v17, &v21);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      goto LABEL_20;
    }
    SetPropW(a2, L"FakeModalRefCount", PropW - 1);
  }
  else if ( a1 == 2 )
  {
    v21 = 0;
    v22 = 0;
    if ( (int)CoCreateUserBroker(&v22) >= 0 )
    {
      v25 = 0;
      v18 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v22 + 48LL))(
              v22,
              &CLSID_CShdocvwBroker,
              &IID_IUnknown,
              &v25);
      if ( v18 >= 0 )
      {
        v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IEUserBroker **))v25)(
                v25,
                &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
                &v21);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v22 + 16LL))(v22);
      if ( v18 >= 0 )
      {
        (*(void (__fastcall **)(struct IEUserBroker *, _QWORD))(*(_QWORD *)v21 + 936LL))(v21, (unsigned int)v24);
        (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
  }
LABEL_31:
  if ( (unsigned __int8)IEConfiguration_GetBool(536870913) )
    goto LABEL_43;
  if ( TabThreadFromAssociatedThread >= 0 && v7 != v23 )
  {
    v21 = 0;
    v22 = 0;
    if ( (int)CoCreateUserBrokerForThread(v23, &v22) < 0 )
      goto LABEL_43;
    v25 = 0;
    v19 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v22 + 48LL))(
            v22,
            &CLSID_CShdocvwBroker,
            &IID_IUnknown,
            &v25);
    if ( v19 < 0 )
      goto LABEL_41;
    v20 = &IID_IShdocvwBroker;
    goto LABEL_40;
  }
  v21 = 0;
  v22 = 0;
  if ( (int)CoCreateUserBroker(&v22) < 0 )
    goto LABEL_43;
  v25 = 0;
  v19 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v22 + 48LL))(
          v22,
          &CLSID_CShdocvwBroker,
          &IID_IUnknown,
          &v25);
  if ( v19 >= 0 )
  {
    v20 = &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42;
LABEL_40:
    v19 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IEUserBroker **))v25)(v25, v20, &v21);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
LABEL_41:
  (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v19 >= 0 )
  {
    (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v21 + 800LL))(v21);
    (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v21 + 16LL))(v21);
  }
LABEL_43:
  if ( a3 )
    CoUninitialize();
}

```

## disassembly

```asm
0x180293518  mov     [rsp-38h+arg_8], rbx
0x18029351d  push    rbp
0x18029351e  push    rsi
0x18029351f  push    rdi
0x180293520  push    r12
0x180293522  push    r13
0x180293524  push    r14
0x180293526  push    r15
0x180293528  mov     rbp, rsp
0x18029352b  sub     rsp, 40h
0x18029352f  mov     r15b, r8b
0x180293532  mov     rbx, rdx
0x180293535  mov     rdi, rcx
0x180293538  call    cs:__imp_GetCurrentThreadId
0x18029353e  xor     r12d, r12d
0x180293541  mov     [rbp+arg_10], 0FFFFFFFFh
0x180293548  mov     ecx, eax; unsigned int
0x18029354a  mov     [rbp+arg_0], r12d
0x18029354e  lea     r8, [rbp+arg_10]; int *
0x180293552  mov     esi, eax
0x180293554  lea     rdx, [rbp+arg_0]; unsigned int *
0x180293558  call    ?FindTabThreadFromAssociatedThread@@YAJKPEAKPEAJ@Z; FindTabThreadFromAssociatedThread(ulong,ulong *,long *)
0x18029355d  lea     r13, IID_IUnknown
0x180293564  mov     r14d, eax
0x180293567  cmp     rdi, 1
0x18029356b  jnz     loc_1802937AB
0x180293571  lea     rdx, aFakemodalrefco; "FakeModalRefCount"
0x180293578  mov     rcx, rbx; hWnd
0x18029357b  call    cs:__imp_GetPropW
0x180293581  cmp     rax, rdi
0x180293584  jnz     loc_180293792
0x18029358a  test    r14d, r14d
0x18029358d  js      loc_180293647
0x180293593  mov     ecx, [rbp+arg_0]
0x180293596  cmp     esi, ecx
0x180293598  jz      loc_180293647
0x18029359e  lea     rdx, [rbp+var_10]
0x1802935a2  mov     [rbp+var_8], r12
0x1802935a6  mov     [rbp+var_10], r12
0x1802935aa  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x1802935b0  test    eax, eax
0x1802935b2  js      loc_18029377D
0x1802935b8  mov     rcx, [rbp+var_10]
0x1802935bc  lea     r9, [rbp+arg_18]
0x1802935c0  mov     [rbp+arg_18], r12
0x1802935c4  lea     rdx, CLSID_CShdocvwBroker
0x1802935cb  mov     r8, r13
0x1802935ce  mov     rax, [rcx]
0x1802935d1  mov     rax, [rax+30h]
0x1802935d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802935da  mov     edi, eax
0x1802935dc  test    eax, eax
0x1802935de  js      short loc_18029360C
0x1802935e0  mov     rcx, [rbp+arg_18]
0x1802935e4  lea     r8, [rbp+var_8]
0x1802935e8  lea     rdx, IID_IShdocvwBroker
0x1802935ef  mov     rax, [rcx]
0x1802935f2  mov     rax, [rax]
0x1802935f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802935fa  mov     rcx, [rbp+arg_18]
0x1802935fe  mov     edi, eax
0x180293600  mov     rax, [rcx]
0x180293603  mov     rax, [rax+10h]
0x180293607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029360c  mov     rcx, [rbp+var_10]
0x180293610  mov     rax, [rcx]
0x180293613  mov     rax, [rax+10h]
0x180293617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029361c  test    edi, edi
0x18029361e  js      loc_18029377D
0x180293624  mov     rcx, [rbp+var_8]
0x180293628  mov     rdx, rbx
0x18029362b  mov     r8d, [rbp+arg_10]
0x18029362f  mov     rax, [rcx]
0x180293632  mov     rax, [rax+318h]
0x180293639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029363e  mov     rcx, [rbp+var_8]
0x180293642  jmp     loc_180293771
0x180293647  lea     rdx, aFakemodaleffec; "FakeModalEffectiveParent"
0x18029364e  mov     rcx, rbx; hWnd
0x180293651  call    cs:__imp_GetPropW
0x180293657  lea     rdx, [rbp+arg_18]
0x18029365b  mov     [rbp+arg_18], r12
0x18029365f  mov     rcx, rax; hWndParent
0x180293662  mov     rdi, rax
0x180293665  call    _IsFrameOrFrameDescendant
0x18029366a  test    rdi, rdi
0x18029366d  jz      short loc_1802936D1
0x18029366f  test    eax, eax
0x180293671  js      short loc_1802936D1
0x180293673  cmp     [rbp+arg_18], r12
0x180293677  jz      short loc_1802936D1
0x180293679  xor     edx, edx; lpdwProcessId
0x18029367b  mov     rcx, rdi; hWnd
0x18029367e  call    cs:__imp_GetWindowThreadProcessId
0x180293684  lea     rdx, [rbp+var_8]
0x180293688  mov     [rbp+var_10], r12
0x18029368c  mov     ecx, eax
0x18029368e  mov     [rbp+var_8], r12
0x180293692  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x180293698  test    eax, eax
0x18029369a  js      loc_18029377D
0x1802936a0  mov     rcx, [rbp+var_8]
0x1802936a4  lea     r9, [rbp+arg_18]
0x1802936a8  mov     [rbp+arg_18], r12
0x1802936ac  lea     rdx, CLSID_CShdocvwBroker
0x1802936b3  mov     r8, r13
0x1802936b6  mov     rax, [rcx]
0x1802936b9  mov     rax, [rax+30h]
0x1802936bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802936c2  mov     edi, eax
0x1802936c4  test    eax, eax
0x1802936c6  js      short loc_18029373F
0x1802936c8  lea     rdx, IID_IShdocvwBroker
0x1802936cf  jmp     short loc_18029371A
0x1802936d1  lea     rcx, [rbp+var_8]
0x1802936d5  mov     [rbp+var_10], r12
0x1802936d9  mov     [rbp+var_8], r12
0x1802936dd  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1802936e3  test    eax, eax
0x1802936e5  js      loc_18029377D
0x1802936eb  mov     rcx, [rbp+var_8]
0x1802936ef  lea     r9, [rbp+arg_18]
0x1802936f3  mov     [rbp+arg_18], r12
0x1802936f7  lea     rdx, CLSID_CShdocvwBroker
0x1802936fe  mov     r8, r13
0x180293701  mov     rax, [rcx]
0x180293704  mov     rax, [rax+30h]
0x180293708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029370d  mov     edi, eax
0x18029370f  test    eax, eax
0x180293711  js      short loc_18029373F
0x180293713  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x18029371a  mov     rcx, [rbp+arg_18]
0x18029371e  lea     r8, [rbp+var_10]
0x180293722  mov     rax, [rcx]
0x180293725  mov     rax, [rax]
0x180293728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029372d  mov     rcx, [rbp+arg_18]
0x180293731  mov     edi, eax
0x180293733  mov     rax, [rcx]
0x180293736  mov     rax, [rax+10h]
0x18029373a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029373f  mov     rcx, [rbp+var_8]
0x180293743  mov     rax, [rcx]
0x180293746  mov     rax, [rax+10h]
0x18029374a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029374f  test    edi, edi
0x180293751  js      short loc_18029377D
0x180293753  mov     rcx, [rbp+var_10]
0x180293757  mov     rdx, rbx
0x18029375a  mov     r8d, [rbp+arg_10]
0x18029375e  mov     rax, [rcx]
0x180293761  mov     rax, [rax+318h]
0x180293768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029376d  mov     rcx, [rbp+var_10]
0x180293771  mov     rax, [rcx]
0x180293774  mov     rax, [rax+10h]
0x180293778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029377d  mov     rcx, rbx; hWnd
0x180293780  call    cs:__imp_DestroyWindow
0x180293786  xor     ecx, ecx; HWND
0x180293788  call    ?TLSSetFakeModalWindow@@YAXPEAUHWND__@@@Z; TLSSetFakeModalWindow(HWND__ *)
0x18029378d  jmp     loc_18029385D
0x180293792  lea     r8, [rax-1]; hData
0x180293796  mov     rcx, rbx; hWnd
0x180293799  lea     rdx, aFakemodalrefco; "FakeModalRefCount"
0x1802937a0  call    cs:__imp_SetPropW
0x1802937a6  jmp     loc_18029385D
0x1802937ab  cmp     rdi, 2
0x1802937af  jnz     loc_18029385D
0x1802937b5  lea     rcx, [rbp+var_8]
0x1802937b9  mov     [rbp+var_10], r12
0x1802937bd  mov     [rbp+var_8], r12
0x1802937c1  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1802937c7  test    eax, eax
0x1802937c9  js      loc_18029385D
0x1802937cf  mov     rcx, [rbp+var_8]
0x1802937d3  lea     r9, [rbp+arg_18]
0x1802937d7  mov     [rbp+arg_18], r12
0x1802937db  lea     rdx, CLSID_CShdocvwBroker
0x1802937e2  mov     r8, r13
0x1802937e5  mov     rax, [rcx]
0x1802937e8  mov     rax, [rax+30h]
0x1802937ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802937f1  mov     ebx, eax
0x1802937f3  test    eax, eax
0x1802937f5  js      short loc_180293823
0x1802937f7  mov     rcx, [rbp+arg_18]
0x1802937fb  lea     r8, [rbp+var_10]
0x1802937ff  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180293806  mov     rax, [rcx]
0x180293809  mov     rax, [rax]
0x18029380c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293811  mov     rcx, [rbp+arg_18]
0x180293815  mov     ebx, eax
0x180293817  mov     rax, [rcx]
0x18029381a  mov     rax, [rax+10h]
0x18029381e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293823  mov     rcx, [rbp+var_8]
0x180293827  mov     rax, [rcx]
0x18029382a  mov     rax, [rax+10h]
0x18029382e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293833  test    ebx, ebx
0x180293835  js      short loc_18029385D
0x180293837  mov     rcx, [rbp+var_10]
0x18029383b  mov     edx, [rbp+arg_10]
0x18029383e  mov     rax, [rcx]
0x180293841  mov     rax, [rax+3A8h]
0x180293848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029384d  mov     rcx, [rbp+var_10]
0x180293851  mov     rax, [rcx]
0x180293854  mov     rax, [rax+10h]
0x180293858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029385d  mov     ecx, 20000001h
0x180293862  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180293868  test    al, al
0x18029386a  jnz     loc_18029396C
0x180293870  test    r14d, r14d
0x180293873  js      short loc_1802938C7
0x180293875  mov     ecx, [rbp+arg_0]
0x180293878  cmp     esi, ecx
0x18029387a  jz      short loc_1802938C7
0x18029387c  lea     rdx, [rbp+var_8]
0x180293880  mov     [rbp+var_10], r12
0x180293884  mov     [rbp+var_8], r12
0x180293888  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x18029388e  test    eax, eax
0x180293890  js      loc_18029396C
0x180293896  mov     rcx, [rbp+var_8]
0x18029389a  lea     r9, [rbp+arg_18]
0x18029389e  mov     [rbp+arg_18], r12
0x1802938a2  lea     rdx, CLSID_CShdocvwBroker
0x1802938a9  mov     r8, r13
0x1802938ac  mov     rax, [rcx]
0x1802938af  mov     rax, [rax+30h]
0x1802938b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802938b8  mov     ebx, eax
0x1802938ba  test    eax, eax
0x1802938bc  js      short loc_180293935
0x1802938be  lea     rdx, IID_IShdocvwBroker
0x1802938c5  jmp     short loc_180293910
0x1802938c7  lea     rcx, [rbp+var_8]
0x1802938cb  mov     [rbp+var_10], r12
0x1802938cf  mov     [rbp+var_8], r12
0x1802938d3  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1802938d9  test    eax, eax
0x1802938db  js      loc_18029396C
0x1802938e1  mov     rcx, [rbp+var_8]
0x1802938e5  lea     r9, [rbp+arg_18]
0x1802938e9  mov     [rbp+arg_18], r12
0x1802938ed  lea     rdx, CLSID_CShdocvwBroker
0x1802938f4  mov     r8, r13
0x1802938f7  mov     rax, [rcx]
0x1802938fa  mov     rax, [rax+30h]
0x1802938fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293903  mov     ebx, eax
0x180293905  test    eax, eax
0x180293907  js      short loc_180293935
0x180293909  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x180293910  mov     rcx, [rbp+arg_18]
0x180293914  lea     r8, [rbp+var_10]
0x180293918  mov     rax, [rcx]
0x18029391b  mov     rax, [rax]
0x18029391e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293923  mov     rcx, [rbp+arg_18]
0x180293927  mov     ebx, eax
0x180293929  mov     rax, [rcx]
0x18029392c  mov     rax, [rax+10h]
0x180293930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293935  mov     rcx, [rbp+var_8]
0x180293939  mov     rax, [rcx]
0x18029393c  mov     rax, [rax+10h]
0x180293940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180293945  test    ebx, ebx
0x180293947  js      short loc_18029396C
0x180293949  mov     rcx, [rbp+var_10]
0x18029394d  mov     rax, [rcx]
0x180293950  mov     rax, [rax+320h]
0x180293957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029395c  mov     rcx, [rbp+var_10]
0x180293960  mov     rax, [rcx]
0x180293963  mov     rax, [rax+10h]
0x180293967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029396c  test    r15b, r15b
0x18029396f  jz      short loc_180293977
0x180293971  call    cs:__imp_CoUninitialize
0x180293977  mov     rbx, [rsp+40h+arg_8]
0x18029397f  add     rsp, 40h
0x180293983  pop     r15
0x180293985  pop     r14
0x180293987  pop     r13
0x180293989  pop     r12
0x18029398b  pop     rdi
0x18029398c  pop     rsi
0x18029398d  pop     rbp
0x18029398e  retn
```
