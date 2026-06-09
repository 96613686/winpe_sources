# ScGetConsoleFileChecksum(ushort const *,tstring &)

- ea: `0x1400dff70`
- end: `0x1400e01b5`
- name: `?ScGetConsoleFileChecksum@@YA?AVSC@mmcerror@@PEBGAEAVtstring@@@Z`
- size: `581`
- prototype: `mmcerror::SC *__fastcall(mmcerror::SC *, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1400e073c`

## callees

- `0x14000c1d0`
- `0x14000d38c`
- `0x14001d9a0`
- `0x1400412e8`
- `0x140060b78`
- `0x140085178`
- `0x1400dff70`
- `0x1400e9e10`

## import_xrefs

- `msvcrt!_ultow` at `0x1400e0152`
- `msvcrt!_ultow` at `0x1400e0152`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400dffe6`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400e0189`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400dffe6`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400e0189`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400dfff0`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400dfff0`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400dffa9`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400dffa9`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x1400e005e`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x1400e0115`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x1400e005e`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x1400e0115`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400e00aa`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400e00de`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400e00aa`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400e00de`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400e0001`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400e006a`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400e00b6`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400e016a`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400e0001`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400e006a`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400e00b6`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400e016a`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400dffdb`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400dffdb`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400dffbb`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400dffbb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400e0042`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400e0042`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400e0106`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400e0106`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1400e0092`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1400e0092`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e017e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400e017e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
mmcerror::SC *__fastcall ScGetConsoleFileChecksum(mmcerror::SC *a1, const WCHAR *a2, __int64 a3)
{
  __int64 v6; // rax
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
  v6 = ScCheckPointers(v25, a2, 2147942487LL);
  mmcerror::SC::operator=(v23, v6);
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
        goto LABEL_19;
LABEL_18:
      CloseHandle(FileW);
      goto LABEL_19;
    }
    FileSizeHigh = 0;
    FileSize = GetFileSize(FileW, &FileSizeHigh);
    v10 = FileSize;
    if ( FileSizeHigh )
    {
      v11 = (const struct mmcerror::SC *)mmcerror::SC::operator=(v23, 2147942414LL);
      mmcerror::SC::SC(a1, v11);
      goto LABEL_18;
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
        goto LABEL_11;
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
        goto LABEL_17;
      }
      v14 = 2147549183LL;
    }
    else
    {
      v14 = 2147942414LL;
    }
    v15 = (struct mmcerror::SC *)mmcerror::SC::operator=(v23, v14);
LABEL_11:
    v16 = v15;
LABEL_17:
    mmcerror::SC::SC(a1, v16);
    CAutoResourceManagementBase<unsigned short *,CAutoArrayPtr<unsigned short>>::Delete(&v22);
    goto LABEL_18;
  }
  mmcerror::SC::SC(a1, (const struct mmcerror::SC *)v23);
LABEL_19:
  mmcerror::SC::~SC((mmcerror::SC *)v23);
  return a1;
}

```

## disassembly

