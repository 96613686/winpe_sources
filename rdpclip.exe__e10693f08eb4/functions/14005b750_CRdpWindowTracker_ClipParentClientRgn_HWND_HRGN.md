# CRdpWindowTracker::ClipParentClientRgn(HWND__ *,HRGN__ *)

- ea: `0x14005b750`
- end: `0x14005ba03`
- name: `?ClipParentClientRgn@CRdpWindowTracker@@AEAAJPEAUHWND__@@PEAUHRGN__@@@Z`
- size: `691`
- prototype: `int(CRdpWindowTracker *__hidden this, HWND, HRGN)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14005ca44`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x14005b5dc`
- `0x14005b750`
- `0x14005e158`
- `0x14006a120`

## import_xrefs

- `USER32!GetClientRect` at `0x14005b7a5`
- `USER32!GetClientRect` at `0x14005b7a5`
- `USER32!GetParent` at `0x14005b78c`
- `USER32!GetParent` at `0x14005b856`
- `USER32!GetParent` at `0x14005b78c`
- `USER32!GetParent` at `0x14005b856`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b7af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b7af`
- `GDI32!CreateRectRgnIndirect` at `0x14005b80f`
- `GDI32!CreateRectRgnIndirect` at `0x14005b80f`
- `GDI32!CombineRgn` at `0x14005b830`
- `GDI32!CombineRgn` at `0x14005b830`
- `GDI32!DeleteObject` at `0x14005b83d`
- `GDI32!DeleteObject` at `0x14005b9d6`
- `GDI32!DeleteObject` at `0x14005b83d`
- `GDI32!DeleteObject` at `0x14005b9d6`

## string_xrefs

- `0x14005b8d9`: `CombineRgn() failed`
- `0x14005b946`: `CreateRectRgnIndirect() failed`

## pseudocode

```c
__int64 __fastcall CRdpWindowTracker::ClipParentClientRgn(CRdpWindowTracker *this, HWND a2, HRGN a3)
{
  unsigned int v3; // ebx
  HWND i; // rax
  HWND v6; // rdi
  signed int LastError; // eax
  int v8; // r14d
  int v9; // r15d
  HRGN v10; // rax
  HRGN v11; // rsi
  CRdpWindowTracker *v12; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v14; // edx
  const char *v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // eax
  struct tagPOINT v19; // [rsp+30h] [rbp-20h] BYREF
  struct tagRECT Rect; // [rsp+38h] [rbp-18h] BYREF

  v3 = 0;
  v19 = 0;
  Rect = 0;
  for ( i = GetParent(a2); ; i = GetParent(v6) )
  {
    v6 = i;
    if ( !i )
      return v3;
    if ( !GetClientRect(i, &Rect) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (v3 & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return v3;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 121;
        v15 = "GetClientRect failed";
LABEL_28:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v15,
          v3);
        return v3;
      }
    }
    v8 = Rect.right - Rect.left;
    v9 = Rect.bottom - Rect.top;
    v3 = CRdpWindowTracker::ClientTopLeftToScreen(v6, &v19);
    if ( (v3 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v3;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 122;
      v15 = "CRdpWindowTracker::ClientTopLeftToScreen() failed";
      goto LABEL_28;
    }
    Rect.left = v19.x;
    Rect.right = v8 + v19.x;
    Rect.top = v19.y;
    Rect.bottom = v9 + v19.y;
    v10 = CreateRectRgnIndirect(&Rect);
    v11 = v10;
    if ( !v10 )
      break;
    if ( !CombineRgn(a3, a3, v10, 1) )
    {
      v3 = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          124,
          (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
          v16,
          (__int64)"CombineRgn() failed",
          -2147467259);
      }
      DeleteObject(v11);
      return v3;
    }
    DeleteObject(v11);
    if ( !CRdpWindowTracker::IsChildStyleSet(v12, v6) )
      return v3;
  }
  v3 = -2147467259;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      123,
      (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
      v17,
      (__int64)"CreateRectRgnIndirect() failed",
      -2147467259);
  }
  return v3;
}

```

## disassembly

