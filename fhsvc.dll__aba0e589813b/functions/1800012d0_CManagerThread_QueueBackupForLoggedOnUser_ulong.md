# CManagerThread::QueueBackupForLoggedOnUser(ulong)

- ea: `0x1800012d0`
- end: `0x180001687`
- name: `?QueueBackupForLoggedOnUser@CManagerThread@@QEAAXK@Z`
- size: `951`
- prototype: `void __fastcall(CManagerThread *this, ULONG)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001200`
- `0x180001950`
- `0x180008180`

## callees

- `0x1800012d0`
- `0x1800065c0`
- `0x180006d38`
- `0x180008b30`
- `0x18000ca14`
- `0x180010558`
- `0x180013010`

## import_xrefs

- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800013ef`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800013ef`
- `ADVAPI32!OpenThreadToken` at `0x18000144b`
- `ADVAPI32!OpenThreadToken` at `0x18000144b`
- `ADVAPI32!SetThreadToken` at `0x180001592`
- `ADVAPI32!SetThreadToken` at `0x180001592`
- `KERNEL32!GetLastError` at `0x1800013b1`
- `KERNEL32!GetLastError` at `0x1800013f9`
- `KERNEL32!GetLastError` at `0x180001455`
- `KERNEL32!GetLastError` at `0x1800015ae`
- `KERNEL32!GetLastError` at `0x1800013b1`
- `KERNEL32!GetLastError` at `0x1800013f9`
- `KERNEL32!GetLastError` at `0x180001455`
- `KERNEL32!GetLastError` at `0x1800015ae`
- `KERNEL32!CloseHandle` at `0x1800015e9`
- `KERNEL32!CloseHandle` at `0x180001601`
- `KERNEL32!CloseHandle` at `0x1800015e9`
- `KERNEL32!CloseHandle` at `0x180001601`
- `KERNEL32!GetCurrentThread` at `0x180001432`
- `KERNEL32!GetCurrentThread` at `0x180001432`
- `WTSAPI32!WTSQueryUserToken` at `0x1800013a7`
- `WTSAPI32!WTSQueryUserToken` at `0x1800013a7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180001634`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180001634`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800014ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800014ae`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000131d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000131d`

## pseudocode

```c
void __fastcall CManagerThread::QueueBackupForLoggedOnUser(CManagerThread *this, ULONG a2)
{
  HRESULT v3; // eax
  int v4; // edi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  int LastError; // eax
  __int64 v9; // r8
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  signed int v12; // eax
  HANDLE CurrentThread; // rax
  HRESULT v14; // eax
  int v15; // eax
  HANDLE v16; // rbx
  signed int v17; // eax
  _QWORD *v18; // rdx
  __int64 v19; // [rsp+30h] [rbp-38h] BYREF
  __int64 v20[6]; // [rsp+38h] [rbp-30h] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+18h] BYREF
  HANDLE phToken; // [rsp+88h] [rbp+20h] BYREF

  TokenHandle = this;
  ppv = 0;
  v19 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  phToken = 0;
  TokenHandle = 0;
  v3 = CoInitializeEx(0, 0);
  v4 = v3;
  if ( v3 == -2147417850 || v3 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        92,
        &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
        (unsigned int)v3);
  }
  else if ( v3 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 93;
      v7 = (unsigned int)v3;
LABEL_7:
      WPP_SF_d(v5[2], v6, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, v7);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  if ( !WTSQueryUserToken(a2, &phToken) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_42;
    v11 = 94;
    goto LABEL_41;
  }
  if ( ImpersonateLoggedOnUser(phToken) )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    {
      v14 = CoCreateInstance(&CLSID_FhConfigMgr, 0, 0x17u, &GUID_e388cb3e_d90b_4e2a_a025_42c7f1e655a4, &ppv);
      if ( v14 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 97;
          v7 = (unsigned int)v14;
          goto LABEL_7;
        }
        goto LABEL_42;
      }
      v15 = LoadUserConfiguration(TokenHandle, &ppv, (__int64)&v19, 0);
      if ( v15 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 98;
          v7 = (unsigned int)v15;
          goto LABEL_7;
        }
        goto LABEL_42;
      }
      v16 = TokenHandle;
      v20[0] = ATL::CSimpleStringT<unsigned short,0>::CloneData(v19 - 24) + 24;
      LastError = CManagerThread::QueueConfig((CConfigDescriptor **)&g_ManagerThread, v20, v16, 1u, 0, 1);
      if ( LastError >= 0 )
        goto LABEL_42;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_42;
      v11 = 99;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_42;
      v11 = 96;
    }
