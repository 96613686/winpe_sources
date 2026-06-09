# sub_1803DDCA8

- ea: `0x1803ddca8`
- end: `0x1803de33b`
- name: `sub_1803DDCA8`
- size: `1683`
- prototype: `__int64 __fastcall(__int64, int, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x1803da5a0`

## callees

- `0x180025067`
- `0x18013f000`
- `0x1801655e0`
- `0x1801655f0`
- `0x180176a30`
- `0x1801a08a8`
- `0x1801a1648`
- `0x1801a166c`
- `0x1801a5560`
- `0x1801c8638`
- `0x1803dd98c`
- `0x1803ddca8`
- `0x1803dfcd8`
- `0x1805687f0`
- `0x180569814`
- `0x18056aed4`
- `0x180754204`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x1803dde25`
- `KERNEL32!GetFileSizeEx` at `0x1803dde25`
- `KERNEL32!MoveFileExW` at `0x1803ddf18`
- `KERNEL32!MoveFileExW` at `0x1803ddf18`
- `KERNEL32!DeleteFileW` at `0x1803dde97`
- `KERNEL32!DeleteFileW` at `0x1803ddf2e`
- `KERNEL32!DeleteFileW` at `0x1803dde97`
- `KERNEL32!DeleteFileW` at `0x1803ddf2e`
- `KERNEL32!CloseHandle` at `0x1803ddeb3`
- `KERNEL32!CloseHandle` at `0x1803ddeb3`
- `KERNEL32!GetLastError` at `0x1803dde33`
- `KERNEL32!GetLastError` at `0x1803ddf22`
- `KERNEL32!GetLastError` at `0x1803de10b`
- `KERNEL32!GetLastError` at `0x1803de1fc`
- `KERNEL32!GetLastError` at `0x1803de265`
- `KERNEL32!GetLastError` at `0x1803de2c8`
- `KERNEL32!GetLastError` at `0x1803dde33`
- `KERNEL32!GetLastError` at `0x1803ddf22`
- `KERNEL32!GetLastError` at `0x1803de10b`
- `KERNEL32!GetLastError` at `0x1803de1fc`
- `KERNEL32!GetLastError` at `0x1803de265`
- `KERNEL32!GetLastError` at `0x1803de2c8`

## pseudocode

```c
__int64 __fastcall sub_1803DDCA8(__int64 a1, int a2, __int64 a3, _OWORD *a4)
{
  DWORD v6; // ebx
  union _LARGE_INTEGER *v7; // r12
  DWORD v8; // eax
  DWORD v9; // eax
  __int64 v10; // rcx
  WCHAR *v11; // r15
  void *v12; // rcx
  DWORD LastError; // eax
  HANDLE *v14; // rcx
  void *v15; // rcx
  NTSTATUS v16; // eax
  ULONG v17; // eax
  int v18; // r15d
  __int64 v19; // rcx
  __int128 v20; // xmm0
  DWORD v21; // eax
  unsigned __int64 v22; // rcx
  __int64 v23; // rax
  _QWORD *v24; // rcx
  __int64 v25; // r9
  __int64 v26; // rdx
  bool v27; // cf
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rdx
  unsigned __int64 v31; // r9
  unsigned __int64 HighPart; // rcx
  int v33; // edx
  unsigned __int64 v34; // r9
  const WCHAR *lpFileName; // [rsp+30h] [rbp-89h]
  _OWORD *lpMem; // [rsp+38h] [rbp-81h]
  unsigned __int64 v41; // [rsp+58h] [rbp-61h] BYREF
  SIZE_T dwBytes; // [rsp+60h] [rbp-59h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v44[96]; // [rsp+70h] [rbp-49h] BYREF

  if ( *(_QWORD *)(a1 + 16) == -1 )
    sub_1801A08A8(a1);
  v6 = 0;
  v41 = 0;
  dwBytes = 32;
  lpMem = 0;
  lpFileName = 0;
  v7 = (union _LARGE_INTEGER *)sub_1801655F0(32);
  sub_1803DFCD8(a1 + 32, v44);
  if ( !v7 )
  {
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
      sub_1801A1648(*((_QWORD *)hDevice + 2), 16, qword_180CBC538);
    goto LABEL_7;
  }
  if ( *(_DWORD *)(a1 + 8) != 2 )
  {
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
      sub_1801A1648(*((_QWORD *)hDevice + 2), 17, qword_180CBC538);
    v6 = 4317;
    goto LABEL_97;
  }
  v8 = *(_DWORD *)(a1 + 48);
  *(_OWORD *)&v7[1].LowPart = *(_OWORD *)(a1 + 32);
  v7[3].LowPart = v8;
  v9 = sub_180569814(a2, 1, (unsigned int)&dwBytes, (_DWORD)v7, (__int64)&v41, 0);
  FileSize.LowPart = v9;
  if ( v9 != 1 )
  {
    if ( v9 )
    {
      if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
        goto LABEL_96;
      GetLastError();
      v30 = 31;
    }
    else
    {
      if ( dwBytes < 0x20 )
      {
        if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
          sub_1801A166C(*((_QWORD *)hDevice + 2), 22, qword_180CBC538, (unsigned int)dwBytes);
        goto LABEL_46;
      }
      v22 = v41;
      if ( v41 + 16 < v41 )
      {
        if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
          sub_1801A1648(*((_QWORD *)hDevice + 2), 23, qword_180CBC538);
        v6 = 111;
        goto LABEL_97;
      }
      if ( dwBytes > 0x20 )
      {
        v23 = sub_180176A30(v7, dwBytes);
        if ( !v23 )
        {
          v24 = hDevice;
          if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
            goto LABEL_7;
          v25 = (unsigned int)dwBytes;
          v26 = 24;
LABEL_57:
          sub_1801A166C(v24[2], v26, qword_180CBC538, v25);
LABEL_7:
          v6 = 8;
LABEL_97:
          v11 = 0;
          goto LABEL_98;
        }
        v22 = v41;
        v7 = (union _LARGE_INTEGER *)v23;
      }
      v27 = __CFADD__(v22, 16);
      v28 = v22 + 16;
      if ( v27 )
        v28 = -1;
      v29 = sub_1801655F0(v28);
      lpMem = (_OWORD *)v29;
      if ( !v29 )
      {
        v24 = hDevice;
        if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
          goto LABEL_7;
        v25 = (unsigned int)v41;
        v26 = 25;
        goto LABEL_57;
      }
      FileSize.LowPart = sub_180569814(a2, 7, (unsigned int)&dwBytes, (_DWORD)v7, (__int64)&v41, v29);
      if ( !FileSize.LowPart )
      {
        v31 = v41;
        HighPart = (unsigned int)v7[3].HighPart;
        if ( HighPart <= v41 >> 4 )
        {
          if ( (_DWORD)HighPart == -1 )
          {
            if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
              sub_1801A1648(*((_QWORD *)hDevice + 2), 29, qword_180CBC538);
            v6 = 534;
            goto LABEL_97;
          }
          v33 = dwBytes;
          v7[3].HighPart = HighPart + 1;
          v34 = v31 + 16;
          v41 = v34;
          lpMem[HighPart] = *a4;
          if ( (unsigned int)sub_18056AED4(a2, v33, (_DWORD)v7, v34, (__int64)lpMem, 0) )
          {
            if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
            {
              GetLastError();
              sub_1801A5560(*((_QWORD *)hDevice + 2), 30, qword_180CBC538);
            }
            v6 = 29;
            goto LABEL_97;
          }
          v18 = v41;
          v19 = (__int64)lpMem;
          goto LABEL_84;
        }
        if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
        {
          _mm_lfence();
          sub_1801A5560(*((_QWORD *)hDevice + 2), 27, qword_180CBC538);
        }
LABEL_46:
        v6 = 13;
        goto LABEL_97;
      }
      if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      {
LABEL_96:
        v6 = 30;
        goto LABEL_97;
      }
      GetLastError();
      v30 = 26;
    }
    sub_1801A5560(*((_QWORD *)hDevice + 2), v30, qword_180CBC538);
    goto LABEL_96;
  }
  lpFileName = (const WCHAR *)sub_1803DD98C(v10, a3, a1 + 32);
  if ( !lpFileName )
  {
    v6 = 8;
    v11 = 0;
    goto LABEL_98;
  }
  v12 = *(void **)(a1 + 16);
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(v12, &FileSize) )
  {
    LastError = GetLastError();
    v6 = LastError;
    v14 = (HANDLE *)hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      goto LABEL_21;
    sub_1801A166C(*((_QWORD *)hDevice + 2), 19, qword_180CBC538, LastError);
LABEL_20:
    v14 = (HANDLE *)hDevice;
LABEL_21:
    v11 = (WCHAR *)lpFileName;
    goto LABEL_22;
  }
  v16 = sub_180754204(*(HANDLE *)(a1 + 16));
  v17 = RtlNtStatusToDosError(v16);
  v6 = v17;
  if ( v17 )
  {
    v14 = (HANDLE *)hDevice;
    if ( hDevice == &hDevice )
    {
LABEL_26:
      DeleteFileW(lpFileName);
      v11 = (WCHAR *)lpFileName;
LABEL_27:
      v15 = *(void **)(a1 + 16);
      if ( v15 != (void *)-1LL )
      {
        CloseHandle(v15);
        *(_QWORD *)(a1 + 16) = -1;
      }
      goto LABEL_98;
    }
    if ( (*((_BYTE *)hDevice + 28) & 1) != 0 )
    {
      sub_1801A166C(*((_QWORD *)hDevice + 2), 20, qword_180CBC538, v17);
      v14 = (HANDLE *)hDevice;
    }
LABEL_23:
    if ( v14 != &hDevice && (*((_BYTE *)v14 + 28) & 1) != 0 )
      sub_1801C8638(v14[2], 33, qword_180CBC538, lpFileName);
    goto LABEL_26;
  }
  if ( !MoveFileExW(*(LPCWSTR *)(a1 + 24), lpFileName, 0) )
  {
    v6 = GetLastError();
    DeleteFileW(*(LPCWSTR *)(a1 + 24));
    goto LABEL_20;
  }
  v18 = 16;
  lpMem = (_OWORD *)sub_1801655F0(16);
  v19 = (__int64)lpMem;
  if ( !lpMem )
  {
    v14 = (HANDLE *)hDevice;
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
    {
      sub_1801A1648(*((_QWORD *)hDevice + 2), 21, qword_180CBC538);
      v14 = (HANDLE *)hDevice;
    }
    v6 = 8;
    goto LABEL_23;
  }
  v20 = *(_OWORD *)(a1 + 32);
  *v7 = FileSize;
  v21 = *(_DWORD *)(a1 + 48);
  *(_OWORD *)&v7[1].LowPart = v20;
  v7[3].LowPart = v21;
  v41 = 16;
  v7[3].HighPart = 1;
  *lpMem = *a4;
