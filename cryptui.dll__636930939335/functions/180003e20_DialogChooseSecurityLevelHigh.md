# DialogChooseSecurityLevelHigh

- ea: `0x180003e20`
- end: `0x1800042e1`
- name: `DialogChooseSecurityLevelHigh`
- size: `1217`
- prototype: `__int64 __fastcall(HWND hDlg)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001f66`
- `0x1800038ac`
- `0x180003e20`
- `0x180005464`
- `0x18003e576`
- `0x18003e582`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004141`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004198`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004198`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004079`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004095`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004079`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004095`
- `USER32!MessageBoxW` at `0x1800040b2`
- `USER32!MessageBoxW` at `0x1800040b2`
- `USER32!SetWindowLongPtrW` at `0x1800041a9`
- `USER32!SetWindowLongPtrW` at `0x1800041a9`
- `USER32!EndDialog` at `0x180003e93`
- `USER32!EndDialog` at `0x180003f94`
- `USER32!EndDialog` at `0x180004188`
- `USER32!EndDialog` at `0x1800041c6`
- `USER32!EndDialog` at `0x180003e93`
- `USER32!EndDialog` at `0x180003f94`
- `USER32!EndDialog` at `0x180004188`
- `USER32!EndDialog` at `0x1800041c6`
- `USER32!SetWindowTextW` at `0x180004296`
- `USER32!SetWindowTextW` at `0x180004296`
- `USER32!GetWindowLongPtrW` at `0x180003eab`
- `USER32!GetWindowLongPtrW` at `0x180003f58`
- `USER32!GetWindowLongPtrW` at `0x180003eab`
- `USER32!GetWindowLongPtrW` at `0x180003f58`
- `USER32!SendDlgItemMessageW` at `0x18000422c`
- `USER32!SendDlgItemMessageW` at `0x180004245`
- `USER32!SendDlgItemMessageW` at `0x18000422c`
- `USER32!SendDlgItemMessageW` at `0x180004245`
- `USER32!SetFocus` at `0x1800042af`
- `USER32!SetFocus` at `0x1800042af`
- `USER32!GetDlgItem` at `0x180003ed2`
- `USER32!GetDlgItem` at `0x180003f13`
- `USER32!GetDlgItem` at `0x180003f31`
- `USER32!GetDlgItem` at `0x180003fa2`
- `USER32!GetDlgItem` at `0x180003ff5`
- `USER32!GetDlgItem` at `0x1800040c5`
- `USER32!GetDlgItem` at `0x1800041e8`
- `USER32!GetDlgItem` at `0x1800041fe`
- `USER32!GetDlgItem` at `0x180004253`
- `USER32!GetDlgItem` at `0x180004275`
- `USER32!GetDlgItem` at `0x18000428a`
- `USER32!GetDlgItem` at `0x180003ed2`
- `USER32!GetDlgItem` at `0x180003f13`
- `USER32!GetDlgItem` at `0x180003f31`
- `USER32!GetDlgItem` at `0x180003fa2`
- `USER32!GetDlgItem` at `0x180003ff5`
- `USER32!GetDlgItem` at `0x1800040c5`
- `USER32!GetDlgItem` at `0x1800041e8`
- `USER32!GetDlgItem` at `0x1800041fe`
- `USER32!GetDlgItem` at `0x180004253`
- `USER32!GetDlgItem` at `0x180004275`
- `USER32!GetDlgItem` at `0x18000428a`
- `USER32!EnableWindow` at `0x180003f1e`
- `USER32!EnableWindow` at `0x1800041f3`
- `USER32!EnableWindow` at `0x180004209`
- `USER32!EnableWindow` at `0x180004261`
- `USER32!EnableWindow` at `0x1800042a1`
- `USER32!EnableWindow` at `0x180003f1e`
- `USER32!EnableWindow` at `0x1800041f3`
- `USER32!EnableWindow` at `0x180004209`
- `USER32!EnableWindow` at `0x180004261`
- `USER32!EnableWindow` at `0x1800042a1`
- `USER32!GetWindowTextW` at `0x180003ee8`
- `USER32!GetWindowTextW` at `0x180003fb8`
- `USER32!GetWindowTextW` at `0x180004005`
- `USER32!GetWindowTextW` at `0x1800040d8`
- `USER32!GetWindowTextW` at `0x180003ee8`
- `USER32!GetWindowTextW` at `0x180003fb8`
- `USER32!GetWindowTextW` at `0x180004005`
- `USER32!GetWindowTextW` at `0x1800040d8`

## pseudocode

```c
__int64 __fastcall DialogChooseSecurityLevelHigh(HWND hDlg, int a2, unsigned __int16 a3, LONG_PTR a4)
{
  int v6; // edx
  LONG_PTR WindowLongPtrW; // rax
  HWND v9; // rax
  int WindowTextW; // eax
  WCHAR *v11; // rcx
  __int64 i; // rax
  HWND v13; // rax
  BOOL v14; // edx
  __int64 v15; // r12
  LONG_PTR v16; // r13
  __int64 v17; // rax
  HWND v18; // rax
  int v19; // eax
  __int64 v20; // rbx
  WCHAR *v21; // rax
  __int64 j; // rcx
  HWND v23; // rax
  int v24; // eax
  bool v25; // zf
  UCHAR *v26; // rax
  __int64 v27; // rbx
  WCHAR *v28; // rax
  UINT v29; // edx
  HWND v30; // rax
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // r12
  __int64 v34; // rbx
  WCHAR *v35; // rax
  int v36; // eax
  __int64 v37; // rbx
  WCHAR *v38; // rcx
  __int64 v39; // rdx
  HLOCAL v40; // rax
  WCHAR *v41; // rax
  HWND DlgItem; // rax
  HWND v43; // rax
  HWND v44; // r15
  HWND v45; // rax
  const WCHAR *v46; // rbx
  HWND v47; // rdi
  HWND v48; // rax
  HWND v49; // rcx
  size_t Size; // [rsp+30h] [rbp-D0h]
  UCHAR Buf1[64]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v52[256]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR String[256]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR Buffer[256]; // [rsp+480h] [rbp+380h] BYREF
  WCHAR Src[256]; // [rsp+680h] [rbp+580h] BYREF

  v6 = a2 - 272;
  if ( !v6 )
  {
    SetLastError(0);
    if ( SetWindowLongPtrW(hDlg, -21, a4) || !GetLastError() )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(a4 + 8) + 4LL) & 0x10) != 0 )
      {
        DlgItem = GetDlgItem(hDlg, 1032);
        EnableWindow(DlgItem, 0);
        v43 = GetDlgItem(hDlg, 1);
        EnableWindow(v43, 0);
      }
      SendDlgItemMessageW(hDlg, 1020, 0xC5u, 0x100u, 0);
      SendDlgItemMessageW(hDlg, 1021, 0xC5u, 0x100u, 0);
      v44 = GetDlgItem(hDlg, 1034);
      EnableWindow(v44, 1);
      if ( *(_QWORD *)(a4 + 16) )
      {
        v45 = GetDlgItem(hDlg, 1020);
        v46 = *(const WCHAR **)(a4 + 16);
        v47 = v45;
        v48 = GetDlgItem(hDlg, 1034);
        SetWindowTextW(v48, v46);
        EnableWindow(v47, 1);
        v49 = v47;
      }
      else
      {
        v49 = v44;
      }
      SetFocus(v49);
    }
    else
    {
      EndDialog(hDlg, 2);
    }
    return 0;
  }
  if ( v6 == 1 )
  {
    if ( a3 != 1 )
    {
      switch ( a3 )
      {
        case 2u:
LABEL_7:
          EndDialog(hDlg, a3);
          return 1;
        case 0x3FCu:
          WindowLongPtrW = GetWindowLongPtrW(hDlg, -21);
          if ( WindowLongPtrW && (*(_BYTE *)(*(_QWORD *)(WindowLongPtrW + 8) + 4LL) & 0x10) != 0 )
          {
            v9 = GetDlgItem(hDlg, 1020);
            WindowTextW = GetWindowTextW(v9, String, 256);
            if ( WindowTextW )
            {
              v11 = String;
              for ( i = 2LL * WindowTextW; i; --i )
              {
                *(_BYTE *)v11 = 0;
                v11 = (WCHAR *)((char *)v11 + 1);
              }
              v13 = GetDlgItem(hDlg, 1);
              v14 = 1;
            }
            else
            {
              v13 = GetDlgItem(hDlg, 1);
              v14 = 0;
            }
            EnableWindow(v13, v14);
          }
          break;
        case 0x408u:
          goto LABEL_7;
      }
      return 0;
    }
    v15 = 64;
    memset_0(Buf1, 0, sizeof(Buf1));
    v16 = GetWindowLongPtrW(hDlg, -21);
    if ( v16 )
    {
      v17 = 64;
      if ( *(_DWORD *)(v16 + 36) != 32782 )
        v17 = 20;
      Size = v17;
      if ( (*(_BYTE *)(*(_QWORD *)(v16 + 8) + 4LL) & 8) == 0 )
        EndDialog(hDlg, 1);
      v18 = GetDlgItem(hDlg, 1020);
      v19 = GetWindowTextW(v18, v52, 256);
      v20 = v19;
      ComputePasswordHash(*(_DWORD *)(v16 + 36), (UCHAR *)v52, 2 * v19, *(UCHAR **)(v16 + 24));
      v21 = v52;
      for ( j = 2 * v20; j; --j )
      {
        *(_BYTE *)v21 = 0;
        v21 = (WCHAR *)((char *)v21 + 1);
      }
      v23 = GetDlgItem(hDlg, 1021);
      v24 = GetWindowTextW(v23, v52, 256);
      ComputePasswordHash(*(_DWORD *)(v16 + 36), (UCHAR *)v52, 2 * v24, Buf1);
      v25 = memcmp_0(Buf1, *(const void **)(v16 + 24), Size) == 0;
      v26 = Buf1;
      do
      {
        *v26++ = 0;
        --v15;
      }
      while ( v15 );
      if ( !v25 )
      {
        v27 = 512;
        v28 = v52;
        do
        {
          *(_BYTE *)v28 = 0;
          v28 = (WCHAR *)((char *)v28 + 1);
          --v27;
        }
        while ( v27 );
        v29 = 3394;
        goto LABEL_29;
      }
      v30 = GetDlgItem(hDlg, 1034);
      v31 = GetWindowTextW(v30, Src, 256);
      v33 = v31;
      if ( !v31 )
      {
        v34 = 512;
        v35 = v52;
        do
        {
          *(_BYTE *)v35 = 0;
          v35 = (WCHAR *)((char *)v35 + 1);
          --v34;
        }
        while ( v34 );
        v29 = 3392;
        goto LABEL_29;
      }
      v36 = ValidatePasswordPolicy(v32, (__int64)v52);
      v37 = 512;
      v38 = v52;
      v39 = 512;
      do
      {
        *(_BYTE *)v38 = 0;
        v38 = (WCHAR *)((char *)v38 + 1);
        --v39;
      }
      while ( v39 );
      if ( v36 )
      {
        v29 = 3414;
LABEL_29:
        LoadStringW(g_hInstProtectUI, v29, String, 256);
        LoadStringW(g_hInstProtectUI, 0xD41u, Buffer, 256);
        MessageBoxW(hDlg, String, Buffer, 0x30u);
        return 0;
      }
      *(_DWORD *)(v16 + 44) = 1;
      v40 = LocalAlloc(0, 2LL * ((int)v33 + 1));
      *(_QWORD *)(v16 + 16) = v40;
      if ( v40 )
      {
        memcpy_0(v40, Src, 2 * v33);
        *(_WORD *)(2 * v33 + *(_QWORD *)(v16 + 16)) = 0;
        EndDialog(hDlg, 1);
        return 1;
      }
      v41 = v52;
      do
      {
        *(_BYTE *)v41 = 0;
        v41 = (WCHAR *)((char *)v41 + 1);
        --v37;
      }
      while ( v37 );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003e20  mov     [rsp-8+arg_8], rbx
0x180003e25  push    rbp
0x180003e26  push    rsi
0x180003e27  push    rdi
0x180003e28  push    r12
0x180003e2a  push    r13
0x180003e2c  push    r14
0x180003e2e  push    r15
0x180003e30  lea     rbp, [rsp-790h]
0x180003e38  sub     rsp, 890h
0x180003e3f  mov     rax, cs:__security_cookie
0x180003e46  xor     rax, rsp
0x180003e49  mov     [rbp+7C0h+var_40], rax
0x180003e50  mov     rbx, r9
0x180003e53  mov     r14, rcx
0x180003e56  sub     edx, 110h
0x180003e5c  jz      loc_180004196
0x180003e62  cmp     edx, 1
0x180003e65  jnz     loc_1800042B5
0x180003e6b  movzx   edx, r8w; nResult
0x180003e6f  mov     ecx, edx
0x180003e71  sub     ecx, 1
0x180003e74  jz      loc_180003F3B
0x180003e7a  sub     ecx, 1
0x180003e7d  jz      short loc_180003E90
0x180003e7f  sub     ecx, 3FAh
0x180003e85  jz      short loc_180003EA3
0x180003e87  cmp     ecx, 0Ch
0x180003e8a  jnz     loc_1800042B5
0x180003e90  mov     rcx, r14; hDlg
0x180003e93  call    cs:__imp_EndDialog
0x180003e99  mov     eax, 1
0x180003e9e  jmp     loc_1800042B7
0x180003ea3  mov     edx, 0FFFFFFEBh; nIndex
0x180003ea8  mov     rcx, r14; hWnd
0x180003eab  call    cs:__imp_GetWindowLongPtrW
0x180003eb1  xor     edi, edi
0x180003eb3  test    rax, rax
0x180003eb6  jz      loc_1800042B5
0x180003ebc  mov     rax, [rax+8]
0x180003ec0  test    byte ptr [rax+4], 10h
0x180003ec4  jz      loc_1800042B5
0x180003eca  mov     edx, 3FCh; nIDDlgItem
0x180003ecf  mov     rcx, r14; hDlg
0x180003ed2  call    cs:__imp_GetDlgItem
0x180003ed8  mov     r8d, 100h; nMaxCount
0x180003ede  lea     rdx, [rbp+7C0h+String]; lpString
0x180003ee5  mov     rcx, rax; hWnd
0x180003ee8  call    cs:__imp_GetWindowTextW
0x180003eee  test    eax, eax
0x180003ef0  jz      short loc_180003F29
0x180003ef2  cdqe
0x180003ef4  lea     esi, [rdi+1]
0x180003ef7  lea     rcx, [rbp+7C0h+String]
0x180003efe  add     rax, rax
0x180003f01  jz      short loc_180003F0E
0x180003f03  mov     [rcx], dil
0x180003f06  add     rcx, rsi
0x180003f09  sub     rax, rsi
0x180003f0c  jnz     short loc_180003F03
0x180003f0e  mov     edx, esi; nIDDlgItem
0x180003f10  mov     rcx, r14; hDlg
0x180003f13  call    cs:__imp_GetDlgItem
0x180003f19  mov     edx, esi; bEnable
0x180003f1b  mov     rcx, rax; hWnd
0x180003f1e  call    cs:__imp_EnableWindow
0x180003f24  jmp     loc_1800042B5
0x180003f29  mov     edx, 1; nIDDlgItem
0x180003f2e  mov     rcx, r14; hDlg
0x180003f31  call    cs:__imp_GetDlgItem
0x180003f37  xor     edx, edx
0x180003f39  jmp     short loc_180003F1B
0x180003f3b  mov     r12d, 40h ; '@'
0x180003f41  lea     rcx, [rsp+8C0h+Buf1]; void *
0x180003f46  mov     r8d, r12d; Size
0x180003f49  xor     edx, edx; Val
0x180003f4b  call    memset_0
0x180003f50  lea     edx, [r12-55h]; nIndex
0x180003f55  mov     rcx, r14; hWnd
0x180003f58  call    cs:__imp_GetWindowLongPtrW
0x180003f5e  xor     edi, edi
0x180003f60  mov     r13, rax
0x180003f63  test    rax, rax
0x180003f66  jz      loc_1800042B5
0x180003f6c  cmp     dword ptr [r13+24h], 800Eh
0x180003f74  lea     ecx, [rdi+14h]
0x180003f77  mov     eax, r12d
0x180003f7a  lea     esi, [rdi+1]
0x180003f7d  cmovnz  eax, ecx
0x180003f80  mov     rcx, [r13+8]
0x180003f84  mov     [rsp+8C0h+Size], rax
0x180003f89  test    byte ptr [rcx+4], 8
0x180003f8d  jnz     short loc_180003F9A
0x180003f8f  mov     edx, esi; nResult
0x180003f91  mov     rcx, r14; hDlg
0x180003f94  call    cs:__imp_EndDialog
0x180003f9a  mov     edx, 3FCh; nIDDlgItem
0x180003f9f  mov     rcx, r14; hDlg
0x180003fa2  call    cs:__imp_GetDlgItem
0x180003fa8  mov     r15d, 100h
0x180003fae  lea     rdx, [rbp+7C0h+var_840]; lpString
0x180003fb2  mov     rcx, rax; hWnd
0x180003fb5  mov     r8d, r15d; nMaxCount
0x180003fb8  call    cs:__imp_GetWindowTextW
0x180003fbe  mov     r9, [r13+18h]
0x180003fc2  lea     rdx, [rbp+7C0h+var_840]
0x180003fc6  mov     ecx, [r13+24h]
0x180003fca  movsxd  rbx, eax
0x180003fcd  lea     r8d, [rbx+rbx]
0x180003fd1  call    ComputePasswordHash
0x180003fd6  mov     rcx, rbx
0x180003fd9  lea     rax, [rbp+7C0h+var_840]
0x180003fdd  add     rcx, rcx
0x180003fe0  jz      short loc_180003FED
0x180003fe2  mov     [rax], dil
0x180003fe5  add     rax, rsi
0x180003fe8  sub     rcx, rsi
0x180003feb  jnz     short loc_180003FE2
0x180003fed  mov     edx, 3FDh; nIDDlgItem
0x180003ff2  mov     rcx, r14; hDlg
0x180003ff5  call    cs:__imp_GetDlgItem
0x180003ffb  mov     r8d, r15d; nMaxCount
0x180003ffe  lea     rdx, [rbp+7C0h+var_840]; lpString
0x180004002  mov     rcx, rax; hWnd
0x180004005  call    cs:__imp_GetWindowTextW
0x18000400b  mov     ecx, [r13+24h]
0x18000400f  lea     r9, [rsp+8C0h+Buf1]
0x180004014  lea     rdx, [rbp+7C0h+var_840]
0x180004018  lea     r8d, [rax+rax]
0x18000401c  call    ComputePasswordHash
0x180004021  mov     r8, [rsp+8C0h+Size]; Size
0x180004026  lea     rcx, [rsp+8C0h+Buf1]; Buf1
0x18000402b  mov     rdx, [r13+18h]; Buf2
0x18000402f  call    memcmp_0
0x180004034  test    eax, eax
0x180004036  mov     ecx, esi
0x180004038  lea     rax, [rsp+8C0h+Buf1]
0x18000403d  cmovnz  ecx, edi
0x180004040  mov     [rax], dil
0x180004043  add     rax, rsi
0x180004046  sub     r12, rsi
0x180004049  jnz     short loc_180004040
0x18000404b  test    ecx, ecx
0x18000404d  jnz     short loc_1800040BD
0x18000404f  mov     ebx, 200h
0x180004054  lea     rax, [rbp+7C0h+var_840]
0x180004058  mov     [rax], dil
0x18000405b  add     rax, rsi
0x18000405e  sub     rbx, rsi
0x180004061  jnz     short loc_180004058
0x180004063  mov     edx, 0D42h; uID
0x180004068  mov     rcx, cs:g_hInstProtectUI; hInstance
0x18000406f  lea     r8, [rbp+7C0h+String]; lpBuffer
0x180004076  mov     r9d, r15d; cchBufferMax
0x180004079  call    cs:__imp_LoadStringW
0x18000407f  mov     rcx, cs:g_hInstProtectUI; hInstance
0x180004086  lea     r8, [rbp+7C0h+Buffer]; lpBuffer
0x18000408d  mov     r9d, r15d; cchBufferMax
0x180004090  mov     edx, 0D41h; uID
0x180004095  call    cs:__imp_LoadStringW
0x18000409b  mov     r9d, 30h ; '0'; uType
0x1800040a1  lea     r8, [rbp+7C0h+Buffer]; lpCaption
0x1800040a8  lea     rdx, [rbp+7C0h+String]; lpText
0x1800040af  mov     rcx, r14; hWnd
0x1800040b2  call    cs:__imp_MessageBoxW
0x1800040b8  jmp     loc_1800042B5
0x1800040bd  mov     edx, 40Ah; nIDDlgItem
0x1800040c2  mov     rcx, r14; hDlg
0x1800040c5  call    cs:__imp_GetDlgItem
0x1800040cb  mov     r8d, r15d; nMaxCount
0x1800040ce  lea     rdx, [rbp+7C0h+Src]; lpString
0x1800040d5  mov     rcx, rax; hWnd
0x1800040d8  call    cs:__imp_GetWindowTextW
0x1800040de  movsxd  r12, eax
0x1800040e1  test    eax, eax
0x1800040e3  jnz     short loc_180004103
0x1800040e5  mov     ebx, 200h
0x1800040ea  lea     rax, [rbp+7C0h+var_840]
0x1800040ee  mov     [rax], dil
0x1800040f1  add     rax, rsi
0x1800040f4  sub     rbx, rsi
0x1800040f7  jnz     short loc_1800040EE
0x1800040f9  mov     edx, 0D40h
0x1800040fe  jmp     loc_180004068
0x180004103  lea     rdx, [rbp+7C0h+var_840]
0x180004107  call    ValidatePasswordPolicy
0x18000410c  mov     ebx, 200h
0x180004111  lea     rcx, [rbp+7C0h+var_840]
0x180004115  mov     edx, ebx
0x180004117  mov     [rcx], dil
0x18000411a  add     rcx, rsi
0x18000411d  sub     rdx, rsi
0x180004120  jnz     short loc_180004117
0x180004122  test    eax, eax
0x180004124  jz      short loc_180004130
0x180004126  mov     edx, 0D56h
0x18000412b  jmp     loc_180004068
0x180004130  lea     eax, [r12+1]
0x180004135  mov     [r13+2Ch], esi
0x180004139  movsxd  rdx, eax
0x18000413c  xor     ecx, ecx; uFlags
0x18000413e  add     rdx, rdx; uBytes
0x180004141  call    cs:__imp_LocalAlloc
0x180004147  mov     [r13+10h], rax
0x18000414b  mov     rcx, rax; void *
0x18000414e  test    rax, rax
0x180004151  jnz     short loc_180004167
0x180004153  lea     rax, [rbp+7C0h+var_840]
0x180004157  mov     [rax], dil
0x18000415a  add     rax, rsi
0x18000415d  sub     rbx, rsi
0x180004160  jnz     short loc_180004157
0x180004162  jmp     loc_1800042B5
0x180004167  lea     rbx, [r12+r12]
0x18000416b  mov     r8, rbx; Size
0x18000416e  lea     rdx, [rbp+7C0h+Src]; Src
0x180004175  call    memcpy_0
0x18000417a  mov     rax, [r13+10h]
0x18000417e  mov     rdx, rsi; nResult
0x180004181  mov     rcx, r14; hDlg
0x180004184  mov     [rbx+rax], di
0x180004188  call    cs:__imp_EndDialog
0x18000418e  mov     rax, rsi
0x180004191  jmp     loc_1800042B7
0x180004196  xor     ecx, ecx; dwErrCode
0x180004198  call    cs:__imp_SetLastError
0x18000419e  mov     r8, rbx; dwNewLong
0x1800041a1  mov     edx, 0FFFFFFEBh; nIndex
0x1800041a6  mov     rcx, r14; hWnd
0x1800041a9  call    cs:__imp_SetWindowLongPtrW
0x1800041af  xor     edi, edi
0x1800041b1  test    rax, rax
0x1800041b4  jnz     short loc_1800041D1
0x1800041b6  call    cs:__imp_GetLastError
0x1800041bc  test    eax, eax
0x1800041be  jz      short loc_1800041D1
0x1800041c0  lea     edx, [rdi+2]; nResult
0x1800041c3  mov     rcx, r14; hDlg
0x1800041c6  call    cs:__imp_EndDialog
0x1800041cc  jmp     loc_1800042B5
0x1800041d1  mov     rax, [rbx+8]
0x1800041d5  mov     esi, 1
0x1800041da  test    byte ptr [rax+4], 10h
0x1800041de  jz      short loc_18000420F
0x1800041e0  mov     edx, 408h; nIDDlgItem
0x1800041e5  mov     rcx, r14; hDlg
0x1800041e8  call    cs:__imp_GetDlgItem
0x1800041ee  mov     rcx, rax; hWnd
0x1800041f1  xor     edx, edx; bEnable
0x1800041f3  call    cs:__imp_EnableWindow
0x1800041f9  mov     edx, esi; nIDDlgItem
0x1800041fb  mov     rcx, r14; hDlg
0x1800041fe  call    cs:__imp_GetDlgItem
0x180004204  mov     rcx, rax; hWnd
0x180004207  xor     edx, edx; bEnable
0x180004209  call    cs:__imp_EnableWindow
0x18000420f  mov     r15d, 100h
0x180004215  mov     [rsp+8C0h+lParam], rdi; lParam
0x18000421a  mov     r9d, r15d; wParam
0x18000421d  mov     edx, 3FCh; nIDDlgItem
0x180004222  mov     rcx, r14; hDlg
0x180004225  lea     r12d, [r15-3Bh]
0x180004229  mov     r8d, r12d; Msg
0x18000422c  call    cs:__imp_SendDlgItemMessageW
0x180004232  mov     r9d, r15d; wParam
0x180004235  mov     [rsp+8C0h+lParam], rdi; lParam
0x18000423a  mov     r8d, r12d; Msg
0x18000423d  mov     edx, 3FDh; nIDDlgItem
0x180004242  mov     rcx, r14; hDlg
0x180004245  call    cs:__imp_SendDlgItemMessageW
0x18000424b  mov     edx, 40Ah; nIDDlgItem
0x180004250  mov     rcx, r14; hDlg
0x180004253  call    cs:__imp_GetDlgItem
0x180004259  mov     rcx, rax; hWnd
0x18000425c  mov     edx, esi; bEnable
0x18000425e  mov     r15, rax
0x180004261  call    cs:__imp_EnableWindow
0x180004267  cmp     [rbx+10h], rdi
0x18000426b  jz      short loc_1800042AC
0x18000426d  mov     edx, 3FCh; nIDDlgItem
0x180004272  mov     rcx, r14; hDlg
0x180004275  call    cs:__imp_GetDlgItem
0x18000427b  mov     rbx, [rbx+10h]
0x18000427f  mov     edx, 40Ah; nIDDlgItem
0x180004284  mov     rcx, r14; hDlg
0x180004287  mov     rdi, rax
0x18000428a  call    cs:__imp_GetDlgItem
0x180004290  mov     rcx, rax; hWnd
0x180004293  mov     rdx, rbx; lpString
0x180004296  call    cs:__imp_SetWindowTextW
0x18000429c  mov     edx, esi; bEnable
0x18000429e  mov     rcx, rdi; hWnd
0x1800042a1  call    cs:__imp_EnableWindow
0x1800042a7  mov     rcx, rdi
0x1800042aa  jmp     short loc_1800042AF
0x1800042ac  mov     rcx, r15; hWnd
0x1800042af  call    cs:__imp_SetFocus
0x1800042b5  xor     eax, eax
0x1800042b7  mov     rcx, [rbp+7C0h+var_40]
0x1800042be  xor     rcx, rsp; StackCookie
  ... truncated ...
```
