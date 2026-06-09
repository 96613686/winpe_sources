# NlDnsWriteLog(void)

- ea: `0x180024b90`
- end: `0x180024f2f`
- name: `?NlDnsWriteLog@@YAXXZ`
- size: `927`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800224e8`
- `0x180022d50`

## callees

- `0x180003340`
- `0x180007518`
- `0x18000e910`
- `0x180021e88`
- `0x1800247c4`
- `0x180024b90`
- `0x180041f80`
- `0x180091010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180024e10`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180024e3c`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180024e10`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180024e3c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180024ce8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180024ce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ea7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024ed9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024ed9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180024c79`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180024c79`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024d1f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024d1f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180024e6c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180024e6c`
- `ntdll!RtlLeaveCriticalSection` at `0x180024bda`
- `ntdll!RtlLeaveCriticalSection` at `0x180024eec`
- `ntdll!RtlLeaveCriticalSection` at `0x180024bda`
- `ntdll!RtlLeaveCriticalSection` at `0x180024eec`
- `ntdll!RtlEnterCriticalSection` at `0x180024bbe`
- `ntdll!RtlEnterCriticalSection` at `0x180024bbe`

## string_xrefs

- `0x180024c95`: `NlDnsWriteLog: Unable to GetSystemWindowsDirectoryW (%ld)\n`
- `0x180024cc3`: `NlDnsWriteLog: file name length is too long \n`
- `0x180024cd9`: `\system32\config\netlogon.dns`
- `0x180024d4a`: `NlDnsWriteLog: %ws: Unable to create file: %ld \n`
- `0x180024df0`: `NlDnsWriteLog: %ld: Invalid state\n`
- `0x180024eb6`: `NlDnsWriteLog: %ws: Unable to WriteFile. %ld\n`
- `0x180024e94`: `NlDnsWriteLog: %ws: Write bad byte count %ld s.b. %ld\n`

## pseudocode

