# CRdpWindowTracker::STATIC_EnumWindowsProc(HWND__ *,__int64)

- ea: `0x14005ea80`
- end: `0x14005ebc7`
- name: `?STATIC_EnumWindowsProc@CRdpWindowTracker@@CAHPEAUHWND__@@_J@Z`
- size: `327`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140004b1c`
- `0x140005750`
- `0x14005ea80`
- `0x14005ebd0`
- `0x14005ef5c`

## import_xrefs

- `USER32!IsWindowVisible` at `0x14005eaa3`
- `USER32!IsWindowVisible` at `0x14005eaa3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005ebb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005ebb6`
- `GDI32!CombineRgn` at `0x14005eb47`
- `GDI32!CombineRgn` at `0x14005eb47`
- `dwmapi!DwmGetWindowAttribute` at `0x14005eac4`
- `dwmapi!DwmGetWindowAttribute` at `0x14005eac4`

## string_xrefs

- `0x14005eb87`: `CombineRgn() failed`

## pseudocode

```c
__int64 __fastcall CRdpWindowTracker::STATIC_EnumWindowsProc(HWND a1, __int64 a2)
{
  int WindowRegionOrBounds; // edi
  int v5; // ebp
  unsigned int v6; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v8; // ebx
  int pvAttribute; // [rsp+60h] [rbp+8h] BYREF

  WindowRegionOrBounds = 0;
  if ( *(HWND *)(a2 + 8) == a1 )
  {
    v5 = 0;
  }
  else
  {
    v5 = 1;
    if ( IsWindowVisible(a1) )
    {
      pvAttribute = 0;
      DwmGetWindowAttribute(a1, 0xEu, &pvAttribute, 4u);
      if ( !pvAttribute && !(unsigned int)CRdpWindowTracker::ShouldIgnoreLayeredWindow(a1) )
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
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                66,
                (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
                CurrentThreadActivityIdPrefix,
                (__int64)"CombineRgn() failed",
                -2147467259);
            }
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            65,
            (unsigned int)&WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
            v6,
            (__int64)"GetWindowRegionOrBounds() failed",
            WindowRegionOrBounds);
        }
      }
    }
  }
  v8 = 0;
  if ( WindowRegionOrBounds >= 0 )
    v8 = v5;
  SetLastError(0);
  return v8;
}

```

## disassembly

```asm
0x14005ea80  push    rbx
0x14005ea82  push    rbp
0x14005ea83  push    rsi
0x14005ea84  push    rdi
0x14005ea85  sub     rsp, 38h
0x14005ea89  xor     edi, edi
0x14005ea8b  mov     rsi, rdx
0x14005ea8e  mov     rbx, rcx
0x14005ea91  cmp     [rdx+8], rcx
0x14005ea95  jnz     short loc_14005EA9E
0x14005ea97  xor     ebp, ebp
0x14005ea99  jmp     loc_14005EBAD
0x14005ea9e  mov     ebp, 1
0x14005eaa3  call    cs:__imp_IsWindowVisible
0x14005eaa9  test    eax, eax
0x14005eaab  jz      loc_14005EBAD
0x14005eab1  lea     r9d, [rbp+3]; cbAttribute
0x14005eab5  mov     [rsp+58h+pvAttribute], edi
0x14005eab9  lea     r8, [rsp+58h+pvAttribute]; pvAttribute
0x14005eabe  mov     rcx, rbx; hwnd
0x14005eac1  lea     edx, [rbp+0Dh]; dwAttribute
0x14005eac4  call    cs:__imp_DwmGetWindowAttribute
0x14005eaca  cmp     [rsp+58h+pvAttribute], edi
0x14005eace  jnz     loc_14005EBAD
0x14005ead4  mov     rcx, rbx; hWnd
0x14005ead7  call    ?ShouldIgnoreLayeredWindow@CRdpWindowTracker@@CAHPEAUHWND__@@@Z; CRdpWindowTracker::ShouldIgnoreLayeredWindow(HWND__ *)
0x14005eadc  test    eax, eax
0x14005eade  jnz     loc_14005EBAD
0x14005eae4  mov     rdx, [rsi+18h]; hrgn
0x14005eae8  mov     rcx, rbx; hWnd
0x14005eaeb  call    ?STATIC_GetWindowRegionOrBounds@CRdpWindowTracker@@CAJPEAUHWND__@@PEAUHRGN__@@@Z; CRdpWindowTracker::STATIC_GetWindowRegionOrBounds(HWND__ *,HRGN__ *)
0x14005eaf0  mov     edi, eax
0x14005eaf2  test    eax, eax
0x14005eaf4  jns     short loc_14005EB36
0x14005eaf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005eafd  lea     rdx, WPP_GLOBAL_Control
0x14005eb04  cmp     rcx, rdx
0x14005eb07  jz      loc_14005EBAD
0x14005eb0d  test    byte ptr [rcx+1Ch], 8
0x14005eb11  jz      loc_14005EBAD
0x14005eb17  cmp     byte ptr [rcx+19h], 2
0x14005eb1b  jb      loc_14005EBAD
0x14005eb21  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005eb26  lea     edx, [rbp+40h]
0x14005eb29  mov     [rsp+58h+var_30], edi
0x14005eb2d  lea     rcx, aGetwindowregio; "GetWindowRegionOrBounds() failed"
0x14005eb34  jmp     short loc_14005EB8E
0x14005eb36  mov     rcx, [rsi+10h]; hrgnDst
0x14005eb3a  mov     r9d, 4; iMode
0x14005eb40  mov     r8, [rsi+18h]; hrgnSrc2
0x14005eb44  mov     rdx, rcx; hrgnSrc1
0x14005eb47  call    cs:__imp_CombineRgn
0x14005eb4d  test    eax, eax
0x14005eb4f  jnz     short loc_14005EBAD
0x14005eb51  mov     edi, 80004005h
0x14005eb56  mov     rax, cs:WPP_GLOBAL_Control
0x14005eb5d  lea     rdx, WPP_GLOBAL_Control
0x14005eb64  cmp     rax, rdx
0x14005eb67  jz      short loc_14005EBAD
0x14005eb69  test    byte ptr [rax+1Ch], 8
0x14005eb6d  jz      short loc_14005EBAD
0x14005eb6f  cmp     byte ptr [rax+19h], 2
0x14005eb73  jb      short loc_14005EBAD
0x14005eb75  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005eb7a  mov     edx, 42h ; 'B'
0x14005eb7f  mov     [rsp+58h+var_30], 80004005h
0x14005eb87  lea     rcx, aCombinergnFail; "CombineRgn() failed"
0x14005eb8e  mov     [rsp+58h+var_38], rcx
0x14005eb93  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005eb9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005eba1  mov     r9d, eax
0x14005eba4  mov     rcx, [rcx+10h]
0x14005eba8  call    WPP_SF_DsD
0x14005ebad  xor     ebx, ebx
0x14005ebaf  test    edi, edi
0x14005ebb1  cmovns  ebx, ebp
0x14005ebb4  xor     ecx, ecx; dwErrCode
0x14005ebb6  call    cs:__imp_SetLastError
0x14005ebbc  mov     eax, ebx
0x14005ebbe  add     rsp, 38h
0x14005ebc2  pop     rdi
0x14005ebc3  pop     rsi
0x14005ebc4  pop     rbp
0x14005ebc5  pop     rbx
0x14005ebc6  retn
```
