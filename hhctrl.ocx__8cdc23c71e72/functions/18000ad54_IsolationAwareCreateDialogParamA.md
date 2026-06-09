# IsolationAwareCreateDialogParamA

- ea: `0x18000ad54`
- end: `0x18000ae15`
- name: `IsolationAwareCreateDialogParamA`
- size: `193`
- prototype: `__int64 __fastcall(HINSTANCE hInstance, LPCSTR lpTemplateName, HWND hWndParent, DLGPROC lpDialogFunc, LPARAM)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800047d0`
- `0x18000da10`
- `0x18001ec9c`
- `0x180064f84`

## callees

- `0x180002b18`
- `0x18000ad54`
- `0x18004ce00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ade9`
- `KERNEL32!GetLastError` at `0x18000ade9`
- `KERNEL32!DeactivateActCtx` at `0x18000adfe`
- `KERNEL32!DeactivateActCtx` at `0x18000adfe`
- `KERNEL32!SetLastError` at `0x18000ae0a`
- `KERNEL32!SetLastError` at `0x18000ae0a`
- `USER32!CreateDialogParamA` at `0x18000adc1`
- `USER32!CreateDialogParamA` at `0x18000adc1`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateDialogParamA(
        HINSTANCE hInstance,
        LPCSTR lpTemplateName,
        HWND hWndParent,
        DLGPROC lpDialogFunc,
        LPARAM dwInitParam)
{
  HWND DialogParamA; // rax
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
  DialogParamA = CreateDialogParamA(hInstance, lpTemplateName, hWndParent, lpDialogFunc, dwInitParam);
  v11 = DialogParamA;
  v15 = DialogParamA;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( DialogParamA )
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
0x18000ad54  push    rbx
0x18000ad56  push    rsi
0x18000ad57  push    rdi
0x18000ad58  push    r14
0x18000ad5a  sub     rsp, 48h
0x18000ad5e  mov     rbx, r9
0x18000ad61  mov     rdi, r8
0x18000ad64  mov     rsi, rdx
0x18000ad67  mov     r14, rcx
0x18000ad6a  mov     [rsp+68h+var_30], 0
0x18000ad73  mov     [rsp+68h+ulCookie], 0
0x18000ad7c  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000ad83  jnz     short loc_18000ADA8
0x18000ad85  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000ad8c  jnz     short loc_18000ADA8
0x18000ad8e  lea     rcx, [rsp+68h+ulCookie]; lpCookie
0x18000ad93  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000ad98  test    eax, eax
0x18000ad9a  jnz     short loc_18000ADA8
0x18000ad9c  xor     eax, eax
0x18000ad9e  add     rsp, 48h
0x18000ada2  pop     r14
0x18000ada4  pop     rdi
0x18000ada5  pop     rsi
0x18000ada6  pop     rbx
0x18000ada7  retn
0x18000ada8  mov     rax, [rsp+68h+arg_20]
0x18000adb0  mov     [rsp+68h+dwInitParam], rax; dwInitParam
0x18000adb5  mov     r9, rbx; lpDialogFunc
0x18000adb8  mov     r8, rdi; hWndParent
0x18000adbb  mov     rdx, rsi; lpTemplateName
0x18000adbe  mov     rcx, r14; hInstance
0x18000adc1  call    cs:__imp_CreateDialogParamA
0x18000adc7  mov     rdi, rax
0x18000adca  mov     [rsp+68h+var_30], rax
0x18000adcf  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000add6  jz      short loc_18000ADE1
0x18000add8  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000addf  jnz     short loc_18000AE10
0x18000ade1  test    rdi, rdi
0x18000ade4  jnz     short loc_18000ADF3
0x18000ade6  lea     esi, [rdi+1]
0x18000ade9  call    cs:__imp_GetLastError
0x18000adef  mov     ebx, eax
0x18000adf1  jmp     short loc_18000ADF7
0x18000adf3  xor     esi, esi
0x18000adf5  xor     ebx, ebx
0x18000adf7  mov     rdx, [rsp+68h+ulCookie]; ulCookie
0x18000adfc  xor     ecx, ecx; dwFlags
0x18000adfe  call    cs:__imp_DeactivateActCtx
0x18000ae04  test    esi, esi
0x18000ae06  jz      short loc_18000AE10
0x18000ae08  mov     ecx, ebx; dwErrCode
0x18000ae0a  call    cs:__imp_SetLastError
0x18000ae10  mov     rax, rdi
0x18000ae13  jmp     short loc_18000AD9E
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
