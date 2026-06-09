# MQFreeSecurityContext

- ea: `0x180017c30`
- end: `0x180017cab`
- name: `MQFreeSecurityContext`
- size: `123`
- prototype: `void __stdcall(HANDLE hSecurityContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180013640`
- `0x1800136dc`
- `0x180013bbc`
- `0x180014458`
- `0x180017c30`
- `0x180026010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180017c72`
- `KERNEL32!LeaveCriticalSection` at `0x180017c72`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __stdcall MQFreeSecurityContext(HANDLE hSecurityContext)
{
  CContextMap *v2; // rcx
  __int64 v3; // rdi
  CContextMap *v4; // rcx
  unsigned int v5; // edx

  if ( (int)RtpOneTimeThreadInit() >= 0 && hSecurityContext )
  {
    try
    {
      CCriticalSection::Lock((CCriticalSection *)&CriticalSection);
      v3 = *(_QWORD *)CContextMap::FindContext(v2, (unsigned int)hSecurityContext);
      LeaveCriticalSection(&CriticalSection);
      if ( v3 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 24LL))(v3, 1);
      v5 = (unsigned int)hSecurityContext;
    }
    catch ( ... )
    {
      return;
    }
    CContextMap::DeleteContext(v4, v5);
  }
}

```

## disassembly

```asm
0x180017c30  mov     [rsp+arg_0], rbx
0x180017c35  mov     [rsp+arg_10], rsi
0x180017c3a  push    rdi
0x180017c3b  sub     rsp, 20h
0x180017c3f  mov     rbx, rcx
0x180017c42  call    ?RtpOneTimeThreadInit@@YAJXZ; RtpOneTimeThreadInit(void)
0x180017c47  test    eax, eax
0x180017c49  js      short loc_180017C9B
0x180017c4b  test    rbx, rbx
0x180017c4e  jz      short loc_180017C9B
0x180017c50  lea     rsi, CriticalSection
0x180017c57  mov     [rsp+28h+arg_8], rsi
0x180017c5c  mov     rcx, rsi; this
0x180017c5f  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180017c64  nop
0x180017c65  mov     edx, ebx; unsigned int
0x180017c67  call    ?FindContext@CContextMap@@IEAAPEAUContextEntry@1@K@Z; CContextMap::FindContext(ulong)
0x180017c6c  mov     rdi, [rax]
0x180017c6f  mov     rcx, rsi; lpCriticalSection
0x180017c72  call    cs:__imp_LeaveCriticalSection
0x180017c78  nop
0x180017c79  test    rdi, rdi
0x180017c7c  jz      short loc_180017C92
0x180017c7e  mov     rax, [rdi]
0x180017c81  mov     edx, 1
0x180017c86  mov     rcx, rdi
0x180017c89  mov     rax, [rax+18h]
0x180017c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c92  mov     edx, ebx; unsigned int
0x180017c94  call    ?DeleteContext@CContextMap@@QEAAXK@Z; CContextMap::DeleteContext(ulong)
0x180017c99  jmp     short $+2
0x180017c9b  mov     rbx, [rsp+28h+arg_0]
0x180017ca0  mov     rsi, [rsp+28h+arg_10]
0x180017ca5  add     rsp, 20h
0x180017ca9  pop     rdi
0x180017caa  retn
```