LABEL_41:
    WPP_SF_dd(v10[2], v11, v9, a2, LastError);
    goto LABEL_42;
  }
  v12 = GetLastError();
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v6 = 95;
    v7 = (unsigned int)v12;
    goto LABEL_7;
  }
LABEL_42:
  if ( !SetThreadToken(0, 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v17 = GetLastError();
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      100,
      &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
      (unsigned int)v17);
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( phToken )
  {
    CloseHandle(phToken);
    phToken = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v4 >= 0 )
    CoUninitialize();
  v18 = (_QWORD *)(v19 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v19 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x1800012d0  mov     [rsp+TokenHandle], rcx
0x1800012d5  push    rbx
0x1800012d6  push    rbp
0x1800012d7  push    rsi
0x1800012d8  push    rdi
0x1800012d9  push    r14
0x1800012db  sub     rsp, 40h
0x1800012df  mov     esi, edx
0x1800012e1  xor     r14d, r14d
0x1800012e4  mov     [rsp+68h+arg_10], r14
0x1800012ec  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800012f3  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800012fa  mov     rax, [rax+18h]
0x1800012fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001303  add     rax, 18h
0x180001307  mov     [rsp+68h+var_38], rax
0x18000130c  mov     [rsp+68h+phToken], r14
0x180001314  mov     [rsp+68h+TokenHandle], r14
0x180001319  xor     edx, edx; dwCoInit
0x18000131b  xor     ecx, ecx; pvReserved
0x18000131d  call    cs:__imp_CoInitializeEx
0x180001323  mov     edi, eax
0x180001325  lea     rbp, WPP_GLOBAL_Control
0x18000132c  cmp     eax, 80010106h
0x180001331  jz      short loc_180001373
0x180001333  cmp     eax, 1
0x180001336  jz      short loc_180001373
0x180001338  test    eax, eax
0x18000133a  jns     short loc_18000139D
0x18000133c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001343  cmp     rcx, rbp
0x180001346  jz      loc_18000158E
0x18000134c  test    byte ptr [rcx+1Ch], 1
0x180001350  jz      loc_18000158E
0x180001356  mov     edx, 5Dh ; ']'
0x18000135b  mov     r9d, eax
0x18000135e  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180001365  mov     rcx, [rcx+10h]
0x180001369  call    WPP_SF_d
0x18000136e  jmp     loc_18000158E
0x180001373  mov     rcx, cs:WPP_GLOBAL_Control
0x18000137a  cmp     rcx, rbp
0x18000137d  jz      short loc_18000139D
0x18000137f  test    byte ptr [rcx+1Ch], 2
0x180001383  jz      short loc_18000139D
0x180001385  mov     edx, 5Ch ; '\'
0x18000138a  mov     r9d, edi
0x18000138d  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180001394  mov     rcx, [rcx+10h]
0x180001398  call    WPP_SF_d
0x18000139d  lea     rdx, [rsp+68h+phToken]; phToken
0x1800013a5  mov     ecx, esi; SessionId
0x1800013a7  call    cs:__imp_WTSQueryUserToken
0x1800013ad  test    eax, eax
0x1800013af  jnz     short loc_1800013E7
0x1800013b1  call    cs:__imp_GetLastError
0x1800013b7  test    eax, eax
0x1800013b9  jle     short loc_1800013C3
0x1800013bb  movzx   eax, ax
0x1800013be  or      eax, 80070000h
0x1800013c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800013ca  cmp     rcx, rbp
0x1800013cd  jz      loc_18000158E
0x1800013d3  test    byte ptr [rcx+1Ch], 1
0x1800013d7  jz      loc_18000158E
0x1800013dd  mov     edx, 5Eh ; '^'
0x1800013e2  jmp     loc_18000157E
0x1800013e7  mov     rcx, [rsp+68h+phToken]; hToken
0x1800013ef  call    cs:__imp_ImpersonateLoggedOnUser
0x1800013f5  test    eax, eax
0x1800013f7  jnz     short loc_180001432
0x1800013f9  call    cs:__imp_GetLastError
0x1800013ff  test    eax, eax
0x180001401  jle     short loc_18000140B
0x180001403  movzx   eax, ax
0x180001406  or      eax, 80070000h
0x18000140b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001412  cmp     rcx, rbp
0x180001415  jz      loc_18000158E
0x18000141b  test    byte ptr [rcx+1Ch], 1
0x18000141f  jz      loc_18000158E
0x180001425  mov     edx, 5Fh ; '_'
0x18000142a  mov     r9d, eax
0x18000142d  jmp     loc_18000135E
0x180001432  call    cs:__imp_GetCurrentThread
0x180001438  mov     rcx, rax; ThreadHandle
0x18000143b  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x180001440  mov     edx, 0Ch; DesiredAccess
0x180001445  mov     r8d, 1; OpenAsSelf
0x18000144b  call    cs:__imp_OpenThreadToken
0x180001451  test    eax, eax
0x180001453  jnz     short loc_18000148B
0x180001455  call    cs:__imp_GetLastError
0x18000145b  test    eax, eax
0x18000145d  jle     short loc_180001467
0x18000145f  movzx   eax, ax
0x180001462  or      eax, 80070000h
0x180001467  mov     rcx, cs:WPP_GLOBAL_Control
0x18000146e  cmp     rcx, rbp
0x180001471  jz      loc_18000158E
0x180001477  test    byte ptr [rcx+1Ch], 1
0x18000147b  jz      loc_18000158E
0x180001481  mov     edx, 60h ; '`'
0x180001486  jmp     loc_18000157E
0x18000148b  lea     rax, [rsp+68h+arg_10]
0x180001493  mov     [rsp+68h+ppv], rax; ppv
0x180001498  lea     r9, _GUID_e388cb3e_d90b_4e2a_a025_42c7f1e655a4; riid
0x18000149f  xor     edx, edx; pUnkOuter
0x1800014a1  mov     r8d, 17h; dwClsContext
0x1800014a7  lea     rcx, CLSID_FhConfigMgr; rclsid
0x1800014ae  call    cs:__imp_CoCreateInstance
0x1800014b4  test    eax, eax
0x1800014b6  jns     short loc_1800014DF
0x1800014b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800014bf  cmp     rcx, rbp
0x1800014c2  jz      loc_18000158E
0x1800014c8  test    byte ptr [rcx+1Ch], 1
0x1800014cc  jz      loc_18000158E
0x1800014d2  mov     edx, 61h ; 'a'
0x1800014d7  mov     r9d, eax
0x1800014da  jmp     loc_18000135E
0x1800014df  xor     r9d, r9d
0x1800014e2  lea     r8, [rsp+68h+var_38]
0x1800014e7  lea     rdx, [rsp+68h+arg_10]; ppv
0x1800014ef  mov     rcx, [rsp+68h+TokenHandle]; Token
0x1800014f4  call    ?LoadUserConfiguration@@YAJPEAXAEAV?$CComPtr@UIFhConfigMgrPriv@@@ATL@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEAH@Z; LoadUserConfiguration(void *,ATL::CComPtr<IFhConfigMgrPriv> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,int *)
0x1800014f9  test    eax, eax
0x1800014fb  jns     short loc_180001520
0x1800014fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180001504  cmp     rcx, rbp
0x180001507  jz      loc_18000158E
0x18000150d  test    byte ptr [rcx+1Ch], 1
0x180001511  jz      short loc_18000158E
0x180001513  mov     edx, 62h ; 'b'
0x180001518  mov     r9d, eax
0x18000151b  jmp     loc_18000135E
0x180001520  mov     rbx, [rsp+68h+TokenHandle]
0x180001525  mov     rcx, [rsp+68h+var_38]
0x18000152a  add     rcx, 0FFFFFFFFFFFFFFE8h
0x18000152e  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180001533  add     rax, 18h
0x180001537  mov     [rsp+68h+var_30], rax
0x18000153c  mov     [rsp+68h+var_40], 1
0x180001544  mov     dword ptr [rsp+68h+ppv], r14d
0x180001549  mov     r9d, 1
0x18000154f  mov     r8, rbx
0x180001552  lea     rdx, [rsp+68h+var_30]
0x180001557  lea     rcx, ?g_ManagerThread@@3VCManagerThread@@A; CManagerThread g_ManagerThread
0x18000155e  call    ?QueueConfig@CManagerThread@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAXW4FhBackupType@@KH@Z; CManagerThread::QueueConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,void *,FhBackupType,ulong,int)
0x180001563  test    eax, eax
0x180001565  jns     short loc_18000158E
0x180001567  mov     rcx, cs:WPP_GLOBAL_Control
0x18000156e  cmp     rcx, rbp
0x180001571  jz      short loc_18000158E
0x180001573  test    byte ptr [rcx+1Ch], 1
0x180001577  jz      short loc_18000158E
0x180001579  mov     edx, 63h ; 'c'
0x18000157e  mov     dword ptr [rsp+68h+ppv], eax
0x180001582  mov     r9d, esi
0x180001585  mov     rcx, [rcx+10h]
0x180001589  call    WPP_SF_dd
0x18000158e  xor     edx, edx; Token
0x180001590  xor     ecx, ecx; Thread
0x180001592  call    cs:__imp_SetThreadToken
0x180001598  test    eax, eax
0x18000159a  jnz     short loc_1800015DF
0x18000159c  mov     rax, cs:WPP_GLOBAL_Control
0x1800015a3  cmp     rax, rbp
0x1800015a6  jz      short loc_1800015DF
0x1800015a8  test    byte ptr [rax+1Ch], 1
0x1800015ac  jz      short loc_1800015DF
0x1800015ae  call    cs:__imp_GetLastError
0x1800015b4  test    eax, eax
0x1800015b6  jle     short loc_1800015C0
0x1800015b8  movzx   eax, ax
0x1800015bb  or      eax, 80070000h
0x1800015c0  mov     edx, 64h ; 'd'
0x1800015c5  mov     r9d, eax
0x1800015c8  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800015cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800015d6  mov     rcx, [rcx+10h]
0x1800015da  call    WPP_SF_d
0x1800015df  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x1800015e4  test    rcx, rcx
0x1800015e7  jz      short loc_1800015F4
0x1800015e9  call    cs:__imp_CloseHandle
0x1800015ef  mov     [rsp+68h+TokenHandle], r14
0x1800015f4  mov     rcx, [rsp+68h+phToken]; hObject
0x1800015fc  test    rcx, rcx
0x1800015ff  jz      short loc_18000160F
0x180001601  call    cs:__imp_CloseHandle
0x180001607  mov     [rsp+68h+phToken], r14
0x18000160f  mov     rcx, [rsp+68h+arg_10]
0x180001617  test    rcx, rcx
0x18000161a  jz      short loc_180001630
0x18000161c  mov     rax, [rcx]
0x18000161f  mov     rax, [rax+10h]
0x180001623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001628  mov     [rsp+68h+arg_10], r14
0x180001630  test    edi, edi
0x180001632  js      short loc_18000163A
0x180001634  call    cs:__imp_CoUninitialize
0x18000163a  mov     rdx, [rsp+68h+var_38]
0x18000163f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180001643  mov     eax, 0FFFFFFFFh
0x180001648  lock xadd [rdx+10h], eax
0x18000164d  sub     eax, 1
0x180001650  jg      short loc_180001662
0x180001652  mov     rcx, [rdx]
0x180001655  mov     rax, [rcx]
0x180001658  mov     rax, [rax+8]
0x18000165c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001661  nop
0x180001662  mov     rcx, [rsp+68h+arg_10]
0x18000166a  test    rcx, rcx
0x18000166d  jz      short loc_18000167C
0x18000166f  mov     rax, [rcx]
0x180001672  mov     rax, [rax+10h]
0x180001676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000167b  nop
0x18000167c  add     rsp, 40h
0x180001680  pop     r14
0x180001682  pop     rdi
0x180001683  pop     rsi
0x180001684  pop     rbp
0x180001685  pop     rbx
0x180001686  retn
```
