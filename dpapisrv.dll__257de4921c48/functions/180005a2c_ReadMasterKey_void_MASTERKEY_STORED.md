# ReadMasterKey(void *,MASTERKEY_STORED *)

- ea: `0x180005a2c`
- end: `0x1800060cf`
- name: `?ReadMasterKey@@YAHPEAXPEAUMASTERKEY_STORED@@@Z`
- size: `1699`
- prototype: `__int64 __fastcall(void *, struct MASTERKEY_STORED *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000e9c0`
- `0x18002d8f0`
- `0x18002ea4c`

## callees

- `0x180004c68`
- `0x180005658`
- `0x1800057e8`
- `0x180005a2c`
- `0x1800060e0`
- `0x18001c340`
- `0x18001c9c0`
- `0x1800244b8`
- `0x18003c620`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005abb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006098`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005cfc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005d4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005d7e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f20`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005cfc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005d4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005d7e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005fd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000600c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005fd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000600c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180005b81`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180005b81`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180005b52`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180005b52`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000606d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000606d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180005aff`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180005aff`

## pseudocode

```c
__int64 __fastcall ReadMasterKey(void *a1, struct MASTERKEY_STORED *a2)
{
  _DWORD *v4; // rdi
  RTL_SRWLOCK *LockEntryForUser; // rax
  DWORD FileSize; // eax
  __int64 v7; // r12
  HANDLE FileMappingW; // rax
  void *v9; // r13
  _DWORD *v10; // rax
  int v11; // r13d
  unsigned int v12; // eax
  unsigned int v13; // ecx
  __int64 v14; // rax
  unsigned int v15; // ecx
  __int64 v16; // rax
  unsigned int v17; // esi
  char *v18; // rsi
  HLOCAL v19; // rcx
  HLOCAL v20; // rcx
  HLOCAL v21; // rcx
  HLOCAL v22; // rcx
  __int64 v24; // rcx
  __int64 v25; // rdx
  HANDLE hObject; // [rsp+38h] [rbp-C0h]
  DWORD FileSizeHigh; // [rsp+40h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-B0h] BYREF
  _DWORD *v29; // [rsp+50h] [rbp-A8h]
  _DWORD *v30; // [rsp+58h] [rbp-A0h]
  PSID pSid2; // [rsp+60h] [rbp-98h]
  struct MASTERKEY_STORED *v32; // [rsp+70h] [rbp-88h]
  _OWORD v33[4]; // [rsp+80h] [rbp-78h]
  __int128 v34; // [rsp+C0h] [rbp-38h]

  v32 = a2;
  hFile = (HANDLE)-1LL;
  hObject = 0;
  FileSizeHigh = 0;
  v4 = 0;
  v30 = 0;
  pSid2 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_SS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      124,
      (unsigned int)WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
      *((_QWORD *)a2 + 1),
      (__int64)a2 + 16);
  if ( a1 )
  {
    pSid2 = (PSID)*((_QWORD *)a1 + 9);
    LockEntryForUser = (RTL_SRWLOCK *)GetLockEntryForUser(pSid2, 1);
    if ( LockEntryForUser )
      AcquireSRWLockShared(LockEntryForUser + 2);
  }
  if ( (unsigned int)OpenFileInStorageArea(
                       a1,
                       0x80000000,
                       *((const unsigned __int16 **)a2 + 1),
                       (const unsigned __int16 *)a2 + 8,
                       &hFile) )
  {
    v24 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_82;
    v25 = 125;
LABEL_88:
    WPP_SF_(*(_QWORD *)(v24 + 16), v25, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
LABEL_82:
    v17 = 0;
LABEL_83:
    v9 = hObject;
    goto LABEL_69;
  }
  FileSize = GetFileSize(hFile, &FileSizeHigh);
  v7 = FileSize;
  if ( FileSize == -1 && GetLastError() )
  {
    v24 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_82;
    v25 = 126;
    goto LABEL_88;
  }
  if ( (unsigned int)v7 < 0x80 || FileSizeHigh || (unsigned int)v7 > 0x3FFFC )
    goto LABEL_82;
  FileMappingW = CreateFileMappingW(hFile, 0, 2u, 0, 0, 0);
  v9 = FileMappingW;
  hObject = FileMappingW;
  if ( FileMappingW )
  {
    v10 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
    v4 = v10;
    v30 = v10;
    if ( v10 )
    {
      v11 = *v10;
      if ( *v10 > 2u )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 129, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
        v9 = hObject;
        v17 = 0;
      }
      else if ( v10[24] > 0xFFFFu || v10[26] > 0xFFFFu || (v12 = v10[28], v12 > 0xFFFF) || (v13 = v4[30], v13 > 0xFFFF) )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 130, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
        v9 = hObject;
        v17 = 0;
      }
      else if ( v4[24] + v4[26] + v12 + v13 > (unsigned __int64)(v7 - 128) )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 131, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
        v9 = hObject;
        v17 = 0;
      }
      else
      {
        v33[0] = *(_OWORD *)(v4 + 3);
        v33[1] = *(_OWORD *)(v4 + 7);
        v33[2] = *(_OWORD *)(v4 + 11);
        v33[3] = *(_OWORD *)(v4 + 15);
        v34 = *(_OWORD *)(v4 + 19);
        HIWORD(v34) = 0;
        v14 = -1;
        do
          ++v14;
        while ( *((_WORD *)a2 + v14 + 8) );
        v15 = 2 * v14 + 2;
        v16 = -1;
        do
          ++v16;
        while ( *((_WORD *)v33 + v16) );
        if ( v15 == 2 * (_DWORD)v16 + 2 )
        {
          if ( !memcmp_0((char *)a2 + 16, v4 + 3, v15) )
          {
            *(_DWORD *)a2 = v11;
            *((_DWORD *)a2 + 24) = v4[23];
            v18 = (char *)(v4 + 32);
            v29 = v4 + 32;
            if ( v4[24] )
            {
              v20 = LocalAlloc(0, (unsigned int)v4[24]);
              *((_QWORD *)a2 + 13) = v20;
              if ( !v20 )
              {
                v9 = hObject;
                v17 = 0;
                goto LABEL_69;
              }
              *((_DWORD *)a2 + 25) = v4[24];
              memcpy_0(v20, v4 + 32, (unsigned int)v4[24]);
              v18 += (unsigned int)v4[24];
              v29 = v18;
            }
            if ( v4[26] )
            {
              v21 = LocalAlloc(0, (unsigned int)v4[26]);
              *((_QWORD *)a2 + 15) = v21;
              if ( !v21 )
              {
                v9 = hObject;
                v17 = 0;
                goto LABEL_69;
              }
              *((_DWORD *)a2 + 28) = v4[26];
              memcpy_0(v21, v18, (unsigned int)v4[26]);
              v18 += (unsigned int)v4[26];
              v29 = v18;
            }
            if ( v4[28] )
            {
              v19 = LocalAlloc(0, (unsigned int)v4[28]);
              *((_QWORD *)a2 + 17) = v19;
              if ( !v19 )
              {
                v9 = hObject;
                v17 = 0;
                goto LABEL_69;
              }
              *((_DWORD *)a2 + 32) = v4[28];
              memcpy_0(v19, v18, (unsigned int)v4[28]);
              v18 += (unsigned int)v4[28];
              v29 = v18;
            }
            if ( v4[30] )
            {
              v22 = LocalAlloc(0, (unsigned int)v4[30]);
              *((_QWORD *)a2 + 19) = v22;
              if ( !v22 )
              {
                v9 = hObject;
                v17 = 0;
                goto LABEL_69;
              }
              *((_DWORD *)a2 + 36) = v4[30];
              memcpy_0(v22, v18, (unsigned int)v4[30]);
            }
            v17 = 1;
            goto LABEL_83;
          }
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_S(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              133,
              WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
              (char *)a2 + 16);
          v9 = hObject;
          v17 = 0;
        }
        else
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_S(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              132,
              WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
              (char *)a2 + 16);
          v9 = hObject;
          v17 = 0;
        }
      }
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 128, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
      v17 = 0;
    }
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 127, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    v17 = 0;
  }
LABEL_69:
  if ( pSid2 )
    ReleaseSharedLockForUser(pSid2);
  if ( v4 )
    UnmapViewOfFile(v4);
  if ( v9 )
    CloseHandle(v9);
  if ( hFile != (HANDLE)-1LL )
    CloseHandle(hFile);
  if ( !v17 )
    FreeMasterKey(a2);
  return v17;
}

```

