# IsolationAwareCreateDialogParamW

- ea: `0x18000c004`
- end: `0x18000c0cf`
- name: `IsolationAwareCreateDialogParamW`
- size: `203`
- prototype: `__int64 __fastcall(int, int, int, int, LPARAM)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012ec0`

## callees

- `0x18000911c`
- `0x18000c004`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c0a3`
- `KERNEL32!GetLastError` at `0x180022b01`
- `KERNEL32!GetLastError` at `0x18000c0a3`
- `KERNEL32!GetLastError` at `0x180022b01`
- `KERNEL32!SetLastError` at `0x18000c0c4`
- `KERNEL32!SetLastError` at `0x180022b21`
- `KERNEL32!SetLastError` at `0x18000c0c4`
- `KERNEL32!SetLastError` at `0x180022b21`
- `KERNEL32!DeactivateActCtx` at `0x18000c0b8`
- `KERNEL32!DeactivateActCtx` at `0x180022b15`
- `KERNEL32!DeactivateActCtx` at `0x18000c0b8`
- `KERNEL32!DeactivateActCtx` at `0x180022b15`
- `USER32!CreateDialogParamW` at `0x18000c07b`
- `USER32!CreateDialogParamW` at `0x18000c07b`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateDialogParamW(__int64 a1, __int64 a2, __int64 a3, __int64 a4, LPARAM dwInitParam)
{
  HINSTANCE v5; // rbx
  HWND DialogParamW; // rax
  HWND v8; // rbx
  int v9; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+68h] [rbp+20h] BYREF

  v5 = g_hinst;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  DialogParamW = CreateDialogParamW(v5, (LPCWSTR)0x6A, 0, CDlg::_DlgProc, dwInitParam);
  v8 = DialogParamW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( DialogParamW )
    {
      v9 = 0;
      LastError = 0;
    }
    else
    {
      v9 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v9 )
      SetLastError(LastError);
  }
  return v8;
}

```

## disassembly

```asm
0x18000c004  mov     rax, rsp
0x18000c007  mov     [rax+8], rbx
0x18000c00b  mov     [rax+10h], rsi
0x18000c00f  mov     [rax+20h], r9
0x18000c013  push    rdi
0x18000c014  sub     rsp, 40h
0x18000c018  mov     rbx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x18000c01f  mov     qword ptr [rax-18h], 0
0x18000c027  mov     qword ptr [rax+20h], 0
0x18000c02f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000c036  jnz     short loc_18000C060
0x18000c038  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000c03f  jnz     short loc_18000C060
0x18000c041  lea     rcx, [rax+20h]; lpCookie
0x18000c045  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000c04a  test    eax, eax
0x18000c04c  jnz     short loc_18000C060
0x18000c04e  xor     eax, eax
0x18000c050  mov     rbx, [rsp+48h+arg_0]
0x18000c055  mov     rsi, [rsp+48h+arg_8]
0x18000c05a  add     rsp, 40h
0x18000c05e  pop     rdi
0x18000c05f  retn
0x18000c060  mov     rax, [rsp+48h+arg_20]
0x18000c065  mov     [rsp+48h+dwInitParam], rax; dwInitParam
0x18000c06a  lea     r9, ?_DlgProc@CDlg@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18000c071  xor     r8d, r8d; hWndParent
0x18000c074  lea     edx, [r8+6Ah]; lpTemplateName
0x18000c078  mov     rcx, rbx; hInstance
0x18000c07b  call    cs:__imp_CreateDialogParamW
0x18000c081  mov     rbx, rax
0x18000c084  mov     [rsp+48h+var_18], rax
0x18000c089  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000c090  jz      short loc_18000C09B
0x18000c092  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000c099  jnz     short loc_18000C0CA
0x18000c09b  test    rbx, rbx
0x18000c09e  jnz     short loc_18000C0AD
0x18000c0a0  lea     esi, [rbx+1]
0x18000c0a3  call    cs:__imp_GetLastError
0x18000c0a9  mov     edi, eax
0x18000c0ab  jmp     short loc_18000C0B1
0x18000c0ad  xor     esi, esi
0x18000c0af  xor     edi, edi
0x18000c0b1  mov     rdx, [rsp+48h+ulCookie]; ulCookie
0x18000c0b6  xor     ecx, ecx; dwFlags
0x18000c0b8  call    cs:__imp_DeactivateActCtx
0x18000c0be  test    esi, esi
0x18000c0c0  jz      short loc_18000C0CA
0x18000c0c2  mov     ecx, edi; dwErrCode
0x18000c0c4  call    cs:__imp_SetLastError
0x18000c0ca  mov     rax, rbx
0x18000c0cd  jmp     short loc_18000C050
0x180022ad8  push    rbx
0x180022ada  push    rbp
0x180022adb  push    rdi
0x180022adc  sub     rsp, 30h
0x180022ae0  mov     rbp, rdx
0x180022ae3  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180022aea  jz      short loc_180022AF5
0x180022aec  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180022af3  jnz     short loc_180022B28
0x180022af5  cmp     qword ptr [rbp+30h], 0
0x180022afa  jnz     short loc_180022B0B
0x180022afc  mov     edi, 1
0x180022b01  call    cs:__imp_GetLastError
0x180022b07  mov     ebx, eax
0x180022b09  jmp     short loc_180022B0F
0x180022b0b  xor     edi, edi
0x180022b0d  xor     ebx, ebx
0x180022b0f  mov     rdx, [rbp+68h]; ulCookie
0x180022b13  xor     ecx, ecx; dwFlags
0x180022b15  call    cs:__imp_DeactivateActCtx
0x180022b1b  test    edi, edi
0x180022b1d  jz      short loc_180022B28
0x180022b1f  mov     ecx, ebx; dwErrCode
0x180022b21  call    cs:__imp_SetLastError
0x180022b27  nop
0x180022b28  add     rsp, 30h
0x180022b2c  pop     rdi
0x180022b2d  pop     rbp
0x180022b2e  pop     rbx
0x180022b2f  retn
```
