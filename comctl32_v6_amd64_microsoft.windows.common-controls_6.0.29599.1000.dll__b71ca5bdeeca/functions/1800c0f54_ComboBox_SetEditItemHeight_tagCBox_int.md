# ComboBox_SetEditItemHeight(tagCBox *,int)

- ea: `0x1800c0f54`
- end: `0x1800c112e`
- name: `?ComboBox_SetEditItemHeight@@YAJPEAUtagCBox@@H@Z`
- size: `474`
- prototype: `int(struct tagCBox *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800b36a0`

## callees

- `0x1800c0f54`
- `0x180114520`

## import_xrefs

- `USER32!SetWindowPos` at `0x1800c0ff4`
- `USER32!SetWindowPos` at `0x1800c0ff4`
- `USER32!MoveWindow` at `0x1800c1096`
- `USER32!MoveWindow` at `0x1800c10c8`
- `USER32!MoveWindow` at `0x1800c1109`
- `USER32!MoveWindow` at `0x1800c1096`
- `USER32!MoveWindow` at `0x1800c10c8`
- `USER32!MoveWindow` at `0x1800c1109`
- `USER32!GetWindowRect` at `0x1800c0fc0`
- `USER32!GetWindowRect` at `0x1800c1118`
- `USER32!GetWindowRect` at `0x1800c0fc0`
- `USER32!GetWindowRect` at `0x1800c1118`
- `USER32!GetSystemMetrics` at `0x1800c1028`
- `USER32!GetSystemMetrics` at `0x1800c1028`
- `UxTheme!GetThemeInt` at `0x1800c1056`
- `UxTheme!GetThemeInt` at `0x1800c1056`

## pseudocode

