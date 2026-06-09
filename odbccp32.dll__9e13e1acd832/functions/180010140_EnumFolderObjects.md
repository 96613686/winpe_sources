# EnumFolderObjects

- ea: `0x180010140`
- end: `0x180010660`
- name: `EnumFolderObjects`
- size: `1312`
- prototype: `__int64 __fastcall(HWND, __int64, wchar_t *, int, __int64, int, void *Buf2)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x18000ffac`
- `0x180010140`
- `0x1800110e8`

## callees

- `0x1800016b0`
- `0x180002e14`
- `0x18000fed0`
- `0x180010140`
- `0x18001085c`
- `0x1800109f4`
- `0x180014aae`
- `0x180014ae0`
- `0x180015010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800103ee`
- `msvcrt!_wcsnicmp` at `0x1800103ee`
- `msvcrt!_wcsicmp` at `0x18001037f`
- `msvcrt!_wcsicmp` at `0x1800104e1`
- `msvcrt!_wcsicmp` at `0x18001037f`
- `msvcrt!_wcsicmp` at `0x1800104e1`
- `msvcrt!_wsplitpath_s` at `0x18001036b`
- `msvcrt!_wsplitpath_s` at `0x18001036b`
- `USER32!SendMessageW` at `0x1800103be`
- `USER32!SendMessageW` at `0x1800104ca`
- `USER32!SendMessageW` at `0x1800104f9`
- `USER32!SendMessageW` at `0x18001050d`
- `USER32!SendMessageW` at `0x1800103be`
- `USER32!SendMessageW` at `0x1800104ca`
- `USER32!SendMessageW` at `0x1800104f9`
- `USER32!SendMessageW` at `0x18001050d`
- `SHELL32!SHGetDesktopFolder` at `0x180010550`
- `SHELL32!SHGetDesktopFolder` at `0x180010550`

## pseudocode

