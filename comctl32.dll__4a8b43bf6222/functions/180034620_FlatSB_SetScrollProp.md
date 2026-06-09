# FlatSB_SetScrollProp

- ea: `0x180034620`
- end: `0x180034872`
- name: `FlatSB_SetScrollProp`
- size: `594`
- prototype: `BOOL __stdcall(HWND, UINT index, INT_PTR newValue, BOOL)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180018090`
- `0x180030440`
- `0x180030800`
- `0x180032a90`
- `0x1800330c4`
- `0x180034620`

## import_xrefs

- `GDI32!DeleteObject` at `0x180034695`
- `GDI32!DeleteObject` at `0x1800346a2`
- `GDI32!DeleteObject` at `0x180034695`
- `GDI32!DeleteObject` at `0x1800346a2`
- `KERNEL32!LocalFree` at `0x1800346ab`
- `KERNEL32!LocalFree` at `0x1800346ab`
- `USER32!ReleaseDC` at `0x180034862`
- `USER32!ReleaseDC` at `0x180034862`
- `USER32!GetWindowDC` at `0x180034838`
- `USER32!GetWindowDC` at `0x180034838`

## pseudocode

```c
BOOL __stdcall FlatSB_SetScrollProp(HWND a1, UINT index, INT_PTR newValue, BOOL a4)
{
  DWORD_PTR v8; // rbx
  char *inited; // rax
  UINT v11; // esi
  UINT v12; // esi
  UINT v13; // esi
  UINT v14; // esi
  UINT v15; // esi
  unsigned int v16; // ebp
  int v17; // esi
  int v18; // edi
  HDC WindowDC; // r14
  DWORD_PTR pdwRefData[9]; // [rsp+20h] [rbp-48h] BYREF

  pdwRefData[0] = 0;
  GetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, pdwRefData);
  v8 = pdwRefData[0];
  if ( !pdwRefData[0] )
    return 0;
  if ( pdwRefData[0] == -1 )
  {
    inited = FlatSB_Internal_InitPwSB((__int64)a1);
    v8 = (DWORD_PTR)inited;
    if ( !inited )
      return 0;
    if ( !SetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, (DWORD_PTR)inited) )
    {
      DeleteObject(*(HGDIOBJ *)(v8 + 248));
      DeleteObject(*(HGDIOBJ *)(v8 + 240));
      LocalFree((HLOCAL)v8);
      return 0;
    }
    a4 = 0;
  }
  if ( *(_DWORD *)(v8 + 108) )
    return 0;
  if ( index > 0x40 )
  {
    v16 = 0;
    switch ( index )
    {
      case 0x80u:
        if ( (_DWORD)newValue == *(_DWORD *)(v8 + 216) )
          return 1;
        *(_DWORD *)(v8 + 216) = newValue;
        break;
      case 0x100u:
        if ( (_DWORD)newValue == *(_DWORD *)(v8 + 192) )
          return 1;
        *(_DWORD *)(v8 + 192) = newValue;
LABEL_32:
        v16 = 1;
        break;
      case 0x200u:
        if ( (_DWORD)newValue == *(_DWORD *)(v8 + 196) )
          return 1;
        *(_DWORD *)(v8 + 196) = newValue;
        break;
      case 0x800u:
        if ( newValue == *(_QWORD *)(v8 + 256) )
          return 1;
        *(_QWORD *)(v8 + 256) = newValue;
        break;
      case 0x1000u:
        if ( (_DWORD)newValue == *(_DWORD *)(v8 + 308) )
          return 1;
        *(_DWORD *)(v8 + 308) = newValue;
        break;
      default:
        return 0;
    }
    if ( a4 )
    {
      v17 = *(_DWORD *)(v8 + 208);
      if ( v16 )
        v18 = *(_DWORD *)(v8 + 112);
      else
        v18 = *(_DWORD *)(v8 + 116);
      WindowDC = GetWindowDC(a1);
      FlatSB_Internal_DrawScrollBar(v8, WindowDC, v16, 0);
      if ( !v18 )
        *(_DWORD *)(v8 + 208) = v17;
      ReleaseDC(a1, WindowDC);
    }
    return 1;
  }
  if ( index == 64 )
  {
    if ( (_DWORD)newValue == *(_DWORD *)(v8 + 212) )
      return 1;
    *(_DWORD *)(v8 + 212) = newValue;
    goto LABEL_32;
  }
  v11 = index - 1;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 2;
      if ( v13 )
      {
        v14 = v13 - 4;
        if ( v14 )
        {
          v15 = v14 - 8;
          if ( v15 )
          {
            if ( v15 != 16 )
              return 0;
            if ( (_DWORD)newValue != *(_DWORD *)(v8 + 332) )
            {
              *(_DWORD *)(v8 + 332) = newValue;
LABEL_29:
              CCInvalidateFrame(a1);
            }
          }
          else if ( (_DWORD)newValue != *(_DWORD *)(v8 + 320) )
          {
            *(_DWORD *)(v8 + 320) = newValue;
            goto LABEL_29;
          }
        }
        else if ( (_DWORD)newValue != *(_DWORD *)(v8 + 312) )
        {
          *(_DWORD *)(v8 + 312) = newValue;
          goto LABEL_29;
        }
      }
      else if ( (_DWORD)newValue != *(_DWORD *)(v8 + 328) )
      {
        *(_DWORD *)(v8 + 328) = newValue;
        goto LABEL_29;
      }
    }
    else if ( (_DWORD)newValue != *(_DWORD *)(v8 + 316) )
    {
      *(_DWORD *)(v8 + 316) = newValue;
      goto LABEL_29;
    }
  }
  else if ( (_DWORD)newValue != *(_DWORD *)(v8 + 324) )
  {
    *(_DWORD *)(v8 + 324) = newValue;
    goto LABEL_29;
  }
  return 1;
}

```

