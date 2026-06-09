# AcquireConfigRefreshMutex(void * *,ushort const *)

- ea: `0x18000b090`
- end: `0x18000b1a2`
- name: `?AcquireConfigRefreshMutex@@YAJPEAPEAXPEBG@Z`
- size: `274`
- prototype: `int(void **, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180007930`
- `0x18000b090`
- `0x180021ec4`
- `0x180021f30`
- `0x180021fec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b132`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b10c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b10c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000b0bb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000b0bb`

## string_xrefs

- `0x18000b0b0`: `__CONFIGREFRESH_NAMED_MUTEX__`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AcquireConfigRefreshMutex(void **a1, const unsigned __int16 *a2)
{
  CConfigRefreshLogger *Logger; // rax
  HANDLE MutexW; // rax
  void *v6; // rdi
  signed int v7; // eax
  unsigned int v8; // ebx
  CConfigRefreshLogger *v9; // rax
  DWORD v10; // eax
  signed int LastError; // eax
  CConfigRefreshLogger *v12; // rax
  CConfigRefreshLogger *v14; // rax

  Logger = CConfigRefreshLogger::GetLogger();
  CConfigRefreshLogger::LogConfigRefreshMutexAcquireStart(Logger, a2);
  MutexW = CreateMutexW(0, 0, L"__CONFIGREFRESH_NAMED_MUTEX__");
  v6 = MutexW;
  if ( MutexW )
  {
    v10 = WaitForSingleObject(MutexW, 0xEA60u);
    if ( (v10 & 0xFFFFFF7F) != 0 )
    {
      if ( v10 == 258 )
      {
        v8 = -2147023436;
        goto LABEL_15;
      }
      if ( v10 != -1 )
      {
        v8 = -2147418113;
LABEL_15:
        v14 = CConfigRefreshLogger::GetLogger();
        CConfigRefreshLogger::LogConfigRefreshMutexAcquireEnd(v14, a2, v8);
        ReleaseOmaDmMutex(v6);
        return v8;
      }
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 )
        goto LABEL_15;
    }
    *a1 = v6;
    v12 = CConfigRefreshLogger::GetLogger();
    CConfigRefreshLogger::LogConfigRefreshMutexAcquireEnd(v12, a2, 0);
    return 0;
  }
  v7 = GetLastError();
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  v9 = CConfigRefreshLogger::GetLogger();
  CConfigRefreshLogger::LogConfigRefreshMutexAcquireEnd(v9, a2, v8);
  return v8;
}

```

## disassembly

