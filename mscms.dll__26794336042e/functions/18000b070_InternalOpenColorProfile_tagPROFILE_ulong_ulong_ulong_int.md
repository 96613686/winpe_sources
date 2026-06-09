# InternalOpenColorProfile(tagPROFILE *,ulong,ulong,ulong,int *)

- ea: `0x18000b070`
- end: `0x18000b488`
- name: `?InternalOpenColorProfile@@YAPEAXPEAUtagPROFILE@@KKKPEAH@Z`
- size: `1048`
- prototype: `void *__fastcall(struct tagPROFILE *, int, DWORD, DWORD, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000a780`

## callees

- `0x180008bf0`
- `0x180009810`
- `0x18000b070`
- `0x18000b828`
- `0x18000bbfc`
- `0x18000be44`
- `0x18000c310`
- `0x180029f14`
- `0x18002f2dc`
- `0x18002f2f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b439`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b446`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b468`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b439`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b446`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b468`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b2a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b2a3`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000b2bc`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000b2bc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000b24c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000b24c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000b316`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000b316`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000b348`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000b348`

## pseudocode

```c
void *__fastcall InternalOpenColorProfile(struct tagPROFILE *a1, int a2, DWORD a3, DWORD a4, int *a5)
{
  DWORD *p_cbDataSize; // rsi
  int v9; // ebp
  __int64 v10; // rax
  __int64 v11; // rbx
  void *v12; // r14
  unsigned int v13; // r15d
  void *v14; // rax
  int v15; // r15d
  const WCHAR *v16; // rcx
  unsigned __int64 v17; // rax
  __int64 FilenameFromPath; // rax
  WCHAR *v19; // rdi
  WCHAR *v20; // rax
  DWORD v21; // ecx
  DWORD v22; // edx
  HANDLE v23; // rax
  DWORD FileSize; // esi
  DWORD v25; // r8d
  HANDLE FileMappingW; // rax
  DWORD v27; // edx
  _DWORD *v28; // rax
  __int64 v29; // rdi
  void *v30; // rcx
  _DWORD *v31; // rax
  int v32; // r10d
  DWORD v34; // ecx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-58h] BYREF
  DWORD pdwSize; // [rsp+A0h] [rbp+8h] BYREF
  DWORD dwShareMode; // [rsp+B0h] [rbp+18h]

  dwShareMode = a3;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( a1
    && ((p_cbDataSize = &a1->cbDataSize, a1->pProfileData) || !*p_cbDataSize)
    && (v9 = 1, a1->dwType - 1 <= 1)
    && (unsigned int)(a2 - 1) <= 1 )
  {
    v10 = MemAlloc(72);
    v11 = v10;
    if ( v10 )
    {
      *(_DWORD *)v10 = 1347569228;
      v12 = (void *)(v10 ^ 0x49434D20);
      if ( v10 != 0x49434D20 )
      {
        v13 = (*p_cbDataSize & 1) + 2;
        if ( ~v13 >= *p_cbDataSize )
        {
          *(_DWORD *)(v10 + 4) = 1;
          *(_DWORD *)(v10 + 8) = a1->dwType;
          *(_DWORD *)(v10 + 24) = *p_cbDataSize;
          v14 = (void *)MemAlloc(v13 + *p_cbDataSize);
          *(_QWORD *)(v11 + 16) = v14;
          if ( !v14 )
          {
LABEL_19:
            v21 = 8;
LABEL_56:
            SetLastError(v21);
LABEL_57:
            FreeProfileObject(v12);
            return 0;
          }
          memcpy_0(v14, a1->pProfileData, *p_cbDataSize);
          memset_0((void *)(*(_QWORD *)(v11 + 16) + *(unsigned int *)(v11 + 24)), 0, v13);
          if ( *(_DWORD *)(v11 + 8) != 1 )
          {
            v29 = v11 + 56;
            if ( *p_cbDataSize )
            {
              *(_QWORD *)v29 = *(_QWORD *)(v11 + 16);
            }
            else
            {
              v30 = *(void **)(v11 + 16);
              *(_DWORD *)(v11 + 24) = 0x4000;
              MemFree(v30);
              v31 = (_DWORD *)MemAlloc(*(unsigned int *)(v11 + 24));
              *(_QWORD *)(v11 + 16) = v31;
              *(_QWORD *)v29 = v31;
              if ( !v31 )
                goto LABEL_19;
              *v31 = -2080374784;
              *(_DWORD *)(*(_QWORD *)v29 + 8LL) = 0x2000000;
              *(_DWORD *)(*(_QWORD *)v29 + 36LL) = 1886610273;
              *(_DWORD *)(*(_QWORD *)v29 + 128LL) = 0;
            }
            *(_DWORD *)(v11 + 48) = *(_DWORD *)(v11 + 24);
            goto LABEL_49;
          }
          v15 = 0;
          if ( a1->pProfileData )
          {
            if ( *p_cbDataSize )
            {
              v16 = *(const WCHAR **)(v11 + 16);
              v17 = -1;
              do
                ++v17;
              while ( v16[v17] );
              if ( v17 <= 0x104 && *p_cbDataSize <= 0x208 )
              {
                FilenameFromPath = GetFilenameFromPath(v16);
                v19 = *(WCHAR **)(v11 + 16);
                if ( (WCHAR *)FilenameFromPath == v19 )
                {
                  pdwSize = 520;
                  v20 = (WCHAR *)MemAlloc(520);
                  v19 = v20;
                  if ( !v20 )
                    goto LABEL_19;
                  GetColorDirectoryW(0, v20, &pdwSize);
                  if ( (int)StringCchCatW(v19, 0x104u, gszBackslash) < 0
                    || (int)StringCchCatW(v19, 0x104u, *(const unsigned __int16 **)(v11 + 16)) < 0 )
                  {
                    MemFree(v19);
                    v21 = 122;
                    goto LABEL_56;
                  }
                  MemFree(*(LPVOID *)(v11 + 16));
                  *(_QWORD *)(v11 + 16) = v19;
                  *(_DWORD *)(v11 + 24) = 520;
                }
                *(_DWORD *)(v11 + 28) |= 1u;
                if ( a4 == 4 && GetFileAttributesW(v19) != -1 )
                  a4 = 3;
                v22 = -1073741824;
                SecurityAttributes.nLength = 24;
                SecurityAttributes.lpSecurityDescriptor = 0;
                SecurityAttributes.bInheritHandle = 0;
                if ( a2 != 2 )
                  v22 = 0x80000000;
                v23 = CreateFileW(*(LPCWSTR *)(v11 + 16), v22, dwShareMode, &SecurityAttributes, a4, 0x10000000u, 0);
                *(_QWORD *)(v11 + 32) = v23;
                if ( v23 == (HANDLE)-1LL )
                  goto LABEL_57;
                FileSize = GetFileSize(v23, 0);
                if ( !FileSize )
                {
                  if ( a4 == 3 )
                  {
                    v21 = 2011;
                    goto LABEL_56;
                  }
                  FileSize = 0x4000;
                  v15 = 1;
                }
                v25 = 4;
                if ( a2 != 2 )
                  v25 = 2;
                FileMappingW = CreateFileMappingW(*(HANDLE *)(v11 + 32), 0, v25, 0, FileSize, 0);
                *(_QWORD *)(v11 + 40) = FileMappingW;
                if ( !FileMappingW )
                  goto LABEL_57;
                v27 = 983071;
                *(_DWORD *)(v11 + 48) = FileSize;
                if ( a2 != 2 )
                  v27 = 4;
                v28 = MapViewOfFile(FileMappingW, v27, 0, 0, 0);
                v29 = v11 + 56;
                *(_QWORD *)(v11 + 56) = v28;
                if ( !v28 )
                  goto LABEL_57;
                if ( v15 )
                {
                  if ( a2 != 2 )
                  {
LABEL_51:
                    if ( !(unsigned int)ValidProfile(v11) || *(_DWORD *)(*(_QWORD *)v29 + 36LL) != 1886610273 )
                      v9 = v32;
                    *a5 = v9;
                    SetLastError(0);
                    return v12;
                  }
                  *v28 = -2080374784;
                  *(_DWORD *)(*(_QWORD *)v29 + 8LL) = 0x2000000;
                  *(_DWORD *)(*(_QWORD *)v29 + 36LL) = 1886610273;
                  *(_DWORD *)(*(_QWORD *)v29 + 128LL) = 0;
                }
LABEL_49:
                if ( a2 == 2 )
                  *(_DWORD *)(v11 + 28) |= 4u;
                goto LABEL_51;
              }
            }
          }
        }
        v21 = 87;
        goto LABEL_56;
      }
    }
    v34 = 8;
  }
  else
  {
    v34 = 87;
  }
  SetLastError(v34);
  return 0;
}

