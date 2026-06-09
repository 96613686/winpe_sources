# UnifiedFrameAware_ReleaseModalDialogLockAndParent

- ea: `0x1802b6128`
- end: `0x1802b65f4`
- name: `UnifiedFrameAware_ReleaseModalDialogLockAndParent`
- size: `1228`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180266160`

## callees

- `0x1800d42c4`
- `0x1802b5770`
- `0x1802b6128`
- `0x1805261dc`
- `0x180594010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1802b6148`
- `KERNEL32!GetCurrentThreadId` at `0x1802b6148`
- `USER32!DestroyWindow` at `0x1802b63ba`
- `USER32!DestroyWindow` at `0x1802b63ba`
- `USER32!GetPropW` at `0x1802b6191`
- `USER32!GetPropW` at `0x1802b6273`
- `USER32!GetPropW` at `0x1802b6191`
- `USER32!GetPropW` at `0x1802b6273`
- `USER32!SetPropW` at `0x1802b63e0`
- `USER32!SetPropW` at `0x1802b63e0`
- `USER32!GetWindowThreadProcessId` at `0x1802b62a6`
- `USER32!GetWindowThreadProcessId` at `0x1802b62a6`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802b6311`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802b6407`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802b652b`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802b6311`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802b6407`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x1802b652b`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802b61c6`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802b62c0`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802b64da`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802b61c6`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802b62c0`
- `iertutil!__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z` at `0x1802b64da`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1802b64ae`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1802b64ae`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1802b65cf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1802b65cf`

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
0x1802b6128  mov     [rsp-38h+arg_8], rbx
0x1802b612d  push    rbp
0x1802b612e  push    rsi
0x1802b612f  push    rdi
0x1802b6130  push    r12
0x1802b6132  push    r13
0x1802b6134  push    r14
0x1802b6136  push    r15
0x1802b6138  mov     rbp, rsp
0x1802b613b  sub     rsp, 40h
0x1802b613f  mov     r15b, r8b
0x1802b6142  mov     rbx, rdx
0x1802b6145  mov     rdi, rcx
0x1802b6148  call    cs:__imp_GetCurrentThreadId
0x1802b614f  nop     dword ptr [rax+rax+00h]
0x1802b6154  xor     r12d, r12d
0x1802b6157  mov     [rbp+arg_10], 0FFFFFFFFh
0x1802b615e  mov     ecx, eax; unsigned int
0x1802b6160  mov     [rbp+arg_0], r12d
0x1802b6164  lea     r8, [rbp+arg_10]; int *
0x1802b6168  mov     esi, eax
0x1802b616a  lea     rdx, [rbp+arg_0]; unsigned int *
0x1802b616e  call    ?FindTabThreadFromAssociatedThread@@YAJKPEAKPEAJ@Z; FindTabThreadFromAssociatedThread(ulong,ulong *,long *)
0x1802b6173  lea     r13, IID_IUnknown
0x1802b617a  mov     r14d, eax
0x1802b617d  cmp     rdi, 1
0x1802b6181  jnz     loc_1802B63F1
0x1802b6187  lea     rdx, aFakemodalrefco; "FakeModalRefCount"
0x1802b618e  mov     rcx, rbx; hWnd
0x1802b6191  call    cs:__imp_GetPropW
0x1802b6198  nop     dword ptr [rax+rax+00h]
0x1802b619d  cmp     rax, rdi
0x1802b61a0  jnz     loc_1802B63D2
0x1802b61a6  test    r14d, r14d
0x1802b61a9  js      loc_1802B6269
0x1802b61af  mov     ecx, [rbp+arg_0]
0x1802b61b2  cmp     esi, ecx
0x1802b61b4  jz      loc_1802B6269
0x1802b61ba  lea     rdx, [rbp+var_10]
0x1802b61be  mov     [rbp+var_8], r12
0x1802b61c2  mov     [rbp+var_10], r12
0x1802b61c6  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x1802b61cd  nop     dword ptr [rax+rax+00h]
0x1802b61d2  test    eax, eax
0x1802b61d4  js      loc_1802B63B7
0x1802b61da  mov     rcx, [rbp+var_10]
0x1802b61de  lea     r9, [rbp+arg_18]
0x1802b61e2  mov     [rbp+arg_18], r12
0x1802b61e6  lea     rdx, CLSID_CShdocvwBroker
0x1802b61ed  mov     r8, r13
0x1802b61f0  mov     rax, [rcx]
0x1802b61f3  mov     rax, [rax+30h]
0x1802b61f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b61fc  mov     edi, eax
0x1802b61fe  test    eax, eax
0x1802b6200  js      short loc_1802B622E
0x1802b6202  mov     rcx, [rbp+arg_18]
0x1802b6206  lea     r8, [rbp+var_8]
0x1802b620a  lea     rdx, IID_IShdocvwBroker
0x1802b6211  mov     rax, [rcx]
0x1802b6214  mov     rax, [rax]
0x1802b6217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b621c  mov     rcx, [rbp+arg_18]
0x1802b6220  mov     edi, eax
0x1802b6222  mov     rax, [rcx]
0x1802b6225  mov     rax, [rax+10h]
0x1802b6229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b622e  mov     rcx, [rbp+var_10]
0x1802b6232  mov     rax, [rcx]
0x1802b6235  mov     rax, [rax+10h]
0x1802b6239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b623e  test    edi, edi
0x1802b6240  js      loc_1802B63B7
0x1802b6246  mov     rcx, [rbp+var_8]
0x1802b624a  mov     rdx, rbx
0x1802b624d  mov     r8d, [rbp+arg_10]
0x1802b6251  mov     rax, [rcx]
0x1802b6254  mov     rax, [rax+318h]
0x1802b625b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b6260  mov     rcx, [rbp+var_8]
0x1802b6264  jmp     loc_1802B63AB
0x1802b6269  lea     rdx, aFakemodaleffec; "FakeModalEffectiveParent"
0x1802b6270  mov     rcx, rbx; hWnd
0x1802b6273  call    cs:__imp_GetPropW
0x1802b627a  nop     dword ptr [rax+rax+00h]
0x1802b627f  lea     rdx, [rbp+arg_18]
0x1802b6283  mov     [rbp+arg_18], r12
0x1802b6287  mov     rcx, rax; hWndParent
0x1802b628a  mov     rdi, rax
0x1802b628d  call    _IsFrameOrFrameDescendant
0x1802b6292  test    rdi, rdi
0x1802b6295  jz      short loc_1802B6305
0x1802b6297  test    eax, eax
0x1802b6299  js      short loc_1802B6305
0x1802b629b  cmp     [rbp+arg_18], r12
0x1802b629f  jz      short loc_1802B6305
0x1802b62a1  xor     edx, edx; lpdwProcessId
0x1802b62a3  mov     rcx, rdi; hWnd
0x1802b62a6  call    cs:__imp_GetWindowThreadProcessId
0x1802b62ad  nop     dword ptr [rax+rax+00h]
0x1802b62b2  lea     rdx, [rbp+var_8]
0x1802b62b6  mov     [rbp+var_10], r12
0x1802b62ba  mov     ecx, eax
0x1802b62bc  mov     [rbp+var_8], r12
0x1802b62c0  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x1802b62c7  nop     dword ptr [rax+rax+00h]
0x1802b62cc  test    eax, eax
0x1802b62ce  js      loc_1802B63B7
0x1802b62d4  mov     rcx, [rbp+var_8]
0x1802b62d8  lea     r9, [rbp+arg_18]
0x1802b62dc  mov     [rbp+arg_18], r12
0x1802b62e0  lea     rdx, CLSID_CShdocvwBroker
0x1802b62e7  mov     r8, r13
0x1802b62ea  mov     rax, [rcx]
0x1802b62ed  mov     rax, [rax+30h]
0x1802b62f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b62f6  mov     edi, eax
0x1802b62f8  test    eax, eax
0x1802b62fa  js      short loc_1802B6379
0x1802b62fc  lea     rdx, IID_IShdocvwBroker
0x1802b6303  jmp     short loc_1802B6354
0x1802b6305  lea     rcx, [rbp+var_8]
0x1802b6309  mov     [rbp+var_10], r12
0x1802b630d  mov     [rbp+var_8], r12
0x1802b6311  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1802b6318  nop     dword ptr [rax+rax+00h]
0x1802b631d  test    eax, eax
0x1802b631f  js      loc_1802B63B7
0x1802b6325  mov     rcx, [rbp+var_8]
0x1802b6329  lea     r9, [rbp+arg_18]
0x1802b632d  mov     [rbp+arg_18], r12
0x1802b6331  lea     rdx, CLSID_CShdocvwBroker
0x1802b6338  mov     r8, r13
0x1802b633b  mov     rax, [rcx]
0x1802b633e  mov     rax, [rax+30h]
0x1802b6342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b6347  mov     edi, eax
0x1802b6349  test    eax, eax
0x1802b634b  js      short loc_1802B6379
0x1802b634d  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1802b6354  mov     rcx, [rbp+arg_18]
0x1802b6358  lea     r8, [rbp+var_10]
0x1802b635c  mov     rax, [rcx]
0x1802b635f  mov     rax, [rax]
0x1802b6362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b6367  mov     rcx, [rbp+arg_18]
0x1802b636b  mov     edi, eax
0x1802b636d  mov     rax, [rcx]
0x1802b6370  mov     rax, [rax+10h]
0x1802b6374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b6379  mov     rcx, [rbp+var_8]
0x1802b637d  mov     rax, [rcx]
0x1802b6380  mov     rax, [rax+10h]
0x1802b6384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b6389  test    edi, edi
0x1802b638b  js      short loc_1802B63B7
0x1802b638d  mov     rcx, [rbp+var_10]
0x1802b6391  mov     rdx, rbx
0x1802b6394  mov     r8d, [rbp+arg_10]
0x1802b6398  mov     rax, [rcx]
0x1802b639b  mov     rax, [rax+318h]
0x1802b63a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b63a7  mov     rcx, [rbp+var_10]
0x1802b63ab  mov     rax, [rcx]
0x1802b63ae  mov     rax, [rax+10h]
0x1802b63b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b63b7  mov     rcx, rbx; hWnd
0x1802b63ba  call    cs:__imp_DestroyWindow
0x1802b63c1  nop     dword ptr [rax+rax+00h]
0x1802b63c6  xor     ecx, ecx; HWND
0x1802b63c8  call    ?TLSSetFakeModalWindow@@YAXPEAUHWND__@@@Z; TLSSetFakeModalWindow(HWND__ *)
0x1802b63cd  jmp     loc_1802B64A9
0x1802b63d2  lea     r8, [rax-1]; hData
0x1802b63d6  mov     rcx, rbx; hWnd
0x1802b63d9  lea     rdx, aFakemodalrefco; "FakeModalRefCount"
0x1802b63e0  call    cs:__imp_SetPropW
0x1802b63e7  nop     dword ptr [rax+rax+00h]
0x1802b63ec  jmp     loc_1802B64A9
0x1802b63f1  cmp     rdi, 2
0x1802b63f5  jnz     loc_1802B64A9
0x1802b63fb  lea     rcx, [rbp+var_8]
0x1802b63ff  mov     [rbp+var_10], r12
0x1802b6403  mov     [rbp+var_8], r12
0x1802b6407  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1802b640e  nop     dword ptr [rax+rax+00h]
0x1802b6413  test    eax, eax
0x1802b6415  js      loc_1802B64A9
0x1802b641b  mov     rcx, [rbp+var_8]
0x1802b641f  lea     r9, [rbp+arg_18]
0x1802b6423  mov     [rbp+arg_18], r12
0x1802b6427  lea     rdx, CLSID_CShdocvwBroker
0x1802b642e  mov     r8, r13
0x1802b6431  mov     rax, [rcx]
0x1802b6434  mov     rax, [rax+30h]
0x1802b6438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b643d  mov     ebx, eax
0x1802b643f  test    eax, eax
0x1802b6441  js      short loc_1802B646F
0x1802b6443  mov     rcx, [rbp+arg_18]
0x1802b6447  lea     r8, [rbp+var_10]
0x1802b644b  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1802b6452  mov     rax, [rcx]
0x1802b6455  mov     rax, [rax]
0x1802b6458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b645d  mov     rcx, [rbp+arg_18]
0x1802b6461  mov     ebx, eax
0x1802b6463  mov     rax, [rcx]
0x1802b6466  mov     rax, [rax+10h]
0x1802b646a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b646f  mov     rcx, [rbp+var_8]
0x1802b6473  mov     rax, [rcx]
0x1802b6476  mov     rax, [rax+10h]
0x1802b647a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b647f  test    ebx, ebx
0x1802b6481  js      short loc_1802B64A9
0x1802b6483  mov     rcx, [rbp+var_10]
0x1802b6487  mov     edx, [rbp+arg_10]
0x1802b648a  mov     rax, [rcx]
0x1802b648d  mov     rax, [rax+3A8h]
0x1802b6494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b6499  mov     rcx, [rbp+var_10]
0x1802b649d  mov     rax, [rcx]
0x1802b64a0  mov     rax, [rax+10h]
0x1802b64a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b64a9  mov     ecx, 20000001h
0x1802b64ae  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1802b64b5  nop     dword ptr [rax+rax+00h]
0x1802b64ba  test    al, al
0x1802b64bc  jnz     loc_1802B65CA
0x1802b64c2  test    r14d, r14d
0x1802b64c5  js      short loc_1802B651F
0x1802b64c7  mov     ecx, [rbp+arg_0]
0x1802b64ca  cmp     esi, ecx
0x1802b64cc  jz      short loc_1802B651F
0x1802b64ce  lea     rdx, [rbp+var_8]
0x1802b64d2  mov     [rbp+var_10], r12
0x1802b64d6  mov     [rbp+var_8], r12
0x1802b64da  call    cs:__imp_?CoCreateUserBrokerForThread@@YAJKPEAPEAUIEUserBroker@@@Z; CoCreateUserBrokerForThread(ulong,IEUserBroker * *)
0x1802b64e1  nop     dword ptr [rax+rax+00h]
0x1802b64e6  test    eax, eax
0x1802b64e8  js      loc_1802B65CA
0x1802b64ee  mov     rcx, [rbp+var_8]
0x1802b64f2  lea     r9, [rbp+arg_18]
0x1802b64f6  mov     [rbp+arg_18], r12
0x1802b64fa  lea     rdx, CLSID_CShdocvwBroker
0x1802b6501  mov     r8, r13
0x1802b6504  mov     rax, [rcx]
0x1802b6507  mov     rax, [rax+30h]
0x1802b650b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b6510  mov     ebx, eax
0x1802b6512  test    eax, eax
0x1802b6514  js      short loc_1802B6593
0x1802b6516  lea     rdx, IID_IShdocvwBroker
0x1802b651d  jmp     short loc_1802B656E
0x1802b651f  lea     rcx, [rbp+var_8]
0x1802b6523  mov     [rbp+var_10], r12
0x1802b6527  mov     [rbp+var_8], r12
0x1802b652b  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x1802b6532  nop     dword ptr [rax+rax+00h]
0x1802b6537  test    eax, eax
0x1802b6539  js      loc_1802B65CA
0x1802b653f  mov     rcx, [rbp+var_8]
0x1802b6543  lea     r9, [rbp+arg_18]
0x1802b6547  mov     [rbp+arg_18], r12
0x1802b654b  lea     rdx, CLSID_CShdocvwBroker
0x1802b6552  mov     r8, r13
0x1802b6555  mov     rax, [rcx]
0x1802b6558  mov     rax, [rax+30h]
0x1802b655c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b6561  mov     ebx, eax
0x1802b6563  test    eax, eax
0x1802b6565  js      short loc_1802B6593
0x1802b6567  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1802b656e  mov     rcx, [rbp+arg_18]
0x1802b6572  lea     r8, [rbp+var_10]
0x1802b6576  mov     rax, [rcx]
0x1802b6579  mov     rax, [rax]
0x1802b657c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b6581  mov     rcx, [rbp+arg_18]
0x1802b6585  mov     ebx, eax
0x1802b6587  mov     rax, [rcx]
0x1802b658a  mov     rax, [rax+10h]
0x1802b658e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b6593  mov     rcx, [rbp+var_8]
0x1802b6597  mov     rax, [rcx]
0x1802b659a  mov     rax, [rax+10h]
0x1802b659e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b65a3  test    ebx, ebx
0x1802b65a5  js      short loc_1802B65CA
0x1802b65a7  mov     rcx, [rbp+var_10]
0x1802b65ab  mov     rax, [rcx]
0x1802b65ae  mov     rax, [rax+320h]
0x1802b65b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b65ba  mov     rcx, [rbp+var_10]
0x1802b65be  mov     rax, [rcx]
0x1802b65c1  mov     rax, [rax+10h]
0x1802b65c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802b65ca  test    r15b, r15b
0x1802b65cd  jz      short loc_1802B65DB
0x1802b65cf  call    cs:__imp_CoUninitialize
  ... truncated ...
```
