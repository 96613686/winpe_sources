# SendContactInfoThread(void *)

- ea: `0x14002f0d0`
- end: `0x14002f60d`
- name: `?SendContactInfoThread@@YAKPEAX@Z`
- size: `1341`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001cc4`
- `0x140027098`
- `0x1400289a8`
- `0x140029334`
- `0x14002b3c8`
- `0x14002f0d0`
- `0x140034ce4`
- `0x140035888`
- `0x140041998`
- `0x140041a4c`
- `0x140041cc8`
- `0x140041d58`
- `0x140042ba8`
- `0x140043e00`
- `0x140044508`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x14002f3a1`
- `KERNEL32!ResetEvent` at `0x14002f3a1`
- `KERNEL32!DeleteFileW` at `0x14002f53d`
- `KERNEL32!DeleteFileW` at `0x14002f573`
- `KERNEL32!DeleteFileW` at `0x14002f53d`
- `KERNEL32!DeleteFileW` at `0x14002f573`
- `KERNEL32!CreateEventW` at `0x14002f380`
- `KERNEL32!CreateEventW` at `0x14002f380`
- `KERNEL32!WaitForSingleObject` at `0x14002f186`
- `KERNEL32!WaitForSingleObject` at `0x14002f3c5`
- `KERNEL32!WaitForSingleObject` at `0x14002f186`
- `KERNEL32!WaitForSingleObject` at `0x14002f3c5`
- `USER32!PostMessageW` at `0x14002f5b1`
- `USER32!PostMessageW` at `0x14002f5b1`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002f5c5`
- `msvcrt!??3@YAXPEAX@Z` at `0x14002f5c5`
- `ole32!CoUninitialize` at `0x14002f5d1`
- `ole32!CoUninitialize` at `0x14002f5d1`
- `ole32!CoInitialize` at `0x14002f167`
- `ole32!CoInitialize` at `0x14002f167`
- `OLEAUT32!__imp_SysFreeString` at `0x14002f551`
- `OLEAUT32!__imp_SysFreeString` at `0x14002f58e`
- `OLEAUT32!__imp_SysFreeString` at `0x14002f551`
- `OLEAUT32!__imp_SysFreeString` at `0x14002f58e`

## string_xrefs

- `0x14002f1ef`: `SendContactInfoThread`
- `0x14002f50f`: `SendContactInfoThread`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SendContactInfoThread(PVOID Parameter)
{
  int v1; // esi
  unsigned __int16 *v2; // rdi
  unsigned __int16 *v3; // r14
  char *v4; // rax
  HWND v5; // r15
  signed int v6; // ebx
  signed int DirectoryAsBSTR; // eax
  CEventLogger *v8; // rcx
  signed int SelfHistoryItem; // eax
  CEventLogger *v10; // rcx
  unsigned int v11; // r9d
  signed int v12; // eax
  CEventLogger *v13; // rcx
  unsigned __int16 *v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // r9d
  CEventLogger *v17; // rdx
  __int64 v18; // rcx
  _BYTE *v19; // rax
  signed int v20; // eax
  CEventLogger *v21; // rcx
  CEventLogger *v22; // rcx
  HANDLE EventW; // rax
  unsigned __int16 *v24; // rsi
  signed int v25; // eax
  CEventLogger *v26; // rcx
  CEventLogger *v27; // rcx
  signed int v28; // eax
  CEventLogger *v29; // rcx
  signed int v30; // eax
  CEventLogger *v31; // rcx
  signed int v32; // eax
  CEventLogger *v33; // rcx
  const WCHAR *v34; // rsi
  LPARAM v35; // r9
  enum __MIDL___MIDL_itf_rdpencomapi_0000_0000_0003 v37; // [rsp+20h] [rbp-E0h]
  _OWORD v38[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h]
  __int128 v40; // [rsp+58h] [rbp-A8h]
  int v41; // [rsp+68h] [rbp-98h]
  _DWORD v42[122]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v43[7]; // [rsp+258h] [rbp+158h] BYREF
  unsigned __int16 *v44; // [rsp+2A0h] [rbp+1A0h] BYREF
  LPCWSTR lpFileName; // [rsp+2A8h] [rbp+1A8h] BYREF

  v1 = (int)Parameter;
  v2 = 0;
  v40 = 0;
  v41 = 0;
  memset(v38, 0, sizeof(v38));
  v39 = 0;
  v42[0] = 0;
  v42[1] = 1;
  v43[1] = v43;
  v43[0] = v43;
  v3 = 0;
  v44 = 0;
  lpFileName = 0;
  if ( Parameter )
    v4 = (char *)_AtlModule + 272;
  else
    v4 = (char *)_AtlModule + 72;
  v5 = (HWND)*((_QWORD *)v4 + 1);
  CoInitialize(0);
  if ( !WaitForSingleObject(*((HANDLE *)_AtlModule + 106), 0x2710u) )
  {
    v6 = -2147467259;
    goto LABEL_47;
  }
  DirectoryAsBSTR = GetDirectoryAsBSTR(0, (unsigned __int16 **)&lpFileName, L"RaRemoteContact");
  v6 = DirectoryAsBSTR;
  if ( DirectoryAsBSTR < 0 )
  {
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
      0x387u,
      L"SendContactInfoThread",
      DirectoryAsBSTR);
    goto LABEL_47;
  }
  SelfHistoryItem = GetDirectoryAsBSTR(0, &v44, L"RaMeContact");
  v6 = SelfHistoryItem;
  if ( SelfHistoryItem < 0 )
  {
    v11 = 904;
LABEL_10:
    CEventLogger::LogError(
      v10,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
      v11,
      L"SendContactInfoThread",
      SelfHistoryItem);
    v3 = v44;
    goto LABEL_47;
  }
  SelfHistoryItem = CreateSelfHistoryItem((struct CRAInvitationHistoryItem *)v38);
  v6 = SelfHistoryItem;
  if ( SelfHistoryItem < 0 )
  {
    v11 = 905;
    goto LABEL_10;
  }
  SelfHistoryItem = CRAInvitationHistoryManager::put_InvitationItem(
                      (CRAInvitationHistoryManager *)v42,
                      (struct CRAInvitationHistoryItem *)v38);
  v6 = SelfHistoryItem;
  if ( SelfHistoryItem < 0 )
  {
    v11 = 906;
    goto LABEL_10;
  }
  v3 = v44;
  v12 = CRAInvitationHistoryManager::SaveRAInvitationsHistory((CRAInvitationHistoryManager *)v42, v44);
  v6 = v12;
  if ( v12 < 0 )
  {
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
      0x38Bu,
      L"SendContactInfoThread",
      v12);
    goto LABEL_47;
  }
  v14 = (unsigned __int16 *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  v2 = v14;
  v44 = v14;
  if ( !v14 )
  {
    v2 = 0;
LABEL_46:
    v6 = -2147024882;
    CEventLogger::LogError(
      (CEventLogger *)v15,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
      0x38Fu,
      L"SendContactInfoThread",
      0x8007000E);
    goto LABEL_47;
  }
  v17 = _AtlModule;
  *((_QWORD *)v14 + 7) = *((_QWORD *)_AtlModule + 104);
  *((_QWORD *)v14 + 8) = 0;
  *((_QWORD *)v14 + 9) = 0;
  v18 = 16;
  do
  {
    *(_BYTE *)v14 = 0;
    v14 = (unsigned __int16 *)((char *)v14 + 1);
    --v18;
  }
  while ( v18 );
  v15 = 40;
  v19 = v2 + 8;
  do
  {
    *v19++ = 0;
    --v15;
  }
  while ( v15 );
  if ( !v2 )
    goto LABEL_46;
  if ( !*(_DWORD *)(*((_QWORD *)v2 + 7) + 460LL) )
  {
    v6 = -2147418113;
    CEventLogger::LogError(
      0,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
      0x397u,
      L"SendContactInfoThread",
      0x8000FFFF);
    goto LABEL_47;
  }
  *(_DWORD *)v2 = 180000;
  *((_DWORD *)v2 + 1) = 1;
  *((_QWORD *)v2 + 1) = &SendFileClientCallback;
  *((_QWORD *)v2 + 5) = v2;
  v20 = RAFileXferClient::SendFile(
          (RAFileXferClient *)v2,
          -(*(_QWORD *)(*((_QWORD *)v17 + 104) + 208LL) != 0),
          v3,
          v16,
          v37);
  v6 = v20;
  if ( v20 < 0 )
  {
    CEventLogger::LogError(
      v21,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
      0x39Cu,
      L"SendContactInfoThread",
      v20);
    goto LABEL_47;
  }
  v22 = _AtlModule;
  if ( !*((_QWORD *)_AtlModule + 107) )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    v22 = _AtlModule;
    *((_QWORD *)_AtlModule + 107) = EventW;
  }
  ResetEvent(*((HANDLE *)v22 + 107));
  if ( v1 == 1 || !WaitForSingleObject(*((HANDLE *)_AtlModule + 107), 0x493E0u) )
  {
    v24 = (unsigned __int16 *)lpFileName;
    if ( (unsigned int)FileExists(lpFileName) )
    {
      v25 = CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory((CRAInvitationHistoryManager *)v42, v24);
      v6 = v25;
      if ( v25 < 0 )
      {
        CEventLogger::LogError(
          v26,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
          0x3BAu,
          L"SendContactInfoThread",
          v25);
        goto LABEL_47;
      }
      if ( v42[0] - 1 < 0 )
      {
        v6 = -2147024809;
        CEventLogger::LogError(
          v26,
          &Recoverable_Error,
          (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
          0x37Cu,
          L"CRAInvitationHistoryManager::get_InvitationItem",
          0x80070057);
LABEL_40:
        CEventLogger::LogError(
          v27,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
          0x3BBu,
          L"SendContactInfoThread",
          v6);
        goto LABEL_47;
      }
      v27 = (CEventLogger *)v43;
      if ( (_QWORD *)v43[0] == v43 )
      {
        v6 = -2147418113;
        goto LABEL_40;
      }
      v28 = CRAInvitationHistoryManager::CloneHistoryItem(
              (CRAInvitationHistoryManager *)v43,
              *(struct CRAInvitationHistoryItem **)(v43[0] + 16LL),
              (struct CRAInvitationHistoryItem *)v38);
      v6 = v28;
      if ( v28 < 0 )
      {
        CEventLogger::LogError(
          v29,
          &Recoverable_Error,
          (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
          0x394u,
          L"CRAInvitationHistoryManager::get_InvitationItem",
          v28);
        goto LABEL_40;
      }
      GetInvitationManagerLoaded((struct CRAInvitationHistoryManager *)v42, 3);
      v30 = CRAInvitationHistoryManager::put_InvitationItem(
              (CRAInvitationHistoryManager *)v42,
              (struct CRAInvitationHistoryItem *)v38);
      v6 = v30;
      if ( v30 >= 0 )
      {
        v32 = SaveInvitationHistory((struct CRAInvitationHistoryManager *)v42, 3);
        v6 = v32;
        if ( v32 < 0 )
          CEventLogger::LogError(
            v33,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
            0x3BEu,
            L"SendContactInfoThread",
            v32);
      }
      else
      {
        CEventLogger::LogError(
          v31,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\filexfer.cpp",
          0x3BDu,
          L"SendContactInfoThread",
          v30);
      }
    }
  }
LABEL_47:
  if ( (unsigned int)FileExists(v3) )
    DeleteFileW(v3);
  if ( v3 )
    SysFreeString(v3);
  v34 = lpFileName;
  if ( (unsigned int)FileExists(lpFileName) )
    DeleteFileW(v34);
  if ( lpFileName )
    SysFreeString((BSTR)lpFileName);
  v35 = 4;
  if ( v6 >= 0 )
    v35 = 2;
  PostMessageW(v5, 0x801Bu, 0, v35);
  if ( v2 )
    operator delete(v2);
  CoUninitialize();
  CRAInvitationHistoryManager::EmptyList((CRAInvitationHistoryManager *)v42);
  CRAInvitationHistoryItem::~CRAInvitationHistoryItem((CRAInvitationHistoryItem *)v38);
  return 0;
}

```