```asm
0x18000b090  push    rbx
0x18000b092  push    rsi
0x18000b093  push    rdi
0x18000b094  push    r14
0x18000b096  sub     rsp, 28h
0x18000b09a  mov     rsi, rdx
0x18000b09d  mov     r14, rcx
0x18000b0a0  call    ?GetLogger@CConfigRefreshLogger@@SAPEAV1@XZ; CConfigRefreshLogger::GetLogger(void)
0x18000b0a5  mov     rdx, rsi; unsigned __int16 *
0x18000b0a8  mov     rcx, rax; this
0x18000b0ab  call    ?LogConfigRefreshMutexAcquireStart@CConfigRefreshLogger@@QEAAXPEBG@Z; CConfigRefreshLogger::LogConfigRefreshMutexAcquireStart(ushort const *)
0x18000b0b0  lea     r8, aConfigrefreshN; "__CONFIGREFRESH_NAMED_MUTEX__"
0x18000b0b7  xor     edx, edx; bInitialOwner
0x18000b0b9  xor     ecx, ecx; lpMutexAttributes
0x18000b0bb  call    cs:__imp_CreateMutexW
0x18000b0c2  nop     dword ptr [rax+rax+00h]
0x18000b0c7  mov     rdi, rax
0x18000b0ca  mov     [rsp+48h+arg_10], rax
0x18000b0cf  test    rax, rax
0x18000b0d2  jnz     short loc_18000B104
0x18000b0d4  call    cs:__imp_GetLastError
0x18000b0db  nop     dword ptr [rax+rax+00h]
0x18000b0e0  mov     ebx, eax
0x18000b0e2  test    eax, eax
0x18000b0e4  jle     short loc_18000B0EF
0x18000b0e6  movzx   ebx, ax
0x18000b0e9  or      ebx, 80070000h
0x18000b0ef  call    ?GetLogger@CConfigRefreshLogger@@SAPEAV1@XZ; CConfigRefreshLogger::GetLogger(void)
0x18000b0f4  mov     r8d, ebx; int
0x18000b0f7  mov     rdx, rsi; unsigned __int16 *
0x18000b0fa  mov     rcx, rax; this
0x18000b0fd  call    ?LogConfigRefreshMutexAcquireEnd@CConfigRefreshLogger@@QEAAXPEBGJ@Z; CConfigRefreshLogger::LogConfigRefreshMutexAcquireEnd(ushort const *,long)
0x18000b102  jmp     short loc_18000B172
0x18000b104  mov     edx, 0EA60h; dwMilliseconds
0x18000b109  mov     rcx, rdi; hHandle
0x18000b10c  call    cs:__imp_WaitForSingleObject
0x18000b113  nop     dword ptr [rax+rax+00h]
0x18000b118  test    eax, 0FFFFFF7Fh
0x18000b11d  jz      short loc_18000B151
0x18000b11f  cmp     eax, 102h
0x18000b124  jz      short loc_18000B17F
0x18000b126  cmp     eax, 0FFFFFFFFh
0x18000b129  jz      short loc_18000B132
0x18000b12b  mov     ebx, 8000FFFFh
0x18000b130  jmp     short loc_18000B184
0x18000b132  call    cs:__imp_GetLastError
0x18000b139  nop     dword ptr [rax+rax+00h]
0x18000b13e  mov     ebx, eax
0x18000b140  test    eax, eax
0x18000b142  jle     short loc_18000B14D
0x18000b144  movzx   ebx, ax
0x18000b147  or      ebx, 80070000h
0x18000b14d  test    ebx, ebx
0x18000b14f  jnz     short loc_18000B184
0x18000b151  mov     [rsp+48h+arg_10], 0
0x18000b15a  mov     [r14], rdi
0x18000b15d  call    ?GetLogger@CConfigRefreshLogger@@SAPEAV1@XZ; CConfigRefreshLogger::GetLogger(void)
0x18000b162  xor     r8d, r8d; int
0x18000b165  mov     rdx, rsi; unsigned __int16 *
0x18000b168  mov     rcx, rax; this
0x18000b16b  call    ?LogConfigRefreshMutexAcquireEnd@CConfigRefreshLogger@@QEAAXPEBGJ@Z; CConfigRefreshLogger::LogConfigRefreshMutexAcquireEnd(ushort const *,long)
0x18000b170  xor     ebx, ebx
0x18000b172  mov     eax, ebx
0x18000b174  add     rsp, 28h
0x18000b178  pop     r14
0x18000b17a  pop     rdi
0x18000b17b  pop     rsi
0x18000b17c  pop     rbx
0x18000b17d  retn
0x18000b17f  mov     ebx, 800705B4h
0x18000b184  call    ?GetLogger@CConfigRefreshLogger@@SAPEAV1@XZ; CConfigRefreshLogger::GetLogger(void)
0x18000b189  mov     r8d, ebx; int
0x18000b18c  mov     rdx, rsi; unsigned __int16 *
0x18000b18f  mov     rcx, rax; this
0x18000b192  call    ?LogConfigRefreshMutexAcquireEnd@CConfigRefreshLogger@@QEAAXPEBGJ@Z; CConfigRefreshLogger::LogConfigRefreshMutexAcquireEnd(ushort const *,long)
0x18000b197  nop
0x18000b198  mov     rcx, rdi; hObject
0x18000b19b  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x18000b1a0  jmp     short loc_18000B172
```
