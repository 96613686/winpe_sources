# ETWLog::DoLogging(long,ulong,wchar_t const *,wchar_t const *,char * *)

- ea: `0x18000c020`
- end: `0x18000c4c3`
- name: `?DoLogging@ETWLog@@CAXJKPEB_W0PEAPEAD@Z`
- size: `1187`
- prototype: `void __fastcall(int, unsigned int, const wchar_t *, const wchar_t *, char **)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000bf8c`
- `0x18000d0d0`
- `0x180045cf4`
- `0x18006c714`

## callees

- `0x18000c020`
- `0x18000c4cc`
- `0x18000c760`
- `0x18009491c`
- `0x1800a23c0`
- `0x1801244c0`
- `0x180125488`
- `0x180156754`
- `0x180222f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c47a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c47a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c434`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c434`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c0c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c2c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c30b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c3ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c0c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c2c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c30b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c3ea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c1e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c1e5`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18000c12f`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18000c12f`

## pseudocode

```c
void __fastcall ETWLog::DoLogging(int a1, int a2, wchar_t *a3, const wchar_t *a4, char **a5)
{
  unsigned int v8; // eax
  int v9; // ecx
  bool v10; // si
  DWORD v11; // eax
  int v12; // eax
  int v13; // edx
  int v14; // ecx
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // r9
  const EVENT_DESCRIPTOR *v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rcx
  int v21; // ecx
  DWORD v22; // eax
  const size_t *v23; // rbx
  DWORD v24; // eax
  __int64 v25; // rax
  const size_t *v26; // rbx
  DWORD CurrentThreadId; // eax
  _DWORD v28[4]; // [rsp+40h] [rbp-3758h] BYREF
  wchar_t *v29; // [rsp+60h] [rbp-3738h]
  __int64 v30; // [rsp+68h] [rbp-3730h]
  wchar_t *v31; // [rsp+70h] [rbp-3728h]
  int v32; // [rsp+78h] [rbp-3720h]
  int v33; // [rsp+7Ch] [rbp-371Ch]
  wchar_t *v34; // [rsp+80h] [rbp-3718h]
  int v35; // [rsp+88h] [rbp-3710h]
  int v36; // [rsp+8Ch] [rbp-370Ch]
  wchar_t Buffer[3504]; // [rsp+90h] [rbp-3708h] BYREF
  WCHAR OutputString[3504]; // [rsp+1BF0h] [rbp-1BA8h] BYREF

  v8 = vsnwprintf(Buffer, 0xDABu, a4, *a5);
  if ( v8 >= 0xDAC )
  {
    v9 = -2147024774;
  }
  else
  {
    v9 = 0;
    if ( v8 != 3499 )
      goto LABEL_6;
  }
  Buffer[3499] = 0;
LABEL_6:
  if ( v9 >= 0 )
  {
    v10 = a2 != -1 || a3;
    if ( a1 < 0 )
    {
      if ( v10 )
      {
        v26 = (const size_t *)a3;
        if ( !a3 )
          v26 = &cchOriginalDestLength;
        CurrentThreadId = GetCurrentThreadId();
        v12 = StringCchPrintfW(
                OutputString,
                0xDACu,
                L"%4d FAILED(%08X) %s (wid:%d %s)\n",
                CurrentThreadId,
                a1,
                Buffer,
                a2,
                v26);
      }
      else
      {
        v22 = GetCurrentThreadId();
        v12 = StringCchPrintfW(OutputString, 0xDACu, L"%4d FAILED(%08X) %s\n", v22, a1, Buffer);
      }
    }
    else if ( v10 )
    {
      v23 = (const size_t *)a3;
      if ( !a3 )
        v23 = &cchOriginalDestLength;
      v24 = GetCurrentThreadId();
      v12 = StringCchPrintfW(OutputString, 0xDACu, L"%4d %s (wid:%d %s)\n", v24, Buffer, a2, v23);
    }
    else
    {
      v11 = GetCurrentThreadId();
      v12 = StringCchPrintfW(OutputString, 0xDACu, L"%4d %s\n", v11, Buffer);
    }
    if ( v12 >= 0 )
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
    if ( dword_1802DBB08 )
    {
      EnterCriticalSection(&CriticalSection);
      StringCchCopyW(
        (wchar_t *)(qword_1802DBB10 + ((unsigned __int64)(unsigned int)dword_1802DBB0C << 11)),
        0x400u,
        OutputString);
      dword_1802DBB0C = (dword_1802DBB0C + 1) % (unsigned int)dword_1802DBB08;
      LeaveCriticalSection(&CriticalSection);
    }
    if ( !g_fETWLoggingChecked )
      ETWLog::CheckEnabled();
    if ( g_fETWLoggingEnabled || EventEnabled(Microsoft_Windows_Search_Core_Context, &MSSearchTraceId_ETWLogging) )
    {
      if ( a1 >= 0 )
      {
        if ( v10 )
        {
          if ( (byte_1802DA182 & 0x20) == 0 )
            return;
          v28[0] = a2;
          v29 = (wchar_t *)v28;
          v30 = 4;
          v19 = -1;
          if ( a3 )
          {
            v20 = -1;
            do
              ++v20;
            while ( a3[v20] );
            v21 = 2 * v20 + 2;
          }
          else
          {
            v21 = 10;
          }
          if ( !a3 )
            a3 = L"NULL";
          v31 = a3;
          v32 = v21;
          v33 = 0;
          do
            ++v19;
          while ( Buffer[v19] );
          v34 = Buffer;
          v35 = 2 * v19 + 2;
          v36 = 0;
          v17 = 4;
          v18 = (const EVENT_DESCRIPTOR *)&MSSearchTraceId_ETWLoggingItem;
        }
        else
        {
          if ( (byte_1802DA182 & 0x20) == 0 )
            return;
          v16 = -1;
          do
            ++v16;
          while ( Buffer[v16] );
          v29 = Buffer;
          v30 = (unsigned int)(2 * v16 + 2);
          v17 = 2;
          v18 = &MSSearchTraceId_ETWLogging;
        }
LABEL_25:
        McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_Search_Core_Context, v18, v15, v17);
        return;
      }
      if ( !v10 )
      {
        if ( (byte_1802DA182 & 0x20) == 0 )
          return;
        v28[0] = a1;
        v29 = (wchar_t *)v28;
        v30 = 4;
        v25 = -1;
        do
          ++v25;
        while ( Buffer[v25] );
        v31 = Buffer;
        v32 = 2 * v25 + 2;
        v33 = 0;
        v17 = 3;
        v18 = (const EVENT_DESCRIPTOR *)&MSSearchTraceId_ETWLoggingFailure;
        goto LABEL_25;
      }
      if ( (byte_1802DA182 & 0x20) != 0 )
        McTemplateU0qqzz_EventWriteTransfer(v14, v13, a1, a2, (__int64)a3, (__int64)Buffer);
    }
  }
}

```

