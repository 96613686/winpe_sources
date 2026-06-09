# CBackupSession::Initialize(IFhConfigMgrPriv *,IFhCatalog *)

- ea: `0x180019dd0`
- end: `0x18001a3dd`
- name: `?Initialize@CBackupSession@@UEAAJPEAUIFhConfigMgrPriv@@PEAUIFhCatalog@@@Z`
- size: `1549`
- prototype: `__int64 __fastcall(struct _FILETIME *this, struct IFhConfigMgrPriv *, struct IFhCatalog *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800031b0`
- `0x1800077f0`
- `0x180007818`
- `0x180009258`
- `0x1800093a8`
- `0x1800094ec`
- `0x18000c004`
- `0x18000eed8`
- `0x1800127b0`
- `0x18001622c`
- `0x18001768c`
- `0x180019dd0`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180019fca`
- `ADVAPI32!SetThreadToken` at `0x18001a2a1`
- `ADVAPI32!SetThreadToken` at `0x18001a2e8`
- `ADVAPI32!SetThreadToken` at `0x180019fca`
- `ADVAPI32!SetThreadToken` at `0x18001a2a1`
- `ADVAPI32!SetThreadToken` at `0x18001a2e8`
- `ADVAPI32!OpenThreadToken` at `0x180019f01`
- `ADVAPI32!OpenThreadToken` at `0x180019f01`
- `KERNEL32!GetLastError` at `0x180019fd4`
- `KERNEL32!GetLastError` at `0x18001a0ef`
- `KERNEL32!GetLastError` at `0x18001a2ab`
- `KERNEL32!GetLastError` at `0x18001a304`
- `KERNEL32!GetLastError` at `0x180019fd4`
- `KERNEL32!GetLastError` at `0x18001a0ef`
- `KERNEL32!GetLastError` at `0x18001a2ab`
- `KERNEL32!GetLastError` at `0x18001a304`
- `KERNEL32!CloseHandle` at `0x180019e8d`
- `KERNEL32!CloseHandle` at `0x180019f3f`
- `KERNEL32!CloseHandle` at `0x180019e8d`
- `KERNEL32!CloseHandle` at `0x180019f3f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180019e26`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180019e26`
- `KERNEL32!GetFileAttributesExW` at `0x18001a0ba`
- `KERNEL32!GetFileAttributesExW` at `0x18001a0ba`
- `KERNEL32!GetCurrentThread` at `0x180019eec`
- `KERNEL32!GetCurrentThread` at `0x180019eec`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a282`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a3ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a282`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a3ae`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180019ea1`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180019ea1`

## string_xrefs

- `0x18001a351`: `!impersonating`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall CBackupSession::Initialize(
        struct _FILETIME *this,
        struct IFhConfigMgrPriv *a2,
        struct IFhCatalog *a3)
{
  int v6; // r13d
  int EventListenerToken; // eax
  signed int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  HANDLE *v12; // r14
  void *v13; // rcx
  HRESULT v14; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  PVOID *v17; // rcx
  char v18; // al
  __int64 *v19; // r12
  __int64 v20; // rdi
  __int64 v21; // rax
  __int64 *v22; // r12
  struct _FILETIME v23; // rdi
  __int64 (__fastcall *v24)(struct _FILETIME, _QWORD, DWORD *, __int64, int *); // rbx
  _QWORD *v25; // rax
  signed int v26; // eax
  PVOID *v27; // rcx
  signed int v28; // eax
  int v30; // [rsp+30h] [rbp-50h] BYREF
  void *ppInterface; // [rsp+38h] [rbp-48h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-40h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-38h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-30h] BYREF
  __int128 v35; // [rsp+60h] [rbp-20h]
  unsigned int v36; // [rsp+70h] [rbp-10h]

  FileInformation = 0;
  v35 = 0;
  v36 = 0;
  lpFileName = 0;
  ppInterface = 0;
  v30 = 0;
  v6 = 0;
  GetSystemTimeAsFileTime(this + 97);
  EventListenerToken = CSessionBaseRW::Initialize((CSessionBaseRW *)&this[1], a2, a3);
  v8 = EventListenerToken;
  if ( EventListenerToken < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 11;
LABEL_5:
      v11 = (unsigned int)EventListenerToken;
LABEL_6:
      WPP_SF_d(v9[2], v10, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v11);
      goto LABEL_79;
    }
    goto LABEL_79;
  }
  v12 = (HANDLE *)&this[48];
  v13 = (void *)this[48];
  if ( v13 )
  {
    CloseHandle(v13);
    *v12 = 0;
  }
  v14 = CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, &ppInterface);
  v8 = v14;
  if ( v14 != -2147417833 )
  {
    if ( !v14 )
    {
      if ( (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface) )
        goto LABEL_14;
      v8 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
      if ( v8 >= 0 )
      {
        v6 = 1;
        goto LABEL_14;
      }
LABEL_27:
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_79;
      v10 = 12;
      goto LABEL_30;
    }
    if ( v14 < 0 )
      goto LABEL_27;
  }
LABEL_14:
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, (PHANDLE)&this[48]) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
    if ( *v12 )
    {
      CloseHandle(*v12);
      *v12 = 0;
    }
  }
  if ( ppInterface )
  {
    if ( v6 )
    {
      v6 = 0;
      EventListenerToken = (*(__int64 (**)(void))(*(_QWORD *)ppInterface + 40LL))();
      v8 = EventListenerToken;
      if ( EventListenerToken < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 14;
          goto LABEL_5;
        }
        goto LABEL_79;
      }
    }
  }
  if ( !SetThreadToken(0, 0) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_79;
    v10 = 15;
LABEL_30:
    v11 = (unsigned int)v8;
    goto LABEL_6;
  }
  EventListenerToken = CBackupSession::CreateEventListenerToken((CBackupSession *)this);
  v8 = EventListenerToken;
  if ( EventListenerToken < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 16;
      goto LABEL_5;
    }
    goto LABEL_79;
  }
  EventListenerToken = CSessionBaseRW::CacheUserSid((CSessionBaseRW *)&this[1], *v12);
  v8 = EventListenerToken;
  if ( EventListenerToken < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 17;
      goto LABEL_5;
    }
    goto LABEL_79;
  }
  EventListenerToken = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR *))(**(_QWORD **)&this[3] + 72LL))(
                         *(_QWORD *)&this[3],
                         &lpFileName);
  v8 = EventListenerToken;
  if ( EventListenerToken < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 18;
      goto LABEL_5;
    }
    goto LABEL_79;
  }
  if ( GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
  {
    this[53] = (struct _FILETIME)(v36 + ((unsigned __int64)HIDWORD(v35) << 32));
  }
  else
  {
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v18 = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (_DWORD)lpFileName,
          v18);
        v17 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 4) != 0 )
        WPP_SF_ss(
          (unsigned int)v17[2],
          20,
          (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (unsigned int)"FALSE",
          (__int64)"Unable to get the current size of the Catalog");
    }
  }
  v19 = (__int64 *)&this[62];
  EventListenerToken = (*(__int64 (__fastcall **)(_QWORD, __int64, struct _FILETIME *))(**(_QWORD **)&this[2] + 64LL))(
                         *(_QWORD *)&this[2],
                         5,
                         this + 62);
  v8 = EventListenerToken;
  if ( EventListenerToken < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 21;
      goto LABEL_5;
    }
    goto LABEL_79;
  }
  v20 = -1;
  v21 = -1;
  if ( (unsigned __int64)*v19 <= 0xC22E45067289LL )
    v21 = 86400 * *v19;
  *v19 = v21;
  v22 = (__int64 *)&this[63];
  EventListenerToken = (*(__int64 (__fastcall **)(_QWORD, __int64, struct _FILETIME *))(**(_QWORD **)&this[2] + 64LL))(
                         *(_QWORD *)&this[2],
                         6,
                         this + 63);
  v8 = EventListenerToken;
  if ( EventListenerToken < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 22;
      goto LABEL_5;
    }
    goto LABEL_79;
  }
  if ( (unsigned __int64)*v22 <= 0xC22E45067289LL )
    v20 = 86400 * *v22;
  *v22 = v20;
  v30 = 4;
  v23 = this[3];
  v24 = *(__int64 (__fastcall **)(struct _FILETIME, _QWORD, DWORD *, __int64, int *))(**(_QWORD **)&v23 + 176LL);
  v25 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"LastReassociationBSet");
  v8 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))v24)(
         v23,
         *v25,
         &this[47].dwHighDateTime,
         4,
         &v30);
  SysFreeString(bstrString);
  if ( v8 < 0 || v30 != 4 )
  {
    this[47].dwHighDateTime = 0;
    v8 = 0;
  }
  if ( SetThreadToken(0, *v12) )
  {
    CBackupSession::CalculateRetentionThresholds((CBackupSession *)this);
    goto LABEL_79;
  }
  v26 = GetLastError();
  v8 = v26;
  if ( v26 > 0 )
    v8 = (unsigned __int16)v26 | 0x80070000;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 23;
    goto LABEL_30;
  }
LABEL_79:
  if ( SetThreadToken(0, 0) )
  {
LABEL_85:
    v27 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_86;
  }
  v27 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v28 = GetLastError();
    if ( v28 > 0 )
      v28 = (unsigned __int16)v28 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      (unsigned int)v28);
    goto LABEL_85;
  }
LABEL_86:
  if ( v6 && v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 4) != 0 )
    WPP_SF_s(v27[2], 25, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, "!impersonating");
  this[99].dwLowDateTime = v8;
  if ( v8 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, "SUCCEEDED(hr)");
  ATL::CComPtrBase<IFhScopeIterator>::~CComPtrBase<IFhScopeIterator>(&ppInterface);
  SysFreeString((BSTR)lpFileName);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180019dd0  mov     [rsp-38h+arg_18], rbx
0x180019dd5  push    rbp
0x180019dd6  push    rsi
0x180019dd7  push    rdi
0x180019dd8  push    r12
0x180019dda  push    r13
0x180019ddc  push    r14
0x180019dde  push    r15
0x180019de0  mov     rbp, rsp
0x180019de3  sub     rsp, 80h
0x180019dea  mov     rax, cs:__security_cookie
0x180019df1  xor     rax, rsp
0x180019df4  mov     [rbp+var_8], rax
0x180019df8  mov     rdi, r8
0x180019dfb  mov     rbx, rdx
0x180019dfe  mov     r15, rcx
0x180019e01  xorps   xmm0, xmm0
0x180019e04  xor     eax, eax
0x180019e06  movups  [rbp+FileInformation], xmm0
0x180019e0a  movups  [rbp+var_20], xmm0
0x180019e0e  mov     [rbp+var_10], eax
0x180019e11  mov     [rbp+lpFileName], rax
0x180019e15  mov     [rbp+ppInterface], rax
0x180019e19  mov     [rbp+var_50], eax
0x180019e1c  xor     r13d, r13d
0x180019e1f  add     rcx, 308h; lpSystemTimeAsFileTime
0x180019e26  call    cs:__imp_GetSystemTimeAsFileTime
0x180019e2c  mov     r8, rdi; struct IFhCatalog *
0x180019e2f  mov     rdx, rbx; struct IFhConfigMgrPriv *
0x180019e32  lea     rcx, [r15+8]; this
0x180019e36  call    ?Initialize@CSessionBaseRW@@IEAAJPEAUIFhConfigMgrPriv@@PEAUIFhCatalog@@@Z; CSessionBaseRW::Initialize(IFhConfigMgrPriv *,IFhCatalog *)
0x180019e3b  mov     ebx, eax
0x180019e3d  test    eax, eax
0x180019e3f  jns     short loc_180019E7E
0x180019e41  lea     rsi, WPP_GLOBAL_Control
0x180019e48  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e4f  cmp     rcx, rsi
0x180019e52  jz      loc_18001A2E4
0x180019e58  test    byte ptr [rcx+1Ch], 1
0x180019e5c  jz      loc_18001A2E4
0x180019e62  lea     edx, [r13+0Bh]
0x180019e66  mov     r9d, eax
0x180019e69  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180019e70  mov     rcx, [rcx+10h]
0x180019e74  call    WPP_SF_d
0x180019e79  jmp     loc_18001A2E4
0x180019e7e  lea     r14, [r15+180h]
0x180019e85  mov     rcx, [r14]; hObject
0x180019e88  test    rcx, rcx
0x180019e8b  jz      short loc_180019E96
0x180019e8d  call    cs:__imp_CloseHandle
0x180019e93  mov     [r14], r13
0x180019e96  lea     rdx, [rbp+ppInterface]; ppInterface
0x180019e9a  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x180019ea1  call    cs:__imp_CoGetCallContext
0x180019ea7  mov     ebx, eax
0x180019ea9  cmp     eax, 80010117h
0x180019eae  jz      short loc_180019EEC
0x180019eb0  test    eax, eax
0x180019eb2  jnz     loc_180019F92
0x180019eb8  mov     rcx, [rbp+ppInterface]
0x180019ebc  mov     rax, [rcx]
0x180019ebf  mov     rax, [rax+30h]
0x180019ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ec8  test    eax, eax
0x180019eca  jnz     short loc_180019EEC
0x180019ecc  mov     rcx, [rbp+ppInterface]
0x180019ed0  mov     rax, [rcx]
0x180019ed3  mov     rax, [rax+20h]
0x180019ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019edc  mov     ebx, eax
0x180019ede  test    eax, eax
0x180019ee0  js      loc_180019F98
0x180019ee6  mov     r13d, 1
0x180019eec  call    cs:__imp_GetCurrentThread
0x180019ef2  mov     rcx, rax; ThreadHandle
0x180019ef5  mov     r9, r14; TokenHandle
0x180019ef8  mov     edx, 0Ch; DesiredAccess
0x180019efd  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180019f01  call    cs:__imp_OpenThreadToken
0x180019f07  lea     rsi, WPP_GLOBAL_Control
0x180019f0e  test    eax, eax
0x180019f10  jnz     short loc_180019F4C
0x180019f12  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f19  cmp     rcx, rsi
0x180019f1c  jz      short loc_180019F37
0x180019f1e  test    byte ptr [rcx+1Ch], 2
0x180019f22  jz      short loc_180019F37
0x180019f24  lea     edx, [rax+0Dh]
0x180019f27  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180019f2e  mov     rcx, [rcx+10h]
0x180019f32  call    WPP_SF_
0x180019f37  mov     rcx, [r14]; hObject
0x180019f3a  test    rcx, rcx
0x180019f3d  jz      short loc_180019F4C
0x180019f3f  call    cs:__imp_CloseHandle
0x180019f45  mov     qword ptr [r14], 0
0x180019f4c  mov     rcx, [rbp+ppInterface]
0x180019f50  test    rcx, rcx
0x180019f53  jz      short loc_180019FC6
0x180019f55  test    r13d, r13d
0x180019f58  jz      short loc_180019FC6
0x180019f5a  xor     r13d, r13d
0x180019f5d  mov     rax, [rcx]
0x180019f60  mov     rax, [rax+28h]
0x180019f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f69  mov     ebx, eax
0x180019f6b  test    eax, eax
0x180019f6d  jns     short loc_180019FC6
0x180019f6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019f76  cmp     rcx, rsi
0x180019f79  jz      loc_18001A2E4
0x180019f7f  test    byte ptr [rcx+1Ch], 1
0x180019f83  jz      loc_18001A2E4
0x180019f89  lea     edx, [r13+0Eh]
0x180019f8d  jmp     loc_180019E66
0x180019f92  jns     loc_180019EEC
0x180019f98  lea     rsi, WPP_GLOBAL_Control
0x180019f9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fa6  cmp     rcx, rsi
0x180019fa9  jz      loc_18001A2E4
0x180019faf  test    byte ptr [rcx+1Ch], 1
0x180019fb3  jz      loc_18001A2E4
0x180019fb9  mov     edx, 0Ch
0x180019fbe  mov     r9d, ebx
0x180019fc1  jmp     loc_180019E69
0x180019fc6  xor     edx, edx; Token
0x180019fc8  xor     ecx, ecx; Thread
0x180019fca  call    cs:__imp_SetThreadToken
0x180019fd0  test    eax, eax
0x180019fd2  jnz     short loc_18001A00A
0x180019fd4  call    cs:__imp_GetLastError
0x180019fda  mov     ebx, eax
0x180019fdc  test    eax, eax
0x180019fde  jle     short loc_180019FE9
0x180019fe0  movzx   ebx, ax
0x180019fe3  or      ebx, 80070000h
0x180019fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ff0  cmp     rcx, rsi
0x180019ff3  jz      loc_18001A2E4
0x180019ff9  test    byte ptr [rcx+1Ch], 1
0x180019ffd  jz      loc_18001A2E4
0x18001a003  mov     edx, 0Fh
0x18001a008  jmp     short loc_180019FBE
0x18001a00a  mov     rcx, r15; this
0x18001a00d  call    ?CreateEventListenerToken@CBackupSession@@AEAAJXZ; CBackupSession::CreateEventListenerToken(void)
0x18001a012  mov     ebx, eax
0x18001a014  test    eax, eax
0x18001a016  jns     short loc_18001A03C
0x18001a018  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a01f  cmp     rcx, rsi
0x18001a022  jz      loc_18001A2E4
0x18001a028  test    byte ptr [rcx+1Ch], 1
0x18001a02c  jz      loc_18001A2E4
0x18001a032  mov     edx, 10h
0x18001a037  jmp     loc_180019E66
0x18001a03c  mov     rdx, [r14]; void *
0x18001a03f  lea     rcx, [r15+8]; this
0x18001a043  call    ?CacheUserSid@CSessionBaseRW@@IEAAJPEAX@Z; CSessionBaseRW::CacheUserSid(void *)
0x18001a048  mov     ebx, eax
0x18001a04a  test    eax, eax
0x18001a04c  jns     short loc_18001A072
0x18001a04e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a055  cmp     rcx, rsi
0x18001a058  jz      loc_18001A2E4
0x18001a05e  test    byte ptr [rcx+1Ch], 1
0x18001a062  jz      loc_18001A2E4
0x18001a068  mov     edx, 11h
0x18001a06d  jmp     loc_180019E66
0x18001a072  mov     rcx, [r15+18h]
0x18001a076  mov     rax, [rcx]
0x18001a079  lea     rdx, [rbp+lpFileName]
0x18001a07d  mov     rax, [rax+48h]
0x18001a081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a086  mov     ebx, eax
0x18001a088  test    eax, eax
0x18001a08a  jns     short loc_18001A0B0
0x18001a08c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a093  cmp     rcx, rsi
0x18001a096  jz      loc_18001A2E4
0x18001a09c  test    byte ptr [rcx+1Ch], 1
0x18001a0a0  jz      loc_18001A2E4
0x18001a0a6  mov     edx, 12h
0x18001a0ab  jmp     loc_180019E66
0x18001a0b0  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18001a0b4  xor     edx, edx; fInfoLevelId
0x18001a0b6  mov     rcx, [rbp+lpFileName]; lpFileName
0x18001a0ba  call    cs:__imp_GetFileAttributesExW
0x18001a0c0  test    eax, eax
0x18001a0c2  jz      short loc_18001A0DD
0x18001a0c4  mov     ecx, dword ptr [rbp+var_20+0Ch]
0x18001a0c7  shl     rcx, 20h
0x18001a0cb  mov     eax, [rbp+var_10]
0x18001a0ce  add     rcx, rax
0x18001a0d1  mov     [r15+1A8h], rcx
0x18001a0d8  jmp     loc_18001A15F
0x18001a0dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0e4  cmp     rcx, rsi
0x18001a0e7  jz      short loc_18001A15F
0x18001a0e9  test    byte ptr [rcx+1Ch], 2
0x18001a0ed  jz      short loc_18001A12C
0x18001a0ef  call    cs:__imp_GetLastError
0x18001a0f5  test    eax, eax
0x18001a0f7  jle     short loc_18001A101
0x18001a0f9  movzx   eax, ax
0x18001a0fc  or      eax, 80070000h
0x18001a101  mov     edx, 13h
0x18001a106  mov     dword ptr [rsp+80h+var_60], eax
0x18001a10a  mov     r9, [rbp+lpFileName]
0x18001a10e  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001a115  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a11c  mov     rcx, [rcx+10h]
0x18001a120  call    WPP_SF_Sd
0x18001a125  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a12c  cmp     rcx, rsi
0x18001a12f  jz      short loc_18001A15F
0x18001a131  test    byte ptr [rcx+1Ch], 4
0x18001a135  jz      short loc_18001A15F
0x18001a137  mov     edx, 14h
0x18001a13c  lea     rax, aUnableToGetThe; "Unable to get the current size of the C"...
0x18001a143  mov     [rsp+80h+var_60], rax
0x18001a148  lea     r9, aFalse; "FALSE"
0x18001a14f  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001a156  mov     rcx, [rcx+10h]
0x18001a15a  call    WPP_SF_ss
0x18001a15f  mov     rcx, [r15+10h]
0x18001a163  lea     r12, [r15+1F0h]
0x18001a16a  mov     rax, [rcx]
0x18001a16d  mov     r8, r12
0x18001a170  mov     edx, 5
0x18001a175  mov     rax, [rax+40h]
0x18001a179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a17e  mov     ebx, eax
0x18001a180  test    eax, eax
0x18001a182  jns     short loc_18001A1A8
0x18001a184  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a18b  cmp     rcx, rsi
0x18001a18e  jz      loc_18001A2E4
0x18001a194  test    byte ptr [rcx+1Ch], 1
0x18001a198  jz      loc_18001A2E4
0x18001a19e  mov     edx, 15h
0x18001a1a3  jmp     loc_180019E66
0x18001a1a8  mov     rax, 0C22E45067289h
0x18001a1b2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001a1b6  cmp     [r12], rax
0x18001a1ba  mov     rax, rdi
0x18001a1bd  ja      short loc_18001A1C7
0x18001a1bf  imul    rax, [r12], 15180h
0x18001a1c7  mov     [r12], rax
0x18001a1cb  mov     rcx, [r15+10h]
0x18001a1cf  lea     r12, [r15+1F8h]
0x18001a1d6  mov     rax, [rcx]
0x18001a1d9  mov     r8, r12
0x18001a1dc  mov     edx, 6
0x18001a1e1  mov     rax, [rax+40h]
0x18001a1e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1ea  mov     ebx, eax
0x18001a1ec  test    eax, eax
0x18001a1ee  jns     short loc_18001A214
0x18001a1f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1f7  cmp     rcx, rsi
0x18001a1fa  jz      loc_18001A2E4
0x18001a200  test    byte ptr [rcx+1Ch], 1
0x18001a204  jz      loc_18001A2E4
0x18001a20a  mov     edx, 16h
0x18001a20f  jmp     loc_180019E66
0x18001a214  mov     rax, 0C22E45067289h
0x18001a21e  cmp     [r12], rax
0x18001a222  ja      short loc_18001A22C
0x18001a224  imul    rdi, [r12], 15180h
0x18001a22c  mov     [r12], rdi
0x18001a230  mov     [rbp+var_50], 4
0x18001a237  mov     rdi, [r15+18h]
0x18001a23b  mov     rax, [rdi]
0x18001a23e  mov     rbx, [rax+0B0h]
0x18001a245  lea     rdx, aLastreassociat; "LastReassociationBSet"
0x18001a24c  lea     rcx, [rbp+bstrString]; this
0x18001a250  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001a255  lea     r12, [r15+17Ch]
0x18001a25c  lea     rcx, [rbp+var_50]
0x18001a260  mov     [rsp+80h+var_60], rcx
0x18001a265  mov     r9d, 4
0x18001a26b  mov     r8, r12
0x18001a26e  mov     rdx, [rax]
0x18001a271  mov     rcx, rdi
0x18001a274  mov     rax, rbx
0x18001a277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a27c  mov     ebx, eax
0x18001a27e  mov     rcx, [rbp+bstrString]; bstrString
0x18001a282  call    cs:__imp_SysFreeString
0x18001a288  test    ebx, ebx
0x18001a28a  js      short loc_18001A292
0x18001a28c  cmp     [rbp+var_50], 4
0x18001a290  jz      short loc_18001A29C
0x18001a292  mov     dword ptr [r12], 0
0x18001a29a  xor     ebx, ebx
0x18001a29c  mov     rdx, [r14]; Token
0x18001a29f  xor     ecx, ecx; Thread
0x18001a2a1  call    cs:__imp_SetThreadToken
0x18001a2a7  test    eax, eax
  ... truncated ...
```
