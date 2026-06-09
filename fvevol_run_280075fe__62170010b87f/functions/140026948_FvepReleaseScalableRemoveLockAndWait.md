# FvepReleaseScalableRemoveLockAndWait

- ea: `0x140026948`
- end: `0x140026a9e`
- name: `FvepReleaseScalableRemoveLockAndWait`
- size: `342`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400267dc`

## callees

- `0x140026948`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400269e7`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400269e7`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400269f7`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400269f7`
- `ntoskrnl!KeBugCheckEx` at `0x14002699c`
- `ntoskrnl!KeBugCheckEx` at `0x1400269d6`
- `ntoskrnl!KeBugCheckEx` at `0x140026a4a`
- `ntoskrnl!KeBugCheckEx` at `0x140026a8a`
- `ntoskrnl!KeBugCheckEx` at `0x14002699c`
- `ntoskrnl!KeBugCheckEx` at `0x1400269d6`
- `ntoskrnl!KeBugCheckEx` at `0x140026a4a`
- `ntoskrnl!KeBugCheckEx` at `0x140026a8a`

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
0x140026948  mov     [rsp+arg_8], rdx
0x14002694d  push    rbx
0x14002694e  sub     rsp, 30h
0x140026952  mov     [rsp+38h+arg_8], 0
0x14002695b  mov     rbx, rcx
0x14002695e  mov     dword ptr [rsp+38h+arg_8+4], 10000h
0x140026966  mov     rax, [rsp+38h+arg_8]
0x14002696b  lock xadd [rcx+8], rax
0x140026971  mov     [rsp+38h+arg_8], rax
0x140026976  shr     rax, 20h
0x14002697a  test    ax, ax
0x14002697d  jz      short loc_1400269A9
0x14002697f  movzx   r9d, ax; BugCheckParameter3
0x140026983  mov     r8, rbx; BugCheckParameter2
0x140026986  shr     rax, 10h
0x14002698a  mov     edx, 0Eh; BugCheckParameter1
0x14002698f  movzx   ecx, al
0x140026992  mov     [rsp+38h+BugCheckParameter4], rcx; BugCheckParameter4
0x140026997  mov     ecx, 120h; BugCheckCode
0x14002699c  call    cs:__imp_KeBugCheckEx
0x1400269a9  test    dword ptr [rsp+38h+arg_8+4], 0FF0000h
0x1400269b1  jz      short loc_1400269E3
0x1400269b3  mov     edx, dword ptr [rsp+38h+arg_8+4]
0x1400269b7  mov     r8, rbx; BugCheckParameter2
0x1400269ba  mov     eax, edx
0x1400269bc  movzx   r9d, dx; BugCheckParameter3
0x1400269c0  shr     rax, 10h
0x1400269c4  mov     edx, 0Eh; BugCheckParameter1
0x1400269c9  movzx   ecx, al
0x1400269cc  mov     [rsp+38h+BugCheckParameter4], rcx; BugCheckParameter4
0x1400269d1  mov     ecx, 120h; BugCheckCode
0x1400269d6  call    cs:__imp_KeBugCheckEx
0x1400269e3  mov     rcx, [rcx+30h]; RunRefCacheAware
0x1400269e7  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400269ee  nop     dword ptr [rax+rax+00h]
0x1400269f3  mov     rcx, [rbx+30h]; RunRef
0x1400269f7  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1400269fe  nop     dword ptr [rax+rax+00h]
0x140026a03  mov     [rsp+38h+arg_8], 0
0x140026a0c  mov     dword ptr [rsp+38h+arg_8+4], 10000h
0x140026a14  mov     rax, [rsp+38h+arg_8]
0x140026a19  lock xadd [rbx+8], rax
0x140026a1f  mov     [rsp+38h+arg_8], rax
0x140026a24  shr     rax, 20h
0x140026a28  test    ax, ax
0x140026a2b  jz      short loc_140026A57
0x140026a2d  movzx   r9d, ax; BugCheckParameter3
0x140026a31  mov     r8, rbx; BugCheckParameter2
0x140026a34  shr     rax, 10h
0x140026a38  mov     edx, 0Eh; BugCheckParameter1
0x140026a3d  movzx   ecx, al
0x140026a40  mov     [rsp+38h+BugCheckParameter4], rcx; BugCheckParameter4
0x140026a45  mov     ecx, 120h; BugCheckCode
0x140026a4a  call    cs:__imp_KeBugCheckEx
0x140026a57  mov     eax, dword ptr [rsp+38h+arg_8+4]
0x140026a5b  and     eax, 0FF0000h
0x140026a60  cmp     eax, 10000h
0x140026a65  jz      short loc_140026A97
0x140026a67  mov     edx, dword ptr [rsp+38h+arg_8+4]
0x140026a6b  mov     r8, rbx; BugCheckParameter2
0x140026a6e  mov     eax, edx
0x140026a70  movzx   r9d, dx; BugCheckParameter3
0x140026a74  shr     rax, 10h
0x140026a78  mov     edx, 0Eh; BugCheckParameter1
0x140026a7d  movzx   ecx, al
0x140026a80  mov     [rsp+38h+BugCheckParameter4], rcx; BugCheckParameter4
0x140026a85  mov     ecx, 120h; BugCheckCode
0x140026a8a  call    cs:__imp_KeBugCheckEx
0x140026a97  add     rsp, 30h
0x140026a9b  pop     rbx
0x140026a9c  retn
```
