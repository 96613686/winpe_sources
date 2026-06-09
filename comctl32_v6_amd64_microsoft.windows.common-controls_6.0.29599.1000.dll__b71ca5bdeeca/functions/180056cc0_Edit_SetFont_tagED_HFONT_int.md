# Edit_SetFont(tagED *,HFONT__ *,int)

- ea: `0x180056cc0`
- end: `0x180057151`
- name: `?Edit_SetFont@@YAHPEAUtagED@@PEAUHFONT__@@H@Z`
- size: `1169`
- prototype: `__int64 __fastcall(struct tagED *, HFONT, int)`
- caller_count: `5`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180056cc0`
- `0x180059720`
- `0x18005b520`
- `0x1800c2a88`
- `0x1800c2bdc`

## callees

- `0x180056cc0`
- `0x180057158`
- `0x180057474`
- `0x180057600`
- `0x1800580a0`
- `0x1800d75f0`
- `0x1800ddb90`
- `0x1800e0344`
- `0x180114520`
- `0x1801310bc`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056f9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056f9b`
- `GDI32!DeleteObject` at `0x180056d34`
- `GDI32!DeleteObject` at `0x180056d34`
- `GDI32!SelectObject` at `0x180056e36`
- `GDI32!SelectObject` at `0x180056f0a`
- `GDI32!SelectObject` at `0x180056f4a`
- `GDI32!SelectObject` at `0x180056e36`
- `GDI32!SelectObject` at `0x180056f0a`
- `GDI32!SelectObject` at `0x180056f4a`
- `GDI32!GetCharWidthInfo` at `0x180056dbc`
- `GDI32!GetCharWidthInfo` at `0x180056dbc`
- `USER32!GetKeyboardLayout` at `0x18005712d`
- `USER32!GetKeyboardLayout` at `0x18005712d`
- `USER32!SystemParametersInfoW` at `0x180057086`
- `USER32!SystemParametersInfoW` at `0x180057086`
- `USER32!DestroyCaret` at `0x180057096`
- `USER32!DestroyCaret` at `0x180057096`
- `USER32!ShowCaret` at `0x1800570c6`
- `USER32!ShowCaret` at `0x1800570c6`
- `USER32!HideCaret` at `0x180057090`
- `USER32!HideCaret` at `0x180057090`
- `USER32!GetDC` at `0x180056d16`
- `USER32!GetDC` at `0x180056d16`
- `USER32!ReleaseDC` at `0x180056e4d`
- `USER32!ReleaseDC` at `0x180056e4d`
- `IMM32!ImmIsIME` at `0x180057136`
- `IMM32!ImmIsIME` at `0x180057136`

## pseudocode

