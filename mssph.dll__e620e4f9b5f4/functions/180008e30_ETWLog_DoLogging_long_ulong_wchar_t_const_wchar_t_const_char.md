# ETWLog::DoLogging(long,ulong,wchar_t const *,wchar_t const *,char * *)

- ea: `0x180008e30`
- end: `0x180009012`
- name: `?DoLogging@ETWLog@@CAXJKPEB_W0PEAPEAD@Z`
- size: `482`
- prototype: `void __fastcall(__int64, __int64, const wchar_t *, const wchar_t *, char **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180008da0`

## callees

- `0x180008e30`
- `0x180009020`
- `0x180009140`
- `0x18000c748`
- `0x18000e9f4`
- `0x18000fcd0`
- `0x180010ba4`
- `0x180024dc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008fb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008fb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008ff8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008ff8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e8c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008f2a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008f2a`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180008eed`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180008eed`

## pseudocode

```c
void __fastcall ETWLog::DoLogging(__int64 a1, __int64 a2, const wchar_t *a3, const wchar_t *a4, char **a5)
{
  unsigned int v5; // eax
  int v6; // ecx
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  __int64 v9; // rax
  _BYTE v10[16]; // [rsp+30h] [rbp-36F8h] BYREF
  wchar_t *v11; // [rsp+40h] [rbp-36E8h]
  int v12; // [rsp+48h] [rbp-36E0h]
  int v13; // [rsp+4Ch] [rbp-36DCh]
  wchar_t Buffer[3504]; // [rsp+50h] [rbp-36D8h] BYREF
  WCHAR OutputString[3504]; // [rsp+1BB0h] [rbp-1B78h] BYREF

  v5 = vsnwprintf(Buffer, 0xDABu, a4, *a5);
  if ( v5 >= 0xDAC )
  {
    v6 = -2147024774;
LABEL_3:
    Buffer[3499] = 0;
    goto LABEL_4;
  }
  v6 = 0;
  if ( v5 == 3499 )
    goto LABEL_3;
LABEL_4:
  if ( v6 >= 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    if ( (int)StringCchPrintfW(OutputString, 0xDACu, L"%4d %s\n", CurrentThreadId, Buffer) >= 0 )
    {
      try
      {
        if ( g_fETWLoggingEnabled )
          OutputDebugStringW(OutputString);
      }
      catch ( ... )
      {
        return;
      }
    }
    if ( dword_1800364E8 )
    {
      EnterCriticalSection(&CriticalSection);
      StringCchCopyW((wchar_t *)lpMem + 1024 * (unsigned __int64)(unsigned int)dword_1800364EC, 0x400u, OutputString);
      dword_1800364EC = (dword_1800364EC + 1) % (unsigned int)dword_1800364E8;
      LeaveCriticalSection(&CriticalSection);
    }
    if ( !g_fETWLoggingChecked )
      ETWLog::CheckEnabled();
    if ( (g_fETWLoggingEnabled || EventEnabled(Microsoft_Windows_Search_Core_Context, &MSSearchTraceId_ETWLogging))
      && (byte_180036342 & 0x20) != 0 )
    {
      v9 = -1;
      do
        ++v9;
      while ( Buffer[v9] );
      v11 = Buffer;
      v12 = 2 * v9 + 2;
      v13 = 0;
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_Search_Core_Context,
        &MSSearchTraceId_ETWLogging,
        v8,
        2,
        v10);
    }
  }
}

```

## disassembly

