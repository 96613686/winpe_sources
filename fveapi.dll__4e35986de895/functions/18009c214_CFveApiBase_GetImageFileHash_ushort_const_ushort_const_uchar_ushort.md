# CFveApiBase::GetImageFileHash(ushort const *,ushort const *,uchar *,ushort)

- ea: `0x18009c214`
- end: `0x18009c54a`
- name: `?GetImageFileHash@CFveApiBase@@SAJPEBG0PEAEG@Z`
- size: `822`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, unsigned __int16)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180087aa4`
- `0x180088e6c`
- `0x18009bc80`

## callees

- `0x180005410`
- `0x1800090c0`
- `0x180018b10`
- `0x18009c214`
- `0x1800eae04`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c51a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009c51a`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18009c2ca`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18009c2ca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009c27d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009c27d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18009c35e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18009c35e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18009c3b4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18009c3b4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18009c4f1`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18009c4f1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009c418`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009c418`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009c4dd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009c4dd`

## pseudocode

```c
__int64 __fastcall CFveApiBase::GetImageFileHash(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned __int16 a4)
{
  void *v4; // rsi
  size_t v5; // rdi
  UCHAR *v8; // r15
  HANDLE FileW; // rax
  void *v10; // r14
  unsigned int LastHresultError; // eax
  int v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  HANDLE FileMappingW; // rax
  NTSTATUS v17; // eax
  unsigned int v18; // eax
  int v19; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  union _LARGE_INTEGER FileSize; // [rsp+70h] [rbp-90h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+78h] [rbp-88h] BYREF
  int v25[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v26; // [rsp+88h] [rbp-78h]
  int v27; // [rsp+290h] [rbp+190h]

  v4 = 0;
  v5 = a4;
  phAlgorithm = 0;
  FileSize.QuadPart = 0;
  v8 = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  v10 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastHresultError = GetLastHresultError();
    v12 = LastHresultError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v14 = 10;
LABEL_30:
      v15 = LastHresultError;
      goto LABEL_31;
    }
  }
  else if ( GetFileSizeEx(FileW, &FileSize) )
  {
    if ( FileSize.HighPart )
    {
      v12 = -2147024673;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v14 = 12;
        v15 = 2147942623LL;
LABEL_31:
        WPP_SF_d(v13[2], v14, &WPP_1559182127783aab3882fe828952d989_Traceguids, v15);
      }
    }
    else
    {
      FileMappingW = CreateFileMappingW(v10, 0, 2u, 0, FileSize.LowPart, 0);
      v4 = FileMappingW;
      if ( FileMappingW )
      {
        v8 = (UCHAR *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
        if ( v8 )
        {
          memset_0(a3, 0, v5);
          v17 = BCryptOpenAlgorithmProvider(&phAlgorithm, a2, L"Microsoft Primitive Provider", 0);
          v18 = FromNtStatus(v17);
          v12 = v18;
          if ( !v18 )
            goto LABEL_28;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_1559182127783aab3882fe828952d989_Traceguids, v18);
          if ( v12 >= 0 )
          {
LABEL_28:
            *(_QWORD *)v25 = phAlgorithm;
            v26 = 0;
            v27 = 0;
            v19 = I_HashComputeImageHashEx<BCRYPT_HASH_CTXT,std::nullptr_t>(
                    (struct BCRYPT_HASH_CTXT *)v25,
                    v8,
                    FileSize.LowPart,
                    FileSize.LowPart,
                    dwCreationDisposition,
                    dwFlagsAndAttributes,
                    a3);
            LastHresultError = FromNtStatus(v19);
            v12 = LastHresultError;
            if ( LastHresultError )
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              {
                v14 = 16;
                goto LABEL_30;
              }
            }
          }
        }
        else
        {
          LastHresultError = GetLastHresultError();
          v12 = LastHresultError;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            v14 = 14;
            goto LABEL_30;
          }
        }
      }
      else
      {
        LastHresultError = GetLastHresultError();
        v12 = LastHresultError;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v14 = 13;
          goto LABEL_30;
        }
      }
    }
  }
  else
  {
    LastHresultError = GetLastHresultError();
    v12 = LastHresultError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v14 = 11;
      goto LABEL_30;
    }
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v8 )
    UnmapViewOfFile(v8);
  if ( v4 )
    CloseHandle(v4);
  if ( v10 != (void *)-1LL )
    CloseHandle(v10);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18009c214  push    rbp
