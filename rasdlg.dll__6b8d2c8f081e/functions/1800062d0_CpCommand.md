# CpCommand

- ea: `0x1800062d0`
- end: `0x1800064ee`
- name: `CpCommand`
- size: `542`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned __int16, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006500`

## callees

- `0x1800062d0`
- `0x18003ce6c`
- `0x18003d184`
- `0x180048f0c`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800063c3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800063c3`
- `USER32!GetWindowTextW` at `0x180006393`
- `USER32!GetWindowTextW` at `0x1800063b0`
- `USER32!GetWindowTextW` at `0x180006463`
- `USER32!GetWindowTextW` at `0x180006393`
- `USER32!GetWindowTextW` at `0x1800063b0`
- `USER32!GetWindowTextW` at `0x180006463`
- `USER32!EndDialog` at `0x1800064c7`
- `USER32!EndDialog` at `0x1800064c7`
- `USER32!SetWindowTextW` at `0x1800063f5`
- `USER32!SetWindowTextW` at `0x180006406`
- `USER32!SetWindowTextW` at `0x1800063f5`
- `USER32!SetWindowTextW` at `0x180006406`
- `USER32!GetWindowLongPtrW` at `0x180006372`
- `USER32!GetWindowLongPtrW` at `0x180006372`
- `USER32!SetFocus` at `0x180006410`
- `USER32!SetFocus` at `0x180006410`
- `rtutils!TracePrintfExA` at `0x180006320`
- `rtutils!TracePrintfExA` at `0x18000634a`
- `rtutils!TracePrintfExA` at `0x180006364`
- `rtutils!TracePrintfExA` at `0x180006320`
- `rtutils!TracePrintfExA` at `0x18000634a`
- `rtutils!TracePrintfExA` at `0x180006364`

## string_xrefs

- `0x18000630e`: `CpCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall CpCommand(HWND hWnd, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  int v5; // ebx
  DWORD v6; // ecx
  int v7; // ebx
  INT_PTR v9; // rdx
  HWND *WindowLongPtrW; // rbx
  __int64 v11; // rax
  WCHAR *v12; // rcx
  __int64 v13; // rdx
  WCHAR *v14; // rcx
  __int64 v15; // rax
  WCHAR *v16; // rcx
  __int64 v17; // rdx
  WCHAR *v18; // rcx
  WCHAR String[264]; // [rsp+30h] [rbp-458h] BYREF
  WCHAR String2[264]; // [rsp+240h] [rbp-248h] BYREF

  v5 = a3;
  v6 = g_dwTraceId;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "CpCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
    v6 = g_dwTraceId;
  }
  v7 = v5 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
      return 0;
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "Cancel pressed");
    v9 = 0;
  }
  else
  {
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "OK pressed");
    String[0] = 0;
    WindowLongPtrW = (HWND *)GetWindowLongPtrW(hWnd, 16);
    GetWindowTextW(WindowLongPtrW[3], String, 257);
    String2[0] = 0;
    GetWindowTextW(WindowLongPtrW[4], String2, 257);
    if ( lstrcmpW(String, String2) )
    {
      MsgDlgUtil(hWnd, 0x15Fu, 0, g_hinstDll, 0x169u);
      SetWindowTextW(WindowLongPtrW[3], &WideCharStr);
      SetWindowTextW(WindowLongPtrW[4], &WideCharStr);
      SetFocus(WindowLongPtrW[3]);
      v11 = 514;
      v12 = String;
      v13 = 514;
      do
      {
        *(_BYTE *)v12 = 0;
        v12 = (WCHAR *)((char *)v12 + 1);
        --v13;
      }
      while ( v13 );
      v14 = String2;
      do
      {
        *(_BYTE *)v14 = 0;
        v14 = (WCHAR *)((char *)v14 + 1);
        --v11;
      }
      while ( v11 );
      return 1;
    }
    if ( *(_DWORD *)*WindowLongPtrW )
    {
      **((_WORD **)*WindowLongPtrW + 1) = 0;
      GetWindowTextW(WindowLongPtrW[2], *((LPWSTR *)*WindowLongPtrW + 1), 257);
      EncodePasswordW(*((_QWORD *)*WindowLongPtrW + 1));
    }
    StringCchCopyWrapW(*((wchar_t **)*WindowLongPtrW + 2), 0x101u, String);
    EncodePasswordW(*((_QWORD *)*WindowLongPtrW + 2));
    v15 = 514;
    v16 = String;
    v17 = 514;
    do
    {
      *(_BYTE *)v16 = 0;
      v16 = (WCHAR *)((char *)v16 + 1);
      --v17;
    }
    while ( v17 );
    v18 = String2;
    do
    {
      *(_BYTE *)v18 = 0;
      v18 = (WCHAR *)((char *)v18 + 1);
      --v15;
    }
    while ( v15 );
    v9 = 1;
  }
  EndDialog(hWnd, v9);
  return 1;
}

```

