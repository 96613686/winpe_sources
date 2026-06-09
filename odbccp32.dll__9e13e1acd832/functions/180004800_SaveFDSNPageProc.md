# SaveFDSNPageProc

- ea: `0x180004800`
- end: `0x180004af6`
- name: `SaveFDSNPageProc`
- size: `758`
- prototype: `__int64 __fastcall(HWND hWnd, int, int, LONG_PTR)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callees

- `0x180002e14`
- `0x180004718`
- `0x180004800`
- `0x180004bac`
- `0x180012b14`
- `0x180013ec4`
- `0x18001484c`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_close` at `0x180004a72`
- `msvcrt!_close` at `0x180004a72`
- `msvcrt!_errno` at `0x180004a63`
- `msvcrt!_errno` at `0x180004a63`
- `msvcrt!_wopen` at `0x180004a58`
- `msvcrt!_wopen` at `0x180004a58`
- `msvcrt!malloc` at `0x18000496d`
- `msvcrt!malloc` at `0x18000496d`
- `USER32!PostMessageW` at `0x1800048f4`
- `USER32!PostMessageW` at `0x1800048f4`
- `USER32!GetWindowLongPtrW` at `0x1800048ad`
- `USER32!GetWindowLongPtrW` at `0x1800048ad`
- `USER32!SendMessageW` at `0x180004abe`
- `USER32!SendMessageW` at `0x180004abe`
- `USER32!GetParent` at `0x1800048dd`
- `USER32!GetParent` at `0x180004aa9`
- `USER32!GetParent` at `0x1800048dd`
- `USER32!GetParent` at `0x180004aa9`
- `USER32!SetWindowLongPtrW` at `0x180004898`
- `USER32!SetWindowLongPtrW` at `0x180004898`
- `KERNEL32!DeleteFileW` at `0x180004a7d`
- `KERNEL32!DeleteFileW` at `0x180004a7d`

## pseudocode

