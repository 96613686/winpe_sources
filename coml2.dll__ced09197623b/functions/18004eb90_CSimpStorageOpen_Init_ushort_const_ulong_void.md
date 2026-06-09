# CSimpStorageOpen::Init(ushort const *,ulong,void *)

- ea: `0x18004eb90`
- end: `0x18004eec4`
- name: `?Init@CSimpStorageOpen@@QEAAJPEBGKPEAX@Z`
- size: `820`
- prototype: `__int64 __fastcall(CSimpStorageOpen *__hidden this, const unsigned __int16 *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004e778`

## callees

- `0x18001e2f0`
- `0x180026bc4`
- `0x18004eaa0`
- `0x18004eb90`
- `0x18004f23c`
- `0x18004f420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ecd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ed85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ec2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ecd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ed85`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004ec9c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004edb0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004ec9c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004edb0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004ed7a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004ed7a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004ec1a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004ec1a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18004eccc`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18004eccc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ed4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ed4b`

## pseudocode

```c
int __fastcall CSimpStorageOpen::Init(CSimpStorageOpen *this, const unsigned __int16 *a2, int a3, void *a4)
{
  int result; // eax
  DWORD v8; // edx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  void *v11; // rcx
  CSimpStorageOpen *v12; // rcx
  DWORD FileSize; // edi
  unsigned int v14; // r14d
  int v15; // r12d
  DWORD v16; // edi
  unsigned int v17; // r13d
  __int64 v18; // rsi
  DWORD v19; // edi
  _DWORD *v20; // r15
  DWORD v21; // eax
  int v22; // edi
  char *v23; // r10
  __int64 i; // rdx
  __int64 v25; // rax
  unsigned int v26; // r8d
  char *v27; // rcx
  int v28; // r9d
  unsigned int v29; // edx
  int v30; // ecx
  unsigned int v31; // esi
  _QWORD v32[4]; // [rsp+40h] [rbp-20h] BYREF
  int v33; // [rsp+A8h] [rbp+48h]
  DWORD NumberOfBytesRead; // [rsp+B0h] [rbp+50h] BYREF
  _DWORD *v35; // [rsp+B8h] [rbp+58h] BYREF

  v32[0] = 24;
  v32[2] = 0;
  v32[1] = a4;
  if ( (a3 & 3) != 0 )
  {
    if ( (a3 & 3) == 1 )
    {
      v8 = 0x40000000;
    }
    else
    {
      if ( (a3 & 3) != 2 )
        return -2147286953;
      v8 = -1073741824;
    }
  }
  else
  {
    v8 = 0x80000000;
  }
  FileW = CreateFileW(a2, v8, 0, (LPSECURITY_ATTRIBUTES)((unsigned __int64)v32 & -(__int64)(a4 != 0)), 3u, 0x80u, 0);
  *((_QWORD *)this + 8) = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_9;
  *((_DWORD *)this + 162) = a3;
  *((_DWORD *)this + 150) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 163) = 0;
  *(GUID *)((char *)this + 604) = GUID_NULL;
  result = StringCbCopyW((unsigned __int16 *)this + 328, 0x208u, a2);
  if ( result < 0 )
    return result;
  v11 = (void *)*((_QWORD *)this + 8);
  NumberOfBytesRead = 0;
  if ( !ReadFile(v11, (char *)this + 76, 0x200u, &NumberOfBytesRead, 0) )
    goto LABEL_9;
  if ( NumberOfBytesRead != 512 )
    return -2147287010;
  result = CSimpStorageOpen::ValidateHeader(v12, (CSimpStorageOpen *)((char *)this + 76));
  if ( result < 0 )
    return result;
  FileSize = GetFileSize(*((HANDLE *)this + 8), 0);
  if ( FileSize == -1 )
  {
    if ( GetLastError() )
    {
LABEL_9:
      LastError = GetLastError();
      return Win32ErrorToScode(LastError);
    }
  }
  v14 = *((_DWORD *)this + 30) << 9;
  if ( !v14 )
    return -2147286775;
  v15 = *((_DWORD *)this + 38);
  v16 = FileSize - (v15 << 9) - v14;
  v17 = v16 - 512;
  if ( v16 == 512 )
    return -2147286775;
  v18 = (unsigned int)(*((_DWORD *)this + 37) << 9);
  v19 = v14 + v18 + v17;
  if ( v19 >= 0x7FFFFF00 )
  {
    v35 = 0;
    goto LABEL_49;
  }
  v33 = *((_DWORD *)this + 36);
  v35 = HeapAlloc(g_hHeap, 0, v19);
  v20 = v35;
  if ( !v35 )
  {
LABEL_49:
    v22 = -2147287032;
    goto LABEL_50;
  }
  if ( (_DWORD)v18 )
    v15 = v33;
  if ( SetFilePointer(*((HANDLE *)this + 8), (v15 + 1) << 9, 0, 0) == -1
    || !ReadFile(*((HANDLE *)this + 8), v20, v19, &NumberOfBytesRead, 0) )
  {
    v21 = GetLastError();
    v22 = Win32ErrorToScode(v21);
LABEL_50:
    CSafeBYTEArray::~CSafeBYTEArray((CSafeBYTEArray *)&v35);
    return v22;
  }
  if ( NumberOfBytesRead != v19 )
  {
    v22 = -2147287010;
    goto LABEL_50;
  }
  v22 = CSimpStorageOpen::ValidateDirectory(
          this,
          (unsigned __int8 *)v20 + (unsigned int)v18 + (unsigned __int64)v14,
          v17);
  if ( v22 < 0 )
    goto LABEL_50;
  v23 = (char *)v20 + v18;
  for ( i = *(_QWORD *)(*((_QWORD *)this + 78) + 80LL); i; i = *(_QWORD *)(i + 80) )
  {
    v25 = *(unsigned int *)(i + 68);
    v26 = v25 + ((unsigned int)(*(_DWORD *)(i + 72) + 511) >> 9);
    v27 = &v23[4 * v25];
    v28 = v25 + 1;
    while ( (unsigned int)v25 < v26 )
    {
      if ( *(_DWORD *)v27 != v28 && *(_DWORD *)v27 != -2 )
        goto LABEL_46;
      v27 += 4;
      ++v28;
      LODWORD(v25) = v25 + 1;
    }
    if ( (unsigned int)((v27 - v23) >> 2) > v14 >> 2 )
    {
LABEL_46:
      v22 = -2147286780;
      goto LABEL_50;
    }
  }
  if ( (_DWORD)v18 )
  {
    v29 = 0;
    v30 = *((_DWORD *)this + 146) + 1;
    v31 = (unsigned int)v18 >> 2;
    while ( v29 < v31 )
    {
      if ( *v20 != -1 && (((_BYTE)v29 + 1) & 0x7F) != 0 )
      {
        if ( *v20 != v30 )
          goto LABEL_46;
        ++v30;
      }
      ++v20;
      ++v29;
    }
  }
  CSafeBYTEArray::~CSafeBYTEArray((CSafeBYTEArray *)&v35);
  return 0;
}

```

