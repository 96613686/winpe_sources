# TargetInfo::CopyHostFile(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800e86a8`
- end: `0x1800e8b2a`
- name: `?CopyHostFile@TargetInfo@@QEAAJPEBG00H@Z`
- size: `1154`
- prototype: `__int64 __fastcall(TargetInfo *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801f7950`

## callees

- `0x1800727b8`
- `0x1800793cc`
- `0x1800797ec`
- `0x18007c2dc`
- `0x18007cf9c`
- `0x18007daa4`
- `0x180085700`
- `0x18008d550`
- `0x1800e86a8`
- `0x1800e8b30`
- `0x1800f0f40`
- `0x180159910`
- `0x1802cac30`
- `0x1802e5634`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e87f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8a29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8ac7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e87f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8a29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8a40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8ac7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e8aa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e8aa2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e89a5`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e89a5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800e87da`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800e87da`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e87b5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e87b5`

## string_xrefs

- `0x1800e8aef`: `Unable to open '%ws', %s\n`
- `0x1800e8818`: `Unable to allocate target path\n`
- `0x1800e894a`: `Copying %ws (%.2lf MB)`
- `0x1800e88da`: `Unable to create '%ws', %s\n`
- `0x1800e8a7c`: `\nUnable to copy file content, %s\n`
- `0x1800e8966`: `Copying %ws (%I64u KB)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TargetInfo::CopyHostFile(
        TargetInfo *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5)
{
  TargetInfo *v7; // r14
  __int64 v8; // r9
  __int64 v9; // r9
  char *FileW; // rax
  void *v11; // r15
  unsigned int v12; // ebx
  signed int v14; // eax
  unsigned __int16 *v15; // rax
  int v16; // r8d
  int v17; // eax
  unsigned __int16 *v18; // rax
  unsigned __int64 v19; // r8
  unsigned int v20; // r12d
  double v21; // xmm2_8
  unsigned __int64 i; // rdi
  signed int v23; // eax
  unsigned __int16 *v24; // rax
  signed int LastError; // eax
  unsigned __int16 *v26; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  DWORD FileSizeHigh; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v29; // [rsp+48h] [rbp-B8h]
  _QWORD v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v31; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v32; // [rsp+6Ch] [rbp-94h]
  char v33; // [rsp+78h] [rbp-88h] BYREF
  _BYTE Buffer[8192]; // [rsp+280h] [rbp+180h] BYREF

  v30[1] = -2;
  v7 = g_Target;
  v30[0] = 0;
  FileSizeHigh = 0;
  DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>(
    (unsigned int)&v31,
    (unsigned int)&v33,
    260,
    (_DWORD)a3,
    1);
  if ( v8 && PathTail(a4) == a4 )
  {
    if ( !DbsDynamicString<unsigned short>::CopyStr(&v31, v9, 0xFFFFFFFFLL)
      || (unsigned int)DbsDynamicString<unsigned short>::AppendStr((DbsDynamicBuffer *)&v31, (void *)L"\\")
      || (unsigned int)DbsDynamicString<unsigned short>::AppendStr((DbsDynamicBuffer *)&v31, a4) )
    {
      ErrOut(L"Unable to allocate target path\n");
      DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v31);
      return 2147942414LL;
    }
    a4 = 0;
    if ( v32 >= 2 )
      a4 = (unsigned __int16 *)v31;
  }
  FileW = (char *)CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v11 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v12 = -2147467259;
    }
    v26 = FormatStatusCode(v12);
    ErrOut(L"Unable to open '%ws', %s\n", a2, v26);
    goto LABEL_53;
  }
  if ( GetFileSize(FileW, &FileSizeHigh) == -1 && GetLastError() )
  {
    if ( GetLastError() )
    {
      v14 = GetLastError();
      v12 = v14;
      if ( v14 > 0 )
        v12 = (unsigned __int16)v14 | 0x80070000;
    }
    else
    {
      v12 = -2147467259;
    }
    v15 = FormatStatusCode(v12);
    ErrOut(L"Unable to get file size of '%ws', %s\n", a2, v15);
    goto LABEL_47;
  }
  if ( PathTail(a4) != a4 )
    TargetInfo::CreateTargetDirPath(v7, a4, v16);
  v17 = (*(__int64 (__fastcall **)(TargetInfo *, unsigned __int16 *, __int64, _QWORD, unsigned int, int, _QWORD *))(*(_QWORD *)v7 + 1248LL))(
          v7,
          a4,
          0x40000000,
          0,
          (unsigned int)(a5 != 0) + 1,
          128,
          v30);
  v12 = v17;
  if ( v17 )
  {
    v18 = FormatStatusCode(v17);
    ErrOut(L"Unable to create '%ws', %s\n", a4, v18);
    goto LABEL_47;
  }
  NumberOfBytesRead = 0;
  v29 = 0;
  v20 = MarkInterrupts(3u);
  if ( v19 <= 0x100000 )
  {
    dprintf(L"Copying %ws (%I64u KB)", a2, (v19 + 1023) >> 10);
  }
  else
  {
    if ( (v19 & 0x8000000000000000uLL) != 0LL )
      v21 = (double)(int)(v19 & 1 | (v19 >> 1)) + (double)(int)(v19 & 1 | (v19 >> 1));
    else
      v21 = (double)(int)v19;
    dprintf(L"Copying %ws (%.2lf MB)", a2, v21 * 0.00000095367431640625);
  }
LABEL_27:
  for ( i = 0x40000; ; i -= v29 )
  {
    if ( v20 != g_UserInterruptCount )
    {
      v12 = -805306054;
      goto LABEL_45;
    }
    if ( !ReadFile(v11, Buffer, 0x2000u, &NumberOfBytesRead, 0) )
    {
      if ( !GetLastError() )
      {
        v12 = -2147467259;
        goto LABEL_45;
      }
      v23 = GetLastError();
      v12 = v23;
      if ( v23 > 0 )
        v12 = (unsigned __int16)v23 | 0x80070000;
      if ( v12 )
        goto LABEL_45;
LABEL_43:
      dprintf(L"\n");
      goto LABEL_46;
    }
    if ( !NumberOfBytesRead )
    {
      v12 = 0;
      goto LABEL_43;
    }
    v12 = (*(__int64 (__fastcall **)(TargetInfo *, _QWORD, _BYTE *))(*(_QWORD *)v7 + 1264LL))(v7, v30[0], Buffer);
    if ( v12 )
      goto LABEL_45;
    if ( v29 != NumberOfBytesRead )
      break;
    if ( i <= v29 )
    {
      dprintf(L".");
      FlushCallbacks();
      goto LABEL_27;
    }
  }
  v12 = -2147024784;
LABEL_45:
  v24 = FormatStatusCode(v12);
  ErrOut(L"\nUnable to copy file content, %s\n", v24);
LABEL_46:
  (*(void (__fastcall **)(TargetInfo *, _QWORD))(*(_QWORD *)v7 + 1272LL))(v7, v30[0]);
LABEL_47:
  CloseHandle(v11);
LABEL_53:
  DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v31);
  return v12;
}

```

