# CCDrawInsertMark

- ea: `0x18011e494`
- end: `0x18011e6df`
- name: `CCDrawInsertMark`
- size: `587`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180015eb8`
- `0x18001cf08`
- `0x18002e5a0`

## callees

- `0x180114520`
- `0x18011e494`

## import_xrefs

- `GDI32!DeleteObject` at `0x18011e6b5`
- `GDI32!DeleteObject` at `0x18011e6b5`
- `GDI32!SelectObject` at `0x18011e4ec`
- `GDI32!SelectObject` at `0x18011e6ac`
- `GDI32!SelectObject` at `0x18011e4ec`
- `GDI32!SelectObject` at `0x18011e6ac`
- `GDI32!CreatePen` at `0x18011e4cc`
- `GDI32!CreatePen` at `0x18011e4cc`
- `GDI32!GetStockObject` at `0x18011e4dd`
- `GDI32!GetStockObject` at `0x18011e4dd`
- `GDI32!Polyline` at `0x18011e567`
- `GDI32!Polyline` at `0x18011e59e`
- `GDI32!Polyline` at `0x18011e634`
- `GDI32!Polyline` at `0x18011e66a`
- `GDI32!Polyline` at `0x18011e69f`
- `GDI32!Polyline` at `0x18011e567`
- `GDI32!Polyline` at `0x18011e59e`
- `GDI32!Polyline` at `0x18011e634`
- `GDI32!Polyline` at `0x18011e66a`
- `GDI32!Polyline` at `0x18011e69f`

## pseudocode

```c
BOOL __fastcall CCDrawInsertMark(HDC hdc, LONG *a2, int a3, COLORREF a4)
{
  void *Pen; // r12
  LONG v8; // r9d
  int v9; // eax
  LONG v10; // r8d
  LONG v11; // r14d
  int v12; // eax
  LONG v13; // eax
  LONG v14; // r9d
  int v15; // eax
  LONG v16; // r8d
  LONG v17; // r14d
  int v18; // eax
  LONG v19; // eax
  HGDIOBJ h; // [rsp+20h] [rbp-30h]
  POINT apt; // [rsp+28h] [rbp-28h] BYREF
  LONG v23; // [rsp+30h] [rbp-20h]
  int v24; // [rsp+34h] [rbp-1Ch]
  int v25; // [rsp+38h] [rbp-18h]
  int v26; // [rsp+3Ch] [rbp-14h]
  LONG x; // [rsp+40h] [rbp-10h]
  LONG y; // [rsp+44h] [rbp-Ch]

  Pen = CreatePen(0, 1, a4);
  if ( !Pen )
    Pen = GetStockObject(7);
  h = SelectObject(hdc, Pen);
  if ( a3 )
  {
    v8 = *a2;
    v9 = a2[2] - *a2;
    if ( v9 > 6 )
    {
      v10 = a2[1];
      if ( a2[3] - v10 > 3 )
      {
        v24 = a2[1];
        v26 = v10;
        v11 = v9 / 2 + v8;
        x = v11;
        apt.y = v10 + 2;
        y = v10 + 2;
        apt.x = v11 + 1;
        v23 = v11 + 3;
        v25 = v11 - 2;
        Polyline(hdc, &apt, 4);
        v12 = a2[3] - 1;
        apt.y = a2[1];
        y = apt.y;
        v24 = v12;
        v26 = v12;
        apt.x = v11;
        v23 = v11;
        v25 = v11 + 1;
        x = v11 + 1;
        Polyline(hdc, &apt, 4);
        v13 = a2[3];
        apt.x = v11 + 1;
        v23 = v11 + 3;
        v25 = v11 - 2;
        x = v11;
        apt.y = v13 - 3;
        v24 = v13 - 1;
        v26 = v13 - 1;
        y = v13 - 3;
LABEL_10:
        Polyline(hdc, &apt, 4);
      }
    }
  }
  else
  {
    v14 = a2[1];
    v15 = a2[3] - v14;
    if ( v15 > 6 )
    {
      v16 = *a2;
      if ( a2[2] - *a2 > 3 )
      {
        v23 = *a2;
        v25 = v16;
        v17 = v15 / 2 + v14;
        apt.y = v17;
        apt.x = v16 + 2;
        x = v16 + 2;
        v24 = v17 - 2;
        v26 = v17 + 3;
        y = v17 + 1;
        Polyline(hdc, &apt, 4);
        v18 = a2[2] - 1;
        apt.x = *a2;
        x = apt.x;
        v23 = v18;
        v25 = v18;
        apt.y = v17;
        v24 = v17;
        v26 = v17 + 1;
        y = v17 + 1;
        Polyline(hdc, &apt, 4);
        v19 = a2[2];
        apt.y = v17;
        v24 = v17 - 2;
        v26 = v17 + 3;
        y = v17 + 1;
        apt.x = v19 - 3;
        v23 = v19 - 1;
        v25 = v19 - 1;
        x = v19 - 3;
        goto LABEL_10;
      }
    }
  }
  SelectObject(hdc, h);
  return DeleteObject(Pen);
}

