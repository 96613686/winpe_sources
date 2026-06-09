# CsvtaskHandler::FindAndScan(void)

- ea: `0x180001e98`
- end: `0x1800021f9`
- name: `?FindAndScan@CsvtaskHandler@@AEAAXXZ`
- size: `865`
- prototype: `void __fastcall(CsvtaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002530`

## callees

- `0x180001e98`
- `0x1800025d4`
- `0x180002728`
- `0x180002be0`
- `0x180003010`

## import_xrefs

- `msvcrt!free` at `0x18000204d`
- `msvcrt!free` at `0x18000204d`
- `msvcrt!realloc` at `0x180001ff5`
- `msvcrt!realloc` at `0x180001ff5`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180001fb7`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180001fb7`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180001fe2`
- `ADVAPI32!AdjustTokenPrivileges` at `0x180001fe2`
- `ADVAPI32!OpenProcessToken` at `0x180001f9c`
- `ADVAPI32!OpenProcessToken` at `0x180001f9c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001ee0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000205a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001ee0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000205a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001f1b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180002083`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001f1b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180002083`
- `KERNEL32!GetLastError` at `0x180002036`
- `KERNEL32!GetLastError` at `0x180002036`
- `KERNEL32!TlsAlloc` at `0x180001ef0`
- `KERNEL32!TlsAlloc` at `0x180001ef0`
- `KERNEL32!CloseHandle` at `0x18000203f`
- `KERNEL32!CloseHandle` at `0x18000203f`
- `KERNEL32!LoadLibraryW` at `0x1800020d6`
- `KERNEL32!LoadLibraryW` at `0x1800020d6`
- `KERNEL32!GetProcAddress` at `0x1800020ee`
- `KERNEL32!GetProcAddress` at `0x18000210a`
- `KERNEL32!GetProcAddress` at `0x180002123`
- `KERNEL32!GetProcAddress` at `0x18000213c`
- `KERNEL32!GetProcAddress` at `0x180002155`
- `KERNEL32!GetProcAddress` at `0x1800020ee`
- `KERNEL32!GetProcAddress` at `0x18000210a`
- `KERNEL32!GetProcAddress` at `0x180002123`
- `KERNEL32!GetProcAddress` at `0x18000213c`
- `KERNEL32!GetProcAddress` at `0x180002155`
- `KERNEL32!FreeLibrary` at `0x1800021c6`
- `KERNEL32!FreeLibrary` at `0x1800021ee`
- `KERNEL32!FreeLibrary` at `0x1800021c6`
- `KERNEL32!FreeLibrary` at `0x1800021ee`
- `KERNEL32!TlsSetValue` at `0x180001f08`
- `KERNEL32!TlsSetValue` at `0x180001f08`
- `KERNEL32!TlsFree` at `0x18000206f`
- `KERNEL32!TlsFree` at `0x18000206f`
- `KERNEL32!GetCurrentProcess` at `0x180001f8c`
- `KERNEL32!GetCurrentProcess` at `0x180001f8c`
- `KERNEL32!DeviceIoControl` at `0x18000202c`
- `KERNEL32!DeviceIoControl` at `0x18000202c`
- `KERNEL32!CreateFileW` at `0x180001f4c`
- `KERNEL32!CreateFileW` at `0x180001f4c`

## string_xrefs

- `0x1800020cf`: `FMIFS.DLL`
- `0x180002100`: `EnableVolumeCompression`
- `0x180001fb0`: `SeManageVolumePrivilege`

## pseudocode

