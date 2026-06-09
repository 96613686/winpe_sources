# CPackage::GetFileContents(tagFORMATETC const *,tagSTGMEDIUM *)

- ea: `0x18000882c`
- end: `0x1800089f2`
- name: `?GetFileContents@CPackage@@IEAAJPEBUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(CPackage *__hidden this, const struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800049f0`

## callees

- `0x18000774c`
- `0x18000882c`
- `0x18000aa50`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000894d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000894d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800089bd`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180008869`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180008869`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000893e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000893e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180008979`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180008979`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000899e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000899e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800088f3`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800088f3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800089c7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800089c7`

## pseudocode

```c
__int64 __fastcall CPackage::GetFileContents(CPackage *this, const struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  DWORD tymed; // eax
  union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *p_hBitmap; // r14
  unsigned int StreamOnHGlobal; // esi
  int ShortcutOnStream; // eax
  __int64 result; // rax
  SIZE_T v10; // r15
  HBITMAP v11; // rax
  HBITMAP v12; // r14
  HANDLE FileW; // rax
  void *v14; // rbp
  signed int LastError; // eax
  signed int v16; // ebx
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp+10h] BYREF

  tymed = a2->tymed;
  if ( (tymed & 4) != 0 )
  {
    p_hBitmap = (union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *)&a3->hBitmap;
    a3->tymed = 4;
    NumberOfBytesRead = 0;
    StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, &a3->pstm);
    if ( (StreamOnHGlobal & 0x80000000) != 0 )
    {
LABEL_8:
      (*(void (__fastcall **)(HBITMAP))(*(_QWORD *)p_hBitmap->hBitmap + 16LL))(p_hBitmap->hBitmap);
      p_hBitmap->hBitmap = 0;
      return StreamOnHGlobal;
    }
    if ( *((_DWORD *)this + 26) == 1 )
    {
      ShortcutOnStream = CPackage::CreateShortcutOnStream(this, p_hBitmap->pstm);
    }
    else
    {
      if ( *((_DWORD *)this + 26) != 3 )
        return StreamOnHGlobal;
      ShortcutOnStream = CopyFileToStream(
                           *(LPCWSTR *)(*((_QWORD *)this + 14) + 592LL),
                           p_hBitmap->pstm,
                           &NumberOfBytesRead);
    }
    StreamOnHGlobal = ShortcutOnStream;
    if ( ShortcutOnStream < 0 )
      goto LABEL_8;
    return StreamOnHGlobal;
  }
  if ( (tymed & 1) == 0 )
    return 2147745892LL;
  a3->tymed = 1;
  if ( *((_DWORD *)this + 26) == 1 )
    return 2147745892LL;
  v10 = *(unsigned int *)(*((_QWORD *)this + 14) + 68LL);
  v11 = (HBITMAP)GlobalAlloc(0x40u, v10);
  v12 = v11;
  if ( !v11 )
    return 2147942414LL;
  a3->hBitmap = v11;
  FileW = CreateFileW(*(LPCWSTR *)(*((_QWORD *)this + 14) + 592LL), 0x80000000, 3u, 0, 3u, 0x8000000u, 0);
  v14 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    if ( v16 >= 0 )
      v16 = -2147467259;
  }
  else
  {
    SetFilePointer(FileW, 0, 0, 0);
    NumberOfBytesRead = 0;
    if ( ReadFile(v14, v12, v10, &NumberOfBytesRead, 0) )
    {
      CloseHandle(v14);
      return 0;
    }
    v16 = -2147467259;
  }
  CloseHandle(v14);
  GlobalFree(a3->hBitmap);
  result = (unsigned int)v16;
  a3->hBitmap = 0;
  return result;
}

