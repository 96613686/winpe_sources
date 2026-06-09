# ExpandVolume(void *,ushort const *)

- ea: `0x1800296d4`
- end: `0x180029944`
- name: `?ExpandVolume@@YA_NPEAXPEBG@Z`
- size: `624`
- prototype: `char __fastcall(void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180027e8c`

## callees

- `0x180002690`
- `0x180006e10`
- `0x180008fac`
- `0x18002523c`
- `0x180029318`
- `0x1800296d4`
- `0x18002a550`
- `0x18002a5ac`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800297a6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800297a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029902`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029902`
- `ntdll!NtQueryVolumeInformationFile` at `0x180029831`
- `ntdll!NtQueryVolumeInformationFile` at `0x180029831`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800298c4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800298c4`

## string_xrefs

- `0x1800297ea`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18002984e`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x1800298e1`: `onecore\vm\compute\shared\storage\diskutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall ExpandVolume(void *a1, const unsigned __int16 *a2)
{
  char v3; // si
  __int64 v4; // r14
  unsigned __int64 v5; // r8
  LPCWSTR *v6; // rax
  __int64 v7; // rdx
  LPCWSTR *v8; // rcx
  const WCHAR *v9; // rcx
  char *FileW; // rax
  char *v11; // rbx
  LPCWSTR *v12; // rdx
  LPCWSTR *v13; // rdi
  unsigned int v14; // eax
  __int64 v15; // rcx
  LPCWSTR *v16; // rdi
  unsigned int v17; // eax
  __int64 v19; // [rsp+40h] [rbp-39h]
  LPCWSTR lpFileName[2]; // [rsp+48h] [rbp-31h] BYREF
  __int64 v21; // [rsp+58h] [rbp-21h]
  unsigned __int64 v22; // [rsp+60h] [rbp-19h]
  DWORD BytesReturned; // [rsp+68h] [rbp-11h] BYREF
  __int64 InBuffer; // [rsp+70h] [rbp-9h] BYREF
  __int128 FsInformation; // [rsp+78h] [rbp-1h] BYREF
  __int128 v26; // [rsp+88h] [rbp+Fh]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v3 = 0;
  v4 = ExpandPartition(a1);
  *(_OWORD *)lpFileName = 0;
  v21 = 0;
  v22 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  std::wstring::_Construct<1,unsigned short const *>((__int64)lpFileName, a2, v5);
  while ( v21 )
  {
    v6 = lpFileName;
    if ( v22 > 7 )
      v6 = (LPCWSTR *)lpFileName[0];
    if ( *((_WORD *)v6 + v21 - 1) != 92 )
      break;
    v7 = --v21;
    v8 = lpFileName;
    if ( v22 > 7 )
      v8 = (LPCWSTR *)lpFileName[0];
    *((_WORD *)v8 + v7) = 0;
  }
  v9 = (const WCHAR *)lpFileName;
  if ( v22 > 7 )
    v9 = lpFileName[0];
  FileW = (char *)CreateFileW(v9, 0xC0000000, 3u, 0, 3u, 0x2000000u, 0);
  v11 = FileW;
  HIWORD(v19) = HIWORD(FileW);
  v12 = lpFileName;
  if ( v22 > 7 )
    v12 = (LPCWSTR *)lpFileName[0];
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x33E,
    (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
    (const char *)((unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL),
    (bool)"%ls",
    (const char *)v12);
  FsInformation = 0;
  v26 = 0;
  IoStatusBlock = 0;
  v13 = lpFileName;
  if ( v22 > 7 )
    v13 = (LPCWSTR *)lpFileName[0];
  v14 = NtQueryVolumeInformationFile(v11, &IoStatusBlock, &FsInformation, 0x20u, FileFsFullSizeInformation);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x347,
    (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
    (const char *)v14,
    (int)"%ls",
    (const char *)v13);
  v15 = v4 / (unsigned int)(HIDWORD(v26) * DWORD2(v26));
  if ( (__int64)FsInformation + 1 < v15 )
  {
    InBuffer = v15 * DWORD2(v26);
    BytesReturned = 0;
    v16 = lpFileName;
    if ( v22 > 7 )
      v16 = (LPCWSTR *)lpFileName[0];
    v17 = DeviceIoControl(v11, 0x900F0u, &InBuffer, 8u, 0, 0, &BytesReturned, 0);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x360,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      (const char *)v17,
      (__int64)"%ls",
      (const char *)v16);
    v3 = 1;
  }
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v11);
  std::wstring::~wstring((char **)lpFileName);
  return v3;
}

