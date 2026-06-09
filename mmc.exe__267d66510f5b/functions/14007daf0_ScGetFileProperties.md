# ScGetFileProperties

- ea: `0x14007daf0`
- end: `0x14007dc3b`
- name: `ScGetFileProperties`
- size: `331`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140030a94`

## callees

- `0x140026d20`
- `0x14007daf0`

## import_xrefs

- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14007db64`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14007db64`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14007db6d`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14007db6d`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14007db1d`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14007db1d`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x14007dbed`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x14007dc13`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x14007dbed`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x14007dc13`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14007db58`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14007db58`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14007db35`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14007db35`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x14007dc06`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x14007dc06`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14007dba2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14007dbdb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14007dba2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14007dbdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007dc1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007dc1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
mmcerror::SC *__fastcall ScGetFileProperties(
        mmcerror::SC *a1,
        const WCHAR *a2,
        bool *a3,
        struct _FILETIME *a4,
        __int64 a5,
        struct _FILETIME *lpLastWriteTime)
{
  __int64 v10; // rax
  char *FileW; // rdi
  _BYTE v13[32]; // [rsp+40h] [rbp-38h] BYREF

  mmcerror::SC::SC(a1, 0);
  mmcerror::SC::SetFunctionName(a1, L"ScGetFileProperties");
  v10 = ScCheckPointers(v13, a2, a3, 2147942487LL);
  mmcerror::SC::operator=(a1, v10);
  mmcerror::SC::~SC((mmcerror::SC *)v13);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(a1) )
  {
    FileW = (char *)CreateFileW(a2, 0x40000000u, 0, 0, 3u, 0x80u, 0);
    *a3 = FileW + 1 == 0;
    if ( FileW == (char *)-1LL && (FileW = (char *)CreateFileW(a2, 0, 0, 0, 3u, 0x80u, 0), FileW == (char *)-1LL) )
    {
      mmcerror::SC::FromLastError(a1);
    }
    else
    {
      if ( !GetFileTime(FileW, a4, 0, lpLastWriteTime) )
        mmcerror::SC::FromLastError(a1);
      CloseHandle(FileW);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14007daf0  mov     rax, rsp
0x14007daf3  mov     [rax+10h], rbx
0x14007daf7  mov     [rax+18h], rbp
0x14007dafb  mov     [rax+8], rcx
0x14007daff  push    rsi
0x14007db00  push    rdi
0x14007db01  push    r14
0x14007db03  sub     rsp, 60h
0x14007db07  mov     rbp, r9
0x14007db0a  mov     r14, r8
0x14007db0d  mov     rsi, rdx
0x14007db10  mov     rbx, rcx
0x14007db13  mov     edi, 1
0x14007db18  mov     [rax+28h], edi
0x14007db1b  xor     edx, edx
0x14007db1d  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x14007db23  nop
0x14007db24  mov     [rsp+78h+arg_20], edi
0x14007db2b  lea     rdx, aScgetfileprope; "ScGetFileProperties"
0x14007db32  mov     rcx, rbx
0x14007db35  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14007db3b  mov     r9d, 80070057h
0x14007db41  mov     r8, r14
0x14007db44  mov     rdx, rsi
0x14007db47  lea     rcx, [rsp+78h+var_38]
0x14007db4c  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBX0J@Z; ScCheckPointers(void const *,void const *,long)
0x14007db51  nop
0x14007db52  mov     rdx, rax
0x14007db55  mov     rcx, rbx
0x14007db58  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14007db5e  nop
0x14007db5f  lea     rcx, [rsp+78h+var_38]
0x14007db64  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14007db6a  mov     rcx, rbx
0x14007db6d  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x14007db73  test    al, al
0x14007db75  jnz     loc_14007DC23
0x14007db7b  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x14007db84  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14007db8c  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x14007db94  xor     r9d, r9d; lpSecurityAttributes
0x14007db97  xor     r8d, r8d; dwShareMode
0x14007db9a  mov     edx, 40000000h; dwDesiredAccess
0x14007db9f  mov     rcx, rsi; lpFileName
0x14007dba2  call    cs:__imp_CreateFileW
0x14007dba8  mov     rdi, rax
0x14007dbab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007dbaf  setz    cl
0x14007dbb2  mov     [r14], cl
0x14007dbb5  jnz     short loc_14007DBF5
0x14007dbb7  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x14007dbc0  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14007dbc8  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x14007dbd0  xor     r9d, r9d; lpSecurityAttributes
0x14007dbd3  xor     r8d, r8d; dwShareMode
0x14007dbd6  xor     edx, edx; dwDesiredAccess
0x14007dbd8  mov     rcx, rsi; lpFileName
0x14007dbdb  call    cs:__imp_CreateFileW
0x14007dbe1  mov     rdi, rax
0x14007dbe4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007dbe8  jnz     short loc_14007DBF5
0x14007dbea  mov     rcx, rbx
0x14007dbed  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x14007dbf3  jmp     short loc_14007DC23
0x14007dbf5  mov     r9, [rsp+78h+lpLastWriteTime]; lpLastWriteTime
0x14007dbfd  xor     r8d, r8d; lpLastAccessTime
0x14007dc00  mov     rdx, rbp; lpCreationTime
0x14007dc03  mov     rcx, rdi; hFile
0x14007dc06  call    cs:__imp_GetFileTime
0x14007dc0c  test    eax, eax
0x14007dc0e  jnz     short loc_14007DC19
0x14007dc10  mov     rcx, rbx
0x14007dc13  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x14007dc19  mov     rcx, rdi; hObject
0x14007dc1c  call    cs:__imp_CloseHandle
0x14007dc22  nop
0x14007dc23  mov     rax, rbx
0x14007dc26  lea     r11, [rsp+78h+var_18]
0x14007dc2b  mov     rbx, [r11+28h]
0x14007dc2f  mov     rbp, [r11+30h]
0x14007dc33  mov     rsp, r11
0x14007dc36  pop     r14
0x14007dc38  pop     rdi
0x14007dc39  pop     rsi
0x14007dc3a  retn
```
