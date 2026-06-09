# CRepositoryPackager::UnPackageFile(void *,ushort const *)

- ea: `0x18003ffd4`
- end: `0x180040184`
- name: `?UnPackageFile@CRepositoryPackager@@AEAAJPEAXPEBG@Z`
- size: `432`
- prototype: `int(CRepositoryPackager *__hidden this, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003fcac`

## callees

- `0x1800012b8`
- `0x180013880`
- `0x180013f90`
- `0x180023bf0`
- `0x18003ec98`
- `0x18003ffd4`
- `0x1800443df`
- `0x180044420`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180040153`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180040153`
- `wbemcomn!GetMemLogObject` at `0x180040107`
- `wbemcomn!GetMemLogObject` at `0x180040107`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180040112`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180040112`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800400d2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800400d2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180040039`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180040039`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800400f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800400f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRepositoryPackager::UnPackageFile(CRepositoryPackager *this, void *a2, const unsigned __int16 *a3)
{
  int v5; // ebx
  int v6; // edi
  unsigned __int16 *v7; // rsi
  HANDLE FileW; // rax
  void *v9; // rdi
  CMemoryLog *MemLogObject; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-258h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-250h] BYREF
  _BYTE v14[4]; // [rsp+50h] [rbp-248h] BYREF
  unsigned __int16 Buffer[262]; // [rsp+54h] [rbp-244h] BYREF
  __int64 v16; // [rsp+260h] [rbp-38h]

  memset_0(v14, 0, 0x214u);
  NumberOfBytesRead = 0;
  v5 = -2147217407;
  if ( !ReadFile(a2, Buffer, 0x210u, &NumberOfBytesRead, 0) || (v6 = 0, NumberOfBytesRead != 528) )
    v6 = -2147217407;
  CFileName::CFileName((CFileName *)&lpFileName);
  v7 = (unsigned __int16 *)lpFileName;
  if ( !lpFileName )
  {
    v5 = -2147217402;
LABEL_11:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v5);
    goto LABEL_12;
  }
  if ( v6 < 0 )
  {
    v5 = v6;
    goto LABEL_11;
  }
  StringCchCopyW((unsigned __int16 *)lpFileName, 0x173u, a3);
  StringCchCatW(v7, 0x173u, L"\\");
  StringCchCatW(v7, 0x173u, Buffer);
  FileW = CreateFileW(v7, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_11;
  v5 = CopyFileW(a2, FileW, (unsigned int)v16);
  CloseHandle(v9);
  if ( v5 < 0 )
    goto LABEL_11;
LABEL_12:
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids, (unsigned int)v5);
  }
  CWin32DefaultArena::WbemMemFree(v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003ffd4  mov     [rsp+arg_0], rbx
0x18003ffd9  mov     [rsp+arg_18], rbp
0x18003ffde  push    rsi
0x18003ffdf  push    rdi
0x18003ffe0  push    r14
0x18003ffe2  sub     rsp, 280h
0x18003ffe9  mov     rax, cs:__security_cookie
0x18003fff0  xor     rax, rsp
0x18003fff3  mov     [rsp+298h+var_28], rax
0x18003fffb  mov     r14, r8
0x18003fffe  mov     rbp, rdx
0x180040001  xor     edx, edx; Val
0x180040003  mov     r8d, 214h; Size
0x180040009  lea     rcx, [rsp+298h+var_248]; void *
0x18004000e  call    memset_0
0x180040013  mov     [rsp+298h+NumberOfBytesRead], 0
0x18004001b  mov     [rsp+298h+lpOverlapped], 0; lpOverlapped
0x180040024  lea     r9, [rsp+298h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180040029  mov     esi, 210h
0x18004002e  mov     r8d, esi; nNumberOfBytesToRead
0x180040031  lea     rdx, [rsp+298h+Buffer]; lpBuffer
0x180040036  mov     rcx, rbp; hFile
0x180040039  call    cs:__imp_ReadFile
0x18004003f  mov     ebx, 80041001h
0x180040044  test    eax, eax
0x180040046  jz      short loc_180040050
0x180040048  xor     edi, edi
0x18004004a  cmp     [rsp+298h+NumberOfBytesRead], esi
0x18004004e  jz      short loc_180040052
0x180040050  mov     edi, ebx
0x180040052  lea     rcx, [rsp+298h+lpFileName]; this
0x180040057  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x18004005c  nop
0x18004005d  mov     rsi, [rsp+298h+lpFileName]
0x180040062  test    rsi, rsi
0x180040065  jnz     short loc_180040071
0x180040067  mov     ebx, 80041006h
0x18004006c  jmp     loc_180040107
0x180040071  test    edi, edi
0x180040073  js      loc_180040105
0x180040079  mov     r8, r14; unsigned __int16 *
0x18004007c  mov     edi, 173h
0x180040081  mov     edx, edi; unsigned __int64
0x180040083  mov     rcx, rsi; unsigned __int16 *
0x180040086  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004008b  lea     r8, asc_18004B0E0; "\\"
0x180040092  mov     edx, edi; unsigned __int64
0x180040094  mov     rcx, rsi; unsigned __int16 *
0x180040097  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004009c  lea     r8, [rsp+298h+Buffer]; unsigned __int16 *
0x1800400a1  mov     edx, edi; unsigned __int64
0x1800400a3  mov     rcx, rsi; unsigned __int16 *
0x1800400a6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800400ab  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x1800400b4  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800400bc  mov     dword ptr [rsp+298h+lpOverlapped], 2; dwCreationDisposition
0x1800400c4  xor     r9d, r9d; lpSecurityAttributes
0x1800400c7  xor     r8d, r8d; dwShareMode
0x1800400ca  mov     edx, 40000000h; dwDesiredAccess
0x1800400cf  mov     rcx, rsi; lpFileName
0x1800400d2  call    cs:__imp_CreateFileW
0x1800400d8  mov     rdi, rax
0x1800400db  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800400df  jz      short loc_180040107
0x1800400e1  mov     r8d, dword ptr [rsp+298h+var_38]; __int64
0x1800400e9  mov     rdx, rax; HANDLE
0x1800400ec  mov     rcx, rbp; hFile
0x1800400ef  call    ?CopyFileW@@YAJPEAX0_J@Z; CopyFileW(void *,void *,__int64)
0x1800400f4  mov     ebx, eax
0x1800400f6  mov     rcx, rdi; hObject
0x1800400f9  call    cs:__imp_CloseHandle
0x1800400ff  test    ebx, ebx
0x180040101  jns     short loc_180040118
0x180040103  jmp     short loc_180040107
0x180040105  mov     ebx, edi
0x180040107  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004010d  mov     edx, ebx
0x18004010f  mov     rcx, rax
0x180040112  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180040118  lea     rax, WPP_GLOBAL_Control
0x18004011f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040126  cmp     rcx, rax
0x180040129  jz      short loc_180040150
0x18004012b  test    byte ptr [rcx+1Ch], 1
0x18004012f  jz      short loc_180040150
0x180040131  cmp     byte ptr [rcx+19h], 2
0x180040135  jb      short loc_180040150
0x180040137  mov     edx, 1Dh
0x18004013c  mov     r9d, ebx
0x18004013f  lea     r8, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids
0x180040146  mov     rcx, [rcx+10h]
0x18004014a  call    WPP_SF_d
0x18004014f  nop
0x180040150  mov     rcx, rsi
0x180040153  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180040159  nop
0x18004015a  mov     eax, ebx
0x18004015c  mov     rcx, [rsp+298h+var_28]
0x180040164  xor     rcx, rsp; StackCookie
0x180040167  call    __security_check_cookie
0x18004016c  lea     r11, [rsp+298h+var_18]
0x180040174  mov     rbx, [r11+20h]
0x180040178  mov     rbp, [r11+38h]
0x18004017c  mov     rsp, r11
0x18004017f  pop     r14
0x180040181  pop     rdi
0x180040182  pop     rsi
0x180040183  retn
```