```c
// bad sp value at call has been detected, the output may be wrong!
void NlDnsWriteLog(void)
{
  void *v0; // rsp
  _BYTE *v1; // rbx
  _DWORD *v2; // rax
  UINT SystemWindowsDirectoryW; // eax
  HANDLE FileW; // r15
  HLOCAL *v5; // rdi
  _BYTE *v6; // r14
  bool v7; // zf
  int v8; // ecx
  int v9; // ecx
  __int64 v10; // rsi
  __int64 v11; // [rsp-20h] [rbp-670h] BYREF
  DWORD dwCreationDisposition[2]; // [rsp+0h] [rbp-650h]
  int v13; // [rsp+20h] [rbp-630h]
  _BYTE v14[1512]; // [rsp+28h] [rbp-628h] BYREF
  unsigned __int8 v15[4]; // [rsp+650h] [rbp+0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+654h] [rbp+4h] BYREF
  unsigned __int16 *v17[2]; // [rsp+658h] [rbp+8h] BYREF

  *(_DWORD *)v15 = 0;
  RtlEnterCriticalSection(&NlGlobalDnsCritSect);
  if ( NlGlobalDnsListDirty )
  {
    if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x627
      || (unsigned __int64)(g_ulAdditionalProbeSize + 1583) < 0x627
      || !(unsigned int)VerifyStackAvailable()
      || (v0 = alloca(1584), &v11 == (__int64 *)-64LL)
      || (v13 = 1801679955, (v1 = v14) == 0) )
    {
      v2 = (_DWORD *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(1583);
      v1 = v2;
      if ( v2 )
      {
        *v2 = 1885431112;
        v1 = v2 + 2;
      }
    }
    if ( v1 )
    {
      NlDnsWriteBinaryLog();
      SystemWindowsDirectoryW = GetSystemWindowsDirectoryW((LPWSTR)v1, 0x20Au);
      if ( SystemWindowsDirectoryW )
      {
        if ( 2 * (unsigned __int64)SystemWindowsDirectoryW + 62 < 0x208 )
        {
          _o_wcscat_s(v1, 261, L"\\system32\\config\\netlogon.dns");
          FileW = CreateFileW((LPCWSTR)v1, 0xC0000000, 1u, 0, 2u, 0x80u, 0);
          if ( FileW == (HANDLE)-1LL )
          {
            *(_OWORD *)v17 = 0;
            *(_DWORD *)v15 = GetLastError();
            NlPrintRoutine(0x100u, L"NlDnsWriteLog: %ws: Unable to create file: %ld \n", v1, *(unsigned int *)v15);
            v17[1] = (unsigned __int16 *)*(unsigned int *)v15;
            v17[0] = (unsigned __int16 *)v1;
            NlpWriteEventlog(0x1690u, 1u, 0x40000000u, v17, 2u, v15, 4u);
          }
          else
          {
            v5 = (HLOCAL *)NlGlobalDnsList;
            v6 = v1 + 778;
            while ( v5 != &NlGlobalDnsList )
            {
              v7 = *((_DWORD *)v5 + 60) == 4;
              NumberOfBytesWritten = 0;
              if ( !v7 )
              {
                *v6 = 0;
                v8 = *((_DWORD *)v5 + 60);
                if ( v8 )
                {
                  v9 = v8 - 1;
                  if ( v9 )
                  {
                    if ( (unsigned int)(v9 - 1) >= 2 )
                      NlPrintRoutine(0x100u, L"NlDnsWriteLog: %ld: Invalid state\n");
                    _o_strcat_s(v1 + 778, 797, "; ");
                  }
                }
                NlDnsNameToStr((struct _NL_DNS_NAME *)v5, dword_1800F8158, v1 + 778);
                _o_strcat_s(v1 + 778, 797, "\r\n");
                v10 = -1;
                do
                  ++v10;
                while ( v6[v10] );
                if ( !WriteFile(FileW, v1 + 778, v10, &NumberOfBytesWritten, 0) )
                {
                  *(_DWORD *)v15 = GetLastError();
                  NlPrintRoutine(0x100u, L"NlDnsWriteLog: %ws: Unable to WriteFile. %ld\n", v1, *(unsigned int *)v15);
                  goto LABEL_34;
                }
                if ( NumberOfBytesWritten != (_DWORD)v10 )
                {
                  dwCreationDisposition[0] = v10;
                  NlPrintRoutine(0x100u, L"NlDnsWriteLog: %ws: Write bad byte count %ld s.b. %ld\n", v1);
                  goto LABEL_34;
                }
              }
              v5 = (HLOCAL *)*v5;
            }
            NlGlobalDnsListDirty = 0;
LABEL_34:
            CloseHandle(FileW);
          }
        }
        else
        {
          NlPrintRoutine(0x100u, L"NlDnsWriteLog: file name length is too long \n");
        }
      }
      else
      {
        *(_DWORD *)v15 = GetLastError();
        NlPrintRoutine(0x100u, L"NlDnsWriteLog: Unable to GetSystemWindowsDirectoryW (%ld)\n", *(unsigned int *)v15);
      }
    }
    else
    {
      *(_DWORD *)v15 = 8;
    }
    RtlLeaveCriticalSection(&NlGlobalDnsCritSect);
    if ( v1 )
    {
      if ( *((_DWORD *)v1 - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
    }
  }
  else
  {
    RtlLeaveCriticalSection(&NlGlobalDnsCritSect);
  }
}

```

## disassembly