```c
__int64 __fastcall EnumFolderObjects(HWND a1, __int64 a2, wchar_t *a3, int a4, __int64 a5, int a6, void *Buf2)
{
  void *v7; // rbx
  int v8; // r12d
  wchar_t *v9; // r14
  __int64 v10; // r15
  __int64 v13; // r8
  int v14; // edi
  void *v15; // rbx
  size_t v16; // r8
  int v17; // r14d
  wchar_t *v18; // r9
  size_t v19; // r10
  int v20; // edx
  __int64 v21; // rcx
  wchar_t *v22; // rdi
  WPARAM v23; // rdi
  bool v24; // zf
  IShellFolder *ppshf; // [rsp+50h] [rbp-B0h] BYREF
  int v27[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+60h] [rbp-A0h]
  void *v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+70h] [rbp-90h] BYREF
  void *v31; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v32; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+88h] [rbp-78h] BYREF
  LPARAM lParam; // [rsp+90h] [rbp-70h] BYREF
  int v35; // [rsp+98h] [rbp-68h]
  wchar_t *v36; // [rsp+A8h] [rbp-58h]
  int v37; // [rsp+B4h] [rbp-4Ch]
  void *v38; // [rsp+B8h] [rbp-48h]
  wchar_t FullPath[264]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t pszSrc[264]; // [rsp+300h] [rbp+200h] BYREF
  wchar_t String1[264]; // [rsp+510h] [rbp+410h] BYREF
  wchar_t pszDest[520]; // [rsp+720h] [rbp+620h] BYREF

  v7 = Buf2;
  v8 = 0;
  v9 = a3;
  v10 = a4;
  v32 = a3;
  v29 = Buf2;
  v33 = 0;
  v31 = 0;
  v30 = 0;
  if ( !Buf2 || (v28 = 1, !(unsigned int)PidlSpecial(Buf2)) )
    v28 = 0;
  if ( (int)v10 < 260 )
  {
    v13 = 96;
    if ( a6 != 2 )
      v13 = 32;
    if ( (*(int (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)a2 + 32LL))(a2, 0, v13, &v33) >= 0 )
    {
      v14 = a6;
      while ( !(*(unsigned int (__fastcall **)(__int64, __int64, void **, int *))(*(_QWORD *)v33 + 24LL))(
                 v33,
                 1,
                 &v31,
                 &v30) )
      {
        v27[0] = 0;
        LODWORD(ppshf) = 0;
        v15 = (void *)ConcatPidls(v7, v31);
        (*(void (__fastcall **)(__int64, void *))(*(_QWORD *)a5 + 40LL))(a5, v31);
        FullPath[0] = 0;
        GetPathFromIDList(v15, FullPath);
        if ( !(unsigned int)GetDisplayName(v15, pszSrc, 261, v27, &ppshf) )
          goto LABEL_54;
        if ( v14 == 2
          && !(unsigned int)PidlSpecial(v15)
          && !(unsigned int)PidlSpecial(v15)
          && !(unsigned int)PidlSpecial(v15)
          && !(unsigned int)PidlSpecial(v15)
          && !(unsigned int)PidlSpecial(v15) )
        {
          memset_0(&lParam, 0, 0x58u);
          v37 = v27[0];
          lParam = 7;
          v38 = v15;
          if ( ((unsigned int)ppshf & 0x60000000) == 0x40000000 )
          {
            _wsplitpath_s(FullPath, 0, 0, 0, 0, 0, 0, String1, 0x105u);
            if ( _wcsicmp(String1, L".dsn") )
              goto LABEL_20;
          }
          v35 = 0;
          v36 = pszSrc;
          SendMessageW(a1, 0x104Du, 0, (LPARAM)&lParam);
          goto LABEL_9;
        }
        if ( !v9 )
          goto LABEL_28;
        v16 = -1;
        do
          ++v16;
        while ( FullPath[v16] );
        if ( v16 && !_wcsnicmp(v9, FullPath, v16) )
        {
          v17 = 1;
        }
        else
        {
LABEL_28:
          v17 = 0;
          if ( !v28 && (_DWORD)v10 )
            goto LABEL_45;
        }
        if ( !(unsigned int)PidlSpecial(v15)
          && !(unsigned int)PidlSpecial(v15)
          && !(unsigned int)PidlSpecial(v15)
          && !(unsigned int)PidlSpecial(v15)
          && !(unsigned int)PidlSpecial(v15) )
        {
          v18 = pszDest;
          v19 = 520;
          v20 = v10;
          if ( (int)v10 > 0 )
          {
            v21 = v10;
            v22 = pszDest;
            while ( v21 )
            {
              *v22++ = 32;
              --v21;
            }
            do
            {
              --v20;
              ++v18;
              --v19;
            }
            while ( v20 > 0 );
          }
          StringCchCopyW(v18, v19, pszSrc);
          v23 = SendMessageW(a1, 0x143u, 0, (LPARAM)pszDest);
          if ( v23 != -1 )
          {
            if ( !_wcsicmp(v32, FullPath) )
              SendMessageW(a1, 0x14Eu, (int)v23, 0);
            SendMessageW(a1, 0x151u, v23, (LPARAM)v15);
            v8 = 1;
          }
          v14 = a6;
        }
LABEL_45:
        if ( (unsigned int)PidlSpecial(v15) || v17 )
        {
          *(_QWORD *)v27 = 0;
          ppshf = 0;
          if ( SHGetDesktopFolder(&ppshf) < 0 )
          {
LABEL_54:
            (*(void (__fastcall **)(__int64, void *))(*(_QWORD *)a5 + 40LL))(a5, v15);
            break;
          }
          if ( ((int (__fastcall *)(IShellFolder *, void *, _QWORD, GUID *, int *))ppshf->lpVtbl->BindToObject)(
                 ppshf,
                 v15,
                 0,
                 &IID_IShellFolder,
                 v27) < 0 )
          {
            (*(void (__fastcall **)(__int64, void *))(*(_QWORD *)a5 + 40LL))(a5, v15);
            ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
            break;
          }
          ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
          v9 = v32;
          EnumFolderObjects((int)a1, v27[0], (int)v32, v10 + 1, a5, v14, v15);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 16LL))(*(_QWORD *)v27);
        }
        else
        {
          v9 = v32;
        }
        v24 = v8 == 0;
        v8 = 0;
        if ( v24 )
LABEL_20:
          (*(void (__fastcall **)(__int64, void *))(*(_QWORD *)a5 + 40LL))(a5, v15);
LABEL_9:
        v7 = v29;
      }
    }
  }
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  return 1;
}

```

