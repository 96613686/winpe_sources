# CSharePageOverwrite::_OnPageNotify(HWND__ *,int,tagNMHDR const *)

- ea: `0x180069110`
- end: `0x180069395`
- name: `?_OnPageNotify@CSharePageOverwrite@@AEAA_JPEAUHWND__@@HPEBUtagNMHDR@@@Z`
- size: `645`
- prototype: `__int64(CSharePageOverwrite *__hidden this, HWND, int, const struct tagNMHDR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180068fec`

## callees

- `0x18001a570`
- `0x180069110`
- `0x18006939c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069154`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800691c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006922e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069281`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069315`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069320`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006932b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069336`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069154`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800691c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006922e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069281`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069315`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069320`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006932b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069336`
- `USER32!ShowWindow` at `0x180069213`
- `USER32!ShowWindow` at `0x180069213`
- `USER32!SetDlgItemTextW` at `0x1800691fa`
- `USER32!SetDlgItemTextW` at `0x1800691fa`
- `USER32!PostMessageW` at `0x1800692e6`
- `USER32!PostMessageW` at `0x180069306`
- `USER32!PostMessageW` at `0x1800692e6`
- `USER32!PostMessageW` at `0x180069306`
- `USER32!GetDlgItem` at `0x180069205`
- `USER32!GetDlgItem` at `0x180069205`
- `USER32!SetWindowLongPtrW` at `0x180069349`
- `USER32!SetWindowLongPtrW` at `0x180069383`
- `USER32!SetWindowLongPtrW` at `0x180069349`
- `USER32!SetWindowLongPtrW` at `0x180069383`
- `USER32!SendMessageW` at `0x180069190`
- `USER32!SendMessageW` at `0x1800691b1`
- `USER32!SendMessageW` at `0x180069271`
- `USER32!SendMessageW` at `0x1800692c4`
- `USER32!SendMessageW` at `0x180069370`
- `USER32!SendMessageW` at `0x180069190`
- `USER32!SendMessageW` at `0x1800691b1`
- `USER32!SendMessageW` at `0x180069271`
- `USER32!SendMessageW` at `0x1800692c4`
- `USER32!SendMessageW` at `0x180069370`
- `USER32!GetParent` at `0x18006919c`
- `USER32!GetParent` at `0x18006925c`
- `USER32!GetParent` at `0x1800692af`
- `USER32!GetParent` at `0x1800692cd`
- `USER32!GetParent` at `0x1800692ef`
- `USER32!GetParent` at `0x180069359`
- `USER32!GetParent` at `0x18006919c`
- `USER32!GetParent` at `0x18006925c`
- `USER32!GetParent` at `0x1800692af`
- `USER32!GetParent` at `0x1800692cd`
- `USER32!GetParent` at `0x1800692ef`
- `USER32!GetParent` at `0x180069359`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSharePageOverwrite::_OnPageNotify(
        CSharePageOverwrite *this,
        HWND a2,
        __int64 a3,
        const struct tagNMHDR *a4)
{
  __int64 v6; // rbx
  WPARAM v7; // rbx
  HWND v8; // rax
  HWND DlgItem; // rax
  HWND v10; // rax
  HWND v11; // rax
  HWND v12; // rax
  HWND v13; // rax
  HWND Parent; // rax
  int v16; // [rsp+20h] [rbp-38h]
  int v17; // [rsp+20h] [rbp-38h]
  int v18; // [rsp+20h] [rbp-38h]
  int v19; // [rsp+20h] [rbp-38h]
  LPARAM v20; // [rsp+30h] [rbp-28h] BYREF
  LPCWSTR lpString; // [rsp+38h] [rbp-20h] BYREF
  LPARAM lParam[3]; // [rsp+40h] [rbp-18h] BYREF
  LPARAM v23; // [rsp+98h] [rbp+40h] BYREF

  if ( a4->code == -208 )
  {
    Parent = GetParent(a2);
    SendMessageW(Parent, 0x472u, 0, 3005);
    v6 = 1;
    SetWindowLongPtrW(a2, 0, 1);
  }
  else if ( a4->code == -207 )
  {
    SetWindowLongPtrW(a2, 0, 3004);
    return 1;
  }
  else
  {
    v6 = 0;
    if ( a4->code == -200 )
    {
      lParam[0] = 0;
      CoTaskMemFree(0);
      if ( (int)TResourceStringAllocCopyEx<unsigned short *>(g_hInstance, v16, lParam) >= 0 )
      {
        v7 = (int)SendMessageW(a2, 0x485u, 0, 3007);
        v8 = GetParent(a2);
        SendMessageW(v8, 0x47Eu, v7, lParam[0]);
      }
      lpString = 0;
      CoTaskMemFree(0);
      if ( (int)TResourceStringAllocCopyEx<unsigned short *>(g_hInstance, v17, &lpString) >= 0 )
      {
        SetDlgItemTextW(a2, 4106, lpString);
        DlgItem = GetDlgItem(a2, 4106);
        ShowWindow(DlgItem, 5);
      }
      CSharePageOverwrite::_SetItemList(this, a2);
      v20 = 0;
      CoTaskMemFree(0);
      if ( (int)TResourceStringAllocCopyEx<unsigned short *>(g_hInstance, v18, &v20) >= 0 )
      {
        v10 = GetParent(a2);
        SendMessageW(v10, 0x479u, 0, v20);
      }
      v23 = 0;
      CoTaskMemFree(0);
      if ( (int)TResourceStringAllocCopyEx<unsigned short *>(g_hInstance, v19, &v23) >= 0 )
      {
        v11 = GetParent(a2);
        SendMessageW(v11, 0x489u, 0, v23);
      }
      v12 = GetParent(a2);
      PostMessageW(v12, 0x470u, 0, 6);
      v13 = GetParent(a2);
      PostMessageW(v13, 0x48Au, 6u, 4294967094LL);
      v6 = 1;
      CoTaskMemFree((LPVOID)v23);
      CoTaskMemFree((LPVOID)v20);
      CoTaskMemFree((LPVOID)lpString);
      CoTaskMemFree((LPVOID)lParam[0]);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180069110  push    rbp
0x180069112  push    rbx
0x180069113  push    rsi
0x180069114  push    rdi
0x180069115  mov     rbp, rsp
0x180069118  sub     rsp, 58h
0x18006911c  mov     rdi, rdx
0x18006911f  mov     rsi, rcx
0x180069122  cmp     dword ptr [r9+10h], 0FFFFFF30h
0x18006912a  jz      loc_180069356
0x180069130  cmp     dword ptr [r9+10h], 0FFFFFF31h
0x180069138  jz      loc_18006933E
0x18006913e  xor     ebx, ebx
0x180069140  cmp     dword ptr [r9+10h], 0FFFFFF38h
0x180069148  jnz     loc_180069389
0x18006914e  mov     [rbp+lParam], rbx
0x180069152  xor     ecx, ecx; pv
0x180069154  call    cs:__imp_CoTaskMemFree
0x18006915a  lea     rax, [rbp+lParam]
0x18006915e  mov     [rsp+58h+var_30], rax; void *
0x180069163  lea     r9, _ResourceStringAllocCopyExCoAlloc
0x18006916a  mov     edx, 0DADh
0x18006916f  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180069176  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18006917b  test    eax, eax
0x18006917d  js      short loc_1800691B7
0x18006917f  mov     r9d, 0BBFh; lParam
0x180069185  xor     r8d, r8d; wParam
0x180069188  mov     edx, 485h; Msg
0x18006918d  mov     rcx, rdi; hWnd
0x180069190  call    cs:__imp_SendMessageW
0x180069196  movsxd  rbx, eax
0x180069199  mov     rcx, rdi; hWnd
0x18006919c  call    cs:__imp_GetParent
0x1800691a2  mov     r9, [rbp+lParam]; lParam
0x1800691a6  mov     r8, rbx; wParam
0x1800691a9  mov     edx, 47Eh; Msg
0x1800691ae  mov     rcx, rax; hWnd
0x1800691b1  call    cs:__imp_SendMessageW
0x1800691b7  mov     [rbp+lpString], 0
0x1800691bf  xor     ecx, ecx; pv
0x1800691c1  call    cs:__imp_CoTaskMemFree
0x1800691c7  lea     rax, [rbp+lpString]
0x1800691cb  mov     [rsp+58h+var_30], rax; void *
0x1800691d0  lea     r9, _ResourceStringAllocCopyExCoAlloc
0x1800691d7  mov     edx, 0DAEh
0x1800691dc  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1800691e3  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800691e8  test    eax, eax
0x1800691ea  js      short loc_180069219
0x1800691ec  mov     r8, [rbp+lpString]; lpString
0x1800691f0  mov     ebx, 100Ah
0x1800691f5  mov     edx, ebx; nIDDlgItem
0x1800691f7  mov     rcx, rdi; hDlg
0x1800691fa  call    cs:__imp_SetDlgItemTextW
0x180069200  mov     edx, ebx; nIDDlgItem
0x180069202  mov     rcx, rdi; hDlg
0x180069205  call    cs:__imp_GetDlgItem
0x18006920b  mov     rcx, rax; hWnd
0x18006920e  mov     edx, 5; nCmdShow
0x180069213  call    cs:__imp_ShowWindow
0x180069219  mov     rdx, rdi; HWND
0x18006921c  mov     rcx, rsi; this
0x18006921f  call    ?_SetItemList@CSharePageOverwrite@@AEAAXPEAUHWND__@@@Z; CSharePageOverwrite::_SetItemList(HWND__ *)
0x180069224  mov     [rbp+var_28], 0
0x18006922c  xor     ecx, ecx; pv
0x18006922e  call    cs:__imp_CoTaskMemFree
0x180069234  lea     rax, [rbp+var_28]
0x180069238  mov     [rsp+58h+var_30], rax; void *
0x18006923d  lea     r9, _ResourceStringAllocCopyExCoAlloc
0x180069244  mov     edx, 0DAFh
0x180069249  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180069250  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180069255  test    eax, eax
0x180069257  js      short loc_180069277
0x180069259  mov     rcx, rdi; hWnd
0x18006925c  call    cs:__imp_GetParent
0x180069262  mov     r9, [rbp+var_28]; lParam
0x180069266  xor     r8d, r8d; wParam
0x180069269  mov     edx, 479h; Msg
0x18006926e  mov     rcx, rax; hWnd
0x180069271  call    cs:__imp_SendMessageW
0x180069277  mov     [rbp+arg_18], 0
0x18006927f  xor     ecx, ecx; pv
0x180069281  call    cs:__imp_CoTaskMemFree
0x180069287  lea     rax, [rbp+arg_18]
0x18006928b  mov     [rsp+58h+var_30], rax; void *
0x180069290  lea     r9, _ResourceStringAllocCopyExCoAlloc
0x180069297  mov     edx, 0DB0h
0x18006929c  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1800692a3  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800692a8  test    eax, eax
0x1800692aa  js      short loc_1800692CA
0x1800692ac  mov     rcx, rdi; hWnd
0x1800692af  call    cs:__imp_GetParent
0x1800692b5  mov     r9, [rbp+arg_18]; lParam
0x1800692b9  xor     r8d, r8d; wParam
0x1800692bc  mov     edx, 489h; Msg
0x1800692c1  mov     rcx, rax; hWnd
0x1800692c4  call    cs:__imp_SendMessageW
0x1800692ca  mov     rcx, rdi; hWnd
0x1800692cd  call    cs:__imp_GetParent
0x1800692d3  mov     rcx, rax; hWnd
0x1800692d6  mov     ebx, 6
0x1800692db  mov     r9d, ebx; lParam
0x1800692de  xor     r8d, r8d; wParam
0x1800692e1  mov     edx, 470h; Msg
0x1800692e6  call    cs:__imp_PostMessageW
0x1800692ec  mov     rcx, rdi; hWnd
0x1800692ef  call    cs:__imp_GetParent
0x1800692f5  mov     rcx, rax; hWnd
0x1800692f8  mov     r9d, 0FFFFFF36h; lParam
0x1800692fe  mov     r8d, ebx; wParam
0x180069301  mov     edx, 48Ah; Msg
0x180069306  call    cs:__imp_PostMessageW
0x18006930c  mov     ebx, 1
0x180069311  mov     rcx, [rbp+arg_18]; pv
0x180069315  call    cs:__imp_CoTaskMemFree
0x18006931b  nop
0x18006931c  mov     rcx, [rbp+var_28]; pv
0x180069320  call    cs:__imp_CoTaskMemFree
0x180069326  nop
0x180069327  mov     rcx, [rbp+lpString]; pv
0x18006932b  call    cs:__imp_CoTaskMemFree
0x180069331  nop
0x180069332  mov     rcx, [rbp+lParam]; pv
0x180069336  call    cs:__imp_CoTaskMemFree
0x18006933c  jmp     short loc_180069389
0x18006933e  xor     edx, edx; nIndex
0x180069340  mov     r8d, 0BBCh; dwNewLong
0x180069346  mov     rcx, rdi; hWnd
0x180069349  call    cs:__imp_SetWindowLongPtrW
0x18006934f  mov     ebx, 1
0x180069354  jmp     short loc_180069389
0x180069356  mov     rcx, rdi; hWnd
0x180069359  call    cs:__imp_GetParent
0x18006935f  mov     rcx, rax; hWnd
0x180069362  mov     r9d, 0BBDh; lParam
0x180069368  xor     r8d, r8d; wParam
0x18006936b  mov     edx, 472h; Msg
0x180069370  call    cs:__imp_SendMessageW
0x180069376  mov     ebx, 1
0x18006937b  mov     r8d, ebx; dwNewLong
0x18006937e  xor     edx, edx; nIndex
0x180069380  mov     rcx, rdi; hWnd
0x180069383  call    cs:__imp_SetWindowLongPtrW
0x180069389  mov     rax, rbx
0x18006938c  add     rsp, 58h
0x180069390  pop     rdi
0x180069391  pop     rsi
0x180069392  pop     rbx
0x180069393  pop     rbp
0x180069394  retn
```
