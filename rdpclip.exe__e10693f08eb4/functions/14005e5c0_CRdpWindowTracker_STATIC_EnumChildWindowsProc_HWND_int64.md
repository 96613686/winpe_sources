# CRdpWindowTracker::STATIC_EnumChildWindowsProc(HWND__ *,__int64)

- ea: `0x14005e5c0`
- end: `0x14005e73c`
- name: `?STATIC_EnumChildWindowsProc@CRdpWindowTracker@@CAHPEAUHWND__@@_J@Z`
- size: `380`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x14005e5c0`
- `0x14005ebd0`
- `0x14005ef5c`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x14005e631`
- `USER32!GetWindowLongPtrW` at `0x14005e631`
- `USER32!IsWindowVisible` at `0x14005e5e8`
- `USER32!IsWindowVisible` at `0x14005e5e8`
- `USER32!GetDesktopWindow` at `0x14005e5f9`
- `USER32!GetDesktopWindow` at `0x14005e5f9`
- `USER32!GetAncestor` at `0x14005e61b`
- `USER32!GetAncestor` at `0x14005e61b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005e727`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005e727`
- `GDI32!CombineRgn` at `0x14005e6b7`
- `GDI32!CombineRgn` at `0x14005e6b7`

## string_xrefs

- `0x14005e6f7`: `CombineRgn() failed`

## pseudocode

```c
__int64 __fastcall CRdpWindowTracker::STATIC_EnumChildWindowsProc(HWND a1, __int64 a2)
{
  int WindowRegionOrBounds; // ebp
  int v5; // r14d
  HWND Ancestor; // rdi
  HWND i; // r15
  unsigned int v8; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v10; // ebx
  int v12; // [rsp+28h] [rbp-40h]
  int v13; // [rsp+28h] [rbp-40h]

  WindowRegionOrBounds = 0;
  if ( *(HWND *)a2 == a1 )
  {
    v5 = 0;
  }
  else
  {
    v5 = 1;
    if ( IsWindowVisible(a1) )
    {
      Ancestor = *(HWND *)a2;
      for ( i = GetDesktopWindow(); Ancestor != i; Ancestor = GetAncestor(Ancestor, 1u) )
      {
        if ( !Ancestor )
          break;
        if ( Ancestor == a1 )
          goto LABEL_20;
      }
      if ( (GetWindowLongPtrW(a1, -16) & 0x8000) == 0 && !(unsigned int)CRdpWindowTracker::ShouldIgnoreLayeredWindow(a1) )
      {
        WindowRegionOrBounds = CRdpWindowTracker::STATIC_GetWindowRegionOrBounds(a1, *(HRGN *)(a2 + 24));
        if ( WindowRegionOrBounds >= 0 )
        {
          if ( !CombineRgn(*(HRGN *)(a2 + 16), *(HRGN *)(a2 + 16), *(HRGN *)(a2 + 24), 4) )
          {
            WindowRegionOrBounds = -2147467259;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v13 = -2147467259;
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                68,
                (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
                CurrentThreadActivityIdPrefix,
                (__int64)"CombineRgn() failed",
                v13);
            }
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = RdpWppGetCurrentThreadActivityIdPrefix();
          v12 = WindowRegionOrBounds;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            67,
            (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
            v8,
            (__int64)"GetWindowRegionOrBounds() failed",
            v12);
        }
      }
    }
  }
LABEL_20:
  v10 = 0;
  if ( WindowRegionOrBounds >= 0 )
    v10 = v5;
  SetLastError(0);
  return v10;
}