```

## disassembly

```asm
0x1800296d4  mov     [rsp-8+arg_10], rbx
0x1800296d9  mov     [rsp-8+arg_18], rsi
0x1800296de  push    rbp
0x1800296df  push    rdi
0x1800296e0  push    r13
0x1800296e2  push    r14
0x1800296e4  push    r15
0x1800296e6  lea     rbp, [rsp-37h]
0x1800296eb  sub     rsp, 0B0h
0x1800296f2  mov     rax, cs:__security_cookie
0x1800296f9  xor     rax, rsp
0x1800296fc  mov     [rbp+57h+var_28], rax
0x180029700  mov     rbx, rdx
0x180029703  xor     r15d, r15d
0x180029706  mov     sil, r15b
0x180029709  call    ?ExpandPartition@@YA_JPEAX@Z; ExpandPartition(void *)
0x18002970e  mov     r14, rax
0x180029711  xorps   xmm0, xmm0
0x180029714  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x180029718  mov     [rbp+57h+var_78], r15
0x18002971c  mov     [rbp+57h+var_70], r15
0x180029720  or      r8, 0FFFFFFFFFFFFFFFFh
0x180029724  inc     r8
0x180029727  cmp     [rbx+r8*2], r15w
0x18002972c  jnz     short loc_180029724
0x18002972e  mov     rdx, rbx
0x180029731  lea     rcx, [rbp+57h+lpFileName]
0x180029735  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002973a  nop
0x18002973b  mov     r8, [rbp+57h+var_70]
0x18002973f  mov     r9, [rbp+57h+lpFileName]
0x180029743  mov     rdx, [rbp+57h+var_78]
0x180029747  test    rdx, rdx
0x18002974a  jz      short loc_18002977A
0x18002974c  lea     rax, [rbp+57h+lpFileName]
0x180029750  cmp     r8, 7
0x180029754  cmova   rax, r9
0x180029758  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x18002975e  jnz     short loc_18002977A
0x180029760  dec     rdx
0x180029763  mov     [rbp+57h+var_78], rdx
0x180029767  lea     rcx, [rbp+57h+lpFileName]
0x18002976b  cmp     r8, 7
0x18002976f  cmova   rcx, r9
0x180029773  mov     [rcx+rdx*2], r15w
0x180029778  jmp     short loc_18002973B
0x18002977a  lea     rcx, [rbp+57h+lpFileName]
0x18002977e  cmp     r8, 7
0x180029782  cmova   rcx, r9; lpFileName
0x180029786  mov     [rsp+0D0h+hTemplateFile], r15; hTemplateFile
0x18002978b  mov     [rsp+0D0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180029793  mov     r8d, 3; dwShareMode
0x180029799  mov     [rsp+0D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002979e  xor     r9d, r9d; lpSecurityAttributes
0x1800297a1  mov     edx, 0C0000000h; dwDesiredAccess
0x1800297a6  call    cs:__imp_CreateFileW
0x1800297ad  nop     dword ptr [rax+rax+00h]
0x1800297b2  mov     rbx, rax
0x1800297b5  mov     [rbp+57h+var_90], rax
0x1800297b9  lea     rdx, [rbp+57h+lpFileName]
0x1800297bd  cmp     [rbp+57h+var_70], 7
0x1800297c2  cmova   rdx, [rbp+57h+lpFileName]
0x1800297c7  dec     rax
0x1800297ca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800297ce  setnbe  al
0x1800297d1  mov     rcx, [rbp+5Fh]; this
0x1800297d5  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rdx; char *
0x1800297da  lea     r13, aLs; "%ls"
0x1800297e1  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13; bool
0x1800297e6  movzx   r9d, al; char *
0x1800297ea  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x1800297f1  mov     edx, 33Eh; void *
0x1800297f6  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800297fb  xorps   xmm0, xmm0
0x1800297fe  movups  [rbp+57h+FsInformation], xmm0
0x180029802  movups  [rbp+57h+var_48], xmm0
0x180029806  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18002980a  lea     rdi, [rbp+57h+lpFileName]
0x18002980e  cmp     [rbp+57h+var_70], 7
0x180029813  cmova   rdi, [rbp+57h+lpFileName]
0x180029818  mov     [rsp+0D0h+dwCreationDisposition], 7; FsInformationClass
0x180029820  mov     r9d, 20h ; ' '; Length
0x180029826  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x18002982a  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002982e  mov     rcx, rbx; FileHandle
0x180029831  call    cs:__imp_NtQueryVolumeInformationFile
0x180029838  nop     dword ptr [rax+rax+00h]
0x18002983d  mov     rcx, [rbp+5Fh]; this
0x180029841  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rdi; char *
0x180029846  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13; int
0x18002984b  mov     r9d, eax; char *
0x18002984e  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x180029855  mov     edx, 347h; void *
0x18002985a  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002985f  mov     ecx, dword ptr [rbp+57h+var_48+8]
0x180029862  imul    ecx, dword ptr [rbp+57h+var_48+0Ch]
0x180029866  mov     rax, r14
0x180029869  cqo
0x18002986b  idiv    rcx
0x18002986e  mov     rcx, rax
0x180029871  mov     rax, qword ptr [rbp+57h+FsInformation]
0x180029875  inc     rax
0x180029878  cmp     rax, rcx
0x18002987b  jge     short loc_1800298F5
0x18002987d  mov     eax, dword ptr [rbp+57h+var_48+8]
0x180029880  imul    rax, rcx
0x180029884  mov     [rbp+57h+InBuffer], rax
0x180029888  mov     [rbp+57h+BytesReturned], r15d
0x18002988c  lea     rdi, [rbp+57h+lpFileName]
0x180029890  cmp     [rbp+57h+var_70], 7
0x180029895  cmova   rdi, [rbp+57h+lpFileName]
0x18002989a  mov     [rsp+0D0h+lpOverlapped], r15; lpOverlapped
0x18002989f  lea     rax, [rbp+57h+BytesReturned]
0x1800298a3  mov     [rsp+0D0h+hTemplateFile], rax; lpBytesReturned
0x1800298a8  mov     [rsp+0D0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x1800298ad  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r15; lpOutBuffer
0x1800298b2  mov     r9d, 8; nInBufferSize
0x1800298b8  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x1800298bc  mov     edx, 900F0h; dwIoControlCode
0x1800298c1  mov     rcx, rbx; hDevice
0x1800298c4  call    cs:__imp_DeviceIoControl
0x1800298cb  nop     dword ptr [rax+rax+00h]
0x1800298d0  mov     rcx, [rbp+5Fh]; this
0x1800298d4  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rdi; char *
0x1800298d9  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13; __int64
0x1800298de  mov     r9d, eax; char *
0x1800298e1  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x1800298e8  mov     edx, 360h; void *
0x1800298ed  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800298f2  mov     sil, 1
0x1800298f5  lea     rcx, [rbx-1]
0x1800298f9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800298fd  ja      short loc_18002990F
0x1800298ff  mov     rcx, rbx; hObject
0x180029902  call    cs:__imp_CloseHandle
0x180029909  nop     dword ptr [rax+rax+00h]
0x18002990e  nop
0x18002990f  lea     rcx, [rbp+57h+lpFileName]
0x180029913  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029918  mov     al, sil
0x18002991b  mov     rcx, [rbp+57h+var_28]
0x18002991f  xor     rcx, rsp; StackCookie
0x180029922  call    __security_check_cookie
0x180029927  lea     r11, [rsp+0D0h+var_20]
0x18002992f  mov     rbx, [r11+40h]
0x180029933  mov     rsi, [r11+48h]
0x180029937  mov     rsp, r11
0x18002993a  pop     r15
0x18002993c  pop     r14
0x18002993e  pop     r13
0x180029940  pop     rdi
0x180029941  pop     rbp
0x180029942  retn
```
