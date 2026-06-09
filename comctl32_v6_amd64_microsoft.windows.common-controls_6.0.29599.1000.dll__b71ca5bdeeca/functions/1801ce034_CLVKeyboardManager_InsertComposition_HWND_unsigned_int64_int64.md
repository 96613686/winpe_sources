# CLVKeyboardManager::InsertComposition(HWND__ *,unsigned __int64,__int64)

- ea: `0x1801ce034`
- end: `0x1801ce348`
- name: `?InsertComposition@CLVKeyboardManager@@QEAAXPEAUHWND__@@_K_J@Z`
- size: `788`
- prototype: `void(CLVKeyboardManager *__hidden this, HWND, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180075b60`

## callees

- `0x180077fa4`
- `0x1801ce034`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ce106`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ce155`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ce1b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ce274`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ce106`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ce155`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ce1b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ce274`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ce118`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ce1ca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ce118`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ce1ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801ce163`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801ce282`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801ce163`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801ce282`
- `USER32!GetPropW` at `0x1801ce09e`
- `USER32!GetPropW` at `0x1801ce09e`
- `USER32!RemovePropW` at `0x1801ce173`
- `USER32!RemovePropW` at `0x1801ce296`
- `USER32!RemovePropW` at `0x1801ce173`
- `USER32!RemovePropW` at `0x1801ce296`
- `USER32!SetPropW` at `0x1801ce2c0`
- `USER32!SetPropW` at `0x1801ce2c0`
- `USER32!SetWindowLongPtrW` at `0x1801ce30e`
- `USER32!SetWindowLongPtrW` at `0x1801ce30e`
- `USER32!SendMessageW` at `0x1801ce079`
- `USER32!SendMessageW` at `0x1801ce0b6`
- `USER32!SendMessageW` at `0x1801ce0da`
- `USER32!SendMessageW` at `0x1801ce14f`
- `USER32!SendMessageW` at `0x1801ce187`
- `USER32!SendMessageW` at `0x1801ce1ff`
- `USER32!SendMessageW` at `0x1801ce26e`
- `USER32!SendMessageW` at `0x1801ce2e2`
- `USER32!SendMessageW` at `0x1801ce079`
- `USER32!SendMessageW` at `0x1801ce0b6`
- `USER32!SendMessageW` at `0x1801ce0da`
- `USER32!SendMessageW` at `0x1801ce14f`
- `USER32!SendMessageW` at `0x1801ce187`
- `USER32!SendMessageW` at `0x1801ce1ff`
- `USER32!SendMessageW` at `0x1801ce26e`
- `USER32!SendMessageW` at `0x1801ce2e2`
- `USER32!RedrawWindow` at `0x1801ce2f4`
- `USER32!RedrawWindow` at `0x1801ce2f4`
- `USER32!GetWindowTextLengthW` at `0x1801ce20b`
- `USER32!GetWindowTextLengthW` at `0x1801ce20b`
- `IMM32!ImmGetContext` at `0x1801ce082`
- `IMM32!ImmGetContext` at `0x1801ce082`
- `IMM32!ImmReleaseContext` at `0x1801ce2cc`
- `IMM32!ImmReleaseContext` at `0x1801ce2cc`
- `IMM32!ImmSetCompositionStringW` at `0x1801ce24e`
- `IMM32!ImmSetCompositionStringW` at `0x1801ce24e`
- `IMM32!ImmGetCompositionStringW` at `0x1801ce0f9`
- `IMM32!ImmGetCompositionStringW` at `0x1801ce135`
- `IMM32!ImmGetCompositionStringW` at `0x1801ce1a7`
- `IMM32!ImmGetCompositionStringW` at `0x1801ce1eb`
- `IMM32!ImmGetCompositionStringW` at `0x1801ce0f9`
- `IMM32!ImmGetCompositionStringW` at `0x1801ce135`
- `IMM32!ImmGetCompositionStringW` at `0x1801ce1a7`
- `IMM32!ImmGetCompositionStringW` at `0x1801ce1eb`

## string_xrefs

- `0x1801ce094`: `IMECompPos`
- `0x1801ce169`: `IMECompPos`
- `0x1801ce28c`: `IMECompPos`
- `0x1801ce2b3`: `IMECompPos`

## pseudocode

