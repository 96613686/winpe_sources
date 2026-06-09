# CStringTraceEvent::CStringTraceEvent(TraceSource,uchar,ushort const *,ushort const *,ulong,long,ushort const *,char *)

- ea: `0x18006f524`
- end: `0x18006f5e8`
- name: `??0CStringTraceEvent@@QEAA@W4TraceSource@@EPEBG1KJ1PEAD@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18006f8ac`

## callees

- `0x18006f524`
- `0x18006fc78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006f55b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006f55b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006f551`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006f551`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18006f54b`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18006f54b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStringTraceEvent::CStringTraceEvent(
        __int64 a1,
        int a2,
        char a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        unsigned __int16 *a8,
        char *a9)
{
  unsigned int v13; // eax

  *(_QWORD *)a1 = &CTraceEvent::`vftable';
  GetLocalTime((LPSYSTEMTIME)(a1 + 8));
  *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
  *(_DWORD *)(a1 + 28) = GetCurrentProcessId();
  *(_BYTE *)(a1 + 32) = a3;
  *(_QWORD *)a1 = &CStringTraceEvent::`vftable';
  *(_DWORD *)(a1 + 40) = a2;
  *(_QWORD *)(a1 + 48) = a4;
  *(_QWORD *)(a1 + 56) = a5;
  *(_DWORD *)(a1 + 64) = a6;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  v13 = a7;
  if ( a7 > 0 )
    v13 = (unsigned __int16)a7 | 0x80070000;
  *(_DWORD *)(a1 + 68) = v13;
  if ( StringCchVPrintfAllocate((unsigned __int16 **)(a1 + 72), a8, a9) < 0 )
    *(_QWORD *)(a1 + 72) = L"[[Unable to format message]]";
  return a1;
}

```

## disassembly

```asm
0x18006f524  mov     [rsp+arg_0], rcx
0x18006f529  push    rbx
0x18006f52a  push    rsi
0x18006f52b  push    rdi
0x18006f52c  push    r14
0x18006f52e  sub     rsp, 28h
0x18006f532  mov     rsi, r9
0x18006f535  mov     bl, r8b
0x18006f538  mov     edi, edx
0x18006f53a  mov     r14, rcx
0x18006f53d  lea     rax, ??_7CTraceEvent@@6B@; const CTraceEvent::`vftable'
0x18006f544  mov     [rcx], rax
0x18006f547  add     rcx, 8; lpSystemTime
0x18006f54b  call    cs:__imp_GetLocalTime
0x18006f551  call    cs:__imp_GetCurrentThreadId
0x18006f557  mov     [r14+18h], eax
0x18006f55b  call    cs:__imp_GetCurrentProcessId
0x18006f561  mov     [r14+1Ch], eax
0x18006f565  mov     [r14+20h], bl
0x18006f569  lea     rax, ??_7CStringTraceEvent@@6B@; const CStringTraceEvent::`vftable'
0x18006f570  mov     [r14], rax
0x18006f573  mov     [r14+28h], edi
0x18006f577  mov     [r14+30h], rsi
0x18006f57b  mov     rax, [rsp+48h+arg_20]
0x18006f580  mov     [r14+38h], rax
0x18006f584  mov     eax, [rsp+48h+arg_28]
0x18006f588  mov     [r14+40h], eax
0x18006f58c  xor     edi, edi
0x18006f58e  mov     [r14+48h], rdi
0x18006f592  mov     [r14+50h], rdi
0x18006f596  mov     [r14+58h], rdi
0x18006f59a  mov     eax, [rsp+48h+arg_30]
0x18006f5a1  test    eax, eax
0x18006f5a3  js      short loc_18006F5AF
0x18006f5a5  jle     short loc_18006F5AF
0x18006f5a7  movzx   eax, ax
0x18006f5aa  or      eax, 80070000h
0x18006f5af  mov     [r14+44h], eax
0x18006f5b3  mov     r8, [rsp+48h+arg_40]; char *
0x18006f5bb  mov     rdx, [rsp+48h+arg_38]; unsigned __int16 *
0x18006f5c3  lea     rcx, [r14+48h]; unsigned __int16 **
0x18006f5c7  call    ?StringCchVPrintfAllocate@@YAJPEAPEAGPEBGPEAD@Z; StringCchVPrintfAllocate(ushort * *,ushort const *,char *)
0x18006f5cc  test    eax, eax
0x18006f5ce  jns     short loc_18006F5DB
0x18006f5d0  lea     rax, aUnableToFormat; "[[Unable to format message]]"
0x18006f5d7  mov     [r14+48h], rax
0x18006f5db  mov     rax, r14
0x18006f5de  add     rsp, 28h
0x18006f5e2  pop     r14
0x18006f5e4  pop     rdi
0x18006f5e5  pop     rsi
0x18006f5e6  pop     rbx
0x18006f5e7  retn
```
