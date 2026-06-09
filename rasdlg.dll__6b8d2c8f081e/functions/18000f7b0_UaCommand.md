# UaCommand

- ea: `0x18000f7b0`
- end: `0x18000f934`
- name: `UaCommand`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f940`

## callees

- `0x18000f7b0`
- `0x18000fdc8`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `msvcrt!wcspbrk` at `0x18000f878`
- `msvcrt!wcspbrk` at `0x18000f878`
- `USER32!GetWindowTextW` at `0x18000f866`
- `USER32!GetWindowTextW` at `0x18000f866`
- `USER32!EndDialog` at `0x18000f90e`
- `USER32!EndDialog` at `0x18000f90e`
- `USER32!SetWindowTextW` at `0x18000f89a`
- `USER32!SetWindowTextW` at `0x18000f8c5`
- `USER32!SetWindowTextW` at `0x18000f89a`
- `USER32!SetWindowTextW` at `0x18000f8c5`
- `USER32!EnableWindow` at `0x18000f889`
- `USER32!EnableWindow` at `0x18000f8a7`
- `USER32!EnableWindow` at `0x18000f889`
- `USER32!EnableWindow` at `0x18000f8a7`
- `rtutils!TracePrintfExA` at `0x18000f7fd`
- `rtutils!TracePrintfExA` at `0x18000f8f3`
- `rtutils!TracePrintfExA` at `0x18000f7fd`
- `rtutils!TracePrintfExA` at `0x18000f8f3`

## string_xrefs

- `0x18000f7ea`: `UaCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall UaCommand(__int64 a1, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  DWORD v6; // ecx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  wchar_t *v11; // rax
  HWND v12; // rcx
  HWND v13; // rcx
  INT_PTR v15; // rdx
  WCHAR String[264]; // [rsp+30h] [rbp-238h] BYREF

  v6 = g_dwTraceId;
  v7 = a3;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "UaCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
    v6 = g_dwTraceId;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    UaSave(a1);
    v15 = 1;
LABEL_21:
    EndDialog(*(HWND *)(a1 + 8), v15);
    return 1;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "Cancel pressed");
    v15 = 0;
    goto LABEL_21;
  }
  v10 = v9 - 1391;
  if ( v10 )
  {
    if ( v10 == 1 && a2 == 768 )
    {
      if ( *(_QWORD *)(a1 + 32) )
      {
        memset_0(String, 0, 0x202u);
        GetWindowTextW(*(HWND *)(a1 + 16), String, 257);
        v11 = wcspbrk(String, L"@\\");
        v12 = *(HWND *)(a1 + 32);
        if ( v11 )
        {
          EnableWindow(v12, 0);
          SetWindowTextW(*(HWND *)(a1 + 32), &WideCharStr);
        }
        else
        {
          EnableWindow(v12, 1);
        }
      }
      if ( *(_DWORD *)(a1 + 48) )
      {
        v13 = *(HWND *)(a1 + 24);
        *(_DWORD *)(a1 + 48) = 0;
        SetWindowTextW(v13, &WideCharStr);
      }
    }
  }
  else if ( a2 == 768 )
  {
    *(_DWORD *)(a1 + 48) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000f7b0  push    rbx
0x18000f7b2  push    rsi
0x18000f7b3  push    rdi
0x18000f7b4  sub     rsp, 250h
0x18000f7bb  mov     rax, cs:__security_cookie
0x18000f7c2  xor     rax, rsp
0x18000f7c5  mov     [rsp+268h+var_28], rax
0x18000f7cd  mov     rdi, rcx
0x18000f7d0  movzx   esi, dx
0x18000f7d3  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000f7d9  mov     rax, r9
0x18000f7dc  movzx   ebx, r8w
0x18000f7e0  cmp     ecx, 0FFFFFFFFh
0x18000f7e3  jz      short loc_18000F809
0x18000f7e5  mov     [rsp+268h+var_240], rax
0x18000f7ea  lea     r8, aUacommandNDIDC; "UaCommand(n=%d,i=%d,c=$%x)"
0x18000f7f1  mov     r9d, esi
0x18000f7f4  mov     [rsp+268h+var_248], ebx
0x18000f7f8  mov     edx, 0Ch; dwFlags
0x18000f7fd  call    cs:__imp_TracePrintfExA
0x18000f803  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000f809  sub     ebx, 1
0x18000f80c  jz      loc_18000F8FD
0x18000f812  sub     ebx, 1
0x18000f815  jz      loc_18000F8E2
0x18000f81b  sub     ebx, 56Fh
0x18000f821  jz      loc_18000F8CD
0x18000f827  cmp     ebx, 1
0x18000f82a  jnz     loc_18000F8DE
0x18000f830  mov     eax, 300h
0x18000f835  cmp     si, ax
0x18000f838  jnz     loc_18000F8DE
0x18000f83e  cmp     qword ptr [rdi+20h], 0
0x18000f843  jz      short loc_18000F8AD
0x18000f845  xor     edx, edx; Val
0x18000f847  lea     rcx, [rsp+268h+String]; void *
0x18000f84c  mov     r8d, 202h; Size
0x18000f852  call    memset_0
0x18000f857  mov     rcx, [rdi+10h]; hWnd
0x18000f85b  lea     rdx, [rsp+268h+String]; lpString
0x18000f860  mov     r8d, 101h; nMaxCount
0x18000f866  call    cs:__imp_GetWindowTextW
0x18000f86c  lea     rdx, Control; "@\\"
0x18000f873  lea     rcx, [rsp+268h+String]; String
0x18000f878  call    cs:__imp_wcspbrk
0x18000f87e  mov     rcx, [rdi+20h]; hWnd
0x18000f882  test    rax, rax
0x18000f885  jz      short loc_18000F8A2
0x18000f887  xor     edx, edx; bEnable
0x18000f889  call    cs:__imp_EnableWindow
0x18000f88f  mov     rcx, [rdi+20h]; hWnd
0x18000f893  lea     rdx, WideCharStr; lpString
0x18000f89a  call    cs:__imp_SetWindowTextW
0x18000f8a0  jmp     short loc_18000F8AD
0x18000f8a2  mov     edx, 1; bEnable
0x18000f8a7  call    cs:__imp_EnableWindow
0x18000f8ad  cmp     dword ptr [rdi+30h], 0
0x18000f8b1  jz      short loc_18000F8DE
0x18000f8b3  mov     rcx, [rdi+18h]; hWnd
0x18000f8b7  lea     rdx, WideCharStr; lpString
0x18000f8be  mov     dword ptr [rdi+30h], 0
0x18000f8c5  call    cs:__imp_SetWindowTextW
0x18000f8cb  jmp     short loc_18000F8DE
0x18000f8cd  mov     eax, 300h
0x18000f8d2  cmp     si, ax
0x18000f8d5  jnz     short loc_18000F8DE
0x18000f8d7  mov     dword ptr [rdi+30h], 0
0x18000f8de  xor     eax, eax
0x18000f8e0  jmp     short loc_18000F919
0x18000f8e2  cmp     ecx, 0FFFFFFFFh
0x18000f8e5  jz      short loc_18000F8F9
0x18000f8e7  lea     r8, aCancelPressed; "Cancel pressed"
0x18000f8ee  mov     edx, 0Ch; dwFlags
0x18000f8f3  call    cs:__imp_TracePrintfExA
0x18000f8f9  xor     edx, edx
0x18000f8fb  jmp     short loc_18000F90A
0x18000f8fd  mov     rcx, rdi
0x18000f900  call    UaSave
0x18000f905  mov     edx, 1; nResult
0x18000f90a  mov     rcx, [rdi+8]; hDlg
0x18000f90e  call    cs:__imp_EndDialog
0x18000f914  mov     eax, 1
0x18000f919  mov     rcx, [rsp+268h+var_28]
0x18000f921  xor     rcx, rsp; StackCookie
0x18000f924  call    __security_check_cookie
0x18000f929  add     rsp, 250h
0x18000f930  pop     rdi
0x18000f931  pop     rsi
0x18000f932  pop     rbx
0x18000f933  retn
```
