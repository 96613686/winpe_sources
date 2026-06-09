# CuUpdateCountryCodeLb

- ea: `0x18001242c`
- end: `0x1800126bf`
- name: `CuUpdateCountryCodeLb`
- size: `659`
- prototype: `int __fastcall(__int64, int)`
- caller_count: `4`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011be0`
- `0x180011c1c`
- `0x180011cec`
- `0x18001219c`

## callees

- `0x18000f380`
- `0x180011b78`
- `0x18001242c`
- `0x180045a58`
- `0x180045bb0`
- `0x180047e00`
- `0x180047ebc`
- `0x180048048`
- `0x180048b6c`
- `0x18004d110`

## import_xrefs

- `USER32!SendMessageW` at `0x18001248b`
- `USER32!SendMessageW` at `0x180012598`
- `USER32!SendMessageW` at `0x1800125e0`
- `USER32!SendMessageW` at `0x1800125fd`
- `USER32!SendMessageW` at `0x1800126ad`
- `USER32!SendMessageW` at `0x18001248b`
- `USER32!SendMessageW` at `0x180012598`
- `USER32!SendMessageW` at `0x1800125e0`
- `USER32!SendMessageW` at `0x1800125fd`
- `USER32!SendMessageW` at `0x1800126ad`
- `USER32!GetParent` at `0x180012649`
- `USER32!GetParent` at `0x180012649`
- `rtutils!TracePrintfExA` at `0x180012476`
- `rtutils!TracePrintfExA` at `0x180012638`
- `rtutils!TracePrintfExA` at `0x180012476`
- `rtutils!TracePrintfExA` at `0x180012638`

## string_xrefs

- `0x18001246a`: `CuUpdateCountryCodeLb(f=%d)`
- `0x18001262c`: `CuUpdateCountryCodeLb: StringCchPrintfEx failed. hr = 0x%x`

## pseudocode

```c
int __fastcall CuUpdateCountryCodeLb(__int64 a1, int a2)
{
  int v4; // eax
  LRESULT ItemDataPtr; // rax
  __int64 v6; // r8
  DWORD CountryInfo; // eax
  HGLOBAL v8; // r12
  DWORD v9; // ebp
  unsigned int v10; // r14d
  unsigned int v11; // r15d
  LPARAM v12; // rsi
  int v13; // eax
  HWND v14; // rcx
  HWND Parent; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-468h]
  unsigned int v18; // [rsp+40h] [rbp-448h] BYREF
  HGLOBAL hMem; // [rsp+48h] [rbp-440h] BYREF
  wchar_t pszDest[512]; // [rsp+50h] [rbp-438h] BYREF

  while ( 1 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "CuUpdateCountryCodeLb(f=%d)", a2);
    v4 = SendMessageW(*(HWND *)(a1 + 56), 0x147u, 0, 0);
    if ( v4 >= 0 )
    {
      ItemDataPtr = ComboBox_GetItemDataPtr(*(HWND *)(a1 + 56), v4);
      if ( (unsigned __int64)(ItemDataPtr - 2) <= 0xFFFFFFFFFFFFFFFCuLL
        && *(_DWORD *)(ItemDataPtr + 8) == *(_DWORD *)(a1 + 120)
        && (!a2 || *(_DWORD *)(a1 + 12)) )
      {
        return ItemDataPtr;
      }
    }
    CuClearCountryCodeLb(a1);
    hMem = 0;
    v18 = 0;
    if ( a2 )
      v6 = 0;
    else
      v6 = *(unsigned int *)(a1 + 120);
    CountryInfo = GetCountryInfo(&hMem, &v18, v6);
    v8 = hMem;
    v9 = CountryInfo;
    v10 = v18;
    if ( !CountryInfo )
    {
      if ( !a2 )
        ComboBox_AddItem(*(HWND *)(a1 + 56), (LPARAM)L"AAAAA", -1);
      v11 = 0;
      v12 = (LPARAM)v8;
      while ( v11 < v10 )
      {
        LODWORD(ItemDataPtr) = StringCchPrintfExW(pszDest, 0x200u, 0, 0, 0x100u, L"%s (%d)");
        if ( (int)ItemDataPtr < 0 )
        {
          if ( g_dwTraceId != -1 )
            LODWORD(ItemDataPtr) = TracePrintfExA(
                                     g_dwTraceId,
                                     0xCu,
                                     "CuUpdateCountryCodeLb: StringCchPrintfEx failed. hr = 0x%x",
                                     ItemDataPtr);
          return ItemDataPtr;
        }
        v13 = ComboBox_AddItem(*(HWND *)(a1 + 56), (LPARAM)pszDest, v12);
        if ( *(_DWORD *)(v12 + 8) == *(_DWORD *)(a1 + 120) )
          SendMessageW(*(HWND *)(a1 + 56), 0x14Eu, v13, 0);
        ++v11;
        v12 += 16LL;
      }
      if ( !a2 )
        ComboBox_AddItem(*(HWND *)(a1 + 56), (LPARAM)L"ZZZZZ", 1);
      ComboBox_AutoSizeDroppedWidth(*(HWND *)(a1 + 56));
      if ( !v10 )
      {
        v14 = *(HWND *)(a1 + 56);
        v9 = 740;
        goto LABEL_30;
      }
    }
    v14 = *(HWND *)(a1 + 56);
    if ( v9 )
    {
LABEL_30:
      Parent = GetParent(v14);
      LODWORD(ItemDataPtr) = ErrorDlgUtil(Parent, 0x147u, v9, dwFlags, 0x169u, 0xFAu);
      return ItemDataPtr;
    }
    LODWORD(ItemDataPtr) = SendMessageW(v14, 0x147u, 0, 0);
    if ( (int)ItemDataPtr >= 0 )
      goto LABEL_33;
    if ( (int)SendMessageW(*(HWND *)(a1 + 56), 0x146u, 0, 0) > 0 )
    {
      LODWORD(ItemDataPtr) = SendMessageW(*(HWND *)(a1 + 56), 0x14Eu, 0, 0);
LABEL_33:
      *(_QWORD *)a1 = v8;
      *(_DWORD *)(a1 + 8) = v10;
      *(_DWORD *)(a1 + 12) = a2;
      return ItemDataPtr;
    }
    FreeLocationInfo(v8);
    a2 = 1;
  }
}

