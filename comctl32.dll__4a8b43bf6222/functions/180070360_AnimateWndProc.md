# AnimateWndProc

- ea: `0x180070360`
- end: `0x180070730`
- name: `AnimateWndProc`
- size: `976`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800115f0`
- `0x18001a590`
- `0x180070360`
- `0x180070738`
- `0x180070b54`
- `0x180070bf4`
- `0x180070d30`
- `0x180070e14`
- `0x18008ea60`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18007053a`
- `KERNEL32!LocalFree` at `0x18007053a`
- `KERNEL32!LocalAlloc` at `0x180070680`
- `KERNEL32!LocalAlloc` at `0x180070680`
- `KERNEL32!MultiByteToWideChar` at `0x180070616`
- `KERNEL32!MultiByteToWideChar` at `0x180070616`
- `KERNEL32!InitializeCriticalSection` at `0x1800706b4`
- `KERNEL32!InitializeCriticalSection` at `0x1800706b4`
- `KERNEL32!DeleteCriticalSection` at `0x180070531`
- `KERNEL32!DeleteCriticalSection` at `0x180070531`
- `USER32!GetClientRect` at `0x18007044e`
- `USER32!GetClientRect` at `0x18007044e`
- `USER32!SendMessageW` at `0x18007043d`
- `USER32!SendMessageW` at `0x180070527`
- `USER32!SendMessageW` at `0x1800706f9`
- `USER32!SendMessageW` at `0x18007043d`
- `USER32!SendMessageW` at `0x180070527`
- `USER32!SendMessageW` at `0x1800706f9`
- `USER32!SetWindowLongPtrW` at `0x180070548`
- `USER32!SetWindowLongPtrW` at `0x1800706c2`
- `USER32!SetWindowLongPtrW` at `0x180070548`
- `USER32!SetWindowLongPtrW` at `0x1800706c2`
- `USER32!InvalidateRect` at `0x18007050e`
- `USER32!InvalidateRect` at `0x18007050e`
- `USER32!FillRect` at `0x18007045f`
- `USER32!FillRect` at `0x18007045f`
- `USER32!GetWindowLongPtrW` at `0x18007038f`
- `USER32!GetWindowLongPtrW` at `0x18007038f`
- `USER32!BeginPaint` at `0x1800704a0`
- `USER32!BeginPaint` at `0x1800704a0`
- `USER32!EndPaint` at `0x1800704b9`
- `USER32!EndPaint` at `0x1800704b9`
- `USER32!DefWindowProcW` at `0x18007070a`
- `USER32!DefWindowProcW` at `0x18007070a`
- `USER32!SetTimer` at `0x180070585`
- `USER32!SetTimer` at `0x180070585`
- `USER32!OffsetRect` at `0x1800704ff`
- `USER32!OffsetRect` at `0x1800704ff`

## pseudocode

