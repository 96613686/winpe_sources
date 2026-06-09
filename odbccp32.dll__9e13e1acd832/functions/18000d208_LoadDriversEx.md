# LoadDriversEx

- ea: `0x18000d208`
- end: `0x18000d3ae`
- name: `LoadDriversEx`
- size: `422`
- prototype: `__int64 __fastcall(HWND hWnd, UINT, void (__fastcall *)(HWND, _QWORD, const WCHAR *))`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180003e10`
- `0x18000aeb0`
- `0x18000af80`
- `0x18000d1f0`

## callees

- `0x180001010`
- `0x1800017c0`
- `0x180002940`
- `0x1800074c4`
- `0x18000d208`
- `0x18000d3b4`
- `0x18000dc18`
- `0x18001418c`
- `0x180014ae0`
- `0x180015010`

## import_xrefs

- `msvcrt!calloc` at `0x18000d245`
- `msvcrt!calloc` at `0x18000d245`
- `USER32!EnableWindow` at `0x18000d371`
- `USER32!EnableWindow` at `0x18000d37f`
- `USER32!EnableWindow` at `0x18000d371`
- `USER32!EnableWindow` at `0x18000d37f`
- `USER32!SendMessageW` at `0x18000d360`
- `USER32!SendMessageW` at `0x18000d360`

## pseudocode

```c
__int64 __fastcall LoadDriversEx(HWND hWnd, UINT a2, void (__fastcall *a3)(HWND, _QWORD, const WCHAR *))
{
  __int64 result; // rax
  const WCHAR *v6; // rax
  __int64 v7; // rcx
  const WCHAR *v8; // rsi
  unsigned int v9; // ebp
  int v10; // eax
  const WCHAR *v11; // rdi
  __int64 v12; // rax
  int v13; // eax
  const WCHAR *v14; // [rsp+50h] [rbp-48h]
  WCHAR v15; // [rsp+58h] [rbp-40h] BYREF

  result = LoadListTitles(hWnd, a2);
  if ( !(_DWORD)result )
  {
    v6 = (const WCHAR *)calloc(0x8000u, 1u);
    v14 = v6;
    v8 = v6;
    if ( v6 )
    {
      v9 = 0;
      v10 = privateDriverNameHelper(v7, v6);
      SQLGetPrivateProfileStringCover(L"ODBC Drivers", 0, &SubKey, &v8[v10], 0x4000 - v10, L"ODBCINST.INI");
      v11 = v8;
      if ( *v8 )
      {
        do
        {
          if ( g_hkeyMachine == -2147483646
            || (int)cpGetPrivateProfileString(
                      HKEY_LOCAL_MACHINE,
                      L"ODBC Drivers",
                      v11,
                      (void *)&SubKey,
                      0xFFFFu,
                      0,
                      &v15,
                      6,
                      (__int64)L"ODBCINST.INI",
                      0) > 0 )
          {
            a3(hWnd, v9++, v11);
          }
          v12 = -1;
          do
            ++v12;
          while ( v11[v12] );
          v11 += v12 + 1;
        }
        while ( *v11 );
        v8 = v14;
      }
      result = SetColumnWidth(hWnd);
      if ( !(_DWORD)result )
      {
        v13 = SendMessageW(hWnd, 0x1004u, 0, 0);
        EnableWindow(hWnd, v13 != 0);
        EnableWindow(hWnd, 1);
        return OFree(v8);
      }
    }
    else
    {
      return MemError();
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d208  mov     [rsp+arg_18], rbx
0x18000d20d  push    rbp
0x18000d20e  push    rsi
0x18000d20f  push    rdi
0x18000d210  push    r14
0x18000d212  push    r15
0x18000d214  sub     rsp, 70h
0x18000d218  mov     rax, cs:__security_cookie
0x18000d21f  xor     rax, rsp
0x18000d222  mov     [rsp+98h+var_38], rax
0x18000d227  mov     r14, r8
0x18000d22a  mov     rbx, rcx
0x18000d22d  call    LoadListTitles
0x18000d232  xor     r15d, r15d
0x18000d235  test    eax, eax
0x18000d237  jnz     loc_18000D38D
0x18000d23d  lea     edx, [rax+1]; Size
0x18000d240  mov     ecx, 8000h; Count
0x18000d245  call    cs:__imp_calloc
0x18000d24b  mov     [rsp+98h+var_48], rax
0x18000d250  mov     rsi, rax
0x18000d253  test    rax, rax
0x18000d256  jnz     short loc_18000D262
0x18000d258  call    MemError
0x18000d25d  jmp     loc_18000D38D
0x18000d262  mov     rdx, rsi
0x18000d265  mov     ebp, r15d
0x18000d268  call    privateDriverNameHelper
0x18000d26d  mov     ecx, 4000h
0x18000d272  lea     r8, SubKey
0x18000d279  sub     ecx, eax
0x18000d27b  xor     edx, edx
0x18000d27d  cdqe
0x18000d27f  lea     r9, [rsi+rax*2]
0x18000d283  lea     rax, aOdbcinstIni; "ODBCINST.INI"
0x18000d28a  mov     [rsp+98h+var_70], rax
0x18000d28f  mov     [rsp+98h+var_78], ecx
0x18000d293  lea     rcx, aOdbcDrivers; "ODBC Drivers"
0x18000d29a  call    SQLGetPrivateProfileStringCover
0x18000d29f  mov     rdi, rsi
0x18000d2a2  cmp     [rsi], r15w
0x18000d2a6  jz      loc_18000D341
0x18000d2ac  lea     rsi, aOdbcinstIni; "ODBCINST.INI"
0x18000d2b3  cmp     cs:g_hkeyMachine, 0FFFFFFFF80000002h
0x18000d2be  jz      short loc_18000D30A
0x18000d2c0  mov     [rsp+98h+var_50], r15
0x18000d2c5  lea     rax, [rsp+98h+var_40]
0x18000d2ca  mov     [rsp+98h+var_58], rsi
0x18000d2cf  lea     r9, SubKey
0x18000d2d6  mov     [rsp+98h+var_60], 6
0x18000d2de  lea     rdx, aOdbcDrivers; "ODBC Drivers"
0x18000d2e5  mov     [rsp+98h+var_68], rax
0x18000d2ea  mov     r8, rdi
0x18000d2ed  mov     [rsp+98h+var_70], r15
0x18000d2f2  mov     rcx, 0FFFFFFFF80000002h
0x18000d2f9  mov     [rsp+98h+var_78], 0FFFFh
0x18000d301  call    cpGetPrivateProfileString
0x18000d306  test    eax, eax
0x18000d308  jle     short loc_18000D31C
0x18000d30a  mov     r8, rdi
0x18000d30d  mov     edx, ebp
0x18000d30f  mov     rcx, rbx
0x18000d312  mov     rax, r14
0x18000d315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d31a  inc     ebp
0x18000d31c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d320  inc     rax
0x18000d323  cmp     [rdi+rax*2], r15w
0x18000d328  jnz     short loc_18000D320
0x18000d32a  lea     rdi, [rdi+rax*2]
0x18000d32e  add     rdi, 2
0x18000d332  cmp     [rdi], r15w
0x18000d336  jnz     loc_18000D2B3
0x18000d33c  mov     rsi, [rsp+98h+var_48]
0x18000d341  mov     edx, 5
0x18000d346  mov     rcx, rbx; hWnd
0x18000d349  call    SetColumnWidth
0x18000d34e  test    eax, eax
0x18000d350  jnz     short loc_18000D38D
0x18000d352  xor     r9d, r9d; lParam
0x18000d355  xor     r8d, r8d; wParam
0x18000d358  mov     edx, 1004h; Msg
0x18000d35d  mov     rcx, rbx; hWnd
0x18000d360  call    cs:__imp_SendMessageW
0x18000d366  mov     edx, r15d
0x18000d369  mov     rcx, rbx; hWnd
0x18000d36c  test    eax, eax
0x18000d36e  setnz   dl; bEnable
0x18000d371  call    cs:__imp_EnableWindow
0x18000d377  mov     edx, 1; bEnable
0x18000d37c  mov     rcx, rbx; hWnd
0x18000d37f  call    cs:__imp_EnableWindow
0x18000d385  mov     rcx, rsi
0x18000d388  call    OFree
0x18000d38d  mov     rcx, [rsp+98h+var_38]
0x18000d392  xor     rcx, rsp; StackCookie
0x18000d395  call    __security_check_cookie
0x18000d39a  mov     rbx, [rsp+98h+arg_18]
0x18000d3a2  add     rsp, 70h
0x18000d3a6  pop     r15
0x18000d3a8  pop     r14
0x18000d3aa  pop     rdi
0x18000d3ab  pop     rsi
0x18000d3ac  pop     rbp
0x18000d3ad  retn
```
