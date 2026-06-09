# GetObjWithReadLock

- ea: `0x180028398`
- end: `0x1800284f5`
- name: `GetObjWithReadLock`
- size: `349`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180027270`
- `0x180027888`
- `0x180027a10`

## callees

- `0x180028398`
- `0x180028d84`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800283fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028439`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800283fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028439`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800283e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002842d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800283e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002842d`
- `rtutils!TracePrintfA` at `0x1800284b6`
- `rtutils!TracePrintfA` at `0x1800284b6`

## string_xrefs

- `0x180028467`: `GetObjWithReadLock: Bad handle (0x%x)`
- `0x1800284af`: `GetObjWithReadLock: Bad handle (0x%x)`

## pseudocode

```c
__int64 __fastcall GetObjWithReadLock(unsigned int a1, _QWORD *a2)
{
  unsigned int v4; // edi
  char *v5; // rbx
  __int64 result; // rax
  int v7; // [rsp+20h] [rbp-828h] BYREF
  _BYTE v8[2044]; // [rsp+24h] [rbp-824h] BYREF

  v4 = a1 >> 1;
  v7 = 0;
  memset_0(v8, 0, sizeof(v8));
  EnterCriticalSection(&CriticalSection);
  ++dword_18003EBB0;
  LeaveCriticalSection(&CriticalSection);
  if ( (unsigned __int16)v4 < (unsigned int)dword_18003EBBC
    && (v5 = (char *)lpMem + 72 * (unsigned __int16)v4, HIWORD(v4) == *((_WORD *)v5 + 32))
    && *((_QWORD *)v5 + 7) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)lpMem + 72 * (unsigned __int16)v4));
    ++*((_DWORD *)v5 + 12);
    LeaveCriticalSection((LPCRITICAL_SECTION)v5);
    result = 0;
    *a2 = *((_QWORD *)lpMem + 9 * (unsigned __int16)v4 + 7);
  }
  else
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v7) = 0;
        FormatRRASErrorString(&v7, L"GetObjWithReadLock: Bad handle (0x%x)", a1);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v7);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetObjWithReadLock: Bad handle (0x%x)", a1);
    }
    ReleaseReadLock(&CriticalSection);
    return 6;
  }
  return result;
}

```

## disassembly

```asm
0x180028398  mov     [rsp+arg_10], rbx
0x18002839d  mov     [rsp+arg_18], rbp
0x1800283a2  push    rsi
0x1800283a3  push    rdi
0x1800283a4  push    r14
0x1800283a6  sub     rsp, 830h
0x1800283ad  mov     rax, cs:__security_cookie
0x1800283b4  xor     rax, rsp
0x1800283b7  mov     [rsp+848h+var_28], rax
0x1800283bf  mov     edi, ecx
0x1800283c1  mov     r14, rdx
0x1800283c4  mov     ebp, ecx
0x1800283c6  shr     edi, 1
0x1800283c8  xor     eax, eax
0x1800283ca  lea     rcx, [rsp+848h+var_824]; void *
0x1800283cf  xor     edx, edx; Val
0x1800283d1  mov     [rsp+848h+var_828], eax
0x1800283d5  mov     r8d, 7FCh; Size
0x1800283db  call    memset_0
0x1800283e0  lea     rcx, CriticalSection; lpCriticalSection
0x1800283e7  call    cs:__imp_EnterCriticalSection
0x1800283ed  inc     cs:dword_18003EBB0
0x1800283f3  lea     rcx, CriticalSection; lpCriticalSection
0x1800283fa  call    cs:__imp_LeaveCriticalSection
0x180028400  movzx   eax, di
0x180028403  cmp     eax, cs:dword_18003EBBC
0x180028409  jnb     short loc_180028452
0x18002840b  lea     rsi, [rax+rax*8]
0x18002840f  shr     edi, 10h
0x180028412  mov     rax, cs:lpMem
0x180028419  lea     rbx, [rax+rsi*8]
0x18002841d  cmp     di, [rbx+40h]
0x180028421  jnz     short loc_180028452
0x180028423  cmp     qword ptr [rbx+38h], 0
0x180028428  jz      short loc_180028452
0x18002842a  mov     rcx, rbx; lpCriticalSection
0x18002842d  call    cs:__imp_EnterCriticalSection
0x180028433  inc     dword ptr [rbx+30h]
0x180028436  mov     rcx, rbx; lpCriticalSection
0x180028439  call    cs:__imp_LeaveCriticalSection
0x18002843f  mov     rax, cs:lpMem
0x180028446  mov     rcx, [rax+rsi*8+38h]
0x18002844b  xor     eax, eax
0x18002844d  mov     [r14], rcx
0x180028450  jmp     short loc_1800284CD
0x180028452  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180028459  jz      short loc_1800284A1
0x18002845b  cmp     cs:qword_18003EC40, 0
0x180028463  jz      short loc_1800284BC
0x180028465  xor     eax, eax
0x180028467  lea     rdx, aGetobjwithread_0; "GetObjWithReadLock: Bad handle (0x%x)"
0x18002846e  mov     r8d, ebp
0x180028471  mov     word ptr [rsp+848h+var_828], ax
0x180028476  lea     rcx, [rsp+848h+var_828]
0x18002847b  call    FormatRRASErrorString
0x180028480  mov     rdx, cs:qword_18003EC40
0x180028487  lea     r8, [rsp+848h+var_828]
0x18002848c  mov     rcx, cs:gNdpspEtwContext
0x180028493  mov     rax, cs:gNdpspTemplateFunc
0x18002849a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002849f  jmp     short loc_1800284BC
0x1800284a1  mov     ecx, cs:dwTraceId; dwTraceID
0x1800284a7  cmp     ecx, 0FFFFFFFFh
0x1800284aa  jz      short loc_1800284BC
0x1800284ac  mov     r8d, ebp
0x1800284af  lea     rdx, aGetobjwithread; "GetObjWithReadLock: Bad handle (0x%x)"
0x1800284b6  call    cs:__imp_TracePrintfA
0x1800284bc  lea     rcx, CriticalSection
0x1800284c3  call    ReleaseReadLock
0x1800284c8  mov     eax, 6
0x1800284cd  mov     rcx, [rsp+848h+var_28]
0x1800284d5  xor     rcx, rsp; StackCookie
0x1800284d8  call    __security_check_cookie
0x1800284dd  lea     r11, [rsp+848h+var_18]
0x1800284e5  mov     rbx, [r11+30h]
0x1800284e9  mov     rbp, [r11+38h]
0x1800284ed  mov     rsp, r11
0x1800284f0  pop     r14
0x1800284f2  pop     rdi
0x1800284f3  pop     rsi
0x1800284f4  retn
```
