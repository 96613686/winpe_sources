# CFileStream::Init_OpenOrCreate(ushort *,ulong,void *)

- ea: `0x18001e364`
- end: `0x18001e6a7`
- name: `?Init_OpenOrCreate@CFileStream@@AEAAJPEAGKPEAX@Z`
- size: `835`
- prototype: `int(CFileStream *__hidden this, unsigned __int16 *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001defc`

## callees

- `0x18001e364`
- `0x18001f708`
- `0x180026bc4`
- `0x18004bf24`
- `0x18004c0d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4aa`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18001e53a`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18001e53a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e489`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e518`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e489`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e518`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e570`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e614`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e570`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e614`
- `ext-ms-win-kernel32-file-l1-1-0!DuplicateEncryptionInfoFileExt` at `0x18001e5ae`
- `ext-ms-win-kernel32-file-l1-1-0!DuplicateEncryptionInfoFileExt` at `0x18001e5ae`

## pseudocode

```c
__int64 __fastcall CFileStream::Init_OpenOrCreate(CFileStream *this, unsigned __int16 *a2, char a3, void *a4)
{
  __int64 v7; // rcx
  int v9; // r8d
  int v10; // r10d
  int v11; // esi
  unsigned int v12; // edx
  int v13; // eax
  DWORD dwCreationDisposition; // ebx
  DWORD v15; // r15d
  DWORD v16; // r14d
  int v17; // ecx
  DWORD dwFlagsAndAttributes; // ebp
  HANDLE v19; // rax
  DWORD LastError; // eax
  __int64 result; // rax
  HANDLE FileW; // rax
  int v23; // eax
  void *v24; // rcx
  unsigned int v25; // ebx
  __int64 v26; // r9
  bool v27; // sf
  __int64 v28; // rdx
  _QWORD *ReservedForOle; // rcx
  __int64 v30; // rsi
  void *v31; // rcx
  _QWORD v32[13]; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v33; // [rsp+C0h] [rbp+18h] BYREF

  v7 = *((_QWORD *)this + 6);
  v9 = 0;
  v10 = *(_DWORD *)(v7 + 32);
  v11 = *(_DWORD *)(v7 + 36);
  v32[0] = 24;
  v32[2] = 0;
  v32[1] = a4;
  v12 = *(_DWORD *)(v7 + 36) & 0xFFFFFFD9;
  if ( !*(_WORD *)(v7 + 72) )
    v12 = *(_DWORD *)(v7 + 36);
  if ( (v12 & 0x20) != 0 )
  {
    dwCreationDisposition = 4;
  }
  else
  {
    v13 = v12 & 2;
    if ( (v12 & 4) != 0 )
      dwCreationDisposition = (v13 != 0) + 1;
    else
      dwCreationDisposition = v13 != 0 ? 5 : 3;
  }
  v15 = (*(_DWORD *)(v7 + 32) & 0x80) != 0 ? -1073741824 : 0x80000000;
  if ( (*(_DWORD *)(v7 + 32) & 0x200) == 0
    || (NtCurrentPeb()->AppCompatFlags.LowPart & 0x10000) != 0 && (*(_DWORD *)(v7 + 32) & 0x80) != 0 )
  {
    v16 = 3;
  }
  else
  {
    v16 = 1;
  }
  switch ( v12 & 0xC0 )
  {
    case 0u:
      goto LABEL_11;
    case 0x40u:
      v9 = 256;
      break;
    case 0x80u:
LABEL_11:
      v9 = 128;
      break;
  }
  if ( (v12 & 0x10) != 0 && (v12 & 0xC0) != 0 )
  {
    v9 |= 0x4000000u;
    v16 |= 4u;
  }
  v17 = v9 | 0x20000000;
  if ( (v12 & 0x200) == 0 )
    v17 = v9;
  dwFlagsAndAttributes = v17 | 0x4000;
  if ( (v12 & 0x400) == 0 )
    dwFlagsAndAttributes = v17;
  if ( (v10 & 0x180) != 256 || (a3 & 1) != 0 )
  {
LABEL_23:
    if ( (v11 & 0x404) == 0x404 )
    {
      v28 = *(_QWORD *)(*((_QWORD *)this + 6) + 616LL);
      if ( v28 )
      {
        ReservedForOle = NtCurrentTeb()->ReservedForOle;
        v30 = v28 + *ReservedForOle;
        if ( v30 )
        {
          if ( (unsigned int)CGlobalFileStream::IsDpapiNgEncryptedFile((CGlobalFileStream *)(v28 + *ReservedForOle)) )
          {
            v26 = dwFlagsAndAttributes;
            LODWORD(v26) = dwFlagsAndAttributes & 0xFBFFFFFF;
            result = DuplicateEncryptionInfoFileExt(v30 + 72, a2, dwCreationDisposition, v26, 0);
            v27 = (int)result < 0;
            if ( (int)result > 0 )
            {
              result = (unsigned __int16)result | 0x80070000;
              v27 = (int)result < 0;
            }
            if ( v27 )
              return result;
            dwCreationDisposition = 3;
          }
        }
      }
    }
    FileW = CreateFileW(
              a2,
              v15,
              v16,
              (LPSECURITY_ATTRIBUTES)((unsigned __int64)v32 & -(__int64)(a4 != 0)),
              dwCreationDisposition,
              dwFlagsAndAttributes,
              0);
    *((_QWORD *)this + 8) = FileW;
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_20;
    v23 = ProtectHandle(FileW);
    v24 = (void *)*((_QWORD *)this + 8);
    v25 = v23;
    if ( v23 < 0 )
    {
      CloseHandle(v24);
      result = v25;
      *((_QWORD *)this + 8) = -1;
      return result;
    }
    if ( (GetFileType(v24) & 0xFFFF7FFF) - 2 <= 1 )
      return 2147680519LL;
    if ( (*(_DWORD *)(*((_QWORD *)this + 6) + 36LL) & 0x200) != 0 )
    {
      v31 = (void *)*((_QWORD *)this + 8);
      v33 = 0;
      result = GetNtHandleSectorSize(v31, &v33);
      if ( (int)result < 0 )
        return result;
      if ( (v33 & 0x1FF) == 0 )
        *(_DWORD *)(*((_QWORD *)this + 6) + 56LL) = v33;
    }
    return 0;
  }
  v19 = CreateFileW(a2, 0x80000000, 0, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
  if ( v19 != (HANDLE)-1LL )
  {
    CloseHandle(v19);
    goto LABEL_23;
  }
  if ( GetLastError() != 183 )
  {
LABEL_20:
    LastError = GetLastError();
    return Win32ErrorToScode(LastError);
  }
  return 2147680336LL;
}

```

## disassembly

```asm
0x18001e364  push    rbx
0x18001e366  push    rbp
0x18001e367  push    rsi
0x18001e368  push    rdi
0x18001e369  push    r12
0x18001e36b  push    r13
0x18001e36d  push    r14
0x18001e36f  push    r15
0x18001e371  sub     rsp, 68h
0x18001e375  xor     ebp, ebp
0x18001e377  mov     r12, rdx
0x18001e37a  mov     rdi, rcx
0x18001e37d  mov     r11d, r8d
0x18001e380  mov     rcx, [rcx+30h]
0x18001e384  mov     r13, r9
0x18001e387  mov     r8d, ebp
0x18001e38a  mov     r10d, [rcx+20h]
0x18001e38e  mov     esi, [rcx+24h]
0x18001e391  mov     [rsp+0A8h+var_68], 18h
0x18001e39a  mov     [rsp+0A8h+var_58], rbp
0x18001e39f  mov     [rsp+0A8h+var_60], r9
0x18001e3a4  mov     edx, [rcx+24h]
0x18001e3a7  and     edx, 0FFFFFFD9h
0x18001e3aa  cmp     [rcx+48h], bp
0x18001e3ae  cmovz   edx, [rcx+24h]
0x18001e3b2  test    dl, 20h
0x18001e3b5  jnz     loc_18001E582
0x18001e3bb  mov     eax, edx
0x18001e3bd  and     eax, 2
0x18001e3c0  test    dl, 4
0x18001e3c3  jnz     loc_18001E5CE
0x18001e3c9  neg     eax
0x18001e3cb  sbb     ebx, ebx
0x18001e3cd  and     ebx, 2
0x18001e3d0  add     ebx, 3
0x18001e3d3  mov     r9d, [rcx+20h]
0x18001e3d7  and     r9d, 80h
0x18001e3de  mov     eax, r9d
0x18001e3e1  neg     eax
0x18001e3e3  sbb     r15d, r15d
0x18001e3e6  and     r15d, 40000000h
0x18001e3ed  add     r15d, 80000000h
0x18001e3f4  test    dword ptr [rcx+20h], 200h
0x18001e3fb  jnz     loc_18001E4BC
0x18001e401  mov     r14d, 3
0x18001e407  mov     ecx, edx
0x18001e409  mov     r9d, 100h
0x18001e40f  and     ecx, 0C0h
0x18001e415  mov     eax, ecx
0x18001e417  jz      short loc_18001E427
0x18001e419  sub     eax, 40h ; '@'
0x18001e41c  jz      loc_18001E5E9
0x18001e422  cmp     eax, 40h ; '@'
0x18001e425  jnz     short loc_18001E42D
0x18001e427  mov     r8d, 80h
0x18001e42d  test    dl, 10h
0x18001e430  jnz     loc_18001E5F1
0x18001e436  mov     ecx, r8d
0x18001e439  bts     ecx, 1Dh
0x18001e43d  bt      edx, 9
0x18001e441  cmovnb  ecx, r8d
0x18001e445  mov     ebp, ecx
0x18001e447  bts     ebp, 0Eh
0x18001e44b  bt      edx, 0Ah
0x18001e44f  cmovnb  ebp, ecx
0x18001e452  and     r10d, 180h
0x18001e459  cmp     r10d, r9d
0x18001e45c  setz    cl
0x18001e45f  test    r11b, 1
0x18001e463  setz    al
0x18001e466  test    al, cl
0x18001e468  jz      short loc_18001E4E1
0x18001e46a  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x18001e473  xor     r9d, r9d; lpSecurityAttributes
0x18001e476  mov     [rsp+0A8h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x18001e47a  xor     r8d, r8d; dwShareMode
0x18001e47d  mov     edx, 80000000h; dwDesiredAccess
0x18001e482  mov     [rsp+0A8h+dwCreationDisposition], ebx; dwCreationDisposition
0x18001e486  mov     rcx, r12; lpFileName
0x18001e489  call    cs:__imp_CreateFileW
0x18001e48f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e493  jnz     loc_18001E611
0x18001e499  call    cs:__imp_GetLastError
0x18001e49f  cmp     eax, 0B7h
0x18001e4a4  jz      loc_18001E607
0x18001e4aa  call    cs:__imp_GetLastError
0x18001e4b0  mov     ecx, eax; unsigned int
0x18001e4b2  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18001e4b7  jmp     loc_18001E55F
0x18001e4bc  mov     rax, gs:60h
0x18001e4c5  mov     ecx, [rax+2C8h]
0x18001e4cb  bt      rcx, 10h
0x18001e4d0  jb      loc_18001E5DB
0x18001e4d6  mov     r14d, 1
0x18001e4dc  jmp     loc_18001E407
0x18001e4e1  mov     eax, 404h
0x18001e4e6  and     esi, eax
0x18001e4e8  cmp     esi, eax
0x18001e4ea  jz      loc_18001E61F
0x18001e4f0  lea     rax, [rsp+0A8h+var_68]
0x18001e4f5  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x18001e4fe  neg     r13
0x18001e501  mov     [rsp+0A8h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x18001e505  mov     r8d, r14d; dwShareMode
0x18001e508  mov     [rsp+0A8h+dwCreationDisposition], ebx; dwCreationDisposition
0x18001e50c  sbb     r9, r9
0x18001e50f  mov     edx, r15d; dwDesiredAccess
0x18001e512  and     r9, rax; lpSecurityAttributes
0x18001e515  mov     rcx, r12; lpFileName
0x18001e518  call    cs:__imp_CreateFileW
0x18001e51e  mov     [rdi+40h], rax
0x18001e522  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e526  jz      short loc_18001E4AA
0x18001e528  mov     rcx, rax; ObjectHandle
0x18001e52b  call    ?ProtectHandle@@YAJPEAX@Z; ProtectHandle(void *)
0x18001e530  mov     rcx, [rdi+40h]; hObject
0x18001e534  mov     ebx, eax
0x18001e536  test    eax, eax
0x18001e538  js      short loc_18001E570
0x18001e53a  call    cs:__imp_GetFileType
0x18001e540  btr     eax, 0Fh
0x18001e544  sub     eax, 2
0x18001e547  cmp     eax, 1
0x18001e54a  jbe     short loc_18001E58C
0x18001e54c  mov     rax, [rdi+30h]
0x18001e550  test    dword ptr [rax+24h], 200h
0x18001e557  jnz     loc_18001E664
0x18001e55d  xor     eax, eax
0x18001e55f  add     rsp, 68h
0x18001e563  pop     r15
0x18001e565  pop     r14
0x18001e567  pop     r13
0x18001e569  pop     r12
0x18001e56b  pop     rdi
0x18001e56c  pop     rsi
0x18001e56d  pop     rbp
0x18001e56e  pop     rbx
0x18001e56f  retn
0x18001e570  call    cs:__imp_CloseHandle
0x18001e576  mov     eax, ebx
0x18001e578  mov     qword ptr [rdi+40h], 0FFFFFFFFFFFFFFFFh
0x18001e580  jmp     short loc_18001E55F
0x18001e582  mov     ebx, 4
0x18001e587  jmp     loc_18001E3D3
0x18001e58c  mov     eax, 80030107h
0x18001e591  jmp     short loc_18001E55F
0x18001e593  mov     r9d, ebp
0x18001e596  mov     qword ptr [rsp+0A8h+dwCreationDisposition], 0
0x18001e59f  btr     r9d, 1Ah
0x18001e5a4  lea     rcx, [rsi+48h]
0x18001e5a8  mov     r8d, ebx
0x18001e5ab  mov     rdx, r12
0x18001e5ae  call    cs:__imp_DuplicateEncryptionInfoFileExt
0x18001e5b4  test    eax, eax
0x18001e5b6  jle     short loc_18001E5C2
0x18001e5b8  movzx   eax, ax
0x18001e5bb  or      eax, 80070000h
0x18001e5c0  test    eax, eax
0x18001e5c2  js      short loc_18001E55F
0x18001e5c4  mov     ebx, 3
0x18001e5c9  jmp     loc_18001E4F0
0x18001e5ce  neg     eax
0x18001e5d0  sbb     ebx, ebx
0x18001e5d2  neg     ebx
0x18001e5d4  inc     ebx
0x18001e5d6  jmp     loc_18001E3D3
0x18001e5db  test    r9d, r9d
0x18001e5de  jnz     loc_18001E401
0x18001e5e4  jmp     loc_18001E4D6
0x18001e5e9  mov     r8d, r9d
0x18001e5ec  jmp     loc_18001E42D
0x18001e5f1  test    ecx, ecx
0x18001e5f3  jz      loc_18001E436
0x18001e5f9  bts     r8d, 1Ah
0x18001e5fe  or      r14d, 4
0x18001e602  jmp     loc_18001E436
0x18001e607  mov     eax, 80030050h
0x18001e60c  jmp     loc_18001E55F
0x18001e611  mov     rcx, rax; hObject
0x18001e614  call    cs:__imp_CloseHandle
0x18001e61a  jmp     loc_18001E4E1
0x18001e61f  mov     rax, [rdi+30h]
0x18001e623  mov     rdx, [rax+268h]
0x18001e62a  test    rdx, rdx
0x18001e62d  jz      loc_18001E4F0
0x18001e633  mov     rax, gs:30h
0x18001e63c  mov     rcx, [rax+1758h]
0x18001e643  mov     rsi, [rcx]
0x18001e646  add     rsi, rdx
0x18001e649  jz      loc_18001E4F0
0x18001e64f  mov     rcx, rsi; this
0x18001e652  call    ?IsDpapiNgEncryptedFile@CGlobalFileStream@@QEBAHXZ; CGlobalFileStream::IsDpapiNgEncryptedFile(void)
0x18001e657  test    eax, eax
0x18001e659  jz      loc_18001E4F0
0x18001e65f  jmp     loc_18001E593
0x18001e664  mov     rcx, [rdi+40h]; void *
0x18001e668  lea     rdx, [rsp+0A8h+arg_10]; unsigned int *
0x18001e670  mov     [rsp+0A8h+arg_10], 0
0x18001e67b  call    ?GetNtHandleSectorSize@@YAJPEAXPEAK@Z; GetNtHandleSectorSize(void *,ulong *)
0x18001e680  test    eax, eax
0x18001e682  js      loc_18001E55F
0x18001e688  mov     ecx, [rsp+0A8h+arg_10]
0x18001e68f  test    ecx, 1FFh
0x18001e695  jnz     loc_18001E55D
0x18001e69b  mov     rax, [rdi+30h]
0x18001e69f  mov     [rax+38h], ecx
0x18001e6a2  jmp     loc_18001E55D
```
