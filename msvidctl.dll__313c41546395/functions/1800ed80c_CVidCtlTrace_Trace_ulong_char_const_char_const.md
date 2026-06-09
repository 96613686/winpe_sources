# CVidCtlTrace::Trace(ulong,char const *,char const *,...)

- ea: `0x1800ed80c`
- end: `0x1800eda0e`
- name: `?Trace@CVidCtlTrace@@QEAAJKPEBD0ZZ`
- size: `514`
- prototype: `int(CVidCtlTrace *__hidden this, unsigned int, const char *, const char *, ...)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180093d50`
- `0x1800c4134`
- `0x1800d00a4`
- `0x1800db6a8`
- `0x1800eda14`

## callees

- `0x180004640`
- `0x180005584`
- `0x1800456f8`
- `0x1800ed7c4`
- `0x1800ed80c`

## import_xrefs

- `KERNEL32!OutputDebugStringA` at `0x1800ed970`
- `KERNEL32!OutputDebugStringA` at `0x1800ed970`
- `KERNEL32!GetLocalTime` at `0x1800ed8ba`
- `KERNEL32!GetLocalTime` at `0x1800ed8ba`
- `KERNEL32!GetLastError` at `0x1800ed9ab`
- `KERNEL32!GetLastError` at `0x1800ed9ab`
- `KERNEL32!GetCurrentThreadId` at `0x1800ed8e0`
- `KERNEL32!GetCurrentThreadId` at `0x1800ed8e0`
- `KERNEL32!CloseHandle` at `0x1800ed9d2`
- `KERNEL32!CloseHandle` at `0x1800ed9d2`
- `KERNEL32!LeaveCriticalSection` at `0x1800ed9e3`
- `KERNEL32!LeaveCriticalSection` at `0x1800ed9e3`
- `KERNEL32!EnterCriticalSection` at `0x1800ed97d`
- `KERNEL32!EnterCriticalSection` at `0x1800ed97d`
- `KERNEL32!WriteFile` at `0x1800ed9a1`
- `KERNEL32!WriteFile` at `0x1800ed9a1`

## pseudocode

