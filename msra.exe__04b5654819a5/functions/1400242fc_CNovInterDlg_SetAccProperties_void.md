# CNovInterDlg::SetAccProperties(void)

- ea: `0x1400242fc`
- end: `0x1400244d6`
- name: `?SetAccProperties@CNovInterDlg@@AEAAXXZ`
- size: `474`
- prototype: `void __fastcall(CNovInterDlg *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140021e00`

## callees

- `0x140002463`
- `0x1400187cc`
- `0x1400242fc`
- `0x140034ce4`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `USER32!LoadStringW` at `0x140024414`
- `USER32!LoadStringW` at `0x140024414`
- `USER32!GetDlgItem` at `0x140024367`
- `USER32!GetDlgItem` at `0x140024381`
- `USER32!GetDlgItem` at `0x140024367`
- `USER32!GetDlgItem` at `0x140024381`
- `ole32!CoCreateInstance` at `0x1400243be`
- `ole32!CoCreateInstance` at `0x1400243be`

## pseudocode

```c
void __fastcall CNovInterDlg::SetAccProperties(CNovInterDlg *this)
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
  v15[0] = *((_QWORD *)this + 9);
  uID[0] = 752;
  uID[1] = 753;
  uID[2] = 754;
  uID[3] = 758;
  DlgItem = GetDlgItem(v2, 1036);
  v4 = (HWND)*((_QWORD *)this + 1);
  v15[1] = DlgItem;
  v15[2] = GetDlgItem(v4, 1035);
  v5 = (__int64 **)((char *)this + 208);
  v15[3] = *((_QWORD *)this + 22);
  Instance = CoCreateInstance(&CLSID_AccPropServices, 0, 0x15u, &IID_IAccPropServices, (LPVOID *)this + 26);
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
            (void *)0x1426,
            (unsigned int)"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
            (const char *)(unsigned int)v13,
            (int)v16);
        v8 = (unsigned int)(v8 + 1);
        if ( (unsigned int)v8 >= 4 )
          return;
      }
      CEventLogger::LogError(
        v9,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
        0x141Fu,
        L"CNovInterDlg::SetAccProperties",
        0);
    }
    else
    {
      CEventLogger::LogError(
        v7,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
        0x1414u,
        L"CNovInterDlg::SetAccProperties",
        0x80004003);
    }
  }
  else
  {
    CEventLogger::LogError(
      v7,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      0x1412u,
      L"CNovInterDlg::SetAccProperties",
      Instance);
  }
}

```

## disassembly

