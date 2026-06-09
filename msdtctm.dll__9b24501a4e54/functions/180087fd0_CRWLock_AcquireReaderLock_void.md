# CRWLock::AcquireReaderLock(void)

- ea: `0x180087fd0`
- end: `0x1800881f3`
- name: `?AcquireReaderLock@CRWLock@@QEAAJXZ`
- size: `547`
- prototype: `__int64 __fastcall(CRWLock *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180025b20`

## callees

- `0x180084698`
- `0x1800846c0`
- `0x180087fd0`
- `0x1800881fc`
- `0x1800883b0`
- `0x1800885bc`
- `0x1800886c4`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180087ff8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180087ff8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180088168`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180088168`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800880d8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180088155`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800880d8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180088155`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800880f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800880f9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180088186`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180088186`

## string_xrefs

- `0x1800881e6`: `Failed to acquire reader lock`

## pseudocode

```c
__int64 __fastcall CRWLock::AcquireReaderLock(CRWLock *this)
{
  int v2; // ebx
  signed int v3; // ebx
  unsigned __int32 v5; // esi
  int v6; // r12d
  unsigned __int32 v7; // r8d
  int v8; // edx
  void *ReaderEvent; // rax
  void *v10; // r14
  DWORD v11; // eax
  DWORD v12; // ebp
  unsigned int v13; // ecx
  signed int LastError; // eax
  signed __int32 v15; // ecx
  unsigned int v16; // r15d
  bool v17; // zf

  if ( (*((_BYTE *)this + 92) & 1) == 0 )
    (**(void (__fastcall ***)(CRWLock *))this)(this);
  v2 = *((_DWORD *)this + 21);
  if ( v2 == GetCurrentThreadId() )
    return (unsigned int)CRWLock::AcquireWriterLock(this);
  v3 = 0;
  if ( (unsigned int)CRWLock::DoesThisThreadOwnReadLock(this) )
    return (unsigned int)v3;
  v5 = *((_DWORD *)this + 20);
  v6 = 0;
  while ( 1 )
  {
    v7 = v5;
    if ( v5 < 0x3FF || (v8 = v5 & 0x3FF, (v5 & 0x1400) == 0x400) && v8 + ((v5 >> 13) & 0x3FF) <= 0x3FD )
    {
      v5 = _InterlockedCompareExchange((volatile signed __int32 *)this + 20, v5 + 1, v5);
      v17 = v5 == v7;
      goto LABEL_36;
    }
    if ( (v5 & 0x7FE000) == 8380416 || v8 == 1023 || (v5 & 0xC00) == 0x400 )
    {
      Sleep(0x3E8u);
      v6 = 0;
LABEL_34:
      v5 = *((_DWORD *)this + 20);
      goto LABEL_37;
    }
    if ( ++v6 <= gdwDefaultSpinCount )
      goto LABEL_34;
    v5 = _InterlockedCompareExchange((volatile signed __int32 *)this + 20, v5 + 0x2000, v5);
    if ( v5 == v7 )
      break;
LABEL_37:
    if ( v3 == -2147417825 )
    {
      v3 = 0;
      DtcDebugBreak();
    }
    else if ( v3 < 0 )
    {
      goto LABEL_44;
    }
  }
  ReaderEvent = CRWLock::GetReaderEvent(this);
  v10 = ReaderEvent;
  if ( ReaderEvent )
  {
    v11 = WaitForSingleObject(ReaderEvent, 0xFFFFFFFF);
    v12 = v11;
    if ( !v11 )
    {
      v13 = -8191;
      goto LABEL_24;
    }
    if ( v11 == 258 )
    {
      v3 = -2147417825;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v12 = -1;
    v3 = -2147417855;
  }
  v13 = -8192;
LABEL_24:
  v15 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 20, v13);
  if ( (v15 & 0x7FE000) == 0x2000 && (v15 & 0x400) != 0 )
  {
    v16 = -1024;
    if ( v12 )
    {
      if ( !v10 )
        v10 = CRWLock::GetReaderEvent(this);
      v3 = 0;
      v16 = -1023;
      v12 = WaitForSingleObject(v10, 0xFFFFFFFF);
    }
    if ( !ResetEvent(v10) )
      DtcInternalErrorW(L"ResetEvent failed");
    _InterlockedAdd((volatile signed __int32 *)this + 20, v16);
  }
  v17 = v12 == 0;
LABEL_36:
  if ( !v17 )
    goto LABEL_37;
  if ( v3 < 0 || (v3 = CRWLock::AddToListOfGrantedReaders(this), v3 < 0) )
LABEL_44:
    DtcInternalErrorW(L"Failed to acquire reader lock");
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180087fd0  push    rbx
0x180087fd2  push    rbp
0x180087fd3  push    rsi
0x180087fd4  push    rdi
0x180087fd5  push    r12
0x180087fd7  push    r13
0x180087fd9  push    r14
0x180087fdb  push    r15
0x180087fdd  sub     rsp, 28h
0x180087fe1  test    byte ptr [rcx+5Ch], 1
0x180087fe5  mov     rdi, rcx
0x180087fe8  jnz     short loc_180087FF5
0x180087fea  mov     rax, [rcx]
0x180087fed  mov     rax, [rax]
0x180087ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087ff5  mov     ebx, [rdi+54h]
0x180087ff8  call    cs:__imp_GetCurrentThreadId
0x180087ffe  mov     rcx, rdi; this
0x180088001  cmp     ebx, eax
0x180088003  jnz     short loc_18008801F
0x180088005  call    ?AcquireWriterLock@CRWLock@@QEAAJXZ; CRWLock::AcquireWriterLock(void)
0x18008800a  mov     ebx, eax
0x18008800c  mov     eax, ebx
0x18008800e  add     rsp, 28h
0x180088012  pop     r15
0x180088014  pop     r14
0x180088016  pop     r13
0x180088018  pop     r12
0x18008801a  pop     rdi
0x18008801b  pop     rsi
0x18008801c  pop     rbp
0x18008801d  pop     rbx
0x18008801e  retn
0x18008801f  xor     ebx, ebx
0x180088021  call    ?DoesThisThreadOwnReadLock@CRWLock@@AEAAHXZ; CRWLock::DoesThisThreadOwnReadLock(void)
0x180088026  test    eax, eax
0x180088028  jnz     short loc_18008800C
0x18008802a  mov     esi, [rdi+50h]
0x18008802d  mov     r13d, 3FFh
0x180088033  xor     r12d, r12d
0x180088036  lea     r15d, [r13+1]
0x18008803a  mov     r8d, esi
0x18008803d  cmp     esi, r13d
0x180088040  jb      loc_180088194
0x180088046  mov     edx, esi
0x180088048  mov     eax, esi
0x18008804a  and     edx, r13d
0x18008804d  and     eax, 1400h
0x180088052  cmp     eax, r15d
0x180088055  jnz     short loc_18008806C
0x180088057  mov     eax, esi
0x180088059  shr     eax, 0Dh
0x18008805c  and     eax, r13d
0x18008805f  add     eax, edx
0x180088061  cmp     eax, 3FDh
0x180088066  jbe     loc_180088194
0x18008806c  mov     eax, esi
0x18008806e  and     eax, 7FE000h
0x180088073  cmp     eax, 7FE000h
0x180088078  setnz   cl
0x18008807b  cmp     edx, r13d
0x18008807e  setnz   al
0x180088081  test    al, cl
0x180088083  jz      loc_180088181
0x180088089  mov     ecx, esi
0x18008808b  and     ecx, 0C00h
0x180088091  cmp     ecx, r15d
0x180088094  jz      loc_180088181
0x18008809a  inc     r12d
0x18008809d  cmp     r12d, cs:?gdwDefaultSpinCount@@3KA; ulong gdwDefaultSpinCount
0x1800880a4  jbe     loc_18008818F
0x1800880aa  lea     ecx, [rsi+2000h]
0x1800880b0  mov     eax, esi
0x1800880b2  lock cmpxchg [rdi+50h], ecx
0x1800880b7  mov     esi, eax
0x1800880b9  cmp     eax, r8d
0x1800880bc  jnz     loc_1800881A5
0x1800880c2  mov     rcx, rdi; this
0x1800880c5  call    ?GetReaderEvent@CRWLock@@AEAAPEAXXZ; CRWLock::GetReaderEvent(void)
0x1800880ca  mov     r14, rax
0x1800880cd  test    rax, rax
0x1800880d0  jz      short loc_180088110
0x1800880d2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800880d5  mov     rcx, rax; hHandle
0x1800880d8  call    cs:__imp_WaitForSingleObject
0x1800880de  mov     ebp, eax
0x1800880e0  test    eax, eax
0x1800880e2  jnz     short loc_1800880EB
0x1800880e4  mov     ecx, 0FFFFE001h
0x1800880e9  jmp     short loc_18008811D
0x1800880eb  cmp     eax, 102h
0x1800880f0  jnz     short loc_1800880F9
0x1800880f2  mov     ebx, 8001011Fh
0x1800880f7  jmp     short loc_180088118
0x1800880f9  call    cs:__imp_GetLastError
0x1800880ff  mov     ebx, eax
0x180088101  test    eax, eax
0x180088103  jle     short loc_180088118
0x180088105  movzx   ebx, ax
0x180088108  or      ebx, 80070000h
0x18008810e  jmp     short loc_180088118
0x180088110  or      ebp, 0FFFFFFFFh
0x180088113  mov     ebx, 80010101h
0x180088118  mov     ecx, 0FFFFE000h
0x18008811d  lock xadd [rdi+50h], ecx
0x180088122  mov     eax, ecx
0x180088124  and     eax, 7FE000h
0x180088129  cmp     eax, 2000h
0x18008812e  jnz     short loc_18008817D
0x180088130  test    r15d, ecx
0x180088133  jz      short loc_18008817D
0x180088135  mov     r15d, 0FFFFFC00h
0x18008813b  test    ebp, ebp
0x18008813d  jz      short loc_180088165
0x18008813f  test    r14, r14
0x180088142  jnz     short loc_18008814F
0x180088144  mov     rcx, rdi; this
0x180088147  call    ?GetReaderEvent@CRWLock@@AEAAPEAXXZ; CRWLock::GetReaderEvent(void)
0x18008814c  mov     r14, rax
0x18008814f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180088152  mov     rcx, r14; hHandle
0x180088155  call    cs:__imp_WaitForSingleObject
0x18008815b  xor     ebx, ebx
0x18008815d  mov     r15d, 0FFFFFC01h
0x180088163  mov     ebp, eax
0x180088165  mov     rcx, r14; hEvent
0x180088168  call    cs:__imp_ResetEvent
0x18008816e  test    eax, eax
0x180088170  jz      short loc_1800881C3
0x180088172  lock add [rdi+50h], r15d
0x180088177  mov     r15d, 400h
0x18008817d  test    ebp, ebp
0x18008817f  jmp     short loc_1800881A3
0x180088181  mov     ecx, 3E8h; dwMilliseconds
0x180088186  call    cs:__imp_Sleep
0x18008818c  xor     r12d, r12d
0x18008818f  mov     esi, [rdi+50h]
0x180088192  jmp     short loc_1800881A5
0x180088194  lea     ecx, [rsi+1]
0x180088197  mov     eax, esi
0x180088199  lock cmpxchg [rdi+50h], ecx
0x18008819e  mov     esi, eax
0x1800881a0  cmp     eax, r8d
0x1800881a3  jz      short loc_1800881D0
0x1800881a5  cmp     ebx, 8001011Fh
0x1800881ab  jnz     short loc_1800881B9
0x1800881ad  xor     ebx, ebx
0x1800881af  call    ?DtcDebugBreak@@YAXXZ; DtcDebugBreak(void)
0x1800881b4  jmp     loc_18008803A
0x1800881b9  test    ebx, ebx
0x1800881bb  jns     loc_18008803A
0x1800881c1  jmp     short loc_1800881E6
0x1800881c3  lea     rcx, aReseteventFail; "ResetEvent failed"
0x1800881ca  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800881d0  test    ebx, ebx
0x1800881d2  js      short loc_1800881E6
0x1800881d4  mov     rcx, rdi; this
0x1800881d7  call    ?AddToListOfGrantedReaders@CRWLock@@AEAAJXZ; CRWLock::AddToListOfGrantedReaders(void)
0x1800881dc  mov     ebx, eax
0x1800881de  test    eax, eax
0x1800881e0  jns     loc_18008800C
0x1800881e6  lea     rcx, aFailedToAcquir; "Failed to acquire reader lock"
0x1800881ed  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
