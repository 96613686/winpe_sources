# DuNewEntry

- ea: `0x180025b48`
- end: `0x180025e40`
- name: `DuNewEntry`
- size: `760`
- prototype: `unsigned int __fastcall(LPWSTR **)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180024664`
- `0x180025350`

## callees

- `0x180014b40`
- `0x180025b48`
- `0x180026218`
- `0x18003b40c`
- `0x18004797c`
- `0x180048b6c`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `RASAPI32!ReadPhonebookFile` at `0x180025d35`
- `RASAPI32!ReadPhonebookFile` at `0x180025d35`
- `RASAPI32!ClosePhonebookFile` at `0x180025d0f`
- `RASAPI32!ClosePhonebookFile` at `0x180025d0f`
- `USER32!GetWindowRect` at `0x180025bff`
- `USER32!GetWindowRect` at `0x180025bff`
- `USER32!EndDialog` at `0x180025d6c`
- `USER32!EndDialog` at `0x180025d6c`
- `USER32!SetFocus` at `0x180025df8`
- `USER32!SetFocus` at `0x180025df8`
- `rtutils!TracePrintfExA` at `0x180025bc5`
- `rtutils!TracePrintfExA` at `0x180025c89`
- `rtutils!TracePrintfExA` at `0x180025cba`
- `rtutils!TracePrintfExA` at `0x180025d9c`
- `rtutils!TracePrintfExA` at `0x180025dd5`
- `rtutils!TracePrintfExA` at `0x180025e0f`
- `rtutils!TracePrintfExA` at `0x180025bc5`
- `rtutils!TracePrintfExA` at `0x180025c89`
- `rtutils!TracePrintfExA` at `0x180025cba`
- `rtutils!TracePrintfExA` at `0x180025d9c`
- `rtutils!TracePrintfExA` at `0x180025dd5`
- `rtutils!TracePrintfExA` at `0x180025e0f`

## pseudocode

```c
unsigned int __fastcall DuNewEntry(LPWSTR **a1)
{
  bool v2; // zf
  int v3; // eax
  unsigned int result; // eax
  DWORD v5; // ecx
  unsigned int v6; // edi
  DWORD PhonebookFile; // eax
  void (__fastcall *v8)(_QWORD, __int64, WCHAR *); // rdi
  _BYTE v9[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v10; // [rsp+44h] [rbp-BCh]
  _QWORD **v11; // [rsp+48h] [rbp-B8h]
  _QWORD **v12; // [rsp+50h] [rbp-B0h]
  int v13; // [rsp+58h] [rbp-A8h]
  LPWSTR *v14; // [rsp+60h] [rbp-A0h]
  struct tagRASENTRYDLGW Info; // [rsp+A0h] [rbp-60h] BYREF
  struct tagRECT Rect; // [rsp+2D0h] [rbp+1D0h] BYREF

  memset_0(&Info, 0, sizeof(Info));
  v10 = 0;
  memset_0(v9, 0, 0x54u);
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DuNewEntry");
  memset_0(&Info.xDlg, 0, 0x220u);
  Info.hwndOwner = (HWND)a1[1];
  Rect = 0;
  Info.dwSize = 560;
  Info.dwFlags = 2;
  GetWindowRect(Info.hwndOwner, &Rect);
  ++Info.dwFlags;
  Info.xDlg = Rect.left + 12;
  Info.yDlg = Rect.top + 25;
  memset_0(v9, 0, 0x58u);
  v2 = *((_DWORD *)a1 + 74) == 0;
  v14 = a1[36];
  v3 = v13;
  if ( !v2 )
    v3 = 64;
  v11 = a1 + 29;
  v13 = v3;
  Info.reserved = (ULONG_PTR)v9;
  v12 = a1 + 6;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "RasEntryDlg");
  result = RasEntryDlgW(**a1, 0, &Info);
  v5 = g_dwTraceId;
  v6 = result;
  if ( g_dwTraceId != -1 )
  {
    result = TracePrintfExA(g_dwTraceId, 0xCu, "RasEntryDlg=%d", result);
    v5 = g_dwTraceId;
  }
  if ( !a1[36] || a1[41] )
  {
    if ( v6 )
    {
      if ( v5 != -1 )
        TracePrintfW1("OK pressed, e=\"%s\"", Info.szEntry);
      ClosePhonebookFile(a1 + 29);
      PhonebookFile = ReadPhonebookFile(**a1, a1 + 6, 0, *((_DWORD *)a1 + 74) != 0 ? 0x20 : 0);
      if ( PhonebookFile )
      {
        ErrorDlgUtil((HWND)a1[1], 0x141u, PhonebookFile, (_DWORD)a1 + 232, 0x169u, 0xFAu);
        return EndDialog((HWND)a1[1], 1);
      }
      else
      {
        v8 = (void (__fastcall *)(_QWORD, __int64, WCHAR *))*((_QWORD *)(*a1)[2] + 4);
        if ( v8 )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "Callback(AddEntry)");
          v8(*((_QWORD *)(*a1)[2] + 3), 1, Info.szEntry);
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "Callback(AddEntry) done");
        }
        DuUpdateLbEntries(a1, Info.szEntry);
        Button_MakeDefault((HWND)a1[1], (HWND)a1[5]);
        return (unsigned int)SetFocus((HWND)a1[4]);
      }
    }
    else if ( v5 != -1 )
    {
      return TracePrintfExA(v5, 0xCu, "Cancel pressed or error");
    }
  }
  else if ( v5 != -1 )
  {
    return TracePrintfExA(v5, 0xCu, "Taking shortcut to exit");
  }
  return result;
}

```