```c
__int64 __fastcall SaveFDSNPageProc(HWND hWnd, int a2, int a3, LONG_PTR a4)
{
  int v6; // edx
  __int64 v7; // rdx
  __int64 *v9; // rsi
  HWND Parent; // rax
  LPARAM v11; // rcx
  int v12; // eax
  int v13; // ebp
  __int64 v14; // r14
  LPARAM v15; // rcx
  __int64 v16; // r14
  __int16 *v17; // rcx
  __int16 v18; // ax
  int v19; // edx
  __int64 v20; // r8
  _WORD *v21; // r9
  __int64 v22; // rcx
  int v23; // eax
  HWND v24; // rax
  wchar_t pszDest[264]; // [rsp+30h] [rbp-248h] BYREF

  v6 = a2 - 78;
  if ( v6 )
  {
    v7 = (unsigned int)(v6 - 194);
    if ( (_DWORD)v7 )
    {
      if ( (_DWORD)v7 != 1 || a3 != 1446 )
        return 0;
      if ( !(unsigned __int16)SaveFileDSNUI(pszDest, v7, hWnd) )
        ODBCSendDlgItemMessage(hWnd, 1601, 0xCu, 0, (LPARAM)pszDest);
    }
    else
    {
      SetWindowLongPtrW(hWnd, -21, a4);
    }
    return 1;
  }
  v9 = *(__int64 **)(GetWindowLongPtrW(hWnd, -21) + 48);
  if ( *(_DWORD *)(a4 + 16) == -209 )
  {
    *((_DWORD *)v9 + 4) = 1;
    return 0;
  }
  if ( *(_DWORD *)(a4 + 16) != -207 )
  {
    if ( *(_DWORD *)(a4 + 16) == -200 )
    {
      Parent = GetParent(hWnd);
      PostMessageW(Parent, 0x470u, 0, 3);
      v11 = *(_QWORD *)(v9[1] + 16);
      if ( !v11 )
        v11 = *v9 + 28;
      ODBCSendDlgItemMessage(hWnd, 1601, 0xCu, 0, v11);
    }
    return 0;
  }
  v12 = ODBCSendDlgItemMessage(hWnd, 1601, 0xEu, 0, 0);
  v13 = v12;
  if ( !v12 || v12 > 260 )
    return (int)SaveFDSNFailMSG(hWnd);
  v14 = v9[1];
  if ( !*(_QWORD *)(v14 + 16) )
    *(_QWORD *)(v14 + 16) = malloc(0x20Au);
  v15 = *(_QWORD *)(v9[1] + 16);
  if ( !v15 )
  {
    PostInstError(21);
    v24 = GetParent(hWnd);
    SendMessageW(v24, 0x471u, 5u, 0);
    return 0;
  }
  v16 = *v9;
  ODBCSendDlgItemMessage(hWnd, 1601, 0xDu, v13 + 1, v15);
  v17 = *(__int16 **)(v9[1] + 16);
  v18 = *v17;
  if ( !*v17 )
    goto LABEL_30;
  v19 = 0;
  v20 = 0;
  v21 = *(_WORD **)(v9[1] + 16);
  do
  {
    if ( v18 == 32 )
    {
      if ( !v19 )
        goto LABEL_26;
    }
    else
    {
      v19 = 1;
    }
    *v17++ = v18;
    ++v20;
LABEL_26:
    v18 = *++v21;
  }
  while ( *v21 );
  if ( v20 )
  {
    do
      --v17;
    while ( *v17 == 32 );
    ++v17;
  }
LABEL_30:
  *v17 = 0;
  StringCchCopyW(pszDest, 0x105u, *(STRSAFE_LPCWSTR *)(v9[1] + 16));
  if ( *(_QWORD *)(v16 + 552) && (unsigned __int16)EnforceDSNExtension(v22, pszDest, 0x105u) == 0xFFFF )
    return (int)SaveFDSNFailMSG(hWnd);
  v23 = _wopen(pszDest, 1280, 384);
  if ( v23 == -1 )
  {
    if ( *_errno() != 17 )
      return (int)SaveFDSNFailMSG(hWnd);
  }
  else
  {
    _close(v23);
    DeleteFileW(pszDest);
  }
  StringCchCopyW((STRSAFE_LPWSTR)(*v9 + 28), 0x105u, *(STRSAFE_LPCWSTR *)(v9[1] + 16));
  return 0;
}

```

## disassembly

