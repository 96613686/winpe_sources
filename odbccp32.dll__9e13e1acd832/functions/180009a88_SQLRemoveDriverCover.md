# SQLRemoveDriverCover

- ea: `0x180009a88`
- end: `0x180009b6c`
- name: `SQLRemoveDriverCover`
- size: `228`
- prototype: `__int64 __fastcall(wchar_t *String1, int, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009bd0`

## callees

- `0x180001010`
- `0x180004bac`
- `0x180006afc`
- `0x180009a88`
- `0x180014ae0`

## import_xrefs

- `USER32!GetActiveWindow` at `0x180009b2a`
- `USER32!GetActiveWindow` at `0x180009b2a`

## pseudocode

```c
__int64 __fastcall SQLRemoveDriverCover(wchar_t *String1, int a2, char *a3)
{
  unsigned __int64 v6; // rax
  int v7; // ecx
  HWND ActiveWindow; // rax
  WCHAR v10[8]; // [rsp+50h] [rbp-38h] BYREF

  if ( !String1 )
    goto LABEL_9;
  if ( !*String1 )
    goto LABEL_9;
  v6 = -1;
  do
    ++v6;
  while ( String1[v6] );
  if ( v6 < 0x104 )
  {
    if ( (unsigned int)cpGetPrivateProfileString(
                         HKEY_LOCAL_MACHINE,
                         L"ODBC Drivers",
                         String1,
                         (void *)&SubKey,
                         0xFFFFu,
                         0,
                         v10,
                         10,
                         (__int64)L"ODBCINST.INI",
                         0) )
    {
      ActiveWindow = GetActiveWindow();
      return RemoveDriver(ActiveWindow, String1, a2, a3);
    }
    v7 = 6;
  }
  else
  {
LABEL_9:
    v7 = 7;
  }
  PostInstError(v7);
  return 0;
}

```

## disassembly

```asm
0x180009a88  mov     [rsp+arg_8], rbx
0x180009a8d  push    rbp
0x180009a8e  push    rsi
0x180009a8f  push    rdi
0x180009a90  sub     rsp, 70h
0x180009a94  mov     rax, cs:__security_cookie
0x180009a9b  xor     rax, rsp
0x180009a9e  mov     [rsp+88h+var_28], rax
0x180009aa3  xor     ebp, ebp
0x180009aa5  mov     rsi, r8
0x180009aa8  mov     edi, edx
0x180009aaa  mov     rbx, rcx
0x180009aad  test    rcx, rcx
0x180009ab0  jz      loc_180009B43
0x180009ab6  cmp     [rcx], bp
0x180009ab9  jz      loc_180009B43
0x180009abf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009ac3  inc     rax
0x180009ac6  cmp     [rcx+rax*2], bp
0x180009aca  jnz     short loc_180009AC3
0x180009acc  cmp     rax, 104h
0x180009ad2  jnb     short loc_180009B43
0x180009ad4  mov     [rsp+88h+var_40], rbp
0x180009ad9  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x180009ae0  mov     [rsp+88h+var_48], rax
0x180009ae5  lea     r9, SubKey
0x180009aec  mov     [rsp+88h+var_50], 0Ah
0x180009af4  lea     rax, [rsp+88h+var_38]
0x180009af9  mov     [rsp+88h+var_58], rax
0x180009afe  lea     rdx, aOdbcDrivers; "ODBC Drivers"
0x180009b05  mov     [rsp+88h+var_60], rbp
0x180009b0a  mov     r8, rbx
0x180009b0d  mov     rcx, 0FFFFFFFF80000002h
0x180009b14  mov     [rsp+88h+var_68], 0FFFFh
0x180009b1c  call    cpGetPrivateProfileString
0x180009b21  test    eax, eax
0x180009b23  jnz     short loc_180009B2A
0x180009b25  lea     ecx, [rax+6]
0x180009b28  jmp     short loc_180009B48
0x180009b2a  call    cs:__imp_GetActiveWindow
0x180009b30  mov     r9, rsi
0x180009b33  mov     r8d, edi
0x180009b36  mov     rcx, rax; hWnd
0x180009b39  mov     rdx, rbx; String1
0x180009b3c  call    RemoveDriver
0x180009b41  jmp     short loc_180009B4F
0x180009b43  mov     ecx, 7
0x180009b48  call    PostInstError
0x180009b4d  xor     eax, eax
0x180009b4f  mov     rcx, [rsp+88h+var_28]
0x180009b54  xor     rcx, rsp; StackCookie
0x180009b57  call    __security_check_cookie
0x180009b5c  mov     rbx, [rsp+88h+arg_8]
0x180009b64  add     rsp, 70h
0x180009b68  pop     rdi
0x180009b69  pop     rsi
0x180009b6a  pop     rbp
0x180009b6b  retn
```
