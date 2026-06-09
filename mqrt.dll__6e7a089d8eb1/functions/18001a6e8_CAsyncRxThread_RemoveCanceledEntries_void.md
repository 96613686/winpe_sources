# CAsyncRxThread::RemoveCanceledEntries(void)

- ea: `0x18001a6e8`
- end: `0x18001a744`
- name: `?RemoveCanceledEntries@CAsyncRxThread@@AEAAXXZ`
- size: `92`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a068`

## callees

- `0x180013bbc`
- `0x18001a6e8`
- `0x18001a74c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001a730`
- `KERNEL32!LeaveCriticalSection` at `0x18001a730`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CAsyncRxThread::RemoveCanceledEntries(CCriticalSection *lpCriticalSection)
{
  unsigned int v2; // edi

  try
  {
    CCriticalSection::Lock(lpCriticalSection);
    v2 = 1;
    while ( v2 < *((_DWORD *)lpCriticalSection + 18) )
    {
      if ( **((_BYTE **)lpCriticalSection + v2 + 10) )
        CAsyncRxThread::RemoveEntry(lpCriticalSection, v2);
      else
        ++v2;
    }
    *((_BYTE *)lpCriticalSection + 1104) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  }
  catch ( std::bad_alloc )
  {
  }
}

```

## disassembly

```asm
0x18001a6e8  mov     [rsp+arg_8], rbx
0x18001a6ed  push    rdi
0x18001a6ee  sub     rsp, 20h
0x18001a6f2  mov     rbx, rcx
0x18001a6f5  mov     [rsp+28h+arg_0], rcx
0x18001a6fa  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001a6ff  nop
0x18001a700  mov     edi, 1
0x18001a705  cmp     edi, [rbx+48h]
0x18001a708  jnb     short loc_18001A726
0x18001a70a  mov     eax, edi
0x18001a70c  mov     rcx, [rbx+rax*8+50h]
0x18001a711  cmp     byte ptr [rcx], 0
0x18001a714  jz      short loc_18001A722
0x18001a716  mov     edx, edi; unsigned int
0x18001a718  mov     rcx, rbx; lpCriticalSection
0x18001a71b  call    ?RemoveEntry@CAsyncRxThread@@AEAAXK@Z; CAsyncRxThread::RemoveEntry(ulong)
0x18001a720  jmp     short loc_18001A705
0x18001a722  inc     edi
0x18001a724  jmp     short loc_18001A705
0x18001a726  mov     byte ptr [rbx+450h], 0
0x18001a72d  mov     rcx, rbx; lpCriticalSection
0x18001a730  call    cs:__imp_LeaveCriticalSection
0x18001a736  nop
0x18001a737  jmp     short $+2
0x18001a739  mov     rbx, [rsp+28h+arg_8]
0x18001a73e  add     rsp, 20h
0x18001a742  pop     rdi
0x18001a743  retn
```
