# CExpInterDlg::SetAccProperties(void)

- ea: `0x14001e344`
- end: `0x14001e51b`
- name: `?SetAccProperties@CExpInterDlg@@AEAAXXZ`
- size: `471`
- prototype: `void __fastcall(CExpInterDlg *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001c458`

## callees

- `0x140002463`
- `0x1400187cc`
- `0x14001e344`
- `0x140034ce4`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `USER32!LoadStringW` at `0x14001e459`
- `USER32!LoadStringW` at `0x14001e459`
- `USER32!GetDlgItem` at `0x14001e3af`
- `USER32!GetDlgItem` at `0x14001e3c9`
- `USER32!GetDlgItem` at `0x14001e3af`
- `USER32!GetDlgItem` at `0x14001e3c9`
- `ole32!CoCreateInstance` at `0x14001e403`
- `ole32!CoCreateInstance` at `0x14001e403`

## pseudocode

```c
void __fastcall CExpInterDlg::SetAccProperties(CExpInterDlg *this)
{
  HWND v2; // rcx
  HWND DlgItem; // rax
  HWND v4; // rcx
  __int64 **v5; // rsi
  HRESULT Instance; // eax
  CEventLogger *v7; // rcx
  __int64 v8; // rbx
  CEventLogger *v9; // rcx
  __int64 *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // eax
  UINT uID[4]; // [rsp+40h] [rbp-C0h]
  _QWORD v15[4]; // [rsp+50h] [rbp-B0h]
  int v16[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[1024]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8B8h] [rbp+7B8h]

  memset_0(Buffer, 0, sizeof(Buffer));
  v2 = (HWND)*((_QWORD *)this + 1);
  v15[0] = *((_QWORD *)this + 10);
  uID[0] = 752;
  uID[1] = 753;
  uID[2] = 754;
  uID[3] = 758;
  DlgItem = GetDlgItem(v2, 1036);
  v4 = (HWND)*((_QWORD *)this + 1);
  v15[1] = DlgItem;
  v15[2] = GetDlgItem(v4, 1035);
  v5 = (__int64 **)((char *)this + 192);
  v15[3] = *((_QWORD *)this + 11);
  Instance = CoCreateInstance(&CLSID_AccPropServices, 0, 0x15u, &IID_IAccPropServices, (LPVOID *)this + 24);
  if ( Instance >= 0 )
  {
    if ( *v5 )
    {
      v8 = 0;
      while ( LoadStringW(*((HINSTANCE *)_AtlModule + 76), uID[v8], Buffer, 1024) )
      {
        v10 = *v5;
        v11 = **v5;
        v12 = v15[v8];
        *(GUID *)v16 = PROPID_ACC_NAME;
        v13 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, _QWORD))(v11 + 56))(v10, v12, 4294967292LL, 0);
        if ( v13 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xE76,
            (unsigned int)"base\\diagnosis\\ra\\ui\\expinterdialog.cpp",
            (const char *)(unsigned int)v13,
            (int)v16);
        v8 = (unsigned int)(v8 + 1);
        if ( (unsigned int)v8 >= 4 )
          return;
      }
      CEventLogger::LogError(
        v9,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\expinterdialog.cpp",
        0xE6Fu,
        L"CExpInterDlg::SetAccProperties",
        0);
    }
    else
    {
      CEventLogger::LogError(
        v7,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\expinterdialog.cpp",
        0xE64u,
        L"CExpInterDlg::SetAccProperties",
        0x80004003);
    }
  }
  else
  {
    CEventLogger::LogError(
      v7,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\expinterdialog.cpp",
      0xE62u,
      L"CExpInterDlg::SetAccProperties",
      Instance);
  }
}

```

## disassembly