```asm
0x1400242fc  push    rbp
0x1400242fe  push    rbx
0x1400242ff  push    rsi
0x140024300  push    rdi
0x140024301  lea     rbp, [rsp-798h]
0x140024309  sub     rsp, 898h
0x140024310  mov     rax, cs:__security_cookie
0x140024317  xor     rax, rsp
0x14002431a  mov     [rbp+7B0h+var_30], rax
0x140024321  mov     rbx, rcx
0x140024324  xor     edx, edx; Val
0x140024326  lea     rcx, [rbp+7B0h+Buffer]; void *
0x14002432a  mov     r8d, 800h; Size
0x140024330  call    memset_0
0x140024335  mov     rax, [rbx+48h]
0x140024339  mov     edx, 40Ch; nIDDlgItem
0x14002433e  mov     rcx, [rbx+8]; hDlg
0x140024342  mov     [rsp+8B0h+var_860], rax
0x140024347  mov     [rsp+8B0h+uID], 2F0h
0x14002434f  mov     [rsp+8B0h+var_86C], 2F1h
0x140024357  mov     [rsp+8B0h+var_868], 2F2h
0x14002435f  mov     [rsp+8B0h+var_864], 2F6h
0x140024367  call    cs:__imp_GetDlgItem
0x14002436e  nop     dword ptr [rax+rax+00h]
0x140024373  mov     rcx, [rbx+8]; hDlg
0x140024377  mov     edx, 40Bh; nIDDlgItem
0x14002437c  mov     [rsp+8B0h+var_858], rax
0x140024381  call    cs:__imp_GetDlgItem
0x140024388  nop     dword ptr [rax+rax+00h]
0x14002438d  xor     edx, edx; pUnkOuter
0x14002438f  mov     [rsp+8B0h+var_850], rax
0x140024394  mov     rax, [rbx+0B0h]
0x14002439b  lea     rsi, [rbx+0D0h]
0x1400243a2  lea     r9, IID_IAccPropServices; riid
0x1400243a9  mov     [rsp+8B0h+var_848], rax
0x1400243ae  lea     rcx, CLSID_AccPropServices; rclsid
0x1400243b5  mov     [rsp+8B0h+ppv], rsi; ppv
0x1400243ba  lea     r8d, [rdx+15h]; dwClsContext
0x1400243be  call    cs:__imp_CoCreateInstance
0x1400243c5  nop     dword ptr [rax+rax+00h]
0x1400243ca  test    eax, eax
0x1400243cc  jns     short loc_1400243DD
0x1400243ce  mov     [rsp+8B0h+var_888], eax
0x1400243d2  mov     r9d, 1412h
0x1400243d8  jmp     loc_14002449B
0x1400243dd  cmp     qword ptr [rsi], 0
0x1400243e1  jnz     short loc_1400243F6
0x1400243e3  mov     [rsp+8B0h+var_888], 80004003h
0x1400243eb  mov     r9d, 1414h
0x1400243f1  jmp     loc_14002449B
0x1400243f6  xor     ebx, ebx
0x1400243f8  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400243ff  lea     r8, [rbp+7B0h+Buffer]; lpBuffer
0x140024403  mov     edx, [rsp+rbx*4+8B0h+uID]; uID
0x140024407  mov     r9d, 400h; cchBufferMax
0x14002440d  mov     rcx, [rcx+260h]; hInstance
0x140024414  call    cs:__imp_LoadStringW
0x14002441b  nop     dword ptr [rax+rax+00h]
0x140024420  test    eax, eax
0x140024422  jz      short loc_14002448D
0x140024424  mov     rcx, [rsi]
0x140024427  lea     rdx, [rbp+7B0h+Buffer]
0x14002442b  movups  xmm0, xmmword ptr cs:PROPID_ACC_NAME.Data1
0x140024432  mov     qword ptr [rsp+8B0h+var_888], rdx
0x140024437  xor     r9d, r9d
0x14002443a  lea     rdx, [rsp+8B0h+var_840]
0x14002443f  mov     r8d, 0FFFFFFFCh
0x140024445  mov     rax, [rcx]
0x140024448  mov     [rsp+8B0h+ppv], rdx; int
0x14002444d  mov     rdx, [rsp+rbx*8+8B0h+var_860]
0x140024452  movdqu  xmmword ptr [rsp+8B0h+var_840], xmm0
0x140024458  mov     rax, [rax+38h]
0x14002445c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024461  test    eax, eax
0x140024463  jns     short loc_140024480
0x140024465  mov     rcx, [rbp+7B8h]; this
0x14002446c  lea     r8, aBaseDiagnosisR_9; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x140024473  mov     r9d, eax; char *
0x140024476  mov     edx, 1426h; void *
0x14002447b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140024480  inc     ebx
0x140024482  cmp     ebx, 4
0x140024485  jb      loc_1400243F8
0x14002448b  jmp     short loc_1400244BA
0x14002448d  mov     [rsp+8B0h+var_888], 0; unsigned int
0x140024495  mov     r9d, 141Fh; unsigned int
0x14002449b  lea     rax, aCnovinterdlgSe_1; "CNovInterDlg::SetAccProperties"
0x1400244a2  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x1400244a9  mov     [rsp+8B0h+ppv], rax; unsigned __int16 *
0x1400244ae  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400244b5  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400244ba  mov     rcx, [rbp+7B0h+var_30]
0x1400244c1  xor     rcx, rsp; StackCookie
0x1400244c4  call    __security_check_cookie
0x1400244c9  add     rsp, 898h
0x1400244d0  pop     rdi
0x1400244d1  pop     rsi
0x1400244d2  pop     rbx
0x1400244d3  pop     rbp
0x1400244d4  retn
```
