# UniStorInit(wchar_t const *,int,long (*)(unsigned __int64,void * *),long (*)(void *),void * *,ulong *)

- ea: `0x18005233c`
- end: `0x180052637`
- name: `?UniStorInit@@YAJPEB_WHP6AJ_KPEAPEAX@ZP6AJPEAX@Z2PEAK@Z`
- size: `763`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int, int (*)(unsigned __int64, void **), int (*)(void *), void **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005212c`

## callees

- `0x18004b5b0`
- `0x18005233c`
- `0x180052640`
- `0x18005265c`
- `0x18005279c`
- `0x18007ac50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524d5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180052410`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180052410`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180052479`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180052479`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18005242e`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18005242e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800524bd`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800524bd`

## pseudocode

```c
__int64 __fastcall UniStorInit(LPCWSTR lpFileName, __int64 a2, int (*a3)(unsigned __int64, void **), int (*a4)(void *))
{
  __int64 v5; // rsi
  signed int v6; // ebx
  struct _UNISTOR_CLIENT *v7; // rax
  HANDLE FileW; // rax
  DWORD LowPart; // ebx
  HANDLE FileMappingW; // rax
  signed int LastError; // eax
  char v13; // r9
  struct _UNISTOR_CLIENT *v14; // [rsp+40h] [rbp-29h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-21h] BYREF
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-19h] BYREF
  __int128 Buffer; // [rsp+58h] [rbp-11h] BYREF
  __int128 v18; // [rsp+68h] [rbp-1h]
  _OWORD v19[2]; // [rsp+78h] [rbp+Fh] BYREF

  memset(v19, 0, 28);
  v5 = 2176;
  v14 = 0;
  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  Buffer = 0;
  v18 = 0;
  v6 = UspAllocForUniStore(0x880u, (void **)&v14);
  if ( v6 < 0 )
    goto LABEL_24;
  v7 = v14;
  do
  {
    *(_BYTE *)v7 = 0;
    v7 = (struct _UNISTOR_CLIENT *)((char *)v7 + 1);
    --v5;
  }
  while ( v5 );
  *(_QWORD *)v14 = -1;
  *((_QWORD *)v14 + 2) = UspAllocForUniStore;
  *((_QWORD *)v14 + 3) = UspFreeForUniStore;
  if ( !lpFileName || !*lpFileName )
  {
LABEL_21:
    v6 = 0;
LABEL_17:
    ghUniStore = v14;
    return (unsigned int)v6;
  }
  FileW = CreateFileW(lpFileName, 0x80000000, 5u, 0, 3u, 0, 0);
  *(_QWORD *)v14 = FileW;
  if ( FileW != (HANDLE)-1LL && GetFileSizeEx(FileW, &FileSize) )
  {
    *((union _LARGE_INTEGER *)v14 + 15) = FileSize;
    if ( FileSize.QuadPart > 209715200 || FileSize.QuadPart < 0x3CuLL )
    {
      v6 = -2147024882;
      goto LABEL_24;
    }
    if ( ReadFile(*(HANDLE *)v14, &Buffer, 0x3Cu, &NumberOfBytesRead, 0) && NumberOfBytesRead == 60 )
    {
      LowPart = FileSize.LowPart;
      if ( !(unsigned int)CheckHeaderIntegrity((struct _UNISTOR_FILE_HEADER *)&Buffer, FileSize) )
      {
        v6 = -2147467259;
        goto LABEL_24;
      }
      FileMappingW = CreateFileMappingW(*(HANDLE *)v14, 0, 0x8000002u, FileSize.HighPart, LowPart, 0);
      *((_QWORD *)v14 + 1) = FileMappingW;
      if ( *((_QWORD *)v14 + 1) )
      {
        v6 = MapFullFile(v14);
        if ( v6 < 0 )
          goto LABEL_24;
        *((_QWORD *)v14 + 5) = *((_QWORD *)v14 + 4);
        *((_QWORD *)v14 + 6) = *((_QWORD *)v14 + 4) + LODWORD(v19[0]);
        *((_QWORD *)v14 + 7) = *((_QWORD *)v14 + 4) + DWORD1(v19[0]);
        *((_QWORD *)v14 + 8) = *((_QWORD *)v14 + 4) + DWORD1(v18);
        *((_DWORD *)v14 + 22) = HIDWORD(v18);
        *((_DWORD *)v14 + 24) = v18;
        *((_DWORD *)v14 + 25) = HIDWORD(Buffer);
        v13 = ((HIDWORD(Buffer) & 0xAAAAAAAA) != 0)
            + ((HIDWORD(Buffer) & 0xCCCCCCCC) != 0 ? 2 : 0)
            + ((HIDWORD(Buffer) & 0xF0F0F0F0) != 0 ? 4 : 0)
            + ((HIDWORD(Buffer) & 0xFF00FF00) != 0 ? 8 : 0)
            + ((HIDWORD(Buffer) & 0xFFFF0000) != 0 ? 0x10 : 0);
        *((_BYTE *)v14 + 104) = v13;
        *((_DWORD *)v14 + 27) = DWORD2(v18) >> v13;
        *((_DWORD *)v14 + 28) = DWORD1(v19[1]);
        *((_DWORD *)v14 + 29) = HIDWORD(v19[0]);
        goto LABEL_21;
      }
    }
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
    goto LABEL_17;
LABEL_24:
  if ( v14 )
    UniStorShutdownInternal(v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005233c  mov     [rsp-8+arg_8], rbx
0x180052341  mov     [rsp-8+arg_10], rsi
0x180052346  push    rbp
0x180052347  push    rdi
0x180052348  push    r14
0x18005234a  lea     rbp, [rsp-37h]
0x18005234f  sub     rsp, 0A0h
0x180052356  mov     rax, cs:__security_cookie
0x18005235d  xor     rax, rsp
0x180052360  mov     [rbp+47h+var_18], rax
0x180052364  xorps   xmm0, xmm0
0x180052367  lea     rdx, [rbp+47h+var_70]; void **
0x18005236b  xor     r14d, r14d
0x18005236e  mov     rdi, rcx
0x180052371  movups  [rbp+47h+var_38], xmm0
0x180052375  mov     esi, 880h
0x18005237a  mov     [rbp+47h+var_70], r14
0x18005237e  mov     ecx, esi; unsigned __int64
0x180052380  mov     qword ptr [rbp+47h+FileSize], r14
0x180052384  movups  [rbp+47h+var_38+0Ch], xmm0
0x180052388  mov     [rbp+47h+NumberOfBytesRead], r14d
0x18005238c  movups  [rbp+47h+Buffer], xmm0
0x180052390  movups  [rbp+47h+var_48], xmm0
0x180052394  call    ?UspAllocForUniStore@@YAJ_KPEAPEAX@Z; UspAllocForUniStore(unsigned __int64,void * *)
0x180052399  mov     ebx, eax
0x18005239b  test    eax, eax
0x18005239d  js      loc_180052620
0x1800523a3  mov     rax, [rbp+47h+var_70]
0x1800523a7  mov     [rax], r14b
0x1800523aa  inc     rax
0x1800523ad  sub     rsi, 1
0x1800523b1  jnz     short loc_1800523A7
0x1800523b3  mov     rax, [rbp+47h+var_70]
0x1800523b7  lea     rcx, ?UspAllocForUniStore@@YAJ_KPEAPEAX@Z; UspAllocForUniStore(unsigned __int64,void * *)
0x1800523be  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1800523c5  mov     rax, [rbp+47h+var_70]
0x1800523c9  mov     [rax+10h], rcx
0x1800523cd  lea     rcx, ?UspFreeForUniStore@@YAJPEAX@Z; UspFreeForUniStore(void *)
0x1800523d4  mov     rax, [rbp+47h+var_70]
0x1800523d8  mov     [rax+18h], rcx
0x1800523dc  test    rdi, rdi
0x1800523df  jz      loc_18005260C
0x1800523e5  cmp     [rdi], r14w
0x1800523e9  jz      loc_18005260C
0x1800523ef  mov     [rsp+0B0h+hTemplateFile], r14; hTemplateFile
0x1800523f4  lea     r8d, [rsi+5]; dwShareMode
0x1800523f8  mov     [rsp+0B0h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x1800523fd  xor     r9d, r9d; lpSecurityAttributes
0x180052400  mov     edx, 80000000h; dwDesiredAccess
0x180052405  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18005240d  mov     rcx, rdi; lpFileName
0x180052410  call    cs:__imp_CreateFileW
0x180052416  mov     rcx, [rbp+47h+var_70]
0x18005241a  mov     [rcx], rax
0x18005241d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180052421  jz      loc_1800524D5
0x180052427  lea     rdx, [rbp+47h+FileSize]; lpFileSize
0x18005242b  mov     rcx, rax; hFile
0x18005242e  call    cs:__imp_GetFileSizeEx
0x180052434  test    eax, eax
0x180052436  jz      loc_1800524D5
0x18005243c  mov     rcx, [rbp+47h+var_70]
0x180052440  mov     rax, qword ptr [rbp+47h+FileSize]
0x180052444  mov     [rcx+78h], rax
0x180052448  cmp     qword ptr [rbp+47h+FileSize], 0C800000h
0x180052450  jg      loc_18005261B
0x180052456  cmp     qword ptr [rbp+47h+FileSize], 3Ch ; '<'
0x18005245b  jb      loc_18005261B
0x180052461  mov     rcx, [rbp+47h+var_70]
0x180052465  lea     r9, [rbp+47h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180052469  lea     r8d, [rsi+3Ch]; nNumberOfBytesToRead
0x18005246d  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14; lpOverlapped
0x180052472  lea     rdx, [rbp+47h+Buffer]; lpBuffer
0x180052476  mov     rcx, [rcx]; hFile
0x180052479  call    cs:__imp_ReadFile
0x18005247f  test    eax, eax
0x180052481  jz      short loc_1800524D5
0x180052483  cmp     [rbp+47h+NumberOfBytesRead], 3Ch ; '<'
0x180052487  jnz     short loc_1800524D5
0x180052489  mov     rbx, qword ptr [rbp+47h+FileSize]
0x18005248d  lea     rcx, [rbp+47h+Buffer]; struct _UNISTOR_FILE_HEADER *
0x180052491  mov     rdx, rbx; union _LARGE_INTEGER
0x180052494  call    ?CheckHeaderIntegrity@@YAHPEAU_UNISTOR_FILE_HEADER@@T_LARGE_INTEGER@@@Z; CheckHeaderIntegrity(_UNISTOR_FILE_HEADER *,_LARGE_INTEGER)
0x180052499  test    eax, eax
0x18005249b  jz      loc_180052614
0x1800524a1  mov     rcx, [rbp+47h+var_70]
0x1800524a5  xor     edx, edx; lpFileMappingAttributes
0x1800524a7  mov     r9d, dword ptr [rbp+47h+FileSize+4]; dwMaximumSizeHigh
0x1800524ab  mov     r8d, 8000002h; flProtect
0x1800524b1  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r14; lpName
0x1800524b6  mov     [rsp+0B0h+dwCreationDisposition], ebx; dwMaximumSizeLow
0x1800524ba  mov     rcx, [rcx]; hFile
0x1800524bd  call    cs:__imp_CreateFileMappingW
0x1800524c3  mov     rcx, [rbp+47h+var_70]
0x1800524c7  mov     [rcx+8], rax
0x1800524cb  mov     rcx, [rbp+47h+var_70]; struct _UNISTOR_CLIENT *
0x1800524cf  cmp     [rcx+8], r14
0x1800524d3  jnz     short loc_180052523
0x1800524d5  call    cs:__imp_GetLastError
0x1800524db  mov     ebx, eax
0x1800524dd  test    eax, eax
0x1800524df  jle     short loc_1800524EA
0x1800524e1  movzx   ebx, ax
0x1800524e4  or      ebx, 80070000h
0x1800524ea  test    ebx, ebx
0x1800524ec  js      loc_180052620
0x1800524f2  mov     rax, [rbp+47h+var_70]
0x1800524f6  mov     cs:?ghUniStore@@3PEAXEA, rax; void * ghUniStore
0x1800524fd  mov     eax, ebx
0x1800524ff  mov     rcx, [rbp+47h+var_18]
0x180052503  xor     rcx, rsp; StackCookie
0x180052506  call    __security_check_cookie
0x18005250b  lea     r11, [rsp+0B0h+var_10]
0x180052513  mov     rbx, [r11+28h]
0x180052517  mov     rsi, [r11+30h]
0x18005251b  mov     rsp, r11
0x18005251e  pop     r14
0x180052520  pop     rdi
0x180052521  pop     rbp
0x180052522  retn
0x180052523  call    ?MapFullFile@@YAJPEAU_UNISTOR_CLIENT@@@Z; MapFullFile(_UNISTOR_CLIENT *)
0x180052528  mov     ebx, eax
0x18005252a  test    eax, eax
0x18005252c  js      loc_180052620
0x180052532  mov     rcx, [rbp+47h+var_70]
0x180052536  mov     rax, [rcx+20h]
0x18005253a  mov     [rcx+28h], rax
0x18005253e  mov     rax, [rbp+47h+var_70]
0x180052542  mov     ecx, dword ptr [rbp+47h+var_38]
0x180052545  add     rcx, [rax+20h]
0x180052549  mov     [rax+30h], rcx
0x18005254d  mov     rax, [rbp+47h+var_70]
0x180052551  mov     ecx, dword ptr [rbp+47h+var_38+4]
0x180052554  add     rcx, [rax+20h]
0x180052558  mov     [rax+38h], rcx
0x18005255c  mov     rax, [rbp+47h+var_70]
0x180052560  mov     ecx, dword ptr [rbp+47h+var_48+4]
0x180052563  add     rcx, [rax+20h]
0x180052567  mov     [rax+40h], rcx
0x18005256b  mov     eax, dword ptr [rbp+47h+var_48+0Ch]
0x18005256e  mov     rcx, [rbp+47h+var_70]
0x180052572  mov     [rcx+58h], eax
0x180052575  mov     eax, dword ptr [rbp+47h+var_48]
0x180052578  mov     rcx, [rbp+47h+var_70]
0x18005257c  mov     [rcx+60h], eax
0x18005257f  mov     rcx, [rbp+47h+var_70]
0x180052583  mov     eax, dword ptr [rbp+47h+Buffer+0Ch]
0x180052586  mov     [rcx+64h], eax
0x180052589  mov     r8d, dword ptr [rbp+47h+Buffer+0Ch]
0x18005258d  mov     eax, r8d
0x180052590  and     eax, 0FFFF0000h
0x180052595  neg     eax
0x180052597  mov     eax, r8d
0x18005259a  sbb     r9b, r9b
0x18005259d  and     eax, 0FF00FF00h
0x1800525a2  and     r9b, 10h
0x1800525a6  neg     eax
0x1800525a8  mov     eax, r8d
0x1800525ab  sbb     cl, cl
0x1800525ad  and     eax, 0F0F0F0F0h
0x1800525b2  and     cl, 8
0x1800525b5  add     r9b, cl
0x1800525b8  neg     eax
0x1800525ba  mov     eax, r8d
0x1800525bd  sbb     cl, cl
0x1800525bf  and     eax, 0CCCCCCCCh
0x1800525c4  and     cl, 4
0x1800525c7  add     r9b, cl
0x1800525ca  neg     eax
0x1800525cc  sbb     dl, dl
0x1800525ce  and     dl, 2
0x1800525d1  add     r9b, dl
0x1800525d4  test    r8d, 0AAAAAAAAh
0x1800525db  setnz   al
0x1800525de  add     r9b, al
0x1800525e1  mov     rax, [rbp+47h+var_70]
0x1800525e5  mov     cl, r9b
0x1800525e8  mov     [rax+68h], r9b
0x1800525ec  mov     rax, [rbp+47h+var_70]
0x1800525f0  mov     edx, dword ptr [rbp+47h+var_48+8]
0x1800525f3  shr     edx, cl
0x1800525f5  mov     [rax+6Ch], edx
0x1800525f8  mov     rcx, [rbp+47h+var_70]
0x1800525fc  mov     eax, [rbp+47h+var_24]
0x1800525ff  mov     [rcx+70h], eax
0x180052602  mov     rcx, [rbp+47h+var_70]
0x180052606  mov     eax, dword ptr [rbp+47h+var_38+0Ch]
0x180052609  mov     [rcx+74h], eax
0x18005260c  mov     ebx, r14d
0x18005260f  jmp     loc_1800524F2
0x180052614  mov     ebx, 80004005h
0x180052619  jmp     short loc_180052620
0x18005261b  mov     ebx, 8007000Eh
0x180052620  mov     rcx, [rbp+47h+var_70]; struct _UNISTOR_CLIENT *
0x180052624  test    rcx, rcx
0x180052627  jz      loc_1800524FD
0x18005262d  call    ?UniStorShutdownInternal@@YAXPEAU_UNISTOR_CLIENT@@@Z; UniStorShutdownInternal(_UNISTOR_CLIENT *)
0x180052632  jmp     loc_1800524FD
```
