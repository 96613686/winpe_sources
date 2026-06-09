# ILOG_FILE::OpenFile(char const *,int)

- ea: `0x18000d2f8`
- end: `0x18000d41c`
- name: `?OpenFile@ILOG_FILE@@AEAAHPEBDH@Z`
- size: `292`
- prototype: `__int64 __fastcall(union _ULARGE_INTEGER *this, LPCSTR lpFileName, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000d22c`

## callees

- `0x18000d0e0`
- `0x18000d13c`
- `0x18000d2f8`
- `0x18000d424`

## import_xrefs

- `IisRTL!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z` at `0x18000d38c`
- `IisRTL!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z` at `0x18000d38c`
- `KERNEL32!SetLastError` at `0x18000d394`
- `KERNEL32!SetLastError` at `0x18000d394`
- `KERNEL32!GetLastError` at `0x18000d35b`
- `KERNEL32!GetLastError` at `0x18000d39e`
- `KERNEL32!GetLastError` at `0x18000d3fa`
- `KERNEL32!GetLastError` at `0x18000d35b`
- `KERNEL32!GetLastError` at `0x18000d39e`
- `KERNEL32!GetLastError` at `0x18000d3fa`
- `KERNEL32!CreateFileA` at `0x18000d34c`
- `KERNEL32!CreateFileA` at `0x18000d34c`

## pseudocode

```c
__int64 __fastcall ILOG_FILE::OpenFile(union _ULARGE_INTEGER *this, LPCSTR lpFileName, int a3)
{
  union _ULARGE_INTEGER *v4; // rdi
  HANDLE FileA; // rax
  DWORD LastError; // eax
  DWORD v9; // ebx
  DWORD v10; // ecx
  union _ULARGE_INTEGER v12; // r8
  union _ULARGE_INTEGER v13; // rcx
  DWORD LowPart; // edx
  DWORD v15; // edi
  unsigned __int64 HighPart; // [rsp+70h] [rbp+8h] BYREF

  this[3].QuadPart = 0;
  v4 = this + 5;
  this[4].LowPart = 0;
  this[5].QuadPart = 0;
  FileA = CreateFileA(lpFileName, 0xC0000000, 3u, 0, 4u, 0x8000080u, 0);
  this->QuadPart = (ULONGLONG)FileA;
  if ( FileA == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( g_eventLog )
    {
      if ( a3 )
      {
        HighPart = (unsigned __int64)lpFileName;
        EVENT_LOG::LogEvent((EVENT_LOG *)g_eventLog, 0xC0000003, 1u, (const char **const)&HighPart, LastError);
      }
    }
    v10 = v9;
    goto LABEL_6;
  }
  if ( GetLastError() == 183 )
  {
    if ( !(unsigned int)ILOG_FILE::PositionToEOF((ILOG_FILE *)this, v4) )
    {
LABEL_14:
      v15 = GetLastError();
      ILOG_FILE::CloseFile((ILOG_FILE *)this);
      v10 = v15;
LABEL_6:
      SetLastError(v10);
      return 0;
    }
    v12 = *v4;
    v13 = this[7];
    HighPart = this[2].HighPart;
    if ( v12.QuadPart >= v13.QuadPart )
    {
      LowPart = this[2].LowPart;
      do
      {
        v13.QuadPart += HighPart;
        ++LowPart;
      }
      while ( v12.QuadPart >= v13.QuadPart );
      this[2].LowPart = LowPart;
      this[7] = v13;
    }
  }
  if ( !(unsigned int)ILOG_FILE::CreateMapping((ILOG_FILE *)this) )
    goto LABEL_14;
  return 1;
}

```

## disassembly