```c
__int64 __fastcall Edit_SetFont(struct tagED *a1, HFONT a2, int a3)
{
  HWND v4; // rcx
  unsigned int v7; // r13d
  HDC DC; // rdi
  void *v9; // rcx
  HGDIOBJ v10; // rsi
  int CharDimensions; // eax
  LONG tmOverhang; // eax
  unsigned int v13; // eax
  int DBCSVector; // eax
  int v15; // edx
  unsigned int v16; // edx
  int v17; // eax
  unsigned int v18; // edx
  __int64 result; // rax
  void *v20; // rcx
  int v21; // edx
  int v22; // eax
  int v23; // r9d
  int v24; // r8d
  unsigned int v25; // r10d
  unsigned int v26; // r11d
  unsigned int v27; // r15d
  unsigned int v28; // ecx
  HKL KeyboardLayout; // rax
  unsigned int pvParam; // [rsp+30h] [rbp-39h] BYREF
  __int64 v31; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v32; // [rsp+40h] [rbp-29h]
  struct tagTEXTMETRICW tm; // [rsp+48h] [rbp-21h] BYREF

  v31 = 0;
  v4 = (HWND)*((_QWORD *)a1 + 8);
  v32 = 0;
  v7 = 0;
  memset(&tm, 0, sizeof(tm));
  DC = GetDC(v4);
  if ( !DC )
    return v7;
  v9 = (void *)*((_QWORD *)a1 + 24);
  if ( v9 )
    DeleteObject(v9);
  *((_QWORD *)a1 + 24) = a2;
  if ( !a2 )
  {
    v10 = 0;
    CharDimensions = UserGetCharDimensionsEx(DC, 0, &tm, (LONG *)a1 + 51);
    *((_DWORD *)a1 + 50) = CharDimensions;
    if ( !CharDimensions )
    {
      *((_DWORD *)a1 + 50) = 8;
      *((_DWORD *)a1 + 51) = 16;
    }
    goto LABEL_7;
  }
  v10 = SelectObject(DC, a2);
  if ( !v10 )
  {
    *((_QWORD *)a1 + 24) = 0;
    a2 = 0;
  }
  v22 = UserGetCharDimensionsEx(DC, a2, &tm, (LONG *)a1 + 51);
  *((_DWORD *)a1 + 50) = v22;
  if ( v22 )
  {
LABEL_7:
    tmOverhang = tm.tmOverhang;
    *((_DWORD *)a1 + 29) &= ~0x40u;
    *((_DWORD *)a1 + 52) = tmOverhang;
    LOBYTE(tmOverhang) = ~tm.tmPitchAndFamily;
    *(_QWORD *)((char *)a1 + 260) = 0;
    v7 = 1;
    *(_QWORD *)((char *)a1 + 252) = 0;
    *((_DWORD *)a1 + 29) |= (tmOverhang & 1) << 6;
    if ( (tm.tmPitchAndFamily & 4) != 0 )
      v13 = *((_DWORD *)a1 + 29) ^ (*((_DWORD *)a1 + 29) ^ ((unsigned int)GetCharWidthInfo(DC, &v31) << 21)) & 0x200000;
    else
      v13 = *((_DWORD *)a1 + 29) & 0xFFDFFFFF;
    *((_DWORD *)a1 + 29) = v13;
    DBCSVector = Edit_GetDBCSVector(a1, DC, tm.tmCharSet);
    v15 = (*((_DWORD *)a1 + 29) ^ (DBCSVector << 12)) & 0x1000;
    *((_BYTE *)a1 + 248) = tm.tmCharSet;
    v16 = *((_DWORD *)a1 + 29) ^ v15;
    *((_DWORD *)a1 + 29) = v16;
    if ( (DBCSVector & 1) != 0 )
    {
      v20 = (void *)*((_QWORD *)a1 + 30);
      if ( v20 )
      {
        LocalFree(v20);
        *((_QWORD *)a1 + 30) = 0;
      }
      v21 = *((_DWORD *)a1 + 29);
      if ( (v21 & 0x40) != 0 && 2 * *((_DWORD *)a1 + 50) == tm.tmMaxCharWidth )
        v16 = v21 | 0x80;
      else
        v16 = v21 & 0xFFFFFF7F;
      *((_DWORD *)a1 + 29) = v16;
    }
    if ( (v16 & 0x200000) != 0 )
    {
      if ( (int)v31 >= 0 )
        v23 = 0;
      else
        v23 = -(int)v31;
      *((_DWORD *)a1 + 63) = v23;
      if ( v31 >= 0 )
        v24 = 0;
      else
        v24 = -HIDWORD(v31);
      *((_DWORD *)a1 + 65) = v24;
      v25 = v32;
      if ( v32 )
      {
        v26 = (v32 - 1 + v23) / v32;
        *((_DWORD *)a1 + 64) = v26;
        v27 = (v25 - 1 + v24) / v25;
        *((_DWORD *)a1 + 66) = v27;
        if ( v24 + v23 > v25 )
        {
          v28 = (v24 + v23 - 1) / v25;
          *((_DWORD *)a1 + 64) = v26 + v28;
          *((_DWORD *)a1 + 66) = v28 + v27;
        }
        goto LABEL_12;
      }
    }
    else
    {
      v17 = *((_DWORD *)a1 + 52);
      if ( !v17 )
      {
LABEL_12:
        if ( a2 )
        {
          if ( v10 )
            SelectObject(DC, v10);
        }
        else
        {
          *((_DWORD *)a1 + 53) = *((_DWORD *)a1 + 50);
          *((_DWORD *)a1 + 54) = *((_DWORD *)a1 + 51);
        }
        if ( (*((_BYTE *)a1 + 116) & 8) != 0 )
        {
          pvParam = 0;
          SystemParametersInfoW(0x2006u, 0, &pvParam, 0);
          HideCaret(*((HWND *)a1 + 8));
          DestroyCaret();
          (*(void (__fastcall **)(struct tagED *, HDC, _QWORD, _QWORD, _DWORD))(*((_QWORD *)a1 + 36) + 96LL))(
            a1,
            DC,
            pvParam,
            *((unsigned int *)a1 + 51),
            0);
          ShowCaret(*((HWND *)a1 + 8));
        }
        ReleaseDC(*((HWND *)a1 + 8), DC);
        v18 = *((_DWORD *)a1 + 13);
        if ( v18 )
          Edit_SetPasswordCharHandler(a1, v18);
        if ( (*((_DWORD *)a1 + 29) & 0x200000) != 0 )
        {
          if ( (*((_DWORD *)a1 + 29) & 0x1000) != 0 )
            Edit_CalcMarginForDBCSFont(a1, a3);
          else
            Edit_SetMargin(a1, 3u, -1, a3);
        }
        if ( (*((_DWORD *)a1 + 29) & 0x4001) == 0 )
          EditML_BuildLines(a1, 0, 0, 0, 0, 0);
        Edit_Size(a1, 0, a3);
        if ( (*((_BYTE *)a1 + 116) & 8) != 0 )
        {
          KeyboardLayout = GetKeyboardLayout(0);
          if ( ImmIsIME(KeyboardLayout) )
            Edit_SetCompositionFont(a1);
        }
        return v7;
      }
      *((_DWORD *)a1 + 65) = v17;
      *((_DWORD *)a1 + 63) = v17;
    }
    *((_DWORD *)a1 + 64) = 0;
    *((_DWORD *)a1 + 66) = 0;
    goto LABEL_12;
  }
  if ( v10 )
    SelectObject(DC, v10);
  result = Edit_SetFont(a1, 0, a3);
  if ( !(_DWORD)result )
  {
    *((_DWORD *)a1 + 50) = 8;
    *((_DWORD *)a1 + 51) = 16;
  }
  return result;
}

```