```asm
0x180008e30  push    rbx
0x180008e32  mov     eax, 3720h
0x180008e37  call    _alloca_probe
0x180008e3c  sub     rsp, rax
0x180008e3f  mov     rax, cs:__security_cookie
0x180008e46  xor     rax, rsp
0x180008e49  mov     [rsp+3728h+var_18], rax
0x180008e51  mov     rax, r9
0x180008e54  mov     r9, [rsp+3728h+arg_20]
0x180008e5c  mov     r9, [r9]; Args
0x180008e5f  mov     r8, rax; Format
0x180008e62  mov     edx, 0DABh; BufferCount
0x180008e67  lea     rcx, [rsp+3728h+Buffer]; Buffer
0x180008e6c  call    _vsnwprintf
0x180008e71  test    eax, eax
0x180008e73  jns     loc_180008F8C
0x180008e79  xor     ebx, ebx
0x180008e7b  mov     ecx, 8007007Ah
0x180008e80  mov     [rsp+3728h+var_1B82], bx
0x180008e88  test    ecx, ecx
0x180008e8a  js      short loc_180008F00
0x180008e8c  call    cs:__imp_GetCurrentThreadId
0x180008e92  mov     r9d, eax
0x180008e95  lea     rax, [rsp+3728h+Buffer]
0x180008e9a  mov     [rsp+3728h+var_3708], rax
0x180008e9f  lea     r8, a4dS; "%4d %s\n"
0x180008ea6  mov     edx, 0DACh; unsigned __int64
0x180008eab  lea     rcx, [rsp+3728h+OutputString]; wchar_t *
0x180008eb3  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180008eb8  test    eax, eax
0x180008eba  jns     short loc_180008F19
0x180008ebc  cmp     cs:dword_1800364E8, 0
0x180008ec3  ja      loc_180008FAB
0x180008ec9  cmp     cs:?g_fETWLoggingChecked@@3_NA, 0; bool g_fETWLoggingChecked
0x180008ed0  jz      loc_180009003
0x180008ed6  cmp     cs:?g_fETWLoggingEnabled@@3_NA, 0; bool g_fETWLoggingEnabled
0x180008edd  jnz     short loc_180008EF7
0x180008edf  lea     rdx, MSSearchTraceId_ETWLogging; EventDescriptor
0x180008ee6  mov     rcx, cs:Microsoft_Windows_Search_Core_Context; RegHandle
0x180008eed  call    cs:__imp_EventEnabled
0x180008ef3  test    al, al
0x180008ef5  jz      short loc_180008F00
0x180008ef7  test    cs:byte_180036342, 20h
0x180008efe  jnz     short loc_180008F32
0x180008f00  mov     rcx, [rsp+3728h+var_18]
0x180008f08  xor     rcx, rsp; StackCookie
0x180008f0b  call    __security_check_cookie
0x180008f10  add     rsp, 3720h
0x180008f17  pop     rbx
0x180008f18  retn
0x180008f19  cmp     cs:?g_fETWLoggingEnabled@@3_NA, 0; bool g_fETWLoggingEnabled
0x180008f20  jz      short loc_180008EBC
0x180008f22  lea     rcx, [rsp+3728h+OutputString]; lpOutputString
0x180008f2a  call    cs:__imp_OutputDebugStringW
0x180008f30  jmp     short loc_180008EBC
0x180008f32  lea     rcx, [rsp+3728h+Buffer]
0x180008f37  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008f3e  xchg    ax, ax
0x180008f40  lea     rax, [rax+1]
0x180008f44  cmp     word ptr [rcx+rax*2], 0
0x180008f49  jnz     short loc_180008F40
0x180008f4b  lea     eax, ds:2[rax*2]
0x180008f52  lea     rcx, [rsp+3728h+Buffer]
0x180008f57  mov     [rsp+3728h+var_36E8], rcx
0x180008f5c  mov     [rsp+3728h+var_36E0], eax
0x180008f60  mov     [rsp+3728h+var_36DC], ebx
0x180008f64  lea     rax, [rsp+3728h+var_36F8]
0x180008f69  mov     [rsp+3728h+var_3708], rax
0x180008f6e  mov     r9d, 2
0x180008f74  lea     rdx, MSSearchTraceId_ETWLogging
0x180008f7b  lea     rcx, Microsoft_Windows_Search_Core_Context
0x180008f82  call    McGenEventWrite_EventWriteTransfer
0x180008f87  jmp     loc_180008F00
0x180008f8c  cmp     eax, 0DABh
0x180008f91  ja      loc_180008E79
0x180008f97  xor     ebx, ebx
0x180008f99  mov     ecx, ebx
0x180008f9b  cmp     eax, 0DABh
0x180008fa0  jnz     loc_180008E88
0x180008fa6  jmp     loc_180008E80
0x180008fab  lea     rcx, CriticalSection; lpCriticalSection
0x180008fb2  call    cs:__imp_EnterCriticalSection
0x180008fb8  mov     ecx, cs:dword_1800364EC
0x180008fbe  shl     rcx, 0Bh
0x180008fc2  add     rcx, cs:lpMem; wchar_t *
0x180008fc9  lea     r8, [rsp+3728h+OutputString]; wchar_t *
0x180008fd1  mov     edx, 400h; unsigned __int64
0x180008fd6  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180008fdb  mov     eax, cs:dword_1800364EC
0x180008fe1  inc     eax
0x180008fe3  xor     edx, edx
0x180008fe5  div     cs:dword_1800364E8
0x180008feb  mov     cs:dword_1800364EC, edx
0x180008ff1  lea     rcx, CriticalSection; lpCriticalSection
0x180008ff8  call    cs:__imp_LeaveCriticalSection
0x180008ffe  jmp     loc_180008EC9
0x180009003  call    ?CheckEnabled@ETWLog@@CAXXZ; ETWLog::CheckEnabled(void)
0x180009008  jmp     loc_180008ED6
0x18000900d  jmp     loc_180008F00
```