```c
void __fastcall CsvtaskHandler::FindAndScan(CsvtaskHandler *this)
{
  DWORD v2; // eax
  HANDLE FileW; // r15
  void *v4; // r14
  HANDLE CurrentProcess; // rax
  _BYTE *v6; // rax
  _BYTE *v7; // rbx
  unsigned __int64 i; // rbx
  HMODULE LibraryW; // rax
  HMODULE v10; // rdi
  FARPROC ProcAddress; // r12
  CsvtaskHandler *v12; // rcx
  unsigned __int8 v13; // al
  CsvtaskHandler *v14; // rcx
  void *TokenHandle; // [rsp+40h] [rbp-79h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-71h] BYREF
  _OWORD v17[3]; // [rsp+50h] [rbp-69h] BYREF
  __int64 v18; // [rsp+80h] [rbp-39h]
  _LUID Luid[2]; // [rsp+88h] [rbp-31h] BYREF
  _OWORD InBuffer[2]; // [rsp+98h] [rbp-21h] BYREF
  int v21; // [rsp+B8h] [rbp-1h]

  v21 = 0;
  memset(InBuffer, 0, sizeof(InBuffer));
  BytesReturned = 0;
  AcquireSRWLockExclusive(&g_srwTLSChkDskThreadData);
  v2 = g_iTLSChkDskThreadData;
  if ( !g_iTLSChkDskThreadData )
  {
    v2 = TlsAlloc();
    g_iTLSChkDskThreadData = v2;
    g_cTLSChkDskThreadData = 0;
  }
  TlsSetValue(v2, this);
  ++g_cTLSChkDskThreadData;
  ReleaseSRWLockExclusive(&g_srwTLSChkDskThreadData);
  FileW = CreateFileW(L"\\\\.\\Ntfs", 0x80000000, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( FileW != (HANDLE)-1LL )
  {
    TokenHandle = 0;
    v21 = 0;
    *(_OWORD *)&Luid[0].LowPart = 0;
    v4 = 0;
    memset((char *)InBuffer + 8, 0, 24);
    *(_QWORD *)&InBuffer[0] = 0x2400000081LL;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
      LookupPrivilegeValueW(0, L"SeManageVolumePrivilege", (PLUID)&Luid[0].HighPart);
      Luid[0].LowPart = 1;
      Luid[1].HighPart = 2;
      if ( AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0) )
      {
        v6 = realloc(0, 0x400u);
        v7 = v6;
        if ( v6 )
        {
          v4 = v6;
          if ( DeviceIoControl(FileW, 0x90260u, InBuffer, 0x24u, v6, 0x400u, &BytesReturned, 0) )
          {
            if ( (v7[24] & 4) != 0 )
            {
              for ( i = (unsigned __int64)(v7 + 32); i < i + 1024 && *(_WORD *)(i + 10); i += *(unsigned __int16 *)(i + 8) )
              {
                if ( (*(_BYTE *)i & 4) != 0 )
                {
                  LibraryW = LoadLibraryW(L"FMIFS.DLL");
                  v10 = LibraryW;
                  if ( !LibraryW )
                    return;
                  ProcAddress = GetProcAddress(LibraryW, "ChkdskEx");
                  if ( !ProcAddress
                    || !GetProcAddress(v10, "EnableVolumeCompression")
                    || !GetProcAddress(v10, "FormatEx2")
                    || !GetProcAddress(v10, "GetDefaultFileSystem") )
                  {
                    FreeLibrary(v10);
                    return;
                  }
                  GetProcAddress(v10, "QueryCorruptionState");
                  v13 = CsvtaskHandler::_IncrementRetryCount(v12, (unsigned __int16 *)(i + 10));
                  v18 = 0;
                  memset(v17, 0, sizeof(v17));
                  DWORD1(v17[0]) = v13 != 0 ? -536838144 : -1610579968;
                  LOWORD(v17[0]) = 257;
                  ((void (__fastcall *)(unsigned __int64, const wchar_t *, _QWORD, _OWORD *, void *))ProcAddress)(
                    i + 10,
                    L"NTFS",
                    0,
                    v17,
                    &CsvtaskHandler::_FmifsCallback);
                  if ( *((_DWORD *)this + 14) != 10 )
                    CsvtaskHandler::_ClearRetryCount(v14, (unsigned __int16 *)(i + 10));
                  FreeLibrary(v10);
                }
              }
            }
          }
          else
          {
            GetLastError();
          }
        }
      }
    }
    CloseHandle(FileW);
    if ( v4 )
      free(v4);
  }
  AcquireSRWLockExclusive(&g_srwTLSChkDskThreadData);
  if ( !--g_cTLSChkDskThreadData )
  {
    TlsFree(g_iTLSChkDskThreadData);
    g_iTLSChkDskThreadData = 0;
  }
  ReleaseSRWLockExclusive(&g_srwTLSChkDskThreadData);
}

```

## disassembly