```asm
0x14001e344  push    rbp
0x14001e346  push    rbx
0x14001e347  push    rsi
0x14001e348  push    rdi
0x14001e349  lea     rbp, [rsp-798h]
0x14001e351  sub     rsp, 898h
0x14001e358  mov     rax, cs:__security_cookie
0x14001e35f  xor     rax, rsp
0x14001e362  mov     [rbp+7B0h+var_30], rax
0x14001e369  mov     rbx, rcx
0x14001e36c  xor     edx, edx; Val
0x14001e36e  lea     rcx, [rbp+7B0h+Buffer]; void *
0x14001e372  mov     r8d, 800h; Size
0x14001e378  call    memset_0
0x14001e37d  mov     rax, [rbx+50h]
0x14001e381  mov     edx, 40Ch; nIDDlgItem
0x14001e386  mov     rcx, [rbx+8]; hDlg
0x14001e38a  mov     [rsp+8B0h+var_860], rax
0x14001e38f  mov     [rsp+8B0h+uID], 2F0h
0x14001e397  mov     [rsp+8B0h+var_86C], 2F1h
0x14001e39f  mov     [rsp+8B0h+var_868], 2F2h
0x14001e3a7  mov     [rsp+8B0h+var_864], 2F6h
0x14001e3af  call    cs:__imp_GetDlgItem
0x14001e3b6  nop     dword ptr [rax+rax+00h]
0x14001e3bb  mov     rcx, [rbx+8]; hDlg
0x14001e3bf  mov     edx, 40Bh; nIDDlgItem
0x14001e3c4  mov     [rsp+8B0h+var_858], rax
0x14001e3c9  call    cs:__imp_GetDlgItem
0x14001e3d0  nop     dword ptr [rax+rax+00h]
0x14001e3d5  xor     edx, edx; pUnkOuter
0x14001e3d7  mov     [rsp+8B0h+var_850], rax
0x14001e3dc  mov     rax, [rbx+58h]
0x14001e3e0  lea     rsi, [rbx+0C0h]
0x14001e3e7  lea     r9, IID_IAccPropServices; riid
0x14001e3ee  mov     [rsp+8B0h+var_848], rax
0x14001e3f3  lea     rcx, CLSID_AccPropServices; rclsid
0x14001e3fa  mov     [rsp+8B0h+ppv], rsi; ppv
0x14001e3ff  lea     r8d, [rdx+15h]; dwClsContext
0x14001e403  call    cs:__imp_CoCreateInstance
0x14001e40a  nop     dword ptr [rax+rax+00h]
0x14001e40f  test    eax, eax
0x14001e411  jns     short loc_14001E422
0x14001e413  mov     [rsp+8B0h+var_888], eax
0x14001e417  mov     r9d, 0E62h
0x14001e41d  jmp     loc_14001E4E0
0x14001e422  cmp     qword ptr [rsi], 0
0x14001e426  jnz     short loc_14001E43B
0x14001e428  mov     [rsp+8B0h+var_888], 80004003h
0x14001e430  mov     r9d, 0E64h
0x14001e436  jmp     loc_14001E4E0
0x14001e43b  xor     ebx, ebx
0x14001e43d  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001e444  lea     r8, [rbp+7B0h+Buffer]; lpBuffer
0x14001e448  mov     edx, [rsp+rbx*4+8B0h+uID]; uID
0x14001e44c  mov     r9d, 400h; cchBufferMax
0x14001e452  mov     rcx, [rcx+260h]; hInstance
0x14001e459  call    cs:__imp_LoadStringW
0x14001e460  nop     dword ptr [rax+rax+00h]
0x14001e465  test    eax, eax
0x14001e467  jz      short loc_14001E4D2
0x14001e469  mov     rcx, [rsi]
0x14001e46c  lea     rdx, [rbp+7B0h+Buffer]
0x14001e470  movups  xmm0, xmmword ptr cs:PROPID_ACC_NAME.Data1
0x14001e477  mov     qword ptr [rsp+8B0h+var_888], rdx
0x14001e47c  xor     r9d, r9d
0x14001e47f  lea     rdx, [rsp+8B0h+var_840]
0x14001e484  mov     r8d, 0FFFFFFFCh
0x14001e48a  mov     rax, [rcx]
0x14001e48d  mov     [rsp+8B0h+ppv], rdx; int
0x14001e492  mov     rdx, [rsp+rbx*8+8B0h+var_860]
0x14001e497  movdqu  xmmword ptr [rsp+8B0h+var_840], xmm0
0x14001e49d  mov     rax, [rax+38h]
0x14001e4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e4a6  test    eax, eax
0x14001e4a8  jns     short loc_14001E4C5
0x14001e4aa  mov     rcx, [rbp+7B8h]; this
0x14001e4b1  lea     r8, aBaseDiagnosisR_0; "base\\diagnosis\\ra\\ui\\expinterdialog"...
0x14001e4b8  mov     r9d, eax; char *
0x14001e4bb  mov     edx, 0E76h; void *
0x14001e4c0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001e4c5  inc     ebx
0x14001e4c7  cmp     ebx, 4
0x14001e4ca  jb      loc_14001E43D
0x14001e4d0  jmp     short loc_14001E4FF
0x14001e4d2  mov     [rsp+8B0h+var_888], 0; unsigned int
0x14001e4da  mov     r9d, 0E6Fh; unsigned int
0x14001e4e0  lea     rax, aCexpinterdlgSe_0; "CExpInterDlg::SetAccProperties"
0x14001e4e7  lea     r8, aBaseDiagnosisR_27; "base\\diagnosis\\ra\\ui\\expinterdialog"...
0x14001e4ee  mov     [rsp+8B0h+ppv], rax; unsigned __int16 *
0x14001e4f3  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14001e4fa  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001e4ff  mov     rcx, [rbp+7B0h+var_30]
0x14001e506  xor     rcx, rsp; StackCookie
0x14001e509  call    __security_check_cookie
0x14001e50e  add     rsp, 898h
0x14001e515  pop     rdi
0x14001e516  pop     rsi
0x14001e517  pop     rbx
0x14001e518  pop     rbp
0x14001e519  retn
```