```c
void __fastcall CLVKeyboardManager::InsertComposition(CLVKeyboardManager *this, HWND a2, __int64 a3, __int16 a4)
{
  int v7; // eax
  HIMC Context; // r15
  unsigned int PropW; // eax
  unsigned int v10; // r12d
  LONG CompositionStringW; // eax
  __int64 v12; // rsi
  HANDLE ProcessHeap; // rax
  char *v14; // rax
  char *v15; // rbx
  HANDLE v16; // rax
  LONG v17; // eax
  __int64 v18; // rsi
  HANDLE v19; // rax
  char *v20; // rax
  char *v21; // r14
  int v22; // ebx
  signed int v23; // ebp
  HANDLE v24; // rax

  v7 = *(_DWORD *)(*(_QWORD *)this + 168LL);
  if ( (v7 & 0x8000) == 0 )
  {
    *(_DWORD *)(*(_QWORD *)this + 168LL) = v7 | 0x8000;
    SendMessageW(a2, 0xBu, 0, 0);
    Context = ImmGetContext(a2);
    if ( Context )
    {
      PropW = (unsigned int)GetPropW(a2, L"IMECompPos");
      if ( PropW )
        v10 = PropW;
      else
        v10 = SendMessageW(a2, 0xB0u, 0, 0);
      SendMessageW(a2, 0xB1u, (__int16)v10, SHIWORD(v10));
      if ( (a4 & 0x800) != 0 )
      {
        CompositionStringW = ImmGetCompositionStringW(Context, 0x800u, 0, 0);
        v12 = CompositionStringW;
        if ( CompositionStringW >= 0 )
        {
          ProcessHeap = GetProcessHeap();
          v14 = (char *)HeapAlloc(ProcessHeap, 8u, v12 + 2);
          v15 = v14;
          if ( v14 )
          {
            ImmGetCompositionStringW(Context, 0x800u, v14, v12 + 2);
            *(_WORD *)&v15[v12] = 0;
            SendMessageW(a2, 0xC2u, 0, (LPARAM)v15);
            v16 = GetProcessHeap();
            HeapFree(v16, 0, v15);
          }
        }
        RemovePropW(a2, L"IMECompPos");
        v10 = SendMessageW(a2, 0xB0u, 0, 0);
      }
      if ( (a4 & 8) != 0 )
      {
        v17 = ImmGetCompositionStringW(Context, 8u, 0, 0);
        v18 = v17;
        if ( v17 < 0 )
          goto LABEL_21;
        v19 = GetProcessHeap();
        v20 = (char *)HeapAlloc(v19, 8u, v18 + 2);
        v21 = v20;
        if ( v20 )
        {
          ImmGetCompositionStringW(Context, 8u, v20, v18 + 2);
          v22 = SendMessageW(a2, 0xD5u, 0, 0);
          v23 = 2 * (v22 + HIWORD(v10) - (unsigned __int16)v10 - GetWindowTextLengthW(a2));
          if ( (int)v18 >= v23 && v23 >= 0 && v23 < (int)v18 )
          {
            *(_WORD *)&v21[v23] = 0;
            ImmSetCompositionStringW(Context, 9u, v21, v23, 0, 0);
            LODWORD(v18) = v23;
          }
          *(_WORD *)&v21[(int)v18] = 0;
          SendMessageW(a2, 0xC2u, 0, (LPARAM)v21);
          v24 = GetProcessHeap();
          HeapFree(v24, 0, v21);
        }
        if ( (_DWORD)v18 )
LABEL_21:
          SetPropW(
            a2,
            L"IMECompPos",
            (HANDLE)((unsigned __int16)v10 | ((unsigned __int16)(v10 + ((unsigned __int64)(int)v18 >> 1)) << 16)));
        else
          RemovePropW(a2, L"IMECompPos");
      }
      ImmReleaseContext(a2, Context);
    }
    SendMessageW(a2, 0xBu, 1u, 0);
    RedrawWindow(a2, 0, 0, 3u);
    SetWindowLongPtrW(**(HWND **)(*(_QWORD *)this + 416LL), -12, 1);
    CLVInPlaceEditingManager::SetEditSize(
      *(CLVInPlaceEditingManager **)(*(_QWORD *)this + 416LL),
      (struct CLVDrawState *)(*(_QWORD *)this + 240LL));
    *(_DWORD *)(*(_QWORD *)this + 168LL) &= ~0x8000u;
  }
}

```

