# CIncomingConnectionSavePage::RASServiceStartThread(CIncomingConnectionSavePage *)

- ea: `0x18001f460`
- end: `0x18001f67a`
- name: `?RASServiceStartThread@CIncomingConnectionSavePage@@CAP6AKPEAX@ZPEAV1@@Z`
- size: `538`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18001f460`
- `0x18001f770`
- `0x1800209bc`
- `0x1800209f8`
- `0x18002b970`

## import_xrefs

- `USER32!PostMessageW` at `0x18001f5d6`
- `USER32!PostMessageW` at `0x18001f5d6`
- `USER32!ShowWindow` at `0x18001f504`
- `USER32!ShowWindow` at `0x18001f510`
- `USER32!ShowWindow` at `0x18001f51f`
- `USER32!ShowWindow` at `0x18001f52e`
- `USER32!ShowWindow` at `0x18001f626`
- `USER32!ShowWindow` at `0x18001f632`
- `USER32!ShowWindow` at `0x18001f641`
- `USER32!ShowWindow` at `0x18001f652`
- `USER32!ShowWindow` at `0x18001f504`
- `USER32!ShowWindow` at `0x18001f510`
- `USER32!ShowWindow` at `0x18001f51f`
- `USER32!ShowWindow` at `0x18001f52e`
- `USER32!ShowWindow` at `0x18001f626`
- `USER32!ShowWindow` at `0x18001f632`
- `USER32!ShowWindow` at `0x18001f641`
- `USER32!ShowWindow` at `0x18001f652`
- `USER32!SendMessageW` at `0x18001f4d7`
- `USER32!SendMessageW` at `0x18001f4f8`
- `USER32!SendMessageW` at `0x18001f547`
- `USER32!SendMessageW` at `0x18001f61a`
- `USER32!SendMessageW` at `0x18001f4d7`
- `USER32!SendMessageW` at `0x18001f4f8`
- `USER32!SendMessageW` at `0x18001f547`
- `USER32!SendMessageW` at `0x18001f61a`
- `USER32!GetParent` at `0x18001f4c3`
- `USER32!GetParent` at `0x18001f4e4`
- `USER32!GetParent` at `0x18001f5c1`
- `USER32!GetParent` at `0x18001f4c3`
- `USER32!GetParent` at `0x18001f4e4`
- `USER32!GetParent` at `0x18001f5c1`
- `rtutils!TracePrintfExA` at `0x18001f58b`
- `rtutils!TracePrintfExA` at `0x18001f5aa`
- `rtutils!TracePrintfExA` at `0x18001f5f5`
- `rtutils!TracePrintfExA` at `0x18001f58b`
- `rtutils!TracePrintfExA` at `0x18001f5aa`
- `rtutils!TracePrintfExA` at `0x18001f5f5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001f482`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001f482`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f568`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f568`

## string_xrefs

- `0x18001f5a0`: `CIncomingConnectionSavePage::RASServiceStartThread: Service Started successfully.`
- `0x18001f57f`: `Failed to initialize COM. hr = %#x`
- `0x18001f5e9`: `CIncomingConnectionSavePage::RASServiceStartThread: Failed to start service: Error=%d.`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionSavePage::RASServiceStartThread(PVOID Parameter)
{
  unsigned int v1; // ebx
  HRESULT v3; // eax
  int v4; // r9d
  HRESULT v5; // ebp
  __int64 StringPcch; // rax
  HWND v7; // rbx
  LPARAM v8; // rdi
  HWND v9; // rax
  WPARAM v10; // rbx
  HWND v11; // rax
  HWND v12; // rdx
  HWND Parent; // rax
  int updated; // ebx
  _OWORD v16[2]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v17; // [rsp+58h] [rbp+10h] BYREF
  int v18; // [rsp+60h] [rbp+18h]

  v1 = 0;
  v17 = 0;
  v16[0] = 0;
  v3 = CoInitializeEx(0, 6u);
  v4 = 0;
  v5 = v3;
  if ( v3 != -2147417850 )
    v4 = v3;
  if ( v4 < 0 )
  {
    if ( g_dwTraceId == -1 )
    {
LABEL_12:
      if ( *((_DWORD *)Parameter + 40) )
      {
        if ( !DWORD2(v16[0]) )
          RasSrvServiceCleanup(v16);
      }
      else
      {
        Parent = GetParent(*((HWND *)Parameter + 8));
        PostMessageW(Parent, 0x471u, 1u, 0);
      }
      return 0;
    }
    TracePrintfExA(g_dwTraceId, 0xCu, "Failed to initialize COM. hr = %#x", v4);
  }
  else
  {
    v18 = 0;
    StringPcch = PszLoadStringPcch(hInst);
    v7 = (HWND)*((_QWORD *)Parameter + 8);
    v8 = StringPcch;
    v9 = GetParent(v7);
    v10 = (int)SendMessageW(v9, 0x481u, (WPARAM)v7, 0);
    v11 = GetParent(*((HWND *)Parameter + 8));
    SendMessageW(v11, 0x47Eu, v10, v8);
    ShowWindow(*((HWND *)Parameter + 12), 0);
    ShowWindow(*((HWND *)Parameter + 11), 0);
    ShowWindow(*((HWND *)Parameter + 9), 5);
    ShowWindow(*((HWND *)Parameter + 10), 5);
    SendMessageW(*((HWND *)Parameter + 10), 0x40Au, 1u, 100);
    RasSrvServiceInitialize(v16, *((_QWORD *)Parameter + 15), &v17);
    if ( v5 != -2147417850 )
      CoUninitialize();
    v1 = v17;
  }
  if ( !v1 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "CIncomingConnectionSavePage::RASServiceStartThread: Service Started successfully.");
    goto LABEL_12;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(
      g_dwTraceId,
      0xCu,
      "CIncomingConnectionSavePage::RASServiceStartThread: Failed to start service: Error=%d.",
      v1);
  updated = CIncomingConnectionSavePage::UpdateDlgWithErrorInfo((CIncomingConnectionSavePage *)Parameter, v12, v1);
  SendMessageW(*((HWND *)Parameter + 10), 0x40Au, 0, 100);
  ShowWindow(*((HWND *)Parameter + 10), 0);
  ShowWindow(*((HWND *)Parameter + 9), 0);
  ShowWindow(*((HWND *)Parameter + 12), 5);
  ShowWindow(*((HWND *)Parameter + 11), updated != 0 ? 5 : 0);
  return 0;
}

