# CleanupMgrWarningPrompt(HWND__ *)

- ea: `0x14000c538`
- end: `0x14000c671`
- name: `?CleanupMgrWarningPrompt@@YAHPEAUHWND__@@@Z`
- size: `313`
- prototype: `_BOOL8 __fastcall(HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000c358`

## callees

- `0x1400029a0`
- `0x140003390`
- `0x14000c538`

## import_xrefs

- `USER32!LoadStringW` at `0x14000c5d8`
- `USER32!LoadStringW` at `0x14000c5d8`
- `USER32!GetWindowLongPtrW` at `0x14000c565`
- `USER32!GetWindowLongPtrW` at `0x14000c565`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14000c63e`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14000c63e`

## pseudocode

```c
_BOOL8 __fastcall CleanupMgrWarningPrompt(HWND a1)
{
  LONG_PTR WindowLongPtrW; // r8
  int i; // edx
  int pnButton; // [rsp+20h] [rbp-E0h] BYREF
  int v6; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR *v7; // [rsp+2Ch] [rbp-D4h]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[40]; // [rsp+E0h] [rbp-20h] BYREF

  WindowLongPtrW = GetWindowLongPtrW(a1, 16);
  if ( WindowLongPtrW )
  {
    for ( i = 0; i < *(_DWORD *)(WindowLongPtrW + 1736); ++i )
    {
      if ( *(_DWORD *)(616LL * i + *(_QWORD *)(WindowLongPtrW + 1744) + 604) == 1 )
      {
        pnButton = 0;
        memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
        LoadStringW(g_hInstance, 0x15u, Buffer, 40);
        v6 = 1;
        v7 = Buffer;
        pTaskConfig.hInstance = g_hInstance;
        pTaskConfig.cbSize = 160;
        pTaskConfig.pButtons = (const TASKDIALOG_BUTTON *)&v6;
        pTaskConfig.hwndParent = a1;
        pTaskConfig.dwCommonButtons = 8;
        pTaskConfig.pszWindowTitle = (PCWSTR)19;
        pTaskConfig.pszMainInstruction = (PCWSTR)20;
        pTaskConfig.cButtons = 1;
        pTaskConfig.nDefaultButton = 1;
        TaskDialogIndirect(&pTaskConfig, &pnButton, 0, 0);
        return pnButton == 1;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14000c538  mov     [rsp-8+arg_8], rbx
0x14000c53d  mov     [rsp-8+arg_10], rsi
0x14000c542  push    rbp
0x14000c543  lea     rbp, [rsp-40h]
0x14000c548  sub     rsp, 140h
0x14000c54f  mov     rax, cs:__security_cookie
0x14000c556  xor     rax, rsp
0x14000c559  mov     [rbp+40h+var_10], rax
0x14000c55d  mov     edx, 10h; nIndex
0x14000c562  mov     rbx, rcx
0x14000c565  call    cs:__imp_GetWindowLongPtrW
0x14000c56b  mov     r8, rax
0x14000c56e  mov     esi, 1
0x14000c573  test    rax, rax
0x14000c576  jz      loc_14000C64E
0x14000c57c  xor     edx, edx
0x14000c57e  cmp     edx, [r8+6C8h]
0x14000c585  jge     loc_14000C64E
0x14000c58b  movsxd  rax, edx
0x14000c58e  imul    rcx, rax, 268h
0x14000c595  mov     rax, [r8+6D0h]
0x14000c59c  cmp     [rcx+rax+25Ch], esi
0x14000c5a3  jz      short loc_14000C5A9
0x14000c5a5  add     edx, esi
0x14000c5a7  jmp     short loc_14000C57E
0x14000c5a9  xor     edx, edx; Val
0x14000c5ab  mov     [rsp+140h+pnButton], 0
0x14000c5b3  mov     r8d, 0A0h; Size
0x14000c5b9  lea     rcx, [rsp+140h+pTaskConfig]; void *
0x14000c5be  call    memset_0
0x14000c5c3  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x14000c5ca  lea     r8, [rbp+40h+Buffer]; lpBuffer
0x14000c5ce  mov     r9d, 28h ; '('; cchBufferMax
0x14000c5d4  lea     edx, [r9-13h]; uID
0x14000c5d8  call    cs:__imp_LoadStringW
0x14000c5de  lea     rax, [rbp+40h+Buffer]
0x14000c5e2  mov     [rsp+140h+var_118], esi
0x14000c5e6  mov     [rsp+140h+var_114], rax
0x14000c5eb  lea     rdx, [rsp+140h+pnButton]; pnButton
0x14000c5f0  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x14000c5f7  lea     rcx, [rsp+140h+pTaskConfig]; pTaskConfig
0x14000c5fc  mov     [rsp+140h+pTaskConfig.hInstance], rax
0x14000c601  xor     r9d, r9d; pfVerificationFlagChecked
0x14000c604  lea     rax, [rsp+140h+var_118]
0x14000c609  mov     [rsp+140h+pTaskConfig.cbSize], 0A0h
0x14000c611  xor     r8d, r8d; pnRadioButton
0x14000c614  mov     [rbp+40h+pTaskConfig.pButtons], rax
0x14000c618  mov     [rsp+140h+pTaskConfig.hwndParent], rbx
0x14000c61d  mov     [rsp+140h+pTaskConfig.dwCommonButtons], 8
0x14000c625  mov     [rsp+140h+pTaskConfig.pszWindowTitle], 13h
0x14000c62e  mov     [rsp+140h+pTaskConfig.pszMainInstruction], 14h
0x14000c637  mov     [rsp+140h+pTaskConfig.cButtons], esi
0x14000c63b  mov     [rbp+40h+pTaskConfig.nDefaultButton], esi
0x14000c63e  call    cs:__imp_TaskDialogIndirect
0x14000c644  cmp     [rsp+140h+pnButton], esi
0x14000c648  jz      short loc_14000C64E
0x14000c64a  xor     eax, eax
0x14000c64c  jmp     short loc_14000C650
0x14000c64e  mov     eax, esi
0x14000c650  mov     rcx, [rbp+40h+var_10]
0x14000c654  xor     rcx, rsp; StackCookie
0x14000c657  call    __security_check_cookie
0x14000c65c  lea     r11, [rsp+140h+var_s0]
0x14000c664  mov     rbx, [r11+18h]
0x14000c668  mov     rsi, [r11+20h]
0x14000c66c  mov     rsp, r11
0x14000c66f  pop     rbp
0x14000c670  retn
```
