# mciSpecial

- ea: `0x1800062f8`
- end: `0x18000648c`
- name: `mciSpecial`
- size: `404`
- prototype: `__int64 __fastcall(LPARAM lParam)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000485c`

## callees

- `0x180004fdc`
- `0x1800050c0`
- `0x1800062f8`

## import_xrefs

- `USER32!PostMessageW` at `0x180006474`
- `USER32!PostMessageW` at `0x180006474`
- `USER32!LoadStringW` at `0x1800063c1`
- `USER32!LoadStringW` at `0x1800063e2`
- `USER32!LoadStringW` at `0x1800063c1`
- `USER32!LoadStringW` at `0x1800063e2`
- `WINMM!mciSetDriverData` at `0x180006449`
- `WINMM!mciSetDriverData` at `0x180006449`

## pseudocode

```c
__int64 __fastcall mciSpecial(LPARAM lParam, int a2, unsigned int a3, int *a4)
{
  LPARAM v4; // r15
  DWORD_PTR v5; // rax
  char v7; // di
  int v8; // edx
  int v9; // edx
  int v10; // edx
  __int64 DevCaps; // rbx
  WCHAR *v12; // rsi
  unsigned int v13; // eax
  int v14; // r14d
  int StringW; // eax
  int v16; // ecx
  DWORD_PTR dwData; // [rsp+20h] [rbp-48h] BYREF

  v4 = (unsigned int)lParam;
  v5 = 0;
  dwData = 0;
  v7 = a3;
  v8 = a2 - 2049;
  if ( !v8 )
  {
    if ( (a3 & 0xA00) != 0 )
    {
      DevCaps = (unsigned int)GraphicOpen((HLOCAL *)&dwData, a3, (__int64)a4, lParam);
      v5 = dwData;
    }
    else
    {
      DevCaps = 0;
    }
    mciSetDriverData(v4, v5);
    goto LABEL_34;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    DevCaps = 0;
    goto LABEL_34;
  }
  v10 = v9 - 8;
  if ( !v10 )
  {
    v12 = (WCHAR *)*((_QWORD *)a4 + 1);
    if ( !v12 )
    {
      LODWORD(DevCaps) = 268;
LABEL_28:
      DevCaps = (unsigned int)DevCaps;
      goto LABEL_34;
    }
    v13 = a3 & 0xFFFFFFDC;
    if ( (a3 & 0xFFFFFFDC) == 0 )
    {
      LODWORD(DevCaps) = 273;
      goto LABEL_28;
    }
    v14 = a4[4];
    LODWORD(DevCaps) = 0;
    switch ( v13 )
    {
      case 0x100u:
        StringW = LoadStringW(ghModule, 2u, v12, v14);
        v16 = 0;
        if ( !StringW )
          v16 = 268;
        LODWORD(DevCaps) = v16;
        break;
      case 0x200u:
        LODWORD(DevCaps) = 274;
        goto LABEL_28;
      case 0x400u:
        LoadStringW(ghModule, 3u, v12, v14);
        break;
      default:
        LODWORD(DevCaps) = 274;
        if ( v13 != 0x4000 )
        {
          if ( v13 == 0x10000 )
            goto LABEL_28;
          if ( v13 != 0x20000 )
            LODWORD(DevCaps) = 284;
        }
        break;
    }
    if ( (v7 & 0x20) != 0 && !(_WORD)DevCaps )
    {
      LODWORD(DevCaps) = 0;
      if ( v14 )
        *v12 = 0;
    }
    goto LABEL_28;
  }
  if ( v10 == 1 )
    DevCaps = (unsigned int)GraphicGetDevCaps(lParam, a3, a4);
  else
    DevCaps = 274;
LABEL_34:
  if ( !(_WORD)DevCaps && (v7 & 1) != 0 && !gfEvil )
    PostMessageW((HWND)*a4, 0x3B9u, 1u, v4);
  return DevCaps;
}

```

## disassembly

