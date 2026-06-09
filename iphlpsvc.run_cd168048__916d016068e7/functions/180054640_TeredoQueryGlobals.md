# TeredoQueryGlobals

- ea: `0x180054640`
- end: `0x1800548db`
- name: `TeredoQueryGlobals`
- size: `667`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004f50`
- `0x18000ce90`
- `0x18000d7b0`
- `0x1800190e0`
- `0x180022b30`
- `0x18002e150`
- `0x18004b630`
- `0x18004c1c8`
- `0x180053058`
- `0x180054640`
- `0x18005ed80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180054882`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180054882`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800546ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800546ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054830`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054873`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054891`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054873`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054891`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180054756`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180054756`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800546a4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800546a4`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180054820`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180054820`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800547d1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800547fb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800547d1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800547fb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800546e6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800546e6`

## string_xrefs

- `0x18005479f`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x180054864`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x1800548a3`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x18005469d`: `%windir%\temp\teredo.txt`
- `0x180054736`: `Found target hardlink file path %s`
- `0x18005477a`: `Failed to add the ACL to the teredo.txt file: %x`

## pseudocode

```c
void __fastcall TeredoQueryGlobals(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  HANDLE FileW; // rbx
  unsigned int v4; // eax
  DWORD LastError; // eax
  _BYTE v6[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE pSid[80]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Dst[264]; // [rsp+A0h] [rbp-60h] BYREF

  NumberOfBytesWritten = 0;
  memset_0(pSid, 0, 0x44u);
  cbSid = 68;
  v6[0] = 0;
  if ( ExpandEnvironmentStringsW(L"%windir%\\temp\\teredo.txt", Dst, 0x104u) - 1 <= 0x103 )
  {
    FileW = CreateFileW(Dst, 0x10000000u, 1u, 0, 4u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      if ( GetLastError() == 183 )
      {
        if ( (unsigned int)IsHardLinkFile(FileW, v6) )
        {
LABEL_14:
          CloseHandle(FileW);
          goto LABEL_15;
        }
        if ( v6[0] )
        {
          EventWrite0(0x800000, L"Found target hardlink file path %s", Dst);
          goto LABEL_14;
        }
      }
      if ( CreateWellKnownSid(WinWorldSid, 0, pSid, &cbSid) )
      {
        v4 = GrantFileAccess(FileW);
        if ( v4 )
          EventWriteError0(0x100000, L"Failed to add the ACL to the teredo.txt file: %x", v4);
      }
      if ( (unsigned int)GetAndTraceLock(
                           "onecoreuap\\net\\netio\\iphlpsvc\\service\\teredo.c",
                           "TeredoQueryGlobals",
                           3599,
                           g_TeredoLock) )
      {
        WriteFile(FileW, &dword_1800CA070, 4u, &NumberOfBytesWritten, 0);
        WriteFile(FileW, &dword_1800CB7E8, 0x110u, &NumberOfBytesWritten, 0);
        ForEachCompartment(TeredoCompartmentQueryGlobals, FileW, &g_ProtocolStateTeredo);
        if ( !SetEndOfFile(FileW) )
        {
          LastError = GetLastError();
          EventWrite0(0x800000, L"Fail to truncate current Teredo file %d", LastError);
        }
        ReleaseAndTraceLock(
          "onecoreuap\\net\\netio\\iphlpsvc\\service\\teredo.c",
          "TeredoQueryGlobals",
          3640,
          g_TeredoLock);
      }
      goto LABEL_14;
    }
  }
LABEL_15:
  SetEvent(Context);
  CloseHandle(Context);
  DereferenceServiceEx("TeredoQueryGlobals", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\teredo.c", 3654);
}

```

## disassembly