## disassembly

```asm
0x1800062d0  push    rbx
0x1800062d2  push    rbp
0x1800062d3  push    rsi
0x1800062d4  push    rdi
0x1800062d5  sub     rsp, 468h
0x1800062dc  mov     rax, cs:__security_cookie
0x1800062e3  xor     rax, rsp
0x1800062e6  mov     [rsp+488h+var_38], rax
0x1800062ee  mov     rdi, rcx
0x1800062f1  movzx   ebx, r8w
0x1800062f5  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800062fb  or      esi, 0FFFFFFFFh
0x1800062fe  mov     rax, r9
0x180006301  mov     ebp, 0Ch
0x180006306  cmp     ecx, esi
0x180006308  jz      short loc_18000632C
0x18000630a  movzx   r9d, dx
0x18000630e  lea     r8, aCpcommandNDIDC; "CpCommand(n=%d,i=%d,c=$%x)"
0x180006315  mov     [rsp+488h+var_460], rax
0x18000631a  mov     edx, ebp; dwFlags
0x18000631c  mov     [rsp+488h+var_468], ebx
0x180006320  call    cs:__imp_TracePrintfExA
0x180006326  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000632c  sub     ebx, 1
0x18000632f  jz      short loc_180006357
0x180006331  cmp     ebx, 1
0x180006334  jz      short loc_18000633D
0x180006336  xor     eax, eax
0x180006338  jmp     loc_1800064D2
0x18000633d  cmp     ecx, esi
0x18000633f  jz      short loc_180006350
0x180006341  lea     r8, aCancelPressed; "Cancel pressed"
0x180006348  mov     edx, ebp; dwFlags
0x18000634a  call    cs:__imp_TracePrintfExA
0x180006350  xor     edx, edx
0x180006352  jmp     loc_1800064C4
0x180006357  cmp     ecx, esi
0x180006359  jz      short loc_18000636A
0x18000635b  lea     r8, aOkPressed; "OK pressed"
0x180006362  mov     edx, ebp; dwFlags
0x180006364  call    cs:__imp_TracePrintfExA
0x18000636a  mov     edx, 10h; nIndex
0x18000636f  mov     rcx, rdi; hWnd
0x180006372  call    cs:__imp_GetWindowLongPtrW
0x180006378  xor     esi, esi
0x18000637a  lea     rdx, [rsp+488h+String]; lpString
0x18000637f  mov     [rsp+488h+String], si
0x180006384  mov     ebp, 101h
0x180006389  mov     r8d, ebp; nMaxCount
0x18000638c  mov     rbx, rax
0x18000638f  mov     rcx, [rax+18h]; hWnd
0x180006393  call    cs:__imp_GetWindowTextW
0x180006399  mov     [rsp+488h+String2], si
0x1800063a1  lea     rdx, [rsp+488h+String2]; lpString
0x1800063a9  mov     rcx, [rbx+20h]; hWnd
0x1800063ad  mov     r8d, ebp; nMaxCount
0x1800063b0  call    cs:__imp_GetWindowTextW
0x1800063b6  lea     rdx, [rsp+488h+String2]; lpString2
0x1800063be  lea     rcx, [rsp+488h+String]; lpString1
0x1800063c3  call    cs:__imp_lstrcmpW
0x1800063c9  test    eax, eax
0x1800063cb  jz      short loc_180006447
0x1800063cd  mov     r9, cs:g_hinstDll; hInstance
0x1800063d4  lea     edx, [rbp+5Eh]; uID
0x1800063d7  xor     r8d, r8d; Arguments
0x1800063da  mov     [rsp+488h+var_468], 169h; UINT
0x1800063e2  mov     rcx, rdi; hWnd
0x1800063e5  call    MsgDlgUtil
0x1800063ea  mov     rcx, [rbx+18h]; hWnd
0x1800063ee  lea     rdx, WideCharStr; lpString
0x1800063f5  call    cs:__imp_SetWindowTextW
0x1800063fb  mov     rcx, [rbx+20h]; hWnd
0x1800063ff  lea     rdx, WideCharStr; lpString
0x180006406  call    cs:__imp_SetWindowTextW
0x18000640c  mov     rcx, [rbx+18h]; hWnd
0x180006410  call    cs:__imp_SetFocus
0x180006416  mov     eax, 202h
0x18000641b  lea     rcx, [rsp+488h+String]
0x180006420  mov     edx, eax
0x180006422  mov     [rcx], sil
0x180006425  inc     rcx
0x180006428  sub     rdx, 1
0x18000642c  jnz     short loc_180006422
0x18000642e  lea     rcx, [rsp+488h+String2]
0x180006436  mov     [rcx], sil
0x180006439  inc     rcx
0x18000643c  sub     rax, 1
0x180006440  jnz     short loc_180006436
0x180006442  jmp     loc_1800064CD
0x180006447  mov     rcx, [rbx]
0x18000644a  cmp     [rcx], esi
0x18000644c  jz      short loc_180006475
0x18000644e  mov     rcx, [rcx+8]
0x180006452  mov     r8d, ebp; nMaxCount
0x180006455  mov     [rcx], si
0x180006458  mov     rdx, [rbx]
0x18000645b  mov     rcx, [rbx+10h]; hWnd
0x18000645f  mov     rdx, [rdx+8]; lpString
0x180006463  call    cs:__imp_GetWindowTextW
0x180006469  mov     rcx, [rbx]
0x18000646c  mov     rcx, [rcx+8]
0x180006470  call    EncodePasswordW
0x180006475  mov     rcx, [rbx]
0x180006478  lea     r8, [rsp+488h+String]
0x18000647d  mov     rdx, rbp
0x180006480  mov     rcx, [rcx+10h]
0x180006484  call    StringCchCopyWrapW
0x180006489  mov     rcx, [rbx]
0x18000648c  mov     rcx, [rcx+10h]
0x180006490  call    EncodePasswordW
0x180006495  mov     eax, 202h
0x18000649a  lea     rcx, [rsp+488h+String]
0x18000649f  mov     edx, eax
0x1800064a1  mov     [rcx], sil
0x1800064a4  inc     rcx
0x1800064a7  sub     rdx, 1
0x1800064ab  jnz     short loc_1800064A1
0x1800064ad  lea     rcx, [rsp+488h+String2]
0x1800064b5  mov     [rcx], sil
0x1800064b8  inc     rcx
0x1800064bb  sub     rax, 1
0x1800064bf  jnz     short loc_1800064B5
0x1800064c1  lea     edx, [rax+1]; nResult
0x1800064c4  mov     rcx, rdi; hDlg
0x1800064c7  call    cs:__imp_EndDialog
0x1800064cd  mov     eax, 1
0x1800064d2  mov     rcx, [rsp+488h+var_38]
0x1800064da  xor     rcx, rsp; StackCookie
0x1800064dd  call    __security_check_cookie
0x1800064e2  add     rsp, 468h
0x1800064e9  pop     rdi
0x1800064ea  pop     rsi
0x1800064eb  pop     rbp
0x1800064ec  pop     rbx
0x1800064ed  retn
```
