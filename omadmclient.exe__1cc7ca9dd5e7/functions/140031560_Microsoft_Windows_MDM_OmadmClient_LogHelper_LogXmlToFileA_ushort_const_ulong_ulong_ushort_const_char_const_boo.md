# Microsoft::Windows::MDM::OmadmClient::LogHelper::LogXmlToFileA(ushort const *,ulong,ulong,ushort const *,char const *,bool)

- ea: `0x140031560`
- end: `0x140031837`
- name: `?LogXmlToFileA@LogHelper@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBGKK0PEBD_N@Z`
- size: `727`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::LogHelper *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, const unsigned __int16 *, const char *, bool)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140003450`
- `0x14000b0d4`
- `0x14000b0f4`
- `0x140030998`
- `0x140031560`
- `0x14005dbd0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140031751`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400317cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140031751`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400317cc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140031722`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140031777`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400317aa`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140031722`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140031777`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400317aa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400316c4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400316c4`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::LogHelper::LogXmlToFileA(
        Microsoft::Windows::MDM::OmadmClient::LogHelper *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        const char *lpBuffer,
        bool a7)
{
  const char *v10; // rax
  __int64 v11; // rcx
  signed int ProgramDataXmlFilePath; // edi
  unsigned __int64 v13; // rbp
  __int64 v14; // rdx
  unsigned int v15; // edx
  const char *v16; // r9
  HANDLE FileW; // rax
  const char *v18; // r9
  void *v19; // rdi
  const char *v21; // r9
  __int64 v22; // rdx
  unsigned int LastError; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-498h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-478h] BYREF
  unsigned __int16 v26[264]; // [rsp+50h] [rbp-468h] BYREF
  WCHAR FileName[264]; // [rsp+260h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+0h]

  if ( !lpBuffer )
  {
    ProgramDataXmlFilePath = -2147024809;
LABEL_33:
    v14 = 347;
    goto LABEL_34;
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
  v13 = (3145728 - v11) & -(__int64)(v11 != 0);
  if ( !v11 )
    goto LABEL_33;
  if ( !v13 )
    return 0;
  if ( v13 > 0xFFFFFFFF )
  {
    ProgramDataXmlFilePath = -2147024362;
    v14 = 351;
    goto LABEL_34;
  }
  ProgramDataXmlFilePath = Microsoft::Windows::MDM::OmadmClient::LogHelper::GetProgramDataXmlFilePath(
                             v26,
                             3145728 - (int)v11,
                             a2,
                             a3,
                             0,
                             0);
  if ( ProgramDataXmlFilePath < 0 )
  {
    v14 = 360;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\loghelper.cpp",
      (const char *)(unsigned int)ProgramDataXmlFilePath,
      dwCreationDisposition);
    return (unsigned int)ProgramDataXmlFilePath;
  }
  if ( !(unsigned int)CreatePath(v26) )
  {
    ProgramDataXmlFilePath = wil::details::in1diag3::Return_GetLastError(
                               retaddr,
                               (void *)0x2A8,
                               (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\loghelper.cpp",
                               v16);
    if ( ProgramDataXmlFilePath < 0 )
    {
      v14 = 362;
      goto LABEL_34;
    }
  }
  ProgramDataXmlFilePath = Microsoft::Windows::MDM::OmadmClient::LogHelper::GetProgramDataXmlFilePath(
                             FileName,
                             v15,
                             a2,
                             a3,
                             a4,
                             a5);
  if ( ProgramDataXmlFilePath < 0 )
  {
    v14 = 371;
    goto LABEL_34;
  }
  FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  v19 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x17D,
             (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\loghelper.cpp",
             v18);
  NumberOfBytesWritten = 0;
  if ( !a7 || WriteFile(FileW, aSyncmllog_1, 0xCu, &NumberOfBytesWritten, 0) )
  {
    if ( !WriteFile(v19, lpBuffer, v13, &NumberOfBytesWritten, 0) )
    {
      v22 = 403;
      goto LABEL_20;
    }
    if ( a7 && !WriteFile(v19, aSyncmllog_2, 0xCu, &NumberOfBytesWritten, 0) )
    {
      v22 = 414;
      goto LABEL_20;
    }
    if ( v19 )
      CloseHandle(v19);
    return 0;
  }
  v22 = 393;
LABEL_20:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v22,
                (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\loghelper.cpp",
                v21);
  if ( v19 )
    CloseHandle(v19);
  return LastError;
}