```

## disassembly

```asm
0x18001f460  mov     [rsp+arg_0], rbx
0x18001f465  push    rbp
0x18001f466  push    rsi
0x18001f467  push    rdi
0x18001f468  sub     rsp, 30h
0x18001f46c  xor     ebx, ebx
0x18001f46e  mov     rsi, rcx
0x18001f471  xorps   xmm0, xmm0
0x18001f474  mov     [rsp+48h+arg_8], ebx
0x18001f478  xor     ecx, ecx; pvReserved
0x18001f47a  movups  [rsp+48h+var_28], xmm0
0x18001f47f  lea     edx, [rbx+6]; dwCoInit
0x18001f482  call    cs:__imp_CoInitializeEx
0x18001f488  xor     r9d, r9d
0x18001f48b  mov     ebp, eax
0x18001f48d  cmp     eax, 80010106h
0x18001f492  cmovnz  r9d, eax
0x18001f496  test    r9d, r9d
0x18001f499  js      loc_18001F574
0x18001f49f  mov     rcx, cs:hInst; hModule
0x18001f4a6  lea     r8, [rsp+48h+arg_10]
0x18001f4ab  mov     edx, 0BF5h
0x18001f4b0  mov     [rsp+48h+arg_10], ebx
0x18001f4b4  call    PszLoadStringPcch
0x18001f4b9  mov     rbx, [rsi+40h]
0x18001f4bd  mov     rdi, rax
0x18001f4c0  mov     rcx, rbx; hWnd
0x18001f4c3  call    cs:__imp_GetParent
0x18001f4c9  xor     r9d, r9d; lParam
0x18001f4cc  mov     r8, rbx; wParam
0x18001f4cf  mov     rcx, rax; hWnd
0x18001f4d2  mov     edx, 481h; Msg
0x18001f4d7  call    cs:__imp_SendMessageW
0x18001f4dd  mov     rcx, [rsi+40h]; hWnd
0x18001f4e1  movsxd  rbx, eax
0x18001f4e4  call    cs:__imp_GetParent
0x18001f4ea  mov     r9, rdi; lParam
0x18001f4ed  mov     r8, rbx; wParam
0x18001f4f0  mov     rcx, rax; hWnd
0x18001f4f3  mov     edx, 47Eh; Msg
0x18001f4f8  call    cs:__imp_SendMessageW
0x18001f4fe  mov     rcx, [rsi+60h]; hWnd
0x18001f502  xor     edx, edx; nCmdShow
0x18001f504  call    cs:__imp_ShowWindow
0x18001f50a  mov     rcx, [rsi+58h]; hWnd
0x18001f50e  xor     edx, edx; nCmdShow
0x18001f510  call    cs:__imp_ShowWindow
0x18001f516  mov     rcx, [rsi+48h]; hWnd
0x18001f51a  mov     edx, 5; nCmdShow
0x18001f51f  call    cs:__imp_ShowWindow
0x18001f525  mov     rcx, [rsi+50h]; hWnd
0x18001f529  mov     edx, 5; nCmdShow
0x18001f52e  call    cs:__imp_ShowWindow
0x18001f534  mov     rcx, [rsi+50h]; hWnd
0x18001f538  mov     r9d, 64h ; 'd'; lParam
0x18001f53e  mov     edx, 40Ah; Msg
0x18001f543  lea     r8d, [r9-63h]; wParam
0x18001f547  call    cs:__imp_SendMessageW
0x18001f54d  mov     rdx, [rsi+78h]
0x18001f551  lea     r8, [rsp+48h+arg_8]
0x18001f556  lea     rcx, [rsp+48h+var_28]
0x18001f55b  call    RasSrvServiceInitialize
0x18001f560  cmp     ebp, 80010106h
0x18001f566  jz      short loc_18001F56E
0x18001f568  call    cs:__imp_CoUninitialize
0x18001f56e  mov     ebx, [rsp+48h+arg_8]
0x18001f572  jmp     short loc_18001F591
0x18001f574  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001f57a  cmp     ecx, 0FFFFFFFFh
0x18001f57d  jz      short loc_18001F5B0
0x18001f57f  lea     r8, aFailedToInitia; "Failed to initialize COM. hr = %#x"
0x18001f586  mov     edx, 0Ch; dwFlags
0x18001f58b  call    cs:__imp_TracePrintfExA
0x18001f591  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001f597  test    ebx, ebx
0x18001f599  jnz     short loc_18001F5E1
0x18001f59b  cmp     ecx, 0FFFFFFFFh
0x18001f59e  jz      short loc_18001F5B0
0x18001f5a0  lea     r8, aCincomingconne_5; "CIncomingConnectionSavePage::RASService"...
0x18001f5a7  lea     edx, [rbx+0Ch]; dwFlags
0x18001f5aa  call    cs:__imp_TracePrintfExA
0x18001f5b0  cmp     dword ptr [rsi+0A0h], 0
0x18001f5b7  jnz     loc_18001F65A
0x18001f5bd  mov     rcx, [rsi+40h]; hWnd
0x18001f5c1  call    cs:__imp_GetParent
0x18001f5c7  xor     r9d, r9d; lParam
0x18001f5ca  mov     edx, 471h; Msg
0x18001f5cf  mov     rcx, rax; hWnd
0x18001f5d2  lea     r8d, [r9+1]; wParam
0x18001f5d6  call    cs:__imp_PostMessageW
0x18001f5dc  jmp     loc_18001F66B
0x18001f5e1  cmp     ecx, 0FFFFFFFFh
0x18001f5e4  jz      short loc_18001F5FB
0x18001f5e6  mov     r9d, ebx
0x18001f5e9  lea     r8, aCincomingconne_0; "CIncomingConnectionSavePage::RASService"...
0x18001f5f0  mov     edx, 0Ch; dwFlags
0x18001f5f5  call    cs:__imp_TracePrintfExA
0x18001f5fb  mov     r8d, ebx; unsigned int
0x18001f5fe  mov     rcx, rsi; this
0x18001f601  call    ?UpdateDlgWithErrorInfo@CIncomingConnectionSavePage@@AEAAHPEAUHWND__@@K@Z; CIncomingConnectionSavePage::UpdateDlgWithErrorInfo(HWND__ *,ulong)
0x18001f606  mov     rcx, [rsi+50h]; hWnd
0x18001f60a  mov     r9d, 64h ; 'd'; lParam
0x18001f610  xor     r8d, r8d; wParam
0x18001f613  mov     edx, 40Ah; Msg
0x18001f618  mov     ebx, eax
0x18001f61a  call    cs:__imp_SendMessageW
0x18001f620  mov     rcx, [rsi+50h]; hWnd
0x18001f624  xor     edx, edx; nCmdShow
0x18001f626  call    cs:__imp_ShowWindow
0x18001f62c  mov     rcx, [rsi+48h]; hWnd
0x18001f630  xor     edx, edx; nCmdShow
0x18001f632  call    cs:__imp_ShowWindow
0x18001f638  mov     rcx, [rsi+60h]; hWnd
0x18001f63c  mov     edx, 5; nCmdShow
0x18001f641  call    cs:__imp_ShowWindow
0x18001f647  mov     rcx, [rsi+58h]; hWnd
0x18001f64b  neg     ebx
0x18001f64d  sbb     edx, edx
0x18001f64f  and     edx, 5; nCmdShow
0x18001f652  call    cs:__imp_ShowWindow
0x18001f658  jmp     short loc_18001F66B
0x18001f65a  cmp     dword ptr [rsp+48h+var_28+8], 0
0x18001f65f  jnz     short loc_18001F66B
0x18001f661  lea     rcx, [rsp+48h+var_28]
0x18001f666  call    RasSrvServiceCleanup
0x18001f66b  mov     rbx, [rsp+48h+arg_0]
0x18001f670  xor     eax, eax
0x18001f672  add     rsp, 30h
0x18001f676  pop     rdi
0x18001f677  pop     rsi
0x18001f678  pop     rbp
0x18001f679  retn
```