```

## disassembly

```asm
0x18001242c  mov     [rsp+arg_10], rbx
0x180012431  mov     [rsp+arg_18], rbp
0x180012436  push    rsi
0x180012437  push    rdi
0x180012438  push    r12
0x18001243a  push    r14
0x18001243c  push    r15
0x18001243e  sub     rsp, 460h
0x180012445  mov     rax, cs:__security_cookie
0x18001244c  xor     rax, rsp
0x18001244f  mov     [rsp+488h+var_38], rax
0x180012457  mov     edi, edx
0x180012459  mov     rbx, rcx
0x18001245c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180012462  cmp     ecx, 0FFFFFFFFh
0x180012465  jz      short loc_18001247C
0x180012467  mov     r9d, edi
0x18001246a  lea     r8, aCuupdatecountr; "CuUpdateCountryCodeLb(f=%d)"
0x180012471  mov     edx, 0Ch; dwFlags
0x180012476  call    cs:__imp_TracePrintfExA
0x18001247c  mov     rcx, [rbx+38h]; hWnd
0x180012480  xor     r9d, r9d; lParam
0x180012483  xor     r8d, r8d; wParam
0x180012486  mov     edx, 147h; Msg
0x18001248b  call    cs:__imp_SendMessageW
0x180012491  test    eax, eax
0x180012493  js      short loc_1800124C4
0x180012495  mov     rcx, [rbx+38h]
0x180012499  mov     edx, eax
0x18001249b  call    ComboBox_GetItemDataPtr
0x1800124a0  lea     rcx, [rax-2]
0x1800124a4  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x1800124a8  ja      short loc_1800124C4
0x1800124aa  mov     ecx, [rbx+78h]
0x1800124ad  cmp     [rax+8], ecx
0x1800124b0  jnz     short loc_1800124C4
0x1800124b2  test    edi, edi
0x1800124b4  jz      loc_180012672
0x1800124ba  cmp     dword ptr [rbx+0Ch], 0
0x1800124be  jnz     loc_180012672
0x1800124c4  mov     rcx, rbx
0x1800124c7  call    CuClearCountryCodeLb
0x1800124cc  mov     [rsp+488h+hMem], 0
0x1800124d5  mov     [rsp+488h+var_448], 0
0x1800124dd  test    edi, edi
0x1800124df  jz      short loc_1800124E6
0x1800124e1  xor     r8d, r8d
0x1800124e4  jmp     short loc_1800124EA
0x1800124e6  mov     r8d, [rbx+78h]
0x1800124ea  lea     rdx, [rsp+488h+var_448]
0x1800124ef  lea     rcx, [rsp+488h+hMem]
0x1800124f4  call    GetCountryInfo
0x1800124f9  mov     r12, [rsp+488h+hMem]
0x1800124fe  mov     ebp, eax
0x180012500  mov     r14d, [rsp+488h+var_448]
0x180012505  test    eax, eax
0x180012507  jnz     loc_1800125CD
0x18001250d  test    edi, edi
0x18001250f  jnz     short loc_180012525
0x180012511  mov     rcx, [rbx+38h]; hWnd
0x180012515  lea     rdx, lParam; "AAAAA"
0x18001251c  or      r8, 0FFFFFFFFFFFFFFFFh; LPARAM
0x180012520  call    ComboBox_AddItem
0x180012525  xor     r15d, r15d
0x180012528  mov     rsi, r12
0x18001252b  cmp     r15d, r14d
0x18001252e  jnb     short loc_1800125A7
0x180012530  mov     eax, [rsi+0Ch]
0x180012533  lea     rcx, [rsp+488h+pszDest]; pszDest
0x180012538  mov     [rsp+488h+var_450], eax
0x18001253c  xor     r9d, r9d; pcchRemaining
0x18001253f  mov     rax, [rsi]
0x180012542  xor     r8d, r8d; ppszDestEnd
0x180012545  mov     qword ptr [rsp+488h+var_458], rax
0x18001254a  mov     edx, 200h; cchDest
0x18001254f  lea     rax, aSD; "%s (%d)"
0x180012556  mov     [rsp+488h+pszFormat], rax; pszFormat
0x18001255b  mov     [rsp+488h+dwFlags], 100h; dwFlags
0x180012563  call    StringCchPrintfExW
0x180012568  test    eax, eax
0x18001256a  js      loc_18001261E
0x180012570  mov     rcx, [rbx+38h]; hWnd
0x180012574  lea     rdx, [rsp+488h+pszDest]; lParam
0x180012579  mov     r8, rsi; LPARAM
0x18001257c  call    ComboBox_AddItem
0x180012581  mov     ecx, [rbx+78h]
0x180012584  cmp     [rsi+8], ecx
0x180012587  jnz     short loc_18001259E
0x180012589  mov     rcx, [rbx+38h]; hWnd
0x18001258d  xor     r9d, r9d; lParam
0x180012590  movsxd  r8, eax; wParam
0x180012593  mov     edx, 14Eh; Msg
0x180012598  call    cs:__imp_SendMessageW
0x18001259e  inc     r15d
0x1800125a1  add     rsi, 10h
0x1800125a5  jmp     short loc_18001252B
0x1800125a7  test    edi, edi
0x1800125a9  jnz     short loc_1800125BF
0x1800125ab  mov     rcx, [rbx+38h]; hWnd
0x1800125af  lea     r8d, [rdi+1]; LPARAM
0x1800125b3  lea     rdx, aZzzzz; "ZZZZZ"
0x1800125ba  call    ComboBox_AddItem
0x1800125bf  mov     rcx, [rbx+38h]; hWnd
0x1800125c3  call    ComboBox_AutoSizeDroppedWidth
0x1800125c8  test    r14d, r14d
0x1800125cb  jz      short loc_180012640
0x1800125cd  mov     rcx, [rbx+38h]; hWnd
0x1800125d1  test    ebp, ebp
0x1800125d3  jnz     short loc_180012649
0x1800125d5  xor     r9d, r9d; lParam
0x1800125d8  xor     r8d, r8d; wParam
0x1800125db  mov     edx, 147h; Msg
0x1800125e0  call    cs:__imp_SendMessageW
0x1800125e6  test    eax, eax
0x1800125e8  jns     loc_1800126B3
0x1800125ee  mov     rcx, [rbx+38h]; hWnd
0x1800125f2  xor     r9d, r9d; lParam
0x1800125f5  xor     r8d, r8d; wParam
0x1800125f8  mov     edx, 146h; Msg
0x1800125fd  call    cs:__imp_SendMessageW
0x180012603  test    eax, eax
0x180012605  jg      loc_18001269E
0x18001260b  mov     edx, r14d
0x18001260e  mov     rcx, r12; hMem
0x180012611  call    FreeLocationInfo
0x180012616  lea     edi, [rbp+1]
0x180012619  jmp     loc_18001245C
0x18001261e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180012624  cmp     ecx, 0FFFFFFFFh
0x180012627  jz      short loc_180012672
0x180012629  mov     r9d, eax
0x18001262c  lea     r8, aCuupdatecountr_0; "CuUpdateCountryCodeLb: StringCchPrintfE"...
0x180012633  mov     edx, 0Ch; dwFlags
0x180012638  call    cs:__imp_TracePrintfExA
0x18001263e  jmp     short loc_180012672
0x180012640  mov     rcx, [rbx+38h]; hWnd
0x180012644  mov     ebp, 2E4h
0x180012649  call    cs:__imp_GetParent
0x18001264f  mov     [rsp+488h+var_458], 0FAh; UINT
0x180012657  xor     r9d, r9d
0x18001265a  mov     rcx, rax; hWnd
0x18001265d  mov     dword ptr [rsp+488h+pszFormat], 169h; UINT
0x180012665  mov     r8d, ebp; dwMessageId
0x180012668  mov     edx, 147h; uID
0x18001266d  call    ErrorDlgUtil
0x180012672  mov     rcx, [rsp+488h+var_38]
0x18001267a  xor     rcx, rsp; StackCookie
0x18001267d  call    __security_check_cookie
0x180012682  lea     r11, [rsp+488h+var_28]
0x18001268a  mov     rbx, [r11+40h]
0x18001268e  mov     rbp, [r11+48h]
0x180012692  mov     rsp, r11
0x180012695  pop     r15
0x180012697  pop     r14
0x180012699  pop     r12
0x18001269b  pop     rdi
0x18001269c  pop     rsi
0x18001269d  retn
0x18001269e  mov     rcx, [rbx+38h]; hWnd
0x1800126a2  xor     r9d, r9d; lParam
0x1800126a5  xor     r8d, r8d; wParam
0x1800126a8  mov     edx, 14Eh; Msg
0x1800126ad  call    cs:__imp_SendMessageW
0x1800126b3  mov     [rbx], r12
0x1800126b6  mov     [rbx+8], r14d
0x1800126ba  mov     [rbx+0Ch], edi
0x1800126bd  jmp     short loc_180012672
```
