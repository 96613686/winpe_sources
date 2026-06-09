# SetGlobalProperty(tagHH_GLOBAL_PROPERTY *,CHHWinType *)

- ea: `0x180038fa8`
- end: `0x1800391a7`
- name: `?SetGlobalProperty@@YA_NPEAUtagHH_GLOBAL_PROPERTY@@PEAVCHHWinType@@@Z`
- size: `511`
- prototype: `bool __fastcall(struct tagHH_GLOBAL_PROPERTY *, struct CHHWinType *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800399ec`

## callees

- `0x18000c02c`
- `0x180038fa8`
- `0x180075c90`

## import_xrefs

- `KERNEL32!GetThreadUILanguage` at `0x180039099`
- `KERNEL32!GetThreadUILanguage` at `0x180039099`
- `USER32!UpdateWindow` at `0x18003915e`
- `USER32!UpdateWindow` at `0x18003915e`
- `USER32!InvalidateRect` at `0x180039154`
- `USER32!InvalidateRect` at `0x180039154`
- `USER32!SendMessageA` at `0x18003911e`
- `USER32!SendMessageA` at `0x18003911e`

## pseudocode

```c
char __fastcall SetGlobalProperty(struct tagHH_GLOBAL_PROPERTY *a1, HWND *a2)
{
  char v5; // bl
  __int32 v6; // ecx
  __int32 v7; // ecx
  __int32 v8; // ecx
  const unsigned __int16 *bstrVal; // r8
  VARTYPE vt; // ax
  SHORT iVal; // di
  LANGID ThreadUILanguage; // ax
  int uiVal; // edx
  HWND v14; // rcx
  RECT Rect; // [rsp+40h] [rbp-28h] BYREF

  if ( !a1 )
    return 0;
  v5 = 0;
  v6 = a1->id - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( !v8 )
      {
        vt = a1->var.vt;
        if ( vt == 3 || vt == 2 || vt == 19 || vt == 18 )
        {
          iVal = a1->var.iVal;
          if ( iVal )
          {
            ThreadUILanguage = word_18008B4C8;
            if ( !word_18008B4C8 )
            {
              word_18008B4C8 = a1->var.iVal;
              ThreadUILanguage = GetThreadUILanguage();
              word_18008B4C8 = ThreadUILanguage;
            }
            return ThreadUILanguage == (LANGID)iVal;
          }
        }
        return v5;
      }
      if ( v8 == 1 && a1->var.vt == 8 )
      {
        bstrVal = a1->var.bstrVal;
        if ( bstrVal )
        {
          if ( *bstrVal )
          {
            HHWideCharToMultiByte(0, 0, bstrVal, -1, &String1, 51, 0, 0);
            return 1;
          }
        }
      }
    }
    else if ( ((a1->var.vt - 19) & 0xFFFB) == 0 )
    {
      uiVal = a1->var.uiVal;
      if ( uiVal == g_tbLeftMargin && WORD1(a1->var.decVal.Lo64) == g_tbRightMargin )
        return 1;
      g_tbRightMargin = WORD1(a1->var.decVal.Lo64);
      g_tbLeftMargin = uiVal;
      if ( a2 && a2[11] )
      {
        SendMessageA(a2[8], 5u, 0, 0);
        v5 = 1;
        v14 = a2[8];
        Rect.bottom = *((_DWORD *)a2 + 135) - *((_DWORD *)a2 + 133);
        Rect.right = *((_DWORD *)a2 + 12) - *((_DWORD *)a2 + 10);
        *(_QWORD *)&Rect.left = 0;
        InvalidateRect(v14, &Rect, 1);
        UpdateWindow(a2[8]);
      }
    }
  }
  else if ( a1->var.vt == 11 )
  {
    g_fStandAlone = a1->var.iVal == 0xFFFF;
    return 1;
  }
  return v5;
}

```

## disassembly