## disassembly

```asm
0x180010140  push    rbp
0x180010142  push    rbx
0x180010143  push    rsi
0x180010144  push    rdi
0x180010145  push    r12
0x180010147  push    r13
0x180010149  push    r14
0x18001014b  push    r15
0x18001014d  lea     rbp, [rsp-0A48h]
0x180010155  sub     rsp, 0B48h
0x18001015c  mov     rax, cs:__security_cookie
0x180010163  xor     rax, rsp
0x180010166  mov     [rbp+0A80h+var_50], rax
0x18001016d  mov     rbx, [rbp+0A80h+Buf2]
0x180010174  xor     r12d, r12d
0x180010177  mov     rsi, [rbp+0A80h+arg_20]
0x18001017e  mov     r14, r8
0x180010181  movsxd  r15, r9d
0x180010184  mov     rdi, rdx
0x180010187  mov     [rbp+0A80h+var_B00], r8
0x18001018b  mov     r13, rcx
0x18001018e  mov     [rsp+0B80h+var_B18], rbx
0x180010193  mov     [rbp+0A80h+var_AF8], r12
0x180010197  mov     [rsp+0B80h+var_B08], r12
0x18001019c  mov     [rsp+0B80h+var_B10], r12d
0x1800101a1  test    rbx, rbx
0x1800101a4  jz      short loc_1800101BF
0x1800101a6  lea     edx, [r12+11h]
0x1800101ab  mov     rcx, rbx; Buf2
0x1800101ae  call    PidlSpecial
0x1800101b3  mov     [rsp+0B80h+var_B20], 1
0x1800101bb  test    eax, eax
0x1800101bd  jnz     short loc_1800101C4
0x1800101bf  mov     [rsp+0B80h+var_B20], r12d
0x1800101c4  cmp     r15d, 104h
0x1800101cb  jge     loc_180010623
0x1800101d1  mov     rax, [rdi]
0x1800101d4  lea     r9, [rbp+0A80h+var_AF8]
0x1800101d8  cmp     [rbp+0A80h+arg_28], 2
0x1800101df  mov     ecx, 20h ; ' '
0x1800101e4  mov     rax, [rax+20h]
0x1800101e8  lea     r8d, [rcx+40h]
0x1800101ec  cmovnz  r8d, ecx
0x1800101f0  xor     edx, edx
0x1800101f2  mov     rcx, rdi
0x1800101f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101fa  test    eax, eax
0x1800101fc  js      loc_180010623
0x180010202  mov     edi, [rbp+0A80h+arg_28]
0x180010208  jmp     short loc_18001020F
0x18001020a  mov     rbx, [rsp+0B80h+var_B18]
0x18001020f  mov     rcx, [rbp+0A80h+var_AF8]
0x180010213  lea     r9, [rsp+0B80h+var_B10]
0x180010218  lea     r8, [rsp+0B80h+var_B08]
0x18001021d  mov     edx, 1
0x180010222  mov     rax, [rcx]
0x180010225  mov     rax, [rax+18h]
0x180010229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001022e  test    eax, eax
0x180010230  jnz     loc_180010623
0x180010236  mov     rdx, [rsp+0B80h+var_B08]; void *
0x18001023b  mov     rcx, rbx; Src
0x18001023e  mov     [rsp+0B80h+var_B28], r12d
0x180010243  mov     dword ptr [rsp+0B80h+ppshf], r12d
0x180010248  call    ConcatPidls
0x18001024d  mov     rdx, [rsp+0B80h+var_B08]
0x180010252  mov     rbx, rax
0x180010255  mov     rax, [rsi]
0x180010258  mov     rcx, rsi
0x18001025b  mov     rax, [rax+28h]
0x18001025f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010264  lea     rdx, [rbp+0A80h+FullPath]
0x180010268  mov     [rbp+0A80h+FullPath], r12w
0x18001026d  mov     rcx, rbx
0x180010270  call    GetPathFromIDList
0x180010275  lea     rax, [rsp+0B80h+ppshf]
0x18001027a  mov     r8d, 105h
0x180010280  lea     r9, [rsp+0B80h+var_B28]
0x180010285  mov     [rsp+0B80h+DirCount], rax
0x18001028a  lea     rdx, [rbp+0A80h+pszSrc]
0x180010291  mov     rcx, rbx
0x180010294  call    GetDisplayName
0x180010299  test    eax, eax
0x18001029b  jz      loc_180010611
0x1800102a1  cmp     edi, 2
0x1800102a4  jnz     loc_1800103C9
0x1800102aa  lea     edx, [rdi+8]
0x1800102ad  mov     rcx, rbx; Buf2
0x1800102b0  call    PidlSpecial
0x1800102b5  test    eax, eax
0x1800102b7  jnz     loc_1800103C9
0x1800102bd  lea     edx, [rdi+12h]
0x1800102c0  mov     rcx, rbx; Buf2
0x1800102c3  call    PidlSpecial
0x1800102c8  test    eax, eax
0x1800102ca  jnz     loc_1800103C9
0x1800102d0  lea     edx, [rdi+2]
0x1800102d3  mov     rcx, rbx; Buf2
0x1800102d6  call    PidlSpecial
0x1800102db  test    eax, eax
0x1800102dd  jnz     loc_1800103C9
0x1800102e3  lea     edx, [rdi+9]
0x1800102e6  mov     rcx, rbx; Buf2
0x1800102e9  call    PidlSpecial
0x1800102ee  test    eax, eax
0x1800102f0  jnz     loc_1800103C9
0x1800102f6  lea     edx, [rdi+1]
0x1800102f9  mov     rcx, rbx; Buf2
0x1800102fc  call    PidlSpecial
0x180010301  test    eax, eax
0x180010303  jnz     loc_1800103C9
0x180010309  xor     edx, edx; Val
0x18001030b  lea     r8d, [rdi+56h]; Size
0x18001030f  lea     rcx, [rbp+0A80h+lParam]; void *
0x180010313  call    memset_0
0x180010318  mov     eax, [rsp+0B80h+var_B28]
0x18001031c  mov     [rbp+0A80h+var_ACC], eax
0x18001031f  mov     eax, dword ptr [rsp+0B80h+ppshf]
0x180010323  and     eax, 60000000h
0x180010328  mov     [rbp+0A80h+lParam], 7
0x180010330  mov     [rbp+0A80h+var_AC8], rbx
0x180010334  cmp     eax, 40000000h
0x180010339  jnz     short loc_1800103A0
0x18001033b  mov     [rsp+0B80h+ExtCount], 105h; ExtCount
0x180010344  lea     rax, [rbp+0A80h+String1]
0x18001034b  mov     [rsp+0B80h+Ext], rax; Ext
0x180010350  lea     rcx, [rbp+0A80h+FullPath]; FullPath
0x180010354  mov     [rsp+0B80h+FilenameCount], r12; FilenameCount
0x180010359  xor     r9d, r9d; Dir
0x18001035c  mov     [rsp+0B80h+Filename], r12; Filename
0x180010361  xor     r8d, r8d; DriveCount
0x180010364  xor     edx, edx; Drive
0x180010366  mov     [rsp+0B80h+DirCount], r12; DirCount
0x18001036b  call    cs:__imp__wsplitpath_s
0x180010371  lea     rdx, aDsn_1; ".dsn"
0x180010378  lea     rcx, [rbp+0A80h+String1]; String1
0x18001037f  call    cs:__imp__wcsicmp
0x180010385  test    eax, eax
0x180010387  jz      short loc_1800103A0
0x180010389  mov     rax, [rsi]
0x18001038c  mov     rdx, rbx
0x18001038f  mov     rcx, rsi
0x180010392  mov     rax, [rax+28h]
0x180010396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001039b  jmp     loc_18001020A
0x1800103a0  lea     rax, [rbp+0A80h+pszSrc]
0x1800103a7  mov     [rbp+0A80h+var_AE8], r12d
0x1800103ab  lea     r9, [rbp+0A80h+lParam]; lParam
0x1800103af  mov     [rbp+0A80h+var_AD8], rax
0x1800103b3  xor     r8d, r8d; wParam
0x1800103b6  mov     edx, 104Dh; Msg
0x1800103bb  mov     rcx, r13; hWnd
0x1800103be  call    cs:__imp_SendMessageW
0x1800103c4  jmp     loc_18001020A
0x1800103c9  xor     eax, eax
0x1800103cb  test    r14, r14
0x1800103ce  jz      short loc_180010400
0x1800103d0  lea     rcx, [rbp+0A80h+FullPath]
0x1800103d4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800103d8  inc     r8; MaxCount
0x1800103db  cmp     [rcx+r8*2], ax
0x1800103e0  jnz     short loc_1800103D8
0x1800103e2  test    r8, r8
0x1800103e5  jz      short loc_180010400
0x1800103e7  lea     rdx, [rbp+0A80h+FullPath]; String2
0x1800103eb  mov     rcx, r14; String1
0x1800103ee  call    cs:__imp__wcsnicmp
0x1800103f4  test    eax, eax
0x1800103f6  jnz     short loc_1800103FE
0x1800103f8  lea     r14d, [rax+1]
0x1800103fc  jmp     short loc_180010412
0x1800103fe  xor     eax, eax
0x180010400  mov     r14d, eax
0x180010403  cmp     [rsp+0B80h+var_B20], eax
0x180010407  jnz     short loc_180010412
0x180010409  test    r15d, r15d
0x18001040c  jnz     loc_18001051F
0x180010412  mov     edx, 0Ah
0x180010417  mov     rcx, rbx; Buf2
0x18001041a  call    PidlSpecial
0x18001041f  test    eax, eax
0x180010421  jnz     loc_18001051F
0x180010427  lea     edx, [rax+14h]
0x18001042a  mov     rcx, rbx; Buf2
0x18001042d  call    PidlSpecial
0x180010432  test    eax, eax
0x180010434  jnz     loc_18001051F
0x18001043a  lea     edx, [rax+4]
0x18001043d  mov     rcx, rbx; Buf2
0x180010440  call    PidlSpecial
0x180010445  test    eax, eax
0x180010447  jnz     loc_18001051F
0x18001044d  lea     edx, [rax+0Bh]
0x180010450  mov     rcx, rbx; Buf2
0x180010453  call    PidlSpecial
0x180010458  test    eax, eax
0x18001045a  jnz     loc_18001051F
0x180010460  lea     edx, [rax+3]
0x180010463  mov     rcx, rbx; Buf2
0x180010466  call    PidlSpecial
0x18001046b  test    eax, eax
0x18001046d  jnz     loc_18001051F
0x180010473  lea     r9, [rbp+0A80h+pszDest]
0x18001047a  mov     r10d, 208h
0x180010480  mov     edx, r15d
0x180010483  test    r15d, r15d
0x180010486  jle     short loc_1800104A6
0x180010488  mov     eax, 20h ; ' '
0x18001048d  mov     rcx, r15
0x180010490  movzx   eax, ax
0x180010493  mov     rdi, r9
0x180010496  rep stosw
0x180010499  dec     edx
0x18001049b  add     r9, 2
0x18001049f  dec     r10
0x1800104a2  test    edx, edx
0x1800104a4  jg      short loc_180010499
0x1800104a6  lea     r8, [rbp+0A80h+pszSrc]; pszSrc
0x1800104ad  mov     rdx, r10; cchDest
0x1800104b0  mov     rcx, r9; pszDest
0x1800104b3  call    StringCchCopyW
0x1800104b8  lea     r9, [rbp+0A80h+pszDest]; lParam
0x1800104bf  xor     r8d, r8d; wParam
0x1800104c2  mov     edx, 143h; Msg
0x1800104c7  mov     rcx, r13; hWnd
0x1800104ca  call    cs:__imp_SendMessageW
0x1800104d0  mov     rdi, rax
0x1800104d3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800104d7  jz      short loc_180010519
0x1800104d9  mov     rcx, [rbp+0A80h+var_B00]; String1
0x1800104dd  lea     rdx, [rbp+0A80h+FullPath]; String2
0x1800104e1  call    cs:__imp__wcsicmp
0x1800104e7  test    eax, eax
0x1800104e9  jnz     short loc_1800104FF
0x1800104eb  movsxd  r8, edi; wParam
0x1800104ee  xor     r9d, r9d; lParam
0x1800104f1  mov     edx, 14Eh; Msg
0x1800104f6  mov     rcx, r13; hWnd
0x1800104f9  call    cs:__imp_SendMessageW
0x1800104ff  mov     r9, rbx; lParam
0x180010502  mov     r8, rdi; wParam
0x180010505  mov     edx, 151h; Msg
0x18001050a  mov     rcx, r13; hWnd
0x18001050d  call    cs:__imp_SendMessageW
0x180010513  mov     r12d, 1
0x180010519  mov     edi, [rbp+0A80h+arg_28]
0x18001051f  mov     edx, 11h
0x180010524  mov     rcx, rbx; Buf2
0x180010527  call    PidlSpecial
0x18001052c  test    eax, eax
0x18001052e  jnz     short loc_180010539
0x180010530  test    r14d, r14d
0x180010533  jz      loc_1800105D4
0x180010539  lea     rcx, [rsp+0B80h+ppshf]; ppshf
0x18001053e  mov     qword ptr [rsp+0B80h+var_B28], 0
0x180010547  mov     [rsp+0B80h+ppshf], 0
0x180010550  call    cs:__imp_SHGetDesktopFolder
0x180010556  test    eax, eax
0x180010558  js      loc_180010611
0x18001055e  mov     rcx, [rsp+0B80h+ppshf]
0x180010563  lea     rdx, [rsp+0B80h+var_B28]
0x180010568  mov     [rsp+0B80h+DirCount], rdx
0x18001056d  lea     r9, IID_IShellFolder
0x180010574  xor     r8d, r8d
0x180010577  mov     rdx, rbx
0x18001057a  mov     rax, [rcx]
0x18001057d  mov     rax, [rax+28h]
0x180010581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010586  test    eax, eax
0x180010588  js      short loc_1800105EC
0x18001058a  mov     rcx, [rsp+0B80h+ppshf]
0x18001058f  mov     rax, [rcx]
0x180010592  mov     rax, [rax+10h]
0x180010596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001059b  mov     r14, [rbp+0A80h+var_B00]
0x18001059f  lea     r9d, [r15+1]; int
0x1800105a3  mov     rdx, qword ptr [rsp+0B80h+var_B28]; int
0x1800105a8  mov     r8, r14; int
0x1800105ab  mov     [rsp+0B80h+FilenameCount], rbx; Buf2
0x1800105b0  mov     rcx, r13; int
0x1800105b3  mov     dword ptr [rsp+0B80h+Filename], edi; int
0x1800105b7  mov     [rsp+0B80h+DirCount], rsi; __int64
0x1800105bc  call    EnumFolderObjects
0x1800105c1  mov     rcx, qword ptr [rsp+0B80h+var_B28]
0x1800105c6  mov     rax, [rcx]
0x1800105c9  mov     rax, [rax+10h]
0x1800105cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105d2  jmp     short loc_1800105D8
0x1800105d4  mov     r14, [rbp+0A80h+var_B00]
0x1800105d8  test    r12d, r12d
0x1800105db  mov     r12d, 0
0x1800105e1  jnz     loc_18001020A
0x1800105e7  jmp     loc_180010389
0x1800105ec  mov     rax, [rsi]
0x1800105ef  mov     rdx, rbx
0x1800105f2  mov     rcx, rsi
0x1800105f5  mov     rax, [rax+28h]
0x1800105f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105fe  mov     rcx, [rsp+0B80h+ppshf]
0x180010603  mov     rax, [rcx]
  ... truncated ...
```