```asm
0x1800062f8  push    rbx
0x1800062fa  push    rbp
0x1800062fb  push    rsi
0x1800062fc  push    rdi
0x1800062fd  push    r12
0x1800062ff  push    r14
0x180006301  push    r15
0x180006303  sub     rsp, 30h
0x180006307  xor     r12d, r12d
0x18000630a  mov     r15d, ecx
0x18000630d  mov     eax, r12d
0x180006310  mov     rbp, r9
0x180006313  mov     [rsp+68h+dwData], rax
0x180006318  mov     edi, r8d
0x18000631b  sub     edx, 801h
0x180006321  jz      loc_18000641D
0x180006327  sub     edx, 1
0x18000632a  jz      loc_180006418
0x180006330  sub     edx, 8
0x180006333  jz      short loc_180006355
0x180006335  cmp     edx, 1
0x180006338  jz      short loc_180006344
0x18000633a  mov     ebx, 112h
0x18000633f  jmp     loc_18000644F
0x180006344  mov     r8, rbp
0x180006347  mov     edx, edi
0x180006349  call    GraphicGetDevCaps
0x18000634e  mov     ebx, eax
0x180006350  jmp     loc_18000644F
0x180006355  mov     rsi, [r9+8]
0x180006359  test    rsi, rsi
0x18000635c  jnz     short loc_180006368
0x18000635e  mov     ebx, 10Ch
0x180006363  jmp     loc_180006414
0x180006368  mov     eax, edi
0x18000636a  and     eax, 0FFFFFFDCh
0x18000636d  jz      loc_18000640F
0x180006373  mov     r14d, [r9+10h]
0x180006377  mov     ebx, r12d
0x18000637a  cmp     eax, 100h
0x18000637f  jz      short loc_1800063D0
0x180006381  cmp     eax, 200h
0x180006386  jz      short loc_1800063C9
0x180006388  cmp     eax, 400h
0x18000638d  jz      short loc_1800063AF
0x18000638f  mov     ebx, 112h
0x180006394  cmp     eax, 4000h
0x180006399  jz      short loc_1800063F6
0x18000639b  cmp     eax, 10000h
0x1800063a0  jz      short loc_180006414
0x1800063a2  cmp     eax, 20000h
0x1800063a7  lea     ecx, [rbx+0Ah]
0x1800063aa  cmovnz  ebx, ecx
0x1800063ad  jmp     short loc_1800063F6
0x1800063af  mov     rcx, cs:?ghModule@@3PEAUHINSTANCE__@@EA; hInstance
0x1800063b6  mov     r9d, r14d; cchBufferMax
0x1800063b9  mov     r8, rsi; lpBuffer
0x1800063bc  mov     edx, 3; uID
0x1800063c1  call    cs:__imp_LoadStringW
0x1800063c7  jmp     short loc_1800063F6
0x1800063c9  mov     ebx, 112h
0x1800063ce  jmp     short loc_180006414
0x1800063d0  mov     rcx, cs:?ghModule@@3PEAUHINSTANCE__@@EA; hInstance
0x1800063d7  mov     r9d, r14d; cchBufferMax
0x1800063da  mov     r8, rsi; lpBuffer
0x1800063dd  mov     edx, 2; uID
0x1800063e2  call    cs:__imp_LoadStringW
0x1800063e8  mov     ecx, ebx
0x1800063ea  mov     ebx, 10Ch
0x1800063ef  test    eax, eax
0x1800063f1  cmovz   ecx, ebx
0x1800063f4  mov     ebx, ecx
0x1800063f6  test    dil, 20h
0x1800063fa  jz      short loc_180006414
0x1800063fc  test    bx, bx
0x1800063ff  jnz     short loc_180006414
0x180006401  mov     ebx, r12d
0x180006404  test    r14d, r14d
0x180006407  jz      short loc_180006414
0x180006409  mov     [rsi], r12w
0x18000640d  jmp     short loc_180006414
0x18000640f  mov     ebx, 111h
0x180006414  mov     ebx, ebx
0x180006416  jmp     short loc_18000644F
0x180006418  mov     rbx, r12
0x18000641b  jmp     short loc_18000644F
0x18000641d  test    edi, 0A00h
0x180006423  jz      short loc_180006440
0x180006425  mov     r9d, r15d
0x180006428  lea     rcx, [rsp+68h+dwData]
0x18000642d  mov     r8, rbp
0x180006430  mov     edx, edi
0x180006432  call    GraphicOpen
0x180006437  mov     ebx, eax
0x180006439  mov     rax, [rsp+68h+dwData]
0x18000643e  jmp     short loc_180006443
0x180006440  mov     rbx, r12
0x180006443  mov     rdx, rax; dwData
0x180006446  mov     ecx, r15d; wDeviceID
0x180006449  call    cs:__imp_mciSetDriverData
0x18000644f  test    bx, bx
0x180006452  jnz     short loc_18000647A
0x180006454  mov     r8d, 1; wParam
0x18000645a  test    r8b, dil
0x18000645d  jz      short loc_18000647A
0x18000645f  cmp     cs:?gfEvil@@3HA, r12d; int gfEvil
0x180006466  jnz     short loc_18000647A
0x180006468  movsxd  rcx, dword ptr [rbp+0]; hWnd
0x18000646c  mov     r9, r15; lParam
0x18000646f  mov     edx, 3B9h; Msg
0x180006474  call    cs:__imp_PostMessageW
0x18000647a  mov     rax, rbx
0x18000647d  add     rsp, 30h
0x180006481  pop     r15
0x180006483  pop     r14
0x180006485  pop     r12
0x180006487  pop     rdi
0x180006488  pop     rsi
0x180006489  pop     rbp
0x18000648a  pop     rbx
0x18000648b  retn
```