## disassembly

```asm
0x1801ce034  push    rbx
0x1801ce036  push    rbp
0x1801ce037  push    rsi
0x1801ce038  push    rdi
0x1801ce039  push    r12
0x1801ce03b  push    r13
0x1801ce03d  push    r14
0x1801ce03f  push    r15
0x1801ce041  sub     rsp, 38h
0x1801ce045  mov     rdi, rdx
0x1801ce048  mov     r13, rcx
0x1801ce04b  mov     rdx, [rcx]
0x1801ce04e  mov     rbp, r9
0x1801ce051  mov     ecx, 8000h
0x1801ce056  mov     eax, [rdx+0A8h]
0x1801ce05c  test    ecx, eax
0x1801ce05e  jnz     loc_1801CE337
0x1801ce064  or      eax, ecx
0x1801ce066  xor     r9d, r9d; lParam
0x1801ce069  mov     [rdx+0A8h], eax
0x1801ce06f  xor     r8d, r8d; wParam
0x1801ce072  mov     rcx, rdi; hWnd
0x1801ce075  lea     edx, [r9+0Bh]; Msg
0x1801ce079  call    cs:__imp_SendMessageW
0x1801ce07f  mov     rcx, rdi; HWND
0x1801ce082  call    cs:__imp_ImmGetContext
0x1801ce088  mov     r15, rax
0x1801ce08b  test    rax, rax
0x1801ce08e  jz      loc_1801CE2D2
0x1801ce094  lea     rdx, ?s_szIMECompPos@CLVKeyboardManager@@1QBGB; "IMECompPos"
0x1801ce09b  mov     rcx, rdi; hWnd
0x1801ce09e  call    cs:__imp_GetPropW
0x1801ce0a4  test    eax, eax
0x1801ce0a6  jnz     short loc_1801CE0C1
0x1801ce0a8  xor     r9d, r9d; lParam
0x1801ce0ab  xor     r8d, r8d; wParam
0x1801ce0ae  mov     edx, 0B0h; Msg
0x1801ce0b3  mov     rcx, rdi; hWnd
0x1801ce0b6  call    cs:__imp_SendMessageW
0x1801ce0bc  mov     r12, rax
0x1801ce0bf  jmp     short loc_1801CE0C4
0x1801ce0c1  mov     r12d, eax
0x1801ce0c4  mov     eax, r12d
0x1801ce0c7  movsx   r8, r12w; wParam
0x1801ce0cb  shr     eax, 10h
0x1801ce0ce  mov     edx, 0B1h; Msg
0x1801ce0d3  movsx   r9, ax; lParam
0x1801ce0d7  mov     rcx, rdi; hWnd
0x1801ce0da  call    cs:__imp_SendMessageW
0x1801ce0e0  mov     eax, 800h
0x1801ce0e5  test    rax, rbp
0x1801ce0e8  jz      loc_1801CE190
0x1801ce0ee  xor     r9d, r9d; dwBufLen
0x1801ce0f1  xor     r8d, r8d; lpBuf
0x1801ce0f4  mov     edx, eax; DWORD
0x1801ce0f6  mov     rcx, r15; HIMC
0x1801ce0f9  call    cs:__imp_ImmGetCompositionStringW
0x1801ce0ff  movsxd  rsi, eax
0x1801ce102  test    eax, eax
0x1801ce104  js      short loc_1801CE169
0x1801ce106  call    cs:__imp_GetProcessHeap
0x1801ce10c  lea     r8, [rsi+2]; dwBytes
0x1801ce110  mov     edx, 8; dwFlags
0x1801ce115  mov     rcx, rax; hHeap
0x1801ce118  call    cs:__imp_HeapAlloc
0x1801ce11e  mov     rbx, rax
0x1801ce121  test    rax, rax
0x1801ce124  jz      short loc_1801CE169
0x1801ce126  lea     r9d, [rsi+2]; dwBufLen
0x1801ce12a  mov     r8, rax; lpBuf
0x1801ce12d  mov     edx, 800h; DWORD
0x1801ce132  mov     rcx, r15; HIMC
0x1801ce135  call    cs:__imp_ImmGetCompositionStringW
0x1801ce13b  xor     ecx, ecx
0x1801ce13d  mov     r9, rbx; lParam
0x1801ce140  mov     [rsi+rbx], cx
0x1801ce144  xor     r8d, r8d; wParam
0x1801ce147  mov     rcx, rdi; hWnd
0x1801ce14a  mov     edx, 0C2h; Msg
0x1801ce14f  call    cs:__imp_SendMessageW
0x1801ce155  call    cs:__imp_GetProcessHeap
0x1801ce15b  mov     r8, rbx; lpMem
0x1801ce15e  xor     edx, edx; dwFlags
0x1801ce160  mov     rcx, rax; hHeap
0x1801ce163  call    cs:__imp_HeapFree
0x1801ce169  lea     rdx, ?s_szIMECompPos@CLVKeyboardManager@@1QBGB; "IMECompPos"
0x1801ce170  mov     rcx, rdi; hWnd
0x1801ce173  call    cs:__imp_RemovePropW
0x1801ce179  xor     r9d, r9d; lParam
0x1801ce17c  xor     r8d, r8d; wParam
0x1801ce17f  mov     edx, 0B0h; Msg
0x1801ce184  mov     rcx, rdi; hWnd
0x1801ce187  call    cs:__imp_SendMessageW
0x1801ce18d  mov     r12d, eax
0x1801ce190  test    bpl, 8
0x1801ce194  jz      loc_1801CE2C6
0x1801ce19a  xor     r9d, r9d; dwBufLen
0x1801ce19d  xor     r8d, r8d; lpBuf
0x1801ce1a0  mov     rcx, r15; HIMC
0x1801ce1a3  lea     edx, [r9+8]; DWORD
0x1801ce1a7  call    cs:__imp_ImmGetCompositionStringW
0x1801ce1ad  movsxd  rsi, eax
0x1801ce1b0  test    eax, eax
0x1801ce1b2  js      loc_1801CE29E
0x1801ce1b8  call    cs:__imp_GetProcessHeap
0x1801ce1be  lea     r8, [rsi+2]; dwBytes
0x1801ce1c2  mov     edx, 8; dwFlags
0x1801ce1c7  mov     rcx, rax; hHeap
0x1801ce1ca  call    cs:__imp_HeapAlloc
0x1801ce1d0  mov     r14, rax
0x1801ce1d3  test    rax, rax
0x1801ce1d6  jz      loc_1801CE288
0x1801ce1dc  lea     r9d, [rsi+2]; dwBufLen
0x1801ce1e0  mov     r8, rax; lpBuf
0x1801ce1e3  mov     edx, 8; DWORD
0x1801ce1e8  mov     rcx, r15; HIMC
0x1801ce1eb  call    cs:__imp_ImmGetCompositionStringW
0x1801ce1f1  xor     r9d, r9d; lParam
0x1801ce1f4  xor     r8d, r8d; wParam
0x1801ce1f7  mov     edx, 0D5h; Msg
0x1801ce1fc  mov     rcx, rdi; hWnd
0x1801ce1ff  call    cs:__imp_SendMessageW
0x1801ce205  mov     rcx, rdi; hWnd
0x1801ce208  mov     rbx, rax
0x1801ce20b  call    cs:__imp_GetWindowTextLengthW
0x1801ce211  mov     ebp, r12d
0x1801ce214  movzx   ecx, r12w
0x1801ce218  shr     ebp, 10h
0x1801ce21b  sub     ebp, ecx
0x1801ce21d  add     ebp, ebx
0x1801ce21f  sub     ebp, eax
0x1801ce221  add     ebp, ebp
0x1801ce223  cmp     esi, ebp
0x1801ce225  jl      short loc_1801CE256
0x1801ce227  test    ebp, ebp
0x1801ce229  js      short loc_1801CE256
0x1801ce22b  cmp     ebp, esi
0x1801ce22d  jge     short loc_1801CE256
0x1801ce22f  xor     eax, eax
0x1801ce231  movsxd  rcx, ebp
0x1801ce234  mov     [rsp+78h+dwReadLen], eax; dwReadLen
0x1801ce238  mov     r9d, ebp; dwCompLen
0x1801ce23b  mov     r8, r14; lpComp
0x1801ce23e  mov     [rsp+78h+lpRead], rax; lpRead
0x1801ce243  mov     [rcx+r14], ax
0x1801ce248  lea     edx, [rax+9]; dwIndex
0x1801ce24b  mov     rcx, r15; HIMC
0x1801ce24e  call    cs:__imp_ImmSetCompositionStringW
0x1801ce254  mov     esi, ebp
0x1801ce256  movsxd  rcx, esi
0x1801ce259  xor     eax, eax
0x1801ce25b  mov     r9, r14; lParam
0x1801ce25e  xor     r8d, r8d; wParam
0x1801ce261  mov     edx, 0C2h; Msg
0x1801ce266  mov     [rcx+r14], ax
0x1801ce26b  mov     rcx, rdi; hWnd
0x1801ce26e  call    cs:__imp_SendMessageW
0x1801ce274  call    cs:__imp_GetProcessHeap
0x1801ce27a  mov     r8, r14; lpMem
0x1801ce27d  xor     edx, edx; dwFlags
0x1801ce27f  mov     rcx, rax; hHeap
0x1801ce282  call    cs:__imp_HeapFree
0x1801ce288  test    esi, esi
0x1801ce28a  jnz     short loc_1801CE29E
0x1801ce28c  lea     rdx, ?s_szIMECompPos@CLVKeyboardManager@@1QBGB; "IMECompPos"
0x1801ce293  mov     rcx, rdi; hWnd
0x1801ce296  call    cs:__imp_RemovePropW
0x1801ce29c  jmp     short loc_1801CE2C6
0x1801ce29e  movzx   edx, r12w
0x1801ce2a2  movsxd  rax, esi
0x1801ce2a5  shr     rax, 1
0x1801ce2a8  add     ax, dx
0x1801ce2ab  movzx   ecx, ax
0x1801ce2ae  shl     ecx, 10h
0x1801ce2b1  or      ecx, edx
0x1801ce2b3  lea     rdx, ?s_szIMECompPos@CLVKeyboardManager@@1QBGB; "IMECompPos"
0x1801ce2ba  movsxd  r8, ecx; hData
0x1801ce2bd  mov     rcx, rdi; hWnd
0x1801ce2c0  call    cs:__imp_SetPropW
0x1801ce2c6  mov     rdx, r15; HIMC
0x1801ce2c9  mov     rcx, rdi; HWND
0x1801ce2cc  call    cs:__imp_ImmReleaseContext
0x1801ce2d2  xor     r9d, r9d; lParam
0x1801ce2d5  mov     rcx, rdi; hWnd
0x1801ce2d8  lea     ebx, [r9+1]
0x1801ce2dc  mov     r8d, ebx; wParam
0x1801ce2df  lea     edx, [rbx+0Ah]; Msg
0x1801ce2e2  call    cs:__imp_SendMessageW
0x1801ce2e8  lea     r9d, [rbx+2]; flags
0x1801ce2ec  xor     r8d, r8d; hrgnUpdate
0x1801ce2ef  xor     edx, edx; lprcUpdate
0x1801ce2f1  mov     rcx, rdi; hWnd
0x1801ce2f4  call    cs:__imp_RedrawWindow
0x1801ce2fa  mov     rax, [r13+0]
0x1801ce2fe  lea     edx, [rbx-0Dh]; nIndex
0x1801ce301  mov     r8d, ebx; dwNewLong
0x1801ce304  mov     rcx, [rax+1A0h]
0x1801ce30b  mov     rcx, [rcx]; hWnd
0x1801ce30e  call    cs:__imp_SetWindowLongPtrW
0x1801ce314  mov     rcx, [r13+0]
0x1801ce318  lea     rdx, [rcx+0F0h]; struct CLVDrawState *
0x1801ce31f  mov     rcx, [rcx+1A0h]; this
0x1801ce326  call    ?SetEditSize@CLVInPlaceEditingManager@@QEAAXPEAVCLVDrawState@@@Z; CLVInPlaceEditingManager::SetEditSize(CLVDrawState *)
0x1801ce32b  mov     rax, [r13+0]
0x1801ce32f  btr     dword ptr [rax+0A8h], 0Fh
0x1801ce337  add     rsp, 38h
0x1801ce33b  pop     r15
0x1801ce33d  pop     r14
0x1801ce33f  pop     r13
0x1801ce341  pop     r12
0x1801ce343  pop     rdi
0x1801ce344  pop     rsi
0x1801ce345  pop     rbp
0x1801ce346  pop     rbx
0x1801ce347  retn
```