```asm
0x180001e98  push    rbp
0x180001e9a  push    rbx
0x180001e9b  push    rsi
0x180001e9c  push    rdi
0x180001e9d  push    r12
0x180001e9f  push    r13
0x180001ea1  push    r14
0x180001ea3  push    r15
0x180001ea5  lea     rbp, [rsp-1Fh]
0x180001eaa  sub     rsp, 0D8h
0x180001eb1  mov     rax, cs:__security_cookie
0x180001eb8  xor     rax, rsp
0x180001ebb  mov     [rbp+57h+var_50], rax
0x180001ebf  xorps   xmm0, xmm0
0x180001ec2  mov     r13, rcx
0x180001ec5  xor     eax, eax
0x180001ec7  lea     rcx, ?g_srwTLSChkDskThreadData@@3U_RTL_SRWLOCK@@A; SRWLock
0x180001ece  xor     r12d, r12d
0x180001ed1  mov     [rbp+57h+var_58], eax
0x180001ed4  movups  [rbp+57h+InBuffer], xmm0
0x180001ed8  mov     [rbp+57h+BytesReturned], r12d
0x180001edc  movups  [rbp+57h+var_68], xmm0
0x180001ee0  call    cs:__imp_AcquireSRWLockExclusive
0x180001ee6  mov     eax, cs:?g_iTLSChkDskThreadData@@3KA; ulong g_iTLSChkDskThreadData
0x180001eec  test    eax, eax
0x180001eee  jnz     short loc_180001F03
0x180001ef0  call    cs:__imp_TlsAlloc
0x180001ef6  mov     cs:?g_iTLSChkDskThreadData@@3KA, eax; ulong g_iTLSChkDskThreadData
0x180001efc  mov     cs:?g_cTLSChkDskThreadData@@3JA, r12d; long g_cTLSChkDskThreadData
0x180001f03  mov     rdx, r13; lpTlsValue
0x180001f06  mov     ecx, eax; dwTlsIndex
0x180001f08  call    cs:__imp_TlsSetValue
0x180001f0e  inc     cs:?g_cTLSChkDskThreadData@@3JA; long g_cTLSChkDskThreadData
0x180001f14  lea     rcx, ?g_srwTLSChkDskThreadData@@3U_RTL_SRWLOCK@@A; SRWLock
0x180001f1b  call    cs:__imp_ReleaseSRWLockExclusive
0x180001f21  mov     r8d, 3; dwShareMode
0x180001f27  mov     [rsp+110h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x180001f30  mov     [rsp+110h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180001f38  lea     rcx, FileName; "\\\\.\\Ntfs"
0x180001f3f  xor     r9d, r9d; lpSecurityAttributes
0x180001f42  mov     [rsp+110h+dwCreationDisposition], r8d; dwCreationDisposition
0x180001f47  mov     edx, 80000000h; dwDesiredAccess
0x180001f4c  call    cs:__imp_CreateFileW
0x180001f52  mov     r15, rax
0x180001f55  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001f59  jz      loc_180002053
0x180001f5f  xorps   xmm0, xmm0
0x180001f62  mov     [rbp+57h+TokenHandle], r12
0x180001f66  xorps   xmm1, xmm1
0x180001f69  mov     qword ptr [rbp+57h+var_68+8], r12
0x180001f6d  mov     esi, 24h ; '$'
0x180001f72  mov     [rbp+57h+var_58], r12d
0x180001f76  movups  xmmword ptr [rbp+57h+Luid.LowPart], xmm0
0x180001f7a  mov     dword ptr [rbp+57h+InBuffer+4], esi
0x180001f7d  mov     r14, r12
0x180001f80  movdqu  [rbp+57h+InBuffer+8], xmm1
0x180001f85  mov     dword ptr [rbp+57h+InBuffer], 81h
0x180001f8c  call    cs:__imp_GetCurrentProcess
0x180001f92  mov     rcx, rax; ProcessHandle
0x180001f95  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180001f99  lea     edx, [rsi+4]; DesiredAccess
0x180001f9c  call    cs:__imp_OpenProcessToken
0x180001fa2  test    eax, eax
0x180001fa4  jz      loc_18000203C
0x180001faa  lea     r8, [rbp+57h+Luid.HighPart]; lpLuid
0x180001fae  xor     ecx, ecx; lpSystemName
0x180001fb0  lea     rdx, Name; "SeManageVolumePrivilege"
0x180001fb7  call    cs:__imp_LookupPrivilegeValueW
0x180001fbd  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180001fc1  lea     r8, [rbp+57h+Luid]; NewState
0x180001fc5  xor     r9d, r9d; BufferLength
0x180001fc8  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r12; ReturnLength
0x180001fcd  xor     edx, edx; DisableAllPrivileges
0x180001fcf  mov     [rbp+57h+Luid.LowPart], 1
0x180001fd6  mov     [rbp+57h+Luid.HighPart+8], 2
0x180001fdd  mov     qword ptr [rsp+110h+dwCreationDisposition], r12; PreviousState
0x180001fe2  call    cs:__imp_AdjustTokenPrivileges
0x180001fe8  test    eax, eax
0x180001fea  jz      short loc_18000203C
0x180001fec  mov     edi, 400h
0x180001ff1  xor     ecx, ecx; Block
0x180001ff3  mov     edx, edi; Size
0x180001ff5  call    cs:__imp_realloc
0x180001ffb  mov     rbx, rax
0x180001ffe  test    rax, rax
0x180002001  jz      short loc_18000203C
0x180002003  mov     [rsp+110h+lpOverlapped], r12; lpOverlapped
0x180002008  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18000200c  mov     r14, rax
0x18000200f  mov     r9d, esi; nInBufferSize
0x180002012  lea     rax, [rbp+57h+BytesReturned]
0x180002016  mov     edx, 90260h; dwIoControlCode
0x18000201b  mov     [rsp+110h+hTemplateFile], rax; lpBytesReturned
0x180002020  mov     rcx, r15; hDevice
0x180002023  mov     [rsp+110h+dwFlagsAndAttributes], edi; nOutBufferSize
0x180002027  mov     qword ptr [rsp+110h+dwCreationDisposition], rbx; lpOutBuffer
0x18000202c  call    cs:__imp_DeviceIoControl
0x180002032  test    eax, eax
0x180002034  jnz     short loc_1800020A9
0x180002036  call    cs:__imp_GetLastError
0x18000203c  mov     rcx, r15; hObject
0x18000203f  call    cs:__imp_CloseHandle
0x180002045  test    r14, r14
0x180002048  jz      short loc_180002053
0x18000204a  mov     rcx, r14; Block
0x18000204d  call    cs:__imp_free
0x180002053  lea     rcx, ?g_srwTLSChkDskThreadData@@3U_RTL_SRWLOCK@@A; SRWLock
0x18000205a  call    cs:__imp_AcquireSRWLockExclusive
0x180002060  sub     cs:?g_cTLSChkDskThreadData@@3JA, 1; long g_cTLSChkDskThreadData
0x180002067  jnz     short loc_18000207C
0x180002069  mov     ecx, cs:?g_iTLSChkDskThreadData@@3KA; dwTlsIndex
0x18000206f  call    cs:__imp_TlsFree
0x180002075  mov     cs:?g_iTLSChkDskThreadData@@3KA, r12d; ulong g_iTLSChkDskThreadData
0x18000207c  lea     rcx, ?g_srwTLSChkDskThreadData@@3U_RTL_SRWLOCK@@A; SRWLock
0x180002083  call    cs:__imp_ReleaseSRWLockExclusive
0x180002089  mov     rcx, [rbp+57h+var_50]
0x18000208d  xor     rcx, rsp; StackCookie
0x180002090  call    __security_check_cookie
0x180002095  add     rsp, 0D8h
0x18000209c  pop     r15
0x18000209e  pop     r14
0x1800020a0  pop     r13
0x1800020a2  pop     r12
0x1800020a4  pop     rdi
0x1800020a5  pop     rsi
0x1800020a6  pop     rbx
0x1800020a7  pop     rbp
0x1800020a8  retn
0x1800020a9  test    byte ptr [rbx+18h], 4
0x1800020ad  jz      short loc_18000203C
0x1800020af  add     rbx, 20h ; ' '
0x1800020b3  jmp     loc_1800021D6
0x1800020b8  lea     rsi, [rbx+0Ah]
0x1800020bc  cmp     [rsi], r12w
0x1800020c0  jz      loc_18000203C
0x1800020c6  test    byte ptr [rbx], 4
0x1800020c9  jz      loc_1800021CF
0x1800020cf  lea     rcx, LibFileName; "FMIFS.DLL"
0x1800020d6  call    cs:__imp_LoadLibraryW
0x1800020dc  mov     rdi, rax
0x1800020df  test    rax, rax
0x1800020e2  jz      short loc_180002089
0x1800020e4  lea     rdx, ProcName; "ChkdskEx"
0x1800020eb  mov     rcx, rax; hModule
0x1800020ee  call    cs:__imp_GetProcAddress
0x1800020f4  mov     r12, rax
0x1800020f7  test    rax, rax
0x1800020fa  jz      loc_1800021EB
0x180002100  lea     rdx, aEnablevolumeco; "EnableVolumeCompression"
0x180002107  mov     rcx, rdi; hModule
0x18000210a  call    cs:__imp_GetProcAddress
0x180002110  test    rax, rax
0x180002113  jz      loc_1800021EB
0x180002119  lea     rdx, aFormatex2; "FormatEx2"
0x180002120  mov     rcx, rdi; hModule
0x180002123  call    cs:__imp_GetProcAddress
0x180002129  test    rax, rax
0x18000212c  jz      loc_1800021EB
0x180002132  lea     rdx, aGetdefaultfile; "GetDefaultFileSystem"
0x180002139  mov     rcx, rdi; hModule
0x18000213c  call    cs:__imp_GetProcAddress
0x180002142  test    rax, rax
0x180002145  jz      loc_1800021EB
0x18000214b  lea     rdx, aQuerycorruptio; "QueryCorruptionState"
0x180002152  mov     rcx, rdi; hModule
0x180002155  call    cs:__imp_GetProcAddress
0x18000215b  mov     rdx, rsi; unsigned __int16 *
0x18000215e  call    ?_IncrementRetryCount@CsvtaskHandler@@AEAAEPEAG@Z; CsvtaskHandler::_IncrementRetryCount(ushort *)
0x180002163  xor     ecx, ecx
0x180002165  lea     r9, [rbp+57h+var_C0]
0x180002169  neg     al
0x18000216b  mov     [rbp+57h+var_90], rcx
0x18000216f  xorps   xmm0, xmm0
0x180002172  lea     rdx, aNtfs; "NTFS"
0x180002179  sbb     eax, eax
0x18000217b  mov     rcx, rsi
0x18000217e  and     eax, 40000000h
0x180002183  xor     r8d, r8d
0x180002186  add     eax, 0A0008000h
0x18000218b  movups  [rbp+57h+var_C0], xmm0
0x18000218f  mov     dword ptr [rbp+57h+var_C0+4], eax
0x180002192  lea     rax, ?_FmifsCallback@CsvtaskHandler@@CAEW4_FMIFS_PACKET_TYPE@@KPEAX@Z; CsvtaskHandler::_FmifsCallback(_FMIFS_PACKET_TYPE,ulong,void *)
0x180002199  mov     qword ptr [rsp+110h+dwCreationDisposition], rax
0x18000219e  mov     rax, r12
0x1800021a1  movups  [rbp+57h+var_B0], xmm0
0x1800021a5  mov     word ptr [rbp+57h+var_C0], 101h
0x1800021ab  movups  [rbp+57h+var_A0], xmm0
0x1800021af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021b4  cmp     dword ptr [r13+38h], 0Ah
0x1800021b9  jz      short loc_1800021C3
0x1800021bb  mov     rdx, rsi; unsigned __int16 *
0x1800021be  call    ?_ClearRetryCount@CsvtaskHandler@@AEAAXPEAG@Z; CsvtaskHandler::_ClearRetryCount(ushort *)
0x1800021c3  mov     rcx, rdi; hLibModule
0x1800021c6  call    cs:__imp_FreeLibrary
0x1800021cc  xor     r12d, r12d
0x1800021cf  movzx   eax, word ptr [rbx+8]
0x1800021d3  add     rbx, rax
0x1800021d6  lea     rax, [rbx+400h]
0x1800021dd  cmp     rbx, rax
0x1800021e0  jb      loc_1800020B8
0x1800021e6  jmp     loc_18000203C
0x1800021eb  mov     rcx, rdi; hLibModule
0x1800021ee  call    cs:__imp_FreeLibrary
0x1800021f4  jmp     loc_180002089
```
