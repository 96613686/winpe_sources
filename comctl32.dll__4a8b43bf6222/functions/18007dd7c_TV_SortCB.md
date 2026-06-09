# TV_SortCB

- ea: `0x18007dd7c`
- end: `0x18007e181`
- name: `TV_SortCB`
- size: `1029`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006bbb0`

## callees

- `0x1800115f0`
- `0x1800197bc`
- `0x18002eab0`
- `0x18002ec60`
- `0x18002ee60`
- `0x18002f730`
- `0x18002f7d0`
- `0x18002f950`
- `0x18002fa90`
- `0x18002fd4c`
- `0x180068e44`
- `0x180068edc`
- `0x18006cca4`
- `0x18007cc7c`
- `0x18007d988`
- `0x18007dc50`
- `0x18007dd7c`
- `0x18007e188`

## import_xrefs

- `USER32!GetClientRect` at `0x18007e039`
- `USER32!GetClientRect` at `0x18007e039`
- `USER32!GetWindowLongW` at `0x18007e0a5`
- `USER32!GetWindowLongW` at `0x18007e0a5`
- `USER32!InvalidateRect` at `0x18007e059`
- `USER32!InvalidateRect` at `0x18007e059`
- `USER32!UpdateWindow` at `0x18007e0fd`
- `USER32!UpdateWindow` at `0x18007e0fd`
- `USER32!GetScrollInfo` at `0x18007e0db`
- `USER32!GetScrollInfo` at `0x18007e0db`

## pseudocode

```c
__int64 __fastcall TV_SortCB(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        int (__stdcall *a4)(void *p1, void *p2, LPARAM lParam))
{
  __int64 v4; // r14
  __int64 v8; // rax
  int v9; // ebx
  HDSA v10; // rsi
  HDPA v11; // r15
  __int64 i; // rbx
  int inserted; // eax
  void *v14; // r8
  _QWORD *v15; // rdx
  __int64 v16; // r10
  int v17; // ecx
  _QWORD *v18; // r9
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r10
  __int128 v22; // xmm0
  __int64 v23; // rdx
  int v24; // ebx
  __int64 v25; // rcx
  unsigned int nPos; // ebx
  HWND v27; // rcx
  _QWORD *v28; // rsi
  __int64 v29; // rbx
  __int128 v31; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v32; // [rsp+30h] [rbp-D0h]
  char *v33; // [rsp+38h] [rbp-C8h]
  _DWORD v34[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct tagSCROLLINFO pitem; // [rsp+60h] [rbp-A0h] BYREF
  RECT Rect; // [rsp+80h] [rbp-80h] BYREF
  char v37; // [rsp+90h] [rbp-70h] BYREF

  v4 = *a2;
  if ( !*a2 || v4 == -65536 )
    v4 = a1[8];
  if ( !(unsigned int)ValidateTreeItem(v4, 0) )
    return 0;
  v8 = *(_QWORD *)(v4 + 16);
  v9 = 0;
  if ( !v8 )
    return 0;
  do
  {
    v8 = *(_QWORD *)(v8 + 8);
    ++v9;
  }
  while ( v8 );
  if ( !v9 )
    return 0;
  v10 = DSA_Create(24, v9);
  if ( v10 )
  {
    v11 = DPA_CreateEx(v9, 0);
    if ( v11 )
    {
      for ( i = *(_QWORD *)(v4 + 16); ; i = *(_QWORD *)(i + 8) )
      {
        if ( !i )
        {
          if ( !a4 )
            a4 = TV_DefCompare;
          DPA_Sort(v11, a4, (LPARAM)a2);
          v15 = (_QWORD *)*((_QWORD *)v11 + 1);
          v16 = *(_QWORD *)(*v15 + 16LL);
          if ( *(_QWORD *)(v4 + 16) == v16 )
            v16 = 0;
          else
            *(_QWORD *)(v4 + 16) = v16;
          v17 = *(_DWORD *)v11;
          while ( --v17 > 0 )
          {
            v18 = v15 + 1;
            v19 = *(_QWORD *)(v15[1] + 16LL);
            v20 = *(_QWORD *)(*v15 + 16LL);
            if ( *(_QWORD *)(v20 + 8) != v19 && !v16 )
              v16 = v19;
            *(_QWORD *)(v20 + 8) = v19;
            v15 = v18;
          }
          *(_QWORD *)(*(_QWORD *)(*v15 + 16LL) + 8LL) = 0;
          TV_UpdateShownIndexes(a1, v4);
          if ( *a2 == -65536 && *((_DWORD *)a1 + 80) < (unsigned int)*((unsigned __int16 *)a1 + 158) )
            a1[41] = *(_QWORD *)(a1[8] + 16LL);
          if ( v21 && (*(_BYTE *)(v4 + 40) & 0x20) != 0 )
          {
            v22 = 0;
            Rect = 0;
            *(double *)&v22 = TV_GetItemRect(a1, v21, &Rect, 0);
            v23 = *(_QWORD *)(v4 + 8);
            *(_OWORD *)&pitem.cbSize = v22;
            if ( v23 )
              TV_GetItemRect(a1, v23, &pitem, 0);
            else
              GetClientRect((HWND)*a1, (LPRECT)&pitem);
            Rect.bottom = pitem.nMax;
            if ( (a1[7] & 0x10) != 0 )
              InvalidateRect((HWND)*a1, &Rect, 1);
          }
          goto LABEL_46;
        }
        *(_QWORD *)&pitem.nMax = 0;
        pitem.nPos = 0;
        if ( a4 || *(_QWORD *)(i + 24) != -1 )
        {
          *(_QWORD *)&pitem.cbSize = *(_QWORD *)(i + 24);
          pitem.nMin = 0;
        }
        else
        {
          memset(v34, 0, 28);
          v34[0] = 260;
          v32 = 0;
          v33 = &v37;
          v31 = 0;
          TV_GetItem(a1, i, 1, &v31);
          *(_QWORD *)&pitem.cbSize = 0;
          pitem.nMin = 1;
          Str_Set(&pitem, v33);
          if ( !*(_QWORD *)&pitem.cbSize )
            goto LABEL_46;
        }
        *(_QWORD *)&pitem.nPage = i;
        inserted = DSA_InsertItem(v10, 0x7FFFFFFF, &pitem);
        if ( inserted < 0 )
          break;
        if ( inserted >= *(_DWORD *)v10 )
          v14 = 0;
        else
          v14 = (void *)(*((_QWORD *)v10 + 1) + (unsigned int)(*((_DWORD *)v10 + 5) * inserted));
        if ( DPA_InsertPtr(v11, 0x7FFFFFFF, v14) < 0 )
          goto LABEL_46;
      }
      if ( pitem.nMin )
        Str_Set(&pitem, 0);
LABEL_46:
      DPA_Destroy(v11);
    }
    v24 = *(_DWORD *)v10;
    while ( --v24 >= 0 )
    {
      if ( v24 >= *(_DWORD *)v10 )
        v25 = 0;
      else
        v25 = *((_QWORD *)v10 + 1) + (unsigned int)(*((_DWORD *)v10 + 5) * v24);
      if ( *(_DWORD *)(v25 + 8) )
        Str_Set(v25, 0);
    }
    DSA_Destroy(v10);
  }
  nPos = 0;
  if ( (GetWindowLongW((HWND)*a1, -16) & 0x200000) != 0 )
  {
    v27 = (HWND)*a1;
    *(_QWORD *)&pitem.cbSize = 0x40000001CLL;
    memset(&pitem.nMin, 0, 20);
    if ( GetScrollInfo(v27, 1, &pitem) )
      nPos = pitem.nPos;
  }
  if ( (unsigned int)TV_SmoothSetTopItem(a1, nPos, 0) )
    UpdateWindow((HWND)*a1);
  v28 = (_QWORD *)a1[9];
  if ( v28 )
  {
    do
    {
      v28 = (_QWORD *)*v28;
      if ( (_QWORD *)v4 == v28 )
      {
        v29 = a1[9];
        TV_ExpandParents(a1, v29, 1);
        TV_ScrollIntoView(a1, v29);
      }
    }
    while ( v28 && v28 != (_QWORD *)a1[8] );
  }
  MyNotifyWinEvent(32772, *a1, 4294967292LL);
  return 1;
}

```

## disassembly

```asm
0x18007dd7c  mov     [rsp-8+arg_10], rbx
0x18007dd81  push    rbp
0x18007dd82  push    rsi
0x18007dd83  push    rdi
0x18007dd84  push    r12
0x18007dd86  push    r13
0x18007dd88  push    r14
0x18007dd8a  push    r15
0x18007dd8c  lea     rbp, [rsp-1B0h]
0x18007dd94  sub     rsp, 2B0h
0x18007dd9b  mov     rax, cs:__security_cookie
0x18007dda2  xor     rax, rsp
0x18007dda5  mov     [rbp+1E0h+var_40], rax
0x18007ddac  mov     r14, [rdx]
0x18007ddaf  mov     r12, r9
0x18007ddb2  mov     r13, rdx
0x18007ddb5  mov     rdi, rcx
0x18007ddb8  test    r14, r14
0x18007ddbb  jz      short loc_18007DDC6
0x18007ddbd  cmp     r14, 0FFFFFFFFFFFF0000h
0x18007ddc4  jnz     short loc_18007DDCA
0x18007ddc6  mov     r14, [rcx+40h]
0x18007ddca  xor     edx, edx
0x18007ddcc  mov     rcx, r14
0x18007ddcf  call    ValidateTreeItem
0x18007ddd4  test    eax, eax
0x18007ddd6  jz      loc_18007E155
0x18007dddc  mov     rax, [r14+10h]
0x18007dde0  xor     ebx, ebx
0x18007dde2  test    rax, rax
0x18007dde5  jz      loc_18007E155
0x18007ddeb  lea     r15d, [rbx+1]
0x18007ddef  mov     rax, [rax+8]
0x18007ddf3  add     ebx, r15d
0x18007ddf6  test    rax, rax
0x18007ddf9  jnz     short loc_18007DDEF
0x18007ddfb  test    ebx, ebx
0x18007ddfd  jz      loc_18007E155
0x18007de03  mov     edx, ebx; cItemGrow
0x18007de05  lea     ecx, [rax+18h]; cbItem
0x18007de08  call    DSA_Create
0x18007de0d  mov     rsi, rax
0x18007de10  test    rax, rax
0x18007de13  jz      loc_18007E09D
0x18007de19  xor     edx, edx; hheap
0x18007de1b  mov     ecx, ebx; cpGrow
0x18007de1d  call    DPA_CreateEx
0x18007de22  mov     r15, rax
0x18007de25  test    rax, rax
0x18007de28  jz      loc_18007E067
0x18007de2e  mov     rbx, [r14+10h]
0x18007de32  jmp     loc_18007DF15
0x18007de37  mov     qword ptr [rsp+2E0h+pitem+0Ch], 0
0x18007de40  mov     [rsp+2E0h+var_26C], 0
0x18007de48  test    r12, r12
0x18007de4b  jnz     short loc_18007DEBC
0x18007de4d  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x18007de52  jnz     short loc_18007DEBC
0x18007de54  xorps   xmm0, xmm0
0x18007de57  lea     r9, [rsp+2E0h+var_2C0]
0x18007de5c  movups  xmmword ptr [rsp+2E0h+var_2A0], xmm0
0x18007de61  xor     eax, eax
0x18007de63  mov     [rsp+2E0h+var_2A0], 104h
0x18007de6b  lea     rax, [rbp+1E0h+var_250]
0x18007de6f  mov     rdx, rbx
0x18007de72  movups  [rsp+2E0h+var_2B0], xmm0
0x18007de77  lea     r8d, [r12+1]
0x18007de7c  mov     qword ptr [rsp+2E0h+var_2B0+8], rax
0x18007de81  mov     rcx, rdi
0x18007de84  movups  [rsp+2E0h+var_2C0], xmm0
0x18007de89  movups  xmmword ptr [rsp+2E0h+var_2A0+0Ch], xmm0
0x18007de8e  call    TV_GetItem
0x18007de93  mov     rdx, qword ptr [rsp+2E0h+var_2B0+8]
0x18007de98  lea     rcx, [rsp+2E0h+pitem]
0x18007de9d  mov     qword ptr [rsp+2E0h+pitem], r12
0x18007dea2  mov     dword ptr [rsp+2E0h+pitem+8], 1
0x18007deaa  call    Str_Set
0x18007deaf  cmp     qword ptr [rsp+2E0h+pitem], r12
0x18007deb4  jz      loc_18007E05F
0x18007deba  jmp     short loc_18007DECD
0x18007debc  mov     rax, [rbx+18h]
0x18007dec0  mov     qword ptr [rsp+2E0h+pitem], rax
0x18007dec5  mov     dword ptr [rsp+2E0h+pitem+8], 0
0x18007decd  lea     r8, [rsp+2E0h+pitem]; pitem
0x18007ded2  mov     [rsp+70h], rbx
0x18007ded7  mov     edx, 7FFFFFFFh; i
0x18007dedc  mov     rcx, rsi; hdsa
0x18007dedf  call    DSA_InsertItem
0x18007dee4  test    eax, eax
0x18007dee6  js      short loc_18007DF51
0x18007dee8  cmp     eax, [rsi]
0x18007deea  jge     short loc_18007DEF9
0x18007deec  imul    eax, [rsi+14h]
0x18007def0  mov     r8d, eax
0x18007def3  add     r8, [rsi+8]
0x18007def7  jmp     short loc_18007DEFC
0x18007def9  xor     r8d, r8d; p
0x18007defc  mov     edx, 7FFFFFFFh; i
0x18007df01  mov     rcx, r15; hdpa
0x18007df04  call    DPA_InsertPtr
0x18007df09  test    eax, eax
0x18007df0b  js      loc_18007E05F
0x18007df11  mov     rbx, [rbx+8]
0x18007df15  test    rbx, rbx
0x18007df18  jnz     loc_18007DE37
0x18007df1e  lea     rax, TV_DefCompare
0x18007df25  test    r12, r12
0x18007df28  mov     r8, r13; lParam
0x18007df2b  mov     rcx, r15; hdpa
0x18007df2e  cmovz   r12, rax
0x18007df32  mov     rdx, r12; pfnCompare
0x18007df35  call    DPA_Sort
0x18007df3a  mov     rdx, [r15+8]
0x18007df3e  mov     rax, [rdx]
0x18007df41  mov     r10, [rax+10h]
0x18007df45  cmp     [r14+10h], r10
0x18007df49  jz      short loc_18007DF6D
0x18007df4b  mov     [r14+10h], r10
0x18007df4f  jmp     short loc_18007DF70
0x18007df51  cmp     dword ptr [rsp+2E0h+pitem+8], 0
0x18007df56  jz      loc_18007E05F
0x18007df5c  xor     edx, edx
0x18007df5e  lea     rcx, [rsp+2E0h+pitem]
0x18007df63  call    Str_Set
0x18007df68  jmp     loc_18007E05F
0x18007df6d  xor     r10d, r10d
0x18007df70  mov     ecx, [r15]
0x18007df73  jmp     short loc_18007DF9B
0x18007df75  lea     r9, [rdx+8]
0x18007df79  mov     rax, [r9]
0x18007df7c  mov     r8, [rax+10h]
0x18007df80  mov     rax, [rdx]
0x18007df83  mov     rdx, [rax+10h]
0x18007df87  cmp     [rdx+8], r8
0x18007df8b  jz      short loc_18007DF94
0x18007df8d  test    r10, r10
0x18007df90  cmovz   r10, r8
0x18007df94  mov     [rdx+8], r8
0x18007df98  mov     rdx, r9
0x18007df9b  dec     ecx
0x18007df9d  test    ecx, ecx
0x18007df9f  jg      short loc_18007DF75
0x18007dfa1  mov     rax, [rdx]
0x18007dfa4  mov     rdx, r14
0x18007dfa7  mov     rcx, [rax+10h]
0x18007dfab  mov     qword ptr [rcx+8], 0
0x18007dfb3  mov     rcx, rdi
0x18007dfb6  call    TV_UpdateShownIndexes
0x18007dfbb  cmp     qword ptr [r13+0], 0FFFFFFFFFFFF0000h
0x18007dfc3  jnz     short loc_18007DFE3
0x18007dfc5  movzx   eax, word ptr [rdi+13Ch]
0x18007dfcc  cmp     [rdi+140h], eax
0x18007dfd2  jnb     short loc_18007DFE3
0x18007dfd4  mov     rax, [rdi+40h]
0x18007dfd8  mov     rcx, [rax+10h]
0x18007dfdc  mov     [rdi+148h], rcx
0x18007dfe3  test    r10, r10
0x18007dfe6  jz      short loc_18007E05F
0x18007dfe8  test    byte ptr [r14+28h], 20h
0x18007dfed  jz      short loc_18007E05F
0x18007dfef  xorps   xmm0, xmm0
0x18007dff2  lea     r8, [rbp+1E0h+Rect]
0x18007dff6  xor     r9d, r9d
0x18007dff9  mov     rdx, r10
0x18007dffc  mov     rcx, rdi
0x18007dfff  movups  xmmword ptr [rbp+1E0h+Rect.left], xmm0
0x18007e003  call    TV_GetItemRect
0x18007e008  mov     rdx, [r14+8]
0x18007e00c  movups  [rsp+2E0h+pitem], xmm0
0x18007e011  test    rdx, rdx
0x18007e014  jz      short loc_18007E031
0x18007e016  xor     r9d, r9d
0x18007e019  lea     r8, [rsp+2E0h+pitem]
0x18007e01e  mov     rcx, rdi
0x18007e021  call    TV_GetItemRect
0x18007e026  mov     r8d, dword ptr [rsp+2E0h+pitem+0Ch]
0x18007e02b  mov     [rbp+1E0h+Rect.bottom], r8d
0x18007e02f  jmp     short loc_18007E046
0x18007e031  mov     rcx, [rdi]; hWnd
0x18007e034  lea     rdx, [rsp+2E0h+pitem]; lpRect
0x18007e039  call    cs:__imp_GetClientRect
0x18007e03f  mov     eax, dword ptr [rsp+2E0h+pitem+0Ch]
0x18007e043  mov     [rbp+1E0h+Rect.bottom], eax
0x18007e046  test    byte ptr [rdi+38h], 10h
0x18007e04a  jz      short loc_18007E05F
0x18007e04c  mov     rcx, [rdi]; hWnd
0x18007e04f  lea     rdx, [rbp+1E0h+Rect]; lpRect
0x18007e053  mov     r8d, 1; bErase
0x18007e059  call    cs:__imp_InvalidateRect
0x18007e05f  mov     rcx, r15; hdpa
0x18007e062  call    DPA_Destroy
0x18007e067  mov     ebx, [rsi]
0x18007e069  mov     r15d, 1
0x18007e06f  jmp     short loc_18007E090
0x18007e071  cmp     ebx, [rsi]
0x18007e073  jge     short loc_18007E081
0x18007e075  mov     ecx, ebx
0x18007e077  imul    ecx, [rsi+14h]
0x18007e07b  add     rcx, [rsi+8]
0x18007e07f  jmp     short loc_18007E083
0x18007e081  xor     ecx, ecx
0x18007e083  cmp     dword ptr [rcx+8], 0
0x18007e087  jz      short loc_18007E090
0x18007e089  xor     edx, edx
0x18007e08b  call    Str_Set
0x18007e090  sub     ebx, r15d
0x18007e093  jns     short loc_18007E071
0x18007e095  mov     rcx, rsi; hdsa
0x18007e098  call    DSA_Destroy
0x18007e09d  mov     rcx, [rdi]; hWnd
0x18007e0a0  mov     edx, 0FFFFFFF0h; nIndex
0x18007e0a5  call    cs:__imp_GetWindowLongW
0x18007e0ab  xor     ebx, ebx
0x18007e0ad  bt      eax, 15h
0x18007e0b1  jnb     short loc_18007E0E9
0x18007e0b3  mov     rcx, [rdi]; hwnd
0x18007e0b6  lea     r8, [rsp+2E0h+pitem]; lpsi
0x18007e0bb  xorps   xmm0, xmm0
0x18007e0be  mov     [rsp+2E0h+var_268], ebx
0x18007e0c2  mov     edx, r15d; nBar
0x18007e0c5  mov     dword ptr [rsp+2E0h+pitem], 1Ch
0x18007e0cd  movdqu  [rsp+2E0h+pitem+8], xmm0
0x18007e0d3  mov     dword ptr [rsp+2E0h+pitem+4], 4
0x18007e0db  call    cs:__imp_GetScrollInfo
0x18007e0e1  test    eax, eax
0x18007e0e3  jz      short loc_18007E0E9
0x18007e0e5  mov     ebx, [rsp+2E0h+var_26C]
0x18007e0e9  xor     r8d, r8d
0x18007e0ec  mov     edx, ebx
0x18007e0ee  mov     rcx, rdi
0x18007e0f1  call    TV_SmoothSetTopItem
0x18007e0f6  test    eax, eax
0x18007e0f8  jz      short loc_18007E103
0x18007e0fa  mov     rcx, [rdi]; hWnd
0x18007e0fd  call    cs:__imp_UpdateWindow
0x18007e103  mov     rsi, [rdi+48h]
0x18007e107  test    rsi, rsi
0x18007e10a  jz      short loc_18007E13C
0x18007e10c  mov     rsi, [rsi]
0x18007e10f  cmp     r14, rsi
0x18007e112  jnz     short loc_18007E131
0x18007e114  mov     rbx, [rdi+48h]
0x18007e118  mov     r8d, r15d
0x18007e11b  mov     rdx, rbx
0x18007e11e  mov     rcx, rdi
0x18007e121  call    TV_ExpandParents
0x18007e126  mov     rdx, rbx
0x18007e129  mov     rcx, rdi
0x18007e12c  call    TV_ScrollIntoView
0x18007e131  test    rsi, rsi
0x18007e134  jz      short loc_18007E13C
0x18007e136  cmp     rsi, [rdi+40h]
0x18007e13a  jnz     short loc_18007E10C
0x18007e13c  mov     rdx, [rdi]
0x18007e13f  xor     r9d, r9d
0x18007e142  mov     ecx, 8004h
0x18007e147  lea     r8d, [r9-4]
0x18007e14b  call    MyNotifyWinEvent
0x18007e150  mov     eax, r15d
0x18007e153  jmp     short loc_18007E157
0x18007e155  xor     eax, eax
0x18007e157  mov     rcx, [rbp+1E0h+var_40]
0x18007e15e  xor     rcx, rsp; StackCookie
0x18007e161  call    __security_check_cookie
0x18007e166  mov     rbx, [rsp+2E0h+arg_10]
0x18007e16e  add     rsp, 2B0h
0x18007e175  pop     r15
0x18007e177  pop     r14
0x18007e179  pop     r13
0x18007e17b  pop     r12
0x18007e17d  pop     rdi
0x18007e17e  pop     rsi
0x18007e17f  pop     rbp
0x18007e180  retn
```
