# HyperVFileIo::Reconnect(void)

- ea: `0x1800811b0`
- end: `0x1800814ff`
- name: `?Reconnect@HyperVFileIo@@UEAAHXZ`
- size: `847`
- prototype: `__int64 __fastcall(HyperVFileIo *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18007e39c`

## callees

- `0x180007dbc`
- `0x180007e24`
- `0x180066284`
- `0x18007eccc`
- `0x18007f66c`
- `0x18007fb2c`
- `0x180080c2c`
- `0x1800811b0`
- `0x180081f2c`
- `0x180082140`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008138b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008138b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180081393`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180081393`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800812b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800812b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800812fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800812fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800812b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800812b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800813a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800813a4`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800812ec`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800812ec`

## pseudocode

```c
__int64 __fastcall HyperVFileIo::Reconnect(HyperVFileIo *this)
{
  char *v1; // rbx
  unsigned int v2; // r14d
  bool v3; // cc
  char *v5; // rcx
  signed int v6; // eax
  signed int v7; // r13d
  int IsDebugTraceEnabled; // ebp
  char v9; // r12
  _DWORD *v10; // rcx
  bool v11; // si
  char *v12; // r8
  DWORD CurrentThreadId; // eax
  HANDLE v14; // r15
  signed int LastError; // esi
  struct _FILETIME v16; // rcx
  const unsigned __int16 *v17; // r8
  unsigned int v18; // esi
  RTL_SRWLOCK *v19; // rcx
  const unsigned __int16 *v20; // r8
  int v21; // esi
  _DWORD *v22; // rcx
  char *v23; // r8
  struct _GUID v25; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v26; // [rsp+80h] [rbp+8h] BYREF
  HANDLE hFile; // [rsp+88h] [rbp+10h] BYREF

  v1 = (char *)this + 40;
  v2 = *((_DWORD *)this + 36) & 0xFFFFFDFC;
  hFile = (HANDLE)-1LL;
  v3 = *((_QWORD *)this + 8) <= 7u;
  v26 = 0;
  if ( v3 )
    v5 = (char *)this + 40;
  else
    v5 = *(char **)v1;
  v6 = HyperVFileIo::OpenInternal((__int64)v5, v2, &hFile, (BOOL *)&v26);
  v26 = 0;
  v7 = v6;
  IsDebugTraceEnabled = HvsIsDebugTraceEnabled(0xC000u);
  v9 = 1;
  v10 = (_DWORD *)*((_QWORD *)HyperVStorageTrace::Instance() + 1);
  v11 = v10 && *v10;
  if ( IsDebugTraceEnabled || v11 )
  {
    if ( dword_1800E483C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 16LL) )
    {
      Init_thread_header(&dword_1800E483C);
      if ( dword_1800E483C == -1 )
      {
        byte_1800E244C = IsDebugTraceEnabled != 0;
        byte_1800E244D = v11;
        Init_thread_footer(&dword_1800E483C);
      }
    }
    if ( *((_QWORD *)v1 + 3) <= 7u )
      v12 = v1;
    else
      v12 = *(char **)v1;
    HvsDebugTraceInternal(0xC000u, (const struct HvsDebugTraceParameters *)&off_1800E2438, v12);
  }
  if ( v7 < 0 )
    goto LABEL_47;
  AcquireSRWLockExclusive((PSRWLOCK)this + 3);
  CurrentThreadId = GetCurrentThreadId();
  v14 = hFile;
  *((_DWORD *)this + 8) = CurrentThreadId;
  if ( *((_QWORD *)this + 9) != -1 )
    goto LABEL_29;
  if ( GetFileTime(v14, (LPFILETIME)this + 16, 0, (LPFILETIME)this + 17) )
    LastError = 0;
  else
    LastError = GetLastError();
  v16 = (struct _FILETIME)*((_QWORD *)this + 17);
  if ( *((_QWORD *)v1 + 3) <= 7u )
    v17 = (const unsigned __int16 *)v1;
  else
    v17 = *(const unsigned __int16 **)v1;
  v25 = *(struct _GUID *)((char *)this + 8);
  HyperVStorageTrace::HyperVFileIo_GetFileTime(&v25, L"HyperVFileIo::Reconnect", v17, v14, v16, LastError);
  if ( LastError )
  {
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    else
      v7 = LastError;
    v9 = 1;
LABEL_29:
    v18 = v26;
    goto LABEL_30;
  }
  v9 = 1;
  *((_QWORD *)this + 9) = v14;
  v18 = 1;
  v26 = 1;
  *((_DWORD *)this + 36) = v2;