```asm
0x180038fa8  mov     [rsp+arg_10], rbx
0x180038fad  mov     [rsp+arg_18], rsi
0x180038fb2  push    rdi
0x180038fb3  sub     rsp, 60h
0x180038fb7  mov     rax, cs:__security_cookie
0x180038fbe  xor     rax, rsp
0x180038fc1  mov     [rsp+68h+var_18], rax
0x180038fc6  xor     esi, esi
0x180038fc8  mov     rdi, rdx
0x180038fcb  mov     r8, rcx
0x180038fce  test    rcx, rcx
0x180038fd1  jnz     short loc_180038FDA
0x180038fd3  xor     al, al
0x180038fd5  jmp     loc_180039188
0x180038fda  mov     ecx, [rcx]
0x180038fdc  mov     bl, sil
0x180038fdf  sub     ecx, 1
0x180038fe2  jz      loc_180039166
0x180038fe8  sub     ecx, 1
0x180038feb  jz      loc_1800390B1
0x180038ff1  sub     ecx, 1
0x180038ff4  jz      short loc_180039052
0x180038ff6  cmp     ecx, 1
0x180038ff9  jnz     loc_180039186
0x180038fff  cmp     word ptr [r8+8], 8
0x180039005  jnz     loc_180039186
0x18003900b  mov     r8, [r8+10h]; unsigned __int16 *
0x18003900f  test    r8, r8
0x180039012  jz      loc_180039186
0x180039018  cmp     [r8], si
0x18003901c  jz      loc_180039186
0x180039022  mov     [rsp+68h+var_30], rsi; LPBOOL
0x180039027  lea     rax, String1
0x18003902e  mov     [rsp+68h+var_38], rsi; LPCCH
0x180039033  or      r9d, 0FFFFFFFFh; int
0x180039037  mov     [rsp+68h+var_40], 33h ; '3'; int
0x18003903f  xor     edx, edx; unsigned int
0x180039041  xor     ecx, ecx; unsigned int
0x180039043  mov     [rsp+68h+var_48], rax; LPSTR
0x180039048  call    ?HHWideCharToMultiByte@@YAHIKPEBGHPEADHPEBDPEAH@Z; HHWideCharToMultiByte(uint,ulong,ushort const *,int,char *,int,char const *,int *)
0x18003904d  jmp     loc_180039181
0x180039052  movzx   eax, word ptr [r8+8]
0x180039057  cmp     ax, 3
0x18003905b  jz      short loc_180039073
0x18003905d  cmp     ax, 2
0x180039061  jz      short loc_180039073
0x180039063  cmp     ax, 13h
0x180039067  jz      short loc_180039073
0x180039069  cmp     ax, 12h
0x18003906d  jnz     loc_180039186
0x180039073  mov     eax, 10h
0x180039078  movzx   edi, word ptr [r8+rax]
0x18003907d  test    di, di
0x180039080  jz      loc_180039186
0x180039086  movzx   eax, cs:word_18008B4C8
0x18003908d  test    ax, ax
0x180039090  jnz     short loc_1800390A6
0x180039092  mov     cs:word_18008B4C8, di
0x180039099  call    cs:__imp_GetThreadUILanguage
0x18003909f  mov     cs:word_18008B4C8, ax
0x1800390a6  cmp     ax, di
0x1800390a9  setz    bl
0x1800390ac  jmp     loc_180039186
0x1800390b1  movzx   eax, word ptr [r8+8]
0x1800390b6  mov     ecx, 0FFFBh
0x1800390bb  sub     ax, 13h
0x1800390bf  test    cx, ax
0x1800390c2  jnz     loc_180039186
0x1800390c8  movzx   edx, word ptr [r8+10h]
0x1800390cd  movsx   eax, cs:?g_tbLeftMargin@@3FA; short g_tbLeftMargin
0x1800390d4  cmp     edx, eax
0x1800390d6  jnz     short loc_1800390F2
0x1800390d8  movzx   ecx, word ptr [r8+12h]
0x1800390dd  movsx   eax, cs:?g_tbRightMargin@@3FA; short g_tbRightMargin
0x1800390e4  cmp     ecx, eax
0x1800390e6  jnz     short loc_1800390F2
0x1800390e8  mov     eax, 1
0x1800390ed  jmp     loc_180039188
0x1800390f2  movzx   eax, word ptr [r8+12h]
0x1800390f7  mov     cs:?g_tbRightMargin@@3FA, ax; short g_tbRightMargin
0x1800390fe  mov     cs:?g_tbLeftMargin@@3FA, dx; short g_tbLeftMargin
0x180039105  test    rdi, rdi
0x180039108  jz      short loc_180039186
0x18003910a  cmp     [rdi+58h], rsi
0x18003910e  jz      short loc_180039186
0x180039110  mov     rcx, [rdi+40h]; hWnd
0x180039114  xor     r9d, r9d; lParam
0x180039117  xor     r8d, r8d; wParam
0x18003911a  lea     edx, [r9+5]; Msg
0x18003911e  call    cs:__imp_SendMessageA
0x180039124  mov     eax, [rdi+21Ch]
0x18003912a  lea     rdx, [rsp+68h+Rect]; lpRect
0x18003912f  sub     eax, [rdi+214h]
0x180039135  mov     ebx, 1
0x18003913a  mov     rcx, [rdi+40h]; hWnd
0x18003913e  mov     r8d, ebx; bErase
0x180039141  mov     [rsp+68h+Rect.bottom], eax
0x180039145  mov     eax, [rdi+30h]
0x180039148  sub     eax, [rdi+28h]
0x18003914b  mov     [rsp+68h+Rect.right], eax
0x18003914f  mov     qword ptr [rsp+68h+Rect.left], rsi
0x180039154  call    cs:__imp_InvalidateRect
0x18003915a  mov     rcx, [rdi+40h]; hWnd
0x18003915e  call    cs:__imp_UpdateWindow
0x180039164  jmp     short loc_180039186
0x180039166  cmp     word ptr [r8+8], 0Bh
0x18003916c  jnz     short loc_180039186
0x18003916e  mov     eax, esi
0x180039170  or      ecx, 0FFFFFFFFh
0x180039173  cmp     [r8+10h], cx
0x180039178  setz    al
0x18003917b  mov     cs:?g_fStandAlone@@3HA, eax; int g_fStandAlone
0x180039181  mov     ebx, 1
0x180039186  mov     al, bl
0x180039188  mov     rcx, [rsp+68h+var_18]
0x18003918d  xor     rcx, rsp; StackCookie
0x180039190  call    __security_check_cookie
0x180039195  lea     r11, [rsp+68h+var_8]
0x18003919a  mov     rbx, [r11+20h]
0x18003919e  mov     rsi, [r11+28h]
0x1800391a2  mov     rsp, r11
0x1800391a5  pop     rdi
0x1800391a6  retn
```