```asm
0x18000d2f8  push    rbx
0x18000d2fa  push    rbp
0x18000d2fb  push    rsi
0x18000d2fc  push    rdi
0x18000d2fd  sub     rsp, 48h
0x18000d301  mov     rsi, rdx
0x18000d304  mov     qword ptr [rcx+18h], 0
0x18000d30c  lea     rdi, [rcx+28h]
0x18000d310  mov     dword ptr [rcx+20h], 0
0x18000d317  xor     r9d, r9d; lpSecurityAttributes
0x18000d31a  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18000d323  mov     ebp, r8d
0x18000d326  mov     [rsp+68h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x18000d32e  mov     rbx, rcx
0x18000d331  mov     qword ptr [rdi], 0
0x18000d338  mov     edx, 0C0000000h; dwDesiredAccess
0x18000d33d  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x18000d345  lea     r8d, [r9+3]; dwShareMode
0x18000d349  mov     rcx, rsi; lpFileName
0x18000d34c  call    cs:__imp_CreateFileA
0x18000d352  mov     [rbx], rax
0x18000d355  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d359  jnz     short loc_18000D39E
0x18000d35b  call    cs:__imp_GetLastError
0x18000d361  mov     rcx, cs:?g_eventLog@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_eventLog
0x18000d368  mov     ebx, eax
0x18000d36a  test    rcx, rcx
0x18000d36d  jz      short loc_18000D392
0x18000d36f  test    ebp, ebp
0x18000d371  jz      short loc_18000D392
0x18000d373  mov     r8d, 1
0x18000d379  mov     [rsp+68h+arg_0], rsi
0x18000d37e  lea     r9, [rsp+68h+arg_0]
0x18000d383  mov     [rsp+68h+dwCreationDisposition], eax
0x18000d387  mov     edx, 0C0000003h
0x18000d38c  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBDK@Z; EVENT_LOG::LogEvent(ulong,ushort,char const * * const,ulong)
0x18000d392  mov     ecx, ebx; dwErrCode
0x18000d394  call    cs:__imp_SetLastError
0x18000d39a  xor     eax, eax
0x18000d39c  jmp     short loc_18000D413
0x18000d39e  call    cs:__imp_GetLastError
0x18000d3a4  cmp     eax, 0B7h
0x18000d3a9  jnz     short loc_18000D3EE
0x18000d3ab  mov     rdx, rdi; union _ULARGE_INTEGER *
0x18000d3ae  mov     rcx, rbx; this
0x18000d3b1  call    ?PositionToEOF@ILOG_FILE@@AEAAHPEAT_ULARGE_INTEGER@@@Z; ILOG_FILE::PositionToEOF(_ULARGE_INTEGER *)
0x18000d3b6  test    eax, eax
0x18000d3b8  jz      short loc_18000D3FA
0x18000d3ba  mov     r8, [rdi]
0x18000d3bd  mov     rcx, [rbx+38h]
0x18000d3c1  mov     eax, [rbx+14h]
0x18000d3c4  mov     dword ptr [rsp+68h+arg_0+4], 0
0x18000d3cc  mov     dword ptr [rsp+68h+arg_0], eax
0x18000d3d0  cmp     r8, rcx
0x18000d3d3  jb      short loc_18000D3EE
0x18000d3d5  mov     edx, [rbx+10h]
0x18000d3d8  mov     rax, [rsp+68h+arg_0]
0x18000d3dd  add     rcx, rax
0x18000d3e0  inc     edx
0x18000d3e2  cmp     r8, rcx
0x18000d3e5  jnb     short loc_18000D3DD
0x18000d3e7  mov     [rbx+10h], edx
0x18000d3ea  mov     [rbx+38h], rcx
0x18000d3ee  mov     rcx, rbx; this
0x18000d3f1  call    ?CreateMapping@ILOG_FILE@@AEAAHXZ; ILOG_FILE::CreateMapping(void)
0x18000d3f6  test    eax, eax
0x18000d3f8  jnz     short loc_18000D40E
0x18000d3fa  call    cs:__imp_GetLastError
0x18000d400  mov     edi, eax
0x18000d402  mov     rcx, rbx; this
0x18000d405  call    ?CloseFile@ILOG_FILE@@QEAAHXZ; ILOG_FILE::CloseFile(void)
0x18000d40a  mov     ecx, edi
0x18000d40c  jmp     short loc_18000D394
0x18000d40e  mov     eax, 1
0x18000d413  add     rsp, 48h
0x18000d417  pop     rdi
0x18000d418  pop     rsi
0x18000d419  pop     rbp
0x18000d41a  pop     rbx
0x18000d41b  retn
```
