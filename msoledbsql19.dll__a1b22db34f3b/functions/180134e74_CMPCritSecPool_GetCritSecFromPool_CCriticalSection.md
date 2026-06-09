# CMPCritSecPool::GetCritSecFromPool(CCriticalSection * *)

- ea: `0x180134e74`
- end: `0x180134f27`
- name: `?GetCritSecFromPool@CMPCritSecPool@@QEAA_NPEAPEAVCCriticalSection@@@Z`
- size: `179`
- prototype: `bool __fastcall(CMPCritSecPool *__hidden this, struct CCriticalSection **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18013532c`

## callees

- `0x180134a64`
- `0x180134e74`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180134f05`
- `KERNEL32!GetLastError` at `0x180134f05`
- `KERNEL32!InterlockedPopEntrySList` at `0x180134ec6`
- `KERNEL32!InterlockedPopEntrySList` at `0x180134ec6`
- `KERNEL32!TlsSetValue` at `0x180134efa`
- `KERNEL32!TlsSetValue` at `0x180134efa`
- `KERNEL32!TlsGetValue` at `0x180134e94`
- `KERNEL32!TlsGetValue` at `0x180134e94`

## pseudocode

```c
bool __fastcall CMPCritSecPool::GetCritSecFromPool(CMPCritSecPool *this, struct CCriticalSection **a2)
{
  __int64 v4; // rbp
  unsigned __int64 v5; // rsi
  PSLIST_ENTRY v6; // rax
  struct CCriticalSection *v7; // rdx

  v4 = 214013LL * (_QWORD)TlsGetValue(g_tlsCSTLSIndex);
  v5 = (((unsigned __int64)(v4 + 2531011) >> 16) & 0x7FFF) % *((unsigned int *)this + 2);
  v6 = InterlockedPopEntrySList((PSLIST_HEADER)(*(_QWORD *)this + 32LL * (unsigned int)v5));
  v7 = (struct CCriticalSection *)((unsigned __int64)&v6[-1] & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64));
  *a2 = v7;
  if ( v7 )
    *(_DWORD *)(((unsigned __int64)&v6[-1] & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64)) + 0x2C) = v5;
  else
    *a2 = CreateCriticalSection(v5);
  if ( !TlsSetValue(g_tlsCSTLSIndex, (LPVOID)(v4 + 2531011)) )
    GetLastError();
  return *a2 != 0;
}

```

## disassembly

```asm
0x180134e74  mov     [rsp+arg_0], rbx
0x180134e79  mov     [rsp+arg_8], rbp
0x180134e7e  mov     [rsp+arg_10], rsi
0x180134e83  push    rdi
0x180134e84  sub     rsp, 20h
0x180134e88  mov     rbx, rcx
0x180134e8b  mov     rdi, rdx
0x180134e8e  mov     ecx, cs:?g_tlsCSTLSIndex@@3VThreadLocalKey@@A; dwTlsIndex
0x180134e94  call    cs:__imp_TlsGetValue
0x180134e9a  mov     r8d, [rbx+8]
0x180134e9e  xor     edx, edx
0x180134ea0  imul    rbp, rax, 343FDh
0x180134ea7  lea     rax, [rbp+269EC3h]
0x180134eae  shr     rax, 10h
0x180134eb2  and     eax, 7FFFh
0x180134eb7  div     r8
0x180134eba  mov     ecx, edx
0x180134ebc  mov     rsi, rdx
0x180134ebf  shl     rcx, 5
0x180134ec3  add     rcx, [rbx]; ListHead
0x180134ec6  call    cs:__imp_InterlockedPopEntrySList
0x180134ecc  lea     rcx, [rax-10h]
0x180134ed0  neg     rax
0x180134ed3  sbb     rdx, rdx
0x180134ed6  and     rdx, rcx
0x180134ed9  mov     [rdi], rdx
0x180134edc  jnz     short loc_180134EEA
0x180134ede  mov     ecx, esi; unsigned int
0x180134ee0  call    ?CreateCriticalSection@@YAPEAVCCriticalSection@@K@Z; CreateCriticalSection(ulong)
0x180134ee5  mov     [rdi], rax
0x180134ee8  jmp     short loc_180134EED
0x180134eea  mov     [rdx+2Ch], esi
0x180134eed  mov     ecx, cs:?g_tlsCSTLSIndex@@3VThreadLocalKey@@A; dwTlsIndex
0x180134ef3  lea     rdx, [rbp+269EC3h]; lpTlsValue
0x180134efa  call    cs:__imp_TlsSetValue
0x180134f00  cmp     eax, 1
0x180134f03  jz      short loc_180134F0B
0x180134f05  call    cs:__imp_GetLastError
0x180134f0b  cmp     qword ptr [rdi], 0
0x180134f0f  mov     rbx, [rsp+28h+arg_0]
0x180134f14  mov     rbp, [rsp+28h+arg_8]
0x180134f19  setnz   al
0x180134f1c  mov     rsi, [rsp+28h+arg_10]
0x180134f21  add     rsp, 20h
0x180134f25  pop     rdi
0x180134f26  retn
```