## disassembly

```asm
0x14002f0d0  mov     [rsp-8+arg_10], rbx
0x14002f0d5  push    rbp
0x14002f0d6  push    rsi
0x14002f0d7  push    rdi
0x14002f0d8  push    r14
0x14002f0da  push    r15
0x14002f0dc  lea     rbp, [rsp-170h]
0x14002f0e4  sub     rsp, 270h
0x14002f0eb  mov     rsi, rcx
0x14002f0ee  xor     edi, edi
0x14002f0f0  xorps   xmm0, xmm0
0x14002f0f3  movups  [rsp+290h+var_238], xmm0
0x14002f0f8  mov     [rsp+290h+var_228], edi
0x14002f0fc  xorps   xmm1, xmm1
0x14002f0ff  movdqa  [rsp+290h+var_260], xmm1
0x14002f105  movdqa  [rsp+290h+var_250], xmm0
0x14002f10b  mov     [rsp+290h+var_240], rdi
0x14002f110  mov     [rsp+290h+var_220], edi
0x14002f114  mov     [rsp+290h+var_21C], 1
0x14002f11c  lea     rax, [rbp+190h+var_38]
0x14002f123  mov     [rbp+190h+var_30], rax
0x14002f12a  lea     rax, [rbp+190h+var_38]
0x14002f131  mov     [rbp+190h+var_38], rax
0x14002f138  xor     r14d, r14d
0x14002f13b  mov     [rbp+190h+arg_0], r14
0x14002f142  mov     [rbp+190h+lpFileName], r14
0x14002f149  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002f150  test    rcx, rcx
0x14002f153  jz      short loc_14002F15D
0x14002f155  add     rax, 110h
0x14002f15b  jmp     short loc_14002F161
0x14002f15d  add     rax, 48h ; 'H'
0x14002f161  mov     r15, [rax+8]
0x14002f165  xor     ecx, ecx; pvReserved
0x14002f167  call    cs:__imp_CoInitialize
0x14002f16e  nop     dword ptr [rax+rax+00h]
0x14002f173  mov     edx, 2710h; dwMilliseconds
0x14002f178  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002f17f  mov     rcx, [rcx+350h]; hHandle
0x14002f186  call    cs:__imp_WaitForSingleObject
0x14002f18d  nop     dword ptr [rax+rax+00h]
0x14002f192  test    eax, eax
0x14002f194  jnz     short loc_14002F1A0
0x14002f196  mov     ebx, 80004005h
0x14002f19b  jmp     loc_14002F52E
0x14002f1a0  lea     r8, aRaremotecontac; "RaRemoteContact"
0x14002f1a7  lea     rdx, [rbp+190h+lpFileName]; unsigned __int16 **
0x14002f1ae  xor     ecx, ecx; csidl
0x14002f1b0  call    ?GetDirectoryAsBSTR@@YAJHPEAPEAGPEAG@Z; GetDirectoryAsBSTR(int,ushort * *,ushort *)
0x14002f1b5  mov     ebx, eax
0x14002f1b7  test    eax, eax
0x14002f1b9  jns     short loc_14002F1CA
0x14002f1bb  mov     [rsp+290h+var_268], eax
0x14002f1bf  mov     r9d, 387h
0x14002f1c5  jmp     loc_14002F50F
0x14002f1ca  lea     r8, aRamecontact; "RaMeContact"
0x14002f1d1  lea     rdx, [rbp+190h+arg_0]; unsigned __int16 **
0x14002f1d8  xor     ecx, ecx; csidl
0x14002f1da  call    ?GetDirectoryAsBSTR@@YAJHPEAPEAGPEAG@Z; GetDirectoryAsBSTR(int,ushort * *,ushort *)
0x14002f1df  mov     ebx, eax
0x14002f1e1  test    eax, eax
0x14002f1e3  jns     short loc_14002F21A
0x14002f1e5  mov     r9d, 388h; unsigned int
0x14002f1eb  mov     [rsp+290h+var_268], eax; unsigned int
0x14002f1ef  lea     rax, aSendcontactinf; "SendContactInfoThread"
0x14002f1f6  mov     [rsp+290h+var_270], rax; unsigned __int16 *
0x14002f1fb  lea     r8, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\ui\\filexfer.cpp"
0x14002f202  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002f209  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002f20e  mov     r14, [rbp+190h+arg_0]
0x14002f215  jmp     loc_14002F52E
0x14002f21a  lea     rcx, [rsp+290h+var_260]; this
0x14002f21f  call    ?CreateSelfHistoryItem@@YAJPEAVCRAInvitationHistoryItem@@@Z; CreateSelfHistoryItem(CRAInvitationHistoryItem *)
0x14002f224  mov     ebx, eax
0x14002f226  test    eax, eax
0x14002f228  jns     short loc_14002F232
0x14002f22a  mov     r9d, 389h
0x14002f230  jmp     short loc_14002F1EB
0x14002f232  lea     rdx, [rsp+290h+var_260]; struct CRAInvitationHistoryItem *
0x14002f237  lea     rcx, [rsp+290h+var_220]; this
0x14002f23c  call    ?put_InvitationItem@CRAInvitationHistoryManager@@QEAAJPEAVCRAInvitationHistoryItem@@@Z; CRAInvitationHistoryManager::put_InvitationItem(CRAInvitationHistoryItem *)
0x14002f241  mov     ebx, eax
0x14002f243  test    eax, eax
0x14002f245  jns     short loc_14002F24F
0x14002f247  mov     r9d, 38Ah
0x14002f24d  jmp     short loc_14002F1EB
0x14002f24f  mov     r14, [rbp+190h+arg_0]
0x14002f256  mov     rdx, r14; unsigned __int16 *
0x14002f259  lea     rcx, [rsp+290h+var_220]; this
0x14002f25e  call    ?SaveRAInvitationsHistory@CRAInvitationHistoryManager@@QEAAJPEAG@Z; CRAInvitationHistoryManager::SaveRAInvitationsHistory(ushort *)
0x14002f263  mov     ebx, eax
0x14002f265  test    eax, eax
0x14002f267  jns     short loc_14002F278
0x14002f269  mov     [rsp+290h+var_268], eax
0x14002f26d  mov     r9d, 38Bh
0x14002f273  jmp     loc_14002F50F
0x14002f278  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002f27f  mov     ecx, 50h ; 'P'; unsigned __int64
0x14002f284  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14002f289  mov     rdi, rax
0x14002f28c  mov     [rbp+190h+arg_0], rax
0x14002f293  test    rax, rax
0x14002f296  jz      loc_14002F4FA
0x14002f29c  mov     rdx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002f2a3  mov     rax, [rdx+340h]
0x14002f2aa  mov     [rdi+38h], rax
0x14002f2ae  mov     qword ptr [rdi+40h], 0
0x14002f2b6  mov     qword ptr [rdi+48h], 0
0x14002f2be  mov     ecx, 10h
0x14002f2c3  mov     rax, rdi
0x14002f2c6  mov     byte ptr [rax], 0
0x14002f2c9  inc     rax
0x14002f2cc  sub     rcx, 1
0x14002f2d0  jnz     short loc_14002F2C6
0x14002f2d2  mov     ecx, 28h ; '('
0x14002f2d7  lea     rax, [rdi+10h]
0x14002f2db  mov     byte ptr [rax], 0
0x14002f2de  inc     rax
0x14002f2e1  sub     rcx, 1
0x14002f2e5  jnz     short loc_14002F2DB
0x14002f2e7  test    rdi, rdi
0x14002f2ea  jz      loc_14002F4FC
0x14002f2f0  mov     rax, [rdi+38h]
0x14002f2f4  cmp     [rax+1CCh], ecx
0x14002f2fa  jnz     short loc_14002F314
0x14002f2fc  mov     ebx, 8000FFFFh
0x14002f301  mov     [rsp+290h+var_268], 8000FFFFh
0x14002f309  mov     r9d, 397h
0x14002f30f  jmp     loc_14002F50F
0x14002f314  mov     dword ptr [rdi], 2BF20h
0x14002f31a  mov     dword ptr [rdi+4], 1
0x14002f321  lea     rax, ?SendFileClientCallback@@YAXPEAURA_FILE_XFER_CLIENT_CONTEXT@@W4RAFX_STATUS@@@Z; SendFileClientCallback(RA_FILE_XFER_CLIENT_CONTEXT *,RAFX_STATUS)
0x14002f328  mov     [rdi+8], rax
0x14002f32c  mov     [rdi+28h], rdi
0x14002f330  mov     rax, [rdx+340h]
0x14002f337  mov     rax, [rax+0D0h]
0x14002f33e  neg     rax
0x14002f341  sbb     edx, edx; int
0x14002f343  mov     r8, r14; unsigned __int16 *
0x14002f346  mov     rcx, rdi; this
0x14002f349  call    ?SendFile@RAFileXferClient@@QEAAJJPEBGKW4__MIDL___MIDL_itf_rdpencomapi_0000_0000_0003@@@Z; RAFileXferClient::SendFile(long,ushort const *,ulong,__MIDL___MIDL_itf_rdpencomapi_0000_0000_0003)
0x14002f34e  mov     ebx, eax
0x14002f350  test    eax, eax
0x14002f352  jns     short loc_14002F363
0x14002f354  mov     [rsp+290h+var_268], eax
0x14002f358  mov     r9d, 39Ch
0x14002f35e  jmp     loc_14002F50F
0x14002f363  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002f36a  cmp     qword ptr [rcx+358h], 0
0x14002f372  jnz     short loc_14002F39A
0x14002f374  xor     r9d, r9d; lpName
0x14002f377  xor     r8d, r8d; bInitialState
0x14002f37a  lea     edx, [r9+1]; bManualReset
0x14002f37e  xor     ecx, ecx; lpEventAttributes
0x14002f380  call    cs:__imp_CreateEventW
0x14002f387  nop     dword ptr [rax+rax+00h]
0x14002f38c  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002f393  mov     [rcx+358h], rax
0x14002f39a  mov     rcx, [rcx+358h]; hEvent
0x14002f3a1  call    cs:__imp_ResetEvent
0x14002f3a8  nop     dword ptr [rax+rax+00h]
0x14002f3ad  cmp     esi, 1
0x14002f3b0  jz      short loc_14002F3D9
0x14002f3b2  mov     edx, 493E0h; dwMilliseconds
0x14002f3b7  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002f3be  mov     rcx, [rcx+358h]; hHandle
0x14002f3c5  call    cs:__imp_WaitForSingleObject
0x14002f3cc  nop     dword ptr [rax+rax+00h]
0x14002f3d1  test    eax, eax
0x14002f3d3  jnz     loc_14002F52E
0x14002f3d9  mov     rsi, [rbp+190h+lpFileName]
0x14002f3e0  mov     rcx, rsi; lpFileName
0x14002f3e3  call    ?FileExists@@YAHPEAG@Z; FileExists(ushort *)
0x14002f3e8  test    eax, eax
0x14002f3ea  jz      loc_14002F52E
0x14002f3f0  mov     rdx, rsi; unsigned __int16 *
0x14002f3f3  lea     rcx, [rsp+290h+var_220]; this
0x14002f3f8  call    ?LoadAndSortRAInvitationsHistory@CRAInvitationHistoryManager@@QEAAJPEAG@Z; CRAInvitationHistoryManager::LoadAndSortRAInvitationsHistory(ushort *)
0x14002f3fd  mov     ebx, eax
0x14002f3ff  test    eax, eax
0x14002f401  jns     short loc_14002F412
0x14002f403  mov     [rsp+290h+var_268], eax
0x14002f407  mov     r9d, 3BAh
0x14002f40d  jmp     loc_14002F50F
0x14002f412  cmp     [rsp+290h+var_220], 1
0x14002f417  jns     short loc_14002F42E
0x14002f419  mov     ebx, 80070057h
0x14002f41e  mov     [rsp+290h+var_268], 80070057h
0x14002f426  mov     r9d, 37Ch
0x14002f42c  jmp     short loc_14002F47F
0x14002f42e  xor     eax, eax
0x14002f430  mov     rdx, [rbp+190h+var_38]
0x14002f437  jmp     short loc_14002F442
0x14002f439  test    eax, eax
0x14002f43b  jle     short loc_14002F44E
0x14002f43d  dec     eax
0x14002f43f  mov     rdx, [rdx]
0x14002f442  lea     rcx, [rbp+190h+var_38]; this
0x14002f449  cmp     rdx, rcx
0x14002f44c  jnz     short loc_14002F439
0x14002f44e  lea     rax, [rbp+190h+var_38]
0x14002f455  cmp     rdx, rax
0x14002f458  jnz     short loc_14002F461
0x14002f45a  mov     ebx, 8000FFFFh
0x14002f45f  jmp     short loc_14002F49E
0x14002f461  lea     r8, [rsp+290h+var_260]; struct CRAInvitationHistoryItem *
0x14002f466  mov     rdx, [rdx+10h]; struct CRAInvitationHistoryItem *
0x14002f46a  call    ?CloneHistoryItem@CRAInvitationHistoryManager@@AEAAJPEAVCRAInvitationHistoryItem@@0@Z; CRAInvitationHistoryManager::CloneHistoryItem(CRAInvitationHistoryItem *,CRAInvitationHistoryItem *)
0x14002f46f  mov     ebx, eax
0x14002f471  test    eax, eax
0x14002f473  jns     short loc_14002F4AA
0x14002f475  mov     [rsp+290h+var_268], eax; unsigned int
0x14002f479  mov     r9d, 394h; unsigned int
0x14002f47f  lea     rax, aCrainvitationh_3; "CRAInvitationHistoryManager::get_Invita"...
0x14002f486  mov     [rsp+290h+var_270], rax; unsigned __int16 *
0x14002f48b  lea     r8, a0123456789abcd+10h; unsigned __int16 *
0x14002f492  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002f499  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002f49e  mov     [rsp+290h+var_268], ebx
0x14002f4a2  mov     r9d, 3BBh
0x14002f4a8  jmp     short loc_14002F50F
0x14002f4aa  mov     esi, 3
0x14002f4af  mov     edx, esi; int
0x14002f4b1  lea     rcx, [rsp+290h+var_220]; this
0x14002f4b6  call    ?GetInvitationManagerLoaded@@YAJPEAVCRAInvitationHistoryManager@@H@Z; GetInvitationManagerLoaded(CRAInvitationHistoryManager *,int)
0x14002f4bb  lea     rdx, [rsp+290h+var_260]; struct CRAInvitationHistoryItem *
0x14002f4c0  lea     rcx, [rsp+290h+var_220]; this
0x14002f4c5  call    ?put_InvitationItem@CRAInvitationHistoryManager@@QEAAJPEAVCRAInvitationHistoryItem@@@Z; CRAInvitationHistoryManager::put_InvitationItem(CRAInvitationHistoryItem *)
0x14002f4ca  mov     ebx, eax
0x14002f4cc  test    eax, eax
0x14002f4ce  jns     short loc_14002F4DC
0x14002f4d0  mov     [rsp+290h+var_268], eax
0x14002f4d4  mov     r9d, 3BDh
0x14002f4da  jmp     short loc_14002F50F
0x14002f4dc  mov     edx, esi; int
0x14002f4de  lea     rcx, [rsp+290h+var_220]; this
0x14002f4e3  call    ?SaveInvitationHistory@@YAJPEAVCRAInvitationHistoryManager@@H@Z; SaveInvitationHistory(CRAInvitationHistoryManager *,int)
0x14002f4e8  mov     ebx, eax
0x14002f4ea  test    eax, eax
0x14002f4ec  jns     short loc_14002F52E
0x14002f4ee  mov     [rsp+290h+var_268], eax
0x14002f4f2  mov     r9d, 3BEh
0x14002f4f8  jmp     short loc_14002F50F
0x14002f4fa  xor     edi, edi
0x14002f4fc  mov     ebx, 8007000Eh
0x14002f501  mov     [rsp+290h+var_268], 8007000Eh; unsigned int
0x14002f509  mov     r9d, 38Fh; unsigned int
0x14002f50f  lea     rax, aSendcontactinf; "SendContactInfoThread"
0x14002f516  mov     [rsp+290h+var_270], rax; unsigned __int16 *
0x14002f51b  lea     r8, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\ui\\filexfer.cpp"
0x14002f522  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002f529  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002f52e  mov     rcx, r14; lpFileName
0x14002f531  call    ?FileExists@@YAHPEAG@Z; FileExists(ushort *)
0x14002f536  test    eax, eax
0x14002f538  jz      short loc_14002F549
0x14002f53a  mov     rcx, r14; lpFileName
0x14002f53d  call    cs:__imp_DeleteFileW
0x14002f544  nop     dword ptr [rax+rax+00h]
0x14002f549  test    r14, r14
0x14002f54c  jz      short loc_14002F55D
0x14002f54e  mov     rcx, r14; bstrString
0x14002f551  call    cs:__imp_SysFreeString
0x14002f558  nop     dword ptr [rax+rax+00h]
0x14002f55d  mov     rsi, [rbp+190h+lpFileName]
0x14002f564  mov     rcx, rsi; lpFileName
0x14002f567  call    ?FileExists@@YAHPEAG@Z; FileExists(ushort *)
0x14002f56c  test    eax, eax
0x14002f56e  jz      short loc_14002F57F
0x14002f570  mov     rcx, rsi; lpFileName
0x14002f573  call    cs:__imp_DeleteFileW
0x14002f57a  nop     dword ptr [rax+rax+00h]
0x14002f57f  mov     rsi, [rbp+190h+lpFileName]
0x14002f586  test    rsi, rsi
0x14002f589  jz      short loc_14002F59A
0x14002f58b  mov     rcx, rsi; bstrString
0x14002f58e  call    cs:__imp_SysFreeString
0x14002f595  nop     dword ptr [rax+rax+00h]
0x14002f59a  xor     r8d, r8d; wParam
0x14002f59d  mov     edx, 801Bh; Msg
0x14002f5a2  mov     rcx, r15; hWnd
0x14002f5a5  test    ebx, ebx
0x14002f5a7  lea     r9d, [r8+4]
0x14002f5ab  js      short loc_14002F5B1
0x14002f5ad  lea     r9d, [r8+2]; lParam
0x14002f5b1  call    cs:__imp_PostMessageW
0x14002f5b8  nop     dword ptr [rax+rax+00h]
0x14002f5bd  test    rdi, rdi
0x14002f5c0  jz      short loc_14002F5D1
0x14002f5c2  mov     rcx, rdi
0x14002f5c5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14002f5cc  nop     dword ptr [rax+rax+00h]
0x14002f5d1  call    cs:__imp_CoUninitialize
0x14002f5d8  nop     dword ptr [rax+rax+00h]
0x14002f5dd  nop
0x14002f5de  lea     rcx, [rsp+290h+var_220]; this
0x14002f5e3  call    ?EmptyList@CRAInvitationHistoryManager@@AEAAXXZ; CRAInvitationHistoryManager::EmptyList(void)
0x14002f5e8  nop
0x14002f5e9  lea     rcx, [rsp+290h+var_260]; this
0x14002f5ee  call    ??1CRAInvitationHistoryItem@@QEAA@XZ; CRAInvitationHistoryItem::~CRAInvitationHistoryItem(void)
  ... truncated ...
```
