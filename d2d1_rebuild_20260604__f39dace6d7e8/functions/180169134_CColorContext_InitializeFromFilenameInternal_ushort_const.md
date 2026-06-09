# CColorContext::InitializeFromFilenameInternal(ushort const *)

- ea: `0x180169134`
- end: `0x1801692b6`
- name: `?InitializeFromFilenameInternal@CColorContext@@IEAAJPEBG@Z`
- size: `386`
- prototype: `__int64 __fastcall(CColorContext *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18024c720`

## callees

- `0x18001fd58`
- `0x180168ed4`
- `0x180169134`
- `0x1801692c0`
- `0x1801d3c04`
- `0x1801d5018`
- `0x1801d506c`
- `0x18025b100`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180169164`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180169175`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180169164`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180169175`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18016925c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18016925c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18016923f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18016923f`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180169209`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180169209`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801691dc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801691dc`

## pseudocode

```c
__int64 __fastcall CColorContext::InitializeFromFilenameInternal(CColorContext *this, unsigned __int16 *a2)
{
  unsigned __int16 *v2; // rsi
  unsigned int v4; // edx
  unsigned __int64 v5; // rdx
  int ColorDirectory; // edi
  HANDLE FileW; // rax
  void *v8; // rsi
  int LastErrorAsFailHr; // eax
  unsigned int v10; // ebx
  LPVOID *v12; // r14
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-248h] BYREF
  unsigned __int16 v14[264]; // [rsp+50h] [rbp-238h] BYREF

  v2 = a2;
  if ( !wcschr(a2, 0x3Au) && !wcschr(v2, 0x5Cu) )
  {
    ColorDirectory = CColorContext::GetColorDirectory(v14, v4);
    if ( ColorDirectory < 0 )
      goto LABEL_4;
    ColorDirectory = StringCchCatW(v14, v5, v2);
    if ( ColorDirectory < 0 )
      goto LABEL_4;
    v2 = v14;
  }
  FileW = CreateFileW(v2, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v8 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v12 = (LPVOID *)((char *)this + 48);
    NumberOfBytesRead = GetFileSize(FileW, 0);
    ColorDirectory = CArray<unsigned char,CDefaultTraits<unsigned char>,CDefaultAllocator>::Resize(
                       (char *)this + 48,
                       NumberOfBytesRead);
    if ( ColorDirectory >= 0
      && (!ReadFile(v8, *v12, *((_DWORD *)this + 14), &NumberOfBytesRead, 0)
       || *((_DWORD *)this + 14) != NumberOfBytesRead) )
    {
      ColorDirectory = GetLastErrorAsFailHr();
    }
    CloseHandle(v8);
    if ( ColorDirectory >= 0 )
    {
      ColorDirectory = CColorContext::InitHeader(this, (const unsigned __int8 *)*v12, *((_DWORD *)this + 14));
      if ( ColorDirectory >= 0 )
      {
        *((_QWORD *)this + 4) = *v12;
        *((_DWORD *)this + 10) = *((_DWORD *)this + 14);
        return (unsigned int)ColorDirectory;
      }
    }
LABEL_4:
    DoStackCapture(ColorDirectory);
    return (unsigned int)ColorDirectory;
  }
  LastErrorAsFailHr = GetLastErrorAsFailHr();
  v10 = LastErrorAsFailHr;
  if ( LastErrorAsFailHr < 0 )
    DoStackCapture(LastErrorAsFailHr);
  return v10;
}

```

## disassembly