```

## disassembly

```asm
0x14005e5c0  push    rbx
0x14005e5c2  push    rbp
0x14005e5c3  push    rsi
0x14005e5c4  push    rdi
0x14005e5c5  push    r14
0x14005e5c7  push    r15
0x14005e5c9  sub     rsp, 38h
0x14005e5cd  xor     ebp, ebp
0x14005e5cf  mov     rsi, rdx
0x14005e5d2  mov     rbx, rcx
0x14005e5d5  cmp     [rdx], rcx
0x14005e5d8  jnz     short loc_14005E5E2
0x14005e5da  xor     r14d, r14d
0x14005e5dd  jmp     loc_14005E71D
0x14005e5e2  mov     r14d, 1
0x14005e5e8  call    cs:__imp_IsWindowVisible
0x14005e5ee  test    eax, eax
0x14005e5f0  jz      loc_14005E71D
0x14005e5f6  mov     rdi, [rsi]
0x14005e5f9  call    cs:__imp_GetDesktopWindow
0x14005e5ff  mov     r15, rax
0x14005e602  cmp     rdi, rax
0x14005e605  jz      short loc_14005E629
0x14005e607  test    rdi, rdi
0x14005e60a  jz      short loc_14005E629
0x14005e60c  cmp     rdi, rbx
0x14005e60f  jz      loc_14005E71D
0x14005e615  mov     edx, r14d; gaFlags
0x14005e618  mov     rcx, rdi; hwnd
0x14005e61b  call    cs:__imp_GetAncestor
0x14005e621  mov     rdi, rax
0x14005e624  cmp     rax, r15
0x14005e627  jnz     short loc_14005E607
0x14005e629  mov     edx, 0FFFFFFF0h; nIndex
0x14005e62e  mov     rcx, rbx; hWnd
0x14005e631  call    cs:__imp_GetWindowLongPtrW
0x14005e637  bt      rax, 0Fh
0x14005e63c  jb      loc_14005E71D
0x14005e642  mov     rcx, rbx; hWnd
0x14005e645  call    ?ShouldIgnoreLayeredWindow@CRdpWindowTracker@@CAHPEAUHWND__@@@Z; CRdpWindowTracker::ShouldIgnoreLayeredWindow(HWND__ *)
0x14005e64a  test    eax, eax
0x14005e64c  jnz     loc_14005E71D
0x14005e652  mov     rdx, [rsi+18h]; hrgn
0x14005e656  mov     rcx, rbx; hWnd
0x14005e659  call    ?STATIC_GetWindowRegionOrBounds@CRdpWindowTracker@@CAJPEAUHWND__@@PEAUHRGN__@@@Z; CRdpWindowTracker::STATIC_GetWindowRegionOrBounds(HWND__ *,HRGN__ *)
0x14005e65e  mov     ebp, eax
0x14005e660  test    eax, eax
0x14005e662  jns     short loc_14005E6A6
0x14005e664  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e66b  lea     rdx, WPP_GLOBAL_Control
0x14005e672  cmp     rcx, rdx
0x14005e675  jz      loc_14005E71D
0x14005e67b  test    byte ptr [rcx+1Ch], 8
0x14005e67f  jz      loc_14005E71D
0x14005e685  cmp     byte ptr [rcx+19h], 2
0x14005e689  jb      loc_14005E71D
0x14005e68f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005e694  mov     edx, 43h ; 'C'
0x14005e699  mov     [rsp+68h+var_40], ebp
0x14005e69d  lea     rcx, aGetwindowregio; "GetWindowRegionOrBounds() failed"
0x14005e6a4  jmp     short loc_14005E6FE
0x14005e6a6  mov     rcx, [rsi+10h]; hrgnDst
0x14005e6aa  mov     r9d, 4; iMode
0x14005e6b0  mov     r8, [rsi+18h]; hrgnSrc2
0x14005e6b4  mov     rdx, rcx; hrgnSrc1
0x14005e6b7  call    cs:__imp_CombineRgn
0x14005e6bd  test    eax, eax
0x14005e6bf  jnz     short loc_14005E71D
0x14005e6c1  mov     ebp, 80004005h
0x14005e6c6  mov     rax, cs:WPP_GLOBAL_Control
0x14005e6cd  lea     rdx, WPP_GLOBAL_Control
0x14005e6d4  cmp     rax, rdx
0x14005e6d7  jz      short loc_14005E71D
0x14005e6d9  test    byte ptr [rax+1Ch], 8
0x14005e6dd  jz      short loc_14005E71D
0x14005e6df  cmp     byte ptr [rax+19h], 2
0x14005e6e3  jb      short loc_14005E71D
0x14005e6e5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005e6ea  mov     edx, 44h ; 'D'
0x14005e6ef  mov     [rsp+68h+var_40], 80004005h
0x14005e6f7  lea     rcx, aCombinergnFail; "CombineRgn() failed"
0x14005e6fe  mov     [rsp+68h+var_48], rcx
0x14005e703  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005e70a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e711  mov     r9d, eax
0x14005e714  mov     rcx, [rcx+10h]
0x14005e718  call    WPP_SF_DsD
0x14005e71d  xor     ebx, ebx
0x14005e71f  test    ebp, ebp
0x14005e721  cmovns  ebx, r14d
0x14005e725  xor     ecx, ecx; dwErrCode
0x14005e727  call    cs:__imp_SetLastError
0x14005e72d  mov     eax, ebx
0x14005e72f  add     rsp, 38h
0x14005e733  pop     r15
0x14005e735  pop     r14
0x14005e737  pop     rdi
0x14005e738  pop     rsi
0x14005e739  pop     rbp
0x14005e73a  pop     rbx
0x14005e73b  retn
```
