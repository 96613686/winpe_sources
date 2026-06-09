# ScGetConsoleFileChecksum(ushort const *,tstring &)

- ea: `0x18004278c`
- end: `0x1800429d7`
- name: `?ScGetConsoleFileChecksum@@YA?AVSC@mmcerror@@PEBGAEAVtstring@@@Z`
- size: `587`
- prototype: `mmcerror::SC *__fastcall(mmcerror::SC *, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180127778`

## callees

- `0x180014ea8`
- `0x1800183c0`
- `0x18002fca0`
- `0x18004278c`
- `0x180071428`
- `0x1800a4568`
- `0x180134540`

## import_xrefs

- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x180042880`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x180042937`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x180042880`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x180042937`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1800427c5`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1800427ee`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1800427c5`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1800427ee`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800428cc`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180042900`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800428cc`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180042900`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180042823`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18004288c`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800428d8`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18004298c`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180042823`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18004288c`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1800428d8`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x18004298c`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1800427fd`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1800427fd`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1800427d7`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1800427d7`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180042812`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180042812`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180042808`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800429ab`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180042808`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800429ab`
- `msvcrt!_ultow` at `0x180042974`
- `msvcrt!_ultow` at `0x180042974`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800428b4`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800428b4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042864`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180042864`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042928`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042928`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800429a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800429a0`

## pseudocode

```c
mmcerror::SC *__fastcall ScGetConsoleFileChecksum(mmcerror::SC *a1, const WCHAR *a2, __int64 a3)
{
  int v6; // edx
  char *FileW; // rbx
  const struct mmcerror::SC *Error; // rax
  DWORD FileSize; // eax
  DWORD v10; // r14d
  const struct mmcerror::SC *v11; // rax
  void *v12; // rax
  void *v13; // rdi
  __int64 v14; // rdx
  struct mmcerror::SC *v15; // rax
  const struct mmcerror::SC *v16; // rdx
  unsigned int v17; // eax
  wchar_t *v18; // rax
  DWORD FileSizeHigh; // [rsp+40h] [rbp-49h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-45h] BYREF
  mmcerror::SC *v22; // [rsp+48h] [rbp-41h] BYREF
  _BYTE v23[32]; // [rsp+50h] [rbp-39h] BYREF
  char *v24; // [rsp+70h] [rbp-19h]
  _BYTE v25[24]; // [rsp+78h] [rbp-11h] BYREF
  wchar_t Buffer[8]; // [rsp+90h] [rbp+7h] BYREF
  __int128 v27; // [rsp+A0h] [rbp+17h]
  __int64 v28; // [rsp+B0h] [rbp+27h]

  v22 = a1;
  mmcerror::SC::SC((mmcerror::SC *)v23, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v23, L"ScGetConsoleFileChecksum");
  v6 = -2147024809;
  if ( a2 )
    v6 = 0;
  mmcerror::SC::SC((mmcerror::SC *)v25, v6);
  mmcerror::SC::operator=(v23, v25);
  mmcerror::SC::~SC((mmcerror::SC *)v25);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(v23) )
  {
    std::wstring::erase(a3, 0, -1);
    FileW = (char *)CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0, 0);
    v24 = FileW;
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      Error = mmcerror::SC::FromLastError((mmcerror::SC *)v23);
      mmcerror::SC::SC(a1, Error);
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_21;
      goto LABEL_20;
    }
    FileSizeHigh = 0;
    FileSize = GetFileSize(FileW, &FileSizeHigh);
    v10 = FileSize;
    if ( FileSizeHigh )
    {
      v11 = (const struct mmcerror::SC *)mmcerror::SC::operator=(v23, 2147942414LL);
      mmcerror::SC::SC(a1, v11);
LABEL_20:
      CloseHandle(FileW);
      goto LABEL_21;
    }
    v12 = operator new[](FileSize);
    v13 = v12;
    v22 = (mmcerror::SC *)v12;
    if ( v12 )
    {
      NumberOfBytesRead = 0;
      if ( !ReadFile(FileW, v12, v10, &NumberOfBytesRead, 0) )
      {
        v15 = mmcerror::SC::FromLastError((mmcerror::SC *)v23);
        goto LABEL_13;
      }
      if ( NumberOfBytesRead == v10 )
      {
        v17 = crc32(0, v13, v10);
        *(_OWORD *)Buffer = 0;
        v27 = 0;
        v28 = 0;
        v18 = _ultow(v17, Buffer, 10);
        tstring::operator=(a3, v18);
        v16 = (const struct mmcerror::SC *)v23;
        goto LABEL_19;
      }
      v14 = 2147549183LL;
    }
    else
    {
      v14 = 2147942414LL;
    }
    v15 = (struct mmcerror::SC *)mmcerror::SC::operator=(v23, v14);
LABEL_13:
    v16 = v15;
LABEL_19:
    mmcerror::SC::SC(a1, v16);
    CAutoArrayPtr<unsigned char>::~CAutoArrayPtr<unsigned char>(&v22);
    goto LABEL_20;
  }
  mmcerror::SC::SC(a1, (const struct mmcerror::SC *)v23);
LABEL_21:
  mmcerror::SC::~SC((mmcerror::SC *)v23);
  return a1;
}

```

