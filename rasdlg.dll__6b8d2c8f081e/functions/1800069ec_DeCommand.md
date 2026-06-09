# DeCommand

- ea: `0x1800069ec`
- end: `0x180006b4e`
- name: `DeCommand`
- size: `354`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned __int16, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006b60`

## callees

- `0x1800069ec`
- `0x180006d5c`
- `0x18002cd5c`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006a44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006a44`
- `USER32!SendMessageW` at `0x180006ae4`
- `USER32!SendMessageW` at `0x180006ae4`
- `USER32!EndDialog` at `0x180006b38`
- `USER32!EndDialog` at `0x180006b38`
- `USER32!GetWindowLongPtrW` at `0x180006a92`
- `USER32!GetWindowLongPtrW` at `0x180006a92`
- `rtutils!TracePrintfExA` at `0x180006a2b`
- `rtutils!TracePrintfExA` at `0x180006a63`
- `rtutils!TracePrintfExA` at `0x180006aff`
- `rtutils!TracePrintfExA` at `0x180006b22`
- `rtutils!TracePrintfExA` at `0x180006a2b`
- `rtutils!TracePrintfExA` at `0x180006a63`
- `rtutils!TracePrintfExA` at `0x180006aff`
- `rtutils!TracePrintfExA` at `0x180006b22`

## string_xrefs

- `0x180006a18`: `DeCommand(n=%d,i=%d,c=$%x)`
- `0x180006a50`: `Current proces:(0x%d), Current Thread:(0x%d)`

## pseudocode

