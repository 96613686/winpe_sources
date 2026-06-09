# TeredoQueryGlobals

- ea: `0x180054660`
- end: `0x1800548fb`
- name: `TeredoQueryGlobals`
- size: `667`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004f60`
- `0x18000cea0`
- `0x18000d7c0`
- `0x1800190f0`
- `0x180022b40`
- `0x18002e160`
- `0x18004b5f0`
- `0x18004c188`
- `0x180053018`
- `0x180054660`
- `0x18005eda0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800548a2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800548a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005471f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054850`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005471f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054850`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054893`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800548b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054893`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800548b1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180054776`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180054776`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800546c4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800546c4`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180054840`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180054840`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800547f1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005481b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800547f1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005481b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180054706`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180054706`

## string_xrefs

- `0x1800547bf`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x180054884`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x1800548c3`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x1800546bd`: `%windir%\temp\teredo.txt`
- `0x180054756`: `Found target hardlink file path %s`
- `0x18005479a`: `Failed to add the ACL to the teredo.txt file: %x`

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
0x180054660  mov     [rsp-8+arg_0], rbx
0x180054665  mov     [rsp-8+arg_10], rdi
0x18005466a  push    rbp
0x18005466b  lea     rbp, [rsp-1C0h]
0x180054673  sub     rsp, 2C0h
0x18005467a  mov     rax, cs:__security_cookie
0x180054681  xor     rax, rsp
0x180054684  mov     [rbp+1C0h+var_10], rax
0x18005468b  mov     rdi, rdx
0x18005468e  mov     [rsp+2C0h+NumberOfBytesWritten], 0
0x180054696  mov     ebx, 44h ; 'D'
0x18005469b  lea     rcx, [rsp+2C0h+pSid]; void *
0x1800546a0  mov     r8d, ebx; Size
0x1800546a3  xor     edx, edx; Val
0x1800546a5  call    memset_0
0x1800546aa  mov     r8d, 104h; nSize
0x1800546b0  mov     [rsp+2C0h+cbSid], ebx
0x1800546b4  lea     rdx, [rbp+1C0h+Dst]; lpDst
0x1800546b8  mov     [rsp+2C0h+var_280], 0
0x1800546bd  lea     rcx, Src; "%windir%\\temp\\teredo.txt"
0x1800546c4  call    cs:__imp_ExpandEnvironmentStringsW
0x1800546cb  nop     dword ptr [rax+rax+00h]
0x1800546d0  dec     eax
0x1800546d2  cmp     eax, 103h
0x1800546d7  ja      loc_18005489F
0x1800546dd  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x1800546e6  lea     r8d, [rbx-43h]; dwShareMode
0x1800546ea  mov     [rsp+2C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800546f2  lea     rcx, [rbp+1C0h+Dst]; lpFileName
0x1800546f6  xor     r9d, r9d; lpSecurityAttributes
0x1800546f9  mov     [rsp+2C0h+dwCreationDisposition], 4; dwCreationDisposition
0x180054701  mov     edx, 10000000h; dwDesiredAccess
0x180054706  call    cs:__imp_CreateFileW
0x18005470d  nop     dword ptr [rax+rax+00h]
0x180054712  mov     rbx, rax
0x180054715  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054719  jz      loc_18005489F
0x18005471f  call    cs:__imp_GetLastError
0x180054726  nop     dword ptr [rax+rax+00h]
0x18005472b  cmp     eax, 0B7h
0x180054730  jnz     short loc_180054767
0x180054732  lea     rdx, [rsp+2C0h+var_280]
0x180054737  mov     rcx, rbx
0x18005473a  call    IsHardLinkFile
0x18005473f  test    eax, eax
0x180054741  jnz     loc_180054890
0x180054747  cmp     [rsp+2C0h+var_280], al
0x18005474b  jz      short loc_180054767
0x18005474d  lea     r8, [rbp+1C0h+Dst]
0x180054751  mov     ecx, 800000h
0x180054756  lea     rdx, aFoundTargetHar; "Found target hardlink file path %s"
0x18005475d  call    EventWrite0
0x180054762  jmp     loc_180054890
0x180054767  xor     edx, edx; DomainSid
0x180054769  lea     r9, [rsp+2C0h+cbSid]; cbSid
0x18005476e  lea     r8, [rsp+2C0h+pSid]; pSid
0x180054773  lea     ecx, [rdx+1]; WellKnownSidType
0x180054776  call    cs:__imp_CreateWellKnownSid
0x18005477d  nop     dword ptr [rax+rax+00h]
0x180054782  test    eax, eax
0x180054784  jz      short loc_1800547AB
0x180054786  lea     rdx, [rsp+2C0h+pSid]
0x18005478b  mov     rcx, rbx; handle
0x18005478e  call    GrantFileAccess
0x180054793  test    eax, eax
0x180054795  jz      short loc_1800547AB
0x180054797  mov     r8d, eax
0x18005479a  lea     rdx, aFailedToAddThe; "Failed to add the ACL to the teredo.txt"...
0x1800547a1  mov     ecx, 100000h
0x1800547a6  call    EventWriteError0
0x1800547ab  mov     r9, cs:g_TeredoLock
0x1800547b2  lea     rdx, aTeredoqueryglo; "TeredoQueryGlobals"
0x1800547b9  mov     r8d, 0E0Fh
0x1800547bf  lea     rcx, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800547c6  call    GetAndTraceLock
0x1800547cb  test    eax, eax
0x1800547cd  jz      loc_180054890
0x1800547d3  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800547d8  mov     qword ptr [rsp+2C0h+dwCreationDisposition], 0; lpOverlapped
0x1800547e1  mov     r8d, 4; nNumberOfBytesToWrite
0x1800547e7  lea     rdx, dword_1800CA070; lpBuffer
0x1800547ee  mov     rcx, rbx; hFile
0x1800547f1  call    cs:__imp_WriteFile
0x1800547f8  nop     dword ptr [rax+rax+00h]
0x1800547fd  lea     r9, [rsp+2C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180054802  mov     qword ptr [rsp+2C0h+dwCreationDisposition], 0; lpOverlapped
0x18005480b  mov     r8d, 110h; nNumberOfBytesToWrite
0x180054811  lea     rdx, dword_1800CB7E8; lpBuffer
0x180054818  mov     rcx, rbx; hFile
0x18005481b  call    cs:__imp_WriteFile
0x180054822  nop     dword ptr [rax+rax+00h]
0x180054827  lea     r8, g_ProtocolStateTeredo
0x18005482e  mov     rdx, rbx
0x180054831  lea     rcx, TeredoCompartmentQueryGlobals
0x180054838  call    ForEachCompartment
0x18005483d  mov     rcx, rbx; hFile
0x180054840  call    cs:__imp_SetEndOfFile
0x180054847  nop     dword ptr [rax+rax+00h]
0x18005484c  test    eax, eax
0x18005484e  jnz     short loc_180054870
0x180054850  call    cs:__imp_GetLastError
0x180054857  nop     dword ptr [rax+rax+00h]
0x18005485c  lea     rdx, aFailToTruncate; "Fail to truncate current Teredo file %d"
0x180054863  mov     ecx, 800000h
0x180054868  mov     r8d, eax
0x18005486b  call    EventWrite0
0x180054870  mov     r9, cs:g_TeredoLock
0x180054877  lea     rdx, aTeredoqueryglo; "TeredoQueryGlobals"
0x18005487e  mov     r8d, 0E38h
0x180054884  lea     rcx, aOnecoreuapNetN_28; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005488b  call    ReleaseAndTraceLock
0x180054890  mov     rcx, rbx; hObject
0x180054893  call    cs:__imp_CloseHandle
0x18005489a  nop     dword ptr [rax+rax+00h]
0x18005489f  mov     rcx, rdi; hEvent
0x1800548a2  call    cs:__imp_SetEvent
0x1800548a9  nop     dword ptr [rax+rax+00h]
0x1800548ae  mov     rcx, rdi; hObject
0x1800548b1  call    cs:__imp_CloseHandle
0x1800548b8  nop     dword ptr [rax+rax+00h]
0x1800548bd  mov     r8d, 0E46h
0x1800548c3  lea     rdx, aOnecoreuapNetN_19; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800548ca  lea     rcx, aTeredoqueryglo; "TeredoQueryGlobals"
0x1800548d1  call    DereferenceServiceEx
0x1800548d6  mov     rcx, [rbp+1C0h+var_10]
0x1800548dd  xor     rcx, rsp; StackCookie
0x1800548e0  call    __security_check_cookie
0x1800548e5  lea     r11, [rsp+2C0h+var_s0]
0x1800548ed  mov     rbx, [r11+10h]
0x1800548f1  mov     rdi, [r11+20h]
0x1800548f5  mov     rsp, r11
0x1800548f8  pop     rbp
0x1800548f9  retn
```
