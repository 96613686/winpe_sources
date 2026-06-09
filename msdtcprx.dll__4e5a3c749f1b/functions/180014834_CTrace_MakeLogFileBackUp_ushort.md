# CTrace::MakeLogFileBackUp(ushort *)

- ea: `0x180014834`
- end: `0x180014abf`
- name: `?MakeLogFileBackUp@CTrace@@AEAAJPEAG@Z`
- size: `651`
- prototype: `int(CTrace *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001881c`

## callees

- `0x180003cf0`
- `0x180014834`
- `0x18001d178`
- `0x18001d184`
- `0x180058a38`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001486c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014961`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001486c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014961`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014861`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014861`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800148bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800148bd`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180014a1a`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180014a1a`
- `KERNEL32!MoveFileW` at `0x180014957`
- `KERNEL32!MoveFileW` at `0x180014957`

## string_xrefs

- `0x18001499b`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x1800149d7`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x180014a20`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x18001498f`: `MoveFile Failed, dwAttemptNum = %d`
- `0x1800149cb`: `MoveFile %ls to %ls, succeeded`
- `0x180014a63`: `MoveFile Failed`
- `0x180014a34`: `MoveFileEx %ls to %ls succeeded`

## pseudocode

```c
__int64 __fastcall CTrace::MakeLogFileBackUp(CTrace *this, unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  unsigned __int16 *v4; // rdi
  unsigned __int16 *v5; // rsi
  unsigned int i; // r14d
  signed int LastError; // eax
  __int64 v9; // [rsp+20h] [rbp-98h]
  __int64 v10; // [rsp+28h] [rbp-90h]
  __int64 v11; // [rsp+38h] [rbp-80h]
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-58h] BYREF

  SystemTime = 0;
  if ( GetFileAttributesW(a2) == -1 && GetLastError() == 2 )
  {
    return 0;
  }
  else
  {
    v4 = (unsigned __int16 *)operator new[](0x608u);
    if ( v4 )
    {
      v5 = (unsigned __int16 *)operator new[](0x608u);
      if ( v5 )
      {
        v3 = 0;
        GetLocalTime(&SystemTime);
        StringCbPrintfW(
          v5,
          0x304u,
          L"%1ws.%04d-%02d-%02d-%02d-%02d-%02d-%04d",
          a2,
          SystemTime.wYear,
          SystemTime.wMonth,
          SystemTime.wDay,
          SystemTime.wHour,
          SystemTime.wMinute,
          SystemTime.wSecond,
          SystemTime.wMilliseconds);
        for ( i = 0; i < 0x64; ++i )
        {
          LODWORD(v9) = i;
          StringCbPrintfW(v4, 0x304u, L"%1ws-%02d", v5, v9);
          if ( MoveFileW(a2, v4) )
          {
            TraceStringInline(
              14,
              3,
              L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
              530,
              L"CTrace::MakeLogFileBackUp",
              0,
              L"MoveFile %ls to %ls, succeeded",
              a2,
              v4);
            v3 = 0;
            goto LABEL_21;
          }
          LastError = GetLastError();
          if ( LastError == 5 || LastError == 32 )
            break;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          else
            v3 = LastError;
          LODWORD(v11) = i;
          LODWORD(v10) = v3;
          TraceStringInline(
            14,
            1,
            L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
            523,
            L"CTrace::MakeLogFileBackUp",
            v10,
            L"MoveFile Failed, dwAttemptNum = %d",
            v11);
        }
        if ( MoveFileExW(a2, v4, 1u) )
          TraceStringInline(
            14,
            3,
            L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
            538,
            L"CTrace::MakeLogFileBackUp",
            0,
            L"MoveFileEx %ls to %ls succeeded",
            a2,
            v4);
        else
          TraceStringInline(
            14,
            1,
            L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
            543,
            L"CTrace::MakeLogFileBackUp",
            0,
            L"MoveFile Failed");
      }
      else
      {
        v3 = -2147024882;
      }
LABEL_21:
      operator delete(v4);
      if ( v5 )
        operator delete(v5);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180014834  push    rbx
0x180014836  push    rbp
0x180014837  push    rsi
0x180014838  push    rdi
0x180014839  push    r13
0x18001483b  push    r14
0x18001483d  sub     rsp, 88h
0x180014844  mov     rax, cs:__security_cookie
0x18001484b  xor     rax, rsp
0x18001484e  mov     [rsp+0B8h+var_48], rax
0x180014853  xorps   xmm0, xmm0
0x180014856  mov     rcx, rdx; lpFileName
0x180014859  movups  xmmword ptr [rsp+0B8h+SystemTime.wYear], xmm0
0x18001485e  mov     rbp, rdx
0x180014861  call    cs:__imp_GetFileAttributesW
0x180014867  cmp     eax, 0FFFFFFFFh
0x18001486a  jnz     short loc_18001487E
0x18001486c  call    cs:__imp_GetLastError
0x180014872  cmp     eax, 2
0x180014875  jnz     short loc_18001487E
0x180014877  xor     ebx, ebx
0x180014879  jmp     loc_180014AA0
0x18001487e  mov     ebx, 608h
0x180014883  mov     ecx, ebx; unsigned __int64
0x180014885  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001488a  mov     rdi, rax
0x18001488d  test    rax, rax
0x180014890  jnz     short loc_18001489C
0x180014892  mov     ebx, 8007000Eh
0x180014897  jmp     loc_180014AA0
0x18001489c  mov     rcx, rbx; unsigned __int64
0x18001489f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800148a4  mov     rsi, rax
0x1800148a7  test    rax, rax
0x1800148aa  jnz     short loc_1800148B6
0x1800148ac  mov     ebx, 8007000Eh
0x1800148b1  jmp     loc_180014A8B
0x1800148b6  lea     rcx, [rsp+0B8h+SystemTime]; lpSystemTime
0x1800148bb  xor     ebx, ebx
0x1800148bd  call    cs:__imp_GetLocalTime
0x1800148c3  movzx   ecx, [rsp+0B8h+SystemTime.wSecond]
0x1800148c8  movzx   edx, [rsp+0B8h+SystemTime.wMinute]
0x1800148cd  movzx   r8d, [rsp+0B8h+SystemTime.wHour]
0x1800148d3  movzx   r9d, [rsp+0B8h+SystemTime.wDay]
0x1800148d9  movzx   eax, [rsp+0B8h+SystemTime.wMilliseconds]
0x1800148de  movzx   r10d, [rsp+0B8h+SystemTime.wMonth]
0x1800148e4  movzx   r11d, [rsp+0B8h+SystemTime.wYear]
0x1800148ea  mov     [rsp+0B8h+var_68], eax
0x1800148ee  mov     [rsp+0B8h+var_70], ecx
0x1800148f2  mov     rcx, rsi; unsigned __int16 *
0x1800148f5  mov     dword ptr [rsp+0B8h+var_78], edx
0x1800148f9  mov     edx, 304h; unsigned __int64
0x1800148fe  mov     dword ptr [rsp+0B8h+var_80], r8d
0x180014903  lea     r8, a1ws04d02d02d02; "%1ws.%04d-%02d-%02d-%02d-%02d-%02d-%04d"
0x18001490a  mov     dword ptr [rsp+0B8h+var_88], r9d
0x18001490f  mov     r9, rbp
0x180014912  mov     dword ptr [rsp+0B8h+var_90], r10d
0x180014917  mov     dword ptr [rsp+0B8h+var_98], r11d
0x18001491c  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014921  xor     r14d, r14d
0x180014924  lea     r13, aCtraceMakelogf; "CTrace::MakeLogFileBackUp"
0x18001492b  cmp     r14d, 64h ; 'd'
0x18001492f  jnb     loc_180014A0B
0x180014935  mov     r9, rsi
0x180014938  mov     dword ptr [rsp+0B8h+var_98], r14d
0x18001493d  lea     r8, a1ws02d; "%1ws-%02d"
0x180014944  mov     edx, 304h; unsigned __int64
0x180014949  mov     rcx, rdi; unsigned __int16 *
0x18001494c  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014951  mov     rdx, rdi; lpNewFileName
0x180014954  mov     rcx, rbp; lpExistingFileName
0x180014957  call    cs:__imp_MoveFileW
0x18001495d  test    eax, eax
0x18001495f  jnz     short loc_1800149C6
0x180014961  call    cs:__imp_GetLastError
0x180014967  cmp     eax, 5
0x18001496a  jz      loc_180014A0B
0x180014970  cmp     eax, 20h ; ' '
0x180014973  jz      loc_180014A0B
0x180014979  test    eax, eax
0x18001497b  jg      short loc_180014981
0x18001497d  mov     ebx, eax
0x18001497f  jmp     short loc_18001498A
0x180014981  movzx   ebx, ax
0x180014984  or      ebx, 80070000h
0x18001498a  mov     dword ptr [rsp+0B8h+var_80], r14d
0x18001498f  lea     rax, aMovefileFailed_0; "MoveFile Failed, dwAttemptNum = %d"
0x180014996  mov     [rsp+0B8h+var_88], rax
0x18001499b  lea     r8, aComComplusDtcD_9; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x1800149a2  mov     edx, 1
0x1800149a7  mov     dword ptr [rsp+0B8h+var_90], ebx
0x1800149ab  mov     r9d, 20Bh
0x1800149b1  mov     [rsp+0B8h+var_98], r13
0x1800149b6  lea     ecx, [rdx+0Dh]
0x1800149b9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800149be  inc     r14d
0x1800149c1  jmp     loc_18001492B
0x1800149c6  mov     [rsp+0B8h+var_78], rdi
0x1800149cb  lea     rax, aMovefileLsToLs; "MoveFile %ls to %ls, succeeded"
0x1800149d2  mov     [rsp+0B8h+var_80], rbp
0x1800149d7  lea     r8, aComComplusDtcD_9; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x1800149de  mov     [rsp+0B8h+var_88], rax
0x1800149e3  mov     edx, 3
0x1800149e8  mov     [rsp+0B8h+var_90], 0
0x1800149f1  mov     r9d, 212h
0x1800149f7  mov     [rsp+0B8h+var_98], r13
0x1800149fc  lea     ecx, [rdx+0Bh]
0x1800149ff  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180014a04  xor     ebx, ebx
0x180014a06  jmp     loc_180014A8B
0x180014a0b  mov     r14d, 1
0x180014a11  mov     rdx, rdi; lpNewFileName
0x180014a14  mov     r8d, r14d; dwFlags
0x180014a17  mov     rcx, rbp; lpExistingFileName
0x180014a1a  call    cs:__imp_MoveFileExW
0x180014a20  lea     r8, aComComplusDtcD_9; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x180014a27  lea     ecx, [r14+0Dh]
0x180014a2b  test    eax, eax
0x180014a2d  jz      short loc_180014A63
0x180014a2f  mov     [rsp+0B8h+var_78], rdi
0x180014a34  lea     rax, aMovefileexLsTo; "MoveFileEx %ls to %ls succeeded"
0x180014a3b  mov     [rsp+0B8h+var_80], rbp
0x180014a40  lea     edx, [rcx-0Bh]
0x180014a43  mov     [rsp+0B8h+var_88], rax
0x180014a48  mov     r9d, 21Ah
0x180014a4e  mov     [rsp+0B8h+var_90], 0
0x180014a57  mov     [rsp+0B8h+var_98], r13
0x180014a5c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180014a61  jmp     short loc_180014A8B
0x180014a63  lea     rax, aMovefileFailed; "MoveFile Failed"
0x180014a6a  mov     r9d, 21Fh
0x180014a70  mov     [rsp+0B8h+var_88], rax
0x180014a75  mov     edx, r14d
0x180014a78  mov     [rsp+0B8h+var_90], 0
0x180014a81  mov     [rsp+0B8h+var_98], r13
0x180014a86  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180014a8b  mov     rcx, rdi; Block
0x180014a8e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014a93  test    rsi, rsi
0x180014a96  jz      short loc_180014AA0
0x180014a98  mov     rcx, rsi; Block
0x180014a9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014aa0  mov     eax, ebx
0x180014aa2  mov     rcx, [rsp+0B8h+var_48]
0x180014aa7  xor     rcx, rsp; StackCookie
0x180014aaa  call    __security_check_cookie
0x180014aaf  add     rsp, 88h
0x180014ab6  pop     r14
0x180014ab8  pop     r13
0x180014aba  pop     rdi
0x180014abb  pop     rsi
0x180014abc  pop     rbp
0x180014abd  pop     rbx
0x180014abe  retn
```
