# CPhishingActionBar::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800708a0`
- end: `0x180070c82`
- name: `?WndProc@CPhishingActionBar@@QEAA_JPEAUHWND__@@I_K_J@Z`
- size: `994`
- prototype: `__int64(CPhishingActionBar *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180071930`

## callees

- `0x18002a2b8`
- `0x18002a2e4`
- `0x18002a354`
- `0x1800708a0`
- `0x1800713ec`
- `0x1800c85d8`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!PszAllocW` at `0x180070b8c`
- `MSOERT2!PszAllocW` at `0x180070b8c`
- `GDI32!DeleteObject` at `0x180070c0b`
- `GDI32!DeleteObject` at `0x180070c0b`
- `GDI32!SetBkColor` at `0x180070974`
- `GDI32!SetBkColor` at `0x180070bcf`
- `GDI32!SetBkColor` at `0x180070974`
- `GDI32!SetBkColor` at `0x180070bcf`
- `GDI32!SetTextColor` at `0x180070be6`
- `GDI32!SetTextColor` at `0x180070be6`
- `GDI32!CreateSolidBrush` at `0x18007094a`
- `GDI32!CreateSolidBrush` at `0x180070bee`
- `GDI32!CreateSolidBrush` at `0x18007094a`
- `GDI32!CreateSolidBrush` at `0x180070bee`
- `USER32!GetWindowTextW` at `0x180070bbe`
- `USER32!GetWindowTextW` at `0x180070bbe`
- `USER32!DrawTextW` at `0x180070c27`
- `USER32!DrawTextW` at `0x180070c27`
- `USER32!GetClientRect` at `0x180070bad`
- `USER32!GetClientRect` at `0x180070bad`
- `USER32!DefWindowProcA` at `0x180070c56`
- `USER32!DefWindowProcA` at `0x180070c56`
- `USER32!UpdateWindow` at `0x180070af1`
- `USER32!UpdateWindow` at `0x180070af1`
- `USER32!GetScrollInfo` at `0x1800709ac`
- `USER32!GetScrollInfo` at `0x1800709ac`
- `USER32!FillRect` at `0x180070c02`
- `USER32!FillRect` at `0x180070c02`
- `USER32!GetSysColor` at `0x180070bda`
- `USER32!GetSysColor` at `0x180070bda`
- `USER32!EnableScrollBar` at `0x180070a8a`
- `USER32!EnableScrollBar` at `0x180070aba`
- `USER32!EnableScrollBar` at `0x180070a8a`
- `USER32!EnableScrollBar` at `0x180070aba`
- `USER32!ScrollWindow` at `0x180070ad4`
- `USER32!ScrollWindow` at `0x180070ad4`
- `USER32!SetScrollPos` at `0x180070ae8`
- `USER32!SetScrollPos` at `0x180070ae8`
- `USER32!GetWindowTextLengthW` at `0x180070b79`
- `USER32!GetWindowTextLengthW` at `0x180070b79`

## pseudocode

```c
__int64 __fastcall CPhishingActionBar::WndProc(CPhishingActionBar *this, HWND a2, UINT a3, HDC a4, LPARAM lParam)
{
  int v8; // esi
  int nPage; // edi
  int nTrackPos; // ebx
  UINT v11; // r8d
  __int64 v12; // rcx
  void (*v13)(void); // rax
  __int64 v14; // rcx
  int WindowTextLengthW; // eax
  int v16; // esi
  WCHAR *v17; // r14
  HWND v18; // rcx
  COLORREF SysColor; // eax
  HBRUSH SolidBrush; // rbx
  int lpClipRect; // [rsp+20h] [rbp-48h]
  struct tagSCROLLINFO v22; // [rsp+30h] [rbp-38h] BYREF

  if ( a3 == 5 )
  {
    CPhishingActionBar::_OnSize(this, a2, 5u, (__int16)lParam, lpClipRect);
    return 0;
  }
  if ( a3 != 43 )
  {
    if ( a3 == 78 )
    {
      if ( *(_DWORD *)(lParam + 16) != -2 || *((_QWORD *)this + 8) != *(_QWORD *)lParam )
        return DefWindowProcA(a2, a3, (WPARAM)a4, lParam);
      ShowHelp(L"mshelp://windows/?id=e4875666-8c43-4db5-ab0f-2eb7377ae330");
      return 0;
    }
    if ( a3 != 273 )
    {
      if ( a3 != 276 )
      {
        if ( a3 == 309 || a3 == 312 )
        {
          if ( dword_1800F3828 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                             + (unsigned int)tls_index)
                                           + 4LL) )
          {
            Init_thread_header(&dword_1800F3828);
            if ( dword_1800F3828 == -1 )
            {
              qword_1800F3830 = (__int64)CreateSolidBrush(0xB9AEFFu);
              atexit(CPhishingActionBar::WndProc_::_21_::_dynamic_atexit_destructor_for__hbrBK__);
              Init_thread_footer(&dword_1800F3828);
            }
          }
          SetBkColor(a4, 0xB9AEFFu);
          return qword_1800F3830;
        }
        return DefWindowProcA(a2, a3, (WPARAM)a4, lParam);
      }
      v22.cbSize = 28;
      v22.fMask = 23;
      memset(&v22.nMin, 0, 20);
      GetScrollInfo(a2, 0, &v22);
      v8 = v22.nMax - v22.nPage;
      if ( (_WORD)a4 )
      {
        if ( (unsigned __int16)a4 == 1 )
        {
          if ( v22.nPos < v8 )
          {
            nPage = -10;
            nTrackPos = v22.nPos + 10;
            goto LABEL_38;
          }
        }
        else
        {
          switch ( (unsigned __int16)a4 )
          {
            case 2u:
              if ( v22.nPos <= 0 )
                return 0;
              nPage = v22.nPage;
              nTrackPos = v22.nPos - v22.nPage;
              break;
            case 3u:
              if ( v22.nPos >= v8 )
                return 0;
              nTrackPos = v22.nPos + v22.nPage;
              nPage = -v22.nPage;
              break;
            case 4u:
            case 5u:
              nTrackPos = v22.nTrackPos;
              if ( v22.nTrackPos > v8 + 1 || v22.nTrackPos < v22.nMin )
                return 0;
              nPage = v22.nPos - v22.nTrackPos;
              break;
            case 6u:
              nPage = 0;
              if ( v22.nPos > 0 )
                nPage = v22.nPos;
              nTrackPos = 0;
              break;
            default:
              if ( (unsigned __int16)a4 != 7 || v22.nPos >= v8 )
                return 0;
              nPage = v22.nPos - v8;
              nTrackPos = v22.nMax - v22.nPage;
              break;
          }
          if ( nPage )
          {
LABEL_38:
            EnableScrollBar(a2, 0, 0);
            if ( nTrackPos <= v8 )
            {
              if ( nTrackPos > v22.nMin )
              {
LABEL_43:
                ScrollWindow(a2, nPage, 0, 0, 0);
                SetScrollPos(a2, 0, nTrackPos, 1);
                UpdateWindow(a2);
                return 0;
              }
              v11 = 1;
              nPage += nTrackPos - v22.nMin;
              nTrackPos = v22.nMin;
            }
            else
            {
              v11 = 2;
              nPage += nTrackPos - v8;
              nTrackPos = v8;
            }
            EnableScrollBar(a2, 0, v11);
            goto LABEL_43;
          }
        }
      }
      else if ( v22.nPos > 0 )
      {
        nPage = 10;
        nTrackPos = v22.nPos - 10;
        goto LABEL_38;
      }
      return 0;
    }
    if ( lParam == *((_QWORD *)this + 9) )
    {
      v12 = *((_QWORD *)this + 14);
      if ( !v12 )
        return 0;
      v13 = *(void (**)(void))(*(_QWORD *)v12 + 24LL);
    }
    else
    {
      if ( lParam != *((_QWORD *)this + 10) )
        return DefWindowProcA(a2, a3, (WPARAM)a4, lParam);
      v14 = *((_QWORD *)this + 14);
      if ( !v14 )
        return 0;
      v13 = *(void (**)(void))(*(_QWORD *)v14 + 32LL);
    }
    v13();
    return 0;
  }
  if ( *(_QWORD *)(lParam + 24) != *((_QWORD *)this + 7) )
    return DefWindowProcA(a2, a3, (WPARAM)a4, lParam);
  WindowTextLengthW = GetWindowTextLengthW(*(HWND *)(lParam + 24));
  v16 = WindowTextLengthW;
  if ( WindowTextLengthW )
  {
    v17 = (WCHAR *)PszAllocW((unsigned int)(WindowTextLengthW + 1));
    if ( v17 )
    {
      v18 = *(HWND *)(lParam + 24);
      *(_OWORD *)&v22.cbSize = 0;
      GetClientRect(v18, (LPRECT)&v22);
      GetWindowTextW(*(HWND *)(lParam + 24), v17, v16 + 1);
      SetBkColor(*(HDC *)(lParam + 32), 0xB9AEFFu);
      SysColor = GetSysColor(23);
      SetTextColor(*(HDC *)(lParam + 32), SysColor);
      SolidBrush = CreateSolidBrush(0xB9AEFFu);
      FillRect(*(HDC *)(lParam + 32), (const RECT *)&v22, SolidBrush);
      DeleteObject(SolidBrush);
      DrawTextW(*(HDC *)(lParam + 32), v17, v16, (LPRECT)&v22, 0x10u);
      ((void (__fastcall *)(LPMALLOC, WCHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v17);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800708a0  push    rbp
0x1800708a2  push    rbx
0x1800708a3  push    rsi
0x1800708a4  push    rdi
0x1800708a5  push    r14
0x1800708a7  push    r15
0x1800708a9  mov     rbp, rsp
0x1800708ac  sub     rsp, 68h
0x1800708b0  mov     rax, cs:__security_cookie
0x1800708b7  xor     rax, rsp
0x1800708ba  mov     [rbp+var_18], rax
0x1800708be  mov     rdi, [rbp+lParam]
0x1800708c2  mov     eax, r8d
0x1800708c5  mov     r15, r9
0x1800708c8  mov     r10d, r8d
0x1800708cb  mov     r14, rdx
0x1800708ce  sub     eax, 5
0x1800708d1  jz      loc_180070C5E
0x1800708d7  sub     eax, 26h ; '&'
0x1800708da  jz      loc_180070B68
0x1800708e0  sub     eax, 23h ; '#'
0x1800708e3  jz      loc_180070B40
0x1800708e9  sub     eax, 0C3h
0x1800708ee  jz      loc_180070AFC
0x1800708f4  sub     eax, 3
0x1800708f7  jz      loc_180070986
0x1800708fd  sub     eax, 21h ; '!'
0x180070900  jz      short loc_18007090B
0x180070902  cmp     eax, 3
0x180070905  jnz     loc_180070C4A
0x18007090b  mov     ecx, cs:_tls_index
0x180070911  mov     ebx, 0B9AEFFh
0x180070916  mov     rax, gs:58h
0x18007091f  mov     edx, 4
0x180070924  mov     rax, [rax+rcx*8]
0x180070928  mov     eax, [rdx+rax]
0x18007092b  cmp     cs:dword_1800F3828, eax
0x180070931  jle     short loc_18007096F
0x180070933  lea     rcx, dword_1800F3828
0x18007093a  call    _Init_thread_header
0x18007093f  cmp     cs:dword_1800F3828, 0FFFFFFFFh
0x180070946  jnz     short loc_18007096F
0x180070948  mov     ecx, ebx; color
0x18007094a  call    cs:__imp_CreateSolidBrush
0x180070950  lea     rcx, _CPhishingActionBar__WndProc____21____dynamic_atexit_destructor_for__hbrBK__; void (__cdecl *)()
0x180070957  mov     cs:qword_1800F3830, rax
0x18007095e  call    atexit
0x180070963  lea     rcx, dword_1800F3828
0x18007096a  call    _Init_thread_footer
0x18007096f  mov     edx, ebx; color
0x180070971  mov     rcx, r15; hdc
0x180070974  call    cs:__imp_SetBkColor
0x18007097a  mov     rax, cs:qword_1800F3830
0x180070981  jmp     loc_180070C69
0x180070986  xorps   xmm0, xmm0
0x180070989  mov     [rbp+var_38.nTrackPos], 0
0x180070990  lea     r8, [rbp+var_38]; lpsi
0x180070994  mov     [rbp+var_38.cbSize], 1Ch
0x18007099b  xor     edx, edx; nBar
0x18007099d  mov     [rbp+var_38.fMask], 17h
0x1800709a4  mov     rcx, r14; hwnd
0x1800709a7  movdqu  xmmword ptr [rbp+var_38.nMin], xmm0
0x1800709ac  call    cs:__imp_GetScrollInfo
0x1800709b2  mov     esi, [rbp+var_38.nMax]
0x1800709b5  mov     edx, [rbp+var_38.nPage]
0x1800709b8  sub     esi, edx
0x1800709ba  movzx   ecx, r15w
0x1800709be  test    ecx, ecx
0x1800709c0  jz      loc_180070A6F
0x1800709c6  sub     ecx, 1
0x1800709c9  jz      loc_180070A5A
0x1800709cf  sub     ecx, 1
0x1800709d2  jz      short loc_180070A41
0x1800709d4  sub     ecx, 1
0x1800709d7  jz      short loc_180070A2D
0x1800709d9  sub     ecx, 1
0x1800709dc  jz      short loc_180070A0F
0x1800709de  sub     ecx, 1
0x1800709e1  jz      short loc_180070A0F
0x1800709e3  sub     ecx, 1
0x1800709e6  jz      short loc_180070A02
0x1800709e8  cmp     ecx, 1
0x1800709eb  jnz     loc_180070C67
0x1800709f1  mov     edi, [rbp+var_38.nPos]
0x1800709f4  cmp     edi, esi
0x1800709f6  jge     loc_180070C67
0x1800709fc  sub     edi, esi
0x1800709fe  mov     ebx, esi
0x180070a00  jmp     short loc_180070A50
0x180070a02  xor     edi, edi
0x180070a04  cmp     [rbp+var_38.nPos], edi
0x180070a07  cmovg   edi, [rbp+var_38.nPos]
0x180070a0b  xor     ebx, ebx
0x180070a0d  jmp     short loc_180070A50
0x180070a0f  mov     ebx, [rbp+var_38.nTrackPos]
0x180070a12  lea     eax, [rsi+1]
0x180070a15  cmp     ebx, eax
0x180070a17  jg      loc_180070C67
0x180070a1d  cmp     ebx, [rbp+var_38.nMin]
0x180070a20  jl      loc_180070C67
0x180070a26  mov     edi, [rbp+var_38.nPos]
0x180070a29  sub     edi, ebx
0x180070a2b  jmp     short loc_180070A50
0x180070a2d  mov     eax, [rbp+var_38.nPos]
0x180070a30  cmp     eax, esi
0x180070a32  jge     loc_180070C67
0x180070a38  mov     edi, edx
0x180070a3a  lea     ebx, [rax+rdx]
0x180070a3d  neg     edi
0x180070a3f  jmp     short loc_180070A50
0x180070a41  mov     ebx, [rbp+var_38.nPos]
0x180070a44  test    ebx, ebx
0x180070a46  jle     loc_180070C67
0x180070a4c  mov     edi, edx
0x180070a4e  sub     ebx, edx
0x180070a50  test    edi, edi
0x180070a52  jz      loc_180070C67
0x180070a58  jmp     short loc_180070A82
0x180070a5a  mov     ebx, [rbp+var_38.nPos]
0x180070a5d  cmp     ebx, esi
0x180070a5f  jge     loc_180070C67
0x180070a65  mov     edi, 0FFFFFFF6h
0x180070a6a  add     ebx, 0Ah
0x180070a6d  jmp     short loc_180070A82
0x180070a6f  mov     ebx, [rbp+var_38.nPos]
0x180070a72  test    ebx, ebx
0x180070a74  jle     loc_180070C67
0x180070a7a  mov     edi, 0Ah
0x180070a7f  add     ebx, 0FFFFFFF6h
0x180070a82  xor     r8d, r8d; wArrows
0x180070a85  xor     edx, edx; wSBflags
0x180070a87  mov     rcx, r14; hWnd
0x180070a8a  call    cs:__imp_EnableScrollBar
0x180070a90  cmp     ebx, esi
0x180070a92  jle     short loc_180070AA2
0x180070a94  sub     ebx, esi
0x180070a96  mov     r8d, 2
0x180070a9c  add     edi, ebx
0x180070a9e  mov     ebx, esi
0x180070aa0  jmp     short loc_180070AB5
0x180070aa2  mov     eax, [rbp+var_38.nMin]
0x180070aa5  cmp     ebx, eax
0x180070aa7  jg      short loc_180070AC0
0x180070aa9  sub     ebx, eax
0x180070aab  mov     r8d, 1; wArrows
0x180070ab1  add     edi, ebx
0x180070ab3  mov     ebx, eax
0x180070ab5  xor     edx, edx; wSBflags
0x180070ab7  mov     rcx, r14; hWnd
0x180070aba  call    cs:__imp_EnableScrollBar
0x180070ac0  xor     r9d, r9d; lpRect
0x180070ac3  mov     qword ptr [rsp+68h+lpClipRect], 0; lpClipRect
0x180070acc  xor     r8d, r8d; YAmount
0x180070acf  mov     edx, edi; XAmount
0x180070ad1  mov     rcx, r14; hWnd
0x180070ad4  call    cs:__imp_ScrollWindow
0x180070ada  mov     r9d, 1; bRedraw
0x180070ae0  mov     r8d, ebx; nPos
0x180070ae3  xor     edx, edx; nBar
0x180070ae5  mov     rcx, r14; hWnd
0x180070ae8  call    cs:__imp_SetScrollPos
0x180070aee  mov     rcx, r14; hWnd
0x180070af1  call    cs:__imp_UpdateWindow
0x180070af7  jmp     loc_180070C67
0x180070afc  cmp     rdi, [rcx+48h]
0x180070b00  jnz     short loc_180070B18
0x180070b02  mov     rcx, [rcx+70h]
0x180070b06  test    rcx, rcx
0x180070b09  jz      loc_180070C67
0x180070b0f  mov     rax, [rcx]
0x180070b12  mov     rax, [rax+18h]
0x180070b16  jmp     short loc_180070B36
0x180070b18  cmp     rdi, [rcx+50h]
0x180070b1c  jnz     loc_180070C4A
0x180070b22  mov     rcx, [rcx+70h]
0x180070b26  test    rcx, rcx
0x180070b29  jz      loc_180070C67
0x180070b2f  mov     rax, [rcx]
0x180070b32  mov     rax, [rax+20h]
0x180070b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070b3b  jmp     loc_180070C67
0x180070b40  cmp     dword ptr [rdi+10h], 0FFFFFFFEh
0x180070b44  jnz     loc_180070C4A
0x180070b4a  mov     rax, [rdi]
0x180070b4d  cmp     [rcx+40h], rax
0x180070b51  jnz     loc_180070C4A
0x180070b57  lea     rcx, c_wszPhishingHelpTopic; "mshelp://windows/?id=e4875666-8c43-4db5"...
0x180070b5e  call    ShowHelp
0x180070b63  jmp     loc_180070C67
0x180070b68  mov     rax, [rdi+18h]
0x180070b6c  cmp     rax, [rcx+38h]
0x180070b70  jnz     loc_180070C4A
0x180070b76  mov     rcx, rax; hWnd
0x180070b79  call    cs:__imp_GetWindowTextLengthW
0x180070b7f  mov     esi, eax
0x180070b81  test    eax, eax
0x180070b83  jz      loc_180070C43
0x180070b89  lea     ecx, [rax+1]
0x180070b8c  call    cs:__imp_PszAllocW
0x180070b92  mov     r14, rax
0x180070b95  test    rax, rax
0x180070b98  jz      loc_180070C43
0x180070b9e  mov     rcx, [rdi+18h]; hWnd
0x180070ba2  lea     rdx, [rbp+var_38]; lpRect
0x180070ba6  xorps   xmm0, xmm0
0x180070ba9  movups  xmmword ptr [rbp+var_38.cbSize], xmm0
0x180070bad  call    cs:__imp_GetClientRect
0x180070bb3  mov     rcx, [rdi+18h]; hWnd
0x180070bb7  lea     r8d, [rsi+1]; nMaxCount
0x180070bbb  mov     rdx, r14; lpString
0x180070bbe  call    cs:__imp_GetWindowTextW
0x180070bc4  mov     rcx, [rdi+20h]; hdc
0x180070bc8  mov     ebx, 0B9AEFFh
0x180070bcd  mov     edx, ebx; color
0x180070bcf  call    cs:__imp_SetBkColor
0x180070bd5  mov     ecx, 17h; nIndex
0x180070bda  call    cs:__imp_GetSysColor
0x180070be0  mov     rcx, [rdi+20h]; hdc
0x180070be4  mov     edx, eax; color
0x180070be6  call    cs:__imp_SetTextColor
0x180070bec  mov     ecx, ebx; color
0x180070bee  call    cs:__imp_CreateSolidBrush
0x180070bf4  mov     rcx, [rdi+20h]; hDC
0x180070bf8  lea     rdx, [rbp+var_38]; lprc
0x180070bfc  mov     r8, rax; hbr
0x180070bff  mov     rbx, rax
0x180070c02  call    cs:__imp_FillRect
0x180070c08  mov     rcx, rbx; ho
0x180070c0b  call    cs:__imp_DeleteObject
0x180070c11  mov     rcx, [rdi+20h]; hdc
0x180070c15  lea     r9, [rbp+var_38]; lprc
0x180070c19  mov     r8d, esi; cchText
0x180070c1c  mov     [rsp+68h+lpClipRect], 10h; format
0x180070c24  mov     rdx, r14; lpchText
0x180070c27  call    cs:__imp_DrawTextW
0x180070c2d  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180070c34  mov     rdx, r14
0x180070c37  mov     rax, [rcx]
0x180070c3a  mov     rax, [rax+28h]
0x180070c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070c43  mov     eax, 1
0x180070c48  jmp     short loc_180070C69
0x180070c4a  mov     r9, rdi; lParam
0x180070c4d  mov     r8, r15; wParam
0x180070c50  mov     edx, r10d; Msg
0x180070c53  mov     rcx, r14; hWnd
0x180070c56  call    cs:__imp_DefWindowProcA
0x180070c5c  jmp     short loc_180070C69
0x180070c5e  movsx   r9d, di; int
0x180070c62  call    ?_OnSize@CPhishingActionBar@@AEAAXPEAUHWND__@@IHH@Z; CPhishingActionBar::_OnSize(HWND__ *,uint,int,int)
0x180070c67  xor     eax, eax
0x180070c69  mov     rcx, [rbp+var_18]
0x180070c6d  xor     rcx, rsp; StackCookie
0x180070c70  call    __security_check_cookie
0x180070c75  add     rsp, 68h
0x180070c79  pop     r15
0x180070c7b  pop     r14
0x180070c7d  pop     rdi
0x180070c7e  pop     rsi
0x180070c7f  pop     rbx
0x180070c80  pop     rbp
0x180070c81  retn
```
