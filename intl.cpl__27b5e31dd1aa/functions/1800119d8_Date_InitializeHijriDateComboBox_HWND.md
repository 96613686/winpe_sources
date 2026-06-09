# Date_InitializeHijriDateComboBox(HWND__ *)

- ea: `0x1800119d8`
- end: `0x180011c5a`
- name: `?Date_InitializeHijriDateComboBox@@YAXPEAUHWND__@@@Z`
- size: `642`
- prototype: `void __fastcall(HWND hDlg)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010790`
- `0x180010c48`
- `0x1800117fc`
- `0x180012274`

## callees

- `0x18000626c`
- `0x1800119d8`
- `0x180027260`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011b49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011b49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011a7c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011a7c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011ab7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011ab7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011c29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011c29`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180011c1e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180011c1e`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180011ba2`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180011ba2`
- `KERNEL32!lstrcmpW` at `0x180011be7`
- `KERNEL32!lstrcmpW` at `0x180011be7`
- `USER32!GetDlgItem` at `0x180011a12`
- `USER32!GetDlgItem` at `0x180011a12`
- `USER32!SendMessageW` at `0x180011a55`
- `USER32!SendMessageW` at `0x180011bbb`
- `USER32!SendMessageW` at `0x180011bd7`
- `USER32!SendMessageW` at `0x180011bff`
- `USER32!SendMessageW` at `0x180011a55`
- `USER32!SendMessageW` at `0x180011bbb`
- `USER32!SendMessageW` at `0x180011bd7`
- `USER32!SendMessageW` at `0x180011bff`

## string_xrefs

- `0x180011b35`: `AddHijriDateTemp`
- `0x180011c17`: `AddHijriDateTemp`

## pseudocode