## disassembly

```asm
0x180025b48  mov     [rsp-8+arg_8], rbx
0x180025b4d  mov     [rsp-8+arg_10], rsi
0x180025b52  push    rbp
0x180025b53  push    rdi
0x180025b54  push    r12
0x180025b56  push    r14
0x180025b58  push    r15
0x180025b5a  lea     rbp, [rsp-1F0h]
0x180025b62  sub     rsp, 2F0h
0x180025b69  mov     rax, cs:__security_cookie
0x180025b70  xor     rax, rsp
0x180025b73  mov     [rbp+210h+var_30], rax
0x180025b7a  mov     rbx, rcx
0x180025b7d  mov     edi, 230h
0x180025b82  mov     r8d, edi; Size
0x180025b85  lea     rcx, [rbp+210h+Info]; void *
0x180025b89  xor     edx, edx; Val
0x180025b8b  call    memset_0
0x180025b90  xor     eax, eax
0x180025b92  lea     rcx, [rsp+310h+var_2D0]; void *
0x180025b97  xor     edx, edx; Val
0x180025b99  mov     [rsp+310h+var_2CC], eax
0x180025b9d  lea     r8d, [rax+54h]; Size
0x180025ba1  call    memset_0
0x180025ba6  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180025bac  or      r15d, 0FFFFFFFFh
0x180025bb0  mov     r12d, 0Ch
0x180025bb6  cmp     ecx, r15d
0x180025bb9  jz      short loc_180025BCB
0x180025bbb  lea     r8, aDunewentry; "DuNewEntry"
0x180025bc2  mov     edx, r12d; dwFlags
0x180025bc5  call    cs:__imp_TracePrintfExA
0x180025bcb  xor     edx, edx; Val
0x180025bcd  lea     rcx, [rbp+210h+Info.xDlg]; void *
0x180025bd1  mov     r8d, 220h; Size
0x180025bd7  call    memset_0
0x180025bdc  mov     rcx, [rbx+8]; hWnd
0x180025be0  lea     rdx, [rbp+210h+Rect]; lpRect
0x180025be7  xorps   xmm0, xmm0
0x180025bea  mov     [rbp+210h+Info.hwndOwner], rcx
0x180025bee  movups  xmmword ptr [rbp+210h+Rect.left], xmm0
0x180025bf5  mov     [rbp+210h+Info.dwSize], edi
0x180025bf8  mov     [rbp+210h+Info.dwFlags], 2
0x180025bff  call    cs:__imp_GetWindowRect
0x180025c05  mov     eax, [rbp+210h+Rect.left]
0x180025c0b  lea     rcx, [rsp+310h+var_2D0]; void *
0x180025c10  inc     [rbp+210h+Info.dwFlags]
0x180025c13  add     eax, r12d
0x180025c16  mov     [rbp+210h+Info.xDlg], eax
0x180025c19  xor     edx, edx; Val
0x180025c1b  mov     eax, [rbp+210h+Rect.top]
0x180025c21  add     eax, 19h
0x180025c24  mov     [rbp+210h+Info.yDlg], eax
0x180025c27  lea     r8d, [rdx+58h]; Size
0x180025c2b  call    memset_0
0x180025c30  mov     rax, [rbx+120h]
0x180025c37  lea     rsi, [rbx+0E8h]
0x180025c3e  cmp     dword ptr [rbx+128h], 0
0x180025c45  lea     r14, [rbx+30h]
0x180025c49  mov     [rsp+310h+var_2B0], rax
0x180025c4e  mov     ecx, 40h ; '@'
0x180025c53  mov     eax, [rsp+310h+var_2B8]
0x180025c57  cmovnz  eax, ecx
0x180025c5a  mov     [rsp+310h+var_2C8], rsi
0x180025c5f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180025c65  mov     [rsp+310h+var_2B8], eax
0x180025c69  lea     rax, [rsp+310h+var_2D0]
0x180025c6e  mov     [rbp+210h+Info.reserved], rax
0x180025c75  mov     [rsp+310h+var_2C0], r14
0x180025c7a  cmp     ecx, r15d
0x180025c7d  jz      short loc_180025C8F
0x180025c7f  lea     r8, aRasentrydlg; "RasEntryDlg"
0x180025c86  mov     edx, r12d; dwFlags
0x180025c89  call    cs:__imp_TracePrintfExA
0x180025c8f  mov     rcx, [rbx]
0x180025c92  lea     r8, [rbp+210h+Info]; lpInfo
0x180025c96  xor     edx, edx; lpszEntry
0x180025c98  mov     rcx, [rcx]; lpszPhonebook
0x180025c9b  call    RasEntryDlgW
0x180025ca0  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180025ca6  mov     edi, eax
0x180025ca8  cmp     ecx, r15d
0x180025cab  jz      short loc_180025CC6
0x180025cad  mov     r9d, eax
0x180025cb0  lea     r8, aRasentrydlgD; "RasEntryDlg=%d"
0x180025cb7  mov     edx, r12d; dwFlags
0x180025cba  call    cs:__imp_TracePrintfExA
0x180025cc0  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180025cc6  cmp     qword ptr [rbx+120h], 0
0x180025cce  jz      short loc_180025CEF
0x180025cd0  cmp     qword ptr [rbx+148h], 0
0x180025cd8  jnz     short loc_180025CEF
0x180025cda  cmp     ecx, r15d
0x180025cdd  jz      loc_180025E15
0x180025ce3  lea     r8, aTakingShortcut; "Taking shortcut to exit"
0x180025cea  jmp     loc_180025E0C
0x180025cef  test    edi, edi
0x180025cf1  jz      loc_180025E00
0x180025cf7  cmp     ecx, r15d
0x180025cfa  jz      short loc_180025D0C
0x180025cfc  lea     rdx, [rbp+210h+Info.szEntry]; lpWideCharStr
0x180025d00  lea     rcx, aOkPressedES; "OK pressed, e=\"%s\""
0x180025d07  call    TracePrintfW1
0x180025d0c  mov     rcx, rsi
0x180025d0f  call    cs:__imp_ClosePhonebookFile
0x180025d15  mov     eax, [rbx+128h]
0x180025d1b  mov     rdx, r14
0x180025d1e  mov     rcx, [rbx]
0x180025d21  neg     eax
0x180025d23  mov     qword ptr [rsp+310h+var_2F0], rsi; int
0x180025d28  sbb     r9d, r9d
0x180025d2b  xor     r8d, r8d
0x180025d2e  and     r9d, 20h
0x180025d32  mov     rcx, [rcx]
0x180025d35  call    cs:__imp_ReadPhonebookFile
0x180025d3b  test    eax, eax
0x180025d3d  jz      short loc_180025D77
0x180025d3f  mov     rcx, [rbx+8]; hWnd
0x180025d43  xor     r9d, r9d
0x180025d46  mov     [rsp+310h+var_2E0], 0FAh; UINT
0x180025d4e  mov     r8d, eax; dwMessageId
0x180025d51  mov     edx, 141h; uID
0x180025d56  mov     [rsp+310h+var_2E8], 169h; UINT
0x180025d5e  call    ErrorDlgUtil
0x180025d63  mov     rcx, [rbx+8]; hDlg
0x180025d67  mov     edx, 1; nResult
0x180025d6c  call    cs:__imp_EndDialog
0x180025d72  jmp     loc_180025E15
0x180025d77  mov     rax, [rbx]
0x180025d7a  mov     rcx, [rax+10h]
0x180025d7e  mov     rdi, [rcx+20h]
0x180025d82  test    rdi, rdi
0x180025d85  jz      short loc_180025DDB
0x180025d87  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180025d8d  cmp     ecx, r15d
0x180025d90  jz      short loc_180025DA2
0x180025d92  lea     r8, aCallbackAddent; "Callback(AddEntry)"
0x180025d99  mov     edx, r12d; dwFlags
0x180025d9c  call    cs:__imp_TracePrintfExA
0x180025da2  mov     rcx, [rbx]
0x180025da5  lea     r8, [rbp+210h+Info.szEntry]
0x180025da9  xor     r9d, r9d
0x180025dac  mov     rax, rdi
0x180025daf  mov     rcx, [rcx+10h]
0x180025db3  lea     edx, [r9+1]
0x180025db7  mov     rcx, [rcx+18h]
0x180025dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025dc0  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180025dc6  cmp     ecx, r15d
0x180025dc9  jz      short loc_180025DDB
0x180025dcb  lea     r8, aCallbackAddent_0; "Callback(AddEntry) done"
0x180025dd2  mov     edx, r12d; dwFlags
0x180025dd5  call    cs:__imp_TracePrintfExA
0x180025ddb  lea     rdx, [rbp+210h+Info.szEntry]
0x180025ddf  mov     rcx, rbx
0x180025de2  call    DuUpdateLbEntries
0x180025de7  mov     rdx, [rbx+28h]; HWND
0x180025deb  mov     rcx, [rbx+8]; hWnd
0x180025def  call    Button_MakeDefault
0x180025df4  mov     rcx, [rbx+20h]; hWnd
0x180025df8  call    cs:__imp_SetFocus
0x180025dfe  jmp     short loc_180025E15
0x180025e00  cmp     ecx, r15d
0x180025e03  jz      short loc_180025E15
0x180025e05  lea     r8, aCancelPressedO; "Cancel pressed or error"
0x180025e0c  mov     edx, r12d; dwFlags
0x180025e0f  call    cs:__imp_TracePrintfExA
0x180025e15  mov     rcx, [rbp+210h+var_30]
0x180025e1c  xor     rcx, rsp; StackCookie
0x180025e1f  call    __security_check_cookie
0x180025e24  lea     r11, [rsp+310h+var_20]
0x180025e2c  mov     rbx, [r11+38h]
0x180025e30  mov     rsi, [r11+40h]
0x180025e34  mov     rsp, r11
0x180025e37  pop     r15
0x180025e39  pop     r14
0x180025e3b  pop     r12
0x180025e3d  pop     rdi
0x180025e3e  pop     rbp
0x180025e3f  retn
```
