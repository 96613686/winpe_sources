# GetOpenFileNameW_0

- ea: `0x1800b3d60`
- end: `0x1800b4201`
- name: `GetOpenFileNameW_0`
- size: `1185`
- prototype: `BOOL __stdcall(LPOPENFILENAMEW)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800b4210`

## callees

- `0x180003030`
- `0x1800030c0`
- `0x180003d20`
- `0x180003d80`
- `0x180013360`
- `0x1800b3d60`
- `0x1801a661c`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b3fcb`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800b3fcb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b41da`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800b41da`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x1800b3f41`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x1800b3f41`
- `USER32!LoadStringW` at `0x1800b3dea`
- `USER32!LoadStringW` at `0x1800b40dd`
- `USER32!LoadStringW` at `0x1800b3dea`
- `USER32!LoadStringW` at `0x1800b40dd`
- `COMDLG32!CommDlgExtendedError` at `0x1800b413d`
- `COMDLG32!CommDlgExtendedError` at `0x1800b413d`
- `COMDLG32!GetOpenFileNameW` at `0x1800b410c`
- `COMDLG32!GetOpenFileNameW` at `0x1800b410c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __stdcall GetOpenFileNameW_0(LPOPENFILENAMEW a1)
{
  UINT v1; // edx
  const wchar_t *v2; // r8
  WCHAR **v3; // r9
  WCHAR **v4; // r15
  const wchar_t *v5; // r14
  int v6; // edi
  __int64 v7; // rsi
  wchar_t *i; // rax
  __int64 v9; // rax
  DWORD v10; // edx
  __int64 v11; // rcx
  const wchar_t *v12; // rax
  unsigned __int64 v13; // rcx
  __int64 v14; // rdx
  WCHAR *v15; // rax
  tagOFNW *v17; // rbx
  __int64 v18; // rax
  unsigned __int64 v19; // rsi
  size_t v20; // rdx
  __int64 v21; // rax
  void *v22; // rsp
  tagOFNW *v23; // rax
  wchar_t *v24; // rdx
  unsigned __int64 v25; // r9
  wchar_t v26; // ax
  unsigned __int64 v27; // rcx
  wchar_t *v28; // rdx
  wchar_t v29; // ax
  unsigned __int64 v30; // rcx
  DWORD v31; // eax
  DWORD v32; // edi
  DWORD v33; // edi
  DWORD v34; // edi
  DWORD v35; // edi
  DWORD v36; // edi
  __int64 v37; // [rsp+0h] [rbp-50h] BYREF
  tagOFNW v38; // [rsp+50h] [rbp+0h] BYREF
  wchar_t Drive[8]; // [rsp+F0h] [rbp+A0h] BYREF
  wchar_t Ext[256]; // [rsp+100h] [rbp+B0h] BYREF
  wchar_t Filename[256]; // [rsp+300h] [rbp+2B0h] BYREF
  wchar_t Dir[256]; // [rsp+500h] [rbp+4B0h] BYREF
  WCHAR Buffer[512]; // [rsp+700h] [rbp+6B0h] BYREF
  WCHAR v44[512]; // [rsp+B00h] [rbp+AB0h] BYREF
  UINT uID; // [rsp+F70h] [rbp+F20h]

  v4 = v3;
  v5 = v2;
  v6 = 0;
  *v3 = 0;
  *(_QWORD *)&v38.lStructSize = 152;
  memset(&v38.lpstrFilter, 0, 128);
  v38.hwndOwner = (HWND)a1;
  v38.hInstance = g_hinstance_language;
  v7 = -1;
  if ( v1 )
  {
    LoadStringW(g_hinstance_language, v1, Buffer, 512);
    for ( i = wcschr_0(Buffer, 0x7Cu); i; i = wcschr_0(i + 1, 0x7Cu) )
      *i = 0;
    v38.lpstrFilter = Buffer;
    v9 = -1;
    do
      ++v9;
    while ( Buffer[v9] );
    v38.lpstrDefExt = &Buffer[v9 + 3];
  }
  else
  {
    v38.lpstrFilter = 0;
    v38.lpstrDefExt = 0;
  }
  v38.lpstrCustomFilter = 0;
  v38.nFilterIndex = 0;
  v10 = 260;
  v38.nMaxFile = 260;
  if ( v5 )
  {
    v11 = 0x7FFFFFFF;
    v12 = v5;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v11;
    }
    while ( v11 );
    if ( v11 )
    {
      if ( (unsigned __int64)(0x7FFFFFFF - v11) > 0x104 )
        v10 = 0x7FFFFFFF - v11;
      v38.nMaxFile = v10;
    }
  }
  v13 = v10 + 1LL;
  v14 = 2 * v13;
  if ( !is_mul_ok(v13, 2u) )
    v14 = -1;
  v15 = (WCHAR *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 112LL))(g_pMO, v14);
  *v4 = v15;
  if ( !v15 )
    return -2147024882;
  v38.lpstrFile = v15;
  *v15 = 0;
  v38.lpstrInitialDir = 0;
  v17 = 0;
  if ( v5 )
  {
    _wsplitpath_s(v5, Drive, 3u, Dir, 0x100u, Filename, 0x100u, Ext, 0x100u);
    v18 = -1;
    do
      ++v18;
    while ( Drive[v18] );
    do
      ++v7;
    while ( Dir[v7] );
    v19 = v18 + 1 + v7;
    v20 = 0;
    if ( 2 * v19 + 16 > 2 * v19 )
      v20 = 2 * v19 + 16;
    if ( !v20 )
    {
      v17 = 0;
      goto LABEL_52;
    }
    if ( v20 > 0x400 )
    {
      _mm_lfence();
      v23 = (tagOFNW *)malloc(v20);
      v17 = v23;
      if ( !v23 )
        goto LABEL_35;
      v23->lStructSize = 56797;
    }
    else
    {
      v21 = v20 + 15;
      if ( v20 + 15 < v20 )
        v21 = 0xFFFFFFFFFFFFFF0LL;
      v22 = alloca(v21 & 0xFFFFFFFFFFFFFFF0uLL);
      v17 = &v38;
      if ( &v37 == (__int64 *)-80LL )
      {
LABEL_35:
        v38.lpstrInitialDir = (LPCWSTR)v17;
        if ( v17 )
        {
          StringCchPrintfW((wchar_t *)v17, v19, L"%ls%ls", Drive, Dir);
          v24 = Filename;
          v25 = 0xD400840000000000uLL;
          v26 = Filename[0];
          if ( Filename[0] )
          {
            while ( v26 != 92 )
            {
              v27 = *v24;
              if ( (unsigned int)v27 <= 0x3F )
              {
                if ( _bittest64((const __int64 *)&v25, v27) )
                  break;
              }
              if ( (_DWORD)v27 == 124 )
                break;
              v26 = *++v24;
              if ( !*v24 )
                goto LABEL_42;
            }
          }
          else
          {
LABEL_42:
            v28 = Ext;
            v29 = Ext[0];
            if ( Ext[0] )
            {
              while ( v29 != 92 )
              {
                v30 = *v28;
                if ( (unsigned int)v30 <= 0x3F )
                {
                  if ( _bittest64((const __int64 *)&v25, v30) )
                    break;
                }
                if ( (_DWORD)v30 == 124 )
                  break;
                v29 = *++v28;
                if ( !*v28 )
                  goto LABEL_48;
              }
            }
            else
            {
LABEL_48:
              StringCchPrintfW(v38.lpstrFile, v38.nMaxFile, L"%ls%ls", Filename, Ext);
            }
          }
          goto LABEL_49;
        }
LABEL_52:
        v6 = -2147024882;
        goto LABEL_70;
      }
      v38.lStructSize = 52428;
    }
    v17 = (tagOFNW *)((char *)v17 + 16);
    goto LABEL_35;
  }
