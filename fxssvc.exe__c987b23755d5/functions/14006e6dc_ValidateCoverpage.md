# ValidateCoverpage

- ea: `0x14006e6dc`
- end: `0x14006ee2e`
- name: `ValidateCoverpage`
- size: `1874`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x14002dee0`

## callees

- `0x140004a30`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004df0`
- `0x14000c450`
- `0x14006a3a4`
- `0x14006e6dc`
- `0x140073ff0`
- `0x1400744c0`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14006ea2a`
- `KERNEL32!GetLastError` at `0x14006ea51`
- `KERNEL32!GetLastError` at `0x14006ea6c`
- `KERNEL32!GetLastError` at `0x14006ea93`
- `KERNEL32!GetLastError` at `0x14006ed5e`
- `KERNEL32!GetLastError` at `0x14006edcf`
- `KERNEL32!GetLastError` at `0x14006ea2a`
- `KERNEL32!GetLastError` at `0x14006ea51`
- `KERNEL32!GetLastError` at `0x14006ea6c`
- `KERNEL32!GetLastError` at `0x14006ea93`
- `KERNEL32!GetLastError` at `0x14006ed5e`
- `KERNEL32!GetLastError` at `0x14006edcf`
- `KERNEL32!SetLastError` at `0x14006edfa`
- `KERNEL32!SetLastError` at `0x14006edfa`
- `KERNEL32!CloseHandle` at `0x14006eda6`
- `KERNEL32!CloseHandle` at `0x14006eda6`
- `KERNEL32!GetFileAttributesW` at `0x14006e9b1`
- `KERNEL32!GetFileAttributesW` at `0x14006ec4c`
- `KERNEL32!GetFileAttributesW` at `0x14006ec5e`
- `KERNEL32!GetFileAttributesW` at `0x14006e9b1`
- `KERNEL32!GetFileAttributesW` at `0x14006ec4c`
- `KERNEL32!GetFileAttributesW` at `0x14006ec5e`
- `msvcrt!wcschr` at `0x14006e9a1`
- `msvcrt!wcschr` at `0x14006e9a1`
- `msvcrt!_wcsicmp` at `0x14006e8f9`
- `msvcrt!_wcsicmp` at `0x14006e95b`
- `msvcrt!_wcsicmp` at `0x14006e8f9`
- `msvcrt!_wcsicmp` at `0x14006e95b`
- `msvcrt!_wsplitpath_s` at `0x14006e842`
- `msvcrt!_wsplitpath_s` at `0x14006e842`

## pseudocode

```c
__int64 __fastcall ValidateCoverpage(unsigned __int16 *a1, __int64 a2, int a3, unsigned __int16 *a4)
{
  CMapDeviceId *v7; // r10
  DWORD LastError; // ebx
  __int64 v9; // r14
  wchar_t *v10; // rax
  __int64 v11; // rcx
  unsigned __int16 *v12; // rdx
  __int64 v13; // rbx
  unsigned int v14; // esi
  wchar_t *v15; // rcx
  wchar_t *v16; // r8
  __int64 v17; // rdx
  wchar_t *v18; // rax
  __int64 v19; // rcx
  wchar_t *v20; // rcx
  CMapDeviceId *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  DWORD v24; // eax
  __int64 v25; // rdx
  int v26; // eax
  unsigned __int16 v27; // di
  CMapDeviceId *v28; // rcx
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // rcx
  wchar_t *v32; // rdx
  __int64 v33; // rdi
  WCHAR *v34; // rax
  WCHAR *v35; // rcx
  CMapDeviceId *v36; // rcx
  __int64 v37; // rdx
  int v38; // eax
  WCHAR *v39; // rcx
  __int64 v40; // rdi
  wchar_t *v41; // rax
  wchar_t *v42; // rcx
  int v43; // eax
  __int64 v44; // r9
  void *File; // rax
  DWORD v46; // eax
  wchar_t FullPath[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+260h] [rbp+160h] BYREF
  wchar_t Ext[256]; // [rsp+470h] [rbp+370h] BYREF
  wchar_t String1[264]; // [rsp+670h] [rbp+570h] BYREF
  wchar_t Filename[256]; // [rsp+880h] [rbp+780h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
    goto LABEL_6;
  v9 = 2147483646;
  v10 = FullPath;
  v11 = 2147483646;
  v12 = a1;
  v13 = 260;
  v14 = 1;
  do
  {
    if ( !v11 )
      break;
    if ( !*v12 )
      break;
    *v10++ = *v12++;
    --v11;
    --v13;
  }
  while ( v13 );
  v15 = v10 - 1;
  if ( v13 )
    v15 = v10;
  *v15 = 0;
  if ( !v13 )
  {
    if ( v7 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 2) != 0 && *((_BYTE *)v7 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v7 + 2), 44, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, 122);
    goto LABEL_18;
  }
  LastError = 0;
  if ( a3 == 1 )
  {
    if ( _wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u) )
    {
      LastError = 1627;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, 1627);
      }
    }
    v16 = Filename;
    v17 = 260;
    v18 = String1;
    v19 = 2147483646;
    do
    {
      if ( !v19 )
        break;
      if ( !*v16 )
        break;
      *v18++ = *v16++;
      --v19;
      --v17;
    }
    while ( v17 );
    v20 = v18 - 1;
    if ( v17 )
      v20 = v18;
    *v20 = 0;
    StringCchCatW(String1, 0x104u, Ext);
    if ( _wcsicmp(String1, FullPath) )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_6;
      }
      v22 = 46;
