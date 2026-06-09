# ListView_InsertComposition

- ea: `0x1800753a8`
- end: `0x180075637`
- name: `ListView_InsertComposition`
- size: `655`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180073cc0`

## callees

- `0x1800753a8`
- `0x180076674`
- `0x180077064`
- `0x180090020`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800754a5`
- `KERNEL32!LocalFree` at `0x180075582`
- `KERNEL32!LocalFree` at `0x1800754a5`
- `KERNEL32!LocalFree` at `0x180075582`
- `USER32!SendMessageW` at `0x1800753f0`
- `USER32!SendMessageW` at `0x18007543e`
- `USER32!SendMessageW` at `0x180075460`
- `USER32!SendMessageW` at `0x18007549a`
- `USER32!SendMessageW` at `0x1800754c6`
- `USER32!SendMessageW` at `0x18007550d`
- `USER32!SendMessageW` at `0x180075579`
- `USER32!SendMessageW` at `0x1800755e5`
- `USER32!SendMessageW` at `0x1800753f0`
- `USER32!SendMessageW` at `0x18007543e`
- `USER32!SendMessageW` at `0x180075460`
- `USER32!SendMessageW` at `0x18007549a`
- `USER32!SendMessageW` at `0x1800754c6`
- `USER32!SendMessageW` at `0x18007550d`
- `USER32!SendMessageW` at `0x180075579`
- `USER32!SendMessageW` at `0x1800755e5`
- `USER32!RedrawWindow` at `0x1800755f7`
- `USER32!RedrawWindow` at `0x1800755f7`
- `USER32!SetWindowLongPtrW` at `0x18007560a`
- `USER32!SetWindowLongPtrW` at `0x18007560a`
- `USER32!GetPropW` at `0x180075424`
- `USER32!GetPropW` at `0x180075424`
- `USER32!RemovePropW` at `0x1800754b5`
- `USER32!RemovePropW` at `0x1800755b8`
- `USER32!RemovePropW` at `0x1800754b5`
- `USER32!RemovePropW` at `0x1800755b8`
- `USER32!SetPropW` at `0x1800755a6`
- `USER32!SetPropW` at `0x1800755a6`
- `USER32!GetWindowTextLengthW` at `0x180075519`
- `USER32!GetWindowTextLengthW` at `0x180075519`

## string_xrefs

- `0x18007541a`: `IMECompPos`
- `0x1800754ab`: `IMECompPos`
- `0x180075590`: `IMECompPos`
- `0x1800755ae`: `IMECompPos`

## pseudocode

```c
__int64 __fastcall ListView_InsertComposition(HWND hWnd, LPARAM a2, __int16 a3, __int64 a4)
{
  __int64 result; // rax
  __int64 Context; // r15
  unsigned int PropW; // eax
  unsigned int v10; // esi
  unsigned int CompositionString; // ebp
  int v12; // r12d
  int v13; // ebx
  int WindowTextLengthW; // eax
  int v15; // esi
  void *v16; // rbx
  __int64 v17; // rsi
  LPARAM lParam; // [rsp+78h] [rbp+10h] BYREF

  lParam = a2;
  result = *(unsigned int *)(a4 + 72);
  if ( (result & 0x8000) == 0 )
  {
    *(_DWORD *)(a4 + 72) = result | 0x8000;
    SendMessageW(hWnd, 0xBu, 0, 0);
    if ( g_pfnImmGetContext )
    {
      Context = g_pfnImmGetContext(hWnd);
      if ( Context )
      {
        PropW = (unsigned int)GetPropW(hWnd, L"IMECompPos");
        if ( PropW )
          v10 = PropW;
        else
          v10 = SendMessageW(hWnd, 0xB0u, 0, 0);
        SendMessageW(hWnd, 0xB1u, (__int16)v10, SHIWORD(v10));
        if ( (a3 & 0x800) != 0 )
        {
          lParam = 0;
          if ( (unsigned int)GetCompositionString(Context, 2048, &lParam) )
          {
            SendMessageW(hWnd, 0xC2u, 0, lParam);
            LocalFree((HLOCAL)lParam);
          }
          RemovePropW(hWnd, L"IMECompPos");
          v10 = SendMessageW(hWnd, 0xB0u, 0, 0);
        }
        if ( (a3 & 8) != 0 )
        {
          lParam = 0;
          CompositionString = GetCompositionString(Context, 8, &lParam);
          if ( !CompositionString )
            goto LABEL_19;
          v12 = (unsigned __int16)v10;
          v13 = SendMessageW(hWnd, 0xD5u, 0, 0);
          WindowTextLengthW = GetWindowTextLengthW(hWnd);
          v15 = v13 + HIWORD(v10) - (unsigned __int16)v10;
          v16 = (void *)lParam;
          v17 = (unsigned int)(v15 - WindowTextLengthW);
          if ( CompositionString > (unsigned int)v17 )
          {
            *(_WORD *)(lParam + 2 * v17) = 0;
            if ( g_pfnImmSetCompositionStringW )
              g_pfnImmSetCompositionStringW(Context, 9, v16, (unsigned int)(2 * v17), 0, 0);
            CompositionString = v17;
          }
          SendMessageW(hWnd, 0xC2u, 0, (LPARAM)v16);
          LocalFree(v16);
          if ( CompositionString )
            SetPropW(hWnd, L"IMECompPos", (HANDLE)(v12 | ((unsigned __int16)(v12 + CompositionString) << 16)));
          else
LABEL_19:
            RemovePropW(hWnd, L"IMECompPos");
        }
        if ( g_pfnImmReleaseContext )
          g_pfnImmReleaseContext(hWnd, Context);
      }
    }
    SendMessageW(hWnd, 0xBu, 1u, 0);
    RedrawWindow(hWnd, 0, 0, 3u);
    SetWindowLongPtrW(*(HWND *)(a4 + 328), -12, 1);
    result = ListView_SetEditSize(a4);
    *(_DWORD *)(a4 + 72) &= ~0x8000u;
  }
  return result;
}

```