LABEL_49:
  v38.lpstrFileTitle = 0;
  if ( uID )
  {
    LoadStringW(g_hinstance_language, uID, v44, 512);
    v38.lpstrTitle = v44;
  }
  else
  {
    v38.lpstrTitle = 0;
  }
  v38.Flags = 6148;
  if ( !GetOpenFileNameW(&v38) )
  {
    if ( *v4 )
      (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 128LL))(g_pMO);
    *v4 = 0;
    v31 = CommDlgExtendedError();
    v32 = v31;
    if ( !v31 )
    {
      v6 = 1;
      goto LABEL_70;
    }
    if ( (bidGblFlags & 2) != 0 && off_1802632A0[0] )
      bidTraceW(off_180260470[0], 176128, off_1802632A0[0], v31);
    v33 = v32 - 2;
    if ( v33 )
    {
      v34 = v33 - 7;
      if ( v34 )
      {
        v35 = v34 - 1;
        if ( v35 )
        {
          v36 = v35 - 2;
          if ( v36 )
          {
            if ( v36 != 12277 )
            {
              v6 = -2147467259;
              goto LABEL_70;
            }
          }
        }
      }
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      v6 = bidTraceHR(off_180260470[0], 184329, 2147942414LL);
      goto LABEL_70;
    }
    goto LABEL_52;
  }