```c
void __fastcall Date_InitializeHijriDateComboBox(HWND hDlg)
{
  HWND DlgItem; // r14
  unsigned __int16 *v3; // rsi
  LPARAM i; // rbx
  __int64 v5; // rax
  const BYTE *v6; // rcx
  int v7; // eax
  WPARAM v8; // rdi
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v12; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v13[128]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR DateStr[128]; // [rsp+170h] [rbp+70h] BYREF

  hKey = 0;
  *(_OWORD *)Data = 0;
  DlgItem = GetDlgItem(hDlg, 1105);
  cbData = 0;
  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  SendMessageW(DlgItem, 0x14Bu, 0, 0);
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\International", 0, 0x2001Fu, &hKey) )
  {
    cbData = 32;
    if ( RegQueryValueExW(hKey, L"AddHijriDate", 0, 0, Data, &cbData) )
      *(_WORD *)Data = 0;
    v3 = 0;
    if ( !(unsigned int)NLSize_Style(hDlg, 1107, g_szNLS_LongDate, 0x80u, 0x20u) )
    {
      StringCchCopyW(v13, 0x80u, g_szNLS_LongDate);
      v3 = v13;
    }
    for ( i = 0; i != 5; ++i )
    {
      v5 = -1;
      v6 = (const BYTE *)off_18002D5C0[i];
      do
        ++v5;
      while ( *(_WORD *)&v6[2 * v5] );
      if ( !RegSetValueExW(hKey, L"AddHijriDateTemp", 0, 1u, v6, 2 * v5 + 2) )
      {
        if ( GetDateFormatEx(
               *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
               (v3 == 0 ? 2 : 0) | 0x40000040,
               0,
               v3,
               DateStr,
               128,
               L"6") )
        {
          v7 = SendMessageW(DlgItem, 0x143u, 0, (LPARAM)DateStr);
          if ( v7 != -1 )
          {
            v8 = v7;
            SendMessageW(DlgItem, 0x151u, v7, i);
            if ( !lstrcmpW((LPCWSTR)Data, off_18002D5C0[i]) )
              SendMessageW(DlgItem, 0x14Eu, v8, 0);
          }
        }
      }
    }
    RegDeleteValueW(hKey, L"AddHijriDateTemp");
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x1800119d8  mov     [rsp-8+arg_8], rbx
0x1800119dd  mov     [rsp-8+arg_10], rsi
0x1800119e2  push    rbp
0x1800119e3  push    rdi
0x1800119e4  push    r13
0x1800119e6  push    r14
0x1800119e8  push    r15
0x1800119ea  lea     rbp, [rsp-180h]
0x1800119f2  sub     rsp, 280h
0x1800119f9  mov     rax, cs:__security_cookie
0x180011a00  xor     rax, rsp
0x180011a03  mov     [rbp+1A0h+var_30], rax
0x180011a0a  mov     edx, 451h; nIDDlgItem
0x180011a0f  mov     rbx, rcx
0x180011a12  call    cs:__imp_GetDlgItem
0x180011a18  xorps   xmm0, xmm0
0x180011a1b  lea     rcx, [rsp+2A0h+var_230]; void *
0x180011a20  xor     r15d, r15d
0x180011a23  xor     edx, edx; Val
0x180011a25  mov     r8d, 100h; Size
0x180011a2b  mov     [rsp+2A0h+hKey], r15
0x180011a30  movups  xmmword ptr [rsp+2A0h+Data], xmm0
0x180011a35  mov     r14, rax
0x180011a38  mov     [rsp+2A0h+cbData], r15d
0x180011a3d  movups  [rsp+2A0h+var_240], xmm0
0x180011a42  call    memset_0
0x180011a47  xor     r9d, r9d; lParam
0x180011a4a  xor     r8d, r8d; wParam
0x180011a4d  mov     edx, 14Bh; Msg
0x180011a52  mov     rcx, r14; hWnd
0x180011a55  call    cs:__imp_SendMessageW
0x180011a5b  lea     rax, [rsp+2A0h+hKey]
0x180011a60  mov     r9d, 2001Fh; samDesired
0x180011a66  xor     r8d, r8d; ulOptions
0x180011a69  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180011a6e  lea     rdx, aControlPanelIn_2; "Control Panel\\International"
0x180011a75  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180011a7c  call    cs:__imp_RegOpenKeyExW
0x180011a82  test    eax, eax
0x180011a84  jnz     loc_180011C2F
0x180011a8a  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180011a8f  lea     edi, [rax+20h]
0x180011a92  lea     rax, [rsp+2A0h+cbData]
0x180011a97  mov     [rsp+2A0h+cbData], edi
0x180011a9b  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x180011aa0  lea     rdx, aAddhijridate_0; "AddHijriDate"
0x180011aa7  lea     rax, [rsp+2A0h+Data]
0x180011aac  xor     r9d, r9d; lpType
0x180011aaf  xor     r8d, r8d; lpReserved
0x180011ab2  mov     [rsp+2A0h+phkResult], rax; lpData
0x180011ab7  call    cs:__imp_RegQueryValueExW
0x180011abd  test    eax, eax
0x180011abf  jz      short loc_180011AC7
0x180011ac1  mov     word ptr [rsp+2A0h+Data], r15w
0x180011ac7  mov     r9d, 80h; unsigned int
0x180011acd  mov     dword ptr [rsp+2A0h+phkResult], edi; unsigned int
0x180011ad1  lea     r8, ?g_szNLS_LongDate@@3PAGA; unsigned __int16 *
0x180011ad8  mov     edx, 453h; nIDDlgItem
0x180011add  mov     rcx, rbx; hDlg
0x180011ae0  mov     rsi, r15
0x180011ae3  call    ?NLSize_Style@@YAHPEAUHWND__@@HPEAGKK@Z; NLSize_Style(HWND__ *,int,ushort *,ulong,ulong)
0x180011ae8  test    eax, eax
0x180011aea  jnz     short loc_180011B07
0x180011aec  lea     r8, ?g_szNLS_LongDate@@3PAGA; unsigned __int16 *
0x180011af3  mov     edx, 80h; unsigned __int64
0x180011af8  lea     rcx, [rsp+2A0h+var_230]; unsigned __int16 *
0x180011afd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011b02  lea     rsi, [rsp+2A0h+var_230]
0x180011b07  mov     rbx, r15
0x180011b0a  lea     r13, off_18002D5C0; "AddHijriDate-2"
0x180011b11  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011b15  mov     rcx, [r13+rbx*8+0]
0x180011b1a  inc     rax
0x180011b1d  cmp     [rcx+rax*2], r15w
0x180011b22  jnz     short loc_180011B1A
0x180011b24  lea     eax, ds:2[rax*2]
0x180011b2b  mov     r9d, 1; dwType
0x180011b31  mov     dword ptr [rsp+2A0h+lpcbData], eax; cbData
0x180011b35  lea     rdx, aAddhijridatete; "AddHijriDateTemp"
0x180011b3c  mov     [rsp+2A0h+phkResult], rcx; lpData
0x180011b41  xor     r8d, r8d; Reserved
0x180011b44  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180011b49  call    cs:__imp_RegSetValueExW
0x180011b4f  test    eax, eax
0x180011b51  jnz     loc_180011C05
0x180011b57  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180011b5d  mov     rax, rsi
0x180011b60  neg     rax
0x180011b63  mov     r9, rsi; lpFormat
0x180011b66  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180011b6d  sbb     edx, edx
0x180011b6f  xor     r8d, r8d; lpDate
0x180011b72  not     edx
0x180011b74  and     edx, 2
0x180011b77  mov     rcx, [rax+rcx*8]
0x180011b7b  or      edx, 40000040h; dwFlags
0x180011b81  lea     rax, Calendar; "6"
0x180011b88  mov     [rsp+2A0h+lpCalendar], rax; lpCalendar
0x180011b8d  lea     rax, [rbp+1A0h+DateStr]
0x180011b91  mov     dword ptr [rsp+2A0h+lpcbData], 80h; cchDate
0x180011b99  mov     rcx, [rcx+8]; lpLocaleName
0x180011b9d  mov     [rsp+2A0h+phkResult], rax; lpDateStr
0x180011ba2  call    cs:__imp_GetDateFormatEx
0x180011ba8  test    eax, eax
0x180011baa  jz      short loc_180011C05
0x180011bac  lea     r9, [rbp+1A0h+DateStr]; lParam
0x180011bb0  xor     r8d, r8d; wParam
0x180011bb3  mov     edx, 143h; Msg
0x180011bb8  mov     rcx, r14; hWnd
0x180011bbb  call    cs:__imp_SendMessageW
0x180011bc1  cmp     eax, 0FFFFFFFFh
0x180011bc4  jz      short loc_180011C05
0x180011bc6  movsxd  rdi, eax
0x180011bc9  mov     r9, rbx; lParam
0x180011bcc  mov     r8, rdi; wParam
0x180011bcf  mov     edx, 151h; Msg
0x180011bd4  mov     rcx, r14; hWnd
0x180011bd7  call    cs:__imp_SendMessageW
0x180011bdd  mov     rdx, [r13+rbx*8+0]; lpString2
0x180011be2  lea     rcx, [rsp+2A0h+Data]; lpString1
0x180011be7  call    cs:__imp_lstrcmpW
0x180011bed  test    eax, eax
0x180011bef  jnz     short loc_180011C05
0x180011bf1  xor     r9d, r9d; lParam
0x180011bf4  mov     r8, rdi; wParam
0x180011bf7  mov     edx, 14Eh; Msg
0x180011bfc  mov     rcx, r14; hWnd
0x180011bff  call    cs:__imp_SendMessageW
0x180011c05  inc     rbx
0x180011c08  cmp     rbx, 5
0x180011c0c  jnz     loc_180011B0A
0x180011c12  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180011c17  lea     rdx, aAddhijridatete; "AddHijriDateTemp"
0x180011c1e  call    cs:__imp_RegDeleteValueW
0x180011c24  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180011c29  call    cs:__imp_RegCloseKey
0x180011c2f  mov     rcx, [rbp+1A0h+var_30]
0x180011c36  xor     rcx, rsp; StackCookie
0x180011c39  call    __security_check_cookie
0x180011c3e  lea     r11, [rsp+2A0h+var_20]
0x180011c46  mov     rbx, [r11+38h]
0x180011c4a  mov     rsi, [r11+40h]
0x180011c4e  mov     rsp, r11
0x180011c51  pop     r15
0x180011c53  pop     r14
0x180011c55  pop     r13
0x180011c57  pop     rdi
0x180011c58  pop     rbp
0x180011c59  retn
```