```

## disassembly

```asm
0x18000b070  mov     [rsp+arg_8], rbx
0x18000b075  mov     [rsp+dwShareMode], r8d
0x18000b07a  push    rbp
0x18000b07b  push    rsi
0x18000b07c  push    rdi
0x18000b07d  push    r12
0x18000b07f  push    r13
0x18000b081  push    r14
0x18000b083  push    r15
0x18000b085  sub     rsp, 60h
0x18000b089  xor     eax, eax
0x18000b08b  xor     r14d, r14d
0x18000b08e  mov     qword ptr [rsp+98h+SecurityAttributes.bInheritHandle], rax
0x18000b093  xorps   xmm0, xmm0
0x18000b096  mov     r12d, r9d
0x18000b099  mov     r13d, edx
0x18000b09c  mov     rdi, rcx
0x18000b09f  movups  xmmword ptr [rsp+98h+SecurityAttributes.nLength], xmm0
0x18000b0a4  test    rcx, rcx
0x18000b0a7  jz      loc_18000B463
0x18000b0ad  lea     rsi, [rcx+10h]
0x18000b0b1  cmp     [rcx+8], r14
0x18000b0b5  jnz     short loc_18000B0C0
0x18000b0b7  cmp     [rsi], r14d
0x18000b0ba  jnz     loc_18000B463
0x18000b0c0  mov     eax, [rcx]
0x18000b0c2  mov     ebp, 1
0x18000b0c7  sub     eax, ebp
0x18000b0c9  cmp     eax, ebp
0x18000b0cb  ja      loc_18000B463
0x18000b0d1  lea     eax, [rdx-1]
0x18000b0d4  cmp     eax, ebp
0x18000b0d6  ja      loc_18000B463
0x18000b0dc  lea     ecx, [rbp+47h]
0x18000b0df  call    MemAlloc
0x18000b0e4  mov     rbx, rax
0x18000b0e7  test    rax, rax
0x18000b0ea  jz      loc_18000B45C
0x18000b0f0  mov     r14, rax
0x18000b0f3  mov     dword ptr [rax], 5052464Ch
0x18000b0f9  xor     r14, 49434D20h
0x18000b100  jz      loc_18000B45C
0x18000b106  mov     r15d, [rsi]
0x18000b109  and     r15d, ebp
0x18000b10c  add     r15d, 2
0x18000b110  mov     ecx, r15d
0x18000b113  not     ecx
0x18000b115  cmp     ecx, [rsi]
0x18000b117  jb      loc_18000B441
0x18000b11d  mov     [rax+4], ebp
0x18000b120  mov     eax, [rdi]
0x18000b122  mov     [rbx+8], eax
0x18000b125  mov     eax, [rsi]
0x18000b127  mov     [rbx+18h], eax
0x18000b12a  mov     ecx, [rsi]
0x18000b12c  add     ecx, r15d
0x18000b12f  call    MemAlloc
0x18000b134  mov     [rbx+10h], rax
0x18000b138  test    rax, rax
0x18000b13b  jz      loc_18000B1DA
0x18000b141  mov     r8d, [rsi]; Size
0x18000b144  mov     rcx, rax; void *
0x18000b147  mov     rdx, [rdi+8]; Src
0x18000b14b  call    memcpy_0
0x18000b150  mov     ecx, [rbx+18h]
0x18000b153  xor     edx, edx; Val
0x18000b155  add     rcx, [rbx+10h]; void *
0x18000b159  mov     r8d, r15d; Size
0x18000b15c  call    memset_0
0x18000b161  lea     ecx, [rbp+3]
0x18000b164  lea     r15d, [rbp+1]
0x18000b168  cmp     [rbx+8], ebp
0x18000b16b  jnz     loc_18000B39D
0x18000b171  xor     r15d, r15d
0x18000b174  cmp     [rdi+8], r15
0x18000b178  jz      loc_18000B441
0x18000b17e  cmp     [rsi], r15d
0x18000b181  jz      loc_18000B441
0x18000b187  mov     rcx, [rbx+10h]; lpStringSource
0x18000b18b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b18f  inc     rax
0x18000b192  cmp     [rcx+rax*2], r15w
0x18000b197  jnz     short loc_18000B18F
0x18000b199  cmp     rax, 104h
0x18000b19f  ja      loc_18000B441
0x18000b1a5  cmp     dword ptr [rsi], 208h
0x18000b1ab  ja      loc_18000B441
0x18000b1b1  call    GetFilenameFromPath
0x18000b1b6  mov     rdi, [rbx+10h]
0x18000b1ba  cmp     rax, rdi
0x18000b1bd  jnz     short loc_18000B23B
0x18000b1bf  mov     esi, 208h
0x18000b1c4  mov     ecx, esi
0x18000b1c6  mov     [rsp+98h+pdwSize], esi
0x18000b1cd  call    MemAlloc
0x18000b1d2  mov     rdi, rax
0x18000b1d5  test    rax, rax
0x18000b1d8  jnz     short loc_18000B1E4
0x18000b1da  mov     ecx, 8
0x18000b1df  jmp     loc_18000B446
0x18000b1e4  lea     r8, [rsp+98h+pdwSize]; pdwSize
0x18000b1ec  mov     rdx, rdi; pBuffer
0x18000b1ef  xor     ecx, ecx; pMachineName
0x18000b1f1  call    GetColorDirectoryW
0x18000b1f6  lea     r8, gszBackslash; "\\"
0x18000b1fd  mov     edx, 104h; unsigned __int64
0x18000b202  mov     rcx, rdi; unsigned __int16 *
0x18000b205  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b20a  test    eax, eax
0x18000b20c  js      loc_18000B2DA
0x18000b212  mov     r8, [rbx+10h]; unsigned __int16 *
0x18000b216  mov     edx, 104h; unsigned __int64
0x18000b21b  mov     rcx, rdi; unsigned __int16 *
0x18000b21e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b223  test    eax, eax
0x18000b225  js      loc_18000B2DA
0x18000b22b  mov     rcx, [rbx+10h]; lpMem
0x18000b22f  call    MemFree
0x18000b234  mov     [rbx+10h], rdi
0x18000b238  mov     [rbx+18h], esi
0x18000b23b  or      [rbx+1Ch], ebp
0x18000b23e  mov     esi, 3
0x18000b243  cmp     r12d, 4
0x18000b247  jnz     short loc_18000B259
0x18000b249  mov     rcx, rdi; lpFileName
0x18000b24c  call    cs:__imp_GetFileAttributesW
0x18000b252  cmp     eax, 0FFFFFFFFh
0x18000b255  cmovnz  r12d, esi
0x18000b259  mov     r8d, [rsp+98h+dwShareMode]; dwShareMode
0x18000b261  lea     r9, [rsp+98h+SecurityAttributes]; lpSecurityAttributes
0x18000b266  mov     edx, 0C0000000h
0x18000b26b  mov     [rsp+98h+SecurityAttributes.nLength], 18h
0x18000b273  mov     eax, 80000000h
0x18000b278  mov     [rsp+98h+SecurityAttributes.lpSecurityDescriptor], r15
0x18000b27d  mov     [rsp+98h+SecurityAttributes.bInheritHandle], r15d
0x18000b282  mov     edi, 2
0x18000b287  mov     rcx, [rbx+10h]; lpFileName
0x18000b28b  cmp     r13d, edi
0x18000b28e  mov     [rsp+98h+hTemplateFile], r15; hTemplateFile
0x18000b293  cmovnz  edx, eax; dwDesiredAccess
0x18000b296  mov     [rsp+98h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x18000b29e  mov     [rsp+98h+dwCreationDisposition], r12d; dwCreationDisposition
0x18000b2a3  call    cs:__imp_CreateFileW
0x18000b2a9  mov     [rbx+20h], rax
0x18000b2ad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b2b1  jz      loc_18000B44C
0x18000b2b7  xor     edx, edx; lpFileSizeHigh
0x18000b2b9  mov     rcx, rax; hFile
0x18000b2bc  call    cs:__imp_GetFileSize
0x18000b2c2  mov     esi, eax
0x18000b2c4  xor     eax, eax
0x18000b2c6  test    esi, esi
0x18000b2c8  jnz     short loc_18000B2F4
0x18000b2ca  cmp     r12d, 3
0x18000b2ce  jnz     short loc_18000B2EC
0x18000b2d0  mov     ecx, 7DBh
0x18000b2d5  jmp     loc_18000B446
0x18000b2da  mov     rcx, rdi; lpMem
0x18000b2dd  call    MemFree
0x18000b2e2  mov     ecx, 7Ah ; 'z'
0x18000b2e7  jmp     loc_18000B446
0x18000b2ec  mov     esi, 4000h
0x18000b2f1  mov     r15d, ebp
0x18000b2f4  mov     rcx, [rbx+20h]; hFile
0x18000b2f8  mov     r12d, 4
0x18000b2fe  mov     r8d, r12d
0x18000b301  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rax; lpName
0x18000b306  cmp     r13d, edi
0x18000b309  mov     [rsp+98h+dwCreationDisposition], esi; dwMaximumSizeLow
0x18000b30d  cmovnz  r8d, edi; flProtect
0x18000b311  xor     r9d, r9d; dwMaximumSizeHigh
0x18000b314  xor     edx, edx; lpFileMappingAttributes
0x18000b316  call    cs:__imp_CreateFileMappingW
0x18000b31c  xor     ecx, ecx
0x18000b31e  mov     [rbx+28h], rax
0x18000b322  test    rax, rax
0x18000b325  jz      loc_18000B44C
0x18000b32b  mov     edx, 0F001Fh
0x18000b330  mov     qword ptr [rsp+98h+dwCreationDisposition], rcx; dwNumberOfBytesToMap
0x18000b335  cmp     r13d, edi
0x18000b338  mov     [rbx+30h], esi
0x18000b33b  mov     rcx, rax; hFileMappingObject
0x18000b33e  cmovnz  edx, r12d; dwDesiredAccess
0x18000b342  xor     r9d, r9d; dwFileOffsetLow
0x18000b345  xor     r8d, r8d; dwFileOffsetHigh
0x18000b348  call    cs:__imp_MapViewOfFile
0x18000b34e  xor     r10d, r10d
0x18000b351  lea     rdi, [rbx+38h]
0x18000b355  mov     [rdi], rax
0x18000b358  test    rax, rax
0x18000b35b  jz      loc_18000B44C
0x18000b361  test    r15d, r15d
0x18000b364  lea     r15d, [r12-2]
0x18000b369  jz      short loc_18000B398
0x18000b36b  cmp     r13d, r15d
0x18000b36e  jnz     loc_18000B412
0x18000b374  mov     dword ptr [rax], 84000000h
0x18000b37a  mov     rax, [rdi]
0x18000b37d  mov     dword ptr [rax+8], 2000000h
0x18000b384  mov     rax, [rdi]
0x18000b387  mov     dword ptr [rax+24h], 70736361h
0x18000b38e  mov     rax, [rdi]
0x18000b391  mov     [rax+80h], r10d
0x18000b398  mov     ecx, r12d
0x18000b39b  jmp     short loc_18000B40A
0x18000b39d  mov     rax, [rbx+10h]
0x18000b3a1  lea     rdi, [rbx+38h]
0x18000b3a5  xor     r10d, r10d
0x18000b3a8  cmp     [rsi], r10d
0x18000b3ab  jnz     short loc_18000B401
0x18000b3ad  mov     rcx, rax; lpMem
0x18000b3b0  mov     dword ptr [rbx+18h], 4000h
0x18000b3b7  call    MemFree
0x18000b3bc  mov     ecx, [rbx+18h]
0x18000b3bf  call    MemAlloc
0x18000b3c4  xor     r10d, r10d
0x18000b3c7  mov     [rbx+10h], rax
0x18000b3cb  mov     [rdi], rax
0x18000b3ce  test    rax, rax
0x18000b3d1  jz      loc_18000B1DA
0x18000b3d7  mov     dword ptr [rax], 84000000h
0x18000b3dd  lea     ecx, [r10+4]
0x18000b3e1  mov     rax, [rdi]
0x18000b3e4  mov     dword ptr [rax+8], 2000000h
0x18000b3eb  mov     rax, [rdi]
0x18000b3ee  mov     dword ptr [rax+24h], 70736361h
0x18000b3f5  mov     rax, [rdi]
0x18000b3f8  mov     [rax+80h], r10d
0x18000b3ff  jmp     short loc_18000B404
0x18000b401  mov     [rdi], rax
0x18000b404  mov     eax, [rbx+18h]
0x18000b407  mov     [rbx+30h], eax
0x18000b40a  cmp     r13d, r15d
0x18000b40d  jnz     short loc_18000B412
0x18000b40f  or      [rbx+1Ch], ecx
0x18000b412  mov     rcx, rbx
0x18000b415  call    ValidProfile
0x18000b41a  test    eax, eax
0x18000b41c  jz      short loc_18000B42A
0x18000b41e  mov     rax, [rdi]
0x18000b421  cmp     dword ptr [rax+24h], 70736361h
0x18000b428  jz      short loc_18000B42D
0x18000b42a  mov     ebp, r10d
0x18000b42d  mov     rax, [rsp+98h+arg_20]
0x18000b435  xor     ecx, ecx; dwErrCode
0x18000b437  mov     [rax], ebp
0x18000b439  call    cs:__imp_SetLastError
0x18000b43f  jmp     short loc_18000B457
0x18000b441  mov     ecx, 57h ; 'W'; dwErrCode
0x18000b446  call    cs:__imp_SetLastError
0x18000b44c  mov     rcx, r14; void *
0x18000b44f  call    ?FreeProfileObject@@YAHPEAX@Z; FreeProfileObject(void *)
0x18000b454  xor     r14d, r14d
0x18000b457  mov     rax, r14
0x18000b45a  jmp     short loc_18000B470
0x18000b45c  mov     ecx, 8
0x18000b461  jmp     short loc_18000B468
0x18000b463  mov     ecx, 57h ; 'W'; dwErrCode
0x18000b468  call    cs:__imp_SetLastError
0x18000b46e  xor     eax, eax
0x18000b470  mov     rbx, [rsp+98h+arg_8]
0x18000b478  add     rsp, 60h
0x18000b47c  pop     r15
0x18000b47e  pop     r14
0x18000b480  pop     r13
0x18000b482  pop     r12
0x18000b484  pop     rdi
0x18000b485  pop     rsi
0x18000b486  pop     rbp
0x18000b487  retn
```