LABEL_84:
  if ( (unsigned int)sub_1805687F0(a2, dwBytes, (_DWORD)v7, v18, v19) )
  {
    v14 = (HANDLE *)hDevice;
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
    {
      GetLastError();
      sub_1801A5560(*((_QWORD *)hDevice + 2), 32, qword_180CBC538);
      v14 = (HANDLE *)hDevice;
    }
    v6 = 29;
  }
  else
  {
    *(_DWORD *)(a1 + 8) = 3;
    v14 = (HANDLE *)hDevice;
  }
  v11 = (WCHAR *)lpFileName;
  if ( lpFileName )
  {
LABEL_22:
    if ( !v6 )
      goto LABEL_27;
    goto LABEL_23;
  }
LABEL_98:
  sub_1801655E0(v11);
  sub_1801655E0(v7);
  sub_1801655E0(lpMem);
  return v6;
}

```

## disassembly

```asm
0x1803ddca8  mov     [rsp-8+arg_18], rbx
0x1803ddcad  push    rbp
0x1803ddcae  push    rsi
0x1803ddcaf  push    rdi
0x1803ddcb0  push    r12
0x1803ddcb2  push    r13
0x1803ddcb4  push    r14
0x1803ddcb6  push    r15
0x1803ddcb8  lea     rbp, [rsp-27h]
0x1803ddcbd  sub     rsp, 0E0h
0x1803ddcc4  mov     rax, cs:__security_cookie
0x1803ddccb  xor     rax, rsp
0x1803ddcce  mov     [rbp+57h+var_40], rax
0x1803ddcd2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1803ddcd6  mov     [rbp+57h+var_C8], r9
0x1803ddcda  mov     rsi, rdx
0x1803ddcdd  mov     [rbp+57h+var_C0], r8
0x1803ddce1  mov     r13, rcx
0x1803ddce4  mov     [rbp+57h+var_D0], rdx
0x1803ddce8  cmp     [rcx+10h], rax
0x1803ddcec  jnz     short loc_1803DDCF3
0x1803ddcee  call    sub_1801A08A8
0x1803ddcf3  xor     edi, edi
0x1803ddcf5  mov     ebx, edi
0x1803ddcf7  mov     [rbp+57h+var_B8], rdi
0x1803ddcfb  lea     eax, [rdi+20h]
0x1803ddcfe  mov     ecx, eax
0x1803ddd00  mov     [rbp+57h+dwBytes], rax
0x1803ddd04  call    sub_1801655F0
0x1803ddd09  lea     r15, [r13+20h]
0x1803ddd0d  mov     [rsp+110h+lpMem], rdi
0x1803ddd12  mov     rcx, r15
0x1803ddd15  mov     [rsp+110h+lpFileName], rdi
0x1803ddd1a  lea     rdx, [rbp+57h+var_A0]
0x1803ddd1e  mov     r12, rax
0x1803ddd21  call    sub_1803DFCD8
0x1803ddd26  test    r12, r12
0x1803ddd29  jnz     short loc_1803DDD66
0x1803ddd2b  mov     rcx, cs:hDevice
0x1803ddd32  lea     rsi, hDevice
0x1803ddd39  cmp     rcx, rsi
0x1803ddd3c  jz      short loc_1803DDD5C
0x1803ddd3e  lea     edi, [r12+1]
0x1803ddd43  test    [rcx+1Ch], dil
0x1803ddd47  jz      short loc_1803DDD5C
0x1803ddd49  mov     rcx, [rcx+10h]
0x1803ddd4d  lea     edx, [rdi+0Fh]
0x1803ddd50  lea     r8, qword_180CBC538
0x1803ddd57  call    sub_1801A1648
0x1803ddd5c  mov     ebx, 8
0x1803ddd61  jmp     loc_1803DE2F3
0x1803ddd66  cmp     dword ptr [r13+8], 2
0x1803ddd6b  jz      short loc_1803DDDA8
0x1803ddd6d  mov     rcx, cs:hDevice
0x1803ddd74  lea     rsi, hDevice
0x1803ddd7b  cmp     rcx, rsi
0x1803ddd7e  jz      short loc_1803DDD9E
0x1803ddd80  mov     edi, 1
0x1803ddd85  test    [rcx+1Ch], dil
0x1803ddd89  jz      short loc_1803DDD9E
0x1803ddd8b  mov     rcx, [rcx+10h]
0x1803ddd8f  lea     edx, [rdi+10h]
0x1803ddd92  lea     r8, qword_180CBC538
0x1803ddd99  call    sub_1801A1648
0x1803ddd9e  mov     ebx, 10DDh
0x1803ddda3  jmp     loc_1803DE2F3
0x1803ddda8  mov     eax, [r15+10h]
0x1803dddac  lea     r8, [rbp+57h+dwBytes]
0x1803dddb0  movups  xmm0, xmmword ptr [r15]
0x1803dddb4  mov     [rsp+110h+var_E8], rdi
0x1803dddb9  mov     r9, r12
0x1803dddbc  mov     edi, 1
0x1803dddc1  mov     rcx, rsi
0x1803dddc4  movups  xmmword ptr [r12+8], xmm0
0x1803dddca  mov     [r12+18h], eax
0x1803dddcf  mov     edx, edi
0x1803dddd1  lea     rax, [rbp+57h+var_B8]
0x1803dddd5  mov     [rsp+110h+var_F0], rax
0x1803dddda  call    sub_180569814
0x1803ddddf  mov     dword ptr [rbp+57h+FileSize], eax
0x1803ddde2  lea     r14, qword_180CBC538
0x1803ddde9  lea     rsi, hDevice
0x1803dddf0  cmp     eax, edi
0x1803dddf2  jnz     loc_1803DDFBB
0x1803dddf8  mov     rdx, [rbp+57h+var_C0]
0x1803dddfc  mov     r8, r15
0x1803dddff  call    sub_1803DD98C
0x1803dde04  mov     [rsp+110h+lpFileName], rax
0x1803dde09  test    rax, rax
0x1803dde0c  jnz     short loc_1803DDE19
0x1803dde0e  lea     ebx, [rdi+7]
0x1803dde11  mov     r15, rax
0x1803dde14  jmp     loc_1803DE2F8
0x1803dde19  mov     rcx, [r13+10h]; hFile
0x1803dde1d  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x1803dde21  mov     qword ptr [rbp+57h+FileSize], rbx
0x1803dde25  call    cs:GetFileSizeEx
0x1803dde2b  test    eax, eax
0x1803dde2d  jnz     loc_1803DDEC2
0x1803dde33  call    cs:__imp_GetLastError
0x1803dde39  mov     ebx, eax
0x1803dde3b  mov     rcx, cs:hDevice
0x1803dde42  cmp     rcx, rsi
0x1803dde45  jz      short loc_1803DDE68
0x1803dde47  test    [rcx+1Ch], dil
0x1803dde4b  jz      short loc_1803DDE68
0x1803dde4d  mov     rcx, [rcx+10h]
0x1803dde51  mov     edx, 13h
0x1803dde56  mov     r9d, eax
0x1803dde59  mov     r8, r14
0x1803dde5c  call    sub_1801A166C
0x1803dde61  mov     rcx, cs:hDevice
0x1803dde68  mov     r15, [rsp+110h+lpFileName]
0x1803dde6d  test    ebx, ebx
0x1803dde6f  jz      short loc_1803DDEA2
0x1803dde71  cmp     rcx, rsi
0x1803dde74  jz      short loc_1803DDE92
0x1803dde76  test    [rcx+1Ch], dil
0x1803dde7a  jz      short loc_1803DDE92
0x1803dde7c  mov     r9, [rsp+110h+lpFileName]
0x1803dde81  mov     edx, 21h ; '!'
0x1803dde86  mov     rcx, [rcx+10h]
0x1803dde8a  mov     r8, r14
0x1803dde8d  call    sub_1801C8638
0x1803dde92  mov     rcx, [rsp+110h+lpFileName]; lpFileName
0x1803dde97  call    cs:__imp_DeleteFileW
0x1803dde9d  mov     r15, [rsp+110h+lpFileName]
0x1803ddea2  mov     rcx, [r13+10h]; hObject
0x1803ddea6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1803ddeaa  cmp     rcx, rdi
0x1803ddead  jz      loc_1803DE2F8
0x1803ddeb3  call    cs:__imp_CloseHandle
0x1803ddeb9  mov     [r13+10h], rdi
0x1803ddebd  jmp     loc_1803DE2F8
0x1803ddec2  mov     rcx, [r13+10h]; FileHandle
0x1803ddec6  xor     edx, edx
0x1803ddec8  call    sub_180754204
0x1803ddecd  mov     ecx, eax; Status
0x1803ddecf  call    RtlNtStatusToDosError
0x1803dded4  mov     ebx, eax
0x1803dded6  test    eax, eax
0x1803dded8  jz      short loc_1803DDF0C
0x1803ddeda  mov     rcx, cs:hDevice
0x1803ddee1  cmp     rcx, rsi
0x1803ddee4  jz      short loc_1803DDE92
0x1803ddee6  test    [rcx+1Ch], dil
0x1803ddeea  jz      short loc_1803DDE71
0x1803ddeec  mov     rcx, [rcx+10h]
0x1803ddef0  mov     edx, 14h
0x1803ddef5  mov     r9d, eax
0x1803ddef8  mov     r8, r14
0x1803ddefb  call    sub_1801A166C
0x1803ddf00  mov     rcx, cs:hDevice
0x1803ddf07  jmp     loc_1803DDE71
0x1803ddf0c  mov     rdx, [rsp+110h+lpFileName]; lpNewFileName
0x1803ddf11  xor     r8d, r8d; dwFlags
0x1803ddf14  mov     rcx, [r13+18h]; lpExistingFileName
0x1803ddf18  call    cs:MoveFileExW
0x1803ddf1e  test    eax, eax
0x1803ddf20  jnz     short loc_1803DDF39
0x1803ddf22  call    cs:__imp_GetLastError
0x1803ddf28  mov     rcx, [r13+18h]; lpFileName
0x1803ddf2c  mov     ebx, eax
0x1803ddf2e  call    cs:__imp_DeleteFileW
0x1803ddf34  jmp     loc_1803DDE61
0x1803ddf39  mov     r15d, 10h
0x1803ddf3f  mov     ecx, r15d
0x1803ddf42  call    sub_1801655F0
0x1803ddf47  mov     [rsp+110h+lpMem], rax
0x1803ddf4c  mov     rcx, rax
0x1803ddf4f  test    rax, rax
0x1803ddf52  jnz     short loc_1803DDF86
0x1803ddf54  mov     rcx, cs:hDevice
0x1803ddf5b  cmp     rcx, rsi
0x1803ddf5e  jz      short loc_1803DDF7C
0x1803ddf60  test    [rcx+1Ch], dil
0x1803ddf64  jz      short loc_1803DDF7C
0x1803ddf66  mov     rcx, [rcx+10h]
0x1803ddf6a  lea     edx, [rax+15h]
0x1803ddf6d  mov     r8, r14
0x1803ddf70  call    sub_1801A1648
0x1803ddf75  mov     rcx, cs:hDevice
0x1803ddf7c  mov     ebx, 8
0x1803ddf81  jmp     loc_1803DDE71
0x1803ddf86  mov     rax, qword ptr [rbp+57h+FileSize]
0x1803ddf8a  movups  xmm0, xmmword ptr [r13+20h]
0x1803ddf8f  mov     [r12], rax
0x1803ddf93  mov     eax, [r13+30h]
0x1803ddf97  movups  xmmword ptr [r12+8], xmm0
0x1803ddf9d  mov     [r12+18h], eax
0x1803ddfa2  mov     rax, [rbp+57h+var_C8]
0x1803ddfa6  mov     [rbp+57h+var_B8], r15
0x1803ddfaa  mov     [r12+1Ch], edi
0x1803ddfaf  movups  xmm0, xmmword ptr [rax]
0x1803ddfb2  movdqu  xmmword ptr [rcx], xmm0
0x1803ddfb6  jmp     loc_1803DE234
0x1803ddfbb  test    eax, eax
0x1803ddfbd  jnz     loc_1803DE2B6
0x1803ddfc3  mov     r8, [rbp+57h+dwBytes]
0x1803ddfc7  cmp     r8, 20h ; ' '
0x1803ddfcb  jnb     short loc_1803DDFFB
0x1803ddfcd  mov     rcx, cs:hDevice
0x1803ddfd4  cmp     rcx, rsi
0x1803ddfd7  jz      short loc_1803DDFF1
0x1803ddfd9  test    [rcx+1Ch], dil
0x1803ddfdd  jz      short loc_1803DDFF1
0x1803ddfdf  mov     rcx, [rcx+10h]
0x1803ddfe3  lea     edx, [rax+16h]
0x1803ddfe6  mov     r9d, r8d
0x1803ddfe9  mov     r8, r14
0x1803ddfec  call    sub_1801A166C
0x1803ddff1  mov     ebx, 0Dh
0x1803ddff6  jmp     loc_1803DE2F3
0x1803ddffb  mov     rcx, [rbp+57h+var_B8]
0x1803ddfff  lea     rax, [rcx+10h]
0x1803de003  cmp     rax, rcx
0x1803de006  jnb     short loc_1803DE035
0x1803de008  mov     rcx, cs:hDevice
0x1803de00f  cmp     rcx, rsi
0x1803de012  jz      short loc_1803DE02B
0x1803de014  test    [rcx+1Ch], dil
0x1803de018  jz      short loc_1803DE02B
0x1803de01a  mov     rcx, [rcx+10h]
0x1803de01e  mov     edx, 17h
0x1803de023  mov     r8, r14
0x1803de026  call    sub_1801A1648
0x1803de02b  mov     ebx, 6Fh ; 'o'
0x1803de030  jmp     loc_1803DE2F3
0x1803de035  cmp     r8, 20h ; ' '
0x1803de039  jbe     short loc_1803DE084
0x1803de03b  mov     rdx, r8; dwBytes
0x1803de03e  mov     rcx, r12; lpMem
0x1803de041  call    sub_180176A30
0x1803de046  test    rax, rax
0x1803de049  jnz     short loc_1803DE07D
0x1803de04b  mov     rcx, cs:hDevice
0x1803de052  cmp     rcx, rsi
0x1803de055  jz      loc_1803DDD5C
0x1803de05b  test    [rcx+1Ch], dil
0x1803de05f  jz      loc_1803DDD5C
0x1803de065  mov     r9d, dword ptr [rbp+57h+dwBytes]
0x1803de069  lea     edx, [rax+18h]
0x1803de06c  mov     rcx, [rcx+10h]
0x1803de070  mov     r8, r14
0x1803de073  call    sub_1801A166C
0x1803de078  jmp     loc_1803DDD5C
0x1803de07d  mov     rcx, [rbp+57h+var_B8]
0x1803de081  mov     r12, rax
0x1803de084  mov     r15d, 10h
0x1803de08a  add     rcx, r15
0x1803de08d  lea     rax, [r15-11h]
0x1803de091  cmovb   rcx, rax
0x1803de095  call    sub_1801655F0
0x1803de09a  mov     [rsp+110h+lpMem], rax
0x1803de09f  test    rax, rax
0x1803de0a2  jnz     short loc_1803DE0C7
0x1803de0a4  mov     rcx, cs:hDevice
0x1803de0ab  cmp     rcx, rsi
0x1803de0ae  jz      loc_1803DDD5C
0x1803de0b4  test    [rcx+1Ch], dil
0x1803de0b8  jz      loc_1803DDD5C
0x1803de0be  mov     r9d, dword ptr [rbp+57h+var_B8]
0x1803de0c2  lea     edx, [rax+19h]
0x1803de0c5  jmp     short loc_1803DE06C
0x1803de0c7  mov     rcx, [rbp+57h+var_D0]
0x1803de0cb  lea     r8, [rbp+57h+dwBytes]
0x1803de0cf  mov     [rsp+110h+var_E8], rax
0x1803de0d4  mov     r9, r12
0x1803de0d7  lea     rax, [rbp+57h+var_B8]
0x1803de0db  mov     edx, 7
0x1803de0e0  mov     [rsp+110h+var_F0], rax
0x1803de0e5  call    sub_180569814
0x1803de0ea  mov     dword ptr [rbp+57h+FileSize], eax
0x1803de0ed  test    eax, eax
0x1803de0ef  jz      short loc_1803DE11B
0x1803de0f1  mov     rcx, cs:hDevice
0x1803de0f8  cmp     rcx, rsi
0x1803de0fb  jz      loc_1803DE2EE
0x1803de101  test    [rcx+1Ch], dil
0x1803de105  jz      loc_1803DE2EE
0x1803de10b  call    cs:__imp_GetLastError
0x1803de111  mov     edx, 1Ah
0x1803de116  jmp     loc_1803DE2D3
0x1803de11b  mov     r9, [rbp+57h+var_B8]
0x1803de11f  mov     ecx, [r12+1Ch]
0x1803de124  mov     rax, r9
0x1803de127  shr     rax, 4
0x1803de12b  cmp     rcx, rax
0x1803de12e  jbe     short loc_1803DE174
0x1803de130  mov     rax, cs:hDevice
0x1803de137  cmp     rax, rsi
0x1803de13a  jz      loc_1803DDFF1
0x1803de140  test    [rax+1Ch], dil
0x1803de144  jz      loc_1803DDFF1
0x1803de14a  lfence
0x1803de14d  mov     eax, dword ptr [rbp+57h+var_B8]
0x1803de150  mov     r9d, ecx
0x1803de153  mov     rcx, cs:hDevice
0x1803de15a  mov     edx, 1Bh
0x1803de15f  mov     r8, r14
  ... truncated ...
```
