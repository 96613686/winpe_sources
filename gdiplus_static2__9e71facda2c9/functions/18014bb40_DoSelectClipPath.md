# DoSelectClipPath

- ea: `0x18014bb40`
- end: `0x18014bde9`
- name: `DoSelectClipPath`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1801485e0`

## callees

- `0x1800c5768`
- `0x1800c6048`
- `0x1800c807c`
- `0x1800c87fc`
- `0x1801470b8`
- `0x1801471ec`
- `0x18014b3a4`
- `0x18014bb40`

## import_xrefs

- `GDI32!SelectClipPath` at `0x18014bd9c`
- `GDI32!SelectClipPath` at `0x18014bd9c`
- `GDI32!ExtSelectClipRgn` at `0x18014bd71`
- `GDI32!ExtSelectClipRgn` at `0x18014bd71`
- `GDI32!MoveToEx` at `0x18014bc53`
- `GDI32!MoveToEx` at `0x18014bc6f`
- `GDI32!MoveToEx` at `0x18014bc53`
- `GDI32!MoveToEx` at `0x18014bc6f`
- `GDI32!SetROP2` at `0x18014bc20`
- `GDI32!SetROP2` at `0x18014bc20`
- `GDI32!GetROP2` at `0x18014bbb1`
- `GDI32!GetROP2` at `0x18014bbb1`
- `GDI32!DeleteObject` at `0x18014bd82`
- `GDI32!DeleteObject` at `0x18014bd82`
- `GDI32!CreateRectRgn` at `0x18014bd4c`
- `GDI32!CreateRectRgn` at `0x18014bd4c`

## pseudocode

```c
__int64 __fastcall DoSelectClipPath(__int64 a1, int a2)
{
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  HDC v7; // rcx
  int ROP2; // eax
  int v9; // ebx
  __int64 result; // rax
  int v11; // r14d
  HRGN RectRgn; // rax
  HRGN v13; // rbp
  int v14; // ebx
  __int16 v15; // [rsp+68h] [rbp+10h] BYREF

  v4 = bNoDCRgn(a1, 1);
  v5 = v4;
  if ( (((a2 - 1) & 0xFFFFFFFB) == 0 || a2 == 2 && v4) && (*(_BYTE *)(a1 + 4) & 0x10) != 0 )
  {
    v6 = *(_DWORD *)(a1 + 484);
    switch ( v6 )
    {
      case 0:
        v7 = *(HDC *)(a1 + 40);
        *(_DWORD *)(a1 + 488) = *(_DWORD *)(a1 + 452);
        *(_DWORD *)(a1 + 484) = 1;
        ROP2 = GetROP2(v7);
        v9 = ROP2;
        if ( ROP2 != 13 && ROP2 != 4 )
        {
          *(_DWORD *)(a1 + 4) |= 0x40000000u;
          return 0;
        }
        if ( !(unsigned int)DoSaveDC(a1) )
          return 0;
        *(_DWORD *)(a1 + 472) = v9;
        v15 = 1;
        if ( !(unsigned int)bEmitWin16Escape(a1, 38, 2, &v15) )
          return 0;
        SetROP2(*(HDC *)(a1 + 40), 7);
        if ( !(unsigned int)bW16Emit1(a1, 260, 7) )
          return 0;
        MoveToEx(*(HDC *)(a1 + 40), 0, 0, (LPPOINT)(a1 + 476));
        MoveToEx(*(HDC *)(a1 + 40), *(_DWORD *)(a1 + 476), *(_DWORD *)(a1 + 480), 0);
        *(_QWORD *)(a1 + 536) = *(_QWORD *)(a1 + 504);
        return 1;
      case 1:
        *(_QWORD *)(a1 + 536) = *(_QWORD *)(a1 + 504);
        return 1;
      case 3:
        return (unsigned int)ConvertPathToPSClipPath(a1, 0)
            && (unsigned int)bW16Emit5(a1, 1574, 262, 20560, 20052, 6, 15);
    }
  }
  v11 = 0;
  if ( (unsigned int)ConvertPathToPSClipPath(a1, 1) )
  {
    ++*(_DWORD *)(a1 + 456);
    v15 = 1;
    v11 = 1;
    if ( !(unsigned int)bEmitWin16Escape(a1, 38, 2, &v15) )
      return 0;
  }
  if ( (unsigned int)(a2 - 2) <= 2 )
  {
    if ( v5 )
    {
      RectRgn = CreateRectRgn(-32768, -32768, 0x7FFF, 0x7FFF);
      v13 = RectRgn;
      if ( !RectRgn )
        return 0;
      v14 = ExtSelectClipRgn(*(HDC *)(a1 + 40), RectRgn, 5);
      DeleteObject(v13);
      if ( !v14 )
        return 0;
    }
  }
  if ( !SelectClipPath(*(HDC *)(a1 + 40), a2) )
    return 0;
  result = bDumpDCClipping(a1);
  if ( v11 )
  {
    v15 = 0;
    return (unsigned int)bEmitWin16Escape(a1, 38, 2, &v15) != 0 ? (unsigned int)result : 0;
  }
  return result;
}