0x18009c216  push    rbx
0x18009c217  push    rsi
0x18009c218  push    rdi
0x18009c219  push    r12
0x18009c21b  push    r14
0x18009c21d  push    r15
0x18009c21f  lea     rbp, [rsp-1B0h]
0x18009c227  sub     rsp, 2B0h
0x18009c22e  mov     rax, cs:__security_cookie
0x18009c235  xor     rax, rsp
0x18009c238  mov     [rbp+1E0h+var_40], rax
0x18009c23f  xor     esi, esi
0x18009c241  movzx   edi, r9w
0x18009c245  mov     r12, r8
0x18009c248  mov     [rsp+2E0h+hTemplateFile], rsi; hTemplateFile
0x18009c24d  mov     rbx, rdx
0x18009c250  mov     [rsp+2E0h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18009c254  xor     r9d, r9d; lpSecurityAttributes
0x18009c257  mov     [rsp+2E0h+phAlgorithm], 0
0x18009c260  lea     r8d, [rsi+1]; dwShareMode
0x18009c264  mov     qword ptr [rsp+2E0h+FileSize], 0
0x18009c26d  mov     edx, 80000000h; dwDesiredAccess
0x18009c272  mov     [rsp+2E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18009c27a  xor     r15d, r15d
0x18009c27d  call    cs:__imp_CreateFileW
0x18009c284  nop     dword ptr [rax+rax+00h]
0x18009c289  mov     r14, rax
0x18009c28c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009c290  jnz     short loc_18009C2C2
0x18009c292  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18009c297  mov     ebx, eax
0x18009c299  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c2a0  lea     rdi, WPP_GLOBAL_Control
0x18009c2a7  cmp     rcx, rdi
0x18009c2aa  jz      loc_18009C4D1
0x18009c2b0  test    byte ptr [rcx+1Ch], 40h
0x18009c2b4  jz      loc_18009C4D1
0x18009c2ba  lea     edx, [rsi+0Ah]
0x18009c2bd  jmp     loc_18009C4BE
0x18009c2c2  lea     rdx, [rsp+2E0h+FileSize]; lpFileSize
0x18009c2c7  mov     rcx, r14; hFile
0x18009c2ca  call    cs:__imp_GetFileSizeEx
0x18009c2d1  nop     dword ptr [rax+rax+00h]
0x18009c2d6  test    eax, eax
0x18009c2d8  jnz     short loc_18009C30C
0x18009c2da  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18009c2df  mov     ebx, eax
0x18009c2e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c2e8  lea     rdi, WPP_GLOBAL_Control
0x18009c2ef  cmp     rcx, rdi
0x18009c2f2  jz      loc_18009C4D1
0x18009c2f8  test    byte ptr [rcx+1Ch], 40h
0x18009c2fc  jz      loc_18009C4D1
0x18009c302  mov     edx, 0Bh
0x18009c307  jmp     loc_18009C4BE
0x18009c30c  cmp     dword ptr [rsp+2E0h+FileSize+4], esi
0x18009c310  jz      short loc_18009C345
0x18009c312  mov     ebx, 800700DFh
0x18009c317  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c31e  lea     rdi, WPP_GLOBAL_Control
0x18009c325  cmp     rcx, rdi
0x18009c328  jz      loc_18009C4D1
0x18009c32e  test    byte ptr [rcx+1Ch], 40h
0x18009c332  jz      loc_18009C4D1
0x18009c338  mov     edx, 0Ch
0x18009c33d  mov     r9d, ebx
0x18009c340  jmp     loc_18009C4C1
0x18009c345  mov     eax, dword ptr [rsp+2E0h+FileSize]
0x18009c349  xor     r9d, r9d; dwMaximumSizeHigh
0x18009c34c  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rsi; int
0x18009c351  xor     edx, edx; lpFileMappingAttributes
0x18009c353  mov     rcx, r14; hFile
0x18009c356  mov     [rsp+2E0h+dwCreationDisposition], eax; dwMaximumSizeLow
0x18009c35a  lea     r8d, [r9+2]; flProtect
0x18009c35e  call    cs:__imp_CreateFileMappingW
0x18009c365  nop     dword ptr [rax+rax+00h]
0x18009c36a  mov     rsi, rax
0x18009c36d  test    rax, rax
0x18009c370  jnz     short loc_18009C3A2
0x18009c372  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18009c377  mov     ebx, eax
0x18009c379  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c380  lea     rdi, WPP_GLOBAL_Control
0x18009c387  cmp     rcx, rdi
0x18009c38a  jz      loc_18009C4D1
0x18009c390  test    byte ptr [rcx+1Ch], 40h
0x18009c394  jz      loc_18009C4D1
0x18009c39a  lea     edx, [rsi+0Dh]
0x18009c39d  jmp     loc_18009C4BE
0x18009c3a2  xor     r9d, r9d; dwFileOffsetLow
0x18009c3a5  mov     qword ptr [rsp+2E0h+dwCreationDisposition], r15; int
0x18009c3aa  xor     r8d, r8d; dwFileOffsetHigh
0x18009c3ad  mov     rcx, rax; hFileMappingObject
0x18009c3b0  lea     edx, [r9+4]; dwDesiredAccess
0x18009c3b4  call    cs:__imp_MapViewOfFile
0x18009c3bb  nop     dword ptr [rax+rax+00h]
0x18009c3c0  mov     r15, rax
0x18009c3c3  test    rax, rax
0x18009c3c6  jnz     short loc_18009C3F9
0x18009c3c8  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18009c3cd  mov     ebx, eax
0x18009c3cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c3d6  lea     rdi, WPP_GLOBAL_Control
0x18009c3dd  cmp     rcx, rdi
0x18009c3e0  jz      loc_18009C4D1
0x18009c3e6  test    byte ptr [rcx+1Ch], 40h
0x18009c3ea  jz      loc_18009C4D1
0x18009c3f0  lea     edx, [r15+0Eh]
0x18009c3f4  jmp     loc_18009C4BE
0x18009c3f9  mov     r8, rdi; Size
0x18009c3fc  xor     edx, edx; Val
0x18009c3fe  mov     rcx, r12; void *
0x18009c401  call    memset_0
0x18009c406  xor     r9d, r9d; dwFlags
0x18009c409  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18009c410  mov     rdx, rbx; pszAlgId
0x18009c413  lea     rcx, [rsp+2E0h+phAlgorithm]; phAlgorithm
0x18009c418  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18009c41f  nop     dword ptr [rax+rax+00h]
0x18009c424  mov     ecx, eax; int
0x18009c426  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009c42b  lea     rdi, WPP_GLOBAL_Control
0x18009c432  mov     ebx, eax
0x18009c434  test    eax, eax
0x18009c436  jz      short loc_18009C466
0x18009c438  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c43f  cmp     rcx, rdi
0x18009c442  jz      short loc_18009C462
0x18009c444  test    byte ptr [rcx+1Ch], 40h
0x18009c448  jz      short loc_18009C462
0x18009c44a  mov     rcx, [rcx+10h]
0x18009c44e  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009c455  mov     edx, 0Fh
0x18009c45a  mov     r9d, eax
0x18009c45d  call    WPP_SF_d
0x18009c462  test    ebx, ebx
0x18009c464  js      short loc_18009C4D1
0x18009c466  mov     r8d, dword ptr [rsp+2E0h+FileSize]; cbInput
0x18009c46b  lea     rcx, [rbp+1E0h+var_260]; int
0x18009c46f  mov     rax, [rsp+2E0h+phAlgorithm]
0x18009c474  mov     r9d, r8d; unsigned int
0x18009c477  mov     rdx, r15; pbInput
0x18009c47a  mov     qword ptr [rbp+1E0h+var_260], rax
0x18009c47e  mov     [rbp+1E0h+var_258], 0
0x18009c486  mov     [rbp+1E0h+var_50], 0
0x18009c490  mov     [rsp+2E0h+hTemplateFile], r12; unsigned __int8 *
0x18009c495  call    ??$I_HashComputeImageHashEx@UBCRYPT_HASH_CTXT@@$$T@@YAJPEAUBCRYPT_HASH_CTXT@@PEBXKKP6AJPEAXKPEAKPEAPEAX3@Z2PEAE3PEAUHASHLIB_CERT_INFO@@6$$T6K@Z; I_HashComputeImageHashEx<BCRYPT_HASH_CTXT,std::nullptr_t>(BCRYPT_HASH_CTXT *,void const *,ulong,ulong,long (*)(void *,ulong,ulong *,void * *,ulong *),void *,uchar *,ulong *,HASHLIB_CERT_INFO *,uchar *,std::nullptr_t,uchar *,ulong)
0x18009c49a  mov     ecx, eax; int
0x18009c49c  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009c4a1  mov     ebx, eax
0x18009c4a3  test    eax, eax
0x18009c4a5  jz      short loc_18009C4D1
0x18009c4a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18009c4ae  cmp     rcx, rdi
0x18009c4b1  jz      short loc_18009C4D1
0x18009c4b3  test    byte ptr [rcx+1Ch], 40h
0x18009c4b7  jz      short loc_18009C4D1
0x18009c4b9  mov     edx, 10h
0x18009c4be  mov     r9d, eax
0x18009c4c1  mov     rcx, [rcx+10h]
0x18009c4c5  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009c4cc  call    WPP_SF_d
0x18009c4d1  mov     rcx, [rsp+2E0h+phAlgorithm]; hAlgorithm
0x18009c4d6  test    rcx, rcx
0x18009c4d9  jz      short loc_18009C4E9
0x18009c4db  xor     edx, edx; dwFlags
0x18009c4dd  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18009c4e4  nop     dword ptr [rax+rax+00h]
0x18009c4e9  test    r15, r15
0x18009c4ec  jz      short loc_18009C4FD
0x18009c4ee  mov     rcx, r15; lpBaseAddress
0x18009c4f1  call    cs:__imp_UnmapViewOfFile
0x18009c4f8  nop     dword ptr [rax+rax+00h]
0x18009c4fd  test    rsi, rsi
0x18009c500  jz      short loc_18009C511
0x18009c502  mov     rcx, rsi; hObject
0x18009c505  call    cs:__imp_CloseHandle
0x18009c50c  nop     dword ptr [rax+rax+00h]
0x18009c511  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18009c515  jz      short loc_18009C526
0x18009c517  mov     rcx, r14; hObject
0x18009c51a  call    cs:__imp_CloseHandle
0x18009c521  nop     dword ptr [rax+rax+00h]
0x18009c526  mov     eax, ebx
0x18009c528  mov     rcx, [rbp+1E0h+var_40]
0x18009c52f  xor     rcx, rsp; StackCookie
0x18009c532  call    __security_check_cookie
0x18009c537  add     rsp, 2B0h
0x18009c53e  pop     r15
0x18009c540  pop     r14
0x18009c542  pop     r12
0x18009c544  pop     rdi
0x18009c545  pop     rsi
0x18009c546  pop     rbx
0x18009c547  pop     rbp
0x18009c548  retn
```
