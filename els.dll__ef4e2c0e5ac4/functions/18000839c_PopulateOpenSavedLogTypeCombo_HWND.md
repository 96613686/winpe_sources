# _PopulateOpenSavedLogTypeCombo(HWND__ *)

- ea: `0x18000839c`
- end: `0x180008692`
- name: `?_PopulateOpenSavedLogTypeCombo@@YAXPEAUHWND__@@@Z`
- size: `758`
- prototype: `void __fastcall(HWND hDlg)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007f70`

## callees

- `0x180002bb8`
- `0x180005274`
- `0x180007014`
- `0x1800070ec`
- `0x18000728c`
- `0x180007724`
- `0x18000839c`
- `0x180008728`
- `0x18001abd8`
- `0x18001ac04`
- `0x18001ae60`
- `0x18001fcf0`
- `0x180020430`
- `0x180022292`
- `0x1800222d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180008446`
- `msvcrt!_wcsicmp` at `0x180008446`
- `USER32!SendMessageW` at `0x18000841f`
- `USER32!SendMessageW` at `0x180008438`
- `USER32!SendMessageW` at `0x1800084fb`
- `USER32!SendMessageW` at `0x18000850f`
- `USER32!SendMessageW` at `0x180008523`
- `USER32!SendMessageW` at `0x18000841f`
- `USER32!SendMessageW` at `0x180008438`
- `USER32!SendMessageW` at `0x1800084fb`
- `USER32!SendMessageW` at `0x18000850f`
- `USER32!SendMessageW` at `0x180008523`
- `USER32!GetDlgItem` at `0x180008408`
- `USER32!GetDlgItem` at `0x180008531`
- `USER32!GetDlgItem` at `0x180008408`
- `USER32!GetDlgItem` at `0x180008531`
- `USER32!SetWindowTextW` at `0x180008541`
- `USER32!SetWindowTextW` at `0x180008541`
- `USER32!SetCursor` at `0x1800085ae`
- `USER32!SetCursor` at `0x1800085ae`

## string_xrefs