## disassembly

```asm
0x180056cc0  mov     [rsp-8+arg_18], rbx
0x180056cc5  push    rbp
0x180056cc6  push    rsi
0x180056cc7  push    rdi
0x180056cc8  push    r12
0x180056cca  push    r13
0x180056ccc  push    r14
0x180056cce  push    r15
0x180056cd0  lea     rbp, [rsp-27h]
0x180056cd5  sub     rsp, 90h
0x180056cdc  mov     rax, cs:__security_cookie
0x180056ce3  xor     rax, rsp
0x180056ce6  mov     [rbp+57h+var_38], rax
0x180056cea  xorps   xmm0, xmm0
0x180056ced  xor     eax, eax
0x180056cef  mov     rbx, rcx
0x180056cf2  mov     [rbp+57h+var_88], rax
0x180056cf6  mov     rcx, [rcx+40h]; hWnd
0x180056cfa  mov     r12d, r8d
0x180056cfd  movups  xmmword ptr [rbp+57h+tm.tmOverhang], xmm0
0x180056d01  mov     r14, rdx
0x180056d04  mov     [rbp+57h+var_80], eax
0x180056d07  movups  xmmword ptr [rbp+57h+tm.tmFirstChar], xmm0
0x180056d0b  xor     r13d, r13d
0x180056d0e  movups  xmmword ptr [rbp+57h+tm.tmHeight], xmm0
0x180056d12  movups  xmmword ptr [rbp+57h+tm.tmExternalLeading], xmm0
0x180056d16  call    cs:__imp_GetDC
0x180056d1c  mov     rdi, rax
0x180056d1f  test    rax, rax
0x180056d22  jz      loc_180056E8F
0x180056d28  mov     rcx, [rbx+0C0h]; ho
0x180056d2f  test    rcx, rcx
0x180056d32  jz      short loc_180056D3A
0x180056d34  call    cs:__imp_DeleteObject
0x180056d3a  mov     [rbx+0C0h], r14
0x180056d41  mov     r13d, 8
0x180056d47  mov     rcx, rdi; hdc
0x180056d4a  test    r14, r14
0x180056d4d  jnz     loc_180056F07
0x180056d53  lea     r15, [rbx+0CCh]
0x180056d5a  xor     edx, edx; h
0x180056d5c  mov     r9, r15; LONG *
0x180056d5f  lea     r8, [rbp+57h+tm]; lptm
0x180056d63  xor     esi, esi
0x180056d65  call    ?UserGetCharDimensionsEx@@YAHPEAUHDC__@@PEAUHFONT__@@PEAUtagTEXTMETRICW@@PEAH@Z; UserGetCharDimensionsEx(HDC__ *,HFONT__ *,tagTEXTMETRICW *,int *)
0x180056d6a  mov     [rbx+0C8h], eax
0x180056d70  test    eax, eax
0x180056d72  jz      loc_180056F88
0x180056d78  mov     eax, [rbp+57h+tm.tmOverhang]
0x180056d7b  xor     r15d, r15d
0x180056d7e  and     dword ptr [rbx+74h], 0FFFFFFBFh
0x180056d82  mov     [rbx+0D0h], eax
0x180056d88  mov     al, [rbp+57h+tm.tmPitchAndFamily]
0x180056d8b  not     al
0x180056d8d  mov     [rbx+104h], r15
0x180056d94  lea     r13d, [r15+1]
0x180056d98  mov     [rbx+0FCh], r15
0x180056d9f  and     eax, r13d
0x180056da2  shl     eax, 6
0x180056da5  or      [rbx+74h], eax
0x180056da8  test    [rbp+57h+tm.tmPitchAndFamily], 4
0x180056dac  mov     eax, [rbx+74h]
0x180056daf  jz      loc_180056EB9
0x180056db5  lea     rdx, [rbp+57h+var_88]
0x180056db9  mov     rcx, rdi
0x180056dbc  call    cs:__imp_GetCharWidthInfo
0x180056dc2  shl     eax, 15h
0x180056dc5  xor     eax, [rbx+74h]
0x180056dc8  and     eax, 200000h
0x180056dcd  xor     eax, [rbx+74h]
0x180056dd0  mov     [rbx+74h], eax
0x180056dd3  mov     rdx, rdi; HDC
0x180056dd6  mov     r8b, [rbp+57h+tm.tmCharSet]; unsigned __int8
0x180056dda  mov     rcx, rbx; struct tagED *
0x180056ddd  call    ?Edit_GetDBCSVector@@YAHPEAUtagED@@PEAUHDC__@@E@Z; Edit_GetDBCSVector(tagED *,HDC__ *,uchar)
0x180056de2  mov     edx, eax
0x180056de4  mov     ecx, eax
0x180056de6  mov     al, [rbp+57h+tm.tmCharSet]
0x180056de9  shl     edx, 0Ch
0x180056dec  xor     edx, [rbx+74h]
0x180056def  and     edx, 1000h
0x180056df5  mov     [rbx+0F8h], al
0x180056dfb  xor     edx, [rbx+74h]
0x180056dfe  mov     [rbx+74h], edx
0x180056e01  test    r13b, cl
0x180056e04  jnz     loc_180056EDF
0x180056e0a  bt      edx, 15h
0x180056e0e  jb      loc_180056FC7
0x180056e14  mov     eax, [rbx+0D0h]
0x180056e1a  test    eax, eax
0x180056e1c  jnz     loc_180057055
0x180056e22  test    r14, r14
0x180056e25  jz      loc_180056EC2
0x180056e2b  test    rsi, rsi
0x180056e2e  jz      short loc_180056E3C
0x180056e30  mov     rdx, rsi; h
0x180056e33  mov     rcx, rdi; hdc
0x180056e36  call    cs:__imp_SelectObject
0x180056e3c  test    byte ptr [rbx+74h], 8
0x180056e40  jnz     loc_180057074
0x180056e46  mov     rcx, [rbx+40h]; hWnd
0x180056e4a  mov     rdx, rdi; hDC
0x180056e4d  call    cs:__imp_ReleaseDC
0x180056e53  mov     edx, [rbx+34h]; unsigned int
0x180056e56  test    edx, edx
0x180056e58  jnz     loc_1800570D1
0x180056e5e  test    dword ptr [rbx+74h], 200000h
0x180056e65  jnz     loc_1800570DE
0x180056e6b  test    dword ptr [rbx+74h], 4001h
0x180056e72  jz      loc_18005710C
0x180056e78  mov     r8d, r12d; int
0x180056e7b  xor     edx, edx; lprcSrc
0x180056e7d  mov     rcx, rbx; struct tagED *
0x180056e80  call    ?Edit_Size@@YAXPEAUtagED@@PEBUtagRECT@@H@Z; Edit_Size(tagED *,tagRECT const *,int)
0x180056e85  test    byte ptr [rbx+74h], 8
0x180056e89  jnz     loc_18005712B
0x180056e8f  mov     eax, r13d
0x180056e92  mov     rcx, [rbp+57h+var_38]
0x180056e96  xor     rcx, rsp; StackCookie
0x180056e99  call    __security_check_cookie
0x180056e9e  mov     rbx, [rsp+0C0h+arg_18]
0x180056ea6  add     rsp, 90h
0x180056ead  pop     r15
0x180056eaf  pop     r14
0x180056eb1  pop     r13
0x180056eb3  pop     r12
0x180056eb5  pop     rdi
0x180056eb6  pop     rsi
0x180056eb7  pop     rbp
0x180056eb8  retn
0x180056eb9  btr     eax, 15h
0x180056ebd  jmp     loc_180056DD0
0x180056ec2  mov     eax, [rbx+0C8h]
0x180056ec8  mov     [rbx+0D4h], eax
0x180056ece  mov     eax, [rbx+0CCh]
0x180056ed4  mov     [rbx+0D8h], eax
0x180056eda  jmp     loc_180056E3C
0x180056edf  mov     rcx, [rbx+0F0h]; hMem
0x180056ee6  test    rcx, rcx
0x180056ee9  jnz     loc_180056F9B
0x180056eef  mov     edx, [rbx+74h]
0x180056ef2  test    dl, 40h
0x180056ef5  jnz     loc_180056FAD
0x180056efb  btr     edx, 7
0x180056eff  mov     [rbx+74h], edx
0x180056f02  jmp     loc_180056E0A
0x180056f07  mov     rdx, r14; h
0x180056f0a  call    cs:__imp_SelectObject
0x180056f10  mov     rsi, rax
0x180056f13  test    rax, rax
0x180056f16  jz      short loc_180056F78
0x180056f18  lea     r15, [rbx+0CCh]
0x180056f1f  mov     rdx, r14; h
0x180056f22  mov     r9, r15; LONG *
0x180056f25  lea     r8, [rbp+57h+tm]; lptm
0x180056f29  mov     rcx, rdi; hdc
0x180056f2c  call    ?UserGetCharDimensionsEx@@YAHPEAUHDC__@@PEAUHFONT__@@PEAUtagTEXTMETRICW@@PEAH@Z; UserGetCharDimensionsEx(HDC__ *,HFONT__ *,tagTEXTMETRICW *,int *)
0x180056f31  mov     [rbx+0C8h], eax
0x180056f37  test    eax, eax
0x180056f39  jnz     loc_180056D78
0x180056f3f  test    rsi, rsi
0x180056f42  jz      short loc_180056F50
0x180056f44  mov     rdx, rsi; h
0x180056f47  mov     rcx, rdi; hdc
0x180056f4a  call    cs:__imp_SelectObject
0x180056f50  mov     r8d, r12d; int
0x180056f53  xor     edx, edx; HFONT
0x180056f55  mov     rcx, rbx; struct tagED *
0x180056f58  call    ?Edit_SetFont@@YAHPEAUtagED@@PEAUHFONT__@@H@Z; Edit_SetFont(tagED *,HFONT__ *,int)
0x180056f5d  test    eax, eax
0x180056f5f  jnz     loc_180056E92
0x180056f65  mov     [rbx+0C8h], r13d
0x180056f6c  mov     dword ptr [r15], 10h
0x180056f73  jmp     loc_180056E92
0x180056f78  mov     qword ptr [rbx+0C0h], 0
0x180056f83  xor     r14d, r14d
0x180056f86  jmp     short loc_180056F18
0x180056f88  mov     [rbx+0C8h], r13d
0x180056f8f  mov     dword ptr [r15], 10h
0x180056f96  jmp     loc_180056D78
0x180056f9b  call    cs:__imp_LocalFree
0x180056fa1  mov     [rbx+0F0h], r15
0x180056fa8  jmp     loc_180056EEF
0x180056fad  mov     eax, [rbx+0C8h]
0x180056fb3  add     eax, eax
0x180056fb5  cmp     eax, [rbp+57h+tm.tmMaxCharWidth]
0x180056fb8  jnz     loc_180056EFB
0x180056fbe  bts     edx, 7
0x180056fc2  jmp     loc_180056EFF
0x180056fc7  mov     r9d, dword ptr [rbp+57h+var_88]
0x180056fcb  test    r9d, r9d
0x180056fce  jns     short loc_180056FD5
0x180056fd0  neg     r9d
0x180056fd3  jmp     short loc_180056FD8
0x180056fd5  mov     r9d, r15d
0x180056fd8  mov     [rbx+0FCh], r9d
0x180056fdf  mov     r8d, dword ptr [rbp+57h+var_88+4]
0x180056fe3  test    r8d, r8d
0x180056fe6  jns     short loc_180056FED
0x180056fe8  neg     r8d
0x180056feb  jmp     short loc_180056FF0
0x180056fed  mov     r8d, r15d
0x180056ff0  mov     [rbx+104h], r8d
0x180056ff7  mov     r10d, [rbp+57h+var_80]
0x180056ffb  test    r10d, r10d
0x180056ffe  jz      short loc_180057061
0x180057000  xor     edx, edx
0x180057002  lea     ecx, [r10-1]
0x180057006  lea     eax, [rcx+r9]
0x18005700a  div     r10d
0x18005700d  xor     edx, edx
0x18005700f  mov     r11d, eax
0x180057012  mov     [rbx+100h], eax
0x180057018  lea     eax, [rcx+r8]
0x18005701c  div     r10d
0x18005701f  mov     r15d, eax
0x180057022  mov     [rbx+108h], eax
0x180057028  lea     eax, [r8+r9]
0x18005702c  cmp     eax, r10d
0x18005702f  jbe     short loc_18005704D
0x180057031  dec     eax
0x180057033  xor     edx, edx
0x180057035  div     r10d
0x180057038  mov     ecx, eax
0x18005703a  add     eax, r11d
0x18005703d  mov     [rbx+100h], eax
0x180057043  lea     eax, [rcx+r15]
0x180057047  mov     [rbx+108h], eax
0x18005704d  xor     r15d, r15d
0x180057050  jmp     loc_180056E22
0x180057055  mov     [rbx+104h], eax
0x18005705b  mov     [rbx+0FCh], eax
0x180057061  mov     [rbx+100h], r15d
0x180057068  mov     [rbx+108h], r15d
0x18005706f  jmp     loc_180056E22
0x180057074  xor     r9d, r9d; fWinIni
0x180057077  mov     [rbp+57h+pvParam], r15d
0x18005707b  lea     r8, [rbp+57h+pvParam]; pvParam
0x18005707f  xor     edx, edx; uiParam
0x180057081  mov     ecx, 2006h; uiAction
0x180057086  call    cs:__imp_SystemParametersInfoW
0x18005708c  mov     rcx, [rbx+40h]; hWnd
0x180057090  call    cs:__imp_HideCaret
0x180057096  call    cs:__imp_DestroyCaret
0x18005709c  mov     rax, [rbx+120h]
0x1800570a3  mov     rdx, rdi
0x1800570a6  mov     r9d, [rbx+0CCh]
0x1800570ad  mov     rcx, rbx
0x1800570b0  mov     r8d, [rbp+57h+pvParam]
0x1800570b4  mov     dword ptr [rsp+0C0h+var_A0], r15d
0x1800570b9  mov     rax, [rax+60h]
0x1800570bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570c2  mov     rcx, [rbx+40h]; hWnd
0x1800570c6  call    cs:__imp_ShowCaret
0x1800570cc  jmp     loc_180056E46
0x1800570d1  mov     rcx, rbx; struct tagED *
0x1800570d4  call    ?Edit_SetPasswordCharHandler@@YAXPEAUtagED@@I@Z; Edit_SetPasswordCharHandler(tagED *,uint)
0x1800570d9  jmp     loc_180056E5E
0x1800570de  test    dword ptr [rbx+74h], 1000h
0x1800570e5  mov     rcx, rbx; struct tagED *
0x1800570e8  jz      short loc_1800570F7
0x1800570ea  mov     edx, r12d; int
0x1800570ed  call    ?Edit_CalcMarginForDBCSFont@@YAXPEAUtagED@@H@Z; Edit_CalcMarginForDBCSFont(tagED *,int)
0x1800570f2  jmp     loc_180056E6B
0x1800570f7  or      r8d, 0FFFFFFFFh; int
0x1800570fb  mov     r9d, r12d; int
0x1800570fe  lea     edx, [r8+4]; unsigned int
0x180057102  call    ?Edit_SetMargin@@YAXPEAUtagED@@IJH@Z; Edit_SetMargin(tagED *,uint,long,int)
0x180057107  jmp     loc_180056E6B
0x18005710c  mov     [rsp+0C0h+var_98], r15
0x180057111  xor     r9d, r9d
0x180057114  xor     r8d, r8d
0x180057117  mov     [rsp+0C0h+var_A0], r15
0x18005711c  xor     edx, edx
0x18005711e  mov     rcx, rbx
0x180057121  call    ?EditML_BuildLines@@YAXPEAUtagED@@KHW4TYPING_STATUS@@PEAJ2@Z; EditML_BuildLines(tagED *,ulong,int,TYPING_STATUS,long *,long *)
0x180057126  jmp     loc_180056E78
0x18005712b  xor     ecx, ecx; idThread
0x18005712d  call    cs:__imp_GetKeyboardLayout
0x180057133  mov     rcx, rax; HKL
0x180057136  call    cs:__imp_ImmIsIME
0x18005713c  test    eax, eax
0x18005713e  jz      loc_180056E8F
0x180057144  mov     rcx, rbx; struct tagED *
0x180057147  call    ?Edit_SetCompositionFont@@YAXPEAUtagED@@@Z; Edit_SetCompositionFont(tagED *)
0x18005714c  jmp     loc_180056E8F
```
