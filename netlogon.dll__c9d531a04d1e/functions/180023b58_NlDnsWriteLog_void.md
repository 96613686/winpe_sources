# NlDnsWriteLog(void)

- ea: `0x180023b58`
- end: `0x180023ea8`
- name: `?NlDnsWriteLog@@YAXXZ`
- size: `848`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800214d8`
- `0x180021cd0`

## callees

- `0x180003220`
- `0x180007278`
- `0x18000e270`
- `0x180020f04`
- `0x1800237b4`
- `0x180023b58`
- `0x18003f648`
- `0x18008a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180023dae`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180023dd4`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180023dae`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180023dd4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180023c98`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180023c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023cdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023cdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023e5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180023c35`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180023c35`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023cc9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023cc9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180023dfe`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180023dfe`
- `ntdll!RtlLeaveCriticalSection` at `0x180023b9c`
- `ntdll!RtlLeaveCriticalSection` at `0x180023e6c`
- `ntdll!RtlLeaveCriticalSection` at `0x180023b9c`
- `ntdll!RtlLeaveCriticalSection` at `0x180023e6c`
- `ntdll!RtlEnterCriticalSection` at `0x180023b86`
- `ntdll!RtlEnterCriticalSection` at `0x180023b86`

## string_xrefs

- `0x180023c45`: `NlDnsWriteLog: Unable to GetSystemWindowsDirectoryW (%ld)\n`
- `0x180023c73`: `NlDnsWriteLog: file name length is too long \n`
- `0x180023c89`: `\system32\config\netlogon.dns`
- `0x180023ce8`: `NlDnsWriteLog: %ws: Unable to create file: %ld \n`
- `0x180023d8e`: `NlDnsWriteLog: %ld: Invalid state\n`
- `0x180023e3c`: `NlDnsWriteLog: %ws: Unable to WriteFile. %ld\n`
- `0x180023e20`: `NlDnsWriteLog: %ws: Write bad byte count %ld s.b. %ld\n`

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
                NlDnsNameToStr((struct _NL_DNS_NAME *)v5, dword_1800F1158, v1 + 778);
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
0x180023b58  push    rbp
0x180023b5a  push    rbx
0x180023b5b  push    rsi
0x180023b5c  push    rdi
0x180023b5d  push    r14
0x180023b5f  push    r15
0x180023b61  sub     rsp, 68h
0x180023b65  lea     rbp, [rsp+40h]
0x180023b6a  mov     rax, cs:__security_cookie
0x180023b71  xor     rax, rbp
0x180023b74  mov     [rbp+50h+var_38], rax
0x180023b78  lea     rcx, ?NlGlobalDnsCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180023b7f  mov     dword ptr [rbp+50h+var_50], 0
0x180023b86  call    cs:__imp_RtlEnterCriticalSection
0x180023b8c  cmp     cs:?NlGlobalDnsListDirty@@3EA, 0; uchar NlGlobalDnsListDirty
0x180023b93  jnz     short loc_180023BA7
0x180023b95  lea     rcx, ?NlGlobalDnsCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180023b9c  call    cs:__imp_RtlLeaveCriticalSection
0x180023ba2  jmp     loc_180023E8F
0x180023ba7  mov     edx, 627h
0x180023bac  cmp     cs:g_ulMaxStackAllocSize, rdx
0x180023bb3  jb      short loc_180023BF4
0x180023bb5  mov     rcx, cs:g_ulAdditionalProbeSize
0x180023bbc  add     rcx, 62Fh
0x180023bc3  cmp     rcx, rdx
0x180023bc6  jb      short loc_180023BF4
0x180023bc8  call    VerifyStackAvailable
0x180023bcd  test    eax, eax
0x180023bcf  jz      short loc_180023BF4
0x180023bd1  mov     eax, [rsp+90h+var_90]
0x180023bd4  mov     eax, 630h
0x180023bd9  sub     rsp, rax
0x180023bdc  lea     rbx, [rsp+6C0h+var_680]
0x180023be1  mov     eax, [rbx]
0x180023be3  test    rbx, rbx
0x180023be6  jz      short loc_180023BF4
0x180023be8  mov     dword ptr [rbx], 6B637453h
0x180023bee  add     rbx, 8
0x180023bf2  jnz     short loc_180023C17
0x180023bf4  mov     rax, cs:g_pfnAllocate
0x180023bfb  mov     ecx, 62Fh
0x180023c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c05  mov     rbx, rax
0x180023c08  test    rax, rax
0x180023c0b  jz      short loc_180023C17
0x180023c0d  mov     dword ptr [rax], 70616548h
0x180023c13  add     rbx, 8
0x180023c17  test    rbx, rbx
0x180023c1a  jnz     short loc_180023C28
0x180023c1c  mov     dword ptr [rbp+50h+var_50], 8
0x180023c23  jmp     loc_180023E65
0x180023c28  call    ?NlDnsWriteBinaryLog@@YAXXZ; NlDnsWriteBinaryLog(void)
0x180023c2d  mov     edx, 20Ah; uSize
0x180023c32  mov     rcx, rbx; lpBuffer
0x180023c35  call    cs:__imp_GetSystemWindowsDirectoryW
0x180023c3b  test    eax, eax
0x180023c3d  jnz     short loc_180023C61
0x180023c3f  call    cs:__imp_GetLastError
0x180023c45  lea     rdx, aNldnswritelogU; "NlDnsWriteLog: Unable to GetSystemWindo"...
0x180023c4c  mov     ecx, 100h; unsigned int
0x180023c51  mov     r8d, eax
0x180023c54  mov     dword ptr [rbp+50h+var_50], eax
0x180023c57  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180023c5c  jmp     loc_180023E65
0x180023c61  mov     eax, eax
0x180023c63  lea     rax, ds:3Eh[rax*2]
0x180023c6b  cmp     rax, 208h
0x180023c71  jb      short loc_180023C89
0x180023c73  lea     rdx, aNldnswritelogF; "NlDnsWriteLog: file name length is too "...
0x180023c7a  mov     ecx, 100h; unsigned int
0x180023c7f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180023c84  jmp     loc_180023E65
0x180023c89  lea     r8, aSystem32Config_2; "\\system32\\config\\netlogon.dns"
0x180023c90  mov     edx, 105h
0x180023c95  mov     rcx, rbx
0x180023c98  call    cs:__imp__o_wcscat_s
0x180023c9e  mov     edi, 2
0x180023ca3  mov     [rsp+6C0h+hTemplateFile], 0; hTemplateFile
0x180023cac  mov     [rsp+6C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180023cb4  xor     r9d, r9d; lpSecurityAttributes
0x180023cb7  mov     edx, 0C0000000h; dwDesiredAccess
0x180023cbc  mov     [rsp+6C0h+dwCreationDisposition], edi; dwCreationDisposition
0x180023cc0  mov     rcx, rbx; lpFileName
0x180023cc3  lea     esi, [rdi-1]
0x180023cc6  mov     r8d, esi; dwShareMode
0x180023cc9  call    cs:__imp_CreateFileW
0x180023ccf  mov     r15, rax
0x180023cd2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023cd6  jnz     short loc_180023D3A
0x180023cd8  xorps   xmm0, xmm0
0x180023cdb  movups  xmmword ptr [rbp+50h+var_48], xmm0
0x180023cdf  call    cs:__imp_GetLastError
0x180023ce5  mov     r8, rbx
0x180023ce8  lea     rdx, aNldnswritelogW; "NlDnsWriteLog: %ws: Unable to create fi"...
0x180023cef  mov     r9d, eax
0x180023cf2  mov     dword ptr [rbp+50h+var_50], eax
0x180023cf5  mov     ecx, 100h; unsigned int
0x180023cfa  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180023cff  mov     eax, dword ptr [rbp+50h+var_50]
0x180023d02  lea     r9, [rbp+50h+var_48]; unsigned __int16 **
0x180023d06  mov     [rbp+50h+var_48+8], rax
0x180023d0a  mov     r8d, 40000000h; unsigned int
0x180023d10  lea     rax, [rbp+50h+var_50]
0x180023d14  mov     dword ptr [rsp+6C0h+hTemplateFile], 4; unsigned int
0x180023d1c  mov     qword ptr [rsp+6C0h+dwFlagsAndAttributes], rax; unsigned __int8 *
0x180023d21  mov     edx, esi; unsigned int
0x180023d23  mov     ecx, 1690h; unsigned int
0x180023d28  mov     [rsp+6C0h+dwCreationDisposition], edi; unsigned int
0x180023d2c  mov     [rbp+50h+var_48], rbx
0x180023d30  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x180023d35  jmp     loc_180023E65
0x180023d3a  mov     rdi, cs:?NlGlobalDnsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalDnsList
0x180023d41  lea     r14, [rbx+30Ah]
0x180023d48  lea     rax, ?NlGlobalDnsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalDnsList
0x180023d4f  cmp     rdi, rax
0x180023d52  jz      loc_180023E55
0x180023d58  cmp     dword ptr [rdi+0F0h], 4
0x180023d5f  mov     [rbp+50h+NumberOfBytesWritten], 0
0x180023d66  jz      loc_180023E11
0x180023d6c  mov     byte ptr [r14], 0
0x180023d70  mov     r8d, [rdi+0F0h]
0x180023d77  mov     ecx, r8d
0x180023d7a  test    r8d, r8d
0x180023d7d  jz      short loc_180023DB4
0x180023d7f  sub     ecx, 1
0x180023d82  jz      short loc_180023DB4
0x180023d84  sub     ecx, 1
0x180023d87  jz      short loc_180023D9F
0x180023d89  cmp     ecx, 1
0x180023d8c  jz      short loc_180023D9F
0x180023d8e  lea     rdx, aNldnswritelogL; "NlDnsWriteLog: %ld: Invalid state\n"
0x180023d95  mov     ecx, 100h; unsigned int
0x180023d9a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180023d9f  lea     r8, asc_180098118; "; "
0x180023da6  mov     edx, 31Dh
0x180023dab  mov     rcx, r14
0x180023dae  call    cs:__imp__o_strcat_s
0x180023db4  mov     edx, cs:dword_1800F1158; unsigned int
0x180023dba  mov     r8, r14; char *
0x180023dbd  mov     rcx, rdi; struct _NL_DNS_NAME *
0x180023dc0  call    ?NlDnsNameToStr@@YAXPEAU_NL_DNS_NAME@@KQEAD@Z; NlDnsNameToStr(_NL_DNS_NAME *,ulong,char * const)
0x180023dc5  lea     r8, asc_18009811C; "\r\n"
0x180023dcc  mov     edx, 31Dh
0x180023dd1  mov     rcx, r14
0x180023dd4  call    cs:__imp__o_strcat_s
0x180023dda  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180023dde  inc     rsi
0x180023de1  cmp     byte ptr [r14+rsi], 0
0x180023de6  jnz     short loc_180023DDE
0x180023de8  lea     r9, [rbp+50h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180023dec  mov     qword ptr [rsp+6C0h+dwCreationDisposition], 0; lpOverlapped
0x180023df5  mov     r8d, esi; nNumberOfBytesToWrite
0x180023df8  mov     rdx, r14; lpBuffer
0x180023dfb  mov     rcx, r15; hFile
0x180023dfe  call    cs:__imp_WriteFile
0x180023e04  test    eax, eax
0x180023e06  jz      short loc_180023E33
0x180023e08  mov     r9d, [rbp+50h+NumberOfBytesWritten]
0x180023e0c  cmp     r9d, esi
0x180023e0f  jnz     short loc_180023E19
0x180023e11  mov     rdi, [rdi]
0x180023e14  jmp     loc_180023D48
0x180023e19  mov     r8, rbx
0x180023e1c  mov     [rsp+6C0h+dwCreationDisposition], esi
0x180023e20  lea     rdx, aNldnswritelogW_1; "NlDnsWriteLog: %ws: Write bad byte coun"...
0x180023e27  mov     ecx, 100h; unsigned int
0x180023e2c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180023e31  jmp     short loc_180023E5C
0x180023e33  call    cs:__imp_GetLastError
0x180023e39  mov     r8, rbx
0x180023e3c  lea     rdx, aNldnswritelogW_0; "NlDnsWriteLog: %ws: Unable to WriteFile"...
0x180023e43  mov     r9d, eax
0x180023e46  mov     dword ptr [rbp+50h+var_50], eax
0x180023e49  mov     ecx, 100h; unsigned int
0x180023e4e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180023e53  jmp     short loc_180023E5C
0x180023e55  mov     cs:?NlGlobalDnsListDirty@@3EA, 0; uchar NlGlobalDnsListDirty
0x180023e5c  mov     rcx, r15; hObject
0x180023e5f  call    cs:__imp_CloseHandle
0x180023e65  lea     rcx, ?NlGlobalDnsCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180023e6c  call    cs:__imp_RtlLeaveCriticalSection
0x180023e72  test    rbx, rbx
0x180023e75  jz      short loc_180023E8F
0x180023e77  lea     rcx, [rbx-8]
0x180023e7b  cmp     dword ptr [rcx], 70616548h
0x180023e81  jnz     short loc_180023E8F
0x180023e83  mov     rax, cs:g_pfnFree
0x180023e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e8f  mov     rcx, [rbp+50h+var_38]
0x180023e93  xor     rcx, rbp; StackCookie
0x180023e96  call    __security_check_cookie
0x180023e9b  lea     rsp, [rbp+28h]
0x180023e9f  pop     r15
0x180023ea1  pop     r14
0x180023ea3  pop     rdi
0x180023ea4  pop     rsi
0x180023ea5  pop     rbx
0x180023ea6  pop     rbp
0x180023ea7  retn
```