LABEL_36:
      WPP_SF_S(*((_QWORD *)v21 + 2), v22, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, FullPath);
LABEL_6:
      LastError = 87;
LABEL_122:
      SetLastError(LastError);
      return 0;
    }
    if ( !_wcsicmp(Ext, L".lnk") )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_6;
      }
      v22 = 47;
      goto LABEL_36;
    }
  }
  if ( !wcschr(FullPath, 0x5Cu) )
  {
    if ( a3 )
    {
      if ( !(unsigned int)GetServerCpDir(v23, FullPath) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v24 = GetLastError();
          v25 = 49;
LABEL_59:
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v24);
        }
      }
    }
    else if ( !(unsigned int)GetClientCpDir(FullPath) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = GetLastError();
        v25 = 51;
        goto LABEL_59;
      }
    }
    if ( LastError )
      goto LABEL_61;
    v26 = StringCchCatW(FullPath, 0x104u, L"\\");
    v27 = v26;
    if ( v26 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_68;
      }
      v29 = 52;
      goto LABEL_67;
    }
    v30 = StringCchCatW(FullPath, 0x104u, a1);
    v27 = v30;
    if ( v30 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_68;
      }
      v29 = 53;
      goto LABEL_67;
    }
    v31 = 2147483646;
    v32 = FullPath;
    v33 = 260;
    v34 = FileName;
    do
    {
      if ( !v31 )
        break;
      if ( !*v32 )
        break;
      *v34++ = *v32++;
      --v31;
      --v33;
    }
    while ( v33 );
    v35 = v34 - 1;
    if ( v33 )
      v35 = v34;
    *v35 = 0;
    if ( v33 )
    {
      v38 = StringCchCatW(FileName, 0x104u, L".cov");
      v27 = v38;
      if ( v38 < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_68;
        }
        v29 = 55;
        goto LABEL_67;
      }
      if ( GetFileAttributesW(FileName) == -1 )
      {
        if ( GetFileAttributesW(FullPath) != -1 )
          goto LABEL_106;
LABEL_61:
        LastError = 2;
        goto LABEL_122;
      }
      v39 = FileName;
      v40 = 260;
      v41 = FullPath;
      do
      {
        if ( !v9 )
          break;
        if ( !*v39 )
          break;
        *v41++ = *v39++;
        --v9;
        --v40;
      }
      while ( v40 );
      v42 = v41 - 1;
      if ( v40 )
        v42 = v41;
      *v42 = 0;
      if ( v40 )
        goto LABEL_106;
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_18:
        LastError = 122;
        goto LABEL_121;
      }
      v37 = 56;
    }
    else
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_18;
      }
      v37 = 54;
    }
    WPP_SF_d(*((_QWORD *)v36 + 2), v37, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, 122);
    goto LABEL_18;
  }
  if ( GetFileAttributesW(FullPath) == -1 )
  {
    LastError = 2;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        (unsigned int)&WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
        (unsigned int)FullPath,
        2);
    }
    goto LABEL_122;
  }