```asm
0x1400dff70  mov     [rsp-8+arg_18], rbx
0x1400dff75  push    rbp
0x1400dff76  push    rsi
0x1400dff77  push    rdi
0x1400dff78  push    r14
0x1400dff7a  push    r15
0x1400dff7c  lea     rbp, [rsp-37h]
0x1400dff81  sub     rsp, 0C0h
0x1400dff88  mov     rax, cs:__security_cookie
0x1400dff8f  xor     rax, rsp
0x1400dff92  mov     [rbp+57h+var_28], rax
0x1400dff96  mov     r15, r8
0x1400dff99  mov     rbx, rdx
0x1400dff9c  mov     rsi, rcx
0x1400dff9f  mov     [rbp+57h+var_98], rcx
0x1400dffa3  xor     edx, edx
0x1400dffa5  lea     rcx, [rbp+57h+var_90]
0x1400dffa9  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1400dffaf  nop
0x1400dffb0  lea     rdx, aScgetconsolefi; "ScGetConsoleFileChecksum"
0x1400dffb7  lea     rcx, [rbp+57h+var_90]
0x1400dffbb  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1400dffc1  mov     r8d, 80070057h
0x1400dffc7  mov     rdx, rbx
0x1400dffca  lea     rcx, [rbp+57h+var_68]
0x1400dffce  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x1400dffd3  nop
0x1400dffd4  mov     rdx, rax
0x1400dffd7  lea     rcx, [rbp+57h+var_90]
0x1400dffdb  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400dffe1  nop
0x1400dffe2  lea     rcx, [rbp+57h+var_68]
0x1400dffe6  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400dffec  lea     rcx, [rbp+57h+var_90]
0x1400dfff0  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400dfff6  test    al, al
0x1400dfff8  jz      short loc_1400E000C
0x1400dfffa  lea     rdx, [rbp+57h+var_90]
0x1400dfffe  mov     rcx, rsi
0x1400e0001  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1400e0007  jmp     loc_1400E0185
0x1400e000c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400e0010  xor     edx, edx
0x1400e0012  mov     rcx, r15
0x1400e0015  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x1400e001a  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x1400e0023  mov     [rsp+0E0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1400e002b  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1400e0033  xor     r9d, r9d; lpSecurityAttributes
0x1400e0036  mov     edx, 80000000h; dwDesiredAccess
0x1400e003b  lea     r8d, [r9+1]; dwShareMode
0x1400e003f  mov     rcx, rbx; lpFileName
0x1400e0042  call    cs:__imp_CreateFileW
0x1400e0048  mov     rbx, rax
0x1400e004b  mov     [rbp+57h+var_70], rax
0x1400e004f  inc     rax
0x1400e0052  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400e0058  jnz     short loc_1400E0084
0x1400e005a  lea     rcx, [rbp+57h+var_90]
0x1400e005e  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x1400e0064  mov     rdx, rax
0x1400e0067  mov     rcx, rsi
0x1400e006a  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1400e0070  nop
0x1400e0071  lea     rax, [rbx-1]
0x1400e0075  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400e0079  ja      loc_1400E0185
0x1400e007f  jmp     loc_1400E017B
0x1400e0084  mov     [rbp+57h+FileSizeHigh], 0
0x1400e008b  lea     rdx, [rbp+57h+FileSizeHigh]; lpFileSizeHigh
0x1400e008f  mov     rcx, rbx; hFile
0x1400e0092  call    cs:__imp_GetFileSize
0x1400e0098  mov     r14d, eax
0x1400e009b  cmp     [rbp+57h+FileSizeHigh], 0
0x1400e009f  jz      short loc_1400E00C1
0x1400e00a1  mov     edx, 8007000Eh
0x1400e00a6  lea     rcx, [rbp+57h+var_90]
0x1400e00aa  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1400e00b0  mov     rdx, rax
0x1400e00b3  mov     rcx, rsi
0x1400e00b6  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1400e00bc  jmp     loc_1400E017B
0x1400e00c1  mov     rcx, r14; unsigned __int64
0x1400e00c4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400e00c9  mov     rdi, rax
0x1400e00cc  mov     [rbp+57h+var_98], rax
0x1400e00d0  test    rax, rax
0x1400e00d3  jnz     short loc_1400E00E9
0x1400e00d5  mov     edx, 8007000Eh
0x1400e00da  lea     rcx, [rbp+57h+var_90]
0x1400e00de  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1400e00e4  mov     rdx, rax
0x1400e00e7  jmp     short loc_1400E0167
0x1400e00e9  mov     [rbp+57h+NumberOfBytesRead], 0
0x1400e00f0  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOverlapped
0x1400e00f9  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400e00fd  mov     r8d, r14d; nNumberOfBytesToRead
0x1400e0100  mov     rdx, rdi; lpBuffer
0x1400e0103  mov     rcx, rbx; hFile
0x1400e0106  call    cs:__imp_ReadFile
0x1400e010c  cmp     eax, 1
0x1400e010f  jz      short loc_1400E011D
0x1400e0111  lea     rcx, [rbp+57h+var_90]
0x1400e0115  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x1400e011b  jmp     short loc_1400E00E4
0x1400e011d  cmp     [rbp+57h+NumberOfBytesRead], r14d
0x1400e0121  jz      short loc_1400E012A
0x1400e0123  mov     edx, 8000FFFFh
0x1400e0128  jmp     short loc_1400E00DA
0x1400e012a  mov     r8d, r14d
0x1400e012d  mov     rdx, rdi
0x1400e0130  xor     ecx, ecx
0x1400e0132  call    crc32
0x1400e0137  xorps   xmm0, xmm0
0x1400e013a  xor     ecx, ecx
0x1400e013c  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1400e0140  movups  [rbp+57h+var_40], xmm0
0x1400e0144  mov     [rbp+57h+var_30], rcx
0x1400e0148  lea     r8d, [rcx+0Ah]; Radix
0x1400e014c  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1400e0150  mov     ecx, eax; Value
0x1400e0152  call    cs:__imp__ultow
0x1400e0158  mov     rdx, rax
0x1400e015b  mov     rcx, r15
0x1400e015e  call    ??4tstring@@QEAAAEAV0@PEBG@Z; tstring::operator=(ushort const *)
0x1400e0163  lea     rdx, [rbp+57h+var_90]
0x1400e0167  mov     rcx, rsi
0x1400e016a  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1400e0170  nop
0x1400e0171  lea     rcx, [rbp+57h+var_98]
0x1400e0175  call    ?Delete@?$CAutoResourceManagementBase@PEAGV?$CAutoArrayPtr@G@@@@QEAAXXZ; CAutoResourceManagementBase<ushort *,CAutoArrayPtr<ushort>>::Delete(void)
0x1400e017a  nop
0x1400e017b  mov     rcx, rbx; hObject
0x1400e017e  call    cs:__imp_CloseHandle
0x1400e0184  nop
0x1400e0185  lea     rcx, [rbp+57h+var_90]
0x1400e0189  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400e018f  mov     rax, rsi
0x1400e0192  mov     rcx, [rbp+57h+var_28]
0x1400e0196  xor     rcx, rsp; StackCookie
0x1400e0199  call    __security_check_cookie
0x1400e019e  mov     rbx, [rsp+0E0h+arg_18]
0x1400e01a6  add     rsp, 0C0h
0x1400e01ad  pop     r15
0x1400e01af  pop     r14
0x1400e01b1  pop     rdi
0x1400e01b2  pop     rsi
0x1400e01b3  pop     rbp
0x1400e01b4  retn
```
