# Header_OnSetItem

- ea: `0x1800616ac`
- end: `0x180061a04`
- name: `Header_OnSetItem`
- size: `856`
- prototype: ``
- caller_count: `7`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x18005f6f0`
- `0x18005fd80`
- `0x180060ff8`
- `0x1800611c4`
- `0x180061a0c`
- `0x180061de4`
- `0x180061f10`

## callees

- `0x1800115f0`
- `0x1800197bc`
- `0x18001a5e0`
- `0x18002fd4c`
- `0x18005f8c8`
- `0x18005fbb0`
- `0x18005fd38`
- `0x180060924`
- `0x180060990`
- `0x1800616ac`
- `0x180061b38`
- `0x180061c2c`
- `0x180061cc8`

## import_xrefs

- `USER32!GetClientRect` at `0x180061778`
- `USER32!GetClientRect` at `0x18006199f`
- `USER32!GetClientRect` at `0x180061778`
- `USER32!GetClientRect` at `0x18006199f`
- `USER32!RedrawWindow` at `0x1800619d0`
- `USER32!RedrawWindow` at `0x1800619d0`
- `USER32!InvalidateRect` at `0x18006181f`
- `USER32!InvalidateRect` at `0x18006181f`
- `USER32!UpdateWindow` at `0x180061800`
- `USER32!UpdateWindow` at `0x180061800`

## pseudocode

```c
__int64 __fastcall Header_OnSetItem(HWND *a1, unsigned int a2, int *a3)
{
  HWND v6; // rdx
  LONG *v7; // rbx
  int v8; // r15d
  int v10; // r13d
  int v11; // eax
  bool v12; // sf
  LONG v13; // ecx
  unsigned int ItemOrder; // eax
  __int64 v15; // r8
  int v16; // eax
  int v17; // eax
  int *v18; // rax
  __int64 v19; // r13
  HWND v20; // rcx
  __int64 v21; // [rsp+20h] [rbp-59h]
  _QWORD v22[2]; // [rsp+30h] [rbp-49h] BYREF
  int v23; // [rsp+40h] [rbp-39h]
  int v24; // [rsp+44h] [rbp-35h]
  __int64 v25; // [rsp+48h] [rbp-31h]
  struct tagRECT *p_Rect; // [rsp+50h] [rbp-29h]
  __int64 v27; // [rsp+58h] [rbp-21h]
  __int64 v28; // [rsp+60h] [rbp-19h]
  int v29; // [rsp+68h] [rbp-11h]
  __int128 v30; // [rsp+6Ch] [rbp-Dh]
  int v31; // [rsp+7Ch] [rbp+3h]
  struct tagRECT Rect; // [rsp+80h] [rbp+7h] BYREF

  if ( !a3 )
    return 0;
  if ( !a1 )
    return 0;
  if ( (a2 & 0x80000000) != 0 )
    return 0;
  v6 = a1[11];
  if ( (signed int)a2 >= *(_DWORD *)v6 )
    return 0;
  v7 = (LONG *)(*((_QWORD *)v6 + 1) + *((_DWORD *)v6 + 5) * a2);
  if ( !v7 )
    return 0;
  v8 = *a3;
  if ( !*a3 )
    return 1;
  if ( !(unsigned int)Header_SendChange(a1, a2, 4294966976LL, a3) )
    return 0;
  v10 = 0;
  HIDWORD(v21) = *v7;
  if ( (v8 & 1) != 0 )
  {
    v11 = 0;
    v12 = a3[1] < 0;
    Rect = 0;
    if ( !v12 )
      v11 = a3[1];
    LODWORD(v21) = v11 - v7[1];
    v7[1] = v11;
    GetClientRect(*a1, &Rect);
    v13 = *v7;
    Rect.left = *v7;
    if ( (int)v21 < 0 )
      Rect.left = v13 + v21;
    ItemOrder = Header_OnGetItemOrder(a1, a2);
    Header_ShiftItems(a1, ItemOrder, (unsigned int)v21);
    v22[0] = 80;
    v24 = 0;
    v7[12] = 0x7FFFFFFF;
    v7[13] = 0x7FFFFFFF;
    v22[1] = *a1;
    v23 = v21;
    v31 = 0;
    v25 = 0;
    v27 = 0;
    v28 = 0;
    p_Rect = &Rect;
    v29 = 6;
    v30 = 0;
    SmoothScrollWindow((__int64)v22);
    UpdateWindow(*a1);
    Header_OnGetItemRect(a1, a2, &Rect);
    InvalidateRect(*a1, &Rect, 0);
  }
  if ( (v8 & 4) != 0 )
  {
    v10 = 1;
    v7[2] = a3[7];
    v7[12] = 0x7FFFFFFF;
    v7[13] = 0x7FFFFFFF;
  }
  if ( (v8 & 8) != 0 )
    *((_QWORD *)v7 + 5) = *((_QWORD *)a3 + 4);
  if ( (v8 & 2) == 0 )
    goto LABEL_22;
  if ( !(unsigned int)Str_Set(v7 + 4, *((_QWORD *)a3 + 1)) )
    return 0;
  v7[13] = 0x7FFFFFFF;
  v10 = 1;
LABEL_22:
  if ( (v8 & 0x10) != 0 )
  {
    v10 = 1;
    *((_QWORD *)v7 + 3) = *((_QWORD *)a3 + 2);
    v7[12] = 0x7FFFFFFF;
  }
  if ( (v8 & 0x20) != 0 )
  {
    v10 = 1;
    v7[8] = a3[10];
    v7[12] = 0x7FFFFFFF;
  }
  if ( (v8 & 0x80u) != 0 )
  {
    v15 = (unsigned int)a3[11];
    if ( (int)v15 >= 0 && (int)v15 < *(_DWORD *)a1[11] )
    {
      Header_OnSetItemOrder(a1, a2, v15);
      MyNotifyWinEvent(32772, *a1, 4294967292LL);
    }
  }
  if ( (v8 & 0x100) != 0 )
  {
    if ( (v7[16] & 0xF) == 0 )
      Str_Set(v7 + 18, 0);
    v16 = a3[12];
    v7[16] = v16;
    v17 = v16 & 0xF;
    if ( v17 )
    {
      if ( v17 == 1 && (a3[12] & 0x8000) == 0 )
      {
        v18 = (int *)*((_QWORD *)a3 + 7);
        if ( v18 )
          v7[22] = *v18;
      }
    }
    else
    {
      v19 = *((_QWORD *)a3 + 7);
      if ( v19 )
      {
        if ( (a3[12] & 0x8000) == 0 )
          Str_Set(v7 + 18, *(_QWORD *)v19);
        v7[20] = *(_DWORD *)(v19 + 8);
      }
    }
    v10 = 1;
  }
  Header_SendChange(a1, a2, 4294966975LL, a3);
  if ( (v8 & 0x100) != 0 )
    Header_Notify(a1, a2, 0, 4294966984LL, v21);
  if ( v10 )
  {
    if ( HIDWORD(v21) == *v7 )
    {
      Header_InvalidateItem(a1, a2, 5);
    }
    else
    {
      v20 = *a1;
      Rect = 0;
      GetClientRect(v20, &Rect);
      if ( (int)a2 > 0 )
      {
        if ( Header_GetItemPtrByOrder(a1, a2 - 1) )
          Rect.left = *v7;
      }
      RedrawWindow(*a1, &Rect, 0, 5u);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800616ac  mov     [rsp-8+arg_18], rbx
0x1800616b1  push    rbp
0x1800616b2  push    rsi
0x1800616b3  push    rdi
0x1800616b4  push    r12
0x1800616b6  push    r13
0x1800616b8  push    r14
0x1800616ba  push    r15
0x1800616bc  lea     rbp, [rsp-27h]
0x1800616c1  sub     rsp, 0A0h
0x1800616c8  mov     rax, cs:__security_cookie
0x1800616cf  xor     rax, rsp
0x1800616d2  mov     [rbp+57h+var_40], rax
0x1800616d6  mov     rdi, r8
0x1800616d9  mov     r14d, edx
0x1800616dc  mov     rsi, rcx
0x1800616df  test    r8, r8
0x1800616e2  jz      loc_1800619DB
0x1800616e8  test    rcx, rcx
0x1800616eb  jz      loc_1800619DB
0x1800616f1  test    edx, edx
0x1800616f3  js      loc_1800619DB
0x1800616f9  mov     rdx, [rcx+58h]
0x1800616fd  cmp     r14d, [rdx]
0x180061700  jge     loc_1800619DB
0x180061706  mov     ebx, r14d
0x180061709  imul    ebx, [rdx+14h]
0x18006170d  add     rbx, [rdx+8]
0x180061711  jz      loc_1800619DB
0x180061717  mov     r15d, [r8]
0x18006171a  test    r15d, r15d
0x18006171d  jnz     short loc_180061728
0x18006171f  lea     eax, [r15+1]
0x180061723  jmp     loc_1800619DD
0x180061728  mov     r9, rdi
0x18006172b  mov     r8d, 0FFFFFEC0h
0x180061731  mov     edx, r14d
0x180061734  call    Header_SendChange
0x180061739  test    eax, eax
0x18006173b  jz      loc_1800619DB
0x180061741  mov     eax, [rbx]
0x180061743  xor     r13d, r13d
0x180061746  mov     [rbp+57h+var_AC], eax
0x180061749  lea     r12d, [r13+1]
0x18006174d  test    r12b, r15b
0x180061750  jz      loc_180061825
0x180061756  xor     eax, eax
0x180061758  lea     rdx, [rbp+57h+Rect]; lpRect
0x18006175c  cmp     [rdi+4], eax
0x18006175f  xorps   xmm0, xmm0
0x180061762  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180061766  cmovge  eax, [rdi+4]
0x18006176a  mov     ecx, eax
0x18006176c  sub     ecx, [rbx+4]
0x18006176f  mov     [rbp+57h+var_B0], ecx
0x180061772  mov     [rbx+4], eax
0x180061775  mov     rcx, [rsi]; hWnd
0x180061778  call    cs:__imp_GetClientRect
0x18006177e  mov     eax, [rbp+57h+var_B0]
0x180061781  mov     ecx, [rbx]
0x180061783  mov     [rbp+57h+Rect.left], ecx
0x180061786  test    eax, eax
0x180061788  jns     short loc_18006178F
0x18006178a  add     eax, ecx
0x18006178c  mov     [rbp+57h+Rect.left], eax
0x18006178f  mov     edx, r14d
0x180061792  mov     rcx, rsi
0x180061795  call    Header_OnGetItemOrder
0x18006179a  mov     r8d, [rbp+57h+var_B0]
0x18006179e  mov     edx, eax
0x1800617a0  mov     rcx, rsi
0x1800617a3  call    Header_ShiftItems
0x1800617a8  xor     ecx, ecx
0x1800617aa  mov     [rbp+57h+var_A0], 50h ; 'P'
0x1800617b2  mov     eax, 7FFFFFFFh
0x1800617b7  mov     [rbp+57h+var_8C], ecx
0x1800617ba  mov     [rbx+30h], eax
0x1800617bd  xorps   xmm0, xmm0
0x1800617c0  mov     [rbx+34h], eax
0x1800617c3  mov     rax, [rsi]
0x1800617c6  mov     [rbp+57h+var_98], rax
0x1800617ca  mov     eax, [rbp+57h+var_B0]
0x1800617cd  mov     [rbp+57h+var_90], eax
0x1800617d0  xor     eax, eax
0x1800617d2  mov     [rbp+57h+var_54], eax
0x1800617d5  lea     rax, [rbp+57h+Rect]
0x1800617d9  mov     [rbp+57h+var_88], rcx
0x1800617dd  mov     [rbp+57h+var_78], rcx
0x1800617e1  mov     [rbp+57h+var_70], rcx
0x1800617e5  lea     rcx, [rbp+57h+var_A0]
0x1800617e9  mov     [rbp+57h+var_80], rax
0x1800617ed  mov     [rbp+57h+var_68], 6
0x1800617f4  movups  [rbp+57h+var_64], xmm0
0x1800617f8  call    SmoothScrollWindow
0x1800617fd  mov     rcx, [rsi]; hWnd
0x180061800  call    cs:__imp_UpdateWindow
0x180061806  lea     r8, [rbp+57h+Rect]
0x18006180a  mov     edx, r14d
0x18006180d  mov     rcx, rsi
0x180061810  call    Header_OnGetItemRect
0x180061815  mov     rcx, [rsi]; hWnd
0x180061818  lea     rdx, [rbp+57h+Rect]; lpRect
0x18006181c  xor     r8d, r8d; bErase
0x18006181f  call    cs:__imp_InvalidateRect
0x180061825  test    r15b, 4
0x180061829  jz      short loc_180061842
0x18006182b  mov     eax, [rdi+1Ch]
0x18006182e  mov     r13d, r12d
0x180061831  mov     [rbx+8], eax
0x180061834  mov     dword ptr [rbx+30h], 7FFFFFFFh
0x18006183b  mov     dword ptr [rbx+34h], 7FFFFFFFh
0x180061842  test    r15b, 8
0x180061846  jz      short loc_180061850
0x180061848  mov     rax, [rdi+20h]
0x18006184c  mov     [rbx+28h], rax
0x180061850  test    r15b, 2
0x180061854  jz      short loc_180061875
0x180061856  mov     rdx, [rdi+8]
0x18006185a  lea     rcx, [rbx+10h]
0x18006185e  call    Str_Set
0x180061863  test    eax, eax
0x180061865  jz      loc_1800619DB
0x18006186b  mov     dword ptr [rbx+34h], 7FFFFFFFh
0x180061872  mov     r13d, r12d
0x180061875  test    r15b, 10h
0x180061879  jz      short loc_18006188D
0x18006187b  mov     rax, [rdi+10h]
0x18006187f  mov     r13d, r12d
0x180061882  mov     [rbx+18h], rax
0x180061886  mov     dword ptr [rbx+30h], 7FFFFFFFh
0x18006188d  test    r15b, 20h
0x180061891  jz      short loc_1800618A3
0x180061893  mov     eax, [rdi+28h]
0x180061896  mov     r13d, r12d
0x180061899  mov     [rbx+20h], eax
0x18006189c  mov     dword ptr [rbx+30h], 7FFFFFFFh
0x1800618a3  test    r15b, r15b
0x1800618a6  jns     short loc_1800618D9
0x1800618a8  mov     r8d, [rdi+2Ch]
0x1800618ac  test    r8d, r8d
0x1800618af  js      short loc_1800618D9
0x1800618b1  mov     rax, [rsi+58h]
0x1800618b5  cmp     r8d, [rax]
0x1800618b8  jge     short loc_1800618D9
0x1800618ba  mov     edx, r14d
0x1800618bd  mov     rcx, rsi
0x1800618c0  call    Header_OnSetItemOrder
0x1800618c5  mov     rdx, [rsi]
0x1800618c8  xor     r9d, r9d
0x1800618cb  mov     ecx, 8004h
0x1800618d0  lea     r8d, [r9-4]
0x1800618d4  call    MyNotifyWinEvent
0x1800618d9  bt      r15d, 8
0x1800618de  jnb     short loc_180061943
0x1800618e0  test    byte ptr [rbx+40h], 0Fh
0x1800618e4  jnz     short loc_1800618F1
0x1800618e6  lea     rcx, [rbx+48h]
0x1800618ea  xor     edx, edx
0x1800618ec  call    Str_Set
0x1800618f1  mov     eax, [rdi+30h]
0x1800618f4  mov     [rbx+40h], eax
0x1800618f7  and     eax, 0Fh
0x1800618fa  jz      short loc_18006191A
0x1800618fc  cmp     eax, r12d
0x1800618ff  jnz     short loc_180061940
0x180061901  test    dword ptr [rdi+30h], 8000h
0x180061908  jnz     short loc_180061940
0x18006190a  mov     rax, [rdi+38h]
0x18006190e  test    rax, rax
0x180061911  jz      short loc_180061940
0x180061913  mov     eax, [rax]
0x180061915  mov     [rbx+58h], eax
0x180061918  jmp     short loc_180061940
0x18006191a  mov     r13, [rdi+38h]
0x18006191e  test    r13, r13
0x180061921  jz      short loc_180061940
0x180061923  test    dword ptr [rdi+30h], 8000h
0x18006192a  jnz     short loc_180061939
0x18006192c  mov     rdx, [r13+0]
0x180061930  lea     rcx, [rbx+48h]
0x180061934  call    Str_Set
0x180061939  mov     eax, [r13+8]
0x18006193d  mov     [rbx+50h], eax
0x180061940  mov     r13d, r12d
0x180061943  mov     r9, rdi
0x180061946  mov     r8d, 0FFFFFEBFh
0x18006194c  mov     edx, r14d
0x18006194f  mov     rcx, rsi
0x180061952  call    Header_SendChange
0x180061957  bt      r15d, 8
0x18006195c  jnb     short loc_180061972
0x18006195e  mov     r9d, 0FFFFFEC8h
0x180061964  xor     r8d, r8d
0x180061967  mov     edx, r14d
0x18006196a  mov     rcx, rsi
0x18006196d  call    Header_Notify
0x180061972  test    r13d, r13d
0x180061975  jz      short loc_1800619D6
0x180061977  mov     eax, [rbp+57h+var_AC]
0x18006197a  cmp     eax, [rbx]
0x18006197c  jnz     short loc_180061991
0x18006197e  mov     r8d, 5
0x180061984  mov     edx, r14d
0x180061987  mov     rcx, rsi
0x18006198a  call    Header_InvalidateItem
0x18006198f  jmp     short loc_1800619D6
0x180061991  mov     rcx, [rsi]; hWnd
0x180061994  lea     rdx, [rbp+57h+Rect]; lpRect
0x180061998  xorps   xmm0, xmm0
0x18006199b  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18006199f  call    cs:__imp_GetClientRect
0x1800619a5  test    r14d, r14d
0x1800619a8  jle     short loc_1800619C0
0x1800619aa  lea     edx, [r14-1]
0x1800619ae  mov     rcx, rsi
0x1800619b1  call    Header_GetItemPtrByOrder
0x1800619b6  test    rax, rax
0x1800619b9  jz      short loc_1800619C0
0x1800619bb  mov     eax, [rbx]
0x1800619bd  mov     [rbp+57h+Rect.left], eax
0x1800619c0  mov     rcx, [rsi]; hWnd
0x1800619c3  lea     rdx, [rbp+57h+Rect]; lprcUpdate
0x1800619c7  mov     r9d, 5; flags
0x1800619cd  xor     r8d, r8d; hrgnUpdate
0x1800619d0  call    cs:__imp_RedrawWindow
0x1800619d6  mov     eax, r12d
0x1800619d9  jmp     short loc_1800619DD
0x1800619db  xor     eax, eax
0x1800619dd  mov     rcx, [rbp+57h+var_40]
0x1800619e1  xor     rcx, rsp; StackCookie
0x1800619e4  call    __security_check_cookie
0x1800619e9  mov     rbx, [rsp+0D0h+arg_18]
0x1800619f1  add     rsp, 0A0h
0x1800619f8  pop     r15
0x1800619fa  pop     r14
0x1800619fc  pop     r13
0x1800619fe  pop     r12
0x180061a00  pop     rdi
0x180061a01  pop     rsi
0x180061a02  pop     rbp
0x180061a03  retn
```