- `0x180008591`: `SYSTEM\CurrentControlSet\Services\EventLog`
- `0x1800085cc`: `SYSTEM\CurrentControlSet\Services\EventLog`
- `0x180008629`: `SYSTEM\CurrentControlSet\Services\EventLog`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall _PopulateOpenSavedLogTypeCombo(HWND hDlg, __int64 a2, size_t *a3)
{
  HWND DlgItem; // rdi
  const wchar_t *v5; // rax
  __int64 v6; // rax
  unsigned __int64 v7; // r14
  unsigned __int16 *v8; // rax
  LPARAM v9; // rsi
  HWND v10; // rax
  HCURSOR v11; // r8
  int RemoteSystemRoot; // ebx
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  HCURSOR hCursor[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 Src; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v18[526]; // [rsp+262h] [rbp+162h] BYREF
  wchar_t lParam[264]; // [rsp+470h] [rbp+370h] BYREF

  if ( g_wszAuxMessageSource )
    StringCopyWorkerW(pszDest, 0x104u, a3, &g_wszAuxMessageSource, 0x103u);
  else
    _GetOpenSavedServer(hDlg, pszDest, (unsigned __int16)a3);
  DlgItem = GetDlgItem(hDlg, 101);
  if ( (unsigned int)SendMessageW(DlgItem, 0x146u, 0, 0) <= 1
    || (v5 = (const wchar_t *)SendMessageW(DlgItem, 0x150u, 0, 0), _wcsicmp(v5, pszDest)) )
  {
    _ResetOpenSavedLogTypeCombo(DlgItem);
    v13 = 0;
    Src = 0;
    memset_0(v18, 0, 0x206u);
    phkResult = 0;
    LoadStr(0x102u, lParam, 0x104u, (wchar_t *)L"(Unspecified)");
    v6 = -1;
    do
      ++v6;
    while ( pszDest[v6] );
    v7 = v6 + 1;
    v8 = (unsigned __int16 *)operator new[](saturated_mul(v6 + 1, 2u));
    v9 = (LPARAM)v8;
    if ( v8 )
    {
      StringCchCopyW(v8, v7, pszDest);
      SendMessageW(DlgItem, 0x143u, 0, (LPARAM)lParam);
      SendMessageW(DlgItem, 0x14Eu, 0, 0);
      SendMessageW(DlgItem, 0x151u, 0, v9);
      v10 = GetDlgItem(hDlg, 102);
      SetWindowTextW(v10, &String);
      if ( pszDest[0] )
      {
        CWaitCursor::CWaitCursor((CWaitCursor *)hCursor);
        RemoteSystemRoot = CSafeReg::Connect(&phkResult, pszDest, v11);
        if ( RemoteSystemRoot >= 0 )
        {
          RemoteSystemRoot = GetRemoteSystemRoot(phkResult, &Src, 0x104u);
          if ( RemoteSystemRoot >= 0 )
            RemoteSystemRoot = CSafeReg::Open(
                                 (CSafeReg *)&v13,
                                 phkResult,
                                 L"SYSTEM\\CurrentControlSet\\Services\\EventLog",
                                 8u);
        }
        SetCursor(hCursor[0]);
        if ( pszDest[0] )
        {
          if ( RemoteSystemRoot >= 0 )
            goto LABEL_16;
        }
      }
      pszDest[0] = 0;
      if ( (int)CSafeReg::Open(
                  (CSafeReg *)&v13,
                  HKEY_LOCAL_MACHINE,
                  L"SYSTEM\\CurrentControlSet\\Services\\EventLog",
                  8u) >= 0 )
LABEL_16:
        _AddRegKeysToLogTypeCombo(DlgItem, (const struct CSafeReg *)&v13, pszDest, &Src, 0);
    }
    CSafeReg::Close((CSafeReg *)&phkResult);
    if ( pszDest[0] )
    {
      CSafeReg::Close((CSafeReg *)&v13);
      if ( (int)CSafeReg::Open(
                  (CSafeReg *)&v13,
                  HKEY_LOCAL_MACHINE,
                  L"SYSTEM\\CurrentControlSet\\Services\\EventLog",
                  8u) >= 0 )
        _AddRegKeysToLogTypeCombo(DlgItem, (const struct CSafeReg *)&v13, (wchar_t *)&String, &String, 1);
    }
    CSafeReg::Close((CSafeReg *)&v13);
  }
}

```

## disassembly

```asm
0x18000839c  push    rbp
0x18000839e  push    rbx
0x18000839f  push    rsi
0x1800083a0  push    rdi
0x1800083a1  push    r14
0x1800083a3  push    r15
0x1800083a5  lea     rbp, [rsp-598h]
0x1800083ad  sub     rsp, 698h
0x1800083b4  mov     rax, cs:__security_cookie
0x1800083bb  xor     rax, rsp
0x1800083be  mov     [rbp+5C0h+var_40], rax
0x1800083c5  mov     rbx, rcx
0x1800083c8  xor     r15d, r15d
0x1800083cb  cmp     cs:?g_wszAuxMessageSource@@3PAGA, r15w; ushort near * g_wszAuxMessageSource
0x1800083d3  jz      short loc_1800083F6
0x1800083d5  mov     [rsp+6C0h+cchToCopy], 103h; cchToCopy
0x1800083de  lea     r9, ?g_wszAuxMessageSource@@3PAGA; pszSrc
0x1800083e5  mov     edx, 104h; cchDest
0x1800083ea  lea     rcx, [rsp+6C0h+pszDest]; pszDest
0x1800083ef  call    StringCopyWorkerW
0x1800083f4  jmp     short loc_180008400
0x1800083f6  lea     rdx, [rsp+6C0h+pszDest]; unsigned __int16 *
0x1800083fb  call    ?_GetOpenSavedServer@@YAXPEAUHWND__@@PEAGG@Z; _GetOpenSavedServer(HWND__ *,ushort *,ushort)
0x180008400  mov     edx, 65h ; 'e'; nIDDlgItem
0x180008405  mov     rcx, rbx; hDlg
0x180008408  call    cs:__imp_GetDlgItem
0x18000840e  mov     rdi, rax
0x180008411  xor     r9d, r9d; lParam
0x180008414  xor     r8d, r8d; wParam
0x180008417  mov     edx, 146h; Msg
0x18000841c  mov     rcx, rax; hWnd
0x18000841f  call    cs:__imp_SendMessageW
0x180008425  cmp     eax, 1
0x180008428  jbe     short loc_180008454
0x18000842a  xor     r9d, r9d; lParam
0x18000842d  xor     r8d, r8d; wParam
0x180008430  mov     edx, 150h; Msg
0x180008435  mov     rcx, rdi; hWnd
0x180008438  call    cs:__imp_SendMessageW
0x18000843e  lea     rdx, [rsp+6C0h+pszDest]; String2
0x180008443  mov     rcx, rax; String1
0x180008446  call    cs:__imp__wcsicmp
0x18000844c  test    eax, eax
0x18000844e  jz      loc_180008673
0x180008454  mov     rcx, rdi; hWnd
0x180008457  call    ?_ResetOpenSavedLogTypeCombo@@YAXPEAUHWND__@@@Z; _ResetOpenSavedLogTypeCombo(HWND__ *)
0x18000845c  mov     [rsp+6C0h+var_690], r15
0x180008461  mov     [rbp+5C0h+Src], r15w
0x180008469  xor     edx, edx; Val
0x18000846b  mov     r8d, 206h; Size
0x180008471  lea     rcx, [rbp+5C0h+var_45E]; void *
0x180008478  call    memset_0
0x18000847d  mov     [rsp+6C0h+phkResult], r15
0x180008482  lea     r9, aUnspecified; "(Unspecified)"
0x180008489  mov     r8d, 104h; SizeInWords
0x18000848f  lea     rdx, [rbp+5C0h+lParam]; Destination
0x180008496  lea     ecx, [r8-2]; uID
0x18000849a  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x18000849f  lea     rdx, [rsp+6C0h+pszDest]
0x1800084a4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800084a8  mov     rax, rcx
0x1800084ab  inc     rax
0x1800084ae  cmp     [rdx+rax*2], r15w
0x1800084b3  jnz     short loc_1800084AB
0x1800084b5  lea     r14, [rax+1]
0x1800084b9  mov     eax, 2
0x1800084be  mul     r14
0x1800084c1  cmovb   rax, rcx
0x1800084c5  mov     rcx, rax; unsigned __int64
0x1800084c8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800084cd  mov     rsi, rax
0x1800084d0  test    rax, rax
0x1800084d3  jz      loc_180008607
0x1800084d9  lea     r8, [rsp+6C0h+pszDest]; unsigned __int16 *
0x1800084de  mov     rdx, r14; unsigned __int64
0x1800084e1  mov     rcx, rax; unsigned __int16 *
0x1800084e4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800084e9  lea     r9, [rbp+5C0h+lParam]; lParam
0x1800084f0  xor     r8d, r8d; wParam
0x1800084f3  mov     edx, 143h; Msg
0x1800084f8  mov     rcx, rdi; hWnd
0x1800084fb  call    cs:__imp_SendMessageW
0x180008501  xor     r9d, r9d; lParam
0x180008504  xor     r8d, r8d; wParam
0x180008507  mov     edx, 14Eh; Msg
0x18000850c  mov     rcx, rdi; hWnd
0x18000850f  call    cs:__imp_SendMessageW
0x180008515  mov     r9, rsi; lParam
0x180008518  xor     r8d, r8d; wParam
0x18000851b  mov     edx, 151h; Msg
0x180008520  mov     rcx, rdi; hWnd
0x180008523  call    cs:__imp_SendMessageW
0x180008529  mov     edx, 66h ; 'f'; nIDDlgItem
0x18000852e  mov     rcx, rbx; hDlg
0x180008531  call    cs:__imp_GetDlgItem
0x180008537  mov     rcx, rax; hWnd
0x18000853a  lea     rdx, String; lpString
0x180008541  call    cs:__imp_SetWindowTextW
0x180008547  cmp     [rsp+6C0h+pszDest], r15w
0x18000854d  jz      short loc_1800085C0
0x18000854f  lea     rcx, [rsp+6C0h+hCursor]; this
0x180008554  call    ??0CWaitCursor@@QEAA@XZ; CWaitCursor::CWaitCursor(void)
0x180008559  lea     rdx, [rsp+6C0h+pszDest]; lpMachineName
0x18000855e  lea     rcx, [rsp+6C0h+phkResult]; phkResult
0x180008563  call    ?Connect@CSafeReg@@QEAAJPEBGPEAUHKEY__@@@Z; CSafeReg::Connect(ushort const *,HKEY__ *)
0x180008568  mov     ebx, eax
0x18000856a  test    eax, eax
0x18000856c  js      short loc_1800085A9
0x18000856e  mov     r8d, 104h; unsigned int
0x180008574  lea     rdx, [rbp+5C0h+Src]; unsigned __int16 *
0x18000857b  mov     rcx, [rsp+6C0h+phkResult]; HKEY
0x180008580  call    ?GetRemoteSystemRoot@@YAJPEAUHKEY__@@PEAGK@Z; GetRemoteSystemRoot(HKEY__ *,ushort *,ulong)
0x180008585  mov     ebx, eax
0x180008587  test    eax, eax
0x180008589  js      short loc_1800085A9
0x18000858b  mov     r9d, 8; unsigned int
0x180008591  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x180008598  mov     rdx, [rsp+6C0h+phkResult]; HKEY
0x18000859d  lea     rcx, [rsp+6C0h+var_690]; this
0x1800085a2  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x1800085a7  mov     ebx, eax
0x1800085a9  mov     rcx, [rsp+6C0h+hCursor]; hCursor
0x1800085ae  call    cs:__imp_SetCursor
0x1800085b4  cmp     [rsp+6C0h+pszDest], r15w
0x1800085ba  jz      short loc_1800085C0
0x1800085bc  test    ebx, ebx
0x1800085be  jns     short loc_1800085E8
0x1800085c0  mov     [rsp+6C0h+pszDest], r15w
0x1800085c6  mov     r9d, 8; unsigned int
0x1800085cc  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x1800085d3  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800085da  lea     rcx, [rsp+6C0h+var_690]; this
0x1800085df  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x1800085e4  test    eax, eax
0x1800085e6  js      short loc_180008607
0x1800085e8  mov     dword ptr [rsp+6C0h+cchToCopy], r15d; int
0x1800085ed  lea     r9, [rbp+5C0h+Src]; Src
0x1800085f4  lea     r8, [rsp+6C0h+pszDest]; Source
0x1800085f9  lea     rdx, [rsp+6C0h+var_690]; this
0x1800085fe  mov     rcx, rdi; hWnd
0x180008601  call    ?_AddRegKeysToLogTypeCombo@@YAXPEAUHWND__@@AEBVCSafeReg@@PEBG2H@Z; _AddRegKeysToLogTypeCombo(HWND__ *,CSafeReg const &,ushort const *,ushort const *,int)
0x180008606  nop
0x180008607  lea     rcx, [rsp+6C0h+phkResult]; this
0x18000860c  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180008611  cmp     [rsp+6C0h+pszDest], r15w
0x180008617  jz      short loc_180008669
0x180008619  lea     rcx, [rsp+6C0h+var_690]; this
0x18000861e  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180008623  mov     r9d, 8; unsigned int
0x180008629  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x180008630  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180008637  lea     rcx, [rsp+6C0h+var_690]; this
0x18000863c  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180008641  test    eax, eax
0x180008643  js      short loc_180008669
0x180008645  mov     dword ptr [rsp+6C0h+cchToCopy], 1; int
0x18000864d  lea     r9, String; Src
0x180008654  lea     r8, String; Source
0x18000865b  lea     rdx, [rsp+6C0h+var_690]; this
0x180008660  mov     rcx, rdi; hWnd
0x180008663  call    ?_AddRegKeysToLogTypeCombo@@YAXPEAUHWND__@@AEBVCSafeReg@@PEBG2H@Z; _AddRegKeysToLogTypeCombo(HWND__ *,CSafeReg const &,ushort const *,ushort const *,int)
0x180008668  nop
0x180008669  lea     rcx, [rsp+6C0h+var_690]; this
0x18000866e  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180008673  mov     rcx, [rbp+5C0h+var_40]
0x18000867a  xor     rcx, rsp; StackCookie
0x18000867d  call    __security_check_cookie
0x180008682  add     rsp, 698h
0x180008689  pop     r15
0x18000868b  pop     r14
0x18000868d  pop     rdi
0x18000868e  pop     rsi
0x18000868f  pop     rbx
0x180008690  pop     rbp
0x180008691  retn
```
