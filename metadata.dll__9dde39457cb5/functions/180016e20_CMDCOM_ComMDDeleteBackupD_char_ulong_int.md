# CMDCOM::ComMDDeleteBackupD(char *,ulong,int)

- ea: `0x180016e20`
- end: `0x180016f4a`
- name: `?ComMDDeleteBackupD@CMDCOM@@QEAAJPEADKH@Z`
- size: `298`
- prototype: `int(CMDCOM *__hidden this, char *, unsigned int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016e10`
- `0x180016f50`

## callees

- `0x180016e20`
- `0x18001cca8`
- `0x1800309d0`

## import_xrefs

- `KERNEL32!DeleteFileA` at `0x180016ebd`
- `KERNEL32!DeleteFileA` at `0x180016ed7`
- `KERNEL32!DeleteFileA` at `0x180016ebd`
- `KERNEL32!DeleteFileA` at `0x180016ed7`
- `KERNEL32!WaitForSingleObject` at `0x180016e66`
- `KERNEL32!WaitForSingleObject` at `0x180016e66`
- `KERNEL32!ReleaseSemaphore` at `0x180016f04`
- `KERNEL32!ReleaseSemaphore` at `0x180016f04`
- `KERNEL32!GetLastError` at `0x180016ee1`
- `KERNEL32!GetLastError` at `0x180016ee1`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180016e74`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180016e7f`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180016e74`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180016e7f`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180016f0f`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180016f1d`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180016f0f`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180016f1d`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180016eb4`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180016ece`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180016eb4`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180016ece`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDDeleteBackupD(CMDCOM *this, char *a2, unsigned int a3, int a4)
{
  int BackupFileName; // ebx
  const CHAR *Str; // rax
  const CHAR *v9; // rax
  signed int LastError; // eax
  _BYTE v12[128]; // [rsp+30h] [rbp-118h] BYREF
  _BYTE v13[128]; // [rsp+B0h] [rbp-98h] BYREF

  if ( a3 == -1 )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    WaitForSingleObject(g_hReadSaveSemaphore, 0xFFFFFFFF);
    STRAU::STRAU((STRAU *)v13);
    STRAU::STRAU((STRAU *)v12);
    BackupFileName = CreateBackupFileName(a2, a3, a4, (struct STRAU *)v13, (struct STRAU *)v12);
    if ( BackupFileName >= 0 )
    {
      Str = STRAU::QueryStr((STRAU *)v13, 0);
      if ( !DeleteFileA(Str) || (v9 = STRAU::QueryStr((STRAU *)v12, 0), !DeleteFileA(v9)) )
      {
        LastError = GetLastError();
        BackupFileName = LastError;
        if ( LastError > 0 )
          BackupFileName = (unsigned __int16)LastError | 0x80070000;
      }
    }
    ReleaseSemaphore(g_hReadSaveSemaphore, 1, 0);
    STRAU::~STRAU((STRAU *)v12);
    STRAU::~STRAU((STRAU *)v13);
  }
  return (unsigned int)BackupFileName;
}

```

## disassembly

```asm
0x180016e20  mov     [rsp+arg_0], rbx
0x180016e25  mov     [rsp+arg_18], rsi
0x180016e2a  push    rdi
0x180016e2b  sub     rsp, 140h
0x180016e32  mov     rax, cs:__security_cookie
0x180016e39  xor     rax, rsp
0x180016e3c  mov     [rsp+148h+var_18], rax
0x180016e44  mov     rsi, rdx
0x180016e47  mov     edi, r9d
0x180016e4a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180016e4d  mov     ebx, r8d
0x180016e50  cmp     r8d, edx
0x180016e53  jnz     short loc_180016E5F
0x180016e55  mov     ebx, 80070057h
0x180016e5a  jmp     loc_180016F23
0x180016e5f  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hHandle
0x180016e66  call    cs:__imp_WaitForSingleObject
0x180016e6c  lea     rcx, [rsp+148h+var_98]
0x180016e74  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180016e7a  lea     rcx, [rsp+148h+var_118]
0x180016e7f  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180016e85  lea     rax, [rsp+148h+var_118]
0x180016e8a  mov     r8d, edi; int
0x180016e8d  lea     r9, [rsp+148h+var_98]; struct STRAU *
0x180016e95  mov     [rsp+148h+var_128], rax; struct STRAU *
0x180016e9a  mov     edx, ebx; unsigned int
0x180016e9c  mov     rcx, rsi; char *
0x180016e9f  call    ?CreateBackupFileName@@YAJPEADKHPEAVSTRAU@@1@Z; CreateBackupFileName(char *,ulong,int,STRAU *,STRAU *)
0x180016ea4  mov     ebx, eax
0x180016ea6  test    eax, eax
0x180016ea8  js      short loc_180016EF6
0x180016eaa  xor     edx, edx
0x180016eac  lea     rcx, [rsp+148h+var_98]
0x180016eb4  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x180016eba  mov     rcx, rax; lpFileName
0x180016ebd  call    cs:__imp_DeleteFileA
0x180016ec3  test    eax, eax
0x180016ec5  jz      short loc_180016EE1
0x180016ec7  xor     edx, edx
0x180016ec9  lea     rcx, [rsp+148h+var_118]
0x180016ece  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x180016ed4  mov     rcx, rax; lpFileName
0x180016ed7  call    cs:__imp_DeleteFileA
0x180016edd  test    eax, eax
0x180016edf  jnz     short loc_180016EF6
0x180016ee1  call    cs:__imp_GetLastError
0x180016ee7  mov     ebx, eax
0x180016ee9  test    eax, eax
0x180016eeb  jle     short loc_180016EF6
0x180016eed  movzx   ebx, ax
0x180016ef0  or      ebx, 80070000h
0x180016ef6  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hSemaphore
0x180016efd  xor     r8d, r8d; lpPreviousCount
0x180016f00  lea     edx, [r8+1]; lReleaseCount
0x180016f04  call    cs:__imp_ReleaseSemaphore
0x180016f0a  lea     rcx, [rsp+148h+var_118]
0x180016f0f  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180016f15  lea     rcx, [rsp+148h+var_98]
0x180016f1d  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180016f23  mov     eax, ebx
0x180016f25  mov     rcx, [rsp+148h+var_18]
0x180016f2d  xor     rcx, rsp; StackCookie
0x180016f30  call    __security_check_cookie
0x180016f35  lea     r11, [rsp+148h+var_8]
0x180016f3d  mov     rbx, [r11+10h]
0x180016f41  mov     rsi, [r11+28h]
0x180016f45  mov     rsp, r11
0x180016f48  pop     rdi
0x180016f49  retn
```
