# CRdpGeometryHelper::STATIC_EnumWindowsProc(HWND__ *,__int64)

- ea: `0x14005e910`
- end: `0x14005ea6e`
- name: `?STATIC_EnumWindowsProc@CRdpGeometryHelper@@SAHPEAUHWND__@@_J@Z`
- size: `350`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140004b1c`
- `0x140032c8c`
- `0x14005e910`
- `0x14005fef4`
- `0x14006a120`

## import_xrefs

- `USER32!GetWindowTextLengthW` at `0x14005e966`
- `USER32!GetWindowTextLengthW` at `0x14005e966`
- `USER32!GetWindowRect` at `0x14005e9cf`
- `USER32!GetWindowRect` at `0x14005e9cf`
- `USER32!IsWindowVisible` at `0x14005e955`
- `USER32!IsWindowVisible` at `0x14005e955`
- `USER32!GetWindowTextW` at `0x14005e986`
- `USER32!GetWindowTextW` at `0x14005e986`
- `USER32!IsWindow` at `0x14005e944`
- `USER32!IsWindow` at `0x14005e944`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14005e9b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14005e9b8`

## pseudocode

```c
__int64 __fastcall CRdpGeometryHelper::STATIC_EnumWindowsProc(HWND a1, __int64 a2)
{
  unsigned int v4; // esi
  int WindowTextLengthW; // eax
  WPP_RECTS *v6; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v8; // edx
  int v9; // r8d
  struct tagRECT v10; // xmm0
  struct tagRECT v12; // [rsp+30h] [rbp-2D8h] BYREF
  struct tagRECT Rect; // [rsp+40h] [rbp-2C8h] BYREF
  wchar_t Buffer[72]; // [rsp+50h] [rbp-2B8h] BYREF
  WCHAR String[256]; // [rsp+E0h] [rbp-228h] BYREF

  Rect = 0;
  v4 = 1;
  if ( IsWindow(a1) )
  {
    if ( IsWindowVisible(a1) )
    {
      WindowTextLengthW = GetWindowTextLengthW(a1);
      if ( WindowTextLengthW < 256
        && GetWindowTextW(a1, String, WindowTextLengthW + 1)
        && CompareStringW(0x409u, 1u, L"Start menu", -1, String, -1) == 2
        && GetWindowRect(a1, &Rect) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v12 = Rect;
          v6 = WPP_RECTS::WPP_RECTS(Buffer, &v12);
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dq_RECTS_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v8,
            v9,
            CurrentThreadActivityIdPrefix,
            (_DWORD)a1,
            (__int64)v6);
        }
        v10 = Rect;
        *(_DWORD *)(a2 + 56) = 1;
        v4 = 0;
        *(struct tagRECT *)(a2 + 60) = v10;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14005e910  mov     [rsp+arg_10], rbx
0x14005e915  push    rbp
0x14005e916  push    rsi
0x14005e917  push    rdi
0x14005e918  sub     rsp, 2F0h
0x14005e91f  mov     rax, cs:__security_cookie
0x14005e926  xor     rax, rsp
0x14005e929  mov     [rsp+308h+var_28], rax
0x14005e931  xorps   xmm0, xmm0
0x14005e934  mov     rbp, rdx
0x14005e937  movups  xmmword ptr [rsp+308h+Rect.left], xmm0
0x14005e93c  mov     rdi, rcx
0x14005e93f  mov     esi, 1
0x14005e944  call    cs:__imp_IsWindow
0x14005e94a  test    eax, eax
0x14005e94c  jz      loc_14005EA49
0x14005e952  mov     rcx, rdi; hWnd
0x14005e955  call    cs:__imp_IsWindowVisible
0x14005e95b  test    eax, eax
0x14005e95d  jz      loc_14005EA49
0x14005e963  mov     rcx, rdi; hWnd
0x14005e966  call    cs:__imp_GetWindowTextLengthW
0x14005e96c  cmp     eax, 100h
0x14005e971  jge     loc_14005EA49
0x14005e977  lea     r8d, [rax+1]; nMaxCount
0x14005e97b  mov     rcx, rdi; hWnd
0x14005e97e  lea     rdx, [rsp+308h+String]; lpString
0x14005e986  call    cs:__imp_GetWindowTextW
0x14005e98c  test    eax, eax
0x14005e98e  jz      loc_14005EA49
0x14005e994  or      r9d, 0FFFFFFFFh; cchCount1
0x14005e998  lea     rax, [rsp+308h+String]
0x14005e9a0  mov     [rsp+308h+cchCount2], r9d; cchCount2
0x14005e9a5  lea     r8, aStartMenu; "Start menu"
0x14005e9ac  mov     edx, esi; dwCmpFlags
0x14005e9ae  mov     [rsp+308h+lpString2], rax; lpString2
0x14005e9b3  mov     ecx, 409h; Locale
0x14005e9b8  call    cs:__imp_CompareStringW
0x14005e9be  cmp     eax, 2
0x14005e9c1  jnz     loc_14005EA49
0x14005e9c7  lea     rdx, [rsp+308h+Rect]; lpRect
0x14005e9cc  mov     rcx, rdi; hWnd
0x14005e9cf  call    cs:__imp_GetWindowRect
0x14005e9d5  test    eax, eax
0x14005e9d7  jz      short loc_14005EA49
0x14005e9d9  mov     rax, cs:WPP_GLOBAL_Control
0x14005e9e0  lea     rcx, WPP_GLOBAL_Control
0x14005e9e7  cmp     rax, rcx
0x14005e9ea  jz      short loc_14005EA3A
0x14005e9ec  test    dword ptr [rax+1Ch], 200h
0x14005e9f3  jz      short loc_14005EA3A
0x14005e9f5  cmp     byte ptr [rax+19h], 5
0x14005e9f9  jb      short loc_14005EA3A
0x14005e9fb  movaps  xmm0, xmmword ptr [rsp+308h+Rect.left]
0x14005ea00  lea     rdx, [rsp+308h+var_2D8]; struct tagRECT
0x14005ea05  lea     rcx, [rsp+308h+Buffer]; Buffer
0x14005ea0a  movdqa  xmmword ptr [rsp+308h+var_2D8.left], xmm0
0x14005ea10  call    ??0WPP_RECTS@@QEAA@UtagRECT@@@Z; WPP_RECTS::WPP_RECTS(tagRECT)
0x14005ea15  mov     rbx, rax
0x14005ea18  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ea1d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ea24  mov     r9d, eax
0x14005ea27  mov     qword ptr [rsp+308h+cchCount2], rbx
0x14005ea2c  mov     [rsp+308h+lpString2], rdi
0x14005ea31  mov     rcx, [rcx+10h]
0x14005ea35  call    WPP_SF_Dq_RECTS_
0x14005ea3a  movaps  xmm0, xmmword ptr [rsp+308h+Rect.left]
0x14005ea3f  mov     [rbp+38h], esi
0x14005ea42  xor     esi, esi
0x14005ea44  movdqu  xmmword ptr [rbp+3Ch], xmm0
0x14005ea49  mov     eax, esi
0x14005ea4b  mov     rcx, [rsp+308h+var_28]
0x14005ea53  xor     rcx, rsp; StackCookie
0x14005ea56  call    __security_check_cookie
0x14005ea5b  mov     rbx, [rsp+308h+arg_10]
0x14005ea63  add     rsp, 2F0h
0x14005ea6a  pop     rdi
0x14005ea6b  pop     rsi
0x14005ea6c  pop     rbp
0x14005ea6d  retn
```
