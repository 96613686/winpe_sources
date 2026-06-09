# Tab_OnInsertItem

- ea: `0x1800654bc`
- end: `0x180065749`
- name: `Tab_OnInsertItem`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180066d40`

## callees

- `0x1800115f0`
- `0x1800197bc`
- `0x18002ee60`
- `0x18002fd4c`
- `0x180062d80`
- `0x180064000`
- `0x180064868`
- `0x1800654bc`
- `0x180066a3c`
- `0x18008e3b0`
- `0x18008ea60`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180065572`
- `KERNEL32!LocalFree` at `0x180065572`
- `KERNEL32!LocalAlloc` at `0x180065502`
- `KERNEL32!LocalAlloc` at `0x180065502`
- `USER32!GetClientRect` at `0x1800656bd`
- `USER32!GetClientRect` at `0x1800656bd`
- `USER32!SendMessageW` at `0x180065643`
- `USER32!SendMessageW` at `0x180065643`
- `USER32!RedrawWindow` at `0x1800656f6`
- `USER32!RedrawWindow` at `0x1800656f6`
- `USER32!UpdateWindow` at `0x180065734`
- `USER32!UpdateWindow` at `0x180065734`

## pseudocode

```c
__int64 __fastcall Tab_OnInsertItem(_QWORD *a1, int a2, __int64 a3)
{
  _DWORD *v6; // rsi
  int v7; // eax
  int inserted; // eax
  __int64 v10; // rdi
  int v11; // eax
  int v12; // eax
  HWND v13; // rsi
  int v14; // eax
  int v15; // eax
  bool v16; // zf
  __int64 v17; // rdx
  LONG *v18; // rsi
  __int64 v19; // rdx
  LPARAM lParam[8]; // [rsp+20h] [rbp-60h] BYREF
  struct tagRECT Rect; // [rsp+60h] [rbp-20h] BYREF

  if ( *((_DWORD *)a1 + 19) >= 0xFFFFFFB8 )
    return 0xFFFFFFFFLL;
  v6 = LocalAlloc(0x40u, (unsigned int)(*((_DWORD *)a1 + 19) + 64));
  if ( !v6 )
    return 0xFFFFFFFFLL;
  if ( (*(_BYTE *)a3 & 2) != 0 )
    v7 = *(_DWORD *)(a3 + 28);
  else
    v7 = -1;
  v6[4] = v7;
  v6[6] = 0x7FFFFFFF;
  v6[5] = 0x7FFFFFFF;
  if ( (*(_BYTE *)a3 & 8) != 0 && *((_DWORD *)a1 + 19) )
    memmove(v6 + 16, (const void *)(a3 + 32), *((int *)a1 + 19));
  if ( (*(_BYTE *)a3 & 1) != 0 )
  {
    if ( !(unsigned int)Str_Set(v6 + 12, *(_QWORD *)(a3 + 16)) )
    {
LABEL_11:
      Str_Set(v6 + 12, 0);
      LocalFree(v6);
      return 0xFFFFFFFFLL;
    }
    v6[15] = 32 * (*(_DWORD *)a3 & 4);
  }
  inserted = DPA_InsertPtr((HDPA)a1[8], a2, v6);
  v10 = inserted;
  if ( inserted == -1 )
    goto LABEL_11;
  v11 = *((_DWORD *)a1 + 24);
  if ( v11 >= 0 )
  {
    if ( v11 >= (int)v10 )
      *((_DWORD *)a1 + 24) = v11 + 1;
  }
  else
  {
    *((_DWORD *)a1 + 24) = v10;
  }
  v12 = *((_DWORD *)a1 + 31);
  if ( v12 > (int)v10 )
    *((_DWORD *)a1 + 31) = v12 + 1;
  v13 = (HWND)a1[22];
  *((_DWORD *)a1 + 26) = 0x7FFFFFFF;
  if ( v13 )
  {
    memset(lParam, 0, sizeof(lParam));
    v14 = *(_BYTE *)a3 & 4;
    LODWORD(lParam[0]) = 64;
    HIDWORD(lParam[0]) = v14;
    lParam[1] = *a1;
    v15 = *(_DWORD *)a1[8] - 1;
    lParam[6] = -1;
    lParam[2] = v15;
    SendMessageW(v13, 0x432u, 0, (LPARAM)lParam);
  }
  if ( (a1[9] & 0x10) != 0 )
  {
    v16 = (a1[2] & 0x100) == 0;
    Rect = 0;
    if ( v16 )
    {
      v19 = *((unsigned int *)a1 + 24);
      if ( (int)v19 > (int)v10 )
      {
        Tab_InvalidateItem(a1, v19, 1);
        UpdateWindow((HWND)*a1);
      }
    }
    else if ( (a1[2] & 0x400) != 0 )
    {
      CalcPaintMetrics(a1, 0);
      v17 = a1[8];
      if ( (_DWORD)v10 == *(_DWORD *)v17 - 1 )
      {
        Tab_InvalidateItem(a1, (unsigned int)v10, 0);
      }
      else
      {
        if ( v17 && (int)v10 >= 0 && (int)v10 < *(_DWORD *)v17 )
        {
          _mm_lfence();
          v18 = *(LONG **)(*(_QWORD *)(v17 + 8) + 8 * v10);
        }
        else
        {
          v18 = 0;
        }
        GetClientRect((HWND)*a1, &Rect);
        if ( v18 )
        {
          v16 = *((_DWORD *)a1 + 37) == 0;
          Rect.top = v18[1];
          if ( v16 )
            Rect.left = *v18;
          Tab_UpdateArrows((__int64)a1, 0);
          RedrawWindow((HWND)*a1, &Rect, 0, 0x41u);
        }
      }
      goto LABEL_37;
    }
    RedrawAll(a1, 65);
  }
LABEL_37:
  MyNotifyWinEvent(0x8000, *a1, 4294967292LL);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800654bc  mov     [rsp-28h+arg_18], rbx
0x1800654c1  push    rbp
0x1800654c2  push    rsi
0x1800654c3  push    rdi
0x1800654c4  push    r14
0x1800654c6  push    r15
0x1800654c8  mov     rbp, rsp
0x1800654cb  sub     rsp, 80h
0x1800654d2  mov     rax, cs:__security_cookie
0x1800654d9  xor     rax, rsp
0x1800654dc  mov     [rbp+var_10], rax
0x1800654e0  mov     eax, [rcx+4Ch]
0x1800654e3  mov     r14, r8
0x1800654e6  add     eax, 48h ; 'H'
0x1800654e9  mov     r15d, edx
0x1800654ec  mov     rbx, rcx
0x1800654ef  cmp     eax, 48h ; 'H'
0x1800654f2  jb      loc_180065578
0x1800654f8  add     eax, 0FFFFFFF8h
0x1800654fb  mov     ecx, 40h ; '@'; uFlags
0x180065500  mov     edx, eax; uBytes
0x180065502  call    cs:__imp_LocalAlloc
0x180065508  mov     rsi, rax
0x18006550b  test    rax, rax
0x18006550e  jz      short loc_180065578
0x180065510  test    byte ptr [r14], 2
0x180065514  jz      short loc_18006551C
0x180065516  mov     eax, [r14+1Ch]
0x18006551a  jmp     short loc_18006551F
0x18006551c  or      eax, 0FFFFFFFFh
0x18006551f  mov     [rsi+10h], eax
0x180065522  mov     dword ptr [rsi+18h], 7FFFFFFFh
0x180065529  mov     dword ptr [rsi+14h], 7FFFFFFFh
0x180065530  test    byte ptr [r14], 8
0x180065534  jz      short loc_18006554D
0x180065536  cmp     dword ptr [rbx+4Ch], 0
0x18006553a  jz      short loc_18006554D
0x18006553c  movsxd  r8, dword ptr [rbx+4Ch]; Size
0x180065540  lea     rdx, [r14+20h]; Src
0x180065544  lea     rcx, [rsi+40h]; void *
0x180065548  call    memmove
0x18006554d  test    byte ptr [r14], 1
0x180065551  jz      short loc_1800655AA
0x180065553  mov     rdx, [r14+10h]
0x180065557  lea     rcx, [rsi+30h]
0x18006555b  call    Str_Set
0x180065560  test    eax, eax
0x180065562  jnz     short loc_18006559E
0x180065564  lea     rcx, [rsi+30h]
0x180065568  xor     edx, edx
0x18006556a  call    Str_Set
0x18006556f  mov     rcx, rsi; hMem
0x180065572  call    cs:__imp_LocalFree
0x180065578  or      eax, 0FFFFFFFFh
0x18006557b  mov     rcx, [rbp+var_10]
0x18006557f  xor     rcx, rsp; StackCookie
0x180065582  call    __security_check_cookie
0x180065587  mov     rbx, [rsp+80h+arg_18]
0x18006558f  add     rsp, 80h
0x180065596  pop     r15
0x180065598  pop     r14
0x18006559a  pop     rdi
0x18006559b  pop     rsi
0x18006559c  pop     rbp
0x18006559d  retn
0x18006559e  mov     eax, [r14]
0x1800655a1  and     eax, 4
0x1800655a4  shl     eax, 5
0x1800655a7  mov     [rsi+3Ch], eax
0x1800655aa  mov     rcx, [rbx+40h]; hdpa
0x1800655ae  mov     r8, rsi; p
0x1800655b1  mov     edx, r15d; i
0x1800655b4  call    DPA_InsertPtr
0x1800655b9  movsxd  rdi, eax
0x1800655bc  cmp     edi, 0FFFFFFFFh
0x1800655bf  jz      short loc_180065564
0x1800655c1  mov     eax, [rbx+60h]
0x1800655c4  test    eax, eax
0x1800655c6  jns     short loc_1800655CD
0x1800655c8  mov     [rbx+60h], edi
0x1800655cb  jmp     short loc_1800655D6
0x1800655cd  cmp     eax, edi
0x1800655cf  jl      short loc_1800655D6
0x1800655d1  inc     eax
0x1800655d3  mov     [rbx+60h], eax
0x1800655d6  mov     eax, [rbx+7Ch]
0x1800655d9  cmp     eax, edi
0x1800655db  jle     short loc_1800655E2
0x1800655dd  inc     eax
0x1800655df  mov     [rbx+7Ch], eax
0x1800655e2  mov     rsi, [rbx+0B0h]
0x1800655e9  mov     dword ptr [rbx+68h], 7FFFFFFFh
0x1800655f0  test    rsi, rsi
0x1800655f3  jz      short loc_180065649
0x1800655f5  mov     r15d, 40h ; '@'
0x1800655fb  lea     rcx, [rbp+lParam]; void *
0x1800655ff  mov     r8d, r15d; Size
0x180065602  xor     edx, edx; Val
0x180065604  call    memset
0x180065609  movzx   eax, byte ptr [r14]
0x18006560d  lea     r9, [rbp+lParam]; lParam
0x180065611  and     eax, 4
0x180065614  mov     dword ptr [rbp+lParam], r15d
0x180065618  mov     dword ptr [rbp+lParam+4], eax
0x18006561b  xor     r8d, r8d; wParam
0x18006561e  mov     rax, [rbx]
0x180065621  mov     edx, 432h; Msg
0x180065626  mov     [rbp+var_58], rax
0x18006562a  mov     rcx, rsi; hWnd
0x18006562d  mov     rax, [rbx+40h]
0x180065631  mov     eax, [rax]
0x180065633  dec     eax
0x180065635  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFFh
0x18006563d  cdqe
0x18006563f  mov     [rbp+var_50], rax
0x180065643  call    cs:__imp_SendMessageW
0x180065649  test    byte ptr [rbx+48h], 10h
0x18006564d  jz      loc_1800656FC
0x180065653  test    dword ptr [rbx+10h], 100h
0x18006565a  xorps   xmm0, xmm0
0x18006565d  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180065661  jz      loc_18006571C
0x180065667  test    dword ptr [rbx+10h], 400h
0x18006566e  jz      loc_18006573A
0x180065674  xor     edx, edx
0x180065676  mov     rcx, rbx
0x180065679  call    CalcPaintMetrics
0x18006567e  mov     rdx, [rbx+40h]
0x180065682  mov     ecx, [rdx]
0x180065684  lea     eax, [rcx-1]
0x180065687  cmp     edi, eax
0x180065689  jnz     short loc_18006569A
0x18006568b  xor     r8d, r8d
0x18006568e  mov     edx, edi
0x180065690  mov     rcx, rbx
0x180065693  call    Tab_InvalidateItem
0x180065698  jmp     short loc_1800656FC
0x18006569a  test    rdx, rdx
0x18006569d  jz      short loc_1800656B4
0x18006569f  test    edi, edi
0x1800656a1  js      short loc_1800656B4
0x1800656a3  cmp     edi, ecx
0x1800656a5  jge     short loc_1800656B4
0x1800656a7  lfence
0x1800656aa  mov     rax, [rdx+8]
0x1800656ae  mov     rsi, [rax+rdi*8]
0x1800656b2  jmp     short loc_1800656B6
0x1800656b4  xor     esi, esi
0x1800656b6  mov     rcx, [rbx]; hWnd
0x1800656b9  lea     rdx, [rbp+Rect]; lpRect
0x1800656bd  call    cs:__imp_GetClientRect
0x1800656c3  test    rsi, rsi
0x1800656c6  jz      short loc_1800656FC
0x1800656c8  cmp     dword ptr [rbx+94h], 0
0x1800656cf  mov     eax, [rsi+4]
0x1800656d2  mov     [rbp+Rect.top], eax
0x1800656d5  jnz     short loc_1800656DC
0x1800656d7  mov     eax, [rsi]
0x1800656d9  mov     [rbp+Rect.left], eax
0x1800656dc  xor     edx, edx
0x1800656de  mov     rcx, rbx
0x1800656e1  call    Tab_UpdateArrows
0x1800656e6  mov     rcx, [rbx]; hWnd
0x1800656e9  lea     rdx, [rbp+Rect]; lprcUpdate
0x1800656ed  mov     r9d, 41h ; 'A'; flags
0x1800656f3  xor     r8d, r8d; hrgnUpdate
0x1800656f6  call    cs:__imp_RedrawWindow
0x1800656fc  mov     rdx, [rbx]
0x1800656ff  lea     eax, [rdi+1]
0x180065702  movsxd  r9, eax
0x180065705  mov     r8d, 0FFFFFFFCh
0x18006570b  mov     ecx, 8000h
0x180065710  call    MyNotifyWinEvent
0x180065715  mov     eax, edi
0x180065717  jmp     loc_18006557B
0x18006571c  mov     edx, [rbx+60h]
0x18006571f  cmp     edx, edi
0x180065721  jle     short loc_18006573A
0x180065723  mov     r8d, 1
0x180065729  mov     rcx, rbx
0x18006572c  call    Tab_InvalidateItem
0x180065731  mov     rcx, [rbx]; hWnd
0x180065734  call    cs:__imp_UpdateWindow
0x18006573a  mov     edx, 41h ; 'A'
0x18006573f  mov     rcx, rbx
0x180065742  call    RedrawAll
0x180065747  jmp     short loc_1800656FC
```
