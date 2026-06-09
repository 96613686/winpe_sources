# COleControl::OnChar(uint,uint,uint)

- ea: `0x1801eccb0`
- end: `0x1801ecf10`
- name: `?OnChar@COleControl@@IEAAXIII@Z`
- size: `608`
- prototype: `void __fastcall(COleControl *this, unsigned int nChar, unsigned int nRepCnt, unsigned int nFlags)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1801ec830`
- `0x1801ecbc4`
- `0x1801eccb0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1801ece78`
- `KERNEL32!CompareStringW` at `0x1801ece9f`
- `KERNEL32!CompareStringW` at `0x1801ecec6`
- `KERNEL32!CompareStringW` at `0x1801ece78`
- `KERNEL32!CompareStringW` at `0x1801ece9f`
- `KERNEL32!CompareStringW` at `0x1801ecec6`
- `KERNEL32!IsDBCSLeadByte` at `0x1801ecceb`
- `KERNEL32!IsDBCSLeadByte` at `0x1801ecdb8`
- `KERNEL32!IsDBCSLeadByte` at `0x1801ecceb`
- `KERNEL32!IsDBCSLeadByte` at `0x1801ecdb8`
- `USER32!PeekMessageW` at `0x1801ecd34`
- `USER32!PeekMessageW` at `0x1801ecde0`
- `USER32!PeekMessageW` at `0x1801ecde8`
- `USER32!PeekMessageW` at `0x1801eceea`
- `USER32!PeekMessageW` at `0x1801ecd34`
- `USER32!PeekMessageW` at `0x1801ecde0`
- `USER32!PeekMessageW` at `0x1801ecde8`
- `USER32!PeekMessageW` at `0x1801eceea`
- `USER32!GetClassNameW` at `0x1801ece48`
- `USER32!GetClassNameW` at `0x1801ece48`

## string_xrefs

- `0x1801eceaa`: `ComboBox`

## pseudocode

```c
void __fastcall COleControl::OnChar(
        COleControl *this,
        unsigned int nChar,
        unsigned __int16 nRepCnt,
        unsigned __int16 nFlags)
{
  unsigned int v7; // esi
  unsigned __int16 v8; // di
  BOOL v9; // r14d
  HWND__ *m_hWnd; // r15
  unsigned __int16 v11; // cx
  BOOL v12; // eax
  HWND__ *v13; // rdx
  unsigned __int16 nCharShort; // [rsp+30h] [rbp-49h] BYREF
  tagMSG msg; // [rsp+38h] [rbp-41h] BYREF
  wchar_t szClassName[12]; // [rsp+68h] [rbp-11h] BYREF

  nCharShort = nChar;
  v7 = nChar;
  v8 = nChar;
  v9 = IsDBCSLeadByte(nChar);
  if ( (*(_BYTE *)this->GetEventMap(this)->lpStockEventMask & 8) == 0 )
  {
    v11 = nCharShort;
    goto LABEL_11;
  }
  if ( v9 && PeekMessageW(&msg, this->m_hWnd, 0x102u, 0x102u, 2u) )
  {
    v8 = LOWORD(msg.wParam) | (nCharShort << 8);
    nCharShort = v8;
  }
  else
  {
    v8 = nCharShort;
  }
  m_hWnd = this->m_hWnd;
  COleControl::FireEvent(this, -603, "B", &nCharShort);
  v11 = nCharShort;
  if ( nCharShort )
  {
    this->OnKeyPressEvent(this, nCharShort);
    v11 = nCharShort;
  }
  if ( this->m_hWnd == m_hWnd )
  {
LABEL_11:
    if ( !v11 )
    {
LABEL_20:
      if ( v9
        && (!GetClassNameW(this->m_hWnd, szClassName, 10)
         || CompareStringW(0x7Fu, 1u, szClassName, -1, L"Edit", -1) != 2
         && CompareStringW(0x7Fu, 1u, szClassName, -1, L"ListBox", -1) != 2
         && CompareStringW(0x7Fu, 1u, szClassName, -1, L"ComboBox", -1) != 2) )
      {
        PeekMessageW(&msg, this->m_hWnd, 0x102u, 0x102u, 3u);
      }
      return;
    }
    if ( v8 != v11 )
    {
      v7 = v11;
      v12 = IsDBCSLeadByte(HIBYTE(v11));
      if ( v9 )
      {
        v13 = this->m_hWnd;
        if ( v12 )
        {
          PeekMessageW(&msg, v13, 0x102u, 0x102u, 3u);
LABEL_18:
          _AfxPostTrailByte(this, nCharShort);
          v7 = HIBYTE(nCharShort);
          goto LABEL_19;
        }
        PeekMessageW(&msg, v13, 0x102u, 0x102u, 3u);
      }
      else if ( v12 )
      {
        goto LABEL_18;
      }
    }
LABEL_19:
    this->DefWindowProcW(this, 258u, v7, nRepCnt | (nFlags << 16));
    goto LABEL_20;
  }
}

```

## disassembly

