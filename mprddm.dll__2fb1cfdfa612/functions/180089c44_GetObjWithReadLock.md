# GetObjWithReadLock

- ea: `0x180089c44`
- end: `0x180089da1`
- name: `GetObjWithReadLock`
- size: `349`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180088b1c`
- `0x180089134`
- `0x1800892bc`

## callees

- `0x180071cec`
- `0x180089c44`
- `0x18008a630`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180089ca6`
- `KERNEL32!LeaveCriticalSection` at `0x180089ce5`
- `KERNEL32!LeaveCriticalSection` at `0x180089ca6`
- `KERNEL32!LeaveCriticalSection` at `0x180089ce5`
- `KERNEL32!EnterCriticalSection` at `0x180089c93`
- `KERNEL32!EnterCriticalSection` at `0x180089cd9`
- `KERNEL32!EnterCriticalSection` at `0x180089c93`
- `KERNEL32!EnterCriticalSection` at `0x180089cd9`
- `rtutils!TracePrintfA` at `0x180089d62`
- `rtutils!TracePrintfA` at `0x180089d62`

## string_xrefs

- `0x180089d5b`: `GetObjWithReadLock: Bad handle (0x%x)`
- `0x180089d13`: `GetObjWithReadLock: Bad handle (0x%x)`

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
  EnterCriticalSection(&stru_1800C9800);
  ++dword_1800C9830;
  LeaveCriticalSection(&stru_1800C9800);
  if ( (unsigned __int16)v4 < (unsigned int)dword_1800C983C
    && (v5 = (char *)qword_1800C9848 + 72 * (unsigned __int16)v4, HIWORD(v4) == *((_WORD *)v5 + 32))
    && *((_QWORD *)v5 + 7) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)qword_1800C9848 + 72 * (unsigned __int16)v4));
    ++*((_DWORD *)v5 + 12);
    LeaveCriticalSection((LPCRITICAL_SECTION)v5);
    result = 0;
    *a2 = *((_QWORD *)qword_1800C9848 + 9 * (unsigned __int16)v4 + 7);
  }
  else
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( (_QWORD)xmmword_1800C9BE0 )
      {
        LOWORD(v7) = 0;
        FormatRRASErrorString(&v7, L"GetObjWithReadLock: Bad handle (0x%x)", a1);
        ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v7);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetObjWithReadLock: Bad handle (0x%x)", a1);
    }
    ReleaseReadLock(&stru_1800C9800);
    return 6;
  }
  return result;
}

```

## disassembly

```asm
0x180089c44  mov     [rsp+arg_10], rbx
0x180089c49  mov     [rsp+arg_18], rbp
0x180089c4e  push    rsi
0x180089c4f  push    rdi
0x180089c50  push    r14
0x180089c52  sub     rsp, 830h
0x180089c59  mov     rax, cs:__security_cookie
0x180089c60  xor     rax, rsp
0x180089c63  mov     [rsp+848h+var_28], rax
0x180089c6b  mov     edi, ecx
0x180089c6d  mov     r14, rdx
0x180089c70  mov     ebp, ecx
0x180089c72  shr     edi, 1
0x180089c74  xor     eax, eax
0x180089c76  lea     rcx, [rsp+848h+var_824]; void *
0x180089c7b  xor     edx, edx; Val
0x180089c7d  mov     [rsp+848h+var_828], eax
0x180089c81  mov     r8d, 7FCh; Size
0x180089c87  call    memset_0
0x180089c8c  lea     rcx, stru_1800C9800; lpCriticalSection
0x180089c93  call    cs:__imp_EnterCriticalSection
0x180089c99  inc     cs:dword_1800C9830
0x180089c9f  lea     rcx, stru_1800C9800; lpCriticalSection
0x180089ca6  call    cs:__imp_LeaveCriticalSection
0x180089cac  movzx   eax, di
0x180089caf  cmp     eax, cs:dword_1800C983C
0x180089cb5  jnb     short loc_180089CFE
0x180089cb7  lea     rsi, [rax+rax*8]
0x180089cbb  shr     edi, 10h
0x180089cbe  mov     rax, cs:qword_1800C9848
0x180089cc5  lea     rbx, [rax+rsi*8]
0x180089cc9  cmp     di, [rbx+40h]
0x180089ccd  jnz     short loc_180089CFE
0x180089ccf  cmp     qword ptr [rbx+38h], 0
0x180089cd4  jz      short loc_180089CFE
0x180089cd6  mov     rcx, rbx; lpCriticalSection
0x180089cd9  call    cs:__imp_EnterCriticalSection
0x180089cdf  inc     dword ptr [rbx+30h]
0x180089ce2  mov     rcx, rbx; lpCriticalSection
0x180089ce5  call    cs:__imp_LeaveCriticalSection
0x180089ceb  mov     rax, cs:qword_1800C9848
0x180089cf2  mov     rcx, [rax+rsi*8+38h]
0x180089cf7  xor     eax, eax
0x180089cf9  mov     [r14], rcx
0x180089cfc  jmp     short loc_180089D79
0x180089cfe  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180089d05  jz      short loc_180089D4D
0x180089d07  cmp     qword ptr cs:xmmword_1800C9BE0, 0
0x180089d0f  jz      short loc_180089D68
0x180089d11  xor     eax, eax
0x180089d13  lea     rdx, aGetobjwithread_0; "GetObjWithReadLock: Bad handle (0x%x)"
0x180089d1a  mov     r8d, ebp
0x180089d1d  mov     word ptr [rsp+848h+var_828], ax
0x180089d22  lea     rcx, [rsp+848h+var_828]
0x180089d27  call    FormatRRASErrorString
0x180089d2c  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180089d33  lea     r8, [rsp+848h+var_828]
0x180089d38  mov     rcx, cs:gNdpspEtwContext
0x180089d3f  mov     rax, cs:gNdpspTemplateFunc
0x180089d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d4b  jmp     short loc_180089D68
0x180089d4d  mov     ecx, cs:dwTraceId; dwTraceID
0x180089d53  cmp     ecx, 0FFFFFFFFh
0x180089d56  jz      short loc_180089D68
0x180089d58  mov     r8d, ebp
0x180089d5b  lea     rdx, aGetobjwithread; "GetObjWithReadLock: Bad handle (0x%x)"
0x180089d62  call    cs:__imp_TracePrintfA
0x180089d68  lea     rcx, stru_1800C9800
0x180089d6f  call    ReleaseReadLock
0x180089d74  mov     eax, 6
0x180089d79  mov     rcx, [rsp+848h+var_28]
0x180089d81  xor     rcx, rsp; StackCookie
0x180089d84  call    __security_check_cookie
0x180089d89  lea     r11, [rsp+848h+var_18]
0x180089d91  mov     rbx, [r11+30h]
0x180089d95  mov     rbp, [r11+38h]
0x180089d99  mov     rsp, r11
0x180089d9c  pop     r14
0x180089d9e  pop     rdi
0x180089d9f  pop     rsi
0x180089da0  retn
```