```c
__int64 __fastcall DeCommand(HWND hDlg, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  DWORD v6; // ecx
  int v7; // edi
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  int v10; // edi
  int v11; // edi
  LONG_PTR WindowLongPtrW; // rax
  LONG_PTR v13; // rbx
  __int64 (*v14)(void); // rax
  int v15; // eax
  INT_PTR v17; // rdx

  v6 = g_dwTraceId;
  v7 = a3;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "DeCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
    v6 = g_dwTraceId;
    if ( g_dwTraceId != -1 )
    {
      CurrentThreadId = GetCurrentThreadId();
      CurrentProcessId = GetCurrentProcessId();
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "Current proces:(0x%d), Current Thread:(0x%d)",
        CurrentProcessId,
        CurrentThreadId);
      v6 = g_dwTraceId;
    }
  }
  v10 = v7 - 1;
  if ( !v10 )
  {
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "Redial pressed");
    DeEnableDiagnostic(hDlg);
    v17 = 1;
    goto LABEL_21;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "Cancel pressed");
    DeEnableDiagnostic(hDlg);
    v17 = 0;
LABEL_21:
    EndDialog(hDlg, v17);
    return 1;
  }
  if ( v11 == 1710 && !a2 )
  {
    WindowLongPtrW = GetWindowLongPtrW(hDlg, 16);
    v13 = WindowLongPtrW;
    if ( WindowLongPtrW )
    {
      if ( !*(_QWORD *)(WindowLongPtrW + 184)
        && (int)GetCoCreateInstanceElevationHandle(
                  *(HWND *)(WindowLongPtrW + 8),
                  (struct _GUID *)(WindowLongPtrW + 184),
                  0) < 0
        && *(_QWORD *)(v13 + 72) )
      {
        v14 = *(__int64 (**)(void))(v13 + 112);
        if ( v14 )
        {
          v15 = v14();
          SendMessageW(*(HWND *)(v13 + 144), 0xF1u, v15, 0);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800069ec  push    rbx
0x1800069ee  push    rbp
0x1800069ef  push    rsi
0x1800069f0  push    rdi
0x1800069f1  push    r14
0x1800069f3  sub     rsp, 30h
0x1800069f7  mov     rsi, rcx
0x1800069fa  movzx   ebp, dx
0x1800069fd  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180006a03  or      r14d, 0FFFFFFFFh
0x180006a07  movzx   edi, r8w
0x180006a0b  mov     rax, r9
0x180006a0e  cmp     ecx, r14d
0x180006a11  jz      short loc_180006A6F
0x180006a13  mov     [rsp+58h+var_30], rax
0x180006a18  lea     r8, aDecommandNDIDC; "DeCommand(n=%d,i=%d,c=$%x)"
0x180006a1f  mov     r9d, ebp
0x180006a22  mov     [rsp+58h+var_38], edi
0x180006a26  mov     edx, 0Ch; dwFlags
0x180006a2b  call    cs:__imp_TracePrintfExA
0x180006a31  mov     ecx, cs:g_dwTraceId
0x180006a37  cmp     ecx, r14d
0x180006a3a  jz      short loc_180006A6F
0x180006a3c  call    cs:__imp_GetCurrentThreadId
0x180006a42  mov     ebx, eax
0x180006a44  call    cs:__imp_GetCurrentProcessId
0x180006a4a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180006a50  lea     r8, aCurrentProces0; "Current proces:(0x%d), Current Thread:("...
0x180006a57  mov     r9d, eax
0x180006a5a  mov     [rsp+58h+var_38], ebx
0x180006a5e  mov     edx, 0Ch; dwFlags
0x180006a63  call    cs:__imp_TracePrintfExA
0x180006a69  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180006a6f  sub     edi, 1
0x180006a72  jz      loc_180006B11
0x180006a78  sub     edi, 1
0x180006a7b  jz      short loc_180006AEE
0x180006a7d  cmp     edi, 6AEh
0x180006a83  jnz     short loc_180006AEA
0x180006a85  xor     eax, eax
0x180006a87  cmp     ax, bp
0x180006a8a  jnz     short loc_180006AEA
0x180006a8c  lea     edx, [rax+10h]; nIndex
0x180006a8f  mov     rcx, rsi; hWnd
0x180006a92  call    cs:__imp_GetWindowLongPtrW
0x180006a98  mov     rbx, rax
0x180006a9b  test    rax, rax
0x180006a9e  jz      short loc_180006AEA
0x180006aa0  lea     rdx, [rax+0B8h]; void **
0x180006aa7  cmp     qword ptr [rdx], 0
0x180006aab  jnz     short loc_180006AEA
0x180006aad  mov     rcx, [rax+8]; hwndOwner
0x180006ab1  xor     r8d, r8d
0x180006ab4  call    GetCoCreateInstanceElevationHandle
0x180006ab9  test    eax, eax
0x180006abb  jns     short loc_180006AEA
0x180006abd  cmp     qword ptr [rbx+48h], 0
0x180006ac2  jz      short loc_180006AEA
0x180006ac4  mov     rax, [rbx+70h]
0x180006ac8  test    rax, rax
0x180006acb  jz      short loc_180006AEA
0x180006acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ad2  mov     rcx, [rbx+90h]; hWnd
0x180006ad9  xor     r9d, r9d; lParam
0x180006adc  movsxd  r8, eax; wParam
0x180006adf  mov     edx, 0F1h; Msg
0x180006ae4  call    cs:__imp_SendMessageW
0x180006aea  xor     eax, eax
0x180006aec  jmp     short loc_180006B43
0x180006aee  cmp     ecx, r14d
0x180006af1  jz      short loc_180006B05
0x180006af3  lea     r8, aCancelPressed; "Cancel pressed"
0x180006afa  mov     edx, 0Ch; dwFlags
0x180006aff  call    cs:__imp_TracePrintfExA
0x180006b05  mov     rcx, rsi
0x180006b08  call    DeEnableDiagnostic
0x180006b0d  xor     edx, edx
0x180006b0f  jmp     short loc_180006B35
0x180006b11  cmp     ecx, r14d
0x180006b14  jz      short loc_180006B28
0x180006b16  lea     r8, aRedialPressed; "Redial pressed"
0x180006b1d  mov     edx, 0Ch; dwFlags
0x180006b22  call    cs:__imp_TracePrintfExA
0x180006b28  mov     rcx, rsi
0x180006b2b  call    DeEnableDiagnostic
0x180006b30  mov     edx, 1; nResult
0x180006b35  mov     rcx, rsi; hDlg
0x180006b38  call    cs:__imp_EndDialog
0x180006b3e  mov     eax, 1
0x180006b43  add     rsp, 30h
0x180006b47  pop     r14
0x180006b49  pop     rdi
0x180006b4a  pop     rsi
0x180006b4b  pop     rbp
0x180006b4c  pop     rbx
0x180006b4d  retn
```
