# Microsoft::Windows::MDM::OmadmClient::LogHelper::LogXmlToFile(ushort const *,ulong,ulong,ushort const *,ushort const *,bool)

- ea: `0x140031250`
- end: `0x14003154f`
- name: `?LogXmlToFile@LogHelper@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBGKK00_N@Z`
- size: `767`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::LogHelper *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140003450`
- `0x14000b0d4`
- `0x14000b0f4`
- `0x140030998`
- `0x140031250`
- `0x14005dbd0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003145c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400314da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003145c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400314da`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14003142a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140031482`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400314b8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14003142a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140031482`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400314b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400313cd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400313cd`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::LogHelper::LogXmlToFile(
        Microsoft::Windows::MDM::OmadmClient::LogHelper *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        const unsigned __int16 *lpBuffer,
        bool a7)
{
  const unsigned __int16 *v10; // rax
  __int64 v11; // rcx
  signed int ProgramDataXmlFilePath; // ebx
  unsigned __int64 v13; // rdx
  unsigned __int128 v14; // rax
  DWORD v15; // esi
  __int64 v16; // rdx
  unsigned int v17; // edx
  const char *v18; // r9
  HANDLE FileW; // rax
  const char *v20; // r9
  void *v21; // rbx
  const char *v23; // r9
  __int64 v24; // rdx
  unsigned int LastError; // edi
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesWritten[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v28[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  if ( !lpBuffer )
  {
    ProgramDataXmlFilePath = -2147024809;
LABEL_35:
    v16 = 261;
    goto LABEL_36;
  }
  v10 = lpBuffer;
  v11 = 3145728;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v11;
  }
  while ( v11 );
  ProgramDataXmlFilePath = v11 == 0 ? 0x80070057 : 0;
  v13 = (3145728 - v11) & ((unsigned __int128)-(__int128)(unsigned __int64)v11 >> 64);
  if ( !v11 )
    goto LABEL_35;
  if ( !v13 )
    return 0;
  *(_QWORD *)NumberOfBytesWritten = 0;
  v14 = v13 * (unsigned __int128)2uLL;
  v15 = v14;
  if ( !is_mul_ok((3145728 - v11) & ((unsigned __int128)-(__int128)(unsigned __int64)v11 >> 64), 2u) )
  {
    ProgramDataXmlFilePath = -2147024362;
    v16 = 265;
    goto LABEL_36;
  }
  if ( (unsigned __int64)v14 > 0xFFFFFFFF )
  {
    ProgramDataXmlFilePath = -2147024362;
    v16 = 268;
    goto LABEL_36;
  }
  ProgramDataXmlFilePath = Microsoft::Windows::MDM::OmadmClient::LogHelper::GetProgramDataXmlFilePath(
                             v28,
                             DWORD2(v14),
                             a2,
                             a3,
                             0,
                             0);
  if ( ProgramDataXmlFilePath < 0 )
  {
    v16 = 277;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\loghelper.cpp",
      (const char *)(unsigned int)ProgramDataXmlFilePath,
      dwCreationDisposition);
    return (unsigned int)ProgramDataXmlFilePath;
  }
  if ( !(unsigned int)CreatePath(v28) )
  {
    ProgramDataXmlFilePath = wil::details::in1diag3::Return_GetLastError(
                               retaddr,
                               (void *)0x2A8,
                               (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\loghelper.cpp",
                               v18);
    if ( ProgramDataXmlFilePath < 0 )
    {
      v16 = 279;
      goto LABEL_36;
    }
  }
  ProgramDataXmlFilePath = Microsoft::Windows::MDM::OmadmClient::LogHelper::GetProgramDataXmlFilePath(
                             FileName,
                             v17,
                             a2,
                             a3,
                             a4,
                             a5);
  if ( ProgramDataXmlFilePath < 0 )
  {
    v16 = 288;
    goto LABEL_36;
  }
  FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v21 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x12A,
             (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\loghelper.cpp",
             v20);
  NumberOfBytesWritten[0] = 0;
  if ( !a7 || WriteFile(FileW, aSyncmllog, 0x16u, NumberOfBytesWritten, 0) )
  {
    if ( !WriteFile(v21, lpBuffer, v15, NumberOfBytesWritten, 0) )
    {
      v24 = 320;
      goto LABEL_21;
    }
    if ( a7 && !WriteFile(v21, aSyncmllog_0, 0x18u, NumberOfBytesWritten, 0) )
    {
      v24 = 331;
      goto LABEL_21;
    }
    if ( v21 )
      CloseHandle(v21);
    return 0;
  }
  v24 = 310;
LABEL_21:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v24,
                (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\loghelper.cpp",
                v23);
  if ( v21 )
    CloseHandle(v21);
  return LastError;
}

```

## disassembly

```asm
0x140031250  mov     [rsp-8+arg_0], rbx
0x140031255  push    rbp
0x140031256  push    rsi
0x140031257  push    rdi
0x140031258  push    r12
0x14003125a  push    r13
0x14003125c  push    r14
0x14003125e  push    r15
0x140031260  lea     rbp, [rsp-380h]
0x140031268  sub     rsp, 480h
0x14003126f  mov     rax, cs:__security_cookie
0x140031276  xor     rax, rsp
0x140031279  mov     [rbp+3B0h+var_40], rax
0x140031280  mov     r14, [rbp+3B0h+lpBuffer]
0x140031287  mov     r12d, r9d
0x14003128a  mov     r13, [rbp+3B0h+arg_20]
0x140031291  xor     r9d, r9d
0x140031294  mov     r15d, r8d
0x140031297  mov     rdi, rdx
0x14003129a  test    r14, r14
0x14003129d  jz      loc_140031502
0x1400312a3  mov     r8d, 300000h
0x1400312a9  mov     rax, r14
0x1400312ac  mov     ecx, r8d
0x1400312af  cmp     [rax], r9w
0x1400312b3  jz      short loc_1400312BF
0x1400312b5  add     rax, 2
0x1400312b9  sub     rcx, 1
0x1400312bd  jnz     short loc_1400312AF
0x1400312bf  mov     rax, rcx
0x1400312c2  neg     rax
0x1400312c5  mov     rax, rcx
0x1400312c8  sbb     ebx, ebx
0x1400312ca  sub     r8, rcx
0x1400312cd  not     ebx
0x1400312cf  and     ebx, 80070057h
0x1400312d5  neg     rax
0x1400312d8  sbb     rdx, rdx
0x1400312db  and     rdx, r8; unsigned int
0x1400312de  test    rcx, rcx
0x1400312e1  jz      loc_140031507
0x1400312e7  test    rdx, rdx
0x1400312ea  jz      loc_1400314E6
0x1400312f0  mov     eax, 2
0x1400312f5  mov     qword ptr [rsp+4B0h+NumberOfBytesWritten], r9
0x1400312fa  mul     rdx
0x1400312fd  mov     rsi, rax
0x140031300  test    rdx, rdx
0x140031303  jnz     loc_1400314F6
0x140031309  mov     eax, 0FFFFFFFFh
0x14003130e  cmp     rsi, rax
0x140031311  ja      loc_1400314EA
0x140031317  mov     qword ptr [rsp+4B0h+dwFlagsAndAttributes], r9; unsigned __int16 *
0x14003131c  lea     rcx, [rsp+4B0h+var_460]; unsigned __int16 *
0x140031321  mov     [rsp+4B0h+dwCreationDisposition], r9d; unsigned int
0x140031326  mov     r8, rdi; unsigned __int16 *
0x140031329  mov     r9d, r15d; unsigned int
0x14003132c  call    ?GetProgramDataXmlFilePath@LogHelper@OmadmClient@MDM@Windows@Microsoft@@KAJPEAGKPEBGKK1@Z; Microsoft::Windows::MDM::OmadmClient::LogHelper::GetProgramDataXmlFilePath(ushort *,ulong,ushort const *,ulong,ulong,ushort const *)
0x140031331  mov     ebx, eax
0x140031333  test    eax, eax
0x140031335  jns     short loc_140031341
0x140031337  mov     edx, 115h
0x14003133c  jmp     loc_14003150C
0x140031341  lea     rcx, [rsp+4B0h+var_460]
0x140031346  call    CreatePath
0x14003134b  test    eax, eax
0x14003134d  jnz     short loc_140031377
0x14003134f  mov     rcx, [rbp+3B8h]; this
0x140031356  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14003135d  mov     edx, 2A8h; void *
0x140031362  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140031367  mov     ebx, eax
0x140031369  test    eax, eax
0x14003136b  jns     short loc_140031377
0x14003136d  mov     edx, 117h
0x140031372  jmp     loc_14003150C
0x140031377  mov     qword ptr [rsp+4B0h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x14003137c  lea     rcx, [rbp+3B0h+FileName]; unsigned __int16 *
0x140031383  mov     r9d, r15d; unsigned int
0x140031386  mov     [rsp+4B0h+dwCreationDisposition], r12d; unsigned int
0x14003138b  mov     r8, rdi; unsigned __int16 *
0x14003138e  call    ?GetProgramDataXmlFilePath@LogHelper@OmadmClient@MDM@Windows@Microsoft@@KAJPEAGKPEBGKK1@Z; Microsoft::Windows::MDM::OmadmClient::LogHelper::GetProgramDataXmlFilePath(ushort *,ulong,ushort const *,ulong,ulong,ushort const *)
0x140031393  xor     r15d, r15d
0x140031396  mov     ebx, eax
0x140031398  test    eax, eax
0x14003139a  jns     short loc_1400313A6
0x14003139c  mov     edx, 120h
0x1400313a1  jmp     loc_14003150C
0x1400313a6  mov     [rsp+4B0h+hTemplateFile], r15; hTemplateFile
0x1400313ab  lea     rcx, [rbp+3B0h+FileName]; lpFileName
0x1400313b2  mov     [rsp+4B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400313ba  xor     r9d, r9d; lpSecurityAttributes
0x1400313bd  xor     r8d, r8d; dwShareMode
0x1400313c0  mov     [rsp+4B0h+dwCreationDisposition], 2; dwCreationDisposition
0x1400313c8  mov     edx, 40000000h; dwDesiredAccess
0x1400313cd  call    cs:__imp_CreateFileW
0x1400313d4  nop     dword ptr [rax+rax+00h]
0x1400313d9  mov     rbx, rax
0x1400313dc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400313e0  jnz     short loc_1400313FF
0x1400313e2  mov     rcx, [rbp+3B8h]; this
0x1400313e9  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x1400313f0  mov     edx, 12Ah; void *
0x1400313f5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400313fa  jmp     loc_140031524
0x1400313ff  mov     dil, [rbp+3B0h+arg_30]
0x140031406  mov     [rsp+4B0h+NumberOfBytesWritten], r15d
0x14003140b  test    dil, dil
0x14003140e  jz      short loc_14003146F
0x140031410  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140031415  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x14003141a  mov     r8d, 16h; nNumberOfBytesToWrite
0x140031420  lea     rdx, aSyncmllog; "<SyncMlLog>"
0x140031427  mov     rcx, rbx; hFile
0x14003142a  call    cs:__imp_WriteFile
0x140031431  nop     dword ptr [rax+rax+00h]
0x140031436  test    eax, eax
0x140031438  jnz     short loc_14003146F
0x14003143a  mov     edx, 136h; void *
0x14003143f  mov     rcx, [rbp+3B8h]; this
0x140031446  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14003144d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140031452  mov     edi, eax
0x140031454  test    rbx, rbx
0x140031457  jz      short loc_140031468
0x140031459  mov     rcx, rbx; hObject
0x14003145c  call    cs:__imp_CloseHandle
0x140031463  nop     dword ptr [rax+rax+00h]
0x140031468  mov     eax, edi
0x14003146a  jmp     loc_140031524
0x14003146f  mov     r8d, esi; nNumberOfBytesToWrite
0x140031472  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x140031477  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14003147c  mov     rdx, r14; lpBuffer
0x14003147f  mov     rcx, rbx; hFile
0x140031482  call    cs:__imp_WriteFile
0x140031489  nop     dword ptr [rax+rax+00h]
0x14003148e  test    eax, eax
0x140031490  jnz     short loc_140031499
0x140031492  mov     edx, 140h
0x140031497  jmp     short loc_14003143F
0x140031499  test    dil, dil
0x14003149c  jz      short loc_1400314D2
0x14003149e  lea     r9, [rsp+4B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400314a3  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x1400314a8  mov     r8d, 18h; nNumberOfBytesToWrite
0x1400314ae  lea     rdx, aSyncmllog_0; "</SyncMlLog>"
0x1400314b5  mov     rcx, rbx; hFile
0x1400314b8  call    cs:__imp_WriteFile
0x1400314bf  nop     dword ptr [rax+rax+00h]
0x1400314c4  test    eax, eax
0x1400314c6  jnz     short loc_1400314D2
0x1400314c8  mov     edx, 14Bh
0x1400314cd  jmp     loc_14003143F
0x1400314d2  test    rbx, rbx
0x1400314d5  jz      short loc_1400314E6
0x1400314d7  mov     rcx, rbx; hObject
0x1400314da  call    cs:__imp_CloseHandle
0x1400314e1  nop     dword ptr [rax+rax+00h]
0x1400314e6  xor     eax, eax
0x1400314e8  jmp     short loc_140031524
0x1400314ea  mov     ebx, 80070216h
0x1400314ef  mov     edx, 10Ch
0x1400314f4  jmp     short loc_14003150C
0x1400314f6  mov     ebx, 80070216h
0x1400314fb  mov     edx, 109h
0x140031500  jmp     short loc_14003150C
0x140031502  mov     ebx, 80070057h
0x140031507  mov     edx, 105h; void *
0x14003150c  mov     rcx, [rbp+3B8h]; this
0x140031513  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14003151a  mov     r9d, ebx; char *
0x14003151d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140031522  mov     eax, ebx
0x140031524  mov     rcx, [rbp+3B0h+var_40]
0x14003152b  xor     rcx, rsp; StackCookie
0x14003152e  call    __security_check_cookie
0x140031533  mov     rbx, [rsp+4B0h+arg_0]
0x14003153b  add     rsp, 480h
0x140031542  pop     r15
0x140031544  pop     r14
0x140031546  pop     r13
0x140031548  pop     r12
0x14003154a  pop     rdi
0x14003154b  pop     rsi
0x14003154c  pop     rbp
0x14003154d  retn
```
