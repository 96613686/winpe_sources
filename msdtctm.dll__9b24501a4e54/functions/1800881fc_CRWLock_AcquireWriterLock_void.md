# CRWLock::AcquireWriterLock(void)

- ea: `0x1800881fc`
- end: `0x1800883a9`
- name: `?AcquireWriterLock@CRWLock@@QEAAJXZ`
- size: `429`
- prototype: `__int64 __fastcall(CRWLock *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002538c`
- `0x180087fd0`

## callees

- `0x180084698`
- `0x1800846c0`
- `0x1800881fc`
- `0x180088710`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088212`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088212`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800882d1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800882d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800882f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800882f4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008827e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18008827e`

## string_xrefs

- `0x18008839c`: `Failed to acquire writer lock`

## pseudocode

```c
__int64 __fastcall CRWLock::AcquireWriterLock(CRWLock *this)
{
  signed int v2; // edi
  DWORD CurrentThreadId; // r14d
  signed __int32 v4; // esi
  DWORD v5; // r12d
  int v6; // r15d
  signed __int32 v7; // edx
  void *WriterEvent; // rax
  DWORD v9; // eax
  int v10; // ebp
  unsigned int v11; // eax
  signed int LastError; // eax
  signed __int32 v13; // eax
  signed __int32 v14; // edx

  v2 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( (*((_BYTE *)this + 92) & 1) == 0 )
    (**(void (__fastcall ***)(CRWLock *))this)(this);
  if ( *((_DWORD *)this + 21) == CurrentThreadId )
  {
    ++*((_WORD *)this + 47);
    return (unsigned int)v2;
  }
  v4 = *((_DWORD *)this + 20);
  v5 = -1;
  v6 = 0;
  do
  {
    while ( 1 )
    {
      v7 = v4;
      if ( !v4 )
      {
        v4 = _InterlockedCompareExchange((volatile signed __int32 *)this + 20, 4096, 0);
        if ( !v4 )
          goto LABEL_33;
        goto LABEL_12;
      }
      if ( (v4 & 0xFF800000) == 0xFF800000 )
      {
        Sleep(0x3E8u);
        v6 = 0;
LABEL_11:
        v4 = *((_DWORD *)this + 20);
        goto LABEL_12;
      }
      if ( ++v6 <= gdwDefaultSpinCount )
        goto LABEL_11;
      v4 = _InterlockedCompareExchange((volatile signed __int32 *)this + 20, v4 + 0x800000, v4);
      if ( v4 == v7 )
      {
LABEL_16:
        WriterEvent = CRWLock::GetWriterEvent(this);
        if ( WriterEvent )
        {
          v9 = WaitForSingleObject(WriterEvent, v5);
          v10 = v9;
          if ( !v9 )
          {
            v11 = -8386560;
            v2 = 0;
LABEL_25:
            v13 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 20, v11);
            if ( !v10 )
              goto LABEL_33;
            if ( (v13 & 0x800) != 0 && (v13 & 0xFF800000) == 0x800000 )
            {
              v4 = *((_DWORD *)this + 20);
              while ( (v4 & 0xFF800800) == 0x800 )
              {
                v14 = v4;
                v4 = _InterlockedCompareExchange((volatile signed __int32 *)this + 20, v4 + 0x800000, v4);
                if ( v4 == v14 )
                {
                  v5 = 100;
                  goto LABEL_16;
                }
              }
            }
            goto LABEL_12;
          }
          if ( v9 == 258 )
          {
            v2 = -2147417825;
          }
          else
          {
            LastError = GetLastError();
            v2 = LastError;
            if ( LastError > 0 )
              v2 = (unsigned __int16)LastError | 0x80070000;
          }
        }
        else
        {
          v10 = -1;
          v2 = -2147417855;
        }
        v11 = -8388608;
        goto LABEL_25;
      }
LABEL_12:
      if ( v2 != -2147417825 )
        break;
      v2 = 0;
      DtcDebugBreak();
    }
  }
  while ( v2 >= 0 );
LABEL_33:
  if ( v2 < 0 )
    DtcInternalErrorW(L"Failed to acquire writer lock");
  ++*((_DWORD *)this + 22);
  *((_DWORD *)this + 21) = CurrentThreadId;
  *((_WORD *)this + 47) = 1;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800881fc  push    rbx