```asm
0x14005b750  mov     [rsp-28h+arg_0], rbx
0x14005b755  mov     [rsp-28h+arg_18], rsi
0x14005b75a  push    rbp
0x14005b75b  push    rdi
0x14005b75c  push    r12
0x14005b75e  push    r14
0x14005b760  push    r15
0x14005b762  mov     rbp, rsp
0x14005b765  sub     rsp, 50h
0x14005b769  mov     rax, cs:__security_cookie
0x14005b770  xor     rax, rsp
0x14005b773  mov     [rbp+var_8], rax
0x14005b777  xor     ebx, ebx
0x14005b779  xorps   xmm0, xmm0
0x14005b77c  xor     esi, esi
0x14005b77e  mov     qword ptr [rbp+var_20.x], rbx
0x14005b782  mov     rcx, rdx; hWnd
0x14005b785  mov     r12, r8
0x14005b788  movups  xmmword ptr [rbp+Rect.left], xmm0
0x14005b78c  call    cs:__imp_GetParent
0x14005b792  mov     rdi, rax
0x14005b795  test    rax, rax
0x14005b798  jz      loc_14005B9DC
0x14005b79e  lea     rdx, [rbp+Rect]; lpRect
0x14005b7a2  mov     rcx, rax; hWnd
0x14005b7a5  call    cs:__imp_GetClientRect
0x14005b7ab  test    eax, eax
0x14005b7ad  jnz     short loc_14005B7CC
0x14005b7af  call    cs:__imp_GetLastError
0x14005b7b5  mov     ebx, eax
0x14005b7b7  test    eax, eax
0x14005b7b9  jle     short loc_14005B7C4
0x14005b7bb  movzx   ebx, ax
0x14005b7be  or      ebx, 80070000h
0x14005b7c4  test    ebx, ebx
0x14005b7c6  js      loc_14005B863
0x14005b7cc  mov     r14d, [rbp+Rect.right]
0x14005b7d0  lea     rdx, [rbp+var_20]; struct tagPOINT *
0x14005b7d4  mov     r15d, [rbp+Rect.bottom]
0x14005b7d8  mov     rcx, rdi; hWnd
0x14005b7db  sub     r14d, [rbp+Rect.left]
0x14005b7df  sub     r15d, [rbp+Rect.top]
0x14005b7e3  call    ?ClientTopLeftToScreen@CRdpWindowTracker@@CAJPEAUHWND__@@PEAUtagPOINT@@@Z; CRdpWindowTracker::ClientTopLeftToScreen(HWND__ *,tagPOINT *)
0x14005b7e8  mov     ebx, eax
0x14005b7ea  test    eax, eax
0x14005b7ec  js      loc_14005B97B
0x14005b7f2  mov     ecx, [rbp+var_20.x]
0x14005b7f5  mov     edx, [rbp+var_20.y]
0x14005b7f8  mov     [rbp+Rect.left], ecx
0x14005b7fb  add     ecx, r14d
0x14005b7fe  mov     [rbp+Rect.right], ecx
0x14005b801  mov     [rbp+Rect.top], edx
0x14005b804  lea     ecx, [r15+rdx]
0x14005b808  mov     [rbp+Rect.bottom], ecx
0x14005b80b  lea     rcx, [rbp+Rect]; lprect
0x14005b80f  call    cs:__imp_CreateRectRgnIndirect
0x14005b815  mov     rsi, rax
0x14005b818  test    rax, rax
0x14005b81b  jz      loc_14005B911
0x14005b821  mov     r9d, 1; iMode
0x14005b827  mov     r8, rax; hrgnSrc2
0x14005b82a  mov     rdx, r12; hrgnSrc1
0x14005b82d  mov     rcx, r12; hrgnDst
0x14005b830  call    cs:__imp_CombineRgn
0x14005b836  test    eax, eax
0x14005b838  jz      short loc_14005B8A4
0x14005b83a  mov     rcx, rsi; ho
0x14005b83d  call    cs:__imp_DeleteObject
0x14005b843  mov     rdx, rdi; HWND
0x14005b846  call    ?IsChildStyleSet@CRdpWindowTracker@@AEAAHPEAUHWND__@@@Z; CRdpWindowTracker::IsChildStyleSet(HWND__ *)
0x14005b84b  test    eax, eax
0x14005b84d  jz      loc_14005B9DC
0x14005b853  mov     rcx, rdi; hWnd
0x14005b856  call    cs:__imp_GetParent
0x14005b85c  xor     esi, esi
0x14005b85e  jmp     loc_14005B792
0x14005b863  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b86a  lea     rax, WPP_GLOBAL_Control
0x14005b871  cmp     rcx, rax
0x14005b874  jz      loc_14005B9CE
0x14005b87a  test    byte ptr [rcx+1Ch], 8
0x14005b87e  jz      loc_14005B9CE
0x14005b884  cmp     byte ptr [rcx+19h], 2
0x14005b888  jb      loc_14005B9CE
0x14005b88e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b893  mov     edx, 79h ; 'y'
0x14005b898  lea     rcx, aGetclientrectF_0; "GetClientRect failed"
0x14005b89f  jmp     loc_14005B9AB
0x14005b8a4  mov     ebx, 80004005h
0x14005b8a9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b8b0  lea     rax, WPP_GLOBAL_Control
0x14005b8b7  cmp     rcx, rax
0x14005b8ba  jz      loc_14005B9D3
0x14005b8c0  test    byte ptr [rcx+1Ch], 8
0x14005b8c4  jz      loc_14005B9D3
0x14005b8ca  cmp     byte ptr [rcx+19h], 2
0x14005b8ce  jb      loc_14005B9D3
0x14005b8d4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b8d9  lea     rcx, aCombinergnFail; "CombineRgn() failed"
0x14005b8e0  mov     [rsp+50h+var_28], 80004005h
0x14005b8e8  mov     [rsp+50h+var_30], rcx
0x14005b8ed  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005b8f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b8fb  mov     edx, 7Ch ; '|'
0x14005b900  mov     r9d, eax
0x14005b903  mov     rcx, [rcx+10h]
0x14005b907  call    WPP_SF_DsD
0x14005b90c  jmp     loc_14005B9D3
0x14005b911  mov     ebx, 80004005h
0x14005b916  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b91d  lea     rax, WPP_GLOBAL_Control
0x14005b924  cmp     rcx, rax
0x14005b927  jz      loc_14005B9DC
0x14005b92d  test    byte ptr [rcx+1Ch], 8
0x14005b931  jz      loc_14005B9DC
0x14005b937  cmp     byte ptr [rcx+19h], 2
0x14005b93b  jb      loc_14005B9DC
0x14005b941  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b946  lea     rcx, aCreaterectrgni; "CreateRectRgnIndirect() failed"
0x14005b94d  mov     [rsp+50h+var_28], 80004005h
0x14005b955  mov     [rsp+50h+var_30], rcx
0x14005b95a  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005b961  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b968  mov     edx, 7Bh ; '{'
0x14005b96d  mov     r9d, eax
0x14005b970  mov     rcx, [rcx+10h]
0x14005b974  call    WPP_SF_DsD
0x14005b979  jmp     short loc_14005B9DC
0x14005b97b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b982  lea     rax, WPP_GLOBAL_Control
0x14005b989  cmp     rcx, rax
0x14005b98c  jz      short loc_14005B9CE
0x14005b98e  test    byte ptr [rcx+1Ch], 8
0x14005b992  jz      short loc_14005B9CE
0x14005b994  cmp     byte ptr [rcx+19h], 2
0x14005b998  jb      short loc_14005B9CE
0x14005b99a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b99f  mov     edx, 7Ah ; 'z'
0x14005b9a4  lea     rcx, aCrdpwindowtrac; "CRdpWindowTracker::ClientTopLeftToScree"...
0x14005b9ab  mov     [rsp+50h+var_28], ebx
0x14005b9af  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005b9b6  mov     [rsp+50h+var_30], rcx
0x14005b9bb  mov     r9d, eax
0x14005b9be  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b9c5  mov     rcx, [rcx+10h]
0x14005b9c9  call    WPP_SF_DsD
0x14005b9ce  test    rsi, rsi
0x14005b9d1  jz      short loc_14005B9DC
0x14005b9d3  mov     rcx, rsi; ho
0x14005b9d6  call    cs:__imp_DeleteObject
0x14005b9dc  mov     eax, ebx
0x14005b9de  mov     rcx, [rbp+var_8]
0x14005b9e2  xor     rcx, rsp; StackCookie
0x14005b9e5  call    __security_check_cookie
0x14005b9ea  lea     r11, [rsp+50h+var_s0]
0x14005b9ef  mov     rbx, [r11+30h]
0x14005b9f3  mov     rsi, [r11+48h]
0x14005b9f7  mov     rsp, r11
0x14005b9fa  pop     r15
0x14005b9fc  pop     r14
0x14005b9fe  pop     r12
0x14005ba00  pop     rdi
0x14005ba01  pop     rbp
0x14005ba02  retn
```
