# UniStorInit(wchar_t const *,int,long (*)(unsigned __int64,void * *),long (*)(void *),void * *,ulong *)

- ea: `0x180057ef8`
- end: `0x180058212`
- name: `?UniStorInit@@YAJPEB_WHP6AJ_KPEAPEAX@ZP6AJPEAX@Z2PEAK@Z`
- size: `794`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int, int (*)(unsigned __int64, void **), int (*)(void *), void **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180057cc8`

## callees

- `0x180051438`
- `0x180057ef8`
- `0x180058220`
- `0x18005823c`
- `0x180058380`
- `0x18007f800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800580a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800580a9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180057fcc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180057fcc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180058041`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180058041`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180057ff0`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180057ff0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18005808b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18005808b`

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
0x180057ef8  mov     [rsp-8+arg_8], rbx
0x180057efd  mov     [rsp-8+arg_10], rsi
0x180057f02  push    rbp
0x180057f03  push    rdi
0x180057f04  push    r14
0x180057f06  lea     rbp, [rsp-37h]
0x180057f0b  sub     rsp, 0A0h
0x180057f12  mov     rax, cs:__security_cookie
0x180057f19  xor     rax, rsp
0x180057f1c  mov     [rbp+47h+var_18], rax
0x180057f20  xorps   xmm0, xmm0
0x180057f23  lea     rdx, [rbp+47h+var_70]; void **
0x180057f27  xor     r14d, r14d
0x180057f2a  mov     rdi, rcx
0x180057f2d  movups  [rbp+47h+var_38], xmm0
0x180057f31  mov     esi, 880h
0x180057f36  mov     [rbp+47h+var_70], r14
0x180057f3a  mov     ecx, esi; unsigned __int64
0x180057f3c  mov     qword ptr [rbp+47h+FileSize], r14
0x180057f40  movups  [rbp+47h+var_38+0Ch], xmm0
0x180057f44  mov     [rbp+47h+NumberOfBytesRead], r14d
0x180057f48  movups  [rbp+47h+Buffer], xmm0
0x180057f4c  movups  [rbp+47h+var_48], xmm0
0x180057f50  call    ?UspAllocForUniStore@@YAJ_KPEAPEAX@Z; UspAllocForUniStore(unsigned __int64,void * *)
0x180057f55  mov     ebx, eax
0x180057f57  test    eax, eax
0x180057f59  js      loc_1800581FB
0x180057f5f  mov     rax, [rbp+47h+var_70]
0x180057f63  mov     [rax], r14b
0x180057f66  inc     rax
0x180057f69  sub     rsi, 1
0x180057f6d  jnz     short loc_180057F63
0x180057f6f  mov     rax, [rbp+47h+var_70]
0x180057f73  lea     rcx, ?UspAllocForUniStore@@YAJ_KPEAPEAX@Z; UspAllocForUniStore(unsigned __int64,void * *)
0x180057f7a  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x180057f81  mov     rax, [rbp+47h+var_70]
0x180057f85  mov     [rax+10h], rcx
0x180057f89  lea     rcx, ?UspFreeForUniStore@@YAJPEAX@Z; UspFreeForUniStore(void *)
0x180057f90  mov     rax, [rbp+47h+var_70]
0x180057f94  mov     [rax+18h], rcx
0x180057f98  test    rdi, rdi
0x180057f9b  jz      loc_1800581E7
0x180057fa1  cmp     [rdi], r14w
0x180057fa5  jz      loc_1800581E7
0x180057fab  mov     [rsp+0B0h+hTemplateFile], r14; hTemplateFile
0x180057fb0  lea     r8d, [rsi+5]; dwShareMode
0x180057fb4  mov     [rsp+0B0h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180057fb9  xor     r9d, r9d; lpSecurityAttributes
0x180057fbc  mov     edx, 80000000h; dwDesiredAccess
0x180057fc1  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180057fc9  mov     rcx, rdi; lpFileName
0x180057fcc  call    cs:__imp_CreateFileW
0x180057fd3  nop     dword ptr [rax+rax+00h]
0x180057fd8  mov     rcx, [rbp+47h+var_70]
0x180057fdc  mov     [rcx], rax
0x180057fdf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180057fe3  jz      loc_1800580A9
0x180057fe9  lea     rdx, [rbp+47h+FileSize]; lpFileSize
0x180057fed  mov     rcx, rax; hFile
0x180057ff0  call    cs:__imp_GetFileSizeEx
0x180057ff7  nop     dword ptr [rax+rax+00h]
0x180057ffc  test    eax, eax
0x180057ffe  jz      loc_1800580A9
0x180058004  mov     rcx, [rbp+47h+var_70]
0x180058008  mov     rax, qword ptr [rbp+47h+FileSize]
0x18005800c  mov     [rcx+78h], rax
0x180058010  cmp     qword ptr [rbp+47h+FileSize], 0C800000h
0x180058018  jg      loc_1800581F6
0x18005801e  cmp     qword ptr [rbp+47h+FileSize], 3Ch ; '<'
0x180058023  jb      loc_1800581F6
0x180058029  mov     rcx, [rbp+47h+var_70]
0x18005802d  lea     r9, [rbp+47h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180058031  lea     r8d, [rsi+3Ch]; nNumberOfBytesToRead
0x180058035  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14; lpOverlapped
0x18005803a  lea     rdx, [rbp+47h+Buffer]; lpBuffer
0x18005803e  mov     rcx, [rcx]; hFile
0x180058041  call    cs:__imp_ReadFile
0x180058048  nop     dword ptr [rax+rax+00h]
0x18005804d  test    eax, eax
0x18005804f  jz      short loc_1800580A9
0x180058051  cmp     [rbp+47h+NumberOfBytesRead], 3Ch ; '<'
0x180058055  jnz     short loc_1800580A9
0x180058057  mov     rbx, qword ptr [rbp+47h+FileSize]
0x18005805b  lea     rcx, [rbp+47h+Buffer]; struct _UNISTOR_FILE_HEADER *
0x18005805f  mov     rdx, rbx; union _LARGE_INTEGER
0x180058062  call    ?CheckHeaderIntegrity@@YAHPEAU_UNISTOR_FILE_HEADER@@T_LARGE_INTEGER@@@Z; CheckHeaderIntegrity(_UNISTOR_FILE_HEADER *,_LARGE_INTEGER)
0x180058067  test    eax, eax
0x180058069  jz      loc_1800581EF
0x18005806f  mov     rcx, [rbp+47h+var_70]
0x180058073  xor     edx, edx; lpFileMappingAttributes
0x180058075  mov     r9d, dword ptr [rbp+47h+FileSize+4]; dwMaximumSizeHigh
0x180058079  mov     r8d, 8000002h; flProtect
0x18005807f  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r14; lpName
0x180058084  mov     [rsp+0B0h+dwCreationDisposition], ebx; dwMaximumSizeLow
0x180058088  mov     rcx, [rcx]; hFile
0x18005808b  call    cs:__imp_CreateFileMappingW
0x180058092  nop     dword ptr [rax+rax+00h]
0x180058097  mov     rcx, [rbp+47h+var_70]
0x18005809b  mov     [rcx+8], rax
0x18005809f  mov     rcx, [rbp+47h+var_70]; struct _UNISTOR_CLIENT *
0x1800580a3  cmp     [rcx+8], r14
0x1800580a7  jnz     short loc_1800580FE
0x1800580a9  call    cs:__imp_GetLastError
0x1800580b0  nop     dword ptr [rax+rax+00h]
0x1800580b5  mov     ebx, eax
0x1800580b7  test    eax, eax
0x1800580b9  jle     short loc_1800580C4
0x1800580bb  movzx   ebx, ax
0x1800580be  or      ebx, 80070000h
0x1800580c4  test    ebx, ebx
0x1800580c6  js      loc_1800581FB
0x1800580cc  mov     rax, [rbp+47h+var_70]
0x1800580d0  mov     cs:?ghUniStore@@3PEAXEA, rax; void * ghUniStore
0x1800580d7  mov     eax, ebx
0x1800580d9  mov     rcx, [rbp+47h+var_18]
0x1800580dd  xor     rcx, rsp; StackCookie
0x1800580e0  call    __security_check_cookie
0x1800580e5  lea     r11, [rsp+0B0h+var_10]
0x1800580ed  mov     rbx, [r11+28h]
0x1800580f1  mov     rsi, [r11+30h]
0x1800580f5  mov     rsp, r11
0x1800580f8  pop     r14
0x1800580fa  pop     rdi
0x1800580fb  pop     rbp
0x1800580fc  retn
0x1800580fe  call    ?MapFullFile@@YAJPEAU_UNISTOR_CLIENT@@@Z; MapFullFile(_UNISTOR_CLIENT *)
0x180058103  mov     ebx, eax
0x180058105  test    eax, eax
0x180058107  js      loc_1800581FB
0x18005810d  mov     rcx, [rbp+47h+var_70]
0x180058111  mov     rax, [rcx+20h]
0x180058115  mov     [rcx+28h], rax
0x180058119  mov     rax, [rbp+47h+var_70]
0x18005811d  mov     ecx, dword ptr [rbp+47h+var_38]
0x180058120  add     rcx, [rax+20h]
0x180058124  mov     [rax+30h], rcx
0x180058128  mov     rax, [rbp+47h+var_70]
0x18005812c  mov     ecx, dword ptr [rbp+47h+var_38+4]
0x18005812f  add     rcx, [rax+20h]
0x180058133  mov     [rax+38h], rcx
0x180058137  mov     rax, [rbp+47h+var_70]
0x18005813b  mov     ecx, dword ptr [rbp+47h+var_48+4]
0x18005813e  add     rcx, [rax+20h]
0x180058142  mov     [rax+40h], rcx
0x180058146  mov     eax, dword ptr [rbp+47h+var_48+0Ch]
0x180058149  mov     rcx, [rbp+47h+var_70]
0x18005814d  mov     [rcx+58h], eax
0x180058150  mov     eax, dword ptr [rbp+47h+var_48]
0x180058153  mov     rcx, [rbp+47h+var_70]
0x180058157  mov     [rcx+60h], eax
0x18005815a  mov     rcx, [rbp+47h+var_70]
0x18005815e  mov     eax, dword ptr [rbp+47h+Buffer+0Ch]
0x180058161  mov     [rcx+64h], eax
0x180058164  mov     r8d, dword ptr [rbp+47h+Buffer+0Ch]
0x180058168  mov     eax, r8d
0x18005816b  and     eax, 0FFFF0000h
0x180058170  neg     eax
0x180058172  mov     eax, r8d
0x180058175  sbb     r9b, r9b
0x180058178  and     eax, 0FF00FF00h
0x18005817d  and     r9b, 10h
0x180058181  neg     eax
0x180058183  mov     eax, r8d
0x180058186  sbb     cl, cl
0x180058188  and     eax, 0F0F0F0F0h
0x18005818d  and     cl, 8
0x180058190  add     r9b, cl
0x180058193  neg     eax
0x180058195  mov     eax, r8d
0x180058198  sbb     cl, cl
0x18005819a  and     eax, 0CCCCCCCCh
0x18005819f  and     cl, 4
0x1800581a2  add     r9b, cl
0x1800581a5  neg     eax
0x1800581a7  sbb     dl, dl
0x1800581a9  and     dl, 2
0x1800581ac  add     r9b, dl
0x1800581af  test    r8d, 0AAAAAAAAh
0x1800581b6  setnz   al
0x1800581b9  add     r9b, al
0x1800581bc  mov     rax, [rbp+47h+var_70]
0x1800581c0  mov     cl, r9b
0x1800581c3  mov     [rax+68h], r9b
0x1800581c7  mov     rax, [rbp+47h+var_70]
0x1800581cb  mov     edx, dword ptr [rbp+47h+var_48+8]
0x1800581ce  shr     edx, cl
0x1800581d0  mov     [rax+6Ch], edx
0x1800581d3  mov     rcx, [rbp+47h+var_70]
0x1800581d7  mov     eax, [rbp+47h+var_24]
0x1800581da  mov     [rcx+70h], eax
0x1800581dd  mov     rcx, [rbp+47h+var_70]
0x1800581e1  mov     eax, dword ptr [rbp+47h+var_38+0Ch]
0x1800581e4  mov     [rcx+74h], eax
0x1800581e7  mov     ebx, r14d
0x1800581ea  jmp     loc_1800580CC
0x1800581ef  mov     ebx, 80004005h
0x1800581f4  jmp     short loc_1800581FB
0x1800581f6  mov     ebx, 8007000Eh
0x1800581fb  mov     rcx, [rbp+47h+var_70]; struct _UNISTOR_CLIENT *
0x1800581ff  test    rcx, rcx
0x180058202  jz      loc_1800580D7
0x180058208  call    ?UniStorShutdownInternal@@YAXPEAU_UNISTOR_CLIENT@@@Z; UniStorShutdownInternal(_UNISTOR_CLIENT *)
0x18005820d  jmp     loc_1800580D7
```