```

## disassembly

```asm
0x18014bb40  mov     [rsp+arg_0], rbx
0x18014bb45  mov     [rsp+arg_10], rbp
0x18014bb4a  push    rsi
0x18014bb4b  push    rdi
0x18014bb4c  push    r14
0x18014bb4e  sub     rsp, 40h
0x18014bb52  mov     esi, edx
0x18014bb54  mov     ebp, 1
0x18014bb59  mov     edx, ebp
0x18014bb5b  mov     rdi, rcx
0x18014bb5e  call    bNoDCRgn
0x18014bb63  lea     r8d, [rsi-1]
0x18014bb67  mov     ebx, eax
0x18014bb69  test    r8d, 0FFFFFFFBh
0x18014bb70  jz      short loc_18014BB83
0x18014bb72  cmp     esi, 2
0x18014bb75  jnz     loc_18014BCF3
0x18014bb7b  test    eax, eax
0x18014bb7d  jz      loc_18014BCF3
0x18014bb83  test    byte ptr [rdi+4], 10h
0x18014bb87  jz      loc_18014BCF3
0x18014bb8d  mov     eax, [rdi+1E4h]
0x18014bb93  test    eax, eax
0x18014bb95  jnz     loc_18014BC90
0x18014bb9b  mov     eax, [rdi+1C4h]
0x18014bba1  mov     rcx, [rdi+28h]; hdc
0x18014bba5  mov     [rdi+1E8h], eax
0x18014bbab  mov     [rdi+1E4h], ebp
0x18014bbb1  call    cs:__imp_GetROP2
0x18014bbb8  nop     dword ptr [rax+rax+00h]
0x18014bbbd  mov     ebx, eax
0x18014bbbf  cmp     eax, 0Dh
0x18014bbc2  jz      short loc_18014BBE4
0x18014bbc4  cmp     eax, 4
0x18014bbc7  jz      short loc_18014BBE4
0x18014bbc9  bts     dword ptr [rdi+4], 1Eh
0x18014bbce  xor     eax, eax
0x18014bbd0  mov     rbx, [rsp+58h+arg_0]
0x18014bbd5  mov     rbp, [rsp+58h+arg_10]
0x18014bbda  add     rsp, 40h
0x18014bbde  pop     r14
0x18014bbe0  pop     rdi
0x18014bbe1  pop     rsi
0x18014bbe2  retn
0x18014bbe4  mov     rcx, rdi
0x18014bbe7  call    DoSaveDC
0x18014bbec  test    eax, eax
0x18014bbee  jz      short loc_18014BBCE
0x18014bbf0  mov     edx, 26h ; '&'
0x18014bbf5  mov     [rdi+1D8h], ebx
0x18014bbfb  lea     r9, [rsp+58h+arg_8]
0x18014bc00  mov     [rsp+58h+arg_8], bp
0x18014bc05  mov     rcx, rdi
0x18014bc08  lea     r8d, [rdx-24h]
0x18014bc0c  call    bEmitWin16Escape
0x18014bc11  test    eax, eax
0x18014bc13  jz      short loc_18014BBCE
0x18014bc15  mov     rcx, [rdi+28h]; hdc
0x18014bc19  mov     ebx, 7
0x18014bc1e  mov     edx, ebx; rop2
0x18014bc20  call    cs:__imp_SetROP2
0x18014bc27  nop     dword ptr [rax+rax+00h]
0x18014bc2c  mov     r8d, ebx
0x18014bc2f  mov     edx, 104h
0x18014bc34  mov     rcx, rdi
0x18014bc37  call    bW16Emit1
0x18014bc3c  test    eax, eax
0x18014bc3e  jz      short loc_18014BBCE
0x18014bc40  mov     rcx, [rdi+28h]; hdc
0x18014bc44  lea     rbx, [rdi+1DCh]
0x18014bc4b  mov     r9, rbx; lppt
0x18014bc4e  xor     r8d, r8d; y
0x18014bc51  xor     edx, edx; x
0x18014bc53  call    cs:__imp_MoveToEx
0x18014bc5a  nop     dword ptr [rax+rax+00h]
0x18014bc5f  mov     r8d, [rdi+1E0h]; y
0x18014bc66  xor     r9d, r9d; lppt
0x18014bc69  mov     edx, [rbx]; x
0x18014bc6b  mov     rcx, [rdi+28h]; hdc
0x18014bc6f  call    cs:__imp_MoveToEx
0x18014bc76  nop     dword ptr [rax+rax+00h]
0x18014bc7b  mov     rcx, [rdi+1F8h]
0x18014bc82  mov     [rdi+218h], rcx
0x18014bc89  mov     eax, ebp
0x18014bc8b  jmp     loc_18014BBD0
0x18014bc90  cmp     eax, ebp
0x18014bc92  jnz     short loc_18014BCA4
0x18014bc94  mov     rax, [rdi+1F8h]
0x18014bc9b  mov     [rdi+218h], rax
0x18014bca2  jmp     short loc_18014BC89
0x18014bca4  cmp     eax, 3
0x18014bca7  jnz     short loc_18014BCF3
0x18014bca9  xor     edx, edx
0x18014bcab  mov     rcx, rdi
0x18014bcae  call    ConvertPathToPSClipPath
0x18014bcb3  test    eax, eax
0x18014bcb5  jz      loc_18014BBCE
0x18014bcbb  mov     [rsp+58h+var_28], 0Fh
0x18014bcc2  mov     edx, 626h
0x18014bcc7  mov     [rsp+58h+var_30], 6
0x18014bcce  mov     r9d, 5050h
0x18014bcd4  mov     r8d, 106h
0x18014bcda  mov     [rsp+58h+var_38], 4E54h
0x18014bce1  mov     rcx, rdi
0x18014bce4  call    bW16Emit5
0x18014bce9  test    eax, eax
0x18014bceb  jz      loc_18014BBCE
0x18014bcf1  jmp     short loc_18014BC89
0x18014bcf3  mov     edx, ebp
0x18014bcf5  mov     rcx, rdi
0x18014bcf8  xor     r14d, r14d
0x18014bcfb  call    ConvertPathToPSClipPath
0x18014bd00  test    eax, eax
0x18014bd02  jz      short loc_18014BD30
0x18014bd04  add     [rdi+1C8h], ebp
0x18014bd0a  lea     r9, [rsp+58h+arg_8]
0x18014bd0f  mov     edx, 26h ; '&'
0x18014bd14  mov     [rsp+58h+arg_8], bp
0x18014bd19  mov     rcx, rdi
0x18014bd1c  mov     r14d, ebp
0x18014bd1f  lea     r8d, [rdx-24h]
0x18014bd23  call    bEmitWin16Escape
0x18014bd28  test    eax, eax
0x18014bd2a  jz      loc_18014BBCE
0x18014bd30  lea     eax, [rsi-2]
0x18014bd33  cmp     eax, 2
0x18014bd36  ja      short loc_18014BD96
0x18014bd38  test    ebx, ebx
0x18014bd3a  jz      short loc_18014BD96
0x18014bd3c  mov     r8d, 7FFFh; x2
0x18014bd42  mov     ecx, 0FFFF8000h; x1
0x18014bd47  mov     r9d, r8d; y2
0x18014bd4a  mov     edx, ecx; y1
0x18014bd4c  call    cs:__imp_CreateRectRgn
0x18014bd53  nop     dword ptr [rax+rax+00h]
0x18014bd58  mov     rbp, rax
0x18014bd5b  test    rax, rax
0x18014bd5e  jz      loc_18014BBCE
0x18014bd64  mov     rcx, [rdi+28h]; hdc
0x18014bd68  mov     r8d, 5; mode
0x18014bd6e  mov     rdx, rax; hrgn
0x18014bd71  call    cs:__imp_ExtSelectClipRgn
0x18014bd78  nop     dword ptr [rax+rax+00h]
0x18014bd7d  mov     rcx, rbp; ho
0x18014bd80  mov     ebx, eax
0x18014bd82  call    cs:__imp_DeleteObject
0x18014bd89  nop     dword ptr [rax+rax+00h]
0x18014bd8e  test    ebx, ebx
0x18014bd90  jz      loc_18014BBCE
0x18014bd96  mov     rcx, [rdi+28h]; hdc
0x18014bd9a  mov     edx, esi; mode
0x18014bd9c  call    cs:__imp_SelectClipPath
0x18014bda3  nop     dword ptr [rax+rax+00h]
0x18014bda8  test    eax, eax
0x18014bdaa  jz      loc_18014BBCE
0x18014bdb0  mov     rcx, rdi
0x18014bdb3  call    bDumpDCClipping
0x18014bdb8  mov     ebx, eax
0x18014bdba  test    r14d, r14d
0x18014bdbd  jz      loc_18014BBD0
0x18014bdc3  xor     ecx, ecx
0x18014bdc5  lea     r9, [rsp+58h+arg_8]
0x18014bdca  mov     [rsp+58h+arg_8], cx
0x18014bdcf  lea     edx, [rcx+26h]
0x18014bdd2  lea     r8d, [rcx+2]
0x18014bdd6  mov     rcx, rdi
0x18014bdd9  call    bEmitWin16Escape
0x18014bdde  neg     eax
0x18014bde0  sbb     eax, eax
0x18014bde2  and     eax, ebx
0x18014bde4  jmp     loc_18014BBD0
```