```c
__int64 CVidCtlTrace::Trace(struct _RTL_CRITICAL_SECTION *this, DWORD a2, const char *a3, const char *a4, ...)
{
  HRESULT v4; // ebx
  unsigned int v5; // eax
  int wMilliseconds; // ebx
  int wSecond; // edi
  int wMinute; // esi
  int wHour; // r14d
  int wDay; // r15d
  int wMonth; // r12d
  int wYear; // r13d
  DWORD CurrentThreadId; // eax
  size_t v14; // rdx
  LPCRITICAL_SECTION v15; // rdi
  HANDLE OwningThread; // rcx
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp-80h] BYREF
  size_t pcchLength; // [rsp+88h] [rbp-78h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+90h] [rbp-70h]
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-68h] BYREF
  char psz[1008]; // [rsp+B0h] [rbp-50h] BYREF
  char Buffer[1008]; // [rsp+4A0h] [rbp+3A0h] BYREF
  va_list ArgList; // [rsp+910h] [rbp+810h] BYREF

  va_start(ArgList, a4);
  pcchLength = (size_t)a3;
  NumberOfBytesWritten = a2;
  lpCriticalSection = this;
  if ( !a4 )
    return (unsigned int)-2147467261;
  if ( a2 >= LODWORD(this[1].DebugInfo) || (v4 = 0, HIDWORD(this[1].DebugInfo)) )
  {
    *(_QWORD *)&SystemTime.wYear = 0;
    v5 = vsnprintf(Buffer, 0x3E7u, a4, ArgList);
    if ( v5 >= 0x3E8 )
    {
      v4 = -2147024774;
    }
    else
    {
      v4 = 0;
      if ( v5 != 999 )
      {
LABEL_10:
        SystemTime = 0;
        if ( v4 >= 0 )
        {
          GetLocalTime(&SystemTime);
          wMilliseconds = SystemTime.wMilliseconds;
          wSecond = SystemTime.wSecond;
          wMinute = SystemTime.wMinute;
          wHour = SystemTime.wHour;
          wDay = SystemTime.wDay;
          wMonth = SystemTime.wMonth;
          wYear = SystemTime.wYear;
          CurrentThreadId = GetCurrentThreadId();
          v4 = StringCchPrintfA(
                 psz,
                 0x3E8u,
                 "[%d/%02d/%02d %02d:%02d:%02d.%03d](P=%d)(T=%d) %s() : %s%s",
                 wYear,
                 wMonth,
                 wDay,
                 wHour,
                 wMinute,
                 wSecond,
                 wMilliseconds,
                 NumberOfBytesWritten,
                 CurrentThreadId,
                 (const char *)pcchLength,
                 Buffer,
                 "\r\n");
          if ( v4 >= 0 )
          {
            pcchLength = 0;
            v4 = StringLengthWorkerA(psz, v14, &pcchLength);
            if ( v4 >= 0 )
            {
              OutputDebugStringA(psz);
              v15 = lpCriticalSection;
              EnterCriticalSection(lpCriticalSection);
              OwningThread = v15[1].OwningThread;
              if ( OwningThread != (HANDLE)-1LL )
              {
                NumberOfBytesWritten = 0;
                if ( !WriteFile(OwningThread, psz, pcchLength, &NumberOfBytesWritten, 0) )
                {
                  LastError = GetLastError();
                  v4 = StringCchPrintfA(
                         psz,
                         0x3E8u,
                         "VIDCTLTRACE Error: Closing Handle = 0x%p Error 0x%x\n",
                         v15[1].OwningThread,
                         LastError);
                  CloseHandle(v15[1].OwningThread);
                  v15[1].OwningThread = (HANDLE)-1LL;
                }
              }
              LeaveCriticalSection(v15);
            }
          }
        }
        return (unsigned int)v4;
      }
    }
    Buffer[999] = 0;
    goto LABEL_10;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800ed80c  mov     [rsp-8+arg_18], r9
0x1800ed811  push    rbp
0x1800ed812  push    rbx
0x1800ed813  push    rsi
0x1800ed814  push    rdi
0x1800ed815  push    r12
0x1800ed817  push    r13
0x1800ed819  push    r14
0x1800ed81b  push    r15
0x1800ed81d  lea     rbp, [rsp-7A8h]
0x1800ed825  sub     rsp, 8A8h
0x1800ed82c  mov     rax, cs:__security_cookie
0x1800ed833  xor     rax, rsp
0x1800ed836  mov     [rbp+7E0h+var_50], rax
0x1800ed83d  xor     edi, edi
0x1800ed83f  mov     [rbp+7E0h+pcchLength], r8
0x1800ed843  mov     [rbp+7E0h+NumberOfBytesWritten], edx
0x1800ed846  mov     rax, r9
0x1800ed849  mov     [rbp+7E0h+lpCriticalSection], rcx
0x1800ed84d  test    r9, r9
0x1800ed850  jnz     short loc_1800ED85C
0x1800ed852  mov     ebx, 80004003h
0x1800ed857  jmp     loc_1800ED9E9
0x1800ed85c  cmp     edx, [rcx+28h]
0x1800ed85f  jnb     short loc_1800ED86C
0x1800ed861  mov     ebx, edi
0x1800ed863  cmp     [rcx+2Ch], edi
0x1800ed866  jz      loc_1800ED9E9
0x1800ed86c  mov     esi, 3E7h
0x1800ed871  mov     qword ptr [rbp+7E0h+SystemTime.wYear], rdi
0x1800ed875  mov     edx, esi; BufferCount
0x1800ed877  lea     r9, [rbp+7E0h+ArgList]; ArgList
0x1800ed87e  mov     r8, rax; Format
0x1800ed881  lea     rcx, [rbp+7E0h+Buffer]; Buffer
0x1800ed888  call    _vsnprintf
0x1800ed88d  test    eax, eax
0x1800ed88f  js      short loc_1800ED89B
0x1800ed891  cmp     eax, esi
0x1800ed893  ja      short loc_1800ED89B
0x1800ed895  mov     ebx, edi
0x1800ed897  jnz     short loc_1800ED8A7
0x1800ed899  jmp     short loc_1800ED8A0
0x1800ed89b  mov     ebx, 8007007Ah
0x1800ed8a0  mov     [rbp+7E0h+var_59], dil
0x1800ed8a7  xorps   xmm0, xmm0
0x1800ed8aa  movups  xmmword ptr [rbp+7E0h+SystemTime.wYear], xmm0
0x1800ed8ae  test    ebx, ebx
0x1800ed8b0  js      loc_1800ED9E9
0x1800ed8b6  lea     rcx, [rbp+7E0h+SystemTime]; lpSystemTime
0x1800ed8ba  call    cs:__imp_GetLocalTime
0x1800ed8c0  movzx   ebx, [rbp+7E0h+SystemTime.wMilliseconds]
0x1800ed8c4  movzx   edi, [rbp+7E0h+SystemTime.wSecond]
0x1800ed8c8  movzx   esi, [rbp+7E0h+SystemTime.wMinute]
0x1800ed8cc  movzx   r14d, [rbp+7E0h+SystemTime.wHour]
0x1800ed8d1  movzx   r15d, [rbp+7E0h+SystemTime.wDay]
0x1800ed8d6  movzx   r12d, [rbp+7E0h+SystemTime.wMonth]
0x1800ed8db  movzx   r13d, [rbp+7E0h+SystemTime.wYear]
0x1800ed8e0  call    cs:__imp_GetCurrentThreadId
0x1800ed8e6  lea     rcx, asc_18016A7DC; "\r\n"
0x1800ed8ed  mov     r9d, r13d
0x1800ed8f0  mov     [rsp+8E0h+var_870], rcx
0x1800ed8f5  lea     r8, aD02d02d02d02d0; "[%d/%02d/%02d %02d:%02d:%02d.%03d](P=%d"...
0x1800ed8fc  lea     rcx, [rbp+7E0h+Buffer]
0x1800ed903  mov     [rsp+8E0h+var_878], rcx
0x1800ed908  mov     rcx, [rbp+7E0h+pcchLength]
0x1800ed90c  mov     [rsp+8E0h+var_880], rcx
0x1800ed911  lea     rcx, [rbp+7E0h+psz]; char *
0x1800ed915  mov     [rsp+8E0h+var_888], eax
0x1800ed919  mov     eax, [rbp+7E0h+NumberOfBytesWritten]
0x1800ed91c  mov     [rsp+8E0h+var_890], eax
0x1800ed920  mov     [rsp+8E0h+var_898], ebx
0x1800ed924  mov     [rsp+8E0h+var_8A0], edi
0x1800ed928  mov     [rsp+8E0h+var_8A8], esi
0x1800ed92c  mov     [rsp+8E0h+var_8B0], r14d
0x1800ed931  mov     r14d, 3E8h
0x1800ed937  mov     edx, r14d; unsigned __int64
0x1800ed93a  mov     [rsp+8E0h+var_8B8], r15d
0x1800ed93f  mov     dword ptr [rsp+8E0h+lpOverlapped], r12d
0x1800ed944  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800ed949  xor     esi, esi
0x1800ed94b  mov     ebx, eax
0x1800ed94d  test    eax, eax
0x1800ed94f  js      loc_1800ED9E9
0x1800ed955  lea     r8, [rbp+7E0h+pcchLength]; pcchLength
0x1800ed959  mov     [rbp+7E0h+pcchLength], rsi
0x1800ed95d  lea     rcx, [rbp+7E0h+psz]; psz
0x1800ed961  call    StringLengthWorkerA
0x1800ed966  mov     ebx, eax
0x1800ed968  test    eax, eax
0x1800ed96a  js      short loc_1800ED9E9
0x1800ed96c  lea     rcx, [rbp+7E0h+psz]; lpOutputString
0x1800ed970  call    cs:__imp_OutputDebugStringA
0x1800ed976  mov     rdi, [rbp+7E0h+lpCriticalSection]
0x1800ed97a  mov     rcx, rdi; lpCriticalSection
0x1800ed97d  call    cs:__imp_EnterCriticalSection
0x1800ed983  mov     rcx, [rdi+38h]; hFile
0x1800ed987  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ed98b  jz      short loc_1800ED9E0
0x1800ed98d  mov     r8d, dword ptr [rbp+7E0h+pcchLength]; nNumberOfBytesToWrite
0x1800ed991  lea     r9, [rbp+7E0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800ed995  lea     rdx, [rbp+7E0h+psz]; lpBuffer
0x1800ed999  mov     [rbp+7E0h+NumberOfBytesWritten], esi
0x1800ed99c  mov     [rsp+8E0h+lpOverlapped], rsi; lpOverlapped
0x1800ed9a1  call    cs:__imp_WriteFile
0x1800ed9a7  test    eax, eax
0x1800ed9a9  jnz     short loc_1800ED9E0
0x1800ed9ab  call    cs:__imp_GetLastError
0x1800ed9b1  mov     r9, [rdi+38h]
0x1800ed9b5  lea     r8, aVidctltraceErr; "VIDCTLTRACE Error: Closing Handle = 0x%"...
0x1800ed9bc  mov     edx, r14d; unsigned __int64
0x1800ed9bf  mov     dword ptr [rsp+8E0h+lpOverlapped], eax
0x1800ed9c3  lea     rcx, [rbp+7E0h+psz]; char *
0x1800ed9c7  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800ed9cc  mov     rcx, [rdi+38h]; hObject
0x1800ed9d0  mov     ebx, eax
0x1800ed9d2  call    cs:__imp_CloseHandle
0x1800ed9d8  mov     qword ptr [rdi+38h], 0FFFFFFFFFFFFFFFFh
0x1800ed9e0  mov     rcx, rdi; lpCriticalSection
0x1800ed9e3  call    cs:__imp_LeaveCriticalSection
0x1800ed9e9  mov     eax, ebx
0x1800ed9eb  mov     rcx, [rbp+7E0h+var_50]
0x1800ed9f2  xor     rcx, rsp; StackCookie
0x1800ed9f5  call    __security_check_cookie
0x1800ed9fa  add     rsp, 8A8h
0x1800eda01  pop     r15
0x1800eda03  pop     r14
0x1800eda05  pop     r13
0x1800eda07  pop     r12
0x1800eda09  pop     rdi
0x1800eda0a  pop     rsi
0x1800eda0b  pop     rbx
0x1800eda0c  pop     rbp
0x1800eda0d  retn
```