LABEL_70:
  if ( v17 )
  {
    if ( LODWORD(v17[-1].pvReserved) == 56797 )
      free(&v17[-1].pvReserved);
  }
  return v6;
}

```

## disassembly

```asm
0x1800b3d60  push    rbp
0x1800b3d62  push    rbx
0x1800b3d63  push    rsi
0x1800b3d64  push    rdi
0x1800b3d65  push    r14
0x1800b3d67  push    r15
0x1800b3d69  sub     rsp, 0F18h
0x1800b3d70  lea     rbp, [rsp+50h]
0x1800b3d75  mov     rax, cs:__security_cookie
0x1800b3d7c  xor     rax, rbp
0x1800b3d7f  mov     [rbp+0EF0h+var_40], rax
0x1800b3d86  mov     r15, r9
0x1800b3d89  mov     r14, r8
0x1800b3d8c  xor     edi, edi
0x1800b3d8e  mov     [r9], rdi
0x1800b3d91  mov     qword ptr [rbp+0EF0h+var_EF0.lStructSize], 98h
0x1800b3d99  xorps   xmm0, xmm0
0x1800b3d9c  movups  xmmword ptr [rbp+0EF0h+var_EF0.hwndOwner], xmm0
0x1800b3da0  movups  xmmword ptr [rbp+0EF0h+var_EF0.lpstrFilter], xmm0
0x1800b3da4  movups  xmmword ptr [rbp+0EF0h+var_EF0.nMaxCustFilter], xmm0
0x1800b3da8  movups  xmmword ptr [rbp+0EF0h+var_EF0.nMaxFile], xmm0
0x1800b3dac  movups  xmmword ptr [rbp+0EF0h+var_EF0.nMaxFileTitle], xmm0
0x1800b3db0  movups  xmmword ptr [rbp+0EF0h+var_EF0.lpstrTitle], xmm0
0x1800b3db4  movups  xmmword ptr [rbp+0EF0h+var_EF0.lpstrDefExt], xmm0
0x1800b3db8  movups  xmmword ptr [rbp+0EF0h+var_EF0.lpfnHook], xmm0
0x1800b3dbc  movups  xmmword ptr [rbp+0EF0h+var_EF0.pvReserved], xmm0
0x1800b3dc3  mov     [rbp+0EF0h+var_EF0.hwndOwner], rcx
0x1800b3dc7  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x1800b3dce  mov     [rbp+0EF0h+var_EF0.hInstance], rcx
0x1800b3dd2  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800b3dd9  test    edx, edx
0x1800b3ddb  jz      short loc_1800B3E58
0x1800b3ddd  mov     r9d, 200h; cchBufferMax
0x1800b3de3  lea     r8, [rbp+0EF0h+Buffer]; lpBuffer
0x1800b3dea  call    cs:__imp_LoadStringW
0x1800b3df0  mov     edx, 7Ch ; '|'; Ch
0x1800b3df5  lea     rcx, [rbp+0EF0h+Buffer]; Str
0x1800b3dfc  call    wcschr_0
0x1800b3e01  test    rax, rax
0x1800b3e04  jz      short loc_1800B3E26
0x1800b3e06  nop     word ptr [rax+rax+00000000h]
0x1800b3e10  mov     [rax], di
0x1800b3e13  mov     edx, 7Ch ; '|'; Ch
0x1800b3e18  lea     rcx, [rax+2]; Str
0x1800b3e1c  call    wcschr_0
0x1800b3e21  test    rax, rax
0x1800b3e24  jnz     short loc_1800B3E10
0x1800b3e26  lea     rax, [rbp+0EF0h+Buffer]
0x1800b3e2d  mov     [rbp+0EF0h+var_EF0.lpstrFilter], rax
0x1800b3e31  lea     rcx, [rbp+0EF0h+Buffer]
0x1800b3e38  mov     rax, rsi
0x1800b3e3b  nop     dword ptr [rax+rax+00h]
0x1800b3e40  lea     rax, [rax+1]
0x1800b3e44  cmp     [rcx+rax*2], di
0x1800b3e48  jnz     short loc_1800B3E40
0x1800b3e4a  lea     rax, [rbp+rax*2+0EF0h+var_83A]
0x1800b3e52  mov     [rbp+0EF0h+var_EF0.lpstrDefExt], rax
0x1800b3e56  jmp     short loc_1800B3E60
0x1800b3e58  mov     [rbp+0EF0h+var_EF0.lpstrFilter], rdi
0x1800b3e5c  mov     [rbp+0EF0h+var_EF0.lpstrDefExt], rdi
0x1800b3e60  mov     [rbp+0EF0h+var_EF0.lpstrCustomFilter], rdi
0x1800b3e64  mov     [rbp+0EF0h+var_EF0.nFilterIndex], edi
0x1800b3e67  mov     edx, 104h
0x1800b3e6c  mov     [rbp+0EF0h+var_EF0.nMaxFile], edx
0x1800b3e6f  test    r14, r14
0x1800b3e72  jz      short loc_1800B3EA5
0x1800b3e74  mov     r8d, 7FFFFFFFh
0x1800b3e7a  mov     ecx, r8d
0x1800b3e7d  mov     rax, r14
0x1800b3e80  cmp     [rax], di
0x1800b3e83  jz      short loc_1800B3E8F
0x1800b3e85  add     rax, 2
0x1800b3e89  sub     rcx, 1
0x1800b3e8d  jnz     short loc_1800B3E80
0x1800b3e8f  sub     r8, rcx
0x1800b3e92  test    rcx, rcx
0x1800b3e95  cmovz   r8, rdi
0x1800b3e99  jz      short loc_1800B3EA5
0x1800b3e9b  cmp     r8, rdx
0x1800b3e9e  cmova   edx, r8d
0x1800b3ea2  mov     [rbp+0EF0h+var_EF0.nMaxFile], edx
0x1800b3ea5  mov     ecx, edx
0x1800b3ea7  inc     rcx
0x1800b3eaa  mov     eax, 2
0x1800b3eaf  mul     rcx
0x1800b3eb2  mov     rdx, rax
0x1800b3eb5  cmovb   rdx, rsi
0x1800b3eb9  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1800b3ec0  mov     rax, [rcx]
0x1800b3ec3  mov     rax, [rax+70h]
0x1800b3ec7  call    cs:__guard_dispatch_icall_fptr
0x1800b3ecd  nop
0x1800b3ece  mov     [r15], rax
0x1800b3ed1  test    rax, rax
0x1800b3ed4  jnz     short loc_1800B3EE0
0x1800b3ed6  mov     eax, 8007000Eh
0x1800b3edb  jmp     loc_1800B41E2
0x1800b3ee0  mov     [rbp+0EF0h+var_EF0.lpstrFile], rax
0x1800b3ee4  mov     [rax], di
0x1800b3ee7  mov     [rbp+0EF0h+var_EF0.lpstrInitialDir], rdi
0x1800b3eeb  mov     rbx, rdi
0x1800b3eee  test    r14, r14
0x1800b3ef1  jz      loc_1800B40BB
0x1800b3ef7  mov     [rsp+0F40h+ExtCount], 100h; ExtCount
0x1800b3f00  lea     rax, [rbp+0EF0h+var_E40]
0x1800b3f07  mov     [rsp+0F40h+Ext], rax; Ext
0x1800b3f0c  mov     [rsp+0F40h+FilenameCount], 100h; FilenameCount
0x1800b3f15  lea     rax, [rbp+0EF0h+var_C40]
0x1800b3f1c  mov     [rsp+0F40h+Filename], rax; Filename
0x1800b3f21  mov     [rsp+0F40h+DirCount], 100h; DirCount
0x1800b3f2a  lea     r9, [rbp+0EF0h+Dir]; Dir
0x1800b3f31  mov     r8d, 3; DriveCount
0x1800b3f37  lea     rdx, [rbp+0EF0h+Drive]; Drive
0x1800b3f3e  mov     rcx, r14; FullPath
0x1800b3f41  call    cs:__imp__wsplitpath_s
0x1800b3f47  lea     rcx, [rbp+0EF0h+Drive]
0x1800b3f4e  mov     rax, rsi
0x1800b3f51  inc     rax
0x1800b3f54  cmp     [rcx+rax*2], bx
0x1800b3f58  jnz     short loc_1800B3F51
0x1800b3f5a  lea     rcx, [rbp+0EF0h+Dir]
0x1800b3f61  inc     rsi
0x1800b3f64  cmp     [rcx+rsi*2], bx
0x1800b3f68  jnz     short loc_1800B3F61
0x1800b3f6a  inc     rax
0x1800b3f6d  add     rsi, rax
0x1800b3f70  lea     rax, [rsi+rsi]
0x1800b3f74  lea     rcx, [rax+10h]
0x1800b3f78  mov     rdx, rdi
0x1800b3f7b  cmp     rcx, rax
0x1800b3f7e  cmova   rdx, rcx
0x1800b3f82  test    rdx, rdx
0x1800b3f85  jz      loc_1800B40F0
0x1800b3f8b  cmp     rdx, 400h
0x1800b3f92  ja      short loc_1800B3FC5
0x1800b3f94  lea     rax, [rdx+0Fh]
0x1800b3f98  cmp     rax, rdx
0x1800b3f9b  ja      short loc_1800B3FA7
0x1800b3f9d  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800b3fa7  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800b3fab  call    _alloca_probe
0x1800b3fb0  sub     rsp, rax
0x1800b3fb3  lea     rbx, [rsp+0F40h+var_EF0]
0x1800b3fb8  test    rbx, rbx
0x1800b3fbb  jz      short loc_1800B3FE3
0x1800b3fbd  mov     dword ptr [rbx], 0CCCCh
0x1800b3fc3  jmp     short loc_1800B3FDF
0x1800b3fc5  lfence
0x1800b3fc8  mov     rcx, rdx; Size
0x1800b3fcb  call    cs:__imp_malloc
0x1800b3fd1  mov     rbx, rax
0x1800b3fd4  test    rax, rax
0x1800b3fd7  jz      short loc_1800B3FE3
0x1800b3fd9  mov     dword ptr [rax], 0DDDDh
0x1800b3fdf  add     rbx, 10h
0x1800b3fe3  mov     [rbp+0EF0h+var_EF0.lpstrInitialDir], rbx
0x1800b3fe7  test    rbx, rbx
0x1800b3fea  jz      loc_1800B40F3
0x1800b3ff0  lea     rax, [rbp+0EF0h+Dir]
0x1800b3ff7  mov     [rsp+0F40h+DirCount], rax
0x1800b3ffc  lea     r9, [rbp+0EF0h+Drive]
0x1800b4003  lea     r8, aLsLs_1; "%ls%ls"
0x1800b400a  mov     rdx, rsi; unsigned __int64
0x1800b400d  mov     rcx, rbx; Buffer
0x1800b4010  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800b4015  lea     rdx, [rbp+0EF0h+var_C40]
0x1800b401c  mov     r9, 0D400840000000000h
0x1800b4026  movzx   eax, [rbp+0EF0h+var_C40]
0x1800b402d  test    ax, ax
0x1800b4030  jz      short loc_1800B405B
0x1800b4032  cmp     ax, 5Ch ; '\'
0x1800b4036  jz      loc_1800B40BB
0x1800b403c  movzx   ecx, word ptr [rdx]
0x1800b403f  cmp     ecx, 3Fh ; '?'
0x1800b4042  ja      short loc_1800B404A
0x1800b4044  bt      r9, rcx
0x1800b4048  jb      short loc_1800B40BB
0x1800b404a  cmp     ecx, 7Ch ; '|'
0x1800b404d  jz      short loc_1800B40BB
0x1800b404f  add     rdx, 2
0x1800b4053  movzx   eax, word ptr [rdx]
0x1800b4056  test    ax, ax
0x1800b4059  jnz     short loc_1800B4032
0x1800b405b  lea     rdx, [rbp+0EF0h+var_E40]
0x1800b4062  movzx   eax, [rbp+0EF0h+var_E40]
0x1800b4069  test    ax, ax
0x1800b406c  jz      short loc_1800B4095
0x1800b406e  xchg    ax, ax
0x1800b4070  cmp     ax, 5Ch ; '\'
0x1800b4074  jz      short loc_1800B40BB
0x1800b4076  movzx   ecx, word ptr [rdx]
0x1800b4079  cmp     ecx, 3Fh ; '?'
0x1800b407c  ja      short loc_1800B4084
0x1800b407e  bt      r9, rcx
0x1800b4082  jb      short loc_1800B40BB
0x1800b4084  cmp     ecx, 7Ch ; '|'
0x1800b4087  jz      short loc_1800B40BB
0x1800b4089  add     rdx, 2
0x1800b408d  movzx   eax, word ptr [rdx]
0x1800b4090  test    ax, ax
0x1800b4093  jnz     short loc_1800B4070
0x1800b4095  mov     edx, [rbp+0EF0h+var_EF0.nMaxFile]; unsigned __int64
0x1800b4098  lea     rax, [rbp+0EF0h+var_E40]
0x1800b409f  mov     [rsp+0F40h+DirCount], rax
0x1800b40a4  lea     r9, [rbp+0EF0h+var_C40]
0x1800b40ab  lea     r8, aLsLs_1; "%ls%ls"
0x1800b40b2  mov     rcx, [rbp+0EF0h+var_EF0.lpstrFile]; Buffer
0x1800b40b6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800b40bb  mov     [rbp+0EF0h+var_EF0.lpstrFileTitle], rdi
0x1800b40bf  mov     edx, [rbp+0EF0h+uID]; uID
0x1800b40c5  test    edx, edx
0x1800b40c7  jz      short loc_1800B40FD
0x1800b40c9  mov     r9d, 200h; cchBufferMax
0x1800b40cf  lea     r8, [rbp+0EF0h+var_440]; lpBuffer
0x1800b40d6  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x1800b40dd  call    cs:__imp_LoadStringW
0x1800b40e3  lea     rax, [rbp+0EF0h+var_440]
0x1800b40ea  mov     [rbp+0EF0h+var_EF0.lpstrTitle], rax
0x1800b40ee  jmp     short loc_1800B4101
0x1800b40f0  mov     rbx, rdi
0x1800b40f3  mov     edi, 8007000Eh
0x1800b40f8  jmp     loc_1800B41C9
0x1800b40fd  mov     [rbp+0EF0h+var_EF0.lpstrTitle], rdi
0x1800b4101  mov     [rbp+0EF0h+var_EF0.Flags], 1804h
0x1800b4108  lea     rcx, [rbp+0EF0h+var_EF0]; LPOPENFILENAMEW
0x1800b410c  call    cs:__imp_GetOpenFileNameW
0x1800b4112  test    eax, eax
0x1800b4114  jnz     loc_1800B41C9
0x1800b411a  mov     rdx, [r15]
0x1800b411d  test    rdx, rdx
0x1800b4120  jz      short loc_1800B413A
0x1800b4122  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1800b4129  mov     rax, [rcx]
0x1800b412c  mov     rax, [rax+80h]
0x1800b4133  call    cs:__guard_dispatch_icall_fptr
0x1800b4139  nop
0x1800b413a  mov     [r15], rdi
0x1800b413d  call    cs:__imp_CommDlgExtendedError
0x1800b4143  mov     edi, eax
0x1800b4145  test    eax, eax
0x1800b4147  jz      short loc_1800B41C4
0x1800b4149  test    byte ptr cs:_bidGblFlags, 2
0x1800b4150  jz      short loc_1800B4179
0x1800b4152  mov     rcx, cs:off_1802632A0; "<GetOpenFileNameW|DataLinkPage|OLEDB|ER"...
0x1800b4159  test    rcx, rcx
0x1800b415c  jz      short loc_1800B4179
0x1800b415e  mov     r9d, eax
0x1800b4161  mov     r8, cs:off_1802632A0; "<GetOpenFileNameW|DataLinkPage|OLEDB|ER"...
0x1800b4168  mov     edx, 2B000h
0x1800b416d  mov     rcx, cs:off_180260470; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800b4174  call    _bidTraceW
0x1800b4179  sub     edi, 2
0x1800b417c  jz      short loc_1800B419C
0x1800b417e  sub     edi, 7
0x1800b4181  jz      short loc_1800B419C
0x1800b4183  sub     edi, 1
0x1800b4186  jz      short loc_1800B419C
0x1800b4188  sub     edi, 2
0x1800b418b  jz      short loc_1800B419C
0x1800b418d  cmp     edi, 2FF5h
0x1800b4193  jz      short loc_1800B419C
0x1800b4195  mov     edi, 80004005h
0x1800b419a  jmp     short loc_1800B41C9
0x1800b419c  test    byte ptr cs:_bidGblFlags, 2
0x1800b41a3  jz      loc_1800B40F3
0x1800b41a9  mov     edx, 2D009h
0x1800b41ae  mov     r8d, 8007000Eh
0x1800b41b4  mov     rcx, cs:off_180260470; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800b41bb  call    _bidTraceHR
0x1800b41c0  mov     edi, eax
0x1800b41c2  jmp     short loc_1800B41C9
0x1800b41c4  mov     edi, 1
0x1800b41c9  test    rbx, rbx
0x1800b41cc  jz      short loc_1800B41E0
0x1800b41ce  lea     rcx, [rbx-10h]; Block
0x1800b41d2  cmp     dword ptr [rcx], 0DDDDh
0x1800b41d8  jnz     short loc_1800B41E0
0x1800b41da  call    cs:__imp_free
0x1800b41e0  mov     eax, edi
0x1800b41e2  mov     rcx, [rbp+0EF0h+var_40]
0x1800b41e9  xor     rcx, rbp; StackCookie
0x1800b41ec  call    __security_check_cookie
0x1800b41f1  lea     rsp, [rbp+0EC8h]
0x1800b41f8  pop     r15
0x1800b41fa  pop     r14
0x1800b41fc  pop     rdi
0x1800b41fd  pop     rsi
0x1800b41fe  pop     rbx
0x1800b41ff  pop     rbp
0x1800b4200  retn
```
