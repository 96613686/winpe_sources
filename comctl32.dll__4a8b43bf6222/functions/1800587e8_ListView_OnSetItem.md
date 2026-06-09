# ListView_OnSetItem

- ea: `0x1800587e8`
- end: `0x180058ccd`
- name: `ListView_OnSetItem`
- size: `1253`
- prototype: `__int64 __fastcall(int)`
- caller_count: `4`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1800590f4`
- `0x18005c0a0`
- `0x1800733e0`
- `0x180077c74`

## callees

- `0x1800115f0`
- `0x1800197bc`
- `0x18002fd4c`
- `0x180051ac4`
- `0x180052ff0`
- `0x180053f50`
- `0x180054344`
- `0x180054958`
- `0x1800587e8`
- `0x1800590f4`
- `0x18005b588`
- `0x180079e60`
- `0x180085d00`

## import_xrefs

- `GDI32!DeleteObject` at `0x180058ac0`
- `GDI32!DeleteObject` at `0x180058b8d`
- `GDI32!DeleteObject` at `0x180058ac0`
- `GDI32!DeleteObject` at `0x180058b8d`
- `USER32!SendMessageW` at `0x180058a8f`
- `USER32!SendMessageW` at `0x180058a8f`
- `USER32!RedrawWindow` at `0x180058a72`
- `USER32!RedrawWindow` at `0x180058a72`

## pseudocode

```c
__int64 __fastcall ListView_OnSetItem(_QWORD *a1, int *a2, __int64 a3, __int64 a4)
{
  struct _IMAGELIST *v6; // rcx
  UINT v7; // r12d
  int v8; // ebx
  int v9; // r15d
  __int64 v11; // rsi
  int v12; // r8d
  __int64 v13; // rax
  __int64 v14; // rbx
  int v15; // r13d
  int v16; // ecx
  int v17; // ebp
  int v18; // r8d
  int v19; // r13d
  int v20; // r15d
  unsigned __int16 v21; // cx
  int v22; // r13d
  char v23; // al
  int v24; // ecx
  int v25; // eax
  int v26; // ebp
  HWND v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  __int16 v30; // ax
  __int64 v31; // rax
  __int64 v32; // rcx
  int v33; // [rsp+40h] [rbp-68h]
  int v34; // [rsp+44h] [rbp-64h]
  int v35; // [rsp+48h] [rbp-60h]
  int v36; // [rsp+4Ch] [rbp-5Ch]
  int v37; // [rsp+50h] [rbp-58h]
  int v38; // [rsp+54h] [rbp-54h]
  RECT rcUpdate; // [rsp+58h] [rbp-50h] BYREF

  if ( (a1[2] & 0x1000) != 0 || !a2 )
    return 0;
  v6 = (struct _IMAGELIST *)a1[34];
  v7 = 1;
  if ( v6 )
  {
    v8 = *((_DWORD *)a1 + 24);
    if ( v8 != ImageList_GetBkColor(v6) )
      v7 = 5;
  }
  v9 = *a2;
  v38 = *a2;
  if ( !*a2 )
    return 1;
  if ( a2[2] > 0 )
    return ListView_SetSubItem(a1, a2);
  v11 = a2[1];
  ListView_InvalidateTTLastHit(a1, (unsigned int)a2[1], a3, a4);
  v13 = a1[8];
  if ( !v13 )
    return 0;
  if ( (int)v11 < 0 )
    return 0;
  if ( (int)v11 >= *(_DWORD *)v13 )
    return 0;
  _mm_lfence();
  v14 = *(_QWORD *)(*(_QWORD *)(v13 + 8) + 8 * v11);
  if ( !v14 )
    return 0;
  v15 = 0;
  v16 = 0;
  v36 = 0;
  v34 = 0;
  v17 = v9 & 8;
  if ( (v9 & 8) != 0 )
  {
    v16 = a2[4] & *(unsigned __int16 *)(v14 + 28);
    v15 = a2[4] & a2[3];
    v36 = v15;
    v34 = v16;
  }
  if ( (a1[2] & 4) != 0 && (v9 & 8) != 0 && (v15 & 2) != 0 )
  {
    ListView_DeselectAll((_DWORD)a1);
    v16 = a2[4] & *(unsigned __int16 *)(v14 + 28);
    v34 = v16;
  }
  if ( !(unsigned int)ListView_SendChange((_DWORD)a1, v11, v12, -100, v16, v15, v9, *(_QWORD *)(v14 + 32)) )
    return 0;
  v19 = 0;
  v35 = 0;
  v20 = 0;
  v37 = 0;
  if ( v17 )
  {
    v21 = *(_WORD *)(v14 + 28);
    v22 = a2[4] & (a2[3] ^ v21);
    if ( v22 )
    {
      v20 = 8;
      v23 = v21 ^ v22;
      *(_WORD *)(v14 + 28) = v21 ^ v22;
      if ( (v22 & 2) != 0 )
      {
        v24 = *((_DWORD *)a1 + 46);
        v37 = 1;
        if ( (v23 & 2) != 0 )
        {
          v25 = v24 + 1;
LABEL_27:
          *((_DWORD *)a1 + 46) = v25;
          goto LABEL_28;
        }
        if ( v24 )
        {
          v25 = v24 - 1;
          goto LABEL_27;
        }
      }
LABEL_28:
      if ( (v22 & 1) != 0 )
      {
        v26 = *((_DWORD *)a1 + 36);
        if ( v26 < 0 || (a1[2] & 3) != 0 || (v33 = 1, *((char *)a1 + 72) >= 0) )
          v33 = 0;
        v35 = 1;
        rcUpdate = 0;
        if ( v26 == (_DWORD)v11 )
        {
          *((_DWORD *)a1 + 36) = -1;
        }
        else if ( v26 == -1 || (unsigned int)ListView_OnSetItemState(a1, (unsigned int)v26, 0, 1) )
        {
          *((_DWORD *)a1 + 36) = v11;
          if ( *((_DWORD *)a1 + 37) == -1 )
            *((_DWORD *)a1 + 37) = v11;
        }
        else
        {
          v35 = 0;
          *(_WORD *)(v14 + 28) &= ~1u;
        }
        if ( v33
          && (v26 < 0 || (a1[2] & 3) != 0 || *((char *)a1 + 72) >= 0 || *((_DWORD *)a1 + 36) != v26)
          && *((_DWORD *)a1 + 38) != v26 )
        {
          ListView_GetUnfoldedRect(a1, (unsigned int)v26, &rcUpdate);
          RedrawWindow((HWND)*a1, &rcUpdate, 0, 5u);
        }
        v27 = (HWND)a1[26];
        if ( v27 )
          SendMessageW(v27, 0x41Cu, 0, 0);
      }
      if ( (v22 & 4) != 0 || *((_DWORD *)a1 + 27) == -1 )
        v7 |= 4u;
      if ( (v22 & 0xF00) != 0 )
      {
        v28 = *(void **)(v14 + 40);
        if ( v28 )
        {
          if ( v28 != (void *)-1LL )
            DeleteObject(v28);
          *(_QWORD *)(v14 + 40) = 0;
        }
      }
      v19 = v22 & 0xF000;
      goto LABEL_59;
    }
    v19 = 0;
  }
LABEL_59:
  if ( (v38 & 1) == 0 )
    goto LABEL_64;
  if ( *((_DWORD *)a1 + 38) != (_DWORD)v11 )
    ListView_InvalidateItemEx((__int64)a1, v11, 0, 5u, 1);
  if ( (unsigned int)Str_Set(v14, *((_QWORD *)a2 + 3)) )
  {
    *((_DWORD *)a1 + 76) = 0x7FFFFFFF;
    v20 |= 1u;
    *(_DWORD *)(v14 + 18) = 2147450879;
    *(_DWORD *)(v14 + 22) = 2147450879;
LABEL_64:
    if ( (v38 & 0x10) != 0 && *(__int16 *)(v14 + 30) != a2[12] )
    {
      v20 |= 0x10u;
      *(_WORD *)(v14 + 30) = *((_WORD *)a2 + 24);
      if ( (a1[2] & 3) == 1 )
        v7 |= 4u;
    }
    if ( (v38 & 2) != 0 && *(__int16 *)(v14 + 16) != a2[9] )
    {
      v29 = *(void **)(v14 + 40);
      v20 |= 2u;
      v30 = *((_WORD *)a2 + 18);
      *(_WORD *)(v14 + 16) = v30;
      if ( v29 )
      {
        if ( v29 != (void *)-1LL )
        {
          DeleteObject(v29);
          v30 = *(_WORD *)(v14 + 16);
        }
        *(_QWORD *)(v14 + 40) = 0;
      }
      if ( v30 != -1 )
        v7 |= 4u;
    }
    if ( (v38 & 4) != 0 )
    {
      v31 = *((_QWORD *)a2 + 5);
      if ( *(_QWORD *)(v14 + 32) != v31 )
      {
        *(_QWORD *)(v14 + 32) = v31;
        v20 |= 4u;
      }
    }
    if ( v20 )
    {
      if ( *((_DWORD *)a1 + 38) != (_DWORD)v11 )
        ListView_InvalidateItemEx((__int64)a1, v11, 0, v7, v20);
      ListView_SendChange((_DWORD)a1, v11, v18, -101, v34, v36, v20, *(_QWORD *)(v14 + 32));
      if ( (v20 & 1) != 0 )
        MyNotifyWinEvent(32780, *a1, 4294967292LL);
      if ( (v20 & 8) != 0 )
      {
        if ( v35 )
          ListView_NotifyFocusEvent(a1);
        if ( v37 )
        {
          if ( (v36 & 2) != 0 )
            v32 = (unsigned int)(*((_DWORD *)a1 + 46) != 1) + 32774;
          else
            v32 = 32776;
          MyNotifyWinEvent(v32, *a1, 4294967292LL);
        }
        if ( v19 )
          MyNotifyWinEvent(32778, *a1, 4294967292LL);
      }
    }
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800587e8  mov     [rsp+arg_10], rbx
0x1800587ed  push    rbp
0x1800587ee  push    rsi
0x1800587ef  push    rdi
0x1800587f0  push    r12
0x1800587f2  push    r13
0x1800587f4  push    r14
0x1800587f6  push    r15
0x1800587f8  sub     rsp, 70h
0x1800587fc  mov     rax, cs:__security_cookie
0x180058803  xor     rax, rsp
0x180058806  mov     [rsp+0A8h+var_40], rax
0x18005880b  test    dword ptr [rcx+10h], 1000h
0x180058812  mov     r14, rdx
0x180058815  mov     rdi, rcx
0x180058818  jnz     loc_180058CA6
0x18005881e  test    rdx, rdx
0x180058821  jz      loc_180058CA6
0x180058827  mov     rcx, [rcx+110h]; himl
0x18005882e  mov     r12d, 1
0x180058834  lea     esi, [r12+4]
0x180058839  test    rcx, rcx
0x18005883c  jz      short loc_18005884C
0x18005883e  mov     ebx, [rdi+60h]
0x180058841  call    ImageList_GetBkColor
0x180058846  cmp     ebx, eax
0x180058848  cmovnz  r12d, esi
0x18005884c  mov     r15d, [r14]
0x18005884f  mov     [rsp+0A8h+var_54], r15d
0x180058854  test    r15d, r15d
0x180058857  jz      loc_180058C9F
0x18005885d  cmp     dword ptr [r14+8], 0
0x180058862  mov     rcx, rdi
0x180058865  jle     short loc_180058874
0x180058867  mov     rdx, r14
0x18005886a  call    ListView_SetSubItem
0x18005886f  jmp     loc_180058CA8
0x180058874  movsxd  rsi, dword ptr [r14+4]
0x180058878  mov     edx, esi
0x18005887a  call    ListView_InvalidateTTLastHit
0x18005887f  mov     rax, [rdi+40h]
0x180058883  test    rax, rax
0x180058886  jz      loc_180058CA6
0x18005888c  test    esi, esi
0x18005888e  js      loc_180058CA6
0x180058894  cmp     esi, [rax]
0x180058896  jge     loc_180058CA6
0x18005889c  lfence
0x18005889f  mov     rax, [rax+8]
0x1800588a3  mov     rbx, [rax+rsi*8]
0x1800588a7  test    rbx, rbx
0x1800588aa  jz      loc_180058CA6
0x1800588b0  xor     r13d, r13d
0x1800588b3  xor     ecx, ecx
0x1800588b5  mov     ebp, r15d
0x1800588b8  mov     [rsp+0A8h+var_5C], r13d
0x1800588bd  mov     [rsp+0A8h+var_64], ecx
0x1800588c1  and     ebp, 8
0x1800588c4  jz      short loc_1800588DF
0x1800588c6  movzx   ecx, word ptr [rbx+1Ch]
0x1800588ca  and     ecx, [r14+10h]
0x1800588ce  mov     r13d, [r14+0Ch]
0x1800588d2  and     r13d, [r14+10h]
0x1800588d6  mov     [rsp+0A8h+var_5C], r13d
0x1800588db  mov     [rsp+0A8h+var_64], ecx
0x1800588df  test    byte ptr [rdi+10h], 4
0x1800588e3  jz      short loc_180058905
0x1800588e5  test    ebp, ebp
0x1800588e7  jz      short loc_180058905
0x1800588e9  test    r13b, 2
0x1800588ed  jz      short loc_180058905
0x1800588ef  mov     edx, esi
0x1800588f1  mov     rcx, rdi
0x1800588f4  call    ListView_DeselectAll
0x1800588f9  movzx   ecx, word ptr [rbx+1Ch]
0x1800588fd  and     ecx, [r14+10h]
0x180058901  mov     [rsp+0A8h+var_64], ecx
0x180058905  mov     rax, [rbx+20h]
0x180058909  mov     r9d, 0FFFFFF9Ch
0x18005890f  mov     [rsp+0A8h+var_70], rax
0x180058914  mov     edx, esi
0x180058916  mov     [rsp+0A8h+var_78], r15d
0x18005891b  mov     [rsp+0A8h+var_80], r13d
0x180058920  mov     [rsp+0A8h+var_88], ecx
0x180058924  mov     rcx, rdi
0x180058927  call    ListView_SendChange
0x18005892c  test    eax, eax
0x18005892e  jz      loc_180058CA6
0x180058934  xor     r13d, r13d
0x180058937  mov     [rsp+0A8h+var_60], 0
0x18005893f  xor     r15d, r15d
0x180058942  mov     [rsp+0A8h+var_58], 0
0x18005894a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005894e  test    ebp, ebp
0x180058950  jz      loc_180058ADA
0x180058956  movzx   ecx, word ptr [rbx+1Ch]
0x18005895a  mov     r13d, ecx
0x18005895d  xor     r13d, [r14+0Ch]
0x180058961  and     r13d, [r14+10h]
0x180058965  jz      loc_180058AD7
0x18005896b  movzx   eax, r13w
0x18005896f  lea     r15d, [rdx+9]
0x180058973  xor     ax, cx
0x180058976  mov     [rbx+1Ch], ax
0x18005897a  test    r13b, 2
0x18005897e  jz      short loc_1800589A4
0x180058980  mov     ecx, [rdi+0B8h]
0x180058986  mov     [rsp+0A8h+var_58], 1
0x18005898e  test    al, 2
0x180058990  jz      short loc_180058997
0x180058992  lea     eax, [rcx+1]
0x180058995  jmp     short loc_18005899E
0x180058997  test    ecx, ecx
0x180058999  jz      short loc_1800589A4
0x18005899b  lea     eax, [rcx-1]
0x18005899e  mov     [rdi+0B8h], eax
0x1800589a4  mov     eax, 1
0x1800589a9  test    al, r13b
0x1800589ac  jz      loc_180058A99
0x1800589b2  mov     ebp, [rdi+90h]
0x1800589b8  test    ebp, ebp
0x1800589ba  js      short loc_1800589CC
0x1800589bc  test    byte ptr [rdi+10h], 3
0x1800589c0  jnz     short loc_1800589CC
0x1800589c2  test    byte ptr [rdi+48h], 80h
0x1800589c6  mov     [rsp+0A8h+var_68], eax
0x1800589ca  jnz     short loc_1800589D4
0x1800589cc  mov     [rsp+0A8h+var_68], 0
0x1800589d4  mov     [rsp+0A8h+var_60], eax
0x1800589d8  xorps   xmm0, xmm0
0x1800589db  movups  xmmword ptr [rsp+0A8h+rcUpdate.left], xmm0
0x1800589e0  cmp     ebp, esi
0x1800589e2  jz      short loc_180058A25
0x1800589e4  cmp     ebp, edx
0x1800589e6  jz      short loc_180058A0F
0x1800589e8  mov     r9d, eax
0x1800589eb  xor     r8d, r8d
0x1800589ee  mov     edx, ebp
0x1800589f0  mov     rcx, rdi
0x1800589f3  call    ListView_OnSetItemState
0x1800589f8  test    eax, eax
0x1800589fa  jnz     short loc_180058A0B
0x1800589fc  mov     [rsp+0A8h+var_60], eax
0x180058a00  mov     eax, 0FFFEh
0x180058a05  and     [rbx+1Ch], ax
0x180058a09  jmp     short loc_180058A2B
0x180058a0b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180058a0f  mov     [rdi+90h], esi
0x180058a15  cmp     [rdi+94h], edx
0x180058a1b  jnz     short loc_180058A2B
0x180058a1d  mov     [rdi+94h], esi
0x180058a23  jmp     short loc_180058A2B
0x180058a25  mov     [rdi+90h], edx
0x180058a2b  cmp     [rsp+0A8h+var_68], 0
0x180058a30  jz      short loc_180058A78
0x180058a32  test    ebp, ebp
0x180058a34  js      short loc_180058A4A
0x180058a36  test    byte ptr [rdi+10h], 3
0x180058a3a  jnz     short loc_180058A4A
0x180058a3c  test    byte ptr [rdi+48h], 80h
0x180058a40  jz      short loc_180058A4A
0x180058a42  cmp     [rdi+90h], ebp
0x180058a48  jz      short loc_180058A78
0x180058a4a  cmp     [rdi+98h], ebp
0x180058a50  jz      short loc_180058A78
0x180058a52  lea     r8, [rsp+0A8h+rcUpdate]
0x180058a57  mov     edx, ebp
0x180058a59  mov     rcx, rdi
0x180058a5c  call    ListView_GetUnfoldedRect
0x180058a61  mov     rcx, [rdi]; hWnd
0x180058a64  lea     rdx, [rsp+0A8h+rcUpdate]; lprcUpdate
0x180058a69  mov     r9d, 5; flags
0x180058a6f  xor     r8d, r8d; hrgnUpdate
0x180058a72  call    cs:__imp_RedrawWindow
0x180058a78  mov     rcx, [rdi+0D0h]; hWnd
0x180058a7f  test    rcx, rcx
0x180058a82  jz      short loc_180058A95
0x180058a84  xor     r9d, r9d; lParam
0x180058a87  xor     r8d, r8d; wParam
0x180058a8a  mov     edx, 41Ch; Msg
0x180058a8f  call    cs:__imp_SendMessageW
0x180058a95  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180058a99  test    r13b, 4
0x180058a9d  jnz     short loc_180058AA5
0x180058a9f  cmp     dword ptr [rdi+6Ch], 0FFFFFFFFh
0x180058aa3  jnz     short loc_180058AA9
0x180058aa5  or      r12d, 4
0x180058aa9  test    r13d, 0F00h
0x180058ab0  jz      short loc_180058ACE
0x180058ab2  mov     rcx, [rbx+28h]; ho
0x180058ab6  test    rcx, rcx
0x180058ab9  jz      short loc_180058ACE
0x180058abb  cmp     rcx, rdx
0x180058abe  jz      short loc_180058AC6
0x180058ac0  call    cs:__imp_DeleteObject
0x180058ac6  mov     qword ptr [rbx+28h], 0
0x180058ace  and     r13d, 0F000h
0x180058ad5  jmp     short loc_180058ADA
0x180058ad7  mov     r13d, r15d
0x180058ada  mov     ebp, [rsp+0A8h+var_54]
0x180058ade  test    bpl, 1
0x180058ae2  jz      short loc_180058B37
0x180058ae4  cmp     [rdi+98h], esi
0x180058aea  jz      short loc_180058B07
0x180058aec  mov     r9d, 5
0x180058af2  mov     [rsp+0A8h+var_88], 1; int
0x180058afa  xor     r8d, r8d
0x180058afd  mov     edx, esi
0x180058aff  mov     rcx, rdi; int
0x180058b02  call    ListView_InvalidateItemEx
0x180058b07  mov     rdx, [r14+18h]
0x180058b0b  mov     rcx, rbx
0x180058b0e  call    Str_Set
0x180058b13  test    eax, eax
0x180058b15  jz      loc_180058CA6
0x180058b1b  mov     dword ptr [rdi+130h], 7FFFFFFFh
0x180058b25  or      r15d, 1
0x180058b29  mov     dword ptr [rbx+12h], 7FFF7FFFh
0x180058b30  mov     dword ptr [rbx+16h], 7FFF7FFFh
0x180058b37  test    bpl, 10h
0x180058b3b  jz      short loc_180058B61
0x180058b3d  movsx   eax, word ptr [rbx+1Eh]
0x180058b41  cmp     eax, [r14+30h]
0x180058b45  jz      short loc_180058B61
0x180058b47  movzx   eax, word ptr [r14+30h]
0x180058b4c  or      r15d, 10h
0x180058b50  mov     [rbx+1Eh], ax
0x180058b54  mov     eax, [rdi+10h]
0x180058b57  and     al, 3
0x180058b59  cmp     al, 1
0x180058b5b  jnz     short loc_180058B61
0x180058b5d  or      r12d, 4
0x180058b61  test    bpl, 2
0x180058b65  jz      short loc_180058BAC
0x180058b67  movsx   eax, word ptr [rbx+10h]
0x180058b6b  cmp     eax, [r14+24h]
0x180058b6f  jz      short loc_180058BAC
0x180058b71  mov     rcx, [rbx+28h]; ho
0x180058b75  or      r15d, 2
0x180058b79  movzx   eax, word ptr [r14+24h]
0x180058b7e  mov     [rbx+10h], ax
0x180058b82  test    rcx, rcx
0x180058b85  jz      short loc_180058B9F
0x180058b87  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180058b8b  jz      short loc_180058B97
0x180058b8d  call    cs:__imp_DeleteObject
0x180058b93  movzx   eax, word ptr [rbx+10h]
0x180058b97  mov     qword ptr [rbx+28h], 0
0x180058b9f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180058ba3  cmp     ax, cx
0x180058ba6  jz      short loc_180058BAC
0x180058ba8  or      r12d, 4
0x180058bac  test    bpl, 4
0x180058bb0  jz      short loc_180058BC4
0x180058bb2  mov     rax, [r14+28h]
0x180058bb6  cmp     [rbx+20h], rax
0x180058bba  jz      short loc_180058BC4
0x180058bbc  mov     [rbx+20h], rax
0x180058bc0  or      r15d, 4
0x180058bc4  test    r15d, r15d
0x180058bc7  jz      loc_180058C9F
0x180058bcd  cmp     [rdi+98h], esi
0x180058bd3  jz      short loc_180058BEA
0x180058bd5  mov     r9d, r12d
0x180058bd8  mov     [rsp+0A8h+var_88], r15d; int
0x180058bdd  xor     r8d, r8d
0x180058be0  mov     edx, esi
0x180058be2  mov     rcx, rdi; int
0x180058be5  call    ListView_InvalidateItemEx
0x180058bea  mov     rax, [rbx+20h]
0x180058bee  mov     r9d, 0FFFFFF9Bh
0x180058bf4  mov     ebx, [rsp+0A8h+var_5C]
0x180058bf8  mov     edx, esi
0x180058bfa  mov     [rsp+0A8h+var_70], rax
0x180058bff  mov     rcx, rdi
0x180058c02  mov     eax, [rsp+0A8h+var_64]
0x180058c06  mov     [rsp+0A8h+var_78], r15d
0x180058c0b  mov     [rsp+0A8h+var_80], ebx
0x180058c0f  mov     [rsp+0A8h+var_88], eax
0x180058c13  call    ListView_SendChange
0x180058c18  mov     ebp, 0FFFFFFFCh
0x180058c1d  test    r15b, 1
0x180058c21  jz      short loc_180058C39
0x180058c23  mov     rdx, [rdi]
0x180058c26  lea     eax, [rsi+1]
0x180058c29  movsxd  r9, eax
0x180058c2c  mov     r8d, ebp
0x180058c2f  mov     ecx, 800Ch
0x180058c34  call    MyNotifyWinEvent
0x180058c39  test    r15b, 8
0x180058c3d  jz      short loc_180058C9F
0x180058c3f  cmp     [rsp+0A8h+var_60], 0
0x180058c44  jz      short loc_180058C4E
0x180058c46  mov     rcx, rdi
0x180058c49  call    ListView_NotifyFocusEvent
0x180058c4e  cmp     [rsp+0A8h+var_58], 0
0x180058c53  jz      short loc_180058C84
0x180058c55  mov     rdx, [rdi]
0x180058c58  lea     eax, [rsi+1]
0x180058c5b  movsxd  r9, eax
  ... truncated ...
```
