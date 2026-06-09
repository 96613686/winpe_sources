# IsolationAwareCreateDialogParamW

- ea: `0x18000ae1c`
- end: `0x18000aedd`
- name: `IsolationAwareCreateDialogParamW`
- size: `193`
- prototype: `__int64 __fastcall(HINSTANCE hInstance, LPCWSTR lpTemplateName, HWND hWndParent, DLGPROC lpDialogFunc, LPARAM)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800047d0`
- `0x18000da10`
- `0x180064f84`

## callees

- `0x180002b18`
- `0x18000ae1c`
- `0x18004ce00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000aeb1`
- `KERNEL32!GetLastError` at `0x18000aeb1`
- `KERNEL32!DeactivateActCtx` at `0x18000aec6`
- `KERNEL32!DeactivateActCtx` at `0x18000aec6`
- `KERNEL32!SetLastError` at `0x18000aed2`
- `KERNEL32!SetLastError` at `0x18000aed2`
- `USER32!CreateDialogParamW` at `0x18000ae89`
- `USER32!CreateDialogParamW` at `0x18000ae89`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateDialogParamW(
        HINSTANCE hInstance,
        LPCWSTR lpTemplateName,
        HWND hWndParent,
        DLGPROC lpDialogFunc,
        LPARAM dwInitParam)
{
  HWND DialogParamW; // rax
  HWND v11; // rdi
  int v12; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp-38h] BYREF
  HWND v15; // [rsp+38h] [rbp-30h]

  v15 = 0;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  DialogParamW = CreateDialogParamW(hInstance, lpTemplateName, hWndParent, lpDialogFunc, dwInitParam);
  v11 = DialogParamW;
  v15 = DialogParamW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( DialogParamW )
    {
      v12 = 0;
      LastError = 0;
    }
    else
    {
      v12 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v12 )
      SetLastError(LastError);
  }
  return v11;
}

```

## disassembly

```asm
0x18000ae1c  push    rbx
0x18000ae1e  push    rsi
0x18000ae1f  push    rdi
0x18000ae20  push    r14
0x18000ae22  sub     rsp, 48h
0x18000ae26  mov     rbx, r9
0x18000ae29  mov     rdi, r8
0x18000ae2c  mov     rsi, rdx
0x18000ae2f  mov     r14, rcx
0x18000ae32  mov     [rsp+68h+var_30], 0
0x18000ae3b  mov     [rsp+68h+ulCookie], 0
0x18000ae44  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000ae4b  jnz     short loc_18000AE70
0x18000ae4d  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000ae54  jnz     short loc_18000AE70
0x18000ae56  lea     rcx, [rsp+68h+ulCookie]; lpCookie
0x18000ae5b  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000ae60  test    eax, eax
0x18000ae62  jnz     short loc_18000AE70
0x18000ae64  xor     eax, eax
0x18000ae66  add     rsp, 48h
0x18000ae6a  pop     r14
0x18000ae6c  pop     rdi
0x18000ae6d  pop     rsi
0x18000ae6e  pop     rbx
0x18000ae6f  retn
0x18000ae70  mov     rax, [rsp+68h+arg_20]
0x18000ae78  mov     [rsp+68h+dwInitParam], rax; dwInitParam
0x18000ae7d  mov     r9, rbx; lpDialogFunc
0x18000ae80  mov     r8, rdi; hWndParent
0x18000ae83  mov     rdx, rsi; lpTemplateName
0x18000ae86  mov     rcx, r14; hInstance
0x18000ae89  call    cs:__imp_CreateDialogParamW
0x18000ae8f  mov     rdi, rax
0x18000ae92  mov     [rsp+68h+var_30], rax
0x18000ae97  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000ae9e  jz      short loc_18000AEA9
0x18000aea0  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000aea7  jnz     short loc_18000AED8
0x18000aea9  test    rdi, rdi
0x18000aeac  jnz     short loc_18000AEBB
0x18000aeae  lea     esi, [rdi+1]
0x18000aeb1  call    cs:__imp_GetLastError
0x18000aeb7  mov     ebx, eax
0x18000aeb9  jmp     short loc_18000AEBF
0x18000aebb  xor     esi, esi
0x18000aebd  xor     ebx, ebx
0x18000aebf  mov     rdx, [rsp+68h+ulCookie]; ulCookie
0x18000aec4  xor     ecx, ecx; dwFlags
0x18000aec6  call    cs:__imp_DeactivateActCtx
0x18000aecc  test    esi, esi
0x18000aece  jz      short loc_18000AED8
0x18000aed0  mov     ecx, ebx; dwErrCode
0x18000aed2  call    cs:__imp_SetLastError
0x18000aed8  mov     rax, rdi
0x18000aedb  jmp     short loc_18000AE66
0x180076232  push    rbx
0x180076234  push    rbp
0x180076235  push    rdi
0x180076236  sub     rsp, 30h
0x18007623a  mov     rbp, rdx
0x18007623d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180076244  jz      short loc_18007624F
0x180076246  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18007624d  jnz     short loc_180076282
0x18007624f  cmp     qword ptr [rbp+38h], 0
0x180076254  jnz     short loc_180076265
0x180076256  mov     edi, 1
0x18007625b  call    cs:__imp_GetLastError
0x180076261  mov     ebx, eax
0x180076263  jmp     short loc_180076269
0x180076265  xor     edi, edi
0x180076267  xor     ebx, ebx
0x180076269  mov     rdx, [rbp+30h]; ulCookie
0x18007626d  xor     ecx, ecx; dwFlags
0x18007626f  call    cs:__imp_DeactivateActCtx
0x180076275  test    edi, edi
0x180076277  jz      short loc_180076282
0x180076279  mov     ecx, ebx; dwErrCode
0x18007627b  call    cs:__imp_SetLastError
0x180076281  nop
0x180076282  add     rsp, 30h
0x180076286  pop     rdi
0x180076287  pop     rbp
0x180076288  pop     rbx
0x180076289  retn
```
