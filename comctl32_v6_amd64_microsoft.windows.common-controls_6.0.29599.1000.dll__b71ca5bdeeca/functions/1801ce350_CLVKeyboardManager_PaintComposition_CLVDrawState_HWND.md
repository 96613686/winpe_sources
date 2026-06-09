# CLVKeyboardManager::PaintComposition(CLVDrawState *,HWND__ *)

- ea: `0x1801ce350`
- end: `0x1801ce55c`
- name: `?PaintComposition@CLVKeyboardManager@@QEAAXPEAVCLVDrawState@@PEAUHWND__@@@Z`
- size: `524`
- prototype: `void(CLVKeyboardManager *__hidden this, struct CLVDrawState *, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180075b60`

## callees

- `0x180114520`
- `0x1801cddd8`
- `0x1801ce350`

## import_xrefs

- `USER32!GetPropW` at `0x1801ce406`
- `USER32!GetPropW` at `0x1801ce406`
- `USER32!GetDC` at `0x1801ce451`
- `USER32!GetDC` at `0x1801ce451`
- `USER32!SendMessageW` at `0x1801ce41d`
- `USER32!SendMessageW` at `0x1801ce484`
- `USER32!SendMessageW` at `0x1801ce498`
- `USER32!SendMessageW` at `0x1801ce4af`
- `USER32!SendMessageW` at `0x1801ce41d`
- `USER32!SendMessageW` at `0x1801ce484`
- `USER32!SendMessageW` at `0x1801ce498`
- `USER32!SendMessageW` at `0x1801ce4af`
- `USER32!ValidateRect` at `0x1801ce52b`
- `USER32!ValidateRect` at `0x1801ce52b`
- `USER32!ReleaseDC` at `0x1801ce520`
- `USER32!ReleaseDC` at `0x1801ce520`
- `USER32!GetWindowTextLengthW` at `0x1801ce42d`
- `USER32!GetWindowTextLengthW` at `0x1801ce42d`
- `IMM32!ImmGetContext` at `0x1801ce398`
- `IMM32!ImmGetContext` at `0x1801ce398`
- `IMM32!ImmReleaseContext` at `0x1801ce3e6`
- `IMM32!ImmReleaseContext` at `0x1801ce3e6`
- `IMM32!ImmGetCompositionStringW` at `0x1801ce3bf`
- `IMM32!ImmGetCompositionStringW` at `0x1801ce3da`
- `IMM32!ImmGetCompositionStringW` at `0x1801ce3bf`
- `IMM32!ImmGetCompositionStringW` at `0x1801ce3da`

## string_xrefs

- `0x1801ce3fc`: `IMECompPos`

## pseudocode

