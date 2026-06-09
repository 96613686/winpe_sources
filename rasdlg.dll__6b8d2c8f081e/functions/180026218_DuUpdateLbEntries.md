# DuUpdateLbEntries

- ea: `0x180026218`
- end: `0x1800264e0`
- name: `DuUpdateLbEntries`
- size: `712`
- prototype: `__int64 __fastcall(__int64, const wchar_t *)`
- caller_count: `4`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800247ac`
- `0x180024ca4`
- `0x180025350`
- `0x180025b48`

## callees

- `0x1800245ec`
- `0x180026218`
- `0x18003bea0`
- `0x18003c860`
- `0x18003e000`
- `0x180047e00`
- `0x180047ebc`
- `0x18004807c`
- `0x1800480fc`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004d1d0`
- `0x18004e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180026405`
- `msvcrt!_wcsicmp` at `0x180026405`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800262ec`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002639b`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800262ec`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18002639b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263d5`
- `USER32!GetFocus` at `0x180026483`
- `USER32!GetFocus` at `0x180026483`
- `USER32!SendMessageW` at `0x18002643f`
- `USER32!SendMessageW` at `0x180026463`
- `USER32!SendMessageW` at `0x18002643f`
- `USER32!SendMessageW` at `0x180026463`
- `USER32!SetFocus` at `0x180026493`
- `USER32!SetFocus` at `0x180026493`
- `USER32!EnableWindow` at `0x18002649f`
- `USER32!EnableWindow` at `0x18002649f`
- `rtutils!TracePrintfExA` at `0x18002628b`
- `rtutils!TracePrintfExA` at `0x18002628b`

## string_xrefs

- `0x180026280`: `DuUpdateLbEntries`

## pseudocode

```c
__int64 __fastcall DuUpdateLbEntries(__int64 a1, const wchar_t *a2)
{
  _DWORD *v4; // r15
  _QWORD *v5; // rdx
  int v6; // eax
  _DWORD *v7; // rax
  unsigned int i; // edi
  unsigned int v9; // eax
  const wchar_t *v10; // r14
  _OWORD *v11; // rax
  LPARAM v12; // rsi
  int v13; // r14d
  unsigned int j; // edi
  const wchar_t *Psz; // rax
  const wchar_t *v16; // rsi
  int v17; // edi
  BOOL v18; // edx
  SIZE_T dwBytes; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+38h] [rbp-C8h]
  _DWORD v22[264]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Destination[4048]; // [rsp+460h] [rbp+360h] BYREF
  int v24; // [rsp+1430h] [rbp+1330h]

  v4 = 0;
  dwBytes = 0;
  memset_0(v22, 0, 0x418u);
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DuUpdateLbEntries");
  CleanupLbEntries(*(HWND *)(a1 + 32));
  v5 = *(_QWORD **)a1;
  v22[0] = 1048;
  LODWORD(dwBytes) = 1048;
  v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _DWORD *, SIZE_T *, char *))g_pRasEnumEntries)(
         0,
         *v5,
         v22,
         &dwBytes,
         (char *)&dwBytes + 4);
  if ( (v6 == 603 || !v6) && (unsigned int)dwBytes >= 0x418 )
  {
    v7 = GlobalAlloc(0x40u, (unsigned int)dwBytes);
    v4 = v7;
    if ( v7 )
    {
      *v7 = 1048;
      if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _DWORD *, SIZE_T *, char *))g_pRasEnumEntries)(
                            0,
                            **(_QWORD **)a1,
                            v7,
                            &dwBytes,
                            (char *)&dwBytes + 4) )
      {
        for ( i = 0; ; ++i )
        {
          v9 = HIDWORD(dwBytes);
          if ( i >= HIDWORD(dwBytes) )
            break;
          v21 = 6724;
          memset_0(Destination, 0, 0x1A44u);
          v10 = (const wchar_t *)&v4[262 * i];
          if ( !(unsigned int)RasGetEntryPropertiesWrapper(v10 + 262, v10 + 2, Destination) && (v24 & 0x8000000) == 0 )
          {
            v11 = GlobalAlloc(0x40u, 0x10u);
            v12 = (LPARAM)v11;
            if ( !v11 )
            {
              GetLastError();
              goto LABEL_28;
            }
            *v11 = 0;
            *(_QWORD *)v11 = StrDup(v10 + 262);
            ComboBox_AddItem(*(HWND *)(a1 + 32), (LPARAM)(v10 + 2), v12);
          }
        }
        v13 = -1;
        if ( a2 )
        {
          for ( j = 0; j < v9; ++j )
          {
            Psz = ComboBox_GetPsz(*(HWND *)(a1 + 32), j);
            v16 = Psz;
            if ( Psz )
            {
              if ( !_wcsicmp(Psz, a2) )
              {
                v13 = j;
                Free0(v16);
                break;
              }
              Free0(v16);
            }
            v9 = HIDWORD(dwBytes);
          }
        }
        v17 = 0;
        if ( v13 >= 0 )
          v17 = v13;
        if ( (int)SendMessageW(*(HWND *)(a1 + 32), 0x146u, 0, 0) > 0 )
          ComboBox_SetCurSelNotify(*(HWND *)(a1 + 32), v17);
      }
    }
  }
LABEL_28:
  if ( (int)SendMessageW(*(HWND *)(a1 + 32), 0x147u, 0, 0) < 0 || *(_DWORD *)(a1 + 296) && !*(_DWORD *)(a1 + 72) )
  {
    if ( GetFocus() == *(HWND *)(a1 + 24) )
      SetFocus(*(HWND *)(a1 + 40));
    v18 = 0;
  }
  else
  {
    v18 = 1;
  }
  EnableWindow(*(HWND *)(a1 + 24), v18);
  ComboBox_AutoSizeDroppedWidth(*(HWND *)(a1 + 32));
  return Free0(v4);
}

```