## disassembly

```asm
0x18004278c  mov     [rsp-8+arg_18], rbx
0x180042791  push    rbp
0x180042792  push    rsi
0x180042793  push    rdi
0x180042794  push    r14
0x180042796  push    r15
0x180042798  lea     rbp, [rsp-37h]
0x18004279d  sub     rsp, 0C0h
0x1800427a4  mov     rax, cs:__security_cookie
0x1800427ab  xor     rax, rsp
0x1800427ae  mov     [rbp+57h+var_28], rax
0x1800427b2  mov     r15, r8
0x1800427b5  mov     rbx, rdx
0x1800427b8  mov     rsi, rcx
0x1800427bb  mov     [rbp+57h+var_98], rcx
0x1800427bf  xor     edx, edx
0x1800427c1  lea     rcx, [rbp+57h+var_90]
0x1800427c5  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1800427cb  nop
0x1800427cc  lea     rdx, aScgetconsolefi; "ScGetConsoleFileChecksum"
0x1800427d3  lea     rcx, [rbp+57h+var_90]
0x1800427d7  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1800427dd  mov     edx, 80070057h
0x1800427e2  xor     eax, eax
0x1800427e4  test    rbx, rbx
0x1800427e7  cmovnz  edx, eax
0x1800427ea  lea     rcx, [rbp+57h+var_68]
0x1800427ee  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1800427f4  nop
0x1800427f5  lea     rdx, [rbp+57h+var_68]
0x1800427f9  lea     rcx, [rbp+57h+var_90]
0x1800427fd  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180042803  nop
0x180042804  lea     rcx, [rbp+57h+var_68]
0x180042808  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18004280e  lea     rcx, [rbp+57h+var_90]
0x180042812  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180042818  test    al, al
0x18004281a  jz      short loc_18004282E
0x18004281c  lea     rdx, [rbp+57h+var_90]
0x180042820  mov     rcx, rsi
0x180042823  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x180042829  jmp     loc_1800429A7
0x18004282e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180042832  xor     edx, edx
0x180042834  mov     rcx, r15
0x180042837  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x18004283c  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x180042845  mov     [rsp+0E0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004284d  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180042855  xor     r9d, r9d; lpSecurityAttributes
0x180042858  mov     edx, 80000000h; dwDesiredAccess
0x18004285d  lea     r8d, [r9+1]; dwShareMode
0x180042861  mov     rcx, rbx; lpFileName
0x180042864  call    cs:__imp_CreateFileW
0x18004286a  mov     rbx, rax
0x18004286d  mov     [rbp+57h+var_70], rax
0x180042871  inc     rax
0x180042874  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004287a  jnz     short loc_1800428A6
0x18004287c  lea     rcx, [rbp+57h+var_90]
0x180042880  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x180042886  mov     rdx, rax
0x180042889  mov     rcx, rsi
0x18004288c  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x180042892  nop
0x180042893  lea     rax, [rbx-1]
0x180042897  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004289b  jbe     loc_18004299D
0x1800428a1  jmp     loc_1800429A7
0x1800428a6  mov     [rbp+57h+FileSizeHigh], 0
0x1800428ad  lea     rdx, [rbp+57h+FileSizeHigh]; lpFileSizeHigh
0x1800428b1  mov     rcx, rbx; hFile
0x1800428b4  call    cs:__imp_GetFileSize
0x1800428ba  mov     r14d, eax
0x1800428bd  cmp     [rbp+57h+FileSizeHigh], 0
0x1800428c1  jz      short loc_1800428E3
0x1800428c3  mov     edx, 8007000Eh
0x1800428c8  lea     rcx, [rbp+57h+var_90]
0x1800428cc  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800428d2  mov     rdx, rax
0x1800428d5  mov     rcx, rsi
0x1800428d8  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1800428de  jmp     loc_18004299D
0x1800428e3  mov     rcx, r14; unsigned __int64
0x1800428e6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800428eb  mov     rdi, rax
0x1800428ee  mov     [rbp+57h+var_98], rax
0x1800428f2  test    rax, rax
0x1800428f5  jnz     short loc_18004290B
0x1800428f7  mov     edx, 8007000Eh
0x1800428fc  lea     rcx, [rbp+57h+var_90]
0x180042900  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180042906  mov     rdx, rax
0x180042909  jmp     short loc_180042989
0x18004290b  mov     [rbp+57h+NumberOfBytesRead], 0
0x180042912  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOverlapped
0x18004291b  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004291f  mov     r8d, r14d; nNumberOfBytesToRead
0x180042922  mov     rdx, rdi; lpBuffer
0x180042925  mov     rcx, rbx; hFile
0x180042928  call    cs:__imp_ReadFile
0x18004292e  cmp     eax, 1
0x180042931  jz      short loc_18004293F
0x180042933  lea     rcx, [rbp+57h+var_90]
0x180042937  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x18004293d  jmp     short loc_180042906
0x18004293f  cmp     [rbp+57h+NumberOfBytesRead], r14d
0x180042943  jz      short loc_18004294C
0x180042945  mov     edx, 8000FFFFh
0x18004294a  jmp     short loc_1800428FC
0x18004294c  mov     r8d, r14d
0x18004294f  mov     rdx, rdi
0x180042952  xor     ecx, ecx
0x180042954  call    crc32
0x180042959  xorps   xmm0, xmm0
0x18004295c  xor     ecx, ecx
0x18004295e  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x180042962  movups  [rbp+57h+var_40], xmm0
0x180042966  mov     [rbp+57h+var_30], rcx
0x18004296a  lea     r8d, [rcx+0Ah]; Radix
0x18004296e  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180042972  mov     ecx, eax; Value
0x180042974  call    cs:__imp__ultow
0x18004297a  mov     rdx, rax
0x18004297d  mov     rcx, r15
0x180042980  call    ??4tstring@@QEAAAEAV0@PEBG@Z; tstring::operator=(ushort const *)
0x180042985  lea     rdx, [rbp+57h+var_90]
0x180042989  mov     rcx, rsi
0x18004298c  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x180042992  nop
0x180042993  lea     rcx, [rbp+57h+var_98]
0x180042997  call    ??1?$CAutoArrayPtr@E@@QEAA@XZ; CAutoArrayPtr<uchar>::~CAutoArrayPtr<uchar>(void)
0x18004299c  nop
0x18004299d  mov     rcx, rbx; hObject
0x1800429a0  call    cs:__imp_CloseHandle
0x1800429a6  nop
0x1800429a7  lea     rcx, [rbp+57h+var_90]
0x1800429ab  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1800429b1  mov     rax, rsi
0x1800429b4  mov     rcx, [rbp+57h+var_28]
0x1800429b8  xor     rcx, rsp; StackCookie
0x1800429bb  call    __security_check_cookie
0x1800429c0  mov     rbx, [rsp+0E0h+arg_18]
0x1800429c8  add     rsp, 0C0h
0x1800429cf  pop     r15
0x1800429d1  pop     r14
0x1800429d3  pop     rdi
0x1800429d4  pop     rsi
0x1800429d5  pop     rbp
0x1800429d6  retn
```