```c
LRESULT __fastcall AnimateWndProc(
        struct _RTL_CRITICAL_SECTION_DEBUG *hWnd,
        UINT Msg,
        HMODULE wParam,
        unsigned __int64 lParam)
{
  LONG_PTR WindowLongPtrW; // rdi
  HWND v9; // r9
  HWND v10; // rcx
  HBRUSH v11; // rbx
  LRESULT result; // rax
  HDC v13; // rax
  int v14; // eax
  UINT v15; // r8d
  WCHAR *v16; // r8
  WCHAR *v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // rax
  LONG_PTR v19; // rdi
  struct tagRECT Rect; // [rsp+30h] [rbp-2B8h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+40h] [rbp-2A8h] BYREF
  WCHAR WideCharStr[264]; // [rsp+90h] [rbp-258h] BYREF

  WindowLongPtrW = GetWindowLongPtrW((HWND)hWnd, 0);
  memset(&Paint, 0, sizeof(Paint));
  switch ( Msg )
  {
    case 0x10u:
      SendMessageW((HWND)hWnd, 0x466u, 0, 0);
      return DefWindowProcW((HWND)hWnd, Msg, (WPARAM)wParam, lParam);
    case 0x3Du:
      if ( (_DWORD)lParam == -12 )
        return 65550;
      return DefWindowProcW((HWND)hWnd, Msg, (WPARAM)wParam, lParam);
    case 0x81u:
      v18 = (struct _RTL_CRITICAL_SECTION *)LocalAlloc(0x40u, 0x88u);
      v19 = (LONG_PTR)v18;
      if ( !v18 )
        return 0;
      v18->DebugInfo = hWnd;
      v18->OwningThread = *(HANDLE *)(lParam + 24);
      v18->LockCount = *(_DWORD *)(lParam + 16);
      HIDWORD(v18->LockSemaphore) = 1;
      LODWORD(v18->LockSemaphore) = *(_DWORD *)(lParam + 48);
      InitializeCriticalSection(v18 + 1);
      SetWindowLongPtrW((HWND)hWnd, 0, v19);
      SetWindowBits((HWND)hWnd, -20);
      return DefWindowProcW((HWND)hWnd, Msg, (WPARAM)wParam, lParam);
    case 0x84u:
      return -1;
  }
  if ( WindowLongPtrW )
  {
    if ( Msg <= 0x113 )
    {
      switch ( Msg )
      {
        case 0x113u:
          v14 = HandleTick(WindowLongPtrW);
          if ( v14 )
          {
            v15 = *(_DWORD *)(WindowLongPtrW + 100);
            if ( v14 < 0 )
              v15 += 4000;
            *(_QWORD *)(WindowLongPtrW + 120) = SetTimer(*(HWND *)WindowLongPtrW, 0x2Au, v15, 0);
          }
          else
          {
            HandleStop(WindowLongPtrW);
          }
          break;
        case 2u:
          SendMessageW((HWND)hWnd, 0x467u, 0, 0);
          DeleteCriticalSection((LPCRITICAL_SECTION)(WindowLongPtrW + 40));
          LocalFree((HLOCAL)WindowLongPtrW);
          SetWindowLongPtrW((HWND)hWnd, 0, 0);
          break;
        case 5u:
          if ( (*(_BYTE *)(WindowLongPtrW + 24) & 1) != 0 )
          {
            OffsetRect(
              (LPRECT)(WindowLongPtrW + 80),
              (*(_DWORD *)(WindowLongPtrW + 80) + (unsigned __int16)lParam - *(_DWORD *)(WindowLongPtrW + 88)) / 2
            - *(_DWORD *)(WindowLongPtrW + 80),
              (*(_DWORD *)(WindowLongPtrW + 84) + WORD1(lParam) - *(_DWORD *)(WindowLongPtrW + 92)) / 2
            - *(_DWORD *)(WindowLongPtrW + 84));
            InvalidateRect((HWND)hWnd, 0, 1);
          }
          break;
        case 0xFu:
          if ( *(_DWORD *)(WindowLongPtrW + 28) )
          {
            *(_DWORD *)(WindowLongPtrW + 28) = 0;
            if ( !*(_DWORD *)(WindowLongPtrW + 96) && (*(_DWORD *)(WindowLongPtrW + 24) & 0x40000000) != 0 )
              HandleOpen(WindowLongPtrW, 0, 0, 42);
          }
          v13 = BeginPaint((HWND)hWnd, &Paint);
          HandlePaint(WindowLongPtrW, v13);
          EndPaint((HWND)hWnd, &Paint);
          return 0;
        case 0x14u:
          v9 = *(HWND *)WindowLongPtrW;
          v10 = *(HWND *)(WindowLongPtrW + 16);
          Rect = 0;
          v11 = (HBRUSH)SendMessageW(v10, 0x138u, (WPARAM)wParam, (LPARAM)v9);
          GetClientRect(*(HWND *)WindowLongPtrW, &Rect);
          FillRect((HDC)wParam, &Rect, v11);
          return 1;
        case 0x7Du:
          if ( wParam == (HMODULE)-16LL )
            *(_DWORD *)(WindowLongPtrW + 24) = *(_DWORD *)(lParam + 4);
          return 0;
      }
      return DefWindowProcW((HWND)hWnd, Msg, (WPARAM)wParam, lParam);
    }
    switch ( Msg )
    {
      case 0x318u:
        if ( *(_DWORD *)(WindowLongPtrW + 28) )
        {
          *(_DWORD *)(WindowLongPtrW + 28) = 0;
          if ( !*(_DWORD *)(WindowLongPtrW + 96) && (*(_DWORD *)(WindowLongPtrW + 24) & 0x40000000) != 0 )
            HandleOpen(WindowLongPtrW, 0, 0, 42);
        }
        HandlePaint(WindowLongPtrW, wParam);
        return 0;
      case 0x464u:
        if ( lParam < 0x10000 )
        {
          v17 = (WCHAR *)lParam;
        }
        else
        {
          v17 = WideCharStr;
          MultiByteToWideChar(0, 0, (LPCCH)lParam, -1, WideCharStr, 260);
        }
        v16 = v17;
        goto LABEL_41;
      case 0x465u:
        LODWORD(result) = HandlePlay((unsigned __int16 *)WindowLongPtrW, (__int16)lParam, SWORD1(lParam), (int)wParam);
        break;
      case 0x466u:
        LODWORD(result) = HandleStop(WindowLongPtrW);
        break;
      case 0x467u:
        v16 = (WCHAR *)lParam;
LABEL_41:
        LODWORD(result) = HandleOpen(WindowLongPtrW, wParam, v16, 0);
        return (int)result;
      default:
        return DefWindowProcW((HWND)hWnd, Msg, (WPARAM)wParam, lParam);
    }
    return (int)result;
  }
  return DefWindowProcW((HWND)hWnd, Msg, (WPARAM)wParam, lParam);
}

```