## disassembly

```asm
0x180034620  push    rbx
0x180034622  push    rbp
0x180034623  push    rsi
0x180034624  push    rdi
0x180034625  push    r14
0x180034627  push    r15
0x180034629  sub     rsp, 38h
0x18003462d  mov     r14d, r9d
0x180034630  mov     [rsp+68h+pdwRefData], 0
0x180034639  mov     rdi, r8
0x18003463c  lea     r9, [rsp+68h+pdwRefData]; pdwRefData
0x180034641  mov     esi, edx
0x180034643  xor     r8d, r8d; uIdSubclass
0x180034646  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x18003464d  mov     r15, rcx
0x180034650  call    GetWindowSubclass
0x180034655  mov     rbx, [rsp+68h+pdwRefData]
0x18003465a  test    rbx, rbx
0x18003465d  jz      short loc_1800346B1
0x18003465f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180034663  jnz     short loc_1800346C3
0x180034665  mov     rcx, r15
0x180034668  call    FlatSB_Internal_InitPwSB
0x18003466d  mov     rbx, rax
0x180034670  test    rax, rax
0x180034673  jz      short loc_1800346B1
0x180034675  mov     r9, rax; dwRefData
0x180034678  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x18003467f  xor     r8d, r8d; uIdSubclass
0x180034682  mov     rcx, r15; hWnd
0x180034685  call    SetWindowSubclass
0x18003468a  test    eax, eax
0x18003468c  jnz     short loc_1800346C0
0x18003468e  mov     rcx, [rbx+0F8h]; ho
0x180034695  call    cs:__imp_DeleteObject
0x18003469b  mov     rcx, [rbx+0F0h]; ho
0x1800346a2  call    cs:__imp_DeleteObject
0x1800346a8  mov     rcx, rbx; hMem
0x1800346ab  call    cs:__imp_LocalFree
0x1800346b1  xor     eax, eax
0x1800346b3  add     rsp, 38h
0x1800346b7  pop     r15
0x1800346b9  pop     r14
0x1800346bb  pop     rdi
0x1800346bc  pop     rsi
0x1800346bd  pop     rbp
0x1800346be  pop     rbx
0x1800346bf  retn
0x1800346c0  xor     r14d, r14d
0x1800346c3  cmp     dword ptr [rbx+6Ch], 0
0x1800346c7  jnz     short loc_1800346B1
0x1800346c9  cmp     esi, 40h ; '@'
0x1800346cc  ja      loc_180034795
0x1800346d2  jz      loc_180034779
0x1800346d8  sub     esi, 1
0x1800346db  jz      short loc_18003475A
0x1800346dd  sub     esi, 1
0x1800346e0  jz      short loc_180034746
0x1800346e2  sub     esi, 2
0x1800346e5  jz      short loc_180034732
0x1800346e7  sub     esi, 4
0x1800346ea  jz      short loc_18003471E
0x1800346ec  sub     esi, 8
0x1800346ef  jz      short loc_18003470A
0x1800346f1  cmp     esi, 10h
0x1800346f4  jnz     short loc_1800346B1
0x1800346f6  cmp     edi, [rbx+14Ch]
0x1800346fc  jz      loc_180034868
0x180034702  mov     [rbx+14Ch], edi
0x180034708  jmp     short loc_18003476C
0x18003470a  cmp     edi, [rbx+140h]
0x180034710  jz      loc_180034868
0x180034716  mov     [rbx+140h], edi
0x18003471c  jmp     short loc_18003476C
0x18003471e  cmp     edi, [rbx+138h]
0x180034724  jz      loc_180034868
0x18003472a  mov     [rbx+138h], edi
0x180034730  jmp     short loc_18003476C
0x180034732  cmp     edi, [rbx+148h]
0x180034738  jz      loc_180034868
0x18003473e  mov     [rbx+148h], edi
0x180034744  jmp     short loc_18003476C
0x180034746  cmp     edi, [rbx+13Ch]
0x18003474c  jz      loc_180034868
0x180034752  mov     [rbx+13Ch], edi
0x180034758  jmp     short loc_18003476C
0x18003475a  cmp     edi, [rbx+144h]
0x180034760  jz      loc_180034868
0x180034766  mov     [rbx+144h], edi
0x18003476c  mov     rcx, r15
0x18003476f  call    CCInvalidateFrame
0x180034774  jmp     loc_180034868
0x180034779  cmp     edi, [rbx+0D4h]
0x18003477f  jz      loc_180034868
0x180034785  mov     [rbx+0D4h], edi
0x18003478b  mov     ebp, 1
0x180034790  jmp     loc_18003481E
0x180034795  xor     ebp, ebp
0x180034797  cmp     esi, 80h
0x18003479d  jz      short loc_180034810
0x18003479f  cmp     esi, 100h
0x1800347a5  jz      short loc_1800347FD
0x1800347a7  cmp     esi, 200h
0x1800347ad  jz      short loc_1800347ED
0x1800347af  cmp     esi, 800h
0x1800347b5  jz      short loc_1800347D7
0x1800347b7  cmp     esi, 1000h
0x1800347bd  jnz     loc_1800346B1
0x1800347c3  cmp     edi, [rbx+134h]
0x1800347c9  jz      loc_180034868
0x1800347cf  mov     [rbx+134h], edi
0x1800347d5  jmp     short loc_18003481E
0x1800347d7  cmp     rdi, [rbx+100h]
0x1800347de  jz      loc_180034868
0x1800347e4  mov     [rbx+100h], rdi
0x1800347eb  jmp     short loc_18003481E
0x1800347ed  cmp     edi, [rbx+0C4h]
0x1800347f3  jz      short loc_180034868
0x1800347f5  mov     [rbx+0C4h], edi
0x1800347fb  jmp     short loc_18003481E
0x1800347fd  cmp     edi, [rbx+0C0h]
0x180034803  jz      short loc_180034868
0x180034805  mov     [rbx+0C0h], edi
0x18003480b  jmp     loc_18003478B
0x180034810  cmp     edi, [rbx+0D8h]
0x180034816  jz      short loc_180034868
0x180034818  mov     [rbx+0D8h], edi
0x18003481e  test    r14d, r14d
0x180034821  jz      short loc_180034868
0x180034823  mov     esi, [rbx+0D0h]
0x180034829  test    ebp, ebp
0x18003482b  jz      short loc_180034832
0x18003482d  mov     edi, [rbx+70h]
0x180034830  jmp     short loc_180034835
0x180034832  mov     edi, [rbx+74h]
0x180034835  mov     rcx, r15; hWnd
0x180034838  call    cs:__imp_GetWindowDC
0x18003483e  xor     r9d, r9d
0x180034841  mov     r8d, ebp
0x180034844  mov     rdx, rax
0x180034847  mov     rcx, rbx
0x18003484a  mov     r14, rax
0x18003484d  call    FlatSB_Internal_DrawScrollBar
0x180034852  test    edi, edi
0x180034854  jnz     short loc_18003485C
0x180034856  mov     [rbx+0D0h], esi
0x18003485c  mov     rdx, r14; hDC
0x18003485f  mov     rcx, r15; hWnd
0x180034862  call    cs:__imp_ReleaseDC
0x180034868  mov     eax, 1
0x18003486d  jmp     loc_1800346B3
```
