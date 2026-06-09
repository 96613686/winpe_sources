# CSpinLock::WriteLock(void)

- ea: `0x180010640`
- end: `0x18001067a`
- name: `?WriteLock@CSpinLock@@QEAAXXZ`
- size: `58`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010550`
- `0x180010680`
- `0x1800106e0`
- `0x1800168b0`
- `0x18001bac0`
- `0x18001bf90`
- `0x18001bff0`
- `0x18001c0c0`
- `0x18001c170`
- `0x18001c1e0`
- `0x18001c250`

## callees

- `0x180010640`
- `0x180010cd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001064f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001064f`

## pseudocode

```c
void __fastcall CSpinLock::WriteLock(CSpinLock *this)
{
  if ( *(_DWORD *)this
    || _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFFC | 1, 0) )
  {
    CSpinLock::_Lock(this);
  }
}

```

## disassembly

```asm
0x180010640  push    rbx; public: void CSpinLock::ReadLock(void)
0x180010642  sub     rsp, 20h
0x180010646  mov     eax, [rcx]
0x180010648  mov     rbx, rcx
0x18001064b  test    eax, eax
0x18001064d  jnz     short loc_18001066B
0x18001064f  call    cs:__imp_GetCurrentThreadId
0x180010656  nop     dword ptr [rax+rax+00h]
0x18001065b  mov     edx, eax
0x18001065d  and     edx, 0FFFFFFFDh
0x180010660  or      edx, 1
0x180010663  xor     eax, eax
0x180010665  lock cmpxchg [rbx], edx
0x180010669  jz      short loc_180010673
0x18001066b  mov     rcx, rbx; this
0x18001066e  call    ?_Lock@CSpinLock@@AEAAXXZ; CSpinLock::_Lock(void)
0x180010673  add     rsp, 20h
0x180010677  pop     rbx
0x180010678  retn
```