```asm
0x180169134  mov     [rsp+arg_10], rbx
0x180169139  push    rsi
0x18016913a  push    rdi
0x18016913b  push    r14
0x18016913d  sub     rsp, 270h
0x180169144  mov     rax, cs:__security_cookie
0x18016914b  xor     rax, rsp
0x18016914e  mov     [rsp+288h+var_28], rax
0x180169156  mov     rsi, rdx
0x180169159  mov     rbx, rcx
0x18016915c  mov     rcx, rsi; Str
0x18016915f  mov     edx, 3Ah ; ':'; Ch
0x180169164  call    cs:__imp_wcschr
0x18016916a  test    rax, rax
0x18016916d  jnz     short loc_1801691B4
0x18016916f  lea     edx, [rax+5Ch]; Ch
0x180169172  mov     rcx, rsi; Str
0x180169175  call    cs:__imp_wcschr
0x18016917b  test    rax, rax
0x18016917e  jnz     short loc_1801691B4
0x180169180  lea     rcx, [rsp+288h+var_238]; unsigned __int16 *
0x180169185  call    ?GetColorDirectory@CColorContext@@KAJPEAGI@Z; CColorContext::GetColorDirectory(ushort *,uint)
0x18016918a  mov     edi, eax
0x18016918c  test    eax, eax
0x18016918e  jns     short loc_18016919C
0x180169190  mov     ecx, edi; int
0x180169192  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180169197  jmp     loc_180169290
0x18016919c  mov     r8, rsi; unsigned __int16 *
0x18016919f  lea     rcx, [rsp+288h+var_238]; unsigned __int16 *
0x1801691a4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801691a9  mov     edi, eax
0x1801691ab  test    eax, eax
0x1801691ad  js      short loc_180169190
0x1801691af  lea     rsi, [rsp+288h+var_238]
0x1801691b4  xor     r9d, r9d; lpSecurityAttributes
0x1801691b7  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x1801691c0  mov     [rsp+288h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x1801691c8  mov     edx, 80000000h; dwDesiredAccess
0x1801691cd  mov     rcx, rsi; lpFileName
0x1801691d0  mov     [rsp+288h+dwCreationDisposition], 3; dwCreationDisposition
0x1801691d8  lea     r8d, [r9+1]; dwShareMode
0x1801691dc  call    cs:__imp_CreateFileW
0x1801691e2  mov     rsi, rax
0x1801691e5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801691e9  jnz     short loc_180169204
0x1801691eb  call    ?GetLastErrorAsFailHr@@YAJXZ; GetLastErrorAsFailHr(void)
0x1801691f0  mov     ebx, eax
0x1801691f2  test    eax, eax
0x1801691f4  jns     short loc_1801691FD
0x1801691f6  mov     ecx, eax; int
0x1801691f8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801691fd  mov     eax, ebx
0x1801691ff  jmp     loc_180169292
0x180169204  xor     edx, edx; lpFileSizeHigh
0x180169206  mov     rcx, rsi; hFile
0x180169209  call    cs:__imp_GetFileSize
0x18016920f  lea     r14, [rbx+30h]
0x180169213  mov     [rsp+288h+NumberOfBytesRead], eax
0x180169217  mov     edx, eax
0x180169219  mov     rcx, r14
0x18016921c  call    ?Resize@?$CArray@EV?$CDefaultTraits@E@@VCDefaultAllocator@@@@QEAAJI@Z; CArray<uchar,CDefaultTraits<uchar>,CDefaultAllocator>::Resize(uint)
0x180169221  mov     edi, eax
0x180169223  test    eax, eax
0x180169225  js      short loc_180169259
0x180169227  mov     r8d, [rbx+38h]; nNumberOfBytesToRead
0x18016922b  lea     r9, [rsp+288h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180169230  mov     rdx, [r14]; lpBuffer
0x180169233  mov     rcx, rsi; hFile
0x180169236  mov     qword ptr [rsp+288h+dwCreationDisposition], 0; lpOverlapped
0x18016923f  call    cs:__imp_ReadFile
0x180169245  test    eax, eax
0x180169247  jz      short loc_180169252
0x180169249  mov     eax, [rsp+288h+NumberOfBytesRead]
0x18016924d  cmp     [rbx+38h], eax
0x180169250  jz      short loc_180169259
0x180169252  call    ?GetLastErrorAsFailHr@@YAJXZ; GetLastErrorAsFailHr(void)
0x180169257  mov     edi, eax
0x180169259  mov     rcx, rsi; hObject
0x18016925c  call    cs:__imp_CloseHandle
0x180169262  test    edi, edi
0x180169264  js      loc_180169190
0x18016926a  mov     r8d, [rbx+38h]; unsigned int
0x18016926e  mov     rcx, rbx; this
0x180169271  mov     rdx, [r14]; unsigned __int8 *
0x180169274  call    ?InitHeader@CColorContext@@IEAAJPEBEI@Z; CColorContext::InitHeader(uchar const *,uint)
0x180169279  mov     edi, eax
0x18016927b  test    eax, eax
0x18016927d  js      loc_180169190
0x180169283  mov     rax, [r14]
0x180169286  mov     [rbx+20h], rax
0x18016928a  mov     eax, [rbx+38h]
0x18016928d  mov     [rbx+28h], eax
0x180169290  mov     eax, edi
0x180169292  mov     rcx, [rsp+288h+var_28]
0x18016929a  xor     rcx, rsp; StackCookie
0x18016929d  call    __security_check_cookie
0x1801692a2  mov     rbx, [rsp+288h+arg_10]
0x1801692aa  add     rsp, 270h
0x1801692b1  pop     r14
0x1801692b3  pop     rdi
0x1801692b4  pop     rsi
0x1801692b5  retn
```