```asm
0x180024b90  push    rbp
0x180024b92  push    rbx
0x180024b93  push    rsi
0x180024b94  push    rdi
0x180024b95  push    r14
0x180024b97  push    r15
0x180024b99  sub     rsp, 68h
0x180024b9d  lea     rbp, [rsp+40h]
0x180024ba2  mov     rax, cs:__security_cookie
0x180024ba9  xor     rax, rbp
0x180024bac  mov     [rbp+50h+var_38], rax
0x180024bb0  lea     rcx, ?NlGlobalDnsCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180024bb7  mov     dword ptr [rbp+50h+var_50], 0
0x180024bbe  call    cs:__imp_RtlEnterCriticalSection
0x180024bc5  nop     dword ptr [rax+rax+00h]
0x180024bca  cmp     cs:?NlGlobalDnsListDirty@@3EA, 0; uchar NlGlobalDnsListDirty
0x180024bd1  jnz     short loc_180024BEB
0x180024bd3  lea     rcx, ?NlGlobalDnsCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180024bda  call    cs:__imp_RtlLeaveCriticalSection
0x180024be1  nop     dword ptr [rax+rax+00h]
0x180024be6  jmp     loc_180024F15
0x180024beb  mov     edx, 627h
0x180024bf0  cmp     cs:g_ulMaxStackAllocSize, rdx
0x180024bf7  jb      short loc_180024C38
0x180024bf9  mov     rcx, cs:g_ulAdditionalProbeSize
0x180024c00  add     rcx, 62Fh
0x180024c07  cmp     rcx, rdx
0x180024c0a  jb      short loc_180024C38
0x180024c0c  call    VerifyStackAvailable
0x180024c11  test    eax, eax
0x180024c13  jz      short loc_180024C38
0x180024c15  mov     eax, [rsp+90h+var_90]
0x180024c18  mov     eax, 630h
0x180024c1d  sub     rsp, rax
0x180024c20  lea     rbx, [rsp+6C0h+var_680]
0x180024c25  mov     eax, [rbx]
0x180024c27  test    rbx, rbx
0x180024c2a  jz      short loc_180024C38
0x180024c2c  mov     dword ptr [rbx], 6B637453h
0x180024c32  add     rbx, 8
0x180024c36  jnz     short loc_180024C5B
0x180024c38  mov     rax, cs:g_pfnAllocate
0x180024c3f  mov     ecx, 62Fh
0x180024c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c49  mov     rbx, rax
0x180024c4c  test    rax, rax
0x180024c4f  jz      short loc_180024C5B
0x180024c51  mov     dword ptr [rax], 70616548h
0x180024c57  add     rbx, 8
0x180024c5b  test    rbx, rbx
0x180024c5e  jnz     short loc_180024C6C
0x180024c60  mov     dword ptr [rbp+50h+var_50], 8
0x180024c67  jmp     loc_180024EE5
0x180024c6c  call    ?NlDnsWriteBinaryLog@@YAXXZ; NlDnsWriteBinaryLog(void)
0x180024c71  mov     edx, 20Ah; uSize
0x180024c76  mov     rcx, rbx; lpBuffer
0x180024c79  call    cs:__imp_GetSystemWindowsDirectoryW
0x180024c80  nop     dword ptr [rax+rax+00h]
0x180024c85  test    eax, eax
0x180024c87  jnz     short loc_180024CB1
0x180024c89  call    cs:__imp_GetLastError
0x180024c90  nop     dword ptr [rax+rax+00h]
0x180024c95  lea     rdx, aNldnswritelogU; "NlDnsWriteLog: Unable to GetSystemWindo"...
0x180024c9c  mov     ecx, 100h; unsigned int
0x180024ca1  mov     r8d, eax
0x180024ca4  mov     dword ptr [rbp+50h+var_50], eax
0x180024ca7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180024cac  jmp     loc_180024EE5
0x180024cb1  mov     eax, eax
0x180024cb3  lea     rax, ds:3Eh[rax*2]
0x180024cbb  cmp     rax, 208h
0x180024cc1  jb      short loc_180024CD9
0x180024cc3  lea     rdx, aNldnswritelogF; "NlDnsWriteLog: file name length is too "...
0x180024cca  mov     ecx, 100h; unsigned int
0x180024ccf  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180024cd4  jmp     loc_180024EE5
0x180024cd9  lea     r8, aSystem32Config_2; "\\system32\\config\\netlogon.dns"
0x180024ce0  mov     edx, 105h
0x180024ce5  mov     rcx, rbx
0x180024ce8  call    cs:__imp__o_wcscat_s
0x180024cef  nop     dword ptr [rax+rax+00h]
0x180024cf4  mov     edi, 2
0x180024cf9  mov     [rsp+6C0h+hTemplateFile], 0; hTemplateFile
0x180024d02  mov     [rsp+6C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180024d0a  xor     r9d, r9d; lpSecurityAttributes
0x180024d0d  mov     edx, 0C0000000h; dwDesiredAccess
0x180024d12  mov     [rsp+6C0h+dwCreationDisposition], edi; dwCreationDisposition
0x180024d16  mov     rcx, rbx; lpFileName
0x180024d19  lea     esi, [rdi-1]
0x180024d1c  mov     r8d, esi; dwShareMode
0x180024d1f  call    cs:__imp_CreateFileW
0x180024d26  nop     dword ptr [rax+rax+00h]
0x180024d2b  mov     r15, rax
0x180024d2e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024d32  jnz     short loc_180024D9C
0x180024d34  xorps   xmm0, xmm0
0x180024d37  movups  xmmword ptr [rbp+50h+var_48], xmm0
0x180024d3b  call    cs:__imp_GetLastError
0x180024d42  nop     dword ptr [rax+rax+00h]
0x180024d47  mov     r8, rbx
0x180024d4a  lea     rdx, aNldnswritelogW; "NlDnsWriteLog: %ws: Unable to create fi"...
0x180024d51  mov     r9d, eax
0x180024d54  mov     dword ptr [rbp+50h+var_50], eax
0x180024d57  mov     ecx, 100h; unsigned int
0x180024d5c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180024d61  mov     eax, dword ptr [rbp+50h+var_50]
0x180024d64  lea     r9, [rbp+50h+var_48]; unsigned __int16 **
0x180024d68  mov     [rbp+50h+var_48+8], rax
0x180024d6c  mov     r8d, 40000000h; unsigned int
0x180024d72  lea     rax, [rbp+50h+var_50]
0x180024d76  mov     dword ptr [rsp+6C0h+hTemplateFile], 4; unsigned int
0x180024d7e  mov     qword ptr [rsp+6C0h+dwFlagsAndAttributes], rax; unsigned __int8 *
0x180024d83  mov     edx, esi; unsigned int
0x180024d85  mov     ecx, 1690h; unsigned int
0x180024d8a  mov     [rsp+6C0h+dwCreationDisposition], edi; unsigned int
0x180024d8e  mov     [rbp+50h+var_48], rbx
0x180024d92  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x180024d97  jmp     loc_180024EE5
0x180024d9c  mov     rdi, cs:?NlGlobalDnsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalDnsList
0x180024da3  lea     r14, [rbx+30Ah]
0x180024daa  lea     rax, ?NlGlobalDnsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalDnsList
0x180024db1  cmp     rdi, rax
0x180024db4  jz      loc_180024ECF
0x180024dba  cmp     dword ptr [rdi+0F0h], 4
0x180024dc1  mov     [rbp+50h+NumberOfBytesWritten], 0
0x180024dc8  jz      loc_180024E85
0x180024dce  mov     byte ptr [r14], 0
0x180024dd2  mov     r8d, [rdi+0F0h]
0x180024dd9  mov     ecx, r8d
0x180024ddc  test    r8d, r8d
0x180024ddf  jz      short loc_180024E1C
0x180024de1  sub     ecx, 1
0x180024de4  jz      short loc_180024E1C
0x180024de6  sub     ecx, 1
0x180024de9  jz      short loc_180024E01
0x180024deb  cmp     ecx, 1
0x180024dee  jz      short loc_180024E01
0x180024df0  lea     rdx, aNldnswritelogL; "NlDnsWriteLog: %ld: Invalid state\n"
0x180024df7  mov     ecx, 100h; unsigned int
0x180024dfc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180024e01  lea     r8, asc_18009F128; "; "
0x180024e08  mov     edx, 31Dh
0x180024e0d  mov     rcx, r14
0x180024e10  call    cs:__imp__o_strcat_s
0x180024e17  nop     dword ptr [rax+rax+00h]
0x180024e1c  mov     edx, cs:dword_1800F8158; unsigned int
0x180024e22  mov     r8, r14; char *
0x180024e25  mov     rcx, rdi; struct _NL_DNS_NAME *
0x180024e28  call    ?NlDnsNameToStr@@YAXPEAU_NL_DNS_NAME@@KQEAD@Z; NlDnsNameToStr(_NL_DNS_NAME *,ulong,char * const)
0x180024e2d  lea     r8, asc_18009F12C; "\r\n"
0x180024e34  mov     edx, 31Dh
0x180024e39  mov     rcx, r14
0x180024e3c  call    cs:__imp__o_strcat_s
0x180024e43  nop     dword ptr [rax+rax+00h]
0x180024e48  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180024e4c  inc     rsi
0x180024e4f  cmp     byte ptr [r14+rsi], 0
0x180024e54  jnz     short loc_180024E4C
0x180024e56  lea     r9, [rbp+50h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180024e5a  mov     qword ptr [rsp+6C0h+dwCreationDisposition], 0; lpOverlapped
0x180024e63  mov     r8d, esi; nNumberOfBytesToWrite
0x180024e66  mov     rdx, r14; lpBuffer
0x180024e69  mov     rcx, r15; hFile
0x180024e6c  call    cs:__imp_WriteFile
0x180024e73  nop     dword ptr [rax+rax+00h]
0x180024e78  test    eax, eax
0x180024e7a  jz      short loc_180024EA7
0x180024e7c  mov     r9d, [rbp+50h+NumberOfBytesWritten]
0x180024e80  cmp     r9d, esi
0x180024e83  jnz     short loc_180024E8D
0x180024e85  mov     rdi, [rdi]
0x180024e88  jmp     loc_180024DAA
0x180024e8d  mov     r8, rbx
0x180024e90  mov     [rsp+6C0h+dwCreationDisposition], esi
0x180024e94  lea     rdx, aNldnswritelogW_1; "NlDnsWriteLog: %ws: Write bad byte coun"...
0x180024e9b  mov     ecx, 100h; unsigned int
0x180024ea0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180024ea5  jmp     short loc_180024ED6
0x180024ea7  call    cs:__imp_GetLastError
0x180024eae  nop     dword ptr [rax+rax+00h]
0x180024eb3  mov     r8, rbx
0x180024eb6  lea     rdx, aNldnswritelogW_0; "NlDnsWriteLog: %ws: Unable to WriteFile"...
0x180024ebd  mov     r9d, eax
0x180024ec0  mov     dword ptr [rbp+50h+var_50], eax
0x180024ec3  mov     ecx, 100h; unsigned int
0x180024ec8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180024ecd  jmp     short loc_180024ED6
0x180024ecf  mov     cs:?NlGlobalDnsListDirty@@3EA, 0; uchar NlGlobalDnsListDirty
0x180024ed6  mov     rcx, r15; hObject
0x180024ed9  call    cs:__imp_CloseHandle
0x180024ee0  nop     dword ptr [rax+rax+00h]
0x180024ee5  lea     rcx, ?NlGlobalDnsCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180024eec  call    cs:__imp_RtlLeaveCriticalSection
0x180024ef3  nop     dword ptr [rax+rax+00h]
0x180024ef8  test    rbx, rbx
0x180024efb  jz      short loc_180024F15
0x180024efd  lea     rcx, [rbx-8]
0x180024f01  cmp     dword ptr [rcx], 70616548h
0x180024f07  jnz     short loc_180024F15
0x180024f09  mov     rax, cs:g_pfnFree
0x180024f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f15  mov     rcx, [rbp+50h+var_38]
0x180024f19  xor     rcx, rbp; StackCookie
0x180024f1c  call    __security_check_cookie
0x180024f21  lea     rsp, [rbp+28h]
0x180024f25  pop     r15
0x180024f27  pop     r14
0x180024f29  pop     rdi
0x180024f2a  pop     rsi
0x180024f2b  pop     rbx
0x180024f2c  pop     rbp
0x180024f2d  retn
```