## disassembly

```asm
0x1800753a8  mov     [rsp+arg_0], rbx
0x1800753ad  mov     [rsp+arg_10], rbp
0x1800753b2  mov     [rsp+lParam], rdx
0x1800753b7  push    rsi
0x1800753b8  push    rdi
0x1800753b9  push    r12
0x1800753bb  push    r14
0x1800753bd  push    r15
0x1800753bf  sub     rsp, 40h
0x1800753c3  mov     eax, [r9+48h]
0x1800753c7  mov     rdi, rcx
0x1800753ca  mov     ecx, 8000h
0x1800753cf  mov     r14, r9
0x1800753d2  mov     rbx, r8
0x1800753d5  test    ecx, eax
0x1800753d7  jnz     loc_18007561E
0x1800753dd  or      eax, ecx
0x1800753df  xor     r8d, r8d; wParam
0x1800753e2  mov     [r9+48h], eax
0x1800753e6  mov     rcx, rdi; hWnd
0x1800753e9  xor     r9d, r9d; lParam
0x1800753ec  lea     edx, [r9+0Bh]; Msg
0x1800753f0  call    cs:__imp_SendMessageW
0x1800753f6  mov     rax, cs:g_pfnImmGetContext
0x1800753fd  test    rax, rax
0x180075400  jz      loc_1800755D5
0x180075406  mov     rcx, rdi
0x180075409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007540e  mov     r15, rax
0x180075411  test    rax, rax
0x180075414  jz      loc_1800755D5
0x18007541a  lea     rdx, aImecomppos; "IMECompPos"
0x180075421  mov     rcx, rdi; hWnd
0x180075424  call    cs:__imp_GetPropW
0x18007542a  mov     ebp, 0B0h
0x18007542f  test    eax, eax
0x180075431  jnz     short loc_180075449
0x180075433  xor     r9d, r9d; lParam
0x180075436  xor     r8d, r8d; wParam
0x180075439  mov     edx, ebp; Msg
0x18007543b  mov     rcx, rdi; hWnd
0x18007543e  call    cs:__imp_SendMessageW
0x180075444  mov     rsi, rax
0x180075447  jmp     short loc_18007544B
0x180075449  mov     esi, eax
0x18007544b  mov     eax, esi
0x18007544d  movsx   r8, si; wParam
0x180075451  shr     eax, 10h
0x180075454  mov     edx, 0B1h; Msg
0x180075459  movsx   r9, ax; lParam
0x18007545d  mov     rcx, rdi; hWnd
0x180075460  call    cs:__imp_SendMessageW
0x180075466  mov     edx, 800h
0x18007546b  test    rdx, rbx
0x18007546e  jz      short loc_1800754CE
0x180075470  lea     r8, [rsp+68h+lParam]
0x180075475  mov     [rsp+68h+lParam], 0
0x18007547e  mov     rcx, r15
0x180075481  call    _GetCompositionString
0x180075486  test    eax, eax
0x180075488  jz      short loc_1800754AB
0x18007548a  mov     r9, [rsp+68h+lParam]; lParam
0x18007548f  xor     r8d, r8d; wParam
0x180075492  mov     edx, 0C2h; Msg
0x180075497  mov     rcx, rdi; hWnd
0x18007549a  call    cs:__imp_SendMessageW
0x1800754a0  mov     rcx, [rsp+68h+lParam]; hMem
0x1800754a5  call    cs:__imp_LocalFree
0x1800754ab  lea     rdx, aImecomppos; "IMECompPos"
0x1800754b2  mov     rcx, rdi; hWnd
0x1800754b5  call    cs:__imp_RemovePropW
0x1800754bb  xor     r9d, r9d; lParam
0x1800754be  xor     r8d, r8d; wParam
0x1800754c1  mov     edx, ebp; Msg
0x1800754c3  mov     rcx, rdi; hWnd
0x1800754c6  call    cs:__imp_SendMessageW
0x1800754cc  mov     esi, eax
0x1800754ce  mov     edx, 8
0x1800754d3  test    dl, bl
0x1800754d5  jz      loc_1800755BE
0x1800754db  lea     r8, [rsp+68h+lParam]
0x1800754e0  mov     [rsp+68h+lParam], 0
0x1800754e9  mov     rcx, r15
0x1800754ec  call    _GetCompositionString
0x1800754f1  mov     ebp, eax
0x1800754f3  test    eax, eax
0x1800754f5  jz      loc_1800755AE
0x1800754fb  xor     r9d, r9d; lParam
0x1800754fe  movzx   r12d, si
0x180075502  xor     r8d, r8d; wParam
0x180075505  mov     edx, 0D5h; Msg
0x18007550a  mov     rcx, rdi; hWnd
0x18007550d  call    cs:__imp_SendMessageW
0x180075513  mov     rcx, rdi; hWnd
0x180075516  mov     rbx, rax
0x180075519  call    cs:__imp_GetWindowTextLengthW
0x18007551f  shr     esi, 10h
0x180075522  sub     esi, r12d
0x180075525  add     esi, ebx
0x180075527  mov     rbx, [rsp+68h+lParam]
0x18007552c  sub     esi, eax
0x18007552e  cmp     ebp, esi
0x180075530  jbe     short loc_18007556B
0x180075532  xor     eax, eax
0x180075534  mov     [rbx+rsi*2], ax
0x180075538  mov     rax, cs:g_pfnImmSetCompositionStringW
0x18007553f  test    rax, rax
0x180075542  jz      short loc_180075569
0x180075544  lea     r9d, [rsi+rsi]
0x180075548  mov     [rsp+68h+var_40], 0
0x180075550  mov     r8, rbx
0x180075553  mov     [rsp+68h+var_48], 0
0x18007555c  mov     edx, 9
0x180075561  mov     rcx, r15
0x180075564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075569  mov     ebp, esi
0x18007556b  mov     r9, rbx; lParam
0x18007556e  xor     r8d, r8d; wParam
0x180075571  mov     edx, 0C2h; Msg
0x180075576  mov     rcx, rdi; hWnd
0x180075579  call    cs:__imp_SendMessageW
0x18007557f  mov     rcx, rbx; hMem
0x180075582  call    cs:__imp_LocalFree
0x180075588  test    ebp, ebp
0x18007558a  jz      short loc_1800755AE
0x18007558c  add     bp, r12w
0x180075590  lea     rdx, aImecomppos; "IMECompPos"
0x180075597  movzx   eax, bp
0x18007559a  mov     rcx, rdi; hWnd
0x18007559d  shl     eax, 10h
0x1800755a0  or      eax, r12d
0x1800755a3  movsxd  r8, eax; hData
0x1800755a6  call    cs:__imp_SetPropW
0x1800755ac  jmp     short loc_1800755BE
0x1800755ae  lea     rdx, aImecomppos; "IMECompPos"
0x1800755b5  mov     rcx, rdi; hWnd
0x1800755b8  call    cs:__imp_RemovePropW
0x1800755be  mov     rax, cs:g_pfnImmReleaseContext
0x1800755c5  test    rax, rax
0x1800755c8  jz      short loc_1800755D5
0x1800755ca  mov     rdx, r15
0x1800755cd  mov     rcx, rdi
0x1800755d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800755d5  xor     r9d, r9d; lParam
0x1800755d8  mov     rcx, rdi; hWnd
0x1800755db  lea     ebx, [r9+1]
0x1800755df  mov     r8d, ebx; wParam
0x1800755e2  lea     edx, [rbx+0Ah]; Msg
0x1800755e5  call    cs:__imp_SendMessageW
0x1800755eb  lea     r9d, [rbx+2]; flags
0x1800755ef  xor     r8d, r8d; hrgnUpdate
0x1800755f2  xor     edx, edx; lprcUpdate
0x1800755f4  mov     rcx, rdi; hWnd
0x1800755f7  call    cs:__imp_RedrawWindow
0x1800755fd  mov     rcx, [r14+148h]; hWnd
0x180075604  lea     edx, [rbx-0Dh]; nIndex
0x180075607  mov     r8d, ebx; dwNewLong
0x18007560a  call    cs:__imp_SetWindowLongPtrW
0x180075610  mov     rcx, r14; int
0x180075613  call    ListView_SetEditSize
0x180075618  btr     dword ptr [r14+48h], 0Fh
0x18007561e  lea     r11, [rsp+68h+var_28]
0x180075623  mov     rbx, [r11+30h]
0x180075627  mov     rbp, [r11+40h]
0x18007562b  mov     rsp, r11
0x18007562e  pop     r15
0x180075630  pop     r14
0x180075632  pop     r12
0x180075634  pop     rdi
0x180075635  pop     rsi
0x180075636  retn
```
