# CloseColorProfile

- ea: `0x18000bce0`
- end: `0x18000be3c`
- name: `CloseColorProfile`
- size: `348`
- prototype: `BOOL __stdcall(HPROFILE hProfile)`
- caller_count: `12`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180009e34`
- `0x18000a3fc`
- `0x18000a658`
- `0x18000a780`
- `0x18001fdc8`
- `0x18001ffe0`
- `0x18003cec4`
- `0x180049220`
- `0x180049924`
- `0x18004fc60`
- `0x180051480`
- `0x180063010`

## callees

- `0x18000bce0`
- `0x18000be44`
- `0x18000c310`
- `0x180050248`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bdb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bdd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bdb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bdd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd3d`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000be31`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000be31`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000be27`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000be27`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000be09`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000be09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be14`

## pseudocode

```c
BOOL __stdcall CloseColorProfile(HPROFILE hProfile)
{
  HANDLE *v1; // rbx
  DWORD LastError; // eax
  HANDLE v4; // rcx
  DWORD v5; // edi
  unsigned int v6; // ebp
  int v7; // esi
  HANDLE v8; // rcx
  HANDLE v9; // rcx
  unsigned int *v10; // r10
  unsigned __int32 v11; // eax

  if ( !hProfile )
    goto LABEL_19;
  v1 = (HANDLE *)((unsigned __int64)hProfile ^ 0x49434D20);
  if ( (unsigned __int64)hProfile == 0x49434D20 )
    goto LABEL_19;
  if ( *(_DWORD *)v1 == 1129860428 )
  {
    DeleteWcsProfile(*(void **)(((unsigned __int64)hProfile ^ 0x49434D20) + 0x40));
    --*((_DWORD *)v1 + 1);
    *(_DWORD *)v1 = 0;
    MemFree(v1);
    return 1;
  }
  if ( *(_DWORD *)v1 == 1347569228 )
  {
    LastError = GetLastError();
    v4 = v1[2];
    v5 = LastError;
    if ( v4 )
      MemFree(v4);
    if ( (*((_BYTE *)v1 + 28) & 1) != 0 )
    {
      v6 = 0;
      v7 = 0;
      if ( v1[7] )
      {
        if ( ValidProfile((__int64)v1) && v10[9] == 1886610273 )
        {
          v6 = *((_DWORD *)v1 + 12);
          v7 = 1;
          v11 = _byteswap_ulong(*v10);
          if ( v11 <= v6 )
            v6 = v11;
        }
        UnmapViewOfFile(v10);
      }
      v8 = v1[5];
      if ( v8 )
        CloseHandle(v8);
      v9 = v1[4];
      if ( v9 )
      {
        if ( v7 )
        {
          SetFilePointer(v9, v6, 0, 0);
          SetEndOfFile(v1[4]);
        }
        CloseHandle(v1[4]);
      }
    }
    --*((_DWORD *)v1 + 1);
    *(_DWORD *)v1 = 0;
    MemFree(v1);
    if ( v5 )
      SetLastError(v5);
    return 1;
  }
  else
  {
LABEL_19:
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000bce0  push    rbx
0x18000bce2  sub     rsp, 20h
0x18000bce6  mov     rbx, rcx
0x18000bce9  test    rcx, rcx
0x18000bcec  jz      loc_18000BDCF
0x18000bcf2  xor     rbx, 49434D20h
0x18000bcf9  jz      loc_18000BDCF
0x18000bcff  cmp     dword ptr [rbx], 43584D4Ch
0x18000bd05  jnz     short loc_18000BD2C
0x18000bd07  mov     rcx, [rbx+40h]; Block
0x18000bd0b  call    DeleteWcsProfile
0x18000bd10  dec     dword ptr [rbx+4]
0x18000bd13  mov     rcx, rbx; lpMem
0x18000bd16  mov     dword ptr [rbx], 0
0x18000bd1c  call    MemFree
0x18000bd21  mov     eax, 1
0x18000bd26  add     rsp, 20h
0x18000bd2a  pop     rbx
0x18000bd2b  retn
0x18000bd2c  cmp     dword ptr [rbx], 5052464Ch
0x18000bd32  jnz     loc_18000BDCF
0x18000bd38  mov     [rsp+28h+arg_10], rdi
0x18000bd3d  call    cs:__imp_GetLastError
0x18000bd43  mov     rcx, [rbx+10h]; lpMem
0x18000bd47  mov     edi, eax
0x18000bd49  test    rcx, rcx
0x18000bd4c  jz      short loc_18000BD53
0x18000bd4e  call    MemFree
0x18000bd53  test    byte ptr [rbx+1Ch], 1
0x18000bd57  jz      short loc_18000BDA2
0x18000bd59  mov     r10, [rbx+38h]
0x18000bd5d  mov     [rsp+28h+arg_0], rbp
0x18000bd62  xor     ebp, ebp
0x18000bd64  mov     [rsp+28h+arg_8], rsi
0x18000bd69  xor     esi, esi
0x18000bd6b  test    r10, r10
0x18000bd6e  jnz     short loc_18000BDDE
0x18000bd70  mov     rcx, [rbx+28h]; hObject
0x18000bd74  test    rcx, rcx
0x18000bd77  jnz     loc_18000BE14
0x18000bd7d  mov     rcx, [rbx+20h]; hFile
0x18000bd81  test    rcx, rcx
0x18000bd84  jz      short loc_18000BD98
0x18000bd86  test    esi, esi
0x18000bd88  jnz     loc_18000BE1F
0x18000bd8e  mov     rcx, [rbx+20h]; hObject
0x18000bd92  call    cs:__imp_CloseHandle
0x18000bd98  mov     rsi, [rsp+28h+arg_8]
0x18000bd9d  mov     rbp, [rsp+28h+arg_0]
0x18000bda2  dec     dword ptr [rbx+4]
0x18000bda5  mov     rcx, rbx; lpMem
0x18000bda8  mov     dword ptr [rbx], 0
0x18000bdae  call    MemFree
0x18000bdb3  test    edi, edi
0x18000bdb5  jz      short loc_18000BDBF
0x18000bdb7  mov     ecx, edi; dwErrCode
0x18000bdb9  call    cs:__imp_SetLastError
0x18000bdbf  mov     rdi, [rsp+28h+arg_10]
0x18000bdc4  mov     eax, 1
0x18000bdc9  add     rsp, 20h
0x18000bdcd  pop     rbx
0x18000bdce  retn
0x18000bdcf  mov     ecx, 57h ; 'W'; dwErrCode
0x18000bdd4  call    cs:__imp_SetLastError
0x18000bdda  xor     eax, eax
0x18000bddc  jmp     short loc_18000BDC9
0x18000bdde  mov     rcx, rbx
0x18000bde1  call    ValidProfile
0x18000bde6  test    eax, eax
0x18000bde8  jz      short loc_18000BE06
0x18000bdea  cmp     dword ptr [r10+24h], 70736361h
0x18000bdf2  jnz     short loc_18000BE06
0x18000bdf4  mov     ebp, [rbx+30h]
0x18000bdf7  mov     esi, 1
0x18000bdfc  mov     eax, [r10]
0x18000bdff  bswap   eax
0x18000be01  cmp     eax, ebp
0x18000be03  cmovbe  ebp, eax
0x18000be06  mov     rcx, r10; lpBaseAddress
0x18000be09  call    cs:__imp_UnmapViewOfFile
0x18000be0f  jmp     loc_18000BD70
0x18000be14  call    cs:__imp_CloseHandle
0x18000be1a  jmp     loc_18000BD7D
0x18000be1f  xor     r9d, r9d; dwMoveMethod
0x18000be22  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000be25  mov     edx, ebp; lDistanceToMove
0x18000be27  call    cs:__imp_SetFilePointer
0x18000be2d  mov     rcx, [rbx+20h]; hFile
0x18000be31  call    cs:__imp_SetEndOfFile
0x18000be37  jmp     loc_18000BD8E
```