```asm
0x180004800  mov     [rsp+arg_8], rbx
0x180004805  push    rbp
0x180004806  push    rsi
0x180004807  push    rdi
0x180004808  push    r14
0x18000480a  push    r15
0x18000480c  sub     rsp, 250h
0x180004813  mov     rax, cs:__security_cookie
0x18000481a  xor     rax, rsp
0x18000481d  mov     [rsp+278h+var_38], rax
0x180004825  mov     rbx, r9
0x180004828  mov     rdi, rcx
0x18000482b  sub     edx, 4Eh ; 'N'
0x18000482e  jz      short loc_1800048A8
0x180004830  sub     edx, 0C2h
0x180004836  jz      short loc_180004890
0x180004838  cmp     edx, 1
0x18000483b  jnz     loc_180004ACD
0x180004841  mov     eax, 5A6h
0x180004846  cmp     r8w, ax
0x18000484a  jnz     loc_180004ACD
0x180004850  shr     r8, 10h
0x180004854  test    r8w, r8w
0x180004858  jnz     loc_180004ACD
0x18000485e  mov     r8, rcx
0x180004861  lea     rcx, [rsp+278h+pszDest]
0x180004866  call    SaveFileDSNUI
0x18000486b  test    ax, ax
0x18000486e  jnz     short loc_18000489E
0x180004870  xor     r9d, r9d
0x180004873  lea     rax, [rsp+278h+pszDest]
0x180004878  mov     edx, 641h
0x18000487d  mov     [rsp+278h+var_258], rax
0x180004882  mov     rcx, rdi
0x180004885  lea     r8d, [r9+0Ch]
0x180004889  call    ODBCSendDlgItemMessage
0x18000488e  jmp     short loc_18000489E
0x180004890  mov     r8, rbx; dwNewLong
0x180004893  mov     edx, 0FFFFFFEBh; nIndex
0x180004898  call    cs:__imp_SetWindowLongPtrW
0x18000489e  mov     eax, 1
0x1800048a3  jmp     loc_180004ACF
0x1800048a8  mov     edx, 0FFFFFFEBh; nIndex
0x1800048ad  call    cs:__imp_GetWindowLongPtrW
0x1800048b3  cmp     dword ptr [rbx+10h], 0FFFFFF2Fh
0x1800048ba  mov     rsi, [rax+30h]
0x1800048be  jz      loc_180004AC6
0x1800048c4  cmp     dword ptr [rbx+10h], 0FFFFFF31h
0x1800048cb  jz      short loc_18000492C
0x1800048cd  cmp     dword ptr [rbx+10h], 0FFFFFF38h
0x1800048d4  jnz     loc_180004ACD
0x1800048da  mov     rcx, rdi; hWnd
0x1800048dd  call    cs:__imp_GetParent
0x1800048e3  mov     r9d, 3; lParam
0x1800048e9  xor     r8d, r8d; wParam
0x1800048ec  mov     rcx, rax; hWnd
0x1800048ef  mov     edx, 470h; Msg
0x1800048f4  call    cs:__imp_PostMessageW
0x1800048fa  mov     rax, [rsi+8]
0x1800048fe  mov     rcx, [rax+10h]
0x180004902  test    rcx, rcx
0x180004905  jnz     short loc_18000490E
0x180004907  mov     rcx, [rsi]
0x18000490a  add     rcx, 1Ch
0x18000490e  xor     r9d, r9d
0x180004911  mov     [rsp+278h+var_258], rcx
0x180004916  mov     edx, 641h
0x18000491b  mov     rcx, rdi
0x18000491e  lea     r8d, [r9+0Ch]
0x180004922  call    ODBCSendDlgItemMessage
0x180004927  jmp     loc_180004ACD
0x18000492c  xor     ebx, ebx
0x18000492e  xor     r9d, r9d
0x180004931  mov     edx, 641h
0x180004936  mov     [rsp+278h+var_258], rbx
0x18000493b  mov     rcx, rdi
0x18000493e  lea     r8d, [rbx+0Eh]
0x180004942  call    ODBCSendDlgItemMessage
0x180004947  mov     rbp, rax
0x18000494a  test    eax, eax
0x18000494c  jz      loc_180004A39
0x180004952  cmp     ebp, 104h
0x180004958  jg      loc_180004A39
0x18000495e  mov     r14, [rsi+8]
0x180004962  cmp     [r14+10h], rbx
0x180004966  jnz     short loc_180004977
0x180004968  mov     ecx, 20Ah; Size
0x18000496d  call    cs:__imp_malloc
0x180004973  mov     [r14+10h], rax
0x180004977  mov     rax, [rsi+8]
0x18000497b  mov     rcx, [rax+10h]
0x18000497f  test    rcx, rcx
0x180004982  jz      loc_180004A9C
0x180004988  mov     r14, [rsi]
0x18000498b  lea     eax, [rbp+1]
0x18000498e  mov     [rsp+278h+var_258], rcx
0x180004993  mov     edx, 641h
0x180004998  movsxd  r9, eax
0x18000499b  mov     r8d, 0Dh
0x1800049a1  mov     rcx, rdi
0x1800049a4  call    ODBCSendDlgItemMessage
0x1800049a9  mov     rax, [rsi+8]
0x1800049ad  mov     rcx, [rax+10h]
0x1800049b1  movzx   eax, word ptr [rcx]
0x1800049b4  test    ax, ax
0x1800049b7  jz      short loc_1800049FD
0x1800049b9  mov     edx, ebx
0x1800049bb  mov     r8, rbx
0x1800049be  mov     r9, rcx
0x1800049c1  cmp     ax, 20h ; ' '
0x1800049c5  jz      short loc_1800049CE
0x1800049c7  mov     edx, 1
0x1800049cc  jmp     short loc_1800049D2
0x1800049ce  test    edx, edx
0x1800049d0  jz      short loc_1800049DC
0x1800049d2  mov     [rcx], ax
0x1800049d5  add     rcx, 2
0x1800049d9  inc     r8
0x1800049dc  add     r9, 2
0x1800049e0  movzx   eax, word ptr [r9]
0x1800049e4  test    ax, ax
0x1800049e7  jnz     short loc_1800049C1
0x1800049e9  cmp     r8, 1
0x1800049ed  jb      short loc_1800049FD
0x1800049ef  sub     rcx, 2
0x1800049f3  cmp     word ptr [rcx], 20h ; ' '
0x1800049f7  jz      short loc_1800049EF
0x1800049f9  add     rcx, 2
0x1800049fd  mov     [rcx], bx
0x180004a00  mov     ebp, 105h
0x180004a05  mov     r8, [rsi+8]
0x180004a09  lea     rcx, [rsp+278h+pszDest]; pszDest
0x180004a0e  mov     edx, ebp; cchDest
0x180004a10  mov     r8, [r8+10h]; pszSrc
0x180004a14  call    StringCchCopyW
0x180004a19  or      r15d, 0FFFFFFFFh
0x180004a1d  cmp     [r14+228h], rbx
0x180004a24  jz      short loc_180004A48
0x180004a26  mov     r8d, ebp
0x180004a29  lea     rdx, [rsp+278h+pszDest]
0x180004a2e  call    EnforceDSNExtension
0x180004a33  cmp     ax, r15w
0x180004a37  jnz     short loc_180004A48
0x180004a39  mov     rcx, rdi; hWnd
0x180004a3c  call    SaveFDSNFailMSG
0x180004a41  cdqe
0x180004a43  jmp     loc_180004ACF
0x180004a48  mov     edx, 500h; OpenFlag
0x180004a4d  lea     rcx, [rsp+278h+pszDest]; FileName
0x180004a52  mov     r8d, 180h
0x180004a58  call    cs:__imp__wopen
0x180004a5e  cmp     eax, r15d
0x180004a61  jnz     short loc_180004A70
0x180004a63  call    cs:__imp__errno
0x180004a69  cmp     dword ptr [rax], 11h
0x180004a6c  jz      short loc_180004A83
0x180004a6e  jmp     short loc_180004A39
0x180004a70  mov     ecx, eax; FileHandle
0x180004a72  call    cs:__imp__close
0x180004a78  lea     rcx, [rsp+278h+pszDest]; lpFileName
0x180004a7d  call    cs:__imp_DeleteFileW
0x180004a83  mov     rax, [rsi+8]
0x180004a87  mov     rdx, rbp; cchDest
0x180004a8a  mov     rcx, [rsi]
0x180004a8d  add     rcx, 1Ch; pszDest
0x180004a91  mov     r8, [rax+10h]; pszSrc
0x180004a95  call    StringCchCopyW
0x180004a9a  jmp     short loc_180004ACD
0x180004a9c  mov     ecx, 15h
0x180004aa1  call    PostInstError
0x180004aa6  mov     rcx, rdi; hWnd
0x180004aa9  call    cs:__imp_GetParent
0x180004aaf  xor     r9d, r9d; lParam
0x180004ab2  mov     edx, 471h; Msg
0x180004ab7  mov     rcx, rax; hWnd
0x180004aba  lea     r8d, [r9+5]; wParam
0x180004abe  call    cs:__imp_SendMessageW
0x180004ac4  jmp     short loc_180004ACD
0x180004ac6  mov     dword ptr [rsi+10h], 1
0x180004acd  xor     eax, eax
0x180004acf  mov     rcx, [rsp+278h+var_38]
0x180004ad7  xor     rcx, rsp; StackCookie
0x180004ada  call    __security_check_cookie
0x180004adf  mov     rbx, [rsp+278h+arg_8]
0x180004ae7  add     rsp, 250h
0x180004aee  pop     r15
0x180004af0  pop     r14
0x180004af2  pop     rdi
0x180004af3  pop     rsi
0x180004af4  pop     rbp
0x180004af5  retn
```