```c
__int64 __fastcall ComboBox_SetEditItemHeight(struct tagCBox *a1, int a2)
{
  int v4; // ecx
  bool v5; // zf
  HWND v6; // rcx
  HWND v7; // rcx
  int cy; // eax
  __int64 result; // rax
  int SystemMetrics; // eax
  void *v11; // rcx
  int v12; // edx
  int v13; // r9d
  HWND v14; // rcx
  HWND v15; // rcx
  int v16; // eax
  int v17; // r9d
  int v18; // r8d
  int piVal; // [rsp+40h] [rbp-28h] BYREF
  struct tagRECT Rect; // [rsp+48h] [rbp-20h] BYREF

  if ( a2 <= 255 )
  {
    v4 = a2 + *((_DWORD *)a1 + 7);
    *((_DWORD *)a1 + 9) = v4;
    v5 = (*((_BYTE *)a1 + 104) & 2) == 0;
    *((_DWORD *)a1 + 15) = *((_DWORD *)a1 + 21) + v4;
    if ( !v5 )
    {
      SystemMetrics = GetSystemMetrics(46);
      v11 = (void *)*((_QWORD *)a1 + 2);
      v12 = SystemMetrics;
      piVal = SystemMetrics;
      if ( v11 )
      {
        GetThemeInt(v11, 4, 1, 2403, &piVal);
        v12 = piVal;
      }
      *((_DWORD *)a1 + 13) = *((_DWORD *)a1 + 15) - v12;
    }
    if ( (*((_DWORD *)a1 + 26) & 0x4000) == 0 )
    {
      v14 = (HWND)*((_QWORD *)a1 + 11);
      if ( v14 )
        MoveWindow(v14, *((_DWORD *)a1 + 6), *((_DWORD *)a1 + 7), *((_DWORD *)a1 + 8) - *((_DWORD *)a1 + 6), a2, 1);
    }
    if ( (*((_DWORD *)a1 + 26) & 3) == 1 )
    {
      v15 = (HWND)*((_QWORD *)a1 + 12);
      if ( !v15 )
        goto LABEL_8;
      v16 = *((_DWORD *)a1 + 17);
      v17 = *((_DWORD *)a1 + 14);
      v18 = *((_DWORD *)a1 + 15);
      Rect = 0;
      MoveWindow(v15, 0, v18, v17, v16, 0);
      GetWindowRect(*((HWND *)a1 + 12), &Rect);
      cy = Rect.bottom + *((_DWORD *)a1 + 15) - Rect.top;
    }
    else
    {
      v6 = *(HWND *)a1;
      Rect = 0;
      GetWindowRect(v6, &Rect);
      v7 = (HWND)*((_QWORD *)a1 + 12);
      if ( v7 )
      {
        v13 = *((_DWORD *)a1 + 16);
        if ( v13 <= *((_DWORD *)a1 + 14) )
          v13 = *((_DWORD *)a1 + 14);
        MoveWindow(v7, Rect.left, *((_DWORD *)a1 + 15) + Rect.top, v13, *((_DWORD *)a1 + 17), 0);
      }
      cy = *((_DWORD *)a1 + 15);
    }
    SetWindowPos(*(HWND *)a1, 0, 0, 0, *((_DWORD *)a1 + 14), cy, 0x16u);
LABEL_8:
    result = 0;
    *(_OWORD *)((char *)a1 + 140) = *(_OWORD *)((char *)a1 + 24);
    return result;
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1800c0f54  mov     [rsp+arg_10], rbx
0x1800c0f59  push    rdi
0x1800c0f5a  sub     rsp, 60h
0x1800c0f5e  mov     rax, cs:__security_cookie
0x1800c0f65  xor     rax, rsp
0x1800c0f68  mov     [rsp+68h+var_10], rax
0x1800c0f6d  mov     edi, edx
0x1800c0f6f  mov     rbx, rcx
0x1800c0f72  cmp     edx, 0FFh
0x1800c0f78  jg      loc_1800C10D3
0x1800c0f7e  mov     ecx, [rcx+1Ch]
0x1800c0f81  add     ecx, edx
0x1800c0f83  mov     [rbx+24h], ecx
0x1800c0f86  add     ecx, [rbx+54h]
0x1800c0f89  test    byte ptr [rbx+68h], 2
0x1800c0f8d  mov     [rbx+3Ch], ecx
0x1800c0f90  jnz     loc_1800C1023
0x1800c0f96  test    dword ptr [rbx+68h], 4000h
0x1800c0f9d  jz      loc_1800C10A1
0x1800c0fa3  mov     eax, [rbx+68h]
0x1800c0fa6  and     al, 3
0x1800c0fa8  cmp     al, 1
0x1800c0faa  jz      loc_1800C10DB
0x1800c0fb0  mov     rcx, [rbx]; hWnd
0x1800c0fb3  lea     rdx, [rsp+68h+Rect]; lpRect
0x1800c0fb8  xorps   xmm0, xmm0
0x1800c0fbb  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x1800c0fc0  call    cs:__imp_GetWindowRect
0x1800c0fc6  mov     rcx, [rbx+60h]; hWnd
0x1800c0fca  test    rcx, rcx
0x1800c0fcd  jnz     loc_1800C106D
0x1800c0fd3  mov     eax, [rbx+3Ch]
0x1800c0fd6  mov     rcx, [rbx]; hWnd
0x1800c0fd9  xor     r9d, r9d; Y
0x1800c0fdc  mov     [rsp+68h+uFlags], 16h; uFlags
0x1800c0fe4  xor     r8d, r8d; X
0x1800c0fe7  mov     [rsp+68h+cy], eax; cy
0x1800c0feb  xor     edx, edx; hWndInsertAfter
0x1800c0fed  mov     eax, [rbx+38h]
0x1800c0ff0  mov     dword ptr [rsp+68h+piVal], eax; cx
0x1800c0ff4  call    cs:__imp_SetWindowPos
0x1800c0ffa  movups  xmm0, xmmword ptr [rbx+18h]
0x1800c0ffe  xor     eax, eax
0x1800c1000  movdqu  xmmword ptr [rbx+8Ch], xmm0
0x1800c1008  mov     rcx, [rsp+68h+var_10]
0x1800c100d  xor     rcx, rsp; StackCookie
0x1800c1010  call    __security_check_cookie
0x1800c1015  mov     rbx, [rsp+68h+arg_10]
0x1800c101d  add     rsp, 60h
0x1800c1021  pop     rdi
0x1800c1022  retn
0x1800c1023  mov     ecx, 2Eh ; '.'; nIndex
0x1800c1028  call    cs:__imp_GetSystemMetrics
0x1800c102e  mov     rcx, [rbx+10h]; hTheme
0x1800c1032  mov     edx, eax
0x1800c1034  mov     [rsp+68h+var_28], eax
0x1800c1038  test    rcx, rcx
0x1800c103b  jz      short loc_1800C1060
0x1800c103d  mov     edx, 4; iPartId
0x1800c1042  lea     rax, [rsp+68h+var_28]
0x1800c1047  mov     r9d, 963h; iPropId
0x1800c104d  mov     [rsp+68h+piVal], rax; piVal
0x1800c1052  lea     r8d, [rdx-3]; iStateId
0x1800c1056  call    cs:__imp_GetThemeInt
0x1800c105c  mov     edx, [rsp+68h+var_28]
0x1800c1060  mov     eax, [rbx+3Ch]
0x1800c1063  sub     eax, edx
0x1800c1065  mov     [rbx+34h], eax
0x1800c1068  jmp     loc_1800C0F96
0x1800c106d  mov     r9d, [rbx+40h]
0x1800c1071  cmp     r9d, [rbx+38h]
0x1800c1075  mov     r8d, [rsp+68h+Rect.top]
0x1800c107a  cmovle  r9d, [rbx+38h]; nWidth
0x1800c107f  mov     eax, [rbx+44h]
0x1800c1082  add     r8d, [rbx+3Ch]; Y
0x1800c1086  mov     edx, [rsp+68h+Rect.left]; X
0x1800c108a  mov     [rsp+68h+cy], 0; bRepaint
0x1800c1092  mov     dword ptr [rsp+68h+piVal], eax; nHeight
0x1800c1096  call    cs:__imp_MoveWindow
0x1800c109c  jmp     loc_1800C0FD3
0x1800c10a1  mov     rcx, [rbx+58h]; hWnd
0x1800c10a5  test    rcx, rcx
0x1800c10a8  jz      loc_1800C0FA3
0x1800c10ae  mov     r9d, [rbx+20h]
0x1800c10b2  mov     edx, [rbx+18h]; X
0x1800c10b5  sub     r9d, edx; nWidth
0x1800c10b8  mov     r8d, [rbx+1Ch]; Y
0x1800c10bc  mov     [rsp+68h+cy], 1; bRepaint
0x1800c10c4  mov     dword ptr [rsp+68h+piVal], edi; nHeight
0x1800c10c8  call    cs:__imp_MoveWindow
0x1800c10ce  jmp     loc_1800C0FA3
0x1800c10d3  or      eax, 0FFFFFFFFh
0x1800c10d6  jmp     loc_1800C1008
0x1800c10db  mov     rcx, [rbx+60h]; hWnd
0x1800c10df  test    rcx, rcx
0x1800c10e2  jz      loc_1800C0FFA
0x1800c10e8  mov     eax, [rbx+44h]
0x1800c10eb  xorps   xmm0, xmm0
0x1800c10ee  mov     r9d, [rbx+38h]; nWidth
0x1800c10f2  xor     edx, edx; X
0x1800c10f4  mov     r8d, [rbx+3Ch]; Y
0x1800c10f8  mov     [rsp+68h+cy], 0; bRepaint
0x1800c1100  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x1800c1105  mov     dword ptr [rsp+68h+piVal], eax; nHeight
0x1800c1109  call    cs:__imp_MoveWindow
0x1800c110f  mov     rcx, [rbx+60h]; hWnd
0x1800c1113  lea     rdx, [rsp+68h+Rect]; lpRect
0x1800c1118  call    cs:__imp_GetWindowRect
0x1800c111e  mov     eax, [rbx+3Ch]
0x1800c1121  sub     eax, [rsp+68h+Rect.top]
0x1800c1125  add     eax, [rsp+68h+Rect.bottom]
0x1800c1129  jmp     loc_1800C0FD6
```