## disassembly

```asm
0x180005a2c  mov     [rsp+arg_10], rbx
0x180005a31  mov     [rsp+arg_18], rsi
0x180005a36  push    rdi
0x180005a37  push    r12
0x180005a39  push    r13
0x180005a3b  push    r14
0x180005a3d  push    r15
0x180005a3f  sub     rsp, 0D0h
0x180005a46  mov     r15, rdx
0x180005a49  mov     r13, rcx
0x180005a4c  mov     [rsp+0F8h+var_88], rdx
0x180005a51  mov     [rsp+0F8h+hFile], 0FFFFFFFFFFFFFFFFh
0x180005a5a  xor     ebx, ebx
0x180005a5c  mov     [rsp+0F8h+hObject], rbx
0x180005a61  mov     [rsp+0F8h+FileSizeHigh], ebx
0x180005a65  mov     edi, ebx
0x180005a67  mov     [rsp+0F8h+var_A0], rbx
0x180005a6c  mov     [rsp+0F8h+var_C8], ebx
0x180005a70  mov     [rsp+0F8h+pSid2], rbx
0x180005a75  lea     r12, WPP_GLOBAL_Control
0x180005a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a83  lea     rsi, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180005a8a  cmp     rcx, r12
0x180005a8d  jnz     loc_180006038
0x180005a93  mov     r14d, 1
0x180005a99  test    r13, r13
0x180005a9c  jz      short loc_180005ACE
0x180005a9e  mov     r12, [r13+48h]
0x180005aa2  mov     [rsp+0F8h+pSid2], r12
0x180005aa7  mov     edx, r14d; int
0x180005aaa  mov     rcx, r12; pSourceSid
0x180005aad  call    ?GetLockEntryForUser@@YAPEAU_PER_USER_LOCK_ENTRY@@PEAXH@Z; GetLockEntryForUser(void *,int)
0x180005ab2  test    rax, rax
0x180005ab5  jz      short loc_180005AC7
0x180005ab7  lea     rcx, [rax+10h]; SRWLock
0x180005abb  call    cs:__imp_AcquireSRWLockShared
0x180005ac2  nop     dword ptr [rax+rax+00h]
0x180005ac7  lea     r12, WPP_GLOBAL_Control
0x180005ace  lea     r9, [r15+10h]; unsigned __int16 *
0x180005ad2  lea     rax, [rsp+0F8h+hFile]
0x180005ad7  mov     qword ptr [rsp+0F8h+dwMaximumSizeLow], rax; void **
0x180005adc  mov     r8, [r15+8]; unsigned __int16 *
0x180005ae0  mov     edx, 80000000h; unsigned int
0x180005ae5  mov     rcx, r13; void *
0x180005ae8  call    ?OpenFileInStorageArea@@YAKPEAXKPEBG1PEAPEAX@Z; OpenFileInStorageArea(void *,ulong,ushort const *,ushort const *,void * *)
0x180005aed  test    eax, eax
0x180005aef  jnz     loc_18000601A
0x180005af5  lea     rdx, [rsp+0F8h+FileSizeHigh]; lpFileSizeHigh
0x180005afa  mov     rcx, [rsp+0F8h+hFile]; hFile
0x180005aff  call    cs:__imp_GetFileSize
0x180005b06  nop     dword ptr [rax+rax+00h]
0x180005b0b  mov     r12d, eax
0x180005b0e  cmp     eax, 0FFFFFFFFh
0x180005b11  jz      loc_180006098
0x180005b17  cmp     r12d, 80h
0x180005b1e  jb      loc_18000602C
0x180005b24  cmp     [rsp+0F8h+FileSizeHigh], ebx
0x180005b28  jnz     loc_18000602C
0x180005b2e  cmp     r12d, 3FFFCh
0x180005b35  ja      loc_18000602C
0x180005b3b  mov     [rsp+0F8h+lpName], rbx; lpName
0x180005b40  mov     [rsp+0F8h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x180005b44  xor     r9d, r9d; dwMaximumSizeHigh
0x180005b47  xor     edx, edx; lpFileMappingAttributes
0x180005b49  lea     r8d, [r9+2]; flProtect
0x180005b4d  mov     rcx, [rsp+0F8h+hFile]; hFile
0x180005b52  call    cs:__imp_CreateFileMappingW
0x180005b59  nop     dword ptr [rax+rax+00h]
0x180005b5e  mov     r13, rax
0x180005b61  mov     [rsp+0F8h+hObject], rax
0x180005b66  test    rax, rax
0x180005b69  jz      loc_180005DBD
0x180005b6f  mov     qword ptr [rsp+0F8h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x180005b74  xor     r9d, r9d; dwFileOffsetLow
0x180005b77  xor     r8d, r8d; dwFileOffsetHigh
0x180005b7a  lea     edx, [r9+4]; dwDesiredAccess
0x180005b7e  mov     rcx, rax; hFileMappingObject
0x180005b81  call    cs:__imp_MapViewOfFile
0x180005b88  nop     dword ptr [rax+rax+00h]
0x180005b8d  mov     rdi, rax
0x180005b90  mov     [rsp+0F8h+var_A0], rax
0x180005b95  test    rax, rax
0x180005b98  jz      loc_180005DF0
0x180005b9e  mov     r13d, [rax]
0x180005ba1  cmp     r13d, 2
0x180005ba5  ja      loc_180005C96
0x180005bab  mov     edx, 0FFFFh
0x180005bb0  cmp     [rax+60h], edx
0x180005bb3  ja      loc_180005F61
0x180005bb9  cmp     [rax+68h], edx
0x180005bbc  ja      loc_180005F61
0x180005bc2  mov     eax, [rax+70h]
0x180005bc5  cmp     eax, edx
0x180005bc7  ja      loc_180005F61
0x180005bcd  mov     ecx, [rdi+78h]
0x180005bd0  cmp     ecx, edx
0x180005bd2  ja      loc_180005F61
0x180005bd8  add     ecx, eax
0x180005bda  add     ecx, [rdi+68h]
0x180005bdd  add     ecx, [rdi+60h]
0x180005be0  lea     rax, [r12-80h]
0x180005be5  cmp     rcx, rax
0x180005be8  ja      loc_180005E43
0x180005bee  lea     rdx, [rdi+0Ch]; Buf2
0x180005bf2  movups  xmm0, xmmword ptr [rdx]
0x180005bf5  movaps  [rsp+0F8h+var_78], xmm0
0x180005bfd  movups  xmm1, xmmword ptr [rdx+10h]
0x180005c01  movaps  [rsp+0F8h+var_68], xmm1
0x180005c09  movups  xmm0, xmmword ptr [rdx+20h]
0x180005c0d  movaps  [rsp+0F8h+var_58], xmm0
0x180005c15  movups  xmm1, xmmword ptr [rdx+30h]
0x180005c19  movaps  [rsp+0F8h+var_48], xmm1
0x180005c21  movups  xmm0, xmmword ptr [rdx+40h]
0x180005c25  movaps  [rsp+0F8h+var_38], xmm0
0x180005c2d  mov     word ptr [rsp+0F8h+var_38+0Eh], bx
0x180005c35  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005c39  mov     rax, r8
0x180005c3c  lea     r12, [r15+10h]
0x180005c40  inc     rax
0x180005c43  cmp     [r12+rax*2], bx
0x180005c48  jnz     short loc_180005C40
0x180005c4a  lea     ecx, ds:2[rax*2]
0x180005c51  lea     r9, [rsp+0F8h+var_78]
0x180005c59  mov     rax, r8
0x180005c5c  inc     rax
0x180005c5f  cmp     [r9+rax*2], bx
0x180005c64  jnz     short loc_180005C5C
0x180005c66  lea     eax, ds:2[rax*2]
0x180005c6d  cmp     ecx, eax
0x180005c6f  jz      short loc_180005CBB
0x180005c71  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c78  lea     rax, WPP_GLOBAL_Control
0x180005c7f  cmp     rcx, rax
0x180005c82  jnz     loc_180005E7B
0x180005c88  mov     r13, [rsp+0F8h+hObject]
0x180005c8d  mov     esi, [rsp+0F8h+var_C8]
0x180005c91  jmp     loc_180005FA9
0x180005c96  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c9d  lea     rax, WPP_GLOBAL_Control
0x180005ca4  cmp     rcx, rax
0x180005ca7  jnz     loc_180005E23
0x180005cad  mov     r13, [rsp+0F8h+hObject]
0x180005cb2  mov     esi, [rsp+0F8h+var_C8]
0x180005cb6  jmp     loc_180005FA9
0x180005cbb  mov     r8d, ecx; Size
0x180005cbe  mov     rcx, r12; Buf1
0x180005cc1  call    memcmp_0
0x180005cc6  test    eax, eax
0x180005cc8  jnz     loc_180005E9E
0x180005cce  mov     [r15], r13d
0x180005cd1  mov     eax, [rdi+5Ch]
0x180005cd4  mov     [r15+60h], eax
0x180005cd8  lea     rsi, [rdi+80h]
0x180005cdf  mov     [rsp+0F8h+var_A8], rsi
0x180005ce4  cmp     [rdi+60h], ebx
0x180005ce7  jnz     short loc_180005D4A
0x180005ce9  cmp     [rdi+68h], ebx
0x180005cec  jnz     loc_180005D79
0x180005cf2  cmp     [rdi+70h], ebx
0x180005cf5  jz      short loc_180005D3C
0x180005cf7  mov     edx, [rdi+70h]; uBytes
0x180005cfa  xor     ecx, ecx; uFlags
0x180005cfc  call    cs:__imp_LocalAlloc
0x180005d03  nop     dword ptr [rax+rax+00h]
0x180005d08  mov     rcx, rax; void *
0x180005d0b  mov     [r15+88h], rax
0x180005d12  test    rax, rax
0x180005d15  jz      loc_180005F0D
0x180005d1b  mov     eax, [rdi+70h]
0x180005d1e  mov     [r15+80h], eax
0x180005d25  mov     r8d, [rdi+70h]; Size
0x180005d29  mov     rdx, rsi; Src
0x180005d2c  call    memcpy_0
0x180005d31  mov     eax, [rdi+70h]
0x180005d34  add     rsi, rax
0x180005d37  mov     [rsp+0F8h+var_A8], rsi
0x180005d3c  cmp     [rdi+78h], ebx
0x180005d3f  jnz     loc_180005F1B
0x180005d45  jmp     loc_180006065
0x180005d4a  mov     edx, [rdi+60h]; uBytes
0x180005d4d  xor     ecx, ecx; uFlags
0x180005d4f  call    cs:__imp_LocalAlloc
0x180005d56  nop     dword ptr [rax+rax+00h]
0x180005d5b  mov     rcx, rax; void *
0x180005d5e  mov     [r15+68h], rax
0x180005d62  test    rax, rax
0x180005d65  jnz     loc_180005ED9
0x180005d6b  mov     r13, [rsp+0F8h+hObject]
0x180005d70  mov     esi, [rsp+0F8h+var_C8]
0x180005d74  jmp     loc_180005FA9
0x180005d79  mov     edx, [rdi+68h]; uBytes
0x180005d7c  xor     ecx, ecx; uFlags
0x180005d7e  call    cs:__imp_LocalAlloc
0x180005d85  nop     dword ptr [rax+rax+00h]
0x180005d8a  mov     rcx, rax; void *
0x180005d8d  mov     [r15+78h], rax
0x180005d91  test    rax, rax
0x180005d94  jz      loc_180005EFF
0x180005d9a  mov     eax, [rdi+68h]
0x180005d9d  mov     [r15+70h], eax
0x180005da1  mov     r8d, [rdi+68h]; Size
0x180005da5  mov     rdx, rsi; Src
0x180005da8  call    memcpy_0
0x180005dad  mov     eax, [rdi+68h]
0x180005db0  add     rsi, rax
0x180005db3  mov     [rsp+0F8h+var_A8], rsi
0x180005db8  jmp     loc_180005CF2
0x180005dbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dc4  lea     rax, WPP_GLOBAL_Control
0x180005dcb  cmp     rcx, rax
0x180005dce  jz      short loc_180005DE7
0x180005dd0  test    [rcx+1Ch], r14b
0x180005dd4  jz      short loc_180005DE7
0x180005dd6  mov     edx, 7Fh
0x180005ddb  mov     r8, rsi
0x180005dde  mov     rcx, [rcx+10h]
0x180005de2  call    WPP_SF_
0x180005de7  mov     esi, [rsp+0F8h+var_C8]
0x180005deb  jmp     loc_180005FA9
0x180005df0  mov     rcx, cs:WPP_GLOBAL_Control
0x180005df7  lea     rax, WPP_GLOBAL_Control
0x180005dfe  cmp     rcx, rax
0x180005e01  jz      short loc_180005E1A
0x180005e03  test    [rcx+1Ch], r14b
0x180005e07  jz      short loc_180005E1A
0x180005e09  mov     edx, 80h
0x180005e0e  mov     r8, rsi
0x180005e11  mov     rcx, [rcx+10h]
0x180005e15  call    WPP_SF_
0x180005e1a  mov     esi, [rsp+0F8h+var_C8]
0x180005e1e  jmp     loc_180005FA9
0x180005e23  test    [rcx+1Ch], r14b
0x180005e27  jz      loc_180005CAD
0x180005e2d  mov     edx, 81h
0x180005e32  mov     r8, rsi
0x180005e35  mov     rcx, [rcx+10h]
0x180005e39  call    WPP_SF_
0x180005e3e  jmp     loc_180005CAD
0x180005e43  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e4a  lea     rax, WPP_GLOBAL_Control
0x180005e51  cmp     rcx, rax
0x180005e54  jz      short loc_180005E6D
0x180005e56  test    [rcx+1Ch], r14b
0x180005e5a  jz      short loc_180005E6D
0x180005e5c  mov     edx, 83h
0x180005e61  mov     r8, rsi
0x180005e64  mov     rcx, [rcx+10h]
0x180005e68  call    WPP_SF_
0x180005e6d  mov     r13, [rsp+0F8h+hObject]
0x180005e72  mov     esi, [rsp+0F8h+var_C8]
0x180005e76  jmp     loc_180005FA9
0x180005e7b  test    [rcx+1Ch], r14b
0x180005e7f  jz      loc_180005C88
0x180005e85  mov     edx, 84h
0x180005e8a  mov     r9, r12
0x180005e8d  mov     r8, rsi
0x180005e90  mov     rcx, [rcx+10h]
0x180005e94  call    WPP_SF_S
0x180005e99  jmp     loc_180005C88
0x180005e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ea5  lea     rax, WPP_GLOBAL_Control
0x180005eac  cmp     rcx, rax
0x180005eaf  jz      short loc_180005ECB
0x180005eb1  test    [rcx+1Ch], r14b
0x180005eb5  jz      short loc_180005ECB
0x180005eb7  mov     edx, 85h
0x180005ebc  mov     r9, r12
0x180005ebf  mov     r8, rsi
0x180005ec2  mov     rcx, [rcx+10h]
0x180005ec6  call    WPP_SF_S
0x180005ecb  mov     r13, [rsp+0F8h+hObject]
0x180005ed0  mov     esi, [rsp+0F8h+var_C8]
0x180005ed4  jmp     loc_180005FA9
0x180005ed9  mov     eax, [rdi+60h]
0x180005edc  mov     [r15+64h], eax
0x180005ee0  mov     r8d, [rdi+60h]; Size
0x180005ee4  mov     rdx, rsi; Src
0x180005ee7  call    memcpy_0
0x180005eec  mov     eax, [rdi+60h]
0x180005eef  add     rax, rsi
0x180005ef2  mov     rsi, rax
0x180005ef5  mov     [rsp+0F8h+var_A8], rax
0x180005efa  jmp     loc_180005CE9
0x180005eff  mov     r13, [rsp+0F8h+hObject]
0x180005f04  mov     esi, [rsp+0F8h+var_C8]
0x180005f08  jmp     loc_180005FA9
0x180005f0d  mov     r13, [rsp+0F8h+hObject]
0x180005f12  mov     esi, [rsp+0F8h+var_C8]
0x180005f16  jmp     loc_180005FA9
0x180005f1b  mov     edx, [rdi+78h]; uBytes
0x180005f1e  xor     ecx, ecx; uFlags
0x180005f20  call    cs:__imp_LocalAlloc
0x180005f27  nop     dword ptr [rax+rax+00h]
0x180005f2c  mov     rcx, rax; void *
0x180005f2f  mov     [r15+98h], rax
0x180005f36  test    rax, rax
0x180005f39  jnz     short loc_180005F46
0x180005f3b  mov     r13, [rsp+0F8h+hObject]
0x180005f40  mov     esi, [rsp+0F8h+var_C8]
0x180005f44  jmp     short loc_180005FA9
  ... truncated ...
```