```

## disassembly

```asm
0x140031560  mov     [rsp+arg_0], rbx
0x140031565  push    rbp
0x140031566  push    rsi
0x140031567  push    rdi
0x140031568  push    r12
0x14003156a  push    r13
0x14003156c  push    r14
0x14003156e  push    r15
0x140031570  sub     rsp, 480h
0x140031577  mov     rax, cs:__security_cookie
0x14003157e  xor     rax, rsp
0x140031581  mov     [rsp+4B8h+var_48], rax
0x140031589  mov     r14, [rsp+4B8h+lpBuffer]
0x140031591  xor     ebx, ebx
0x140031593  mov     r13, [rsp+4B8h+arg_20]
0x14003159b  mov     r12d, r9d
0x14003159e  mov     r15d, r8d
0x1400315a1  mov     rsi, rdx
0x1400315a4  test    r14, r14
0x1400315a7  jz      loc_1400317E8
0x1400315ad  mov     edx, 300000h
0x1400315b2  mov     rax, r14
0x1400315b5  mov     ecx, edx
0x1400315b7  cmp     [rax], bl
0x1400315b9  jz      short loc_1400315C4
0x1400315bb  inc     rax
0x1400315be  sub     rcx, 1
0x1400315c2  jnz     short loc_1400315B7
0x1400315c4  mov     rax, rcx
0x1400315c7  neg     rax
0x1400315ca  mov     rax, rcx
0x1400315cd  sbb     edi, edi
0x1400315cf  sub     rdx, rcx; unsigned int
0x1400315d2  not     edi
0x1400315d4  and     edi, 80070057h
0x1400315da  neg     rax
0x1400315dd  sbb     rbp, rbp
0x1400315e0  and     rbp, rdx
0x1400315e3  test    rcx, rcx
0x1400315e6  jz      loc_1400317ED
0x1400315ec  test    rbp, rbp
0x1400315ef  jz      loc_1400317D8
0x1400315f5  mov     eax, 0FFFFFFFFh
0x1400315fa  cmp     rbp, rax
0x1400315fd  ja      loc_1400317DC
0x140031603  mov     qword ptr [rsp+4B8h+dwFlagsAndAttributes], rbx; unsigned __int16 *
0x140031608  lea     rcx, [rsp+4B8h+var_468]; unsigned __int16 *
0x14003160d  mov     r9d, r15d; unsigned int
0x140031610  mov     [rsp+4B8h+dwCreationDisposition], ebx; unsigned int
0x140031614  mov     r8, rsi; unsigned __int16 *
0x140031617  call    ?GetProgramDataXmlFilePath@LogHelper@OmadmClient@MDM@Windows@Microsoft@@KAJPEAGKPEBGKK1@Z; Microsoft::Windows::MDM::OmadmClient::LogHelper::GetProgramDataXmlFilePath(ushort *,ulong,ushort const *,ulong,ulong,ushort const *)
0x14003161c  mov     edi, eax
0x14003161e  test    eax, eax
0x140031620  jns     short loc_14003162C
0x140031622  mov     edx, 168h
0x140031627  jmp     loc_1400317F2
0x14003162c  lea     rcx, [rsp+4B8h+var_468]
0x140031631  call    CreatePath
0x140031636  lea     rbx, aOnecoreuapAdmi_16; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14003163d  test    eax, eax
0x14003163f  jnz     short loc_140031669
0x140031641  mov     rcx, [rsp+4B8h]; this
0x140031649  mov     r8, rbx; unsigned int
0x14003164c  mov     edx, 2A8h; void *
0x140031651  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140031656  mov     edi, eax
0x140031658  test    eax, eax
0x14003165a  jns     short loc_140031669
0x14003165c  mov     r8, rbx
0x14003165f  mov     edx, 16Ah
0x140031664  jmp     loc_1400317F9
0x140031669  mov     qword ptr [rsp+4B8h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x14003166e  lea     rcx, [rsp+4B8h+FileName]; unsigned __int16 *
0x140031676  mov     r9d, r15d; unsigned int
0x140031679  mov     [rsp+4B8h+dwCreationDisposition], r12d; unsigned int
0x14003167e  mov     r8, rsi; unsigned __int16 *
0x140031681  call    ?GetProgramDataXmlFilePath@LogHelper@OmadmClient@MDM@Windows@Microsoft@@KAJPEAGKPEBGKK1@Z; Microsoft::Windows::MDM::OmadmClient::LogHelper::GetProgramDataXmlFilePath(ushort *,ulong,ushort const *,ulong,ulong,ushort const *)
0x140031686  xor     r15d, r15d
0x140031689  mov     edi, eax
0x14003168b  test    eax, eax
0x14003168d  jns     short loc_14003169C
0x14003168f  mov     r8, rbx
0x140031692  mov     edx, 173h
0x140031697  jmp     loc_1400317F9
0x14003169c  mov     [rsp+4B8h+hTemplateFile], r15; hTemplateFile
0x1400316a1  lea     rcx, [rsp+4B8h+FileName]; lpFileName
0x1400316a9  mov     [rsp+4B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400316b1  xor     r9d, r9d; lpSecurityAttributes
0x1400316b4  xor     r8d, r8d; dwShareMode
0x1400316b7  mov     [rsp+4B8h+dwCreationDisposition], 2; dwCreationDisposition
0x1400316bf  mov     edx, 40000000h; dwDesiredAccess
0x1400316c4  call    cs:__imp_CreateFileW
0x1400316cb  nop     dword ptr [rax+rax+00h]
0x1400316d0  mov     rdi, rax
0x1400316d3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400316d7  jnz     short loc_1400316F3
0x1400316d9  mov     rcx, [rsp+4B8h]; this
0x1400316e1  mov     r8, rbx; unsigned int
0x1400316e4  mov     edx, 17Dh; void *
0x1400316e9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400316ee  jmp     loc_14003180B
0x1400316f3  mov     sil, [rsp+4B8h+arg_30]
0x1400316fb  mov     r12d, 0Ch
0x140031701  mov     [rsp+4B8h+NumberOfBytesWritten], r15d
0x140031706  test    sil, sil
0x140031709  jz      short loc_140031764
0x14003170b  lea     r9, [rsp+4B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140031710  mov     qword ptr [rsp+4B8h+dwCreationDisposition], r15; lpOverlapped
0x140031715  mov     r8d, r12d; nNumberOfBytesToWrite
0x140031718  lea     rdx, aSyncmllog_1; "<SyncMlLog>"
0x14003171f  mov     rcx, rdi; hFile
0x140031722  call    cs:__imp_WriteFile
0x140031729  nop     dword ptr [rax+rax+00h]
0x14003172e  test    eax, eax
0x140031730  jnz     short loc_140031764
0x140031732  mov     edx, 189h; void *
0x140031737  mov     rcx, [rsp+4B8h]; this
0x14003173f  mov     r8, rbx; unsigned int
0x140031742  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140031747  mov     ebx, eax
0x140031749  test    rdi, rdi
0x14003174c  jz      short loc_14003175D
0x14003174e  mov     rcx, rdi; hObject
0x140031751  call    cs:__imp_CloseHandle
0x140031758  nop     dword ptr [rax+rax+00h]
0x14003175d  mov     eax, ebx
0x14003175f  jmp     loc_14003180B
0x140031764  mov     r8d, ebp; nNumberOfBytesToWrite
0x140031767  mov     qword ptr [rsp+4B8h+dwCreationDisposition], r15; lpOverlapped
0x14003176c  lea     r9, [rsp+4B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140031771  mov     rdx, r14; lpBuffer
0x140031774  mov     rcx, rdi; hFile
0x140031777  call    cs:__imp_WriteFile
0x14003177e  nop     dword ptr [rax+rax+00h]
0x140031783  test    eax, eax
0x140031785  jnz     short loc_14003178E
0x140031787  mov     edx, 193h
0x14003178c  jmp     short loc_140031737
0x14003178e  test    sil, sil
0x140031791  jz      short loc_1400317C4
0x140031793  lea     r9, [rsp+4B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140031798  mov     qword ptr [rsp+4B8h+dwCreationDisposition], r15; lpOverlapped
0x14003179d  mov     r8d, r12d; nNumberOfBytesToWrite
0x1400317a0  lea     rdx, aSyncmllog_2; "</SyncMlLog>"
0x1400317a7  mov     rcx, rdi; hFile
0x1400317aa  call    cs:__imp_WriteFile
0x1400317b1  nop     dword ptr [rax+rax+00h]
0x1400317b6  test    eax, eax
0x1400317b8  jnz     short loc_1400317C4
0x1400317ba  mov     edx, 19Eh
0x1400317bf  jmp     loc_140031737
0x1400317c4  test    rdi, rdi
0x1400317c7  jz      short loc_1400317D8
0x1400317c9  mov     rcx, rdi; hObject
0x1400317cc  call    cs:__imp_CloseHandle
0x1400317d3  nop     dword ptr [rax+rax+00h]
0x1400317d8  xor     eax, eax
0x1400317da  jmp     short loc_14003180B
0x1400317dc  mov     edi, 80070216h
0x1400317e1  mov     edx, 15Fh
0x1400317e6  jmp     short loc_1400317F2
0x1400317e8  mov     edi, 80070057h
0x1400317ed  mov     edx, 15Bh; void *
0x1400317f2  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x1400317f9  mov     rcx, [rsp+4B8h]; this
0x140031801  mov     r9d, edi; char *
0x140031804  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140031809  mov     eax, edi
0x14003180b  mov     rcx, [rsp+4B8h+var_48]
0x140031813  xor     rcx, rsp; StackCookie
0x140031816  call    __security_check_cookie
0x14003181b  mov     rbx, [rsp+4B8h+arg_0]
0x140031823  add     rsp, 480h
0x14003182a  pop     r15
0x14003182c  pop     r14
0x14003182e  pop     r13
0x140031830  pop     r12
0x140031832  pop     rdi
0x140031833  pop     rsi
0x140031834  pop     rbp
0x140031835  retn
```