```c
void __fastcall CLVKeyboardManager::PaintComposition(CLVKeyboardManager *this, HFONT *a2, HWND a3)
{
  HIMC Context; // rax
  HIMC v7; // rbx
  LONG CompositionStringW; // ebp
  unsigned int PropW; // edi
  signed int v10; // r14d
  int v11; // ebx
  int v12; // edi
  HDC DC; // r12
  unsigned __int64 v14; // rbx
  signed int v15; // edi
  signed int v16; // ebp
  int v17; // eax
  int v18; // ebx
  signed int v19; // ebx
  BOOL v20; // eax
  unsigned __int16 Buf[136]; // [rsp+50h] [rbp-268h] BYREF
  unsigned __int8 v22[272]; // [rsp+160h] [rbp-158h] BYREF

  if ( (*(_DWORD *)(*(_QWORD *)this + 168LL) & 0x8000) == 0 )
  {
    Context = ImmGetContext(a3);
    v7 = Context;
    if ( Context )
    {
      CompositionStringW = ImmGetCompositionStringW(Context, 8u, Buf, 0x104u);
      ImmGetCompositionStringW(v7, 0x10u, v22, 0x104u);
      ImmReleaseContext(a3, v7);
      if ( CompositionStringW > 0 && (unsigned int)CompositionStringW <= 0x104 )
      {
        PropW = (unsigned int)GetPropW(a3, L"IMECompPos");
        v10 = (unsigned __int16)PropW;
        v11 = SendMessageW(a3, 0xD5u, 0, 0);
        v12 = 2 * (v11 + HIWORD(PropW) - (unsigned __int16)PropW - GetWindowTextLengthW(a3));
        if ( CompositionStringW < v12 )
          v12 = CompositionStringW;
        *(unsigned __int16 *)((char *)Buf + v12) = 0;
        DC = GetDC(a3);
        if ( DC )
        {
          v14 = (unsigned __int64)v12 >> 1;
          v15 = v10;
          v16 = v14 + v10;
          if ( v10 < (int)v14 + v10 )
          {
            do
            {
              v17 = SendMessageW(a3, 0xC9u, v15, 0);
              v18 = SendMessageW(a3, 0xBBu, v17, 0);
              v19 = SendMessageW(a3, 0xC1u, v18, 0) + v18;
              if ( v19 <= v16 )
              {
                if ( v19 <= v15 )
                  break;
              }
              else
              {
                v19 = v16;
              }
              v20 = (*(_BYTE *)(*(_QWORD *)this + 832LL) & 1) != 0 || *(_DWORD *)(*(_QWORD *)this + 48LL);
              DrawCompositionLine(a3, DC, a2[5], Buf, v22, v15, v19, v10, v20);
              v15 = v19;
            }
            while ( v19 < v16 );
          }
          ReleaseDC(a3, DC);
          ValidateRect(a3, 0);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1801ce350  mov     [rsp+arg_0], rbx
0x1801ce355  push    rbp
0x1801ce356  push    rsi
0x1801ce357  push    rdi
0x1801ce358  push    r12
0x1801ce35a  push    r13
0x1801ce35c  push    r14
0x1801ce35e  push    r15
0x1801ce360  sub     rsp, 280h
0x1801ce367  mov     rax, cs:__security_cookie
0x1801ce36e  xor     rax, rsp
0x1801ce371  mov     [rsp+2B8h+var_48], rax
0x1801ce379  mov     rax, [rcx]
0x1801ce37c  mov     rsi, r8
0x1801ce37f  mov     r13, rdx
0x1801ce382  mov     r15, rcx
0x1801ce385  test    dword ptr [rax+0A8h], 8000h
0x1801ce38f  jnz     loc_1801CE531
0x1801ce395  mov     rcx, r8; HWND
0x1801ce398  call    cs:__imp_ImmGetContext
0x1801ce39e  mov     rbx, rax
0x1801ce3a1  test    rax, rax
0x1801ce3a4  jz      loc_1801CE531
0x1801ce3aa  mov     edi, 104h
0x1801ce3af  lea     r8, [rsp+2B8h+Buf]; lpBuf
0x1801ce3b4  mov     r9d, edi; dwBufLen
0x1801ce3b7  mov     edx, 8; DWORD
0x1801ce3bc  mov     rcx, rax; HIMC
0x1801ce3bf  call    cs:__imp_ImmGetCompositionStringW
0x1801ce3c5  mov     r9d, edi; dwBufLen
0x1801ce3c8  lea     r8, [rsp+2B8h+var_158]; lpBuf
0x1801ce3d0  mov     edx, 10h; DWORD
0x1801ce3d5  mov     rcx, rbx; HIMC
0x1801ce3d8  mov     ebp, eax
0x1801ce3da  call    cs:__imp_ImmGetCompositionStringW
0x1801ce3e0  mov     rdx, rbx; HIMC
0x1801ce3e3  mov     rcx, rsi; HWND
0x1801ce3e6  call    cs:__imp_ImmReleaseContext
0x1801ce3ec  test    ebp, ebp
0x1801ce3ee  jle     loc_1801CE531
0x1801ce3f4  cmp     ebp, edi
0x1801ce3f6  ja      loc_1801CE531
0x1801ce3fc  lea     rdx, ?s_szIMECompPos@CLVKeyboardManager@@1QBGB; "IMECompPos"
0x1801ce403  mov     rcx, rsi; hWnd
0x1801ce406  call    cs:__imp_GetPropW
0x1801ce40c  xor     r9d, r9d; lParam
0x1801ce40f  xor     r8d, r8d; wParam
0x1801ce412  mov     edx, 0D5h; Msg
0x1801ce417  mov     rcx, rsi; hWnd
0x1801ce41a  mov     rdi, rax
0x1801ce41d  call    cs:__imp_SendMessageW
0x1801ce423  mov     rcx, rsi; hWnd
0x1801ce426  movzx   r14d, di
0x1801ce42a  mov     rbx, rax
0x1801ce42d  call    cs:__imp_GetWindowTextLengthW
0x1801ce433  shr     edi, 10h
0x1801ce436  mov     rcx, rsi; hWnd
0x1801ce439  sub     edi, r14d
0x1801ce43c  add     edi, ebx
0x1801ce43e  sub     edi, eax
0x1801ce440  add     edi, edi
0x1801ce442  cmp     ebp, edi
0x1801ce444  cmovl   edi, ebp
0x1801ce447  xor     eax, eax
0x1801ce449  movsxd  rbx, edi
0x1801ce44c  mov     [rsp+rbx+2B8h+Buf], ax
0x1801ce451  call    cs:__imp_GetDC
0x1801ce457  mov     r12, rax
0x1801ce45a  test    rax, rax
0x1801ce45d  jz      loc_1801CE531
0x1801ce463  shr     rbx, 1
0x1801ce466  mov     edi, r14d
0x1801ce469  lea     ebp, [rbx+r14]
0x1801ce46d  cmp     r14d, ebp
0x1801ce470  jge     loc_1801CE51A
0x1801ce476  movsxd  r8, edi; wParam
0x1801ce479  xor     r9d, r9d; lParam
0x1801ce47c  mov     edx, 0C9h; Msg
0x1801ce481  mov     rcx, rsi; hWnd
0x1801ce484  call    cs:__imp_SendMessageW
0x1801ce48a  movsxd  r8, eax; wParam
0x1801ce48d  xor     r9d, r9d; lParam
0x1801ce490  mov     edx, 0BBh; Msg
0x1801ce495  mov     rcx, rsi; hWnd
0x1801ce498  call    cs:__imp_SendMessageW
0x1801ce49e  movsxd  r8, eax; wParam
0x1801ce4a1  xor     r9d, r9d; lParam
0x1801ce4a4  mov     edx, 0C1h; Msg
0x1801ce4a9  mov     rcx, rsi; hWnd
0x1801ce4ac  mov     rbx, rax
0x1801ce4af  call    cs:__imp_SendMessageW
0x1801ce4b5  add     ebx, eax
0x1801ce4b7  cmp     ebx, ebp
0x1801ce4b9  jle     short loc_1801CE4BF
0x1801ce4bb  mov     ebx, ebp
0x1801ce4bd  jmp     short loc_1801CE4C3
0x1801ce4bf  cmp     ebx, edi
0x1801ce4c1  jle     short loc_1801CE51A
0x1801ce4c3  mov     rax, [r15]
0x1801ce4c6  test    byte ptr [rax+340h], 1
0x1801ce4cd  jnz     short loc_1801CE4D9
0x1801ce4cf  cmp     dword ptr [rax+30h], 0
0x1801ce4d3  jnz     short loc_1801CE4D9
0x1801ce4d5  xor     eax, eax
0x1801ce4d7  jmp     short loc_1801CE4DE
0x1801ce4d9  mov     eax, 1
0x1801ce4de  mov     r8, [r13+28h]; HFONT
0x1801ce4e2  lea     r9, [rsp+2B8h+Buf]; unsigned __int16 *
0x1801ce4e7  mov     [rsp+2B8h+var_278], eax; int
0x1801ce4eb  mov     rdx, r12; HDC
0x1801ce4ee  mov     [rsp+2B8h+var_280], r14d; unsigned int
0x1801ce4f3  lea     rax, [rsp+2B8h+var_158]
0x1801ce4fb  mov     [rsp+2B8h+var_288], ebx; unsigned int
0x1801ce4ff  mov     rcx, rsi; HWND
0x1801ce502  mov     [rsp+2B8h+var_290], edi; unsigned int
0x1801ce506  mov     [rsp+2B8h+var_298], rax; unsigned __int8 *
0x1801ce50b  call    ?DrawCompositionLine@@YAXPEAUHWND__@@PEAUHDC__@@PEAUHFONT__@@PEBGPEBEIIIH@Z; DrawCompositionLine(HWND__ *,HDC__ *,HFONT__ *,ushort const *,uchar const *,uint,uint,uint,int)
0x1801ce510  mov     edi, ebx
0x1801ce512  cmp     ebx, ebp
0x1801ce514  jl      loc_1801CE476
0x1801ce51a  mov     rdx, r12; hDC
0x1801ce51d  mov     rcx, rsi; hWnd
0x1801ce520  call    cs:__imp_ReleaseDC
0x1801ce526  xor     edx, edx; lpRect
0x1801ce528  mov     rcx, rsi; hWnd
0x1801ce52b  call    cs:__imp_ValidateRect
0x1801ce531  mov     rcx, [rsp+2B8h+var_48]
0x1801ce539  xor     rcx, rsp; StackCookie
0x1801ce53c  call    __security_check_cookie
0x1801ce541  mov     rbx, [rsp+2B8h+arg_0]
0x1801ce549  add     rsp, 280h
0x1801ce550  pop     r15
0x1801ce552  pop     r14
0x1801ce554  pop     r13
0x1801ce556  pop     r12
0x1801ce558  pop     rdi
0x1801ce559  pop     rsi
0x1801ce55a  pop     rbp
0x1801ce55b  retn
```