## disassembly

```asm
0x1800e86a8  push    rbp
0x1800e86aa  push    rbx
0x1800e86ab  push    rsi
0x1800e86ac  push    rdi
0x1800e86ad  push    r12
0x1800e86af  push    r14
0x1800e86b1  push    r15
0x1800e86b3  lea     rbp, [rsp-2190h]
0x1800e86bb  mov     eax, 2290h
0x1800e86c0  call    _alloca_probe
0x1800e86c5  sub     rsp, rax
0x1800e86c8  mov     [rsp+22C0h+var_2268], 0FFFFFFFFFFFFFFFEh
0x1800e86d1  mov     rax, cs:__security_cookie
0x1800e86d8  xor     rax, rsp
0x1800e86db  mov     [rbp+21C0h+var_40], rax
0x1800e86e2  mov     rdi, r9
0x1800e86e5  mov     r9, r8
0x1800e86e8  mov     rsi, rdx
0x1800e86eb  mov     r14, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x1800e86f2  mov     [rsp+22C0h+var_2270], 0
0x1800e86fb  mov     [rsp+22C0h+FileSizeHigh], 0
0x1800e8703  mov     byte ptr [rsp+22C0h+dwCreationDisposition], 1
0x1800e8708  mov     r8d, 104h
0x1800e870e  lea     rdx, [rsp+22C0h+var_2248]
0x1800e8713  lea     rcx, [rsp+22C0h+var_2260]
0x1800e8718  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x1800e871d  nop
0x1800e871e  or      ebx, 0FFFFFFFFh
0x1800e8721  test    r9, r9
0x1800e8724  jz      short loc_1800E878D
0x1800e8726  mov     rcx, rdi; unsigned __int16 *
0x1800e8729  call    ?PathTail@@YAPEBGPEBG@Z; PathTail(ushort const *)
0x1800e872e  cmp     rax, rdi
0x1800e8731  jnz     short loc_1800E878D
0x1800e8733  mov     r8d, ebx
0x1800e8736  mov     rdx, r9
0x1800e8739  lea     rcx, [rsp+22C0h+var_2260]
0x1800e873e  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x1800e8743  test    rax, rax
0x1800e8746  jz      loc_1800E8818
0x1800e874c  mov     r8d, ebx
0x1800e874f  lea     rdx, asc_1805DF320; "\\"
0x1800e8756  lea     rcx, [rsp+22C0h+var_2260]; this
0x1800e875b  call    ?AppendStr@?$DbsDynamicString@G@@QEAAJPEBGK@Z; DbsDynamicString<ushort>::AppendStr(ushort const *,ulong)
0x1800e8760  test    eax, eax
0x1800e8762  jnz     loc_1800E8818
0x1800e8768  mov     r8d, ebx
0x1800e876b  mov     rdx, rdi; Src
0x1800e876e  lea     rcx, [rsp+22C0h+var_2260]; this
0x1800e8773  call    ?AppendStr@?$DbsDynamicString@G@@QEAAJPEBGK@Z; DbsDynamicString<ushort>::AppendStr(ushort const *,ulong)
0x1800e8778  test    eax, eax
0x1800e877a  jnz     loc_1800E8818
0x1800e8780  xor     edi, edi
0x1800e8782  cmp     [rsp+22C0h+var_2254], 2
0x1800e8787  cmovnb  rdi, [rsp+22C0h+var_2260]
0x1800e878d  mov     [rsp+22C0h+hTemplateFile], 0; hTemplateFile
0x1800e8796  mov     [rsp+22C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800e879e  mov     [rsp+22C0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800e87a6  xor     r9d, r9d; lpSecurityAttributes
0x1800e87a9  mov     edx, 80000000h; dwDesiredAccess
0x1800e87ae  lea     r8d, [r9+1]; dwShareMode
0x1800e87b2  mov     rcx, rsi; lpFileName
0x1800e87b5  call    cs:__imp_CreateFileW
0x1800e87bc  nop     dword ptr [rax+rax+00h]
0x1800e87c1  mov     r15, rax
0x1800e87c4  lea     rcx, [rax-1]
0x1800e87c8  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800e87cc  ja      loc_1800E8AB0
0x1800e87d2  lea     rdx, [rsp+22C0h+FileSizeHigh]; lpFileSizeHigh
0x1800e87d7  mov     rcx, rax; hFile
0x1800e87da  call    cs:__imp_GetFileSize
0x1800e87e1  nop     dword ptr [rax+rax+00h]
0x1800e87e6  mov     r12d, eax
0x1800e87e9  cmp     eax, ebx
0x1800e87eb  jnz     loc_1800E8872
0x1800e87f1  call    cs:__imp_GetLastError
0x1800e87f8  nop     dword ptr [rax+rax+00h]
0x1800e87fd  test    eax, eax
0x1800e87ff  jz      short loc_1800E8872
0x1800e8801  call    cs:__imp_GetLastError
0x1800e8808  nop     dword ptr [rax+rax+00h]
0x1800e880d  test    eax, eax
0x1800e880f  jnz     short loc_1800E8839
0x1800e8811  mov     ebx, 80004005h
0x1800e8816  jmp     short loc_1800E8854
0x1800e8818  lea     rcx, aUnableToAlloca_18; "Unable to allocate target path\n"
0x1800e881f  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800e8824  nop
0x1800e8825  lea     rcx, [rsp+22C0h+var_2260]
0x1800e882a  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x1800e882f  mov     eax, 8007000Eh
0x1800e8834  jmp     loc_1800E8B08
0x1800e8839  call    cs:__imp_GetLastError
0x1800e8840  nop     dword ptr [rax+rax+00h]
0x1800e8845  mov     ebx, eax
0x1800e8847  test    eax, eax
0x1800e8849  jle     short loc_1800E8854
0x1800e884b  movzx   ebx, ax
0x1800e884e  or      ebx, 80070000h
0x1800e8854  mov     ecx, ebx; int
0x1800e8856  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x1800e885b  mov     rdx, rsi
0x1800e885e  lea     rcx, aUnableToGetFil; "Unable to get file size of '%ws', %s\n"
0x1800e8865  mov     r8, rax
0x1800e8868  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800e886d  jmp     loc_1800E8A9F
0x1800e8872  mov     rcx, rdi; unsigned __int16 *
0x1800e8875  call    ?PathTail@@YAPEBGPEBG@Z; PathTail(ushort const *)
0x1800e887a  cmp     rax, rdi
0x1800e887d  jz      short loc_1800E888A
0x1800e887f  mov     rdx, rdi; unsigned __int16 *
0x1800e8882  mov     rcx, r14; this
0x1800e8885  call    ?CreateTargetDirPath@TargetInfo@@QEAAJPEBGH@Z; TargetInfo::CreateTargetDirPath(ushort const *,int)
0x1800e888a  mov     rax, [r14]
0x1800e888d  neg     [rbp+21C0h+arg_20]
0x1800e8893  sbb     ecx, ecx
0x1800e8895  neg     ecx
0x1800e8897  inc     ecx
0x1800e8899  lea     rdx, [rsp+22C0h+var_2270]
0x1800e889e  mov     [rsp+22C0h+hTemplateFile], rdx
0x1800e88a3  mov     [rsp+22C0h+dwFlagsAndAttributes], 80h
0x1800e88ab  mov     [rsp+22C0h+dwCreationDisposition], ecx
0x1800e88af  xor     r9d, r9d
0x1800e88b2  mov     r8d, 40000000h
0x1800e88b8  mov     rdx, rdi
0x1800e88bb  mov     rcx, r14
0x1800e88be  mov     rax, [rax+4E0h]
0x1800e88c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e88ca  mov     ebx, eax
0x1800e88cc  test    eax, eax
0x1800e88ce  jz      short loc_1800E88E3
0x1800e88d0  mov     ecx, eax; int
0x1800e88d2  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x1800e88d7  mov     rdx, rdi
0x1800e88da  lea     rcx, aUnableToCreate_2; "Unable to create '%ws', %s\n"
0x1800e88e1  jmp     short loc_1800E8865
0x1800e88e3  mov     [rsp+22C0h+NumberOfBytesRead], 0
0x1800e88eb  mov     [rsp+22C0h+var_2278], 0
0x1800e88f3  mov     r8d, [rsp+22C0h+FileSizeHigh]
0x1800e88f8  shl     r8, 20h
0x1800e88fc  or      r8, r12
0x1800e88ff  mov     ecx, 3; unsigned int
0x1800e8904  call    ?MarkInterrupts@@YAKK@Z; MarkInterrupts(ulong)
0x1800e8909  mov     r12d, eax
0x1800e890c  cmp     r8, 100000h
0x1800e8913  jbe     short loc_1800E8958
0x1800e8915  xorps   xmm2, xmm2
0x1800e8918  test    r8, r8
0x1800e891b  js      short loc_1800E8924
0x1800e891d  cvtsi2sd xmm2, r8
0x1800e8922  jmp     short loc_1800E893A
0x1800e8924  mov     rax, r8
0x1800e8927  shr     rax, 1
0x1800e892a  and     r8d, 1
0x1800e892e  or      rax, r8
0x1800e8931  cvtsi2sd xmm2, rax
0x1800e8936  addsd   xmm2, xmm2
0x1800e893a  mulsd   xmm2, cs:__real@3eb0000000000000
0x1800e8942  movq    r8, xmm2
0x1800e8947  mov     rdx, rsi
0x1800e894a  lea     rcx, aCopyingWs2lfMb; "Copying %ws (%.2lf MB)"
0x1800e8951  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e8956  jmp     short loc_1800E8972
0x1800e8958  add     r8, 3FFh
0x1800e895f  shr     r8, 0Ah
0x1800e8963  mov     rdx, rsi
0x1800e8966  lea     rcx, aCopyingWsI64uK; "Copying %ws (%I64u KB)"
0x1800e896d  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e8972  mov     esi, 40000h
0x1800e8977  mov     rdi, rsi
0x1800e897a  cmp     r12d, cs:?g_UserInterruptCount@@3KA; ulong g_UserInterruptCount
0x1800e8981  jnz     loc_1800E8A6D
0x1800e8987  mov     qword ptr [rsp+22C0h+dwCreationDisposition], 0; lpOverlapped
0x1800e8990  lea     r9, [rsp+22C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800e8995  mov     r8d, 2000h; nNumberOfBytesToRead
0x1800e899b  lea     rdx, [rbp+21C0h+Buffer]; lpBuffer
0x1800e89a2  mov     rcx, r15; hFile
0x1800e89a5  call    cs:__imp_ReadFile
0x1800e89ac  nop     dword ptr [rax+rax+00h]
0x1800e89b1  test    eax, eax
0x1800e89b3  jz      short loc_1800E8A29
0x1800e89b5  mov     r9d, [rsp+22C0h+NumberOfBytesRead]
0x1800e89ba  test    r9d, r9d
0x1800e89bd  jz      short loc_1800E8A25
0x1800e89bf  mov     rax, [r14]
0x1800e89c2  lea     rcx, [rsp+22C0h+var_2278]
0x1800e89c7  mov     qword ptr [rsp+22C0h+dwCreationDisposition], rcx
0x1800e89cc  lea     r8, [rbp+21C0h+Buffer]
0x1800e89d3  mov     rdx, [rsp+22C0h+var_2270]
0x1800e89d8  mov     rcx, r14
0x1800e89db  mov     rax, [rax+4F0h]
0x1800e89e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e89e7  mov     ebx, eax
0x1800e89e9  test    eax, eax
0x1800e89eb  jnz     loc_1800E8A72
0x1800e89f1  mov     eax, [rsp+22C0h+var_2278]
0x1800e89f5  cmp     eax, [rsp+22C0h+NumberOfBytesRead]
0x1800e89f9  jnz     short loc_1800E8A1E
0x1800e89fb  cmp     rdi, rax
0x1800e89fe  ja      short loc_1800E8A16
0x1800e8a00  lea     rcx, asc_1805B8788; "."
0x1800e8a07  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e8a0c  call    ?FlushCallbacks@@YAXXZ; FlushCallbacks(void)
0x1800e8a11  jmp     loc_1800E8977
0x1800e8a16  sub     rdi, rax
0x1800e8a19  jmp     loc_1800E897A
0x1800e8a1e  mov     ebx, 80070070h
0x1800e8a23  jmp     short loc_1800E8A72
0x1800e8a25  xor     ebx, ebx
0x1800e8a27  jmp     short loc_1800E8A5F
0x1800e8a29  call    cs:__imp_GetLastError
0x1800e8a30  nop     dword ptr [rax+rax+00h]
0x1800e8a35  test    eax, eax
0x1800e8a37  jnz     short loc_1800E8A40
0x1800e8a39  mov     ebx, 80004005h
0x1800e8a3e  jmp     short loc_1800E8A72
0x1800e8a40  call    cs:__imp_GetLastError
0x1800e8a47  nop     dword ptr [rax+rax+00h]
0x1800e8a4c  mov     ebx, eax
0x1800e8a4e  test    eax, eax
0x1800e8a50  jle     short loc_1800E8A5B
0x1800e8a52  movzx   ebx, ax
0x1800e8a55  or      ebx, 80070000h
0x1800e8a5b  test    ebx, ebx
0x1800e8a5d  jnz     short loc_1800E8A72
0x1800e8a5f  lea     rcx, asc_1805BAA38; "\n"
0x1800e8a66  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e8a6b  jmp     short loc_1800E8A88
0x1800e8a6d  mov     ebx, 0D000013Ah
0x1800e8a72  mov     ecx, ebx; int
0x1800e8a74  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x1800e8a79  mov     rdx, rax
0x1800e8a7c  lea     rcx, aUnableToCopyFi; "\nUnable to copy file content, %s\n"
0x1800e8a83  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800e8a88  mov     rax, [r14]
0x1800e8a8b  mov     rdx, [rsp+22C0h+var_2270]
0x1800e8a90  mov     rcx, r14
0x1800e8a93  mov     rax, [rax+4F8h]
0x1800e8a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8a9f  mov     rcx, r15; hObject
0x1800e8aa2  call    cs:__imp_CloseHandle
0x1800e8aa9  nop     dword ptr [rax+rax+00h]
0x1800e8aae  jmp     short loc_1800E8AFC
0x1800e8ab0  call    cs:__imp_GetLastError
0x1800e8ab7  nop     dword ptr [rax+rax+00h]
0x1800e8abc  test    eax, eax
0x1800e8abe  jnz     short loc_1800E8AC7
0x1800e8ac0  mov     ebx, 80004005h
0x1800e8ac5  jmp     short loc_1800E8AE2
0x1800e8ac7  call    cs:__imp_GetLastError
0x1800e8ace  nop     dword ptr [rax+rax+00h]
0x1800e8ad3  mov     ebx, eax
0x1800e8ad5  test    eax, eax
0x1800e8ad7  jle     short loc_1800E8AE2
0x1800e8ad9  movzx   ebx, ax
0x1800e8adc  or      ebx, 80070000h
0x1800e8ae2  mov     ecx, ebx; int
0x1800e8ae4  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x1800e8ae9  mov     r8, rax
0x1800e8aec  mov     rdx, rsi
0x1800e8aef  lea     rcx, aUnableToOpenWs; "Unable to open '%ws', %s\n"
0x1800e8af6  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800e8afb  nop
0x1800e8afc  lea     rcx, [rsp+22C0h+var_2260]
0x1800e8b01  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x1800e8b06  mov     eax, ebx
0x1800e8b08  mov     rcx, [rbp+21C0h+var_40]
0x1800e8b0f  xor     rcx, rsp; StackCookie
0x1800e8b12  call    __security_check_cookie
0x1800e8b17  add     rsp, 2290h
0x1800e8b1e  pop     r15
0x1800e8b20  pop     r14
0x1800e8b22  pop     r12
0x1800e8b24  pop     rdi
0x1800e8b25  pop     rsi
0x1800e8b26  pop     rbx
0x1800e8b27  pop     rbp
0x1800e8b28  retn
```