## disassembly

```asm
0x180070360  push    rbx
0x180070362  push    rbp
0x180070363  push    rsi
0x180070364  push    rdi
0x180070365  push    r14
0x180070367  push    r15
0x180070369  sub     rsp, 2B8h
0x180070370  mov     rax, cs:__security_cookie
0x180070377  xor     rax, rsp
0x18007037a  mov     [rsp+2E8h+var_48], rax
0x180070382  mov     ebp, edx
0x180070384  mov     rsi, r9
0x180070387  xor     edx, edx; nIndex
0x180070389  mov     r15, r8
0x18007038c  mov     r14, rcx
0x18007038f  call    cs:__imp_GetWindowLongPtrW
0x180070395  xor     edx, edx; Val
0x180070397  lea     rcx, [rsp+2E8h+Paint]; void *
0x18007039c  mov     rdi, rax
0x18007039f  lea     r8d, [rdx+48h]; Size
0x1800703a3  call    memset
0x1800703a8  mov     eax, ebp
0x1800703aa  sub     eax, 10h
0x1800703ad  jz      loc_1800706EB
0x1800703b3  sub     eax, 2Dh ; '-'
0x1800703b6  jz      loc_1800706DF
0x1800703bc  sub     eax, 44h ; 'D'
0x1800703bf  jz      loc_180070678
0x1800703c5  cmp     eax, 3
0x1800703c8  jz      loc_18007066F
0x1800703ce  xor     ebx, ebx
0x1800703d0  test    rdi, rdi
0x1800703d3  jz      loc_1800706FF
0x1800703d9  mov     eax, 113h
0x1800703de  cmp     ebp, eax
0x1800703e0  ja      loc_180070594
0x1800703e6  jz      loc_180070553
0x1800703ec  cmp     ebp, 2
0x1800703ef  jz      loc_180070519
0x1800703f5  cmp     ebp, 5
0x1800703f8  jz      loc_1800704C4
0x1800703fe  cmp     ebp, 0Fh
0x180070401  jz      short loc_18007046F
0x180070403  cmp     ebp, 14h
0x180070406  jz      short loc_180070426
0x180070408  cmp     ebp, 7Dh ; '}'
0x18007040b  jnz     loc_1800706FF
0x180070411  cmp     r15, 0FFFFFFFFFFFFFFF0h
0x180070415  jnz     loc_18007068E
0x18007041b  mov     eax, [rsi+4]
0x18007041e  mov     [rdi+18h], eax
0x180070421  jmp     loc_18007068E
0x180070426  mov     r9, [rdi]; lParam
0x180070429  xorps   xmm0, xmm0
0x18007042c  mov     rcx, [rdi+10h]; hWnd
0x180070430  mov     r8, r15; wParam
0x180070433  mov     edx, 138h; Msg
0x180070438  movups  xmmword ptr [rsp+2E8h+Rect.left], xmm0
0x18007043d  call    cs:__imp_SendMessageW
0x180070443  mov     rcx, [rdi]; hWnd
0x180070446  lea     rdx, [rsp+2E8h+Rect]; lpRect
0x18007044b  mov     rbx, rax
0x18007044e  call    cs:__imp_GetClientRect
0x180070454  mov     r8, rbx; hbr
0x180070457  lea     rdx, [rsp+2E8h+Rect]; lprc
0x18007045c  mov     rcx, r15; hDC
0x18007045f  call    cs:__imp_FillRect
0x180070465  mov     eax, 1
0x18007046a  jmp     loc_180070710
0x18007046f  cmp     [rdi+1Ch], ebx
0x180070472  jz      short loc_180070498
0x180070474  mov     [rdi+1Ch], ebx
0x180070477  cmp     [rdi+60h], ebx
0x18007047a  jnz     short loc_180070498
0x18007047c  test    dword ptr [rdi+18h], 40000000h
0x180070483  jz      short loc_180070498
0x180070485  mov     r9d, 2Ah ; '*'
0x18007048b  xor     r8d, r8d
0x18007048e  xor     edx, edx
0x180070490  mov     rcx, rdi
0x180070493  call    HandleOpen
0x180070498  lea     rdx, [rsp+2E8h+Paint]; lpPaint
0x18007049d  mov     rcx, r14; hWnd
0x1800704a0  call    cs:__imp_BeginPaint
0x1800704a6  mov     rdx, rax
0x1800704a9  mov     rcx, rdi
0x1800704ac  call    HandlePaint
0x1800704b1  lea     rdx, [rsp+2E8h+Paint]; lpPaint
0x1800704b6  mov     rcx, r14; hWnd
0x1800704b9  call    cs:__imp_EndPaint
0x1800704bf  jmp     loc_18007068E
0x1800704c4  test    byte ptr [rdi+18h], 1
0x1800704c8  jz      loc_1800706FF
0x1800704ce  lea     rcx, [rdi+50h]; lprc
0x1800704d2  mov     rax, rsi
0x1800704d5  shr     rax, 10h
0x1800704d9  movzx   eax, ax
0x1800704dc  sub     eax, [rdi+5Ch]
0x1800704df  add     eax, [rdi+54h]
0x1800704e2  cdq
0x1800704e3  sub     eax, edx
0x1800704e5  sar     eax, 1
0x1800704e7  mov     r8d, eax
0x1800704ea  movzx   eax, si
0x1800704ed  sub     eax, [rdi+58h]
0x1800704f0  add     eax, [rcx]
0x1800704f2  sub     r8d, [rdi+54h]; dy
0x1800704f6  cdq
0x1800704f7  sub     eax, edx
0x1800704f9  sar     eax, 1
0x1800704fb  sub     eax, [rcx]
0x1800704fd  mov     edx, eax; dx
0x1800704ff  call    cs:__imp_OffsetRect
0x180070505  xor     edx, edx; lpRect
0x180070507  mov     rcx, r14; hWnd
0x18007050a  lea     r8d, [rdx+1]; bErase
0x18007050e  call    cs:__imp_InvalidateRect
0x180070514  jmp     loc_1800706FF
0x180070519  xor     r9d, r9d; lParam
0x18007051c  xor     r8d, r8d; wParam
0x18007051f  mov     edx, 467h; Msg
0x180070524  mov     rcx, r14; hWnd
0x180070527  call    cs:__imp_SendMessageW
0x18007052d  lea     rcx, [rdi+28h]; lpCriticalSection
0x180070531  call    cs:__imp_DeleteCriticalSection
0x180070537  mov     rcx, rdi; hMem
0x18007053a  call    cs:__imp_LocalFree
0x180070540  xor     r8d, r8d; dwNewLong
0x180070543  xor     edx, edx; nIndex
0x180070545  mov     rcx, r14; hWnd
0x180070548  call    cs:__imp_SetWindowLongPtrW
0x18007054e  jmp     loc_1800706FF
0x180070553  mov     rcx, rdi
0x180070556  call    HandleTick
0x18007055b  test    eax, eax
0x18007055d  jnz     short loc_18007056C
0x18007055f  mov     rcx, rdi
0x180070562  call    HandleStop
0x180070567  jmp     loc_1800706FF
0x18007056c  mov     r8d, [rdi+64h]
0x180070570  xor     r9d, r9d; lpTimerFunc
0x180070573  mov     rcx, [rdi]; hWnd
0x180070576  lea     edx, [r9+2Ah]; nIDEvent
0x18007057a  test    eax, eax
0x18007057c  jns     short loc_180070585
0x18007057e  add     r8d, 0FA0h; uElapse
0x180070585  call    cs:__imp_SetTimer
0x18007058b  mov     [rdi+78h], rax
0x18007058f  jmp     loc_1800706FF
0x180070594  mov     eax, ebp
0x180070596  sub     eax, 318h
0x18007059b  jz      loc_180070639
0x1800705a1  sub     eax, 14Ch
0x1800705a6  jz      short loc_1800705E5
0x1800705a8  sub     eax, 1
0x1800705ab  jz      short loc_1800705CA
0x1800705ad  sub     eax, 1
0x1800705b0  jz      short loc_1800705C0
0x1800705b2  cmp     eax, 1
0x1800705b5  jnz     loc_1800706FF
0x1800705bb  mov     r8, rsi
0x1800705be  jmp     short loc_180070624
0x1800705c0  mov     rcx, rdi
0x1800705c3  call    HandleStop
0x1800705c8  jmp     short loc_180070632
0x1800705ca  mov     rax, rsi
0x1800705cd  movsx   edx, si
0x1800705d0  shr     rax, 10h
0x1800705d4  mov     r9d, r15d
0x1800705d7  movsx   r8d, ax
0x1800705db  mov     rcx, rdi; lpParameter
0x1800705de  call    HandlePlay
0x1800705e3  jmp     short loc_180070632
0x1800705e5  cmp     rsi, 10000h
0x1800705ec  jb      short loc_18007061E
0x1800705ee  lea     rax, [rsp+2E8h+WideCharStr]
0x1800705f6  mov     [rsp+2E8h+cchWideChar], 104h; cchWideChar
0x1800705fe  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180070602  mov     [rsp+2E8h+lpWideCharStr], rax; lpWideCharStr
0x180070607  mov     r8, rsi; lpMultiByteStr
0x18007060a  lea     rbx, [rsp+2E8h+WideCharStr]
0x180070612  xor     edx, edx; dwFlags
0x180070614  xor     ecx, ecx; CodePage
0x180070616  call    cs:__imp_MultiByteToWideChar
0x18007061c  jmp     short loc_180070621
0x18007061e  mov     rbx, rsi
0x180070621  mov     r8, rbx
0x180070624  xor     r9d, r9d
0x180070627  mov     rdx, r15
0x18007062a  mov     rcx, rdi
0x18007062d  call    HandleOpen
0x180070632  cdqe
0x180070634  jmp     loc_180070710
0x180070639  cmp     [rdi+1Ch], ebx
0x18007063c  jz      short loc_180070662
0x18007063e  mov     [rdi+1Ch], ebx
0x180070641  cmp     [rdi+60h], ebx
0x180070644  jnz     short loc_180070662
0x180070646  test    dword ptr [rdi+18h], 40000000h
0x18007064d  jz      short loc_180070662
0x18007064f  mov     r9d, 2Ah ; '*'
0x180070655  xor     r8d, r8d
0x180070658  xor     edx, edx
0x18007065a  mov     rcx, rdi
0x18007065d  call    HandleOpen
0x180070662  mov     rdx, r15
0x180070665  mov     rcx, rdi
0x180070668  call    HandlePaint
0x18007066d  jmp     short loc_18007068E
0x18007066f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180070673  jmp     loc_180070710
0x180070678  mov     edx, 88h; uBytes
0x18007067d  lea     ecx, [rdx-48h]; uFlags
0x180070680  call    cs:__imp_LocalAlloc
0x180070686  mov     rdi, rax
0x180070689  test    rax, rax
0x18007068c  jnz     short loc_180070692
0x18007068e  xor     eax, eax
0x180070690  jmp     short loc_180070710
0x180070692  mov     [rax], r14
0x180070695  lea     rcx, [rdi+28h]; lpCriticalSection
0x180070699  mov     rax, [rsi+18h]
0x18007069d  mov     [rdi+10h], rax
0x1800706a1  mov     eax, [rsi+10h]
0x1800706a4  mov     [rdi+8], eax
0x1800706a7  mov     dword ptr [rdi+1Ch], 1
0x1800706ae  mov     eax, [rsi+30h]
0x1800706b1  mov     [rdi+18h], eax
0x1800706b4  call    cs:__imp_InitializeCriticalSection
0x1800706ba  mov     r8, rdi; dwNewLong
0x1800706bd  xor     edx, edx; nIndex
0x1800706bf  mov     rcx, r14; hWnd
0x1800706c2  call    cs:__imp_SetWindowLongPtrW
0x1800706c8  xor     r9d, r9d
0x1800706cb  mov     r8d, 400000h
0x1800706d1  mov     rcx, r14; hWnd
0x1800706d4  lea     edx, [r9-14h]; nIndex
0x1800706d8  call    SetWindowBits
0x1800706dd  jmp     short loc_1800706FF
0x1800706df  cmp     esi, 0FFFFFFF4h
0x1800706e2  jnz     short loc_1800706FF
0x1800706e4  mov     eax, 1000Eh
0x1800706e9  jmp     short loc_180070710
0x1800706eb  xor     r9d, r9d; lParam
0x1800706ee  xor     r8d, r8d; wParam
0x1800706f1  mov     edx, 466h; Msg
0x1800706f6  mov     rcx, r14; hWnd
0x1800706f9  call    cs:__imp_SendMessageW
0x1800706ff  mov     r9, rsi; lParam
0x180070702  mov     r8, r15; wParam
0x180070705  mov     edx, ebp; Msg
0x180070707  mov     rcx, r14; hWnd
0x18007070a  call    cs:__imp_DefWindowProcW
0x180070710  mov     rcx, [rsp+2E8h+var_48]
0x180070718  xor     rcx, rsp; StackCookie
0x18007071b  call    __security_check_cookie
0x180070720  add     rsp, 2B8h
0x180070727  pop     r15
0x180070729  pop     r14
0x18007072b  pop     rdi
0x18007072c  pop     rsi
0x18007072d  pop     rbp
0x18007072e  pop     rbx
0x18007072f  retn
```