LABEL_30:
  v19 = (RTL_SRWLOCK *)((char *)this + 24);
  if ( *((_DWORD *)this + 8) )
  {
    *((_DWORD *)this + 8) = 0;
    ReleaseSRWLockExclusive(v19);
  }
  else
  {
    ReleaseSRWLockShared(v19);
  }
  if ( v18 )
    goto LABEL_48;
  CloseHandle(v14);
  if ( *((_QWORD *)v1 + 3) <= 7u )
    v20 = (const unsigned __int16 *)v1;
  else
    v20 = *(const unsigned __int16 **)v1;
  v25 = *(struct _GUID *)((char *)this + 8);
  HyperVStorageTrace::HyperVFileIo_Close(&v25, L"HyperVFileIo::Reconnect", v20, v14);
  v21 = HvsIsDebugTraceEnabled(0xC000u);
  v22 = (_DWORD *)*((_QWORD *)HyperVStorageTrace::Instance() + 1);
  if ( !v22 || !*v22 )
    v9 = 0;
  if ( v21 || v9 )
  {
    if ( dword_1800E4840 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 16LL) )
    {
      Init_thread_header(&dword_1800E4840);
      if ( dword_1800E4840 == -1 )
      {
        byte_1800E241C = v21 != 0;
        byte_1800E241D = v9;
        Init_thread_footer(&dword_1800E4840);
      }
    }
    if ( *((_QWORD *)v1 + 3) <= 7u )
      v23 = v1;
    else
      v23 = *(char **)v1;
    HvsDebugTraceInternal(0xC000u, (const struct HvsDebugTraceParameters *)&off_1800E2408, v23);
  }
LABEL_47:
  v18 = v26;
LABEL_48:
  if ( *((_QWORD *)v1 + 3) > 7u )
    v1 = *(char **)v1;
  v25 = *(struct _GUID *)((char *)this + 8);
  HyperVStorageTrace::HyperVFileIo_Reconnect(&v25, (const unsigned __int16 *)v1, v7);
  return v18;
}