```asm
0x180054640  mov     [rsp-8+arg_0], rbx
0x180054645  mov     [rsp-8+arg_10], rdi
0x18005464a  push    rbp
0x18005464b  lea     rbp, [rsp-1C0h]
0x180054653  sub     rsp, 2C0h
0x18005465a  mov     rax, cs:__security_cookie
0x180054661  xor     rax, rsp
0x180054664  mov     [rbp+1C0h+var_10], rax
0x18005466b  mov     rdi, rdx
0x18005466e  mov     [rsp+2C0h+NumberOfBytesWritten], 0
0x180054676  mov     ebx, 44h ; 'D'
0x18005467b  lea     rcx, [rsp+2C0h+pSid]; void *
0x180054680  mov     r8d, ebx; Size
0x180054683  xor     edx, edx; Val
0x180054685  call    memset_0
0x18005468a  mov     r8d, 104h; nSize
0x180054690  mov     [rsp+2C0h+cbSid], ebx
0x180054694  lea     rdx, [rbp+1C0h+Dst]; lpDst
0x180054698  mov     [rsp+2C0h+var_280], 0
0x18005469d  lea     rcx, Src; "%windir%\\temp\\teredo.txt"
0x1800546a4  call    cs:__imp_ExpandEnvironmentStringsW
0x1800546ab  nop     dword ptr [rax+rax+00h]
0x1800546b0  dec     eax
0x1800546b2  cmp     eax, 103h
0x1800546b7  ja      loc_18005487F
0x1800546bd  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x1800546c6  lea     r8d, [rbx-43h]; dwShareMode
0x1800546ca  mov     [rsp+2C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800546d2  lea     rcx, [rbp+1C0h+Dst]; lpFileName
0x1800546d6  xor     r9d, r9d; lpSecurityAttributes
0x1800546d9  mov     [rsp+2C0h+dwCreationDisposition], 4; dwCreationDisposition
0x1800546e1  mov     edx, 10000000h; dwDesiredAccess
0x1800546e6  call    cs:__imp_CreateFileW
0x1800546ed  nop     dword ptr [rax+rax+00h]
0x1800546f2  mov     rbx, rax
0x1800546f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800546f9  jz      loc_18005487F
0x1800546ff  call    cs:__imp_GetLastError
0x180054706  nop     dword ptr [rax+rax+00h]
0x18005470b  cmp     eax, 0B7h
0x180054710  jnz     short loc_180054747
0x180054712  lea     rdx, [rsp+2C0h+var_280]
0x180054717  mov     rcx, rbx
0x18005471a  call    IsHardLinkFile
0x18005471f  test    eax, eax
0x180054721  jnz     loc_180054870
0x180054727  cmp     [rsp+2C0h+var_280], al
0x18005472b  jz      short loc_180054747
0x18005472d  lea     r8, [rbp+1C0h+Dst]
0x180054731  mov     ecx, 800000h
0x180054736  lea     rdx, aFoundTargetHar; "Found target hardlink file path %s"
0x18005473d  call    EventWrite0
0x180054742  jmp     loc_180054870
0x180054747  xor     edx, edx; DomainSid
0x180054749  lea     r9, [rsp+2C0h+cbSid]; cbSid
0x18005474e  lea     r8, [rsp+2C0h+pSid]; pSid
0x180054753  lea     ecx, [rdx+1]; WellKnownSidType
0x180054756  call    cs:__imp_CreateWellKnownSid
0x18005475d  nop     dword ptr [rax+rax+00h]
0x180054762  test    eax, eax
0x180054764  jz      short loc_18005478B
0x180054766  lea     rdx, [rsp+2C0h+pSid]
0x18005476b  mov     rcx, rbx; handle
0x18005476e  call    GrantFileAccess
0x180054773  test    eax, eax
0x180054775  jz      short loc_18005478B
0x180054777  mov     r8d, eax
0x18005477a  lea     rdx, aFailedToAddThe; "Failed to add the ACL to the teredo.txt"...
0x180054781  mov     ecx, 100000h
0x180054786  call    EventWriteError0
0x18005478b  mov     r9, cs:g_TeredoLock
0x180054792  lea     rdx, aTeredoqueryglo; "TeredoQueryGlobals"
0x180054799  mov     r8d, 0E0Fh
0x18005479f  lea     rcx, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800547a6  call    GetAndTraceLock
0x1800547ab  test    eax, eax
0x1800547ad  jz      loc_180054870
0x1800547b3  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800547b8  mov     qword ptr [rsp+2C0h+dwCreationDisposition], 0; lpOverlapped
0x1800547c1  mov     r8d, 4; nNumberOfBytesToWrite
0x1800547c7  lea     rdx, dword_1800CA070; lpBuffer
0x1800547ce  mov     rcx, rbx; hFile
0x1800547d1  call    cs:__imp_WriteFile
0x1800547d8  nop     dword ptr [rax+rax+00h]
0x1800547dd  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800547e2  mov     qword ptr [rsp+2C0h+dwCreationDisposition], 0; lpOverlapped
0x1800547eb  mov     r8d, 110h; nNumberOfBytesToWrite
0x1800547f1  lea     rdx, dword_1800CB7E8; lpBuffer
0x1800547f8  mov     rcx, rbx; hFile
0x1800547fb  call    cs:__imp_WriteFile
0x180054802  nop     dword ptr [rax+rax+00h]
0x180054807  lea     r8, g_ProtocolStateTeredo
0x18005480e  mov     rdx, rbx
0x180054811  lea     rcx, TeredoCompartmentQueryGlobals
0x180054818  call    ForEachCompartment
0x18005481d  mov     rcx, rbx; hFile
0x180054820  call    cs:__imp_SetEndOfFile
0x180054827  nop     dword ptr [rax+rax+00h]
0x18005482c  test    eax, eax
0x18005482e  jnz     short loc_180054850
0x180054830  call    cs:__imp_GetLastError
0x180054837  nop     dword ptr [rax+rax+00h]
0x18005483c  lea     rdx, aFailToTruncate; "Fail to truncate current Teredo file %d"
0x180054843  mov     ecx, 800000h
0x180054848  mov     r8d, eax
0x18005484b  call    EventWrite0
0x180054850  mov     r9, cs:g_TeredoLock
0x180054857  lea     rdx, aTeredoqueryglo; "TeredoQueryGlobals"
0x18005485e  mov     r8d, 0E38h
0x180054864  lea     rcx, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005486b  call    ReleaseAndTraceLock
0x180054870  mov     rcx, rbx; hObject
0x180054873  call    cs:__imp_CloseHandle
0x18005487a  nop     dword ptr [rax+rax+00h]
0x18005487f  mov     rcx, rdi; hEvent
0x180054882  call    cs:__imp_SetEvent
0x180054889  nop     dword ptr [rax+rax+00h]
0x18005488e  mov     rcx, rdi; hObject
0x180054891  call    cs:__imp_CloseHandle
0x180054898  nop     dword ptr [rax+rax+00h]
0x18005489d  mov     r8d, 0E46h
0x1800548a3  lea     rdx, aOnecoreuapNetN_19; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800548aa  lea     rcx, aTeredoqueryglo; "TeredoQueryGlobals"
0x1800548b1  call    DereferenceServiceEx
0x1800548b6  mov     rcx, [rbp+1C0h+var_10]
0x1800548bd  xor     rcx, rsp; StackCookie
0x1800548c0  call    __security_check_cookie
0x1800548c5  lea     r11, [rsp+2C0h+var_s0]
0x1800548cd  mov     rbx, [r11+10h]
0x1800548d1  mov     rdi, [r11+20h]
0x1800548d5  mov     rsp, r11
0x1800548d8  pop     rbp
0x1800548d9  retn
```
