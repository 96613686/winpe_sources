# CAdminAclCache::Flush(void)

- ea: `0x18000b2d4`
- end: `0x18000b3b6`
- name: `?Flush@CAdminAclCache@@QEAAJXZ`
- size: `226`
- prototype: `__int64 __fastcall(CAdminAclCache *__hidden this)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180003fd0`
- `0x180008ae0`
- `0x180009200`
- `0x18000a0b0`
- `0x18000a6c0`
- `0x18000ff80`

## callees

- `0x18000b2d4`
- `0x18000bddc`
- `0x18000fb06`
- `0x18000fb1e`
- `0x18000fb50`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b332`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b36e`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b332`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b36e`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b31a`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b31a`

## pseudocode

```c
__int64 __fastcall CAdminAclCache::Flush(CAdminAclCache *this)
{
  unsigned int v2; // ebp
  unsigned int v3; // r14d
  __int64 i; // rbx
  CAdminAcl *v6[256]; // [rsp+20h] [rbp-828h] BYREF

  memset_0(v6, 0, sizeof(v6));
  CReaderWriterLock3::WriteLock((CAdminAclCache *)((char *)this + 2056));
  if ( *((_DWORD *)this + 1) <= 0x100u )
  {
    v3 = *((_DWORD *)this + 1);
    v2 = 0;
    memcpy_0(v6, (char *)this + 8, 8LL * v3);
    _InterlockedExchange((volatile __int32 *)this + 1, 0);
    memset_0((char *)this + 8, 0, 0x800u);
    CReaderWriterLock3::WriteUnlock((CAdminAclCache *)((char *)this + 2056));
    for ( i = 0; (unsigned int)i < v3; i = (unsigned int)(i + 1) )
      CAdminAcl::Release(v6[i]);
  }
  else
  {
    v2 = -2147024872;
    CReaderWriterLock3::WriteUnlock((CAdminAclCache *)((char *)this + 2056));
  }
  return v2;
}

```

## disassembly

```asm
0x18000b2d4  mov     [rsp+arg_8], rbx
0x18000b2d9  mov     [rsp+arg_10], rbp
0x18000b2de  push    rsi
0x18000b2df  push    rdi
0x18000b2e0  push    r14
0x18000b2e2  sub     rsp, 830h
0x18000b2e9  mov     rax, cs:__security_cookie
0x18000b2f0  xor     rax, rsp
0x18000b2f3  mov     [rsp+848h+var_28], rax
0x18000b2fb  mov     rdi, rcx
0x18000b2fe  xor     edx, edx; Val
0x18000b300  lea     rcx, [rsp+848h+var_828]; void *
0x18000b305  mov     r8d, 800h; Size
0x18000b30b  call    memset_0
0x18000b310  lea     rsi, [rdi+808h]
0x18000b317  mov     rcx, rsi
0x18000b31a  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000b320  mov     eax, [rdi+4]
0x18000b323  cmp     eax, 100h
0x18000b328  jbe     short loc_18000B33A
0x18000b32a  mov     rcx, rsi
0x18000b32d  mov     ebp, 80070018h
0x18000b332  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b338  jmp     short loc_18000B38C
0x18000b33a  mov     r14d, [rdi+4]
0x18000b33e  lea     rdx, [rdi+8]; Src
0x18000b342  mov     r8d, r14d
0x18000b345  lea     rcx, [rsp+848h+var_828]; void *
0x18000b34a  shl     r8, 3; Size
0x18000b34e  xor     ebp, ebp
0x18000b350  call    memcpy_0
0x18000b355  xor     eax, eax
0x18000b357  lea     rcx, [rdi+8]; void *
0x18000b35b  xchg    eax, [rdi+4]
0x18000b35e  xor     edx, edx; Val
0x18000b360  mov     r8d, 800h; Size
0x18000b366  call    memset_0
0x18000b36b  mov     rcx, rsi
0x18000b36e  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b374  xor     ebx, ebx
0x18000b376  test    r14d, r14d
0x18000b379  jz      short loc_18000B38C
0x18000b37b  mov     rcx, [rsp+rbx*8+848h+var_828]; this
0x18000b380  call    ?Release@CAdminAcl@@QEAAKXZ; CAdminAcl::Release(void)
0x18000b385  inc     ebx
0x18000b387  cmp     ebx, r14d
0x18000b38a  jb      short loc_18000B37B
0x18000b38c  mov     eax, ebp
0x18000b38e  mov     rcx, [rsp+848h+var_28]
0x18000b396  xor     rcx, rsp; StackCookie
0x18000b399  call    __security_check_cookie
0x18000b39e  lea     r11, [rsp+848h+var_18]
0x18000b3a6  mov     rbx, [r11+28h]
0x18000b3aa  mov     rbp, [r11+30h]
0x18000b3ae  mov     rsp, r11
0x18000b3b1  pop     r14
0x18000b3b3  pop     rdi
0x18000b3b4  pop     rsi
0x18000b3b5  retn
```