## disassembly

```asm
0x18004eb90  mov     [rsp-38h+arg_0], rbx
0x18004eb95  push    rbp
0x18004eb96  push    rsi
0x18004eb97  push    rdi
0x18004eb98  push    r12
0x18004eb9a  push    r13
0x18004eb9c  push    r14
0x18004eb9e  push    r15
0x18004eba0  mov     rbp, rsp
0x18004eba3  sub     rsp, 60h
0x18004eba7  xor     r15d, r15d
0x18004ebaa  mov     [rbp+var_20], 18h
0x18004ebb2  mov     eax, r8d
0x18004ebb5  mov     [rbp+var_10], r15
0x18004ebb9  mov     [rbp+var_18], r9
0x18004ebbd  mov     edi, r8d
0x18004ebc0  mov     rsi, rdx
0x18004ebc3  mov     rbx, rcx
0x18004ebc6  and     eax, 3
0x18004ebc9  jz      short loc_18004EBED
0x18004ebcb  sub     eax, 1
0x18004ebce  jz      short loc_18004EBE6
0x18004ebd0  cmp     eax, 1
0x18004ebd3  jz      short loc_18004EBDF
0x18004ebd5  mov     eax, 80030057h
0x18004ebda  jmp     loc_18004EEAC
0x18004ebdf  mov     edx, 0C0000000h
0x18004ebe4  jmp     short loc_18004EBF2
0x18004ebe6  mov     edx, 40000000h
0x18004ebeb  jmp     short loc_18004EBF2
0x18004ebed  mov     edx, 80000000h; dwDesiredAccess
0x18004ebf2  neg     r9
0x18004ebf5  mov     [rsp+60h+hTemplateFile], r15; hTemplateFile
0x18004ebfa  lea     rax, [rbp+var_20]
0x18004ebfe  mov     [rsp+60h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004ec06  sbb     r9, r9
0x18004ec09  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x18004ec11  and     r9, rax; lpSecurityAttributes
0x18004ec14  xor     r8d, r8d; dwShareMode
0x18004ec17  mov     rcx, rsi; lpFileName
0x18004ec1a  call    cs:__imp_CreateFileW
0x18004ec20  mov     [rbx+40h], rax
0x18004ec24  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004ec28  jnz     short loc_18004EC3C
0x18004ec2a  call    cs:__imp_GetLastError
0x18004ec30  mov     ecx, eax; unsigned int
0x18004ec32  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004ec37  jmp     loc_18004EEAC
0x18004ec3c  mov     [rbx+288h], edi
0x18004ec42  lea     rcx, [rbx+290h]; unsigned __int16 *
0x18004ec49  mov     [rbx+258h], r15d
0x18004ec50  mov     r8, rsi; unsigned __int16 *
0x18004ec53  mov     [rbx+48h], r15d
0x18004ec57  mov     edx, 208h; unsigned __int64
0x18004ec5c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004ec63  mov     [rbx+28Ch], r15d
0x18004ec6a  movdqu  xmmword ptr [rbx+25Ch], xmm0
0x18004ec72  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18004ec77  test    eax, eax
0x18004ec79  js      loc_18004EEAC
0x18004ec7f  mov     rcx, [rbx+40h]; hFile
0x18004ec83  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004ec87  mov     esi, 200h
0x18004ec8c  mov     [rbp+NumberOfBytesRead], r15d
0x18004ec90  mov     r8d, esi; nNumberOfBytesToRead
0x18004ec93  mov     qword ptr [rsp+60h+dwCreationDisposition], r15; lpOverlapped
0x18004ec98  lea     rdx, [rbx+4Ch]; lpBuffer
0x18004ec9c  call    cs:__imp_ReadFile
0x18004eca2  test    eax, eax
0x18004eca4  jz      short loc_18004EC2A
0x18004eca6  cmp     [rbp+NumberOfBytesRead], esi
0x18004eca9  jz      short loc_18004ECB5
0x18004ecab  mov     eax, 8003001Eh
0x18004ecb0  jmp     loc_18004EEAC
0x18004ecb5  lea     rdx, [rbx+4Ch]; struct CMSFHeader *
0x18004ecb9  call    ?ValidateHeader@CSimpStorageOpen@@QEAAJAEAVCMSFHeader@@@Z; CSimpStorageOpen::ValidateHeader(CMSFHeader &)
0x18004ecbe  test    eax, eax
0x18004ecc0  js      loc_18004EEAC
0x18004ecc6  mov     rcx, [rbx+40h]; hFile
0x18004ecca  xor     edx, edx; lpFileSizeHigh
0x18004eccc  call    cs:__imp_GetFileSize
0x18004ecd2  mov     edi, eax
0x18004ecd4  cmp     eax, 0FFFFFFFFh
0x18004ecd7  jnz     short loc_18004ECE7
0x18004ecd9  call    cs:__imp_GetLastError
0x18004ecdf  test    eax, eax
0x18004ece1  jnz     loc_18004EC2A
0x18004ece7  mov     r14d, [rbx+78h]
0x18004eceb  shl     r14d, 9
0x18004ecef  test    r14d, r14d
0x18004ecf2  jz      loc_18004EEA7
0x18004ecf8  mov     r12d, [rbx+98h]
0x18004ecff  mov     eax, r12d
0x18004ed02  shl     eax, 9
0x18004ed05  sub     edi, eax
0x18004ed07  sub     edi, r14d
0x18004ed0a  lea     r13d, [rdi-200h]
0x18004ed11  test    r13d, r13d
0x18004ed14  jz      loc_18004EEA7
0x18004ed1a  mov     esi, [rbx+94h]
0x18004ed20  shl     esi, 9
0x18004ed23  lea     edi, [rsi+r13]
0x18004ed27  add     edi, r14d
0x18004ed2a  cmp     edi, 7FFFFF00h
0x18004ed30  jnb     loc_18004EE91
0x18004ed36  mov     eax, [rbx+90h]
0x18004ed3c  xor     edx, edx; dwFlags
0x18004ed3e  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18004ed45  mov     r8d, edi; dwBytes
0x18004ed48  mov     [rbp+arg_8], eax
0x18004ed4b  call    cs:__imp_HeapAlloc
0x18004ed51  mov     [rbp+arg_18], rax
0x18004ed55  mov     r15, rax
0x18004ed58  test    rax, rax
0x18004ed5b  jz      loc_18004EE95
0x18004ed61  mov     rcx, [rbx+40h]; hFile
0x18004ed65  test    esi, esi
0x18004ed67  cmovnz  r12d, [rbp+arg_8]
0x18004ed6c  xor     r9d, r9d; dwMoveMethod
0x18004ed6f  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004ed72  lea     edx, [r12+1]
0x18004ed77  shl     edx, 9; lDistanceToMove
0x18004ed7a  call    cs:__imp_SetFilePointer
0x18004ed80  cmp     eax, 0FFFFFFFFh
0x18004ed83  jnz     short loc_18004ED99
0x18004ed85  call    cs:__imp_GetLastError
0x18004ed8b  mov     ecx, eax; unsigned int
0x18004ed8d  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004ed92  mov     edi, eax
0x18004ed94  jmp     loc_18004EE9A
0x18004ed99  mov     rcx, [rbx+40h]; hFile
0x18004ed9d  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004eda1  mov     r8d, edi; nNumberOfBytesToRead
0x18004eda4  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; lpOverlapped
0x18004edad  mov     rdx, r15; lpBuffer
0x18004edb0  call    cs:__imp_ReadFile
0x18004edb6  test    eax, eax
0x18004edb8  jz      short loc_18004ED85
0x18004edba  cmp     [rbp+NumberOfBytesRead], edi
0x18004edbd  jz      short loc_18004EDC9
0x18004edbf  mov     edi, 8003001Eh
0x18004edc4  jmp     loc_18004EE9A
0x18004edc9  mov     r12d, esi
0x18004edcc  mov     r8d, r13d; unsigned int
0x18004edcf  mov     edx, r14d
0x18004edd2  mov     rcx, rbx; this
0x18004edd5  add     rdx, r12
0x18004edd8  add     rdx, r15; unsigned __int8 *
0x18004eddb  call    ?ValidateDirectory@CSimpStorageOpen@@QEAAJPEAEK@Z; CSimpStorageOpen::ValidateDirectory(uchar *,ulong)
0x18004ede0  mov     edi, eax
0x18004ede2  test    eax, eax
0x18004ede4  js      loc_18004EE9A
0x18004edea  mov     rax, [rbx+270h]
0x18004edf1  lea     r10, [rsi+r15]
0x18004edf5  mov     rdx, [rax+50h]
0x18004edf9  test    rdx, rdx
0x18004edfc  jz      short loc_18004EE4C
0x18004edfe  mov     eax, [rdx+44h]
0x18004ee01  mov     r8d, [rdx+48h]
0x18004ee05  add     r8d, 1FFh
0x18004ee0c  shr     r8d, 9
0x18004ee10  add     r8d, eax
0x18004ee13  lea     rcx, [r10+rax*4]
0x18004ee17  lea     r9d, [rax+1]
0x18004ee1b  cmp     eax, r8d
0x18004ee1e  jnb     short loc_18004EE35
0x18004ee20  cmp     [rcx], r9d
0x18004ee23  jz      short loc_18004EE2A
0x18004ee25  cmp     dword ptr [rcx], 0FFFFFFFEh
0x18004ee28  jnz     short loc_18004EE7D
0x18004ee2a  add     rcx, 4
0x18004ee2e  inc     r9d
0x18004ee31  inc     eax
0x18004ee33  jmp     short loc_18004EE1B
0x18004ee35  sub     rcx, r10
0x18004ee38  mov     eax, r14d
0x18004ee3b  sar     rcx, 2
0x18004ee3f  shr     eax, 2
0x18004ee42  cmp     ecx, eax
0x18004ee44  ja      short loc_18004EE7D
0x18004ee46  mov     rdx, [rdx+50h]
0x18004ee4a  jmp     short loc_18004EDF9
0x18004ee4c  test    esi, esi
0x18004ee4e  jz      short loc_18004EE84
0x18004ee50  mov     ecx, [rbx+248h]
0x18004ee56  xor     edx, edx
0x18004ee58  inc     ecx
0x18004ee5a  shr     esi, 2
0x18004ee5d  cmp     edx, esi
0x18004ee5f  jnb     short loc_18004EE84
0x18004ee61  cmp     dword ptr [r15], 0FFFFFFFFh
0x18004ee65  jz      short loc_18004EE75
0x18004ee67  lea     eax, [rdx+1]
0x18004ee6a  test    al, 7Fh
0x18004ee6c  jz      short loc_18004EE75
0x18004ee6e  cmp     [r15], ecx
0x18004ee71  jnz     short loc_18004EE7D
0x18004ee73  inc     ecx
0x18004ee75  add     r15, 4
0x18004ee79  inc     edx
0x18004ee7b  jmp     short loc_18004EE5D
0x18004ee7d  mov     edi, 80030104h
0x18004ee82  jmp     short loc_18004EE9A
0x18004ee84  lea     rcx, [rbp+arg_18]; this
0x18004ee88  call    ??1CSafeBYTEArray@@QEAA@XZ; CSafeBYTEArray::~CSafeBYTEArray(void)
0x18004ee8d  xor     eax, eax
0x18004ee8f  jmp     short loc_18004EEAC
0x18004ee91  mov     [rbp+arg_18], r15
0x18004ee95  mov     edi, 80030008h
0x18004ee9a  lea     rcx, [rbp+arg_18]; this
0x18004ee9e  call    ??1CSafeBYTEArray@@QEAA@XZ; CSafeBYTEArray::~CSafeBYTEArray(void)
0x18004eea3  mov     eax, edi
0x18004eea5  jmp     short loc_18004EEAC
0x18004eea7  mov     eax, 80030109h
0x18004eeac  mov     rbx, [rsp+60h+arg_0]
0x18004eeb4  add     rsp, 60h
0x18004eeb8  pop     r15
0x18004eeba  pop     r14
0x18004eebc  pop     r13
0x18004eebe  pop     r12
0x18004eec0  pop     rdi
0x18004eec1  pop     rsi
0x18004eec2  pop     rbp
0x18004eec3  retn
```