```

## disassembly

```asm
0x18011e494  mov     [rsp-38h+arg_8], rbx
0x18011e499  push    rbp
0x18011e49a  push    rsi
0x18011e49b  push    rdi
0x18011e49c  push    r12
0x18011e49e  push    r13
0x18011e4a0  push    r14
0x18011e4a2  push    r15
0x18011e4a4  mov     rbp, rsp
0x18011e4a7  sub     rsp, 50h
0x18011e4ab  mov     rax, cs:__security_cookie
0x18011e4b2  xor     rax, rsp
0x18011e4b5  mov     [rbp+var_8], rax
0x18011e4b9  mov     ebx, r8d
0x18011e4bc  mov     r15, rdx
0x18011e4bf  mov     r13, rcx
0x18011e4c2  mov     r8d, r9d; color
0x18011e4c5  mov     edx, 1; cWidth
0x18011e4ca  xor     ecx, ecx; iStyle
0x18011e4cc  call    cs:__imp_CreatePen
0x18011e4d2  mov     r12, rax
0x18011e4d5  test    rax, rax
0x18011e4d8  jnz     short loc_18011E4E6
0x18011e4da  lea     ecx, [rax+7]; i
0x18011e4dd  call    cs:__imp_GetStockObject
0x18011e4e3  mov     r12, rax
0x18011e4e6  mov     rdx, r12; h
0x18011e4e9  mov     rcx, r13; hdc
0x18011e4ec  call    cs:__imp_SelectObject
0x18011e4f2  mov     [rbp+h], rax
0x18011e4f6  test    ebx, ebx
0x18011e4f8  jz      loc_18011E5CB
0x18011e4fe  mov     eax, [r15+8]
0x18011e502  mov     r9d, [r15]
0x18011e505  sub     eax, r9d
0x18011e508  cmp     eax, 6
0x18011e50b  jle     loc_18011E6A5
0x18011e511  mov     ecx, [r15+0Ch]
0x18011e515  mov     r8d, [r15+4]
0x18011e519  sub     ecx, r8d
0x18011e51c  cmp     ecx, 3
0x18011e51f  jle     loc_18011E6A5
0x18011e525  cdq
0x18011e526  mov     [rbp+var_1C], r8d
0x18011e52a  mov     ecx, 2
0x18011e52f  mov     [rbp+var_14], r8d
0x18011e533  idiv    ecx
0x18011e535  lea     rdx, [rbp+apt]; apt
0x18011e539  lea     r14d, [rax+r9]
0x18011e53d  lea     eax, [r8+2]
0x18011e541  mov     [rbp+var_10], r14d
0x18011e545  lea     r8d, [rcx+2]; cpt
0x18011e549  mov     [rbp+apt.y], eax
0x18011e54c  lea     ebx, [r14+1]
0x18011e550  mov     [rbp+var_C], eax
0x18011e553  lea     edi, [r14+3]
0x18011e557  mov     [rbp+apt.x], ebx
0x18011e55a  lea     esi, [r14-2]
0x18011e55e  mov     [rbp+var_20], edi
0x18011e561  mov     rcx, r13; hdc
0x18011e564  mov     [rbp+var_18], esi
0x18011e567  call    cs:__imp_Polyline
0x18011e56d  mov     ecx, [r15+4]
0x18011e571  lea     rdx, [rbp+apt]; apt
0x18011e575  mov     eax, [r15+0Ch]
0x18011e579  mov     r8d, 4; cpt
0x18011e57f  dec     eax
0x18011e581  mov     [rbp+apt.y], ecx
0x18011e584  mov     [rbp+var_C], ecx
0x18011e587  mov     rcx, r13; hdc
0x18011e58a  mov     [rbp+var_1C], eax
0x18011e58d  mov     [rbp+var_14], eax
0x18011e590  mov     [rbp+apt.x], r14d
0x18011e594  mov     [rbp+var_20], r14d
0x18011e598  mov     [rbp+var_18], ebx
0x18011e59b  mov     [rbp+var_10], ebx
0x18011e59e  call    cs:__imp_Polyline
0x18011e5a4  mov     eax, [r15+0Ch]
0x18011e5a8  mov     [rbp+apt.x], ebx
0x18011e5ab  mov     [rbp+var_20], edi
0x18011e5ae  mov     [rbp+var_18], esi
0x18011e5b1  lea     ecx, [rax-3]
0x18011e5b4  mov     [rbp+var_10], r14d
0x18011e5b8  dec     eax
0x18011e5ba  mov     [rbp+apt.y], ecx
0x18011e5bd  mov     [rbp+var_1C], eax
0x18011e5c0  mov     [rbp+var_14], eax
0x18011e5c3  mov     [rbp+var_C], ecx
0x18011e5c6  jmp     loc_18011E692
0x18011e5cb  mov     eax, [r15+0Ch]
0x18011e5cf  mov     r9d, [r15+4]
0x18011e5d3  sub     eax, r9d
0x18011e5d6  cmp     eax, 6
0x18011e5d9  jle     loc_18011E6A5
0x18011e5df  mov     ecx, [r15+8]
0x18011e5e3  mov     r8d, [r15]
0x18011e5e6  sub     ecx, r8d
0x18011e5e9  cmp     ecx, 3
0x18011e5ec  jle     loc_18011E6A5
0x18011e5f2  cdq
0x18011e5f3  mov     [rbp+var_20], r8d
0x18011e5f7  mov     ecx, 2
0x18011e5fc  mov     [rbp+var_18], r8d
0x18011e600  idiv    ecx
0x18011e602  lea     rdx, [rbp+apt]; apt
0x18011e606  lea     r14d, [rax+r9]
0x18011e60a  lea     eax, [r8+2]
0x18011e60e  mov     [rbp+apt.y], r14d
0x18011e612  lea     r8d, [rcx+2]; cpt
0x18011e616  mov     [rbp+apt.x], eax
0x18011e619  lea     esi, [r14-2]
0x18011e61d  mov     [rbp+var_10], eax
0x18011e620  lea     edi, [r14+3]
0x18011e624  mov     [rbp+var_1C], esi
0x18011e627  lea     ebx, [r14+1]
0x18011e62b  mov     [rbp+var_14], edi
0x18011e62e  mov     rcx, r13; hdc
0x18011e631  mov     [rbp+var_C], ebx
0x18011e634  call    cs:__imp_Polyline
0x18011e63a  mov     ecx, [r15]
0x18011e63d  lea     rdx, [rbp+apt]; apt
0x18011e641  mov     eax, [r15+8]
0x18011e645  mov     r8d, 4; cpt
0x18011e64b  dec     eax
0x18011e64d  mov     [rbp+apt.x], ecx
0x18011e650  mov     [rbp+var_10], ecx
0x18011e653  mov     rcx, r13; hdc
0x18011e656  mov     [rbp+var_20], eax
0x18011e659  mov     [rbp+var_18], eax
0x18011e65c  mov     [rbp+apt.y], r14d
0x18011e660  mov     [rbp+var_1C], r14d
0x18011e664  mov     [rbp+var_14], ebx
0x18011e667  mov     [rbp+var_C], ebx
0x18011e66a  call    cs:__imp_Polyline
0x18011e670  mov     eax, [r15+8]
0x18011e674  mov     [rbp+apt.y], r14d
0x18011e678  mov     [rbp+var_1C], esi
0x18011e67b  mov     [rbp+var_14], edi
0x18011e67e  lea     edx, [rax-3]
0x18011e681  mov     [rbp+var_C], ebx
0x18011e684  dec     eax
0x18011e686  mov     [rbp+apt.x], edx
0x18011e689  mov     [rbp+var_20], eax
0x18011e68c  mov     [rbp+var_18], eax
0x18011e68f  mov     [rbp+var_10], edx
0x18011e692  mov     r8d, 4; cpt
0x18011e698  lea     rdx, [rbp+apt]; apt
0x18011e69c  mov     rcx, r13; hdc
0x18011e69f  call    cs:__imp_Polyline
0x18011e6a5  mov     rdx, [rbp+h]; h
0x18011e6a9  mov     rcx, r13; hdc
0x18011e6ac  call    cs:__imp_SelectObject
0x18011e6b2  mov     rcx, r12; ho
0x18011e6b5  call    cs:__imp_DeleteObject
0x18011e6bb  mov     rcx, [rbp+var_8]
0x18011e6bf  xor     rcx, rsp; StackCookie
0x18011e6c2  call    __security_check_cookie
0x18011e6c7  mov     rbx, [rsp+50h+arg_8]
0x18011e6cf  add     rsp, 50h
0x18011e6d3  pop     r15
0x18011e6d5  pop     r14
0x18011e6d7  pop     r13
0x18011e6d9  pop     r12
0x18011e6db  pop     rdi
0x18011e6dc  pop     rsi
0x18011e6dd  pop     rbp
0x18011e6de  retn
```