```

## disassembly

```asm
0x18000882c  mov     [rsp+arg_0], rbx
0x180008831  mov     [rsp+arg_10], rbp
0x180008836  push    rsi
0x180008837  push    r14
0x180008839  push    r15
0x18000883b  sub     rsp, 40h
0x18000883f  mov     eax, [rdx+18h]
0x180008842  mov     rsi, r8
0x180008845  mov     rbx, rcx
0x180008848  test    al, 4
0x18000884a  jz      short loc_1800088CA
0x18000884c  lea     r14, [r8+8]
0x180008850  mov     dword ptr [r8], 4
0x180008857  mov     r8, r14; ppstm
0x18000885a  mov     [rsp+58h+NumberOfBytesRead], 0
0x180008862  mov     edx, 1; fDeleteOnRelease
0x180008867  xor     ecx, ecx; hGlobal
0x180008869  call    cs:__imp_CreateStreamOnHGlobal
0x18000886f  mov     esi, eax
0x180008871  test    eax, eax
0x180008873  js      short loc_1800088AD
0x180008875  mov     edx, [rbx+68h]
0x180008878  sub     edx, 1
0x18000887b  jz      short loc_18000889C
0x18000887d  cmp     edx, 2
0x180008880  jnz     short loc_1800088C3
0x180008882  mov     rcx, [rbx+70h]
0x180008886  lea     r8, [rsp+58h+NumberOfBytesRead]; unsigned int *
0x18000888b  mov     rdx, [r14]; struct IStream *
0x18000888e  mov     rcx, [rcx+250h]; lpFileName
0x180008895  call    ?CopyFileToStream@@YAJPEBGPEAUIStream@@PEAK@Z; CopyFileToStream(ushort const *,IStream *,ulong *)
0x18000889a  jmp     short loc_1800088A7
0x18000889c  mov     rdx, [r14]; struct IStream *
0x18000889f  mov     rcx, rbx; this
0x1800088a2  call    ?CreateShortcutOnStream@CPackage@@IEAAJPEAUIStream@@@Z; CPackage::CreateShortcutOnStream(IStream *)
0x1800088a7  mov     esi, eax
0x1800088a9  test    eax, eax
0x1800088ab  jns     short loc_1800088C3
0x1800088ad  mov     rcx, [r14]
0x1800088b0  mov     rax, [rcx]
0x1800088b3  mov     rax, [rax+10h]
0x1800088b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088bc  mov     qword ptr [r14], 0
0x1800088c3  mov     eax, esi
0x1800088c5  jmp     loc_1800089DE
0x1800088ca  test    al, 1
0x1800088cc  jz      loc_1800089D9
0x1800088d2  mov     dword ptr [r8], 1
0x1800088d9  cmp     dword ptr [rcx+68h], 1
0x1800088dd  jz      loc_1800089D9
0x1800088e3  mov     rax, [rcx+70h]
0x1800088e7  mov     ecx, 40h ; '@'; uFlags
0x1800088ec  mov     r15d, [rax+44h]
0x1800088f0  mov     edx, r15d; dwBytes
0x1800088f3  call    cs:__imp_GlobalAlloc
0x1800088f9  mov     r14, rax
0x1800088fc  test    rax, rax
0x1800088ff  jnz     short loc_18000890B
0x180008901  mov     eax, 8007000Eh
0x180008906  jmp     loc_1800089DE
0x18000890b  mov     [rsi+8], r14
0x18000890f  mov     r8d, 3; dwShareMode
0x180008915  mov     rcx, [rbx+70h]
0x180008919  xor     r9d, r9d; lpSecurityAttributes
0x18000891c  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180008925  mov     edx, 80000000h; dwDesiredAccess
0x18000892a  mov     [rsp+58h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180008932  mov     [rsp+58h+dwCreationDisposition], r8d; dwCreationDisposition
0x180008937  mov     rcx, [rcx+250h]; lpFileName
0x18000893e  call    cs:__imp_CreateFileW
0x180008944  mov     rbp, rax
0x180008947  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000894b  jnz     short loc_18000896E
0x18000894d  call    cs:__imp_GetLastError
0x180008953  mov     ebx, eax
0x180008955  test    eax, eax
0x180008957  jle     short loc_180008962
0x180008959  movzx   ebx, ax
0x18000895c  or      ebx, 80070000h
0x180008962  test    ebx, ebx
0x180008964  mov     eax, 80004005h
0x180008969  cmovns  ebx, eax
0x18000896c  jmp     short loc_1800089BA
0x18000896e  xor     r9d, r9d; dwMoveMethod
0x180008971  xor     r8d, r8d; lpDistanceToMoveHigh
0x180008974  xor     edx, edx; lDistanceToMove
0x180008976  mov     rcx, rbp; hFile
0x180008979  call    cs:__imp_SetFilePointer
0x18000897f  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180008984  mov     [rsp+58h+NumberOfBytesRead], 0
0x18000898c  mov     r8d, r15d; nNumberOfBytesToRead
0x18000898f  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOverlapped
0x180008998  mov     rdx, r14; lpBuffer
0x18000899b  mov     rcx, rbp; hFile
0x18000899e  call    cs:__imp_ReadFile
0x1800089a4  test    eax, eax
0x1800089a6  jz      short loc_1800089B5
0x1800089a8  mov     rcx, rbp; hObject
0x1800089ab  call    cs:__imp_CloseHandle
0x1800089b1  xor     eax, eax
0x1800089b3  jmp     short loc_1800089DE
0x1800089b5  mov     ebx, 80004005h
0x1800089ba  mov     rcx, rbp; hObject
0x1800089bd  call    cs:__imp_CloseHandle
0x1800089c3  mov     rcx, [rsi+8]; hMem
0x1800089c7  call    cs:__imp_GlobalFree
0x1800089cd  mov     eax, ebx
0x1800089cf  mov     qword ptr [rsi+8], 0
0x1800089d7  jmp     short loc_1800089DE
0x1800089d9  mov     eax, 80040064h
0x1800089de  mov     rbx, [rsp+58h+arg_0]
0x1800089e3  mov     rbp, [rsp+58h+arg_10]
0x1800089e8  add     rsp, 40h
0x1800089ec  pop     r15
0x1800089ee  pop     r14
0x1800089f0  pop     rsi
0x1800089f1  retn
```