0x1800881fe  push    rbp
0x1800881ff  push    rsi
0x180088200  push    rdi
0x180088201  push    r12
0x180088203  push    r13
0x180088205  push    r14
0x180088207  push    r15
0x180088209  sub     rsp, 28h
0x18008820d  mov     rbx, rcx
0x180088210  xor     edi, edi
0x180088212  call    cs:__imp_GetCurrentThreadId
0x180088218  lea     r13d, [rdi+1]
0x18008821c  mov     r14d, eax
0x18008821f  test    [rbx+5Ch], r13b
0x180088223  jnz     short loc_180088233
0x180088225  mov     rax, [rbx]
0x180088228  mov     rcx, rbx
0x18008822b  mov     rax, [rax]
0x18008822e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088233  cmp     [rbx+54h], r14d
0x180088237  jnz     short loc_180088243
0x180088239  add     [rbx+5Eh], r13w
0x18008823e  jmp     loc_180088389
0x180088243  mov     esi, [rbx+50h]
0x180088246  or      r12d, 0FFFFFFFFh
0x18008824a  xor     r15d, r15d
0x18008824d  mov     edx, esi
0x18008824f  test    esi, esi
0x180088251  jnz     short loc_18008826B
0x180088253  mov     ecx, 1000h
0x180088258  xor     eax, eax
0x18008825a  lock cmpxchg [rbx+50h], ecx
0x18008825f  mov     esi, eax
0x180088261  cmp     eax, edx
0x180088263  jz      loc_180088378
0x180088269  jmp     short loc_18008828A
0x18008826b  mov     eax, esi
0x18008826d  and     eax, 0FF800000h
0x180088272  cmp     eax, 0FF800000h
0x180088277  jnz     short loc_18008829F
0x180088279  mov     ecx, 3E8h; dwMilliseconds
0x18008827e  call    cs:__imp_Sleep
0x180088284  xor     r15d, r15d
0x180088287  mov     esi, [rbx+50h]
0x18008828a  cmp     edi, 8001011Fh
0x180088290  jnz     loc_180088370
0x180088296  xor     edi, edi
0x180088298  call    ?DtcDebugBreak@@YAXXZ; DtcDebugBreak(void)
0x18008829d  jmp     short loc_18008824D
0x18008829f  add     r15d, r13d
0x1800882a2  cmp     r15d, cs:?gdwDefaultSpinCount@@3KA; ulong gdwDefaultSpinCount
0x1800882a9  jbe     short loc_180088287
0x1800882ab  lea     ecx, [rsi+800000h]
0x1800882b1  mov     eax, esi
0x1800882b3  lock cmpxchg [rbx+50h], ecx
0x1800882b8  mov     esi, eax
0x1800882ba  cmp     eax, edx
0x1800882bc  jnz     short loc_18008828A
0x1800882be  mov     rcx, rbx; this
0x1800882c1  call    ?GetWriterEvent@CRWLock@@AEAAPEAXXZ; CRWLock::GetWriterEvent(void)
0x1800882c6  test    rax, rax
0x1800882c9  jz      short loc_18008830B
0x1800882cb  mov     edx, r12d; dwMilliseconds
0x1800882ce  mov     rcx, rax; hHandle
0x1800882d1  call    cs:__imp_WaitForSingleObject
0x1800882d7  mov     ebp, eax
0x1800882d9  test    eax, eax
0x1800882db  jnz     short loc_1800882E6
0x1800882dd  mov     eax, 0FF800800h
0x1800882e2  xor     edi, edi
0x1800882e4  jmp     short loc_180088318
0x1800882e6  cmp     eax, 102h
0x1800882eb  jnz     short loc_1800882F4
0x1800882ed  mov     edi, 8001011Fh
0x1800882f2  jmp     short loc_180088313
0x1800882f4  call    cs:__imp_GetLastError
0x1800882fa  mov     edi, eax
0x1800882fc  test    eax, eax
0x1800882fe  jle     short loc_180088313
0x180088300  movzx   edi, ax
0x180088303  or      edi, 80070000h
0x180088309  jmp     short loc_180088313
0x18008830b  or      ebp, 0FFFFFFFFh
0x18008830e  mov     edi, 80010101h
0x180088313  mov     eax, 0FF800000h
0x180088318  lock xadd [rbx+50h], eax
0x18008831d  test    ebp, ebp
0x18008831f  jz      short loc_180088378
0x180088321  bt      eax, 0Bh
0x180088325  jnb     loc_18008828A
0x18008832b  and     eax, 0FF800000h
0x180088330  cmp     eax, 800000h
0x180088335  jnz     loc_18008828A
0x18008833b  mov     esi, [rbx+50h]
0x18008833e  mov     eax, esi
0x180088340  and     eax, 0FF800800h
0x180088345  cmp     eax, 800h
0x18008834a  jnz     loc_18008828A
0x180088350  mov     edx, esi
0x180088352  lea     ecx, [rsi+800000h]
0x180088358  mov     eax, esi
0x18008835a  lock cmpxchg [rbx+50h], ecx
0x18008835f  mov     esi, eax
0x180088361  cmp     eax, edx
0x180088363  jnz     short loc_18008833E
0x180088365  mov     r12d, 64h ; 'd'
0x18008836b  jmp     loc_1800882BE
0x180088370  test    edi, edi
0x180088372  jns     loc_18008824D
0x180088378  test    edi, edi
0x18008837a  js      short loc_18008839C
0x18008837c  add     [rbx+58h], r13d
0x180088380  mov     [rbx+54h], r14d
0x180088384  mov     [rbx+5Eh], r13w
0x180088389  mov     eax, edi
0x18008838b  add     rsp, 28h
0x18008838f  pop     r15
0x180088391  pop     r14
0x180088393  pop     r13
0x180088395  pop     r12
0x180088397  pop     rdi
0x180088398  pop     rsi
0x180088399  pop     rbp
0x18008839a  pop     rbx
0x18008839b  retn
0x18008839c  lea     rcx, aFailedToAcquir_0; "Failed to acquire writer lock"
0x1800883a3  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
