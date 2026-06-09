# FvepReleaseScalableRemoveLockAndWait

- ea: `0x140027948`
- end: `0x140027a9e`
- name: `FvepReleaseScalableRemoveLockAndWait`
- size: `342`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400277dc`

## callees

- `0x140027948`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400279e7`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400279e7`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400279f7`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400279f7`
- `ntoskrnl!KeBugCheckEx` at `0x14002799c`
- `ntoskrnl!KeBugCheckEx` at `0x1400279d6`
- `ntoskrnl!KeBugCheckEx` at `0x140027a4a`
- `ntoskrnl!KeBugCheckEx` at `0x140027a8a`
- `ntoskrnl!KeBugCheckEx` at `0x14002799c`
- `ntoskrnl!KeBugCheckEx` at `0x1400279d6`
- `ntoskrnl!KeBugCheckEx` at `0x140027a4a`
- `ntoskrnl!KeBugCheckEx` at `0x140027a8a`

## pseudocode

```c
__int64 __fastcall FvepReleaseScalableRemoveLockAndWait(ULONG_PTR BugCheckParameter2)
{
  __int64 result; // rax
  signed __int64 v3; // [rsp+48h] [rbp+10h]
  signed __int64 v4; // [rsp+48h] [rbp+10h]

  v3 = _InterlockedExchangeAdd64((volatile signed __int64 *)(BugCheckParameter2 + 8), 0x1000000000000uLL);
  if ( WORD2(v3) )
    KeBugCheckEx(0x120u, 0xEu, BugCheckParameter2, WORD2(v3), BYTE6(v3));
  if ( (v3 & 0xFF000000000000LL) != 0 )
    KeBugCheckEx(0x120u, 0xEu, BugCheckParameter2, 0, BYTE6(v3));
  ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(BugCheckParameter2 + 48));
  ExWaitForRundownProtectionReleaseCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(BugCheckParameter2 + 48));
  v4 = _InterlockedExchangeAdd64((volatile signed __int64 *)(BugCheckParameter2 + 8), 0x1000000000000uLL);
  if ( WORD2(v4) )
    KeBugCheckEx(0x120u, 0xEu, BugCheckParameter2, WORD2(v4), BYTE6(v4));
  result = HIDWORD(v4) & 0xFF0000;
  if ( (_DWORD)result != 0x10000 )
    KeBugCheckEx(0x120u, 0xEu, BugCheckParameter2, 0, BYTE6(v4));
  return result;
}

```

## disassembly

```asm
0x140027948  mov     [rsp+arg_8], rdx
0x14002794d  push    rbx
0x14002794e  sub     rsp, 30h
0x140027952  mov     [rsp+38h+arg_8], 0
0x14002795b  mov     rbx, rcx
0x14002795e  mov     dword ptr [rsp+38h+arg_8+4], 10000h
0x140027966  mov     rax, [rsp+38h+arg_8]
0x14002796b  lock xadd [rcx+8], rax
0x140027971  mov     [rsp+38h+arg_8], rax
0x140027976  shr     rax, 20h
0x14002797a  test    ax, ax
0x14002797d  jz      short loc_1400279A9
0x14002797f  movzx   r9d, ax; BugCheckParameter3
0x140027983  mov     r8, rbx; BugCheckParameter2
0x140027986  shr     rax, 10h
0x14002798a  mov     edx, 0Eh; BugCheckParameter1
0x14002798f  movzx   ecx, al
0x140027992  mov     [rsp+38h+BugCheckParameter4], rcx; BugCheckParameter4
0x140027997  mov     ecx, 120h; BugCheckCode
0x14002799c  call    cs:__imp_KeBugCheckEx
0x1400279a9  test    dword ptr [rsp+38h+arg_8+4], 0FF0000h
0x1400279b1  jz      short loc_1400279E3
0x1400279b3  mov     edx, dword ptr [rsp+38h+arg_8+4]
0x1400279b7  mov     r8, rbx; BugCheckParameter2
0x1400279ba  mov     eax, edx
0x1400279bc  movzx   r9d, dx; BugCheckParameter3
0x1400279c0  shr     rax, 10h
0x1400279c4  mov     edx, 0Eh; BugCheckParameter1
0x1400279c9  movzx   ecx, al
0x1400279cc  mov     [rsp+38h+BugCheckParameter4], rcx; BugCheckParameter4
0x1400279d1  mov     ecx, 120h; BugCheckCode
0x1400279d6  call    cs:__imp_KeBugCheckEx
0x1400279e3  mov     rcx, [rcx+30h]; RunRefCacheAware
0x1400279e7  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400279ee  nop     dword ptr [rax+rax+00h]
0x1400279f3  mov     rcx, [rbx+30h]; RunRef
0x1400279f7  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1400279fe  nop     dword ptr [rax+rax+00h]
0x140027a03  mov     [rsp+38h+arg_8], 0
0x140027a0c  mov     dword ptr [rsp+38h+arg_8+4], 10000h
0x140027a14  mov     rax, [rsp+38h+arg_8]
0x140027a19  lock xadd [rbx+8], rax
0x140027a1f  mov     [rsp+38h+arg_8], rax
0x140027a24  shr     rax, 20h
0x140027a28  test    ax, ax
0x140027a2b  jz      short loc_140027A57
0x140027a2d  movzx   r9d, ax; BugCheckParameter3
0x140027a31  mov     r8, rbx; BugCheckParameter2
0x140027a34  shr     rax, 10h
0x140027a38  mov     edx, 0Eh; BugCheckParameter1
0x140027a3d  movzx   ecx, al
0x140027a40  mov     [rsp+38h+BugCheckParameter4], rcx; BugCheckParameter4
0x140027a45  mov     ecx, 120h; BugCheckCode
0x140027a4a  call    cs:__imp_KeBugCheckEx
0x140027a57  mov     eax, dword ptr [rsp+38h+arg_8+4]
0x140027a5b  and     eax, 0FF0000h
0x140027a60  cmp     eax, 10000h
0x140027a65  jz      short loc_140027A97
0x140027a67  mov     edx, dword ptr [rsp+38h+arg_8+4]
0x140027a6b  mov     r8, rbx; BugCheckParameter2
0x140027a6e  mov     eax, edx
0x140027a70  movzx   r9d, dx; BugCheckParameter3
0x140027a74  shr     rax, 10h
0x140027a78  mov     edx, 0Eh; BugCheckParameter1
0x140027a7d  movzx   ecx, al
0x140027a80  mov     [rsp+38h+BugCheckParameter4], rcx; BugCheckParameter4
0x140027a85  mov     ecx, 120h; BugCheckCode
0x140027a8a  call    cs:__imp_KeBugCheckEx
0x140027a97  add     rsp, 30h
0x140027a9b  pop     rbx
0x140027a9c  retn
```
