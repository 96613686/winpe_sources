# CMPCritSecPool::GetCritSecFromPool(CCriticalSection * *)

- ea: `0x10046bf2c`
- end: `0x10046bfdf`
- name: `?GetCritSecFromPool@CMPCritSecPool@@QEAA_NPEAPEAVCCriticalSection@@@Z`
- size: `179`
- prototype: `bool __fastcall(CMPCritSecPool *__hidden this, struct CCriticalSection **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x10046c3c8`

## callees

- `0x10046bbf0`
- `0x10046bf2c`

## import_xrefs

- `KERNEL32!InterlockedPopEntrySList` at `0x10046bf7e`
- `KERNEL32!InterlockedPopEntrySList` at `0x10046bf7e`
- `KERNEL32!GetLastError` at `0x10046bfbd`
- `KERNEL32!GetLastError` at `0x10046bfbd`
- `KERNEL32!TlsGetValue` at `0x10046bf4c`
- `KERNEL32!TlsGetValue` at `0x10046bf4c`
- `KERNEL32!TlsSetValue` at `0x10046bfb2`
- `KERNEL32!TlsSetValue` at `0x10046bfb2`

## pseudocode

```c
bool __fastcall CMPCritSecPool::GetCritSecFromPool(CMPCritSecPool *this, struct CCriticalSection **a2)
{
  __int64 v4; // rbp
  unsigned __int64 v5; // rsi
  PSLIST_ENTRY v6; // rax
  bool v7; // zf
  struct CCriticalSection *v8; // rax

  v4 = 214013LL * (_QWORD)TlsGetValue(g_tlsCSTLSIndex);
  v5 = (((unsigned __int64)(v4 + 2531011) >> 16) & 0x7FFF) % *((unsigned int *)this + 2);
  v6 = InterlockedPopEntrySList((PSLIST_HEADER)(*(_QWORD *)this + 32LL * (unsigned int)v5));
  if ( v6 )
  {
    v7 = v6 == (PSLIST_ENTRY)16;
    v8 = (struct CCriticalSection *)&v6[-1];
    *a2 = v8;
    if ( !v7 )
    {
      *((_DWORD *)v8 + 11) = v5;
      goto LABEL_6;
    }
  }
  else
  {
    *a2 = 0;
  }
  *a2 = CreateCriticalSection(v5);
LABEL_6:
  if ( !TlsSetValue(g_tlsCSTLSIndex, (LPVOID)(v4 + 2531011)) )
    GetLastError();
  return *a2 != 0;
}

```

## disassembly

```asm
0x10046bf2c  mov     [rsp+arg_0], rbx
0x10046bf31  mov     [rsp+arg_8], rbp
0x10046bf36  mov     [rsp+arg_10], rsi
0x10046bf3b  push    rdi
0x10046bf3c  sub     rsp, 20h
0x10046bf40  mov     rbx, rcx
0x10046bf43  mov     rdi, rdx
0x10046bf46  mov     ecx, cs:?g_tlsCSTLSIndex@@3VThreadLocalKey@@A; dwTlsIndex
0x10046bf4c  call    cs:__imp_TlsGetValue
0x10046bf52  mov     r8d, [rbx+8]
0x10046bf56  xor     edx, edx
0x10046bf58  imul    rbp, rax, 343FDh
0x10046bf5f  lea     rax, [rbp+269EC3h]
0x10046bf66  shr     rax, 10h
0x10046bf6a  and     eax, 7FFFh
0x10046bf6f  div     r8
0x10046bf72  mov     ecx, edx
0x10046bf74  mov     rsi, rdx
0x10046bf77  shl     rcx, 5
0x10046bf7b  add     rcx, [rbx]; ListHead
0x10046bf7e  call    cs:__imp_InterlockedPopEntrySList
0x10046bf84  test    rax, rax
0x10046bf87  jz      short loc_10046BF97
0x10046bf89  add     rax, 0FFFFFFFFFFFFFFF0h
0x10046bf8d  mov     [rdi], rax
0x10046bf90  jz      short loc_10046BF9B
0x10046bf92  mov     [rax+2Ch], esi
0x10046bf95  jmp     short loc_10046BFA5
0x10046bf97  and     qword ptr [rdi], 0
0x10046bf9b  mov     ecx, esi; unsigned int
0x10046bf9d  call    ?CreateCriticalSection@@YAPEAVCCriticalSection@@K@Z; CreateCriticalSection(ulong)
0x10046bfa2  mov     [rdi], rax
0x10046bfa5  mov     ecx, cs:?g_tlsCSTLSIndex@@3VThreadLocalKey@@A; dwTlsIndex
0x10046bfab  lea     rdx, [rbp+269EC3h]; lpTlsValue
0x10046bfb2  call    cs:__imp_TlsSetValue
0x10046bfb8  cmp     eax, 1
0x10046bfbb  jz      short loc_10046BFC3
0x10046bfbd  call    cs:__imp_GetLastError
0x10046bfc3  cmp     qword ptr [rdi], 0
0x10046bfc7  mov     rbx, [rsp+28h+arg_0]
0x10046bfcc  mov     rbp, [rsp+28h+arg_8]
0x10046bfd1  setnz   al
0x10046bfd4  mov     rsi, [rsp+28h+arg_10]
0x10046bfd9  add     rsp, 20h
0x10046bfdd  pop     rdi
0x10046bfde  retn
```