## disassembly

```asm
0x18000c020  push    rbx
0x18000c022  push    rsi
0x18000c023  push    rdi
0x18000c024  push    r12
0x18000c026  push    r14
0x18000c028  push    r15
0x18000c02a  mov     eax, 3768h
0x18000c02f  call    _alloca_probe
0x18000c034  sub     rsp, rax
0x18000c037  mov     rax, cs:__security_cookie
0x18000c03e  xor     rax, rsp
0x18000c041  mov     [rsp+3798h+var_48], rax
0x18000c049  mov     rax, r9
0x18000c04c  mov     rdi, r8
0x18000c04f  mov     r12d, edx
0x18000c052  mov     r14d, ecx
0x18000c055  mov     r9, [rsp+3798h+arg_20]
0x18000c05d  mov     r9, [r9]; Args
0x18000c060  mov     r8, rax; Format
0x18000c063  mov     edx, 0DABh; BufferCount
0x18000c068  lea     rcx, [rsp+3798h+Buffer]; Buffer
0x18000c070  call    _vsnwprintf
0x18000c075  test    eax, eax
0x18000c077  js      short loc_18000C08F
0x18000c079  cmp     eax, 0DABh
0x18000c07e  ja      short loc_18000C08F
0x18000c080  xor     r15d, r15d
0x18000c083  mov     ecx, r15d
0x18000c086  cmp     eax, 0DABh
0x18000c08b  jz      short loc_18000C097
0x18000c08d  jmp     short loc_18000C0A0
0x18000c08f  xor     r15d, r15d
0x18000c092  mov     ecx, 8007007Ah
0x18000c097  mov     [rsp+3798h+var_1BB2], r15w
0x18000c0a0  test    ecx, ecx
0x18000c0a2  js      loc_18000C1AF
0x18000c0a8  cmp     r12d, 0FFFFFFFFh
0x18000c0ac  jz      loc_18000C1F0
0x18000c0b2  mov     sil, 1
0x18000c0b5  test    r14d, r14d
0x18000c0b8  js      loc_18000C2B8
0x18000c0be  test    sil, sil
0x18000c0c1  jnz     loc_18000C2FA
0x18000c0c7  call    cs:__imp_GetCurrentThreadId
0x18000c0cd  mov     r9d, eax
0x18000c0d0  lea     rax, [rsp+3798h+Buffer]
0x18000c0d8  mov     [rsp+3798h+var_3778], rax
0x18000c0dd  lea     r8, a4dS; "%4d %s\n"
0x18000c0e4  mov     edx, 0DACh; unsigned __int64
0x18000c0e9  lea     rcx, [rsp+3798h+OutputString]; wchar_t *
0x18000c0f1  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000c0f6  test    eax, eax
0x18000c0f8  jns     loc_18000C1D0
0x18000c0fe  cmp     cs:dword_1802DBB08, 0
0x18000c105  ja      loc_18000C42D
0x18000c10b  cmp     cs:?g_fETWLoggingChecked@@3_NA, 0; bool g_fETWLoggingChecked
0x18000c112  jz      loc_18000C485
0x18000c118  cmp     cs:?g_fETWLoggingEnabled@@3_NA, 0; bool g_fETWLoggingEnabled
0x18000c11f  jnz     short loc_18000C139
0x18000c121  lea     rdx, MSSearchTraceId_ETWLogging; EventDescriptor
0x18000c128  mov     rcx, cs:Microsoft_Windows_Search_Core_Context; RegHandle
0x18000c12f  call    cs:__imp_EventEnabled
0x18000c135  test    al, al
0x18000c137  jz      short loc_18000C1AF
0x18000c139  test    r14d, r14d
0x18000c13c  js      loc_18000C349
0x18000c142  test    sil, sil
0x18000c145  jnz     loc_18000C201
0x18000c14b  test    cs:byte_1802DA182, 20h
0x18000c152  jz      short loc_18000C1AF
0x18000c154  lea     rcx, [rsp+3798h+Buffer]
0x18000c15c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c163  lea     rax, [rax+1]
0x18000c167  cmp     word ptr [rcx+rax*2], 0
0x18000c16c  jnz     short loc_18000C163
0x18000c16e  lea     eax, ds:2[rax*2]
0x18000c175  lea     rcx, [rsp+3798h+Buffer]
0x18000c17d  mov     [rsp+3798h+var_3738], rcx
0x18000c182  mov     dword ptr [rsp+3798h+var_3730], eax
0x18000c186  mov     dword ptr [rsp+3798h+var_3730+4], r15d
0x18000c18b  lea     rax, [rsp+3798h+var_3748]
0x18000c190  mov     r9d, 2
0x18000c196  lea     rdx, MSSearchTraceId_ETWLogging
0x18000c19d  mov     [rsp+3798h+var_3778], rax
0x18000c1a2  lea     rcx, Microsoft_Windows_Search_Core_Context
0x18000c1a9  call    McGenEventWrite_EventWriteTransfer
0x18000c1ae  nop
0x18000c1af  mov     rcx, [rsp+3798h+var_48]
0x18000c1b7  xor     rcx, rsp; StackCookie
0x18000c1ba  call    __security_check_cookie
0x18000c1bf  add     rsp, 3768h
0x18000c1c6  pop     r15
0x18000c1c8  pop     r14
0x18000c1ca  pop     r12
0x18000c1cc  pop     rdi
0x18000c1cd  pop     rsi
0x18000c1ce  pop     rbx
0x18000c1cf  retn
0x18000c1d0  cmp     cs:?g_fETWLoggingEnabled@@3_NA, 0; bool g_fETWLoggingEnabled
0x18000c1d7  jz      loc_18000C0FE
0x18000c1dd  lea     rcx, [rsp+3798h+OutputString]; lpOutputString
0x18000c1e5  call    cs:__imp_OutputDebugStringW
0x18000c1eb  jmp     loc_18000C0FE
0x18000c1f0  test    rdi, rdi
0x18000c1f3  jnz     loc_18000C0B2
0x18000c1f9  xor     sil, sil
0x18000c1fc  jmp     loc_18000C0B5
0x18000c201  test    cs:byte_1802DA182, 20h
0x18000c208  jz      short loc_18000C1AF
0x18000c20a  mov     [rsp+3798h+var_3758], r12d
0x18000c20f  lea     rax, [rsp+3798h+var_3758]
0x18000c214  mov     [rsp+3798h+var_3738], rax
0x18000c219  mov     [rsp+3798h+var_3730], 4
0x18000c222  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c229  test    rdi, rdi
0x18000c22c  jz      loc_18000C3CF
0x18000c232  mov     rcx, rax
0x18000c235  lea     rcx, [rcx+1]
0x18000c239  cmp     word ptr [rdi+rcx*2], 0
0x18000c23e  jnz     short loc_18000C235
0x18000c240  lea     ecx, ds:2[rcx*2]
0x18000c247  lea     rdx, aNull_0; "NULL"
0x18000c24e  test    rdi, rdi
0x18000c251  cmovz   rdi, rdx
0x18000c255  mov     [rsp+3798h+var_3728], rdi
0x18000c25a  mov     [rsp+3798h+var_3720], ecx
0x18000c25e  mov     [rsp+3798h+var_371C], r15d
0x18000c263  lea     rcx, [rsp+3798h+Buffer]
0x18000c26b  nop     dword ptr [rax+rax+00h]
0x18000c270  lea     rax, [rax+1]
0x18000c274  cmp     word ptr [rcx+rax*2], 0
0x18000c279  jnz     short loc_18000C270
0x18000c27b  lea     eax, ds:2[rax*2]
0x18000c282  lea     rcx, [rsp+3798h+Buffer]
0x18000c28a  mov     [rsp+3798h+var_3718], rcx
0x18000c292  mov     [rsp+3798h+var_3710], eax
0x18000c299  mov     [rsp+3798h+var_370C], r15d
0x18000c2a1  lea     rax, [rsp+3798h+var_3748]
0x18000c2a6  mov     r9d, 4
0x18000c2ac  lea     rdx, MSSearchTraceId_ETWLoggingItem
0x18000c2b3  jmp     loc_18000C19D
0x18000c2b8  test    sil, sil
0x18000c2bb  jnz     loc_18000C3D9
0x18000c2c1  call    cs:__imp_GetCurrentThreadId
0x18000c2c7  mov     r9d, eax
0x18000c2ca  lea     rax, [rsp+3798h+Buffer]
0x18000c2d2  mov     [rsp+3798h+var_3770], rax
0x18000c2d7  mov     dword ptr [rsp+3798h+var_3778], r14d
0x18000c2dc  lea     r8, a4dFailed08xS; "%4d FAILED(%08X) %s\n"
0x18000c2e3  mov     edx, 0DACh; unsigned __int64
0x18000c2e8  lea     rcx, [rsp+3798h+OutputString]; wchar_t *
0x18000c2f0  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000c2f5  jmp     loc_18000C0F6
0x18000c2fa  lea     rax, cchOriginalDestLength
0x18000c301  mov     rbx, rdi
0x18000c304  test    rdi, rdi
0x18000c307  cmovz   rbx, rax
0x18000c30b  call    cs:__imp_GetCurrentThreadId
0x18000c311  mov     r9d, eax
0x18000c314  mov     [rsp+3798h+var_3768], rbx
0x18000c319  mov     dword ptr [rsp+3798h+var_3770], r12d
0x18000c31e  lea     rax, [rsp+3798h+Buffer]
0x18000c326  mov     [rsp+3798h+var_3778], rax
0x18000c32b  lea     r8, a4dSWidDS; "%4d %s (wid:%d %s)\n"
0x18000c332  mov     edx, 0DACh; unsigned __int64
0x18000c337  lea     rcx, [rsp+3798h+OutputString]; wchar_t *
0x18000c33f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000c344  jmp     loc_18000C0F6
0x18000c349  test    sil, sil
0x18000c34c  jnz     loc_18000C48F
0x18000c352  test    cs:byte_1802DA182, 20h
0x18000c359  jz      loc_18000C1AF
0x18000c35f  mov     [rsp+3798h+var_3758], r14d
0x18000c364  lea     rax, [rsp+3798h+var_3758]
0x18000c369  mov     [rsp+3798h+var_3738], rax
0x18000c36e  mov     [rsp+3798h+var_3730], 4
0x18000c377  lea     rcx, [rsp+3798h+Buffer]
0x18000c37f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c386  nop     word ptr [rax+rax+00000000h]
0x18000c390  lea     rax, [rax+1]
0x18000c394  cmp     word ptr [rcx+rax*2], 0
0x18000c399  jnz     short loc_18000C390
0x18000c39b  lea     eax, ds:2[rax*2]
0x18000c3a2  lea     rcx, [rsp+3798h+Buffer]
0x18000c3aa  mov     [rsp+3798h+var_3728], rcx
0x18000c3af  mov     [rsp+3798h+var_3720], eax
0x18000c3b3  mov     [rsp+3798h+var_371C], r15d
0x18000c3b8  lea     rax, [rsp+3798h+var_3748]
0x18000c3bd  mov     r9d, 3
0x18000c3c3  lea     rdx, MSSearchTraceId_ETWLoggingFailure
0x18000c3ca  jmp     loc_18000C19D
0x18000c3cf  mov     ecx, 0Ah
0x18000c3d4  jmp     loc_18000C247
0x18000c3d9  lea     rax, cchOriginalDestLength
0x18000c3e0  mov     rbx, rdi
0x18000c3e3  test    rdi, rdi
0x18000c3e6  cmovz   rbx, rax
0x18000c3ea  call    cs:__imp_GetCurrentThreadId
0x18000c3f0  mov     r9d, eax
0x18000c3f3  mov     [rsp+3798h+var_3760], rbx
0x18000c3f8  mov     dword ptr [rsp+3798h+var_3768], r12d
0x18000c3fd  lea     rax, [rsp+3798h+Buffer]
0x18000c405  mov     [rsp+3798h+var_3770], rax
0x18000c40a  mov     dword ptr [rsp+3798h+var_3778], r14d
0x18000c40f  lea     r8, a4dFailed08xSWi; "%4d FAILED(%08X) %s (wid:%d %s)\n"
0x18000c416  mov     edx, 0DACh; unsigned __int64
0x18000c41b  lea     rcx, [rsp+3798h+OutputString]; wchar_t *
0x18000c423  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000c428  jmp     loc_18000C0F6
0x18000c42d  lea     rcx, CriticalSection; lpCriticalSection
0x18000c434  call    cs:__imp_EnterCriticalSection
0x18000c43a  mov     ecx, cs:dword_1802DBB0C
0x18000c440  shl     rcx, 0Bh
0x18000c444  add     rcx, cs:qword_1802DBB10; wchar_t *
0x18000c44b  lea     r8, [rsp+3798h+OutputString]; wchar_t *
0x18000c453  mov     edx, 400h; unsigned __int64
0x18000c458  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000c45d  mov     eax, cs:dword_1802DBB0C
0x18000c463  inc     eax
0x18000c465  xor     edx, edx
0x18000c467  div     cs:dword_1802DBB08
0x18000c46d  mov     cs:dword_1802DBB0C, edx
0x18000c473  lea     rcx, CriticalSection; lpCriticalSection
0x18000c47a  call    cs:__imp_LeaveCriticalSection
0x18000c480  jmp     loc_18000C10B
0x18000c485  call    ?CheckEnabled@ETWLog@@CAXXZ; ETWLog::CheckEnabled(void)
0x18000c48a  jmp     loc_18000C118
0x18000c48f  test    cs:byte_1802DA182, 20h
0x18000c496  jz      loc_18000C1AF
0x18000c49c  lea     rax, [rsp+3798h+Buffer]
0x18000c4a4  mov     [rsp+3798h+var_3770], rax
0x18000c4a9  mov     [rsp+3798h+var_3778], rdi
0x18000c4ae  mov     r9d, r12d
0x18000c4b1  mov     r8d, r14d
0x18000c4b4  call    McTemplateU0qqzz_EventWriteTransfer
0x18000c4b9  jmp     loc_18000C1AF
0x18000c4be  jmp     loc_18000C1AF
```