```

## disassembly

```asm
0x1800811b0  mov     rax, rsp
0x1800811b3  mov     [rax+18h], rbx
0x1800811b7  push    rbp
0x1800811b8  push    rsi
0x1800811b9  push    rdi
0x1800811ba  push    r12
0x1800811bc  push    r13
0x1800811be  push    r14
0x1800811c0  push    r15
0x1800811c2  sub     rsp, 40h
0x1800811c6  mov     r14d, [rcx+90h]
0x1800811cd  lea     rbx, [rcx+28h]
0x1800811d1  and     r14d, 0FFFFFDFCh
0x1800811d8  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x1800811e0  cmp     qword ptr [rbx+18h], 7
0x1800811e5  mov     rdi, rcx
0x1800811e8  mov     dword ptr [rax+8], 0
0x1800811ef  jbe     short loc_1800811F6
0x1800811f1  mov     rcx, [rbx]
0x1800811f4  jmp     short loc_1800811F9
0x1800811f6  mov     rcx, rbx
0x1800811f9  lea     r9, [rsp+78h+arg_0]
0x180081201  mov     edx, r14d
0x180081204  lea     r8, [rsp+78h+hFile]
0x18008120c  call    ?OpenInternal@HyperVFileIo@@CAJPEBGW4HyperVFileOpenFlags@@PEAPEAXPEAH@Z; HyperVFileIo::OpenInternal(ushort const *,HyperVFileOpenFlags,void * *,int *)
0x180081211  mov     ecx, 0C000h; unsigned __int16
0x180081216  mov     [rsp+78h+arg_0], 0
0x180081221  mov     r13d, eax
0x180081224  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x180081229  test    eax, eax
0x18008122b  mov     ebp, eax
0x18008122d  setnz   r15b
0x180081231  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x180081236  mov     r12d, 1
0x18008123c  mov     rcx, [rax+8]
0x180081240  test    rcx, rcx
0x180081243  jz      short loc_180081250
0x180081245  mov     ecx, [rcx]
0x180081247  test    ecx, ecx
0x180081249  jz      short loc_180081250
0x18008124b  mov     sil, r12b
0x18008124e  jmp     short loc_180081253
0x180081250  xor     sil, sil
0x180081253  mov     edx, 10h
0x180081258  test    ebp, ebp
0x18008125a  jnz     short loc_180081261
0x18008125c  test    sil, sil
0x18008125f  jz      short loc_1800812A3
0x180081261  mov     ecx, cs:_tls_index
0x180081267  mov     rax, gs:58h
0x180081270  mov     rax, [rax+rcx*8]
0x180081274  mov     eax, [rdx+rax]
0x180081277  cmp     cs:dword_1800E483C, eax
0x18008127d  jg      loc_1800814C7
0x180081283  cmp     qword ptr [rbx+18h], 7
0x180081288  jbe     short loc_18008128F
0x18008128a  mov     r8, [rbx]
0x18008128d  jmp     short loc_180081292
0x18008128f  mov     r8, rbx
0x180081292  lea     rdx, off_1800E2438; struct HvsDebugTraceParameters *
0x180081299  mov     ecx, 0C000h; unsigned int
0x18008129e  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x1800812a3  test    r13d, r13d
0x1800812a6  js      loc_18008144E
0x1800812ac  lea     rbp, [rdi+18h]
0x1800812b0  mov     rcx, rbp; SRWLock
0x1800812b3  call    cs:__imp_AcquireSRWLockExclusive
0x1800812b9  call    cs:__imp_GetCurrentThreadId
0x1800812bf  mov     r15, [rsp+78h+hFile]
0x1800812c7  mov     [rbp+8], eax
0x1800812ca  cmp     qword ptr [rdi+48h], 0FFFFFFFFFFFFFFFFh
0x1800812cf  jnz     loc_180081374
0x1800812d5  lea     r12, [rdi+88h]
0x1800812dc  xor     r8d, r8d; lpLastAccessTime
0x1800812df  mov     r9, r12; lpLastWriteTime
0x1800812e2  lea     rdx, [rdi+80h]; lpCreationTime
0x1800812e9  mov     rcx, r15; hFile
0x1800812ec  call    cs:__imp_GetFileTime
0x1800812f2  test    eax, eax
0x1800812f4  jz      short loc_1800812FA
0x1800812f6  xor     esi, esi
0x1800812f8  jmp     short loc_180081302
0x1800812fa  call    cs:__imp_GetLastError
0x180081300  mov     esi, eax
0x180081302  cmp     qword ptr [rbx+18h], 7
0x180081307  mov     rcx, [r12]
0x18008130b  jbe     short loc_180081312
0x18008130d  mov     r8, [rbx]
0x180081310  jmp     short loc_180081315
0x180081312  mov     r8, rbx; unsigned __int16 *
0x180081315  movups  xmm0, xmmword ptr [rdi+8]
0x180081319  mov     [rsp+78h+var_50], esi; unsigned int
0x18008131d  lea     rdx, aHypervfileioRe; "HyperVFileIo::Reconnect"
0x180081324  mov     qword ptr [rsp+78h+var_58.dwLowDateTime], rcx; struct _FILETIME
0x180081329  mov     r9, r15; void *
0x18008132c  lea     rcx, [rsp+78h+var_48]; struct _GUID *
0x180081331  movdqu  xmmword ptr [rsp+78h+var_48.Data1], xmm0
0x180081337  call    ?HyperVFileIo_GetFileTime@HyperVStorageTrace@@SAXU_GUID@@PEBG1PEAXU_FILETIME@@K@Z; HyperVStorageTrace::HyperVFileIo_GetFileTime(_GUID,ushort const *,ushort const *,void *,_FILETIME,ulong)
0x18008133c  test    esi, esi
0x18008133e  jnz     short loc_18008135C
0x180081340  lea     r12d, [rsi+1]
0x180081344  mov     [rdi+48h], r15
0x180081348  mov     esi, r12d
0x18008134b  mov     [rsp+78h+arg_0], r12d
0x180081353  mov     [rdi+90h], r14d
0x18008135a  jmp     short loc_18008137B
0x18008135c  jg      short loc_180081363
0x18008135e  mov     r13d, esi
0x180081361  jmp     short loc_18008136E
0x180081363  movzx   r13d, si
0x180081367  or      r13d, 80070000h
0x18008136e  mov     r12d, 1
0x180081374  mov     esi, [rsp+78h+arg_0]
0x18008137b  cmp     dword ptr [rbp+8], 0
0x18008137f  mov     rcx, rbp; SRWLock
0x180081382  jz      short loc_180081393
0x180081384  mov     dword ptr [rbp+8], 0
0x18008138b  call    cs:__imp_ReleaseSRWLockExclusive
0x180081391  jmp     short loc_180081399
0x180081393  call    cs:__imp_ReleaseSRWLockShared
0x180081399  test    esi, esi
0x18008139b  jnz     loc_180081455
0x1800813a1  mov     rcx, r15; hObject
0x1800813a4  call    cs:__imp_CloseHandle
0x1800813aa  cmp     qword ptr [rbx+18h], 7
0x1800813af  jbe     short loc_1800813B6
0x1800813b1  mov     r8, [rbx]
0x1800813b4  jmp     short loc_1800813B9
0x1800813b6  mov     r8, rbx; unsigned __int16 *
0x1800813b9  movups  xmm0, xmmword ptr [rdi+8]
0x1800813bd  mov     r9, r15; void *
0x1800813c0  lea     rdx, aHypervfileioRe; "HyperVFileIo::Reconnect"
0x1800813c7  lea     rcx, [rsp+78h+var_48]; struct _GUID
0x1800813cc  movdqu  xmmword ptr [rsp+78h+var_48.Data1], xmm0
0x1800813d2  call    ?HyperVFileIo_Close@HyperVStorageTrace@@SAXU_GUID@@PEBG1PEAX@Z; HyperVStorageTrace::HyperVFileIo_Close(_GUID,ushort const *,ushort const *,void *)
0x1800813d7  mov     r14d, 0C000h
0x1800813dd  mov     ecx, r14d; unsigned __int16
0x1800813e0  call    ?HvsIsDebugTraceEnabled@@YAHG@Z; HvsIsDebugTraceEnabled(ushort)
0x1800813e5  test    eax, eax
0x1800813e7  mov     esi, eax
0x1800813e9  setnz   bpl
0x1800813ed  call    ?Instance@HyperVStorageTrace@@KAPEAV1@XZ; HyperVStorageTrace::Instance(void)
0x1800813f2  mov     rcx, [rax+8]
0x1800813f6  test    rcx, rcx
0x1800813f9  jz      short loc_180081401
0x1800813fb  mov     ecx, [rcx]
0x1800813fd  test    ecx, ecx
0x1800813ff  jnz     short loc_180081404
0x180081401  xor     r12b, r12b
0x180081404  test    esi, esi
0x180081406  jnz     short loc_18008140D
0x180081408  test    r12b, r12b
0x18008140b  jz      short loc_18008144E
0x18008140d  mov     ecx, cs:_tls_index
0x180081413  mov     rax, gs:58h
0x18008141c  mov     edx, 10h
0x180081421  mov     rax, [rax+rcx*8]
0x180081425  mov     eax, [rdx+rax]
0x180081428  cmp     cs:dword_1800E4840, eax
0x18008142e  jg      short loc_180081493
0x180081430  cmp     qword ptr [rbx+18h], 7
0x180081435  jbe     short loc_18008143C
0x180081437  mov     r8, [rbx]
0x18008143a  jmp     short loc_18008143F
0x18008143c  mov     r8, rbx
0x18008143f  lea     rdx, off_1800E2408; struct HvsDebugTraceParameters *
0x180081446  mov     ecx, r14d; unsigned int
0x180081449  call    ?HvsDebugTraceInternal@@YAXIPEBUHvsDebugTraceParameters@@ZZ; HvsDebugTraceInternal(uint,HvsDebugTraceParameters const *,...)
0x18008144e  mov     esi, [rsp+78h+arg_0]
0x180081455  cmp     qword ptr [rbx+18h], 7
0x18008145a  jbe     short loc_18008145F
0x18008145c  mov     rbx, [rbx]
0x18008145f  movups  xmm0, xmmword ptr [rdi+8]
0x180081463  mov     r8d, r13d; int
0x180081466  lea     rcx, [rsp+78h+var_48]; struct _GUID
0x18008146b  mov     rdx, rbx; unsigned __int16 *
0x18008146e  movdqu  xmmword ptr [rsp+78h+var_48.Data1], xmm0
0x180081474  call    ?HyperVFileIo_Reconnect@HyperVStorageTrace@@SAXU_GUID@@PEBGJ@Z; HyperVStorageTrace::HyperVFileIo_Reconnect(_GUID,ushort const *,long)
0x180081479  mov     rbx, [rsp+78h+arg_10]
0x180081481  mov     eax, esi
0x180081483  add     rsp, 40h
0x180081487  pop     r15
0x180081489  pop     r14
0x18008148b  pop     r13
0x18008148d  pop     r12
0x18008148f  pop     rdi
0x180081490  pop     rsi
0x180081491  pop     rbp
0x180081492  retn
0x180081493  lea     rcx, dword_1800E4840
0x18008149a  call    _Init_thread_header
0x18008149f  cmp     cs:dword_1800E4840, 0FFFFFFFFh
0x1800814a6  jnz     short loc_180081430
0x1800814a8  lea     rcx, dword_1800E4840
0x1800814af  mov     cs:byte_1800E241C, bpl
0x1800814b6  mov     cs:byte_1800E241D, r12b
0x1800814bd  call    _Init_thread_footer
0x1800814c2  jmp     loc_180081430
0x1800814c7  lea     rcx, dword_1800E483C
0x1800814ce  call    _Init_thread_header
0x1800814d3  cmp     cs:dword_1800E483C, 0FFFFFFFFh
0x1800814da  jnz     loc_180081283
0x1800814e0  lea     rcx, dword_1800E483C
0x1800814e7  mov     cs:byte_1800E244C, r15b
0x1800814ee  mov     cs:byte_1800E244D, sil
0x1800814f5  call    _Init_thread_footer
0x1800814fa  jmp     loc_180081283
```