## disassembly

```asm
0x180026218  mov     [rsp-8+arg_10], rbx
0x18002621d  push    rbp
0x18002621e  push    rsi
0x18002621f  push    rdi
0x180026220  push    r12
0x180026222  push    r13
0x180026224  push    r14
0x180026226  push    r15
0x180026228  lea     rbp, [rsp-1DC0h]
0x180026230  mov     eax, 1EC0h
0x180026235  call    _alloca_probe
0x18002623a  sub     rsp, rax
0x18002623d  mov     rax, cs:__security_cookie
0x180026244  xor     rax, rsp
0x180026247  mov     [rbp+1DF0h+var_40], rax
0x18002624e  mov     r12, rdx
0x180026251  mov     rbx, rcx
0x180026254  xor     r15d, r15d
0x180026257  lea     rcx, [rsp+1EF0h+var_1EB0]; void *
0x18002625c  mov     edi, 418h
0x180026261  mov     dword ptr [rsp+1EF0h+dwBytes+4], r15d
0x180026266  mov     r8d, edi; Size
0x180026269  mov     dword ptr [rsp+1EF0h+dwBytes], r15d
0x18002626e  xor     edx, edx; Val
0x180026270  call    memset_0
0x180026275  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002627b  cmp     ecx, 0FFFFFFFFh
0x18002627e  jz      short loc_180026291
0x180026280  lea     r8, aDuupdatelbentr; "DuUpdateLbEntries"
0x180026287  lea     edx, [r15+0Ch]; dwFlags
0x18002628b  call    cs:__imp_TracePrintfExA
0x180026291  mov     rcx, [rbx+20h]; hWnd
0x180026295  call    CleanupLbEntries
0x18002629a  mov     rdx, [rbx]
0x18002629d  lea     rax, [rsp+1EF0h+dwBytes+4]
0x1800262a2  mov     [rsp+1EF0h+var_1EB0], edi
0x1800262a6  lea     r9, [rsp+1EF0h+dwBytes]
0x1800262ab  mov     dword ptr [rsp+1EF0h+dwBytes], edi
0x1800262af  lea     r8, [rsp+1EF0h+var_1EB0]
0x1800262b4  mov     [rsp+1EF0h+var_1ED0], rax
0x1800262b9  xor     ecx, ecx
0x1800262bb  mov     rdx, [rdx]
0x1800262be  mov     rax, cs:g_pRasEnumEntries
0x1800262c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262ca  cmp     eax, 25Bh
0x1800262cf  jz      short loc_1800262D9
0x1800262d1  test    eax, eax
0x1800262d3  jnz     loc_180026454
0x1800262d9  cmp     dword ptr [rsp+1EF0h+dwBytes], edi
0x1800262dd  jb      loc_180026454
0x1800262e3  mov     edx, dword ptr [rsp+1EF0h+dwBytes]; dwBytes
0x1800262e7  mov     ecx, 40h ; '@'; uFlags
0x1800262ec  call    cs:__imp_GlobalAlloc
0x1800262f2  mov     r15, rax
0x1800262f5  test    rax, rax
0x1800262f8  jz      loc_180026454
0x1800262fe  mov     [rax], edi
0x180026300  lea     r9, [rsp+1EF0h+dwBytes]
0x180026305  mov     rdx, [rbx]
0x180026308  lea     rax, [rsp+1EF0h+dwBytes+4]
0x18002630d  mov     [rsp+1EF0h+var_1ED0], rax
0x180026312  mov     r8, r15
0x180026315  mov     rax, cs:g_pRasEnumEntries
0x18002631c  xor     ecx, ecx
0x18002631e  mov     rdx, [rdx]
0x180026321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026326  test    eax, eax
0x180026328  jnz     loc_180026454
0x18002632e  xor     edi, edi
0x180026330  mov     eax, dword ptr [rsp+1EF0h+dwBytes+4]
0x180026334  cmp     edi, eax
0x180026336  jnb     loc_1800263DD
0x18002633c  xor     edx, edx; Val
0x18002633e  mov     [rsp+1EF0h+var_1EB8], 1A44h
0x180026346  mov     r8d, 1A44h; Size
0x18002634c  lea     rcx, [rbp+1DF0h+Destination]; void *
0x180026353  call    memset_0
0x180026358  mov     eax, edi
0x18002635a  lea     r9, [rsp+1EF0h+var_1EB8]
0x18002635f  imul    rcx, rax, 418h
0x180026366  lea     r8, [rbp+1DF0h+Destination]; Destination
0x18002636d  lea     r14, [rcx+r15]
0x180026371  lea     r13, [rcx+r15]
0x180026375  lea     rdx, [r14+4]; LPCWSTR
0x180026379  lea     rcx, [r13+20Ch]; LPCWSTR
0x180026380  call    RasGetEntryPropertiesWrapper
0x180026385  test    eax, eax
0x180026387  jnz     short loc_1800263CE
0x180026389  test    [rbp+1DF0h+var_AC0], 8000000h
0x180026393  jnz     short loc_1800263CE
0x180026395  lea     edx, [rax+10h]; dwBytes
0x180026398  lea     ecx, [rax+40h]; uFlags
0x18002639b  call    cs:__imp_GlobalAlloc
0x1800263a1  mov     rsi, rax
0x1800263a4  test    rax, rax
0x1800263a7  jz      short loc_1800263D5
0x1800263a9  xorps   xmm0, xmm0
0x1800263ac  lea     rcx, [r13+20Ch]; pszSrc
0x1800263b3  movups  xmmword ptr [rax], xmm0
0x1800263b6  call    StrDup
0x1800263bb  mov     [rsi], rax
0x1800263be  lea     rdx, [r14+4]; lParam
0x1800263c2  mov     rcx, [rbx+20h]; hWnd
0x1800263c6  mov     r8, rsi; LPARAM
0x1800263c9  call    ComboBox_AddItem
0x1800263ce  inc     edi
0x1800263d0  jmp     loc_180026330
0x1800263d5  call    cs:__imp_GetLastError
0x1800263db  jmp     short loc_180026454
0x1800263dd  or      r14d, 0FFFFFFFFh
0x1800263e1  test    r12, r12
0x1800263e4  jz      short loc_180026427
0x1800263e6  xor     edi, edi
0x1800263e8  cmp     edi, eax
0x1800263ea  jnb     short loc_180026427
0x1800263ec  mov     rcx, [rbx+20h]; hWnd
0x1800263f0  mov     edx, edi
0x1800263f2  call    ComboBox_GetPsz
0x1800263f7  mov     rsi, rax
0x1800263fa  test    rax, rax
0x1800263fd  jz      short loc_180026417
0x1800263ff  mov     rdx, r12; String2
0x180026402  mov     rcx, rax; String1
0x180026405  call    cs:__imp__wcsicmp
0x18002640b  mov     rcx, rsi
0x18002640e  test    eax, eax
0x180026410  jz      short loc_18002641F
0x180026412  call    Free0
0x180026417  mov     eax, dword ptr [rsp+1EF0h+dwBytes+4]
0x18002641b  inc     edi
0x18002641d  jmp     short loc_1800263E8
0x18002641f  mov     r14d, edi
0x180026422  call    Free0
0x180026427  mov     rcx, [rbx+20h]; hWnd
0x18002642b  xor     edi, edi
0x18002642d  test    r14d, r14d
0x180026430  mov     edx, 146h; Msg
0x180026435  cmovns  edi, r14d
0x180026439  xor     r9d, r9d; lParam
0x18002643c  xor     r8d, r8d; wParam
0x18002643f  call    cs:__imp_SendMessageW
0x180026445  test    eax, eax
0x180026447  jle     short loc_180026454
0x180026449  mov     rcx, [rbx+20h]; hWnd
0x18002644d  mov     edx, edi
0x18002644f  call    ComboBox_SetCurSelNotify
0x180026454  mov     rcx, [rbx+20h]; hWnd
0x180026458  xor     r9d, r9d; lParam
0x18002645b  xor     r8d, r8d; wParam
0x18002645e  mov     edx, 147h; Msg
0x180026463  call    cs:__imp_SendMessageW
0x180026469  test    eax, eax
0x18002646b  js      short loc_180026483
0x18002646d  cmp     dword ptr [rbx+128h], 0
0x180026474  jz      short loc_18002647C
0x180026476  cmp     dword ptr [rbx+48h], 0
0x18002647a  jz      short loc_180026483
0x18002647c  mov     edx, 1
0x180026481  jmp     short loc_18002649B
0x180026483  call    cs:__imp_GetFocus
0x180026489  cmp     rax, [rbx+18h]
0x18002648d  jnz     short loc_180026499
0x18002648f  mov     rcx, [rbx+28h]; hWnd
0x180026493  call    cs:__imp_SetFocus
0x180026499  xor     edx, edx; bEnable
0x18002649b  mov     rcx, [rbx+18h]; hWnd
0x18002649f  call    cs:__imp_EnableWindow
0x1800264a5  mov     rcx, [rbx+20h]; hWnd
0x1800264a9  call    ComboBox_AutoSizeDroppedWidth
0x1800264ae  mov     rcx, r15
0x1800264b1  call    Free0
0x1800264b6  mov     rcx, [rbp+1DF0h+var_40]
0x1800264bd  xor     rcx, rsp; StackCookie
0x1800264c0  call    __security_check_cookie
0x1800264c5  mov     rbx, [rsp+1EF0h+arg_10]
0x1800264cd  add     rsp, 1EC0h
0x1800264d4  pop     r15
0x1800264d6  pop     r14
0x1800264d8  pop     r13
0x1800264da  pop     r12
0x1800264dc  pop     rdi
0x1800264dd  pop     rsi
0x1800264de  pop     rbp
0x1800264df  retn
```