LABEL_106:
  v43 = StringCchCopyW(a4, 0x104u, FullPath);
  v27 = v43;
  if ( v43 < 0 )
  {
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_68;
    }
    v29 = 57;
LABEL_67:
    WPP_SF_d(*((_QWORD *)v28 + 2), v29, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v27);
LABEL_68:
    LastError = v27;
    goto LABEL_121;
  }
  File = (void *)InternalSafeCreateFile(a4, 0x80000000, 1u, v44, 3u, 128);
  if ( File == (void *)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        (unsigned int)&WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
        (_DWORD)a4,
        LastError);
    }
  }
  else if ( !CloseHandle(File)
         && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v46 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, v46);
  }
LABEL_121:
  if ( LastError )
    goto LABEL_122;
  return v14;
}

```

## disassembly

```asm
0x14006e6dc  mov     [rsp-8+arg_8], rbx
0x14006e6e1  push    rbp
0x14006e6e2  push    rsi
0x14006e6e3  push    rdi
0x14006e6e4  push    r12
0x14006e6e6  push    r13
0x14006e6e8  push    r14
0x14006e6ea  push    r15
0x14006e6ec  lea     rbp, [rsp-990h]
0x14006e6f4  sub     rsp, 0A90h
0x14006e6fb  mov     rax, cs:__security_cookie
0x14006e702  xor     rax, rsp
0x14006e705  mov     [rbp+9C0h+var_40], rax
0x14006e70c  mov     r12, r9
0x14006e70f  mov     edi, r8d
0x14006e712  mov     r15, rcx
0x14006e715  mov     r10, cs:WPP_GLOBAL_Control
0x14006e71c  lea     r11, WPP_GLOBAL_Control
0x14006e723  mov     r13d, 2
0x14006e729  cmp     r10, r11
0x14006e72c  jz      short loc_14006E75D
0x14006e72e  test    [r10+1Ch], r13b
0x14006e732  jz      short loc_14006E75D
0x14006e734  cmp     byte ptr [r10+19h], 5
0x14006e739  jb      short loc_14006E75D
0x14006e73b  mov     rcx, [r10+10h]
0x14006e73f  lea     edx, [r13+29h]
0x14006e743  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006e74a  call    WPP_SF_
0x14006e74f  mov     r10, cs:WPP_GLOBAL_Control
0x14006e756  lea     r11, WPP_GLOBAL_Control
0x14006e75d  xor     r9d, r9d; Dir
0x14006e760  test    r15, r15
0x14006e763  jnz     short loc_14006E76F
0x14006e765  mov     ebx, 57h ; 'W'
0x14006e76a  jmp     loc_14006EDF8
0x14006e76f  mov     r14d, 7FFFFFFEh
0x14006e775  lea     rax, [rsp+0AC0h+FullPath]
0x14006e77a  mov     ecx, r14d
0x14006e77d  mov     rdx, r15
0x14006e780  mov     ebx, 104h
0x14006e785  mov     esi, 1
0x14006e78a  test    rcx, rcx
0x14006e78d  jz      short loc_14006E7AB
0x14006e78f  movzx   r8d, word ptr [rdx]
0x14006e793  test    r8w, r8w
0x14006e797  jz      short loc_14006E7AB
0x14006e799  mov     [rax], r8w
0x14006e79d  add     rdx, r13
0x14006e7a0  add     rax, r13
0x14006e7a3  sub     rcx, rsi
0x14006e7a6  sub     rbx, rsi
0x14006e7a9  jnz     short loc_14006E78A
0x14006e7ab  test    rbx, rbx
0x14006e7ae  lea     rcx, [rax-2]
0x14006e7b2  cmovnz  rcx, rax
0x14006e7b6  mov     [rcx], r9w
0x14006e7ba  jnz     short loc_14006E801
0x14006e7bc  cmp     r10, r11
0x14006e7bf  jz      short loc_14006E7F2
0x14006e7c1  test    [r10+1Ch], r13b
0x14006e7c5  jz      short loc_14006E7F2
0x14006e7c7  cmp     [r10+19h], r13b
0x14006e7cb  jb      short loc_14006E7F2
0x14006e7cd  mov     rcx, [r10+10h]
0x14006e7d1  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006e7d8  mov     rax, rbx
0x14006e7db  mov     edx, 2Ch ; ','
0x14006e7e0  neg     rax
0x14006e7e3  sbb     r9d, r9d
0x14006e7e6  not     r9d
0x14006e7e9  and     r9d, 7Ah
0x14006e7ed  call    WPP_SF_d
0x14006e7f2  neg     rbx
0x14006e7f5  sbb     ebx, ebx
0x14006e7f7  not     ebx
0x14006e7f9  and     ebx, 7Ah
0x14006e7fc  jmp     loc_14006EDF4
0x14006e801  mov     ebx, r9d
0x14006e804  cmp     edi, esi
0x14006e806  jnz     loc_14006E997
0x14006e80c  mov     ecx, 100h
0x14006e811  lea     rax, [rbp+9C0h+var_650]
0x14006e818  mov     [rsp+0AC0h+ExtCount], rcx; ExtCount
0x14006e81d  xor     r8d, r8d; DriveCount
0x14006e820  mov     [rsp+0AC0h+Ext], rax; Ext
0x14006e825  xor     edx, edx; Drive
0x14006e827  mov     [rsp+0AC0h+FilenameCount], rcx; FilenameCount
0x14006e82c  lea     rax, [rbp+9C0h+var_240]
0x14006e833  mov     [rsp+0AC0h+Filename], rax; Filename
0x14006e838  lea     rcx, [rsp+0AC0h+FullPath]; FullPath
0x14006e83d  mov     [rsp+0AC0h+DirCount], r9; DirCount
0x14006e842  call    cs:__imp__wsplitpath_s
0x14006e848  xor     r10d, r10d
0x14006e84b  test    eax, eax
0x14006e84d  jz      short loc_14006E88D
0x14006e84f  mov     ebx, 65Bh
0x14006e854  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e85b  lea     rax, WPP_GLOBAL_Control
0x14006e862  cmp     rcx, rax
0x14006e865  jz      short loc_14006E88D
0x14006e867  test    [rcx+1Ch], r13b
0x14006e86b  jz      short loc_14006E88D
0x14006e86d  cmp     [rcx+19h], r13b
0x14006e871  jb      short loc_14006E88D
0x14006e873  mov     rcx, [rcx+10h]
0x14006e877  lea     edx, [r10+2Dh]
0x14006e87b  mov     r9d, ebx
0x14006e87e  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006e885  call    WPP_SF_d
0x14006e88a  xor     r10d, r10d
0x14006e88d  mov     r11d, 104h
0x14006e893  lea     r8, [rbp+9C0h+var_240]
0x14006e89a  mov     edx, r11d
0x14006e89d  lea     rax, [rbp+9C0h+String1]
0x14006e8a4  mov     rcx, r14
0x14006e8a7  test    rcx, rcx
0x14006e8aa  jz      short loc_14006E8C8
0x14006e8ac  movzx   r9d, word ptr [r8]
0x14006e8b0  test    r9w, r9w
0x14006e8b4  jz      short loc_14006E8C8
0x14006e8b6  mov     [rax], r9w
0x14006e8ba  add     r8, r13
0x14006e8bd  add     rax, r13
0x14006e8c0  sub     rcx, rsi
0x14006e8c3  sub     rdx, rsi
0x14006e8c6  jnz     short loc_14006E8A7
0x14006e8c8  test    rdx, rdx
0x14006e8cb  lea     rcx, [rax-2]
0x14006e8cf  lea     r8, [rbp+9C0h+var_650]; unsigned __int16 *
0x14006e8d6  mov     rdx, r11; unsigned __int64
0x14006e8d9  cmovnz  rcx, rax
0x14006e8dd  mov     [rcx], r10w
0x14006e8e1  lea     rcx, [rbp+9C0h+String1]; unsigned __int16 *
0x14006e8e8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14006e8ed  lea     rdx, [rsp+0AC0h+FullPath]; String2
0x14006e8f2  lea     rcx, [rbp+9C0h+String1]; String1
0x14006e8f9  call    cs:__imp__wcsicmp
0x14006e8ff  test    eax, eax
0x14006e901  jz      short loc_14006E94D
0x14006e903  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e90a  lea     rax, WPP_GLOBAL_Control
0x14006e911  cmp     rcx, rax
0x14006e914  jz      loc_14006E765
0x14006e91a  test    [rcx+1Ch], r13b
0x14006e91e  jz      loc_14006E765
0x14006e924  cmp     [rcx+19h], r13b
0x14006e928  jb      loc_14006E765
0x14006e92e  mov     edx, 2Eh ; '.'
0x14006e933  mov     rcx, [rcx+10h]
0x14006e937  lea     r9, [rsp+0AC0h+FullPath]
0x14006e93c  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006e943  call    WPP_SF_S
0x14006e948  jmp     loc_14006E765
0x14006e94d  lea     rdx, aLnk; ".lnk"
0x14006e954  lea     rcx, [rbp+9C0h+var_650]; String1
0x14006e95b  call    cs:__imp__wcsicmp
0x14006e961  test    eax, eax
0x14006e963  jnz     short loc_14006E997
0x14006e965  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e96c  lea     rax, WPP_GLOBAL_Control
0x14006e973  cmp     rcx, rax
0x14006e976  jz      loc_14006E765
0x14006e97c  test    [rcx+1Ch], r13b
0x14006e980  jz      loc_14006E765
0x14006e986  cmp     [rcx+19h], r13b
0x14006e98a  jb      loc_14006E765
0x14006e990  mov     edx, 2Fh ; '/'
0x14006e995  jmp     short loc_14006E933
0x14006e997  mov     edx, 5Ch ; '\'; Ch
0x14006e99c  lea     rcx, [rsp+0AC0h+FullPath]; Str
0x14006e9a1  call    cs:__imp_wcschr
0x14006e9a7  test    rax, rax
0x14006e9aa  jz      short loc_14006EA14
0x14006e9ac  lea     rcx, [rsp+0AC0h+FullPath]; lpFileName
0x14006e9b1  call    cs:__imp_GetFileAttributesW
0x14006e9b7  or      edi, 0FFFFFFFFh
0x14006e9ba  cmp     eax, edi
0x14006e9bc  jnz     loc_14006ECE7
0x14006e9c2  mov     ebx, r13d
0x14006e9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e9cc  lea     rax, WPP_GLOBAL_Control
0x14006e9d3  cmp     rcx, rax
0x14006e9d6  jz      loc_14006EDF8
0x14006e9dc  test    [rcx+1Ch], r13b
0x14006e9e0  jz      loc_14006EDF8
0x14006e9e6  cmp     [rcx+19h], r13b
0x14006e9ea  jb      loc_14006EDF8
0x14006e9f0  mov     rcx, [rcx+10h]
0x14006e9f4  lea     r9, [rsp+0AC0h+FullPath]
0x14006e9f9  mov     edx, 30h ; '0'
0x14006e9fe  mov     dword ptr [rsp+0AC0h+DirCount], r13d
0x14006ea03  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006ea0a  call    WPP_SF_Sd
0x14006ea0f  jmp     loc_14006EDF8
0x14006ea14  test    edi, edi
0x14006ea16  jz      short loc_14006EA5E
0x14006ea18  lea     rdx, [rsp+0AC0h+FullPath]
0x14006ea1d  call    GetServerCpDir
0x14006ea22  test    eax, eax
0x14006ea24  jnz     loc_14006EAB8
0x14006ea2a  call    cs:__imp_GetLastError
0x14006ea30  mov     ebx, eax
0x14006ea32  mov     rax, cs:WPP_GLOBAL_Control
0x14006ea39  lea     rcx, WPP_GLOBAL_Control
0x14006ea40  cmp     rax, rcx
0x14006ea43  jz      short loc_14006EAB8
0x14006ea45  test    [rax+1Ch], r13b
0x14006ea49  jz      short loc_14006EAB8
0x14006ea4b  cmp     [rax+19h], r13b
0x14006ea4f  jb      short loc_14006EAB8
0x14006ea51  call    cs:__imp_GetLastError
0x14006ea57  mov     edx, 31h ; '1'
0x14006ea5c  jmp     short loc_14006EA9E
0x14006ea5e  lea     rcx, [rsp+0AC0h+FullPath]; unsigned __int16 *
0x14006ea63  call    GetClientCpDir
0x14006ea68  test    eax, eax
0x14006ea6a  jnz     short loc_14006EAB8
0x14006ea6c  call    cs:__imp_GetLastError
0x14006ea72  mov     ebx, eax
0x14006ea74  mov     rax, cs:WPP_GLOBAL_Control
0x14006ea7b  lea     rcx, WPP_GLOBAL_Control
0x14006ea82  cmp     rax, rcx
0x14006ea85  jz      short loc_14006EAB8
0x14006ea87  test    [rax+1Ch], r13b
0x14006ea8b  jz      short loc_14006EAB8
0x14006ea8d  cmp     [rax+19h], r13b
0x14006ea91  jb      short loc_14006EAB8
0x14006ea93  call    cs:__imp_GetLastError
0x14006ea99  mov     edx, 33h ; '3'
0x14006ea9e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006eaa5  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006eaac  mov     r9d, eax
0x14006eaaf  mov     rcx, [rcx+10h]
0x14006eab3  call    WPP_SF_d
0x14006eab8  test    ebx, ebx
0x14006eaba  jz      short loc_14006EAC4
0x14006eabc  mov     ebx, r13d
0x14006eabf  jmp     loc_14006EDF8
0x14006eac4  lea     r8, SubBlock; "\\"
0x14006eacb  mov     edx, 104h; unsigned __int64
0x14006ead0  lea     rcx, [rsp+0AC0h+FullPath]; unsigned __int16 *
0x14006ead5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14006eada  mov     edi, eax
0x14006eadc  test    eax, eax
0x14006eade  jns     short loc_14006EB20
0x14006eae0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006eae7  lea     rax, WPP_GLOBAL_Control
0x14006eaee  cmp     rcx, rax
0x14006eaf1  jz      short loc_14006EB18
0x14006eaf3  test    [rcx+1Ch], r13b
0x14006eaf7  jz      short loc_14006EB18
0x14006eaf9  cmp     [rcx+19h], r13b
0x14006eafd  jb      short loc_14006EB18
0x14006eaff  mov     edx, 34h ; '4'
0x14006eb04  mov     rcx, [rcx+10h]
0x14006eb08  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x14006eb0f  movzx   r9d, di
0x14006eb13  call    WPP_SF_d
0x14006eb18  movzx   ebx, di
0x14006eb1b  jmp     loc_14006EDF4
0x14006eb20  mov     r8, r15; unsigned __int16 *
0x14006eb23  lea     rcx, [rsp+0AC0h+FullPath]; unsigned __int16 *
0x14006eb28  mov     r15d, 104h
0x14006eb2e  mov     edx, r15d; unsigned __int64
0x14006eb31  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14006eb36  xor     r9d, r9d
0x14006eb39  mov     edi, eax
0x14006eb3b  test    eax, eax
0x14006eb3d  jns     short loc_14006EB64
0x14006eb3f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006eb46  lea     rax, WPP_GLOBAL_Control
0x14006eb4d  cmp     rcx, rax
0x14006eb50  jz      short loc_14006EB18
0x14006eb52  test    [rcx+1Ch], r13b
0x14006eb56  jz      short loc_14006EB18
0x14006eb58  cmp     [rcx+19h], r13b
0x14006eb5c  jb      short loc_14006EB18
0x14006eb5e  lea     edx, [r9+35h]
0x14006eb62  jmp     short loc_14006EB04
0x14006eb64  mov     rcx, r14
0x14006eb67  lea     rdx, [rsp+0AC0h+FullPath]
0x14006eb6c  mov     rdi, r15
0x14006eb6f  lea     rax, [rbp+9C0h+FileName]
0x14006eb76  test    rcx, rcx
0x14006eb79  jz      short loc_14006EB97
0x14006eb7b  movzx   r8d, word ptr [rdx]
0x14006eb7f  test    r8w, r8w
0x14006eb83  jz      short loc_14006EB97
0x14006eb85  mov     [rax], r8w
0x14006eb89  add     rdx, r13
0x14006eb8c  add     rax, r13
0x14006eb8f  sub     rcx, rsi
0x14006eb92  sub     rdi, rsi
0x14006eb95  jnz     short loc_14006EB76
0x14006eb97  test    rdi, rdi
0x14006eb9a  lea     rcx, [rax-2]
0x14006eb9e  cmovnz  rcx, rax
0x14006eba2  mov     [rcx], r9w
0x14006eba6  jnz     short loc_14006EBF4
  ... truncated ...
```
