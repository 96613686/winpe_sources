# FlatSB_Internal_DrawInvertScrollArea

- ea: `0x18003272c`
- end: `0x180032864`
- name: `FlatSB_Internal_DrawInvertScrollArea`
- size: `312`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180032f20`
- `0x180033c40`

## callees

- `0x1800197bc`
- `0x180031efc`
- `0x18003272c`

## import_xrefs

- `USER32!ReleaseDC` at `0x18003277e`
- `USER32!ReleaseDC` at `0x180032853`
- `USER32!ReleaseDC` at `0x18003277e`
- `USER32!ReleaseDC` at `0x180032853`
- `USER32!GetWindowDC` at `0x180032763`
- `USER32!GetWindowDC` at `0x1800327bc`
- `USER32!GetWindowDC` at `0x180032763`
- `USER32!GetWindowDC` at `0x1800327bc`
- `USER32!IsRectEmpty` at `0x180032756`
- `USER32!IsRectEmpty` at `0x180032756`
- `USER32!InvertRect` at `0x180032772`
- `USER32!InvertRect` at `0x180032772`

## pseudocode

```c
int __fastcall FlatSB_Internal_DrawInvertScrollArea(__int64 a1, int a2, unsigned int a3)
{
  HWND v3; // rbp
  const RECT *v7; // r14
  HDC v8; // rbx
  HDC WindowDC; // rax
  int v11; // edx
  HDC v12; // r14
  __int64 v13; // rax
  int v14; // ecx
  bool v15; // cf
  __int64 v16; // rdx
  UINT v17; // r9d
  bool v18; // zf

  v3 = *(HWND *)(a1 + 264);
  if ( a3 <= 1 )
  {
    WindowDC = GetWindowDC(*(HWND *)(a1 + 264));
    v11 = *(_DWORD *)(a1 + 104);
    v12 = WindowDC;
    if ( a3 )
    {
      v18 = v11 == 0;
      v13 = 176;
      v16 = a1;
      v17 = 1;
      if ( v18 )
        v17 = 3;
      v14 = a2 != 0 ? 0x200 : 0;
    }
    else
    {
      v13 = a1;
      v14 = a2 != 0 ? 0x200 : 0;
      v15 = v11 != 0;
      v16 = 176;
      v17 = v15 ? 0 : 2;
    }
    FlatSB_Internal_DrawArrow((_DWORD *)a1, v12, (const RECT *)(v13 + v16), v17, v14);
    MyNotifyWinEvent(32778, *(_QWORD *)(a1 + 264), (unsigned int)(*(_DWORD *)(a1 + 104) != 0) - 6);
    return ReleaseDC(v3, v12);
  }
  else
  {
    v7 = (const RECT *)(a1 + 176);
    if ( !IsRectEmpty((const RECT *)(a1 + 176)) )
    {
      v8 = GetWindowDC(v3);
      InvertRect(v8, v7);
      ReleaseDC(v3, v8);
    }
    return MyNotifyWinEvent(32778, *(_QWORD *)(a1 + 264), (unsigned int)(*(_DWORD *)(a1 + 104) != 0) - 6);
  }
}

```

## disassembly

```asm
0x18003272c  push    rbx
0x18003272e  push    rbp
0x18003272f  push    rsi
0x180032730  push    rdi
0x180032731  push    r14
0x180032733  sub     rsp, 30h
0x180032737  mov     rbp, [rcx+108h]
0x18003273e  mov     esi, r8d
0x180032741  mov     ebx, edx
0x180032743  mov     rdi, rcx
0x180032746  cmp     r8d, 1
0x18003274a  jbe     short loc_1800327B9
0x18003274c  lea     r14, [rcx+0B0h]
0x180032753  mov     rcx, r14; lprc
0x180032756  call    cs:__imp_IsRectEmpty
0x18003275c  test    eax, eax
0x18003275e  jnz     short loc_180032784
0x180032760  mov     rcx, rbp; hWnd
0x180032763  call    cs:__imp_GetWindowDC
0x180032769  mov     rcx, rax; hDC
0x18003276c  mov     rdx, r14; lprc
0x18003276f  mov     rbx, rax
0x180032772  call    cs:__imp_InvertRect
0x180032778  mov     rdx, rbx; hDC
0x18003277b  mov     rcx, rbp; hWnd
0x18003277e  call    cs:__imp_ReleaseDC
0x180032784  mov     edx, 2
0x180032789  mov     ecx, 800Ah
0x18003278e  cmp     esi, edx
0x180032790  lea     eax, [rdx+2]
0x180032793  cmovnz  edx, eax
0x180032796  mov     eax, [rdi+68h]
0x180032799  neg     eax
0x18003279b  mov     r9d, edx
0x18003279e  mov     rdx, [rdi+108h]
0x1800327a5  sbb     r8d, r8d
0x1800327a8  neg     r8d
0x1800327ab  add     r8d, 0FFFFFFFAh
0x1800327af  call    MyNotifyWinEvent
0x1800327b4  jmp     loc_180032859
0x1800327b9  mov     rcx, rbp; hWnd
0x1800327bc  call    cs:__imp_GetWindowDC
0x1800327c2  mov     edx, [rdi+68h]
0x1800327c5  mov     r14, rax
0x1800327c8  test    esi, esi
0x1800327ca  jnz     short loc_1800327EC
0x1800327cc  neg     ebx
0x1800327ce  mov     rax, rdi
0x1800327d1  sbb     ecx, ecx
0x1800327d3  and     ecx, 200h
0x1800327d9  neg     edx
0x1800327db  mov     edx, 0B0h
0x1800327e0  sbb     r9d, r9d
0x1800327e3  not     r9d
0x1800327e6  and     r9d, 2
0x1800327ea  jmp     short loc_18003280E
0x1800327ec  test    edx, edx
0x1800327ee  mov     eax, 0B0h
0x1800327f3  mov     rdx, rdi
0x1800327f6  mov     r9d, 1
0x1800327fc  jnz     short loc_180032804
0x1800327fe  mov     r9d, 3
0x180032804  neg     ebx
0x180032806  sbb     ecx, ecx
0x180032808  and     ecx, 200h
0x18003280e  lea     r8, [rax+rdx]
0x180032812  mov     [rsp+58h+var_38], ecx
0x180032816  mov     rdx, r14
0x180032819  mov     rcx, rdi
0x18003281c  call    FlatSB_Internal_DrawArrow
0x180032821  mov     eax, [rdi+68h]
0x180032824  neg     esi
0x180032826  mov     rdx, [rdi+108h]
0x18003282d  mov     ecx, 800Ah
0x180032832  sbb     r9, r9
0x180032835  and     r9, 4
0x180032839  inc     r9
0x18003283c  neg     eax
0x18003283e  sbb     r8d, r8d
0x180032841  neg     r8d
0x180032844  add     r8d, 0FFFFFFFAh
0x180032848  call    MyNotifyWinEvent
0x18003284d  mov     rdx, r14; hDC
0x180032850  mov     rcx, rbp; hWnd
0x180032853  call    cs:__imp_ReleaseDC
0x180032859  add     rsp, 30h
0x18003285d  pop     r14
0x18003285f  pop     rdi
0x180032860  pop     rsi
0x180032861  pop     rbp
0x180032862  pop     rbx
0x180032863  retn
```
