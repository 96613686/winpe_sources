# CRWLock::AcquireWriterLock(void)

- ea: `0x18000cddc`
- end: `0x18000cf89`
- name: `?AcquireWriterLock@CRWLock@@QEAAJXZ`
- size: `429`
- prototype: `__int64 __fastcall(CRWLock *__hidden this)`
- caller_count: `15`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000290c`
- `0x1800041a0`
- `0x180004dc0`
- `0x1800055a0`
- `0x18000c954`
- `0x18000cb8c`
- `0x18000fa88`
- `0x180056bac`
- `0x180056e20`
- `0x180057f68`
- `0x180058304`
- `0x180065208`
- `0x180065da0`
- `0x18006c844`
- `0x18006cb54`

## callees

- `0x18000cddc`
- `0x18000d5f4`
- `0x18000d7ec`
- `0x18007cb3c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ceb1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ceb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ced4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ced4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cdf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cdf2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000ce5e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000ce5e`

## string_xrefs

- `0x18000cf7c`: `Failed to acquire writer lock`

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
0x18000cddc  push    rbx
0x18000cdde  push    rbp
0x18000cddf  push    rsi
0x18000cde0  push    rdi
0x18000cde1  push    r12
0x18000cde3  push    r13
0x18000cde5  push    r14
0x18000cde7  push    r15
0x18000cde9  sub     rsp, 28h
0x18000cded  mov     rbx, rcx
0x18000cdf0  xor     edi, edi
0x18000cdf2  call    cs:__imp_GetCurrentThreadId
0x18000cdf8  lea     r13d, [rdi+1]
0x18000cdfc  mov     r14d, eax
0x18000cdff  test    [rbx+5Ch], r13b
0x18000ce03  jnz     short loc_18000CE13
0x18000ce05  mov     rax, [rbx]
0x18000ce08  mov     rcx, rbx
0x18000ce0b  mov     rax, [rax]
0x18000ce0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce13  cmp     [rbx+54h], r14d
0x18000ce17  jnz     short loc_18000CE23
0x18000ce19  add     [rbx+5Eh], r13w
0x18000ce1e  jmp     loc_18000CF69
0x18000ce23  mov     esi, [rbx+50h]
0x18000ce26  or      r12d, 0FFFFFFFFh
0x18000ce2a  xor     r15d, r15d
0x18000ce2d  mov     edx, esi
0x18000ce2f  test    esi, esi
0x18000ce31  jnz     short loc_18000CE4B
0x18000ce33  mov     ecx, 1000h
0x18000ce38  xor     eax, eax
0x18000ce3a  lock cmpxchg [rbx+50h], ecx
0x18000ce3f  mov     esi, eax
0x18000ce41  cmp     eax, edx
0x18000ce43  jz      loc_18000CF58
0x18000ce49  jmp     short loc_18000CE6A
0x18000ce4b  mov     eax, esi
0x18000ce4d  and     eax, 0FF800000h
0x18000ce52  cmp     eax, 0FF800000h
0x18000ce57  jnz     short loc_18000CE7F
0x18000ce59  mov     ecx, 3E8h; dwMilliseconds
0x18000ce5e  call    cs:__imp_Sleep
0x18000ce64  xor     r15d, r15d
0x18000ce67  mov     esi, [rbx+50h]
0x18000ce6a  cmp     edi, 8001011Fh
0x18000ce70  jnz     loc_18000CF50
0x18000ce76  xor     edi, edi
0x18000ce78  call    ?DtcDebugBreak@@YAXXZ; DtcDebugBreak(void)
0x18000ce7d  jmp     short loc_18000CE2D
0x18000ce7f  add     r15d, r13d
0x18000ce82  cmp     r15d, cs:?gdwDefaultSpinCount@@3KA; ulong gdwDefaultSpinCount
0x18000ce89  jbe     short loc_18000CE67
0x18000ce8b  lea     ecx, [rsi+800000h]
0x18000ce91  mov     eax, esi
0x18000ce93  lock cmpxchg [rbx+50h], ecx
0x18000ce98  mov     esi, eax
0x18000ce9a  cmp     eax, edx
0x18000ce9c  jnz     short loc_18000CE6A
0x18000ce9e  mov     rcx, rbx; this
0x18000cea1  call    ?GetWriterEvent@CRWLock@@AEAAPEAXXZ; CRWLock::GetWriterEvent(void)
0x18000cea6  test    rax, rax
0x18000cea9  jz      short loc_18000CEEB
0x18000ceab  mov     edx, r12d; dwMilliseconds
0x18000ceae  mov     rcx, rax; hHandle
0x18000ceb1  call    cs:__imp_WaitForSingleObject
0x18000ceb7  mov     ebp, eax
0x18000ceb9  test    eax, eax
0x18000cebb  jnz     short loc_18000CEC6
0x18000cebd  mov     eax, 0FF800800h
0x18000cec2  xor     edi, edi
0x18000cec4  jmp     short loc_18000CEF8
0x18000cec6  cmp     eax, 102h
0x18000cecb  jnz     short loc_18000CED4
0x18000cecd  mov     edi, 8001011Fh
0x18000ced2  jmp     short loc_18000CEF3
0x18000ced4  call    cs:__imp_GetLastError
0x18000ceda  mov     edi, eax
0x18000cedc  test    eax, eax
0x18000cede  jle     short loc_18000CEF3
0x18000cee0  movzx   edi, ax
0x18000cee3  or      edi, 80070000h
0x18000cee9  jmp     short loc_18000CEF3
0x18000ceeb  or      ebp, 0FFFFFFFFh
0x18000ceee  mov     edi, 80010101h
0x18000cef3  mov     eax, 0FF800000h
0x18000cef8  lock xadd [rbx+50h], eax
0x18000cefd  test    ebp, ebp
0x18000ceff  jz      short loc_18000CF58
0x18000cf01  bt      eax, 0Bh
0x18000cf05  jnb     loc_18000CE6A
0x18000cf0b  and     eax, 0FF800000h
0x18000cf10  cmp     eax, 800000h
0x18000cf15  jnz     loc_18000CE6A
0x18000cf1b  mov     esi, [rbx+50h]
0x18000cf1e  mov     eax, esi
0x18000cf20  and     eax, 0FF800800h
0x18000cf25  cmp     eax, 800h
0x18000cf2a  jnz     loc_18000CE6A
0x18000cf30  mov     edx, esi
0x18000cf32  lea     ecx, [rsi+800000h]
0x18000cf38  mov     eax, esi
0x18000cf3a  lock cmpxchg [rbx+50h], ecx
0x18000cf3f  mov     esi, eax
0x18000cf41  cmp     eax, edx
0x18000cf43  jnz     short loc_18000CF1E
0x18000cf45  mov     r12d, 64h ; 'd'
0x18000cf4b  jmp     loc_18000CE9E
0x18000cf50  test    edi, edi
0x18000cf52  jns     loc_18000CE2D
0x18000cf58  test    edi, edi
0x18000cf5a  js      short loc_18000CF7C
0x18000cf5c  add     [rbx+58h], r13d
0x18000cf60  mov     [rbx+54h], r14d
0x18000cf64  mov     [rbx+5Eh], r13w
0x18000cf69  mov     eax, edi
0x18000cf6b  add     rsp, 28h
0x18000cf6f  pop     r15
0x18000cf71  pop     r14
0x18000cf73  pop     r13
0x18000cf75  pop     r12
0x18000cf77  pop     rdi
0x18000cf78  pop     rsi
0x18000cf79  pop     rbp
0x18000cf7a  pop     rbx
0x18000cf7b  retn
0x18000cf7c  lea     rcx, aFailedToAcquir_0; "Failed to acquire writer lock"
0x18000cf83  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