```asm
0x1801eccb0  push    rbp
0x1801eccb2  push    rbx
0x1801eccb3  push    rsi
0x1801eccb4  push    rdi
0x1801eccb5  push    r12
0x1801eccb7  push    r13
0x1801eccb9  push    r14
0x1801eccbb  push    r15
0x1801eccbd  lea     rbp, [rsp-1Fh]
0x1801eccc2  sub     rsp, 98h
0x1801eccc9  mov     rax, cs:__security_cookie
0x1801eccd0  xor     rax, rsp
0x1801eccd3  mov     [rbp+57h+var_50], rax
0x1801eccd7  mov     rbx, this
0x1801eccda  mov     [rbp+57h+nCharShort], dx
0x1801eccde  mov     cl, dl; TestChar
0x1801ecce0  mov     r13d, nFlags
0x1801ecce3  mov     r12d, nRepCnt
0x1801ecce6  mov     esi, nChar
0x1801ecce8  movzx   edi, dx
0x1801ecceb  call    cs:__imp_IsDBCSLeadByte
0x1801eccf1  mov     this, [rbx]
0x1801eccf4  mov     r14d, eax
0x1801eccf7  mov     rax, [this+4D0h]
0x1801eccfe  mov     this, rbx
0x1801ecd01  call    cs:__guard_dispatch_icall_fptr
0x1801ecd07  mov     this, [rax+10h]
0x1801ecd0b  mov     eax, 102h
0x1801ecd10  test    byte ptr [this], 8
0x1801ecd13  jz      loc_1801ECD9F
0x1801ecd19  test    r14d, r14d
0x1801ecd1c  jz      short loc_1801ECD50
0x1801ecd1e  mov     rdx, [rbx+40h]; hWnd
0x1801ecd22  lea     this, [rbp+57h+msg]; lpMsg
0x1801ecd26  mov     nFlags, eax; wMsgFilterMax
0x1801ecd29  mov     [rsp+0D0h+wRemoveMsg], 2; wRemoveMsg
0x1801ecd31  mov     nRepCnt, eax; wMsgFilterMin
0x1801ecd34  call    cs:__imp_PeekMessageW
0x1801ecd3a  test    eax, eax
0x1801ecd3c  jz      short loc_1801ECD50
0x1801ecd3e  movzx   edi, [rbp+57h+nCharShort]
0x1801ecd42  shl     rdi, 8
0x1801ecd46  or      di, word ptr [rbp+57h+msg.wParam]
0x1801ecd4a  mov     [rbp+57h+nCharShort], di
0x1801ecd4e  jmp     short loc_1801ECD54
0x1801ecd50  movzx   edi, [rbp+57h+nCharShort]
0x1801ecd54  mov     r15, [rbx+40h]
0x1801ecd58  lea     r9, [rbp+57h+nCharShort]
0x1801ecd5c  lea     r8, aB_0; "B"
0x1801ecd63  mov     nChar, 0FFFFFDA5h; dispid
0x1801ecd68  mov     this, rbx; this
0x1801ecd6b  call    ?FireEvent@COleControl@@QEAAXJPEAEZZ; COleControl::FireEvent(long,uchar *,...)
0x1801ecd70  movzx   ecx, [rbp+57h+nCharShort]
0x1801ecd74  test    cx, cx
0x1801ecd77  jz      short loc_1801ECD93
0x1801ecd79  mov     rax, [rbx]
0x1801ecd7c  movzx   nChar, cx
0x1801ecd7f  mov     this, rbx
0x1801ecd82  mov     rax, [rax+358h]
0x1801ecd89  call    cs:__guard_dispatch_icall_fptr
0x1801ecd8f  movzx   ecx, [rbp+57h+nCharShort]
0x1801ecd93  cmp     [rbx+40h], r15
0x1801ecd97  jnz     loc_1801ECEF0
0x1801ecd9d  jmp     short loc_1801ECDA3
0x1801ecd9f  movzx   ecx, [rbp+57h+nCharShort]
0x1801ecda3  test    cx, cx
0x1801ecda6  jz      loc_1801ECE31
0x1801ecdac  cmp     di, cx
0x1801ecdaf  jz      short loc_1801ECE06
0x1801ecdb1  movzx   esi, cx
0x1801ecdb4  shr     cx, 8; TestChar
0x1801ecdb8  call    cs:__imp_IsDBCSLeadByte
0x1801ecdbe  test    r14d, r14d
0x1801ecdc1  jz      short loc_1801ECDF0
0x1801ecdc3  mov     rdx, [rbx+40h]; hWnd
0x1801ecdc7  mov     nFlags, 102h; wMsgFilterMax
0x1801ecdcd  mov     [rsp+0D0h+wRemoveMsg], 3; wRemoveMsg
0x1801ecdd5  mov     nRepCnt, nFlags; wMsgFilterMin
0x1801ecdd8  lea     this, [rbp+57h+msg]; lpMsg
0x1801ecddc  test    eax, eax
0x1801ecdde  jz      short loc_1801ECDE8
0x1801ecde0  call    cs:__imp_PeekMessageW
0x1801ecde6  jmp     short loc_1801ECDF4
0x1801ecde8  call    cs:__imp_PeekMessageW
0x1801ecdee  jmp     short loc_1801ECE06
0x1801ecdf0  test    eax, eax
0x1801ecdf2  jz      short loc_1801ECE06
0x1801ecdf4  mov     dl, byte ptr [rbp+57h+nCharShort]; bTrailByte
0x1801ecdf7  mov     this, rbx; pWnd
0x1801ecdfa  call    ?_AfxPostTrailByte@@YAXPEAVCWnd@@E@Z; _AfxPostTrailByte(CWnd *,uchar)
0x1801ecdff  movzx   esi, [rbp+57h+nCharShort]
0x1801ece03  shr     esi, 8
0x1801ece06  mov     r10, [rbx]
0x1801ece09  mov     nChar, 102h
0x1801ece0e  movzx   ecx, r13w
0x1801ece12  shl     ecx, 10h
0x1801ece15  movzx   eax, r12w
0x1801ece19  or      ecx, eax
0x1801ece1b  mov     nRepCnt, esi
0x1801ece1e  mov     rax, [r10+248h]
0x1801ece25  movsxd  r9, ecx
0x1801ece28  mov     this, rbx
0x1801ece2b  call    cs:__guard_dispatch_icall_fptr
0x1801ece31  test    r14d, r14d
0x1801ece34  jz      loc_1801ECEF0
0x1801ece3a  mov     this, [rbx+40h]; hWnd
0x1801ece3e  lea     rdx, [rbp+57h+szClassName]; lpClassName
0x1801ece42  mov     nRepCnt, 0Ah; nMaxCount
0x1801ece48  call    cs:__imp_GetClassNameW
0x1801ece4e  test    eax, eax
0x1801ece50  jz      short loc_1801ECED1
0x1801ece52  or      edi, 0FFFFFFFFh
0x1801ece55  lea     rax, aEdit_0; "Edit"
0x1801ece5c  mov     [rsp+0D0h+cchCount2], edi; cchCount2
0x1801ece60  lea     r8, [rbp+57h+szClassName]; lpString1
0x1801ece64  mov     nFlags, edi; cchCount1
0x1801ece67  mov     qword ptr [rsp+0D0h+wRemoveMsg], rax; lpString2
0x1801ece6c  lea     esi, [rdi+2]
0x1801ece6f  lea     r14d, [rsi+7Eh]
0x1801ece73  mov     nChar, esi; dwCmpFlags
0x1801ece75  mov     ecx, r14d; Locale
0x1801ece78  call    cs:__imp_CompareStringW
0x1801ece7e  cmp     eax, 2
0x1801ece81  jz      short loc_1801ECEF0
0x1801ece83  lea     rax, aListbox_0; "ListBox"
0x1801ece8a  mov     [rsp+0D0h+cchCount2], edi; cchCount2
0x1801ece8e  mov     nFlags, edi; cchCount1
0x1801ece91  mov     qword ptr [rsp+0D0h+wRemoveMsg], rax; lpString2
0x1801ece96  lea     r8, [rbp+57h+szClassName]; lpString1
0x1801ece9a  mov     nChar, esi; dwCmpFlags
0x1801ece9c  mov     ecx, r14d; Locale
0x1801ece9f  call    cs:__imp_CompareStringW
0x1801ecea5  cmp     eax, 2
0x1801ecea8  jz      short loc_1801ECEF0
0x1801eceaa  lea     rax, aCombobox; "ComboBox"
0x1801eceb1  mov     [rsp+0D0h+cchCount2], edi; cchCount2
0x1801eceb5  mov     nFlags, edi; cchCount1
0x1801eceb8  mov     qword ptr [rsp+0D0h+wRemoveMsg], rax; lpString2
0x1801ecebd  lea     r8, [rbp+57h+szClassName]; lpString1
0x1801ecec1  mov     nChar, esi; dwCmpFlags
0x1801ecec3  mov     ecx, r14d; Locale
0x1801ecec6  call    cs:__imp_CompareStringW
0x1801ececc  cmp     eax, 2
0x1801ececf  jz      short loc_1801ECEF0
0x1801eced1  mov     rdx, [rbx+40h]; hWnd
0x1801eced5  lea     this, [rbp+57h+msg]; lpMsg
0x1801eced9  mov     nFlags, 102h; wMsgFilterMax
0x1801ecedf  mov     [rsp+0D0h+wRemoveMsg], 3; wRemoveMsg
0x1801ecee7  mov     nRepCnt, nFlags; wMsgFilterMin
0x1801eceea  call    cs:__imp_PeekMessageW
0x1801ecef0  mov     this, [rbp+57h+var_50]
0x1801ecef4  xor     this, rsp; StackCookie
0x1801ecef7  call    __security_check_cookie
0x1801ecefc  add     rsp, 98h
0x1801ecf03  pop     r15
0x1801ecf05  pop     r14
0x1801ecf07  pop     r13
0x1801ecf09  pop     r12
0x1801ecf0b  pop     rdi
0x1801ecf0c  pop     rsi
0x1801ecf0d  pop     rbx
0x1801ecf0e  pop     rbp
0x1801ecf0f  retn
```
