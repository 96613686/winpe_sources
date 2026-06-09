# PcpFilterIncrementIntercept

- ea: `0x14000b250`
- end: `0x14000b2e2`
- name: `PcpFilterIncrementIntercept`
- size: `146`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003ab0`
- `0x14000e7e0`
- `0x14000e880`

## callees

- `0x14000b250`
- `0x14000b91c`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x14000b2c8`
- `NDIS!NdisReleaseRWLock` at `0x14000b2c8`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b274`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b274`

## pseudocode

```c
__int64 PcpFilterIncrementIntercept()
{
  int v0; // ebx
  __int64 *v1; // rdi
  __int64 *v2; // rcx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(PcgFilterDriverContext, &LockState, 0);
  if ( ++dword_140018838 )
  {
    v1 = (__int64 *)qword_140018828;
    v0 = 0;
    while ( v1 != &qword_140018828 )
    {
      v2 = v1;
      v1 = (__int64 *)*v1;
      v0 = PcpFilterEnableIntercept(v2);
      if ( v0 < 0 )
        goto LABEL_6;
    }
  }
  else
  {
    v0 = -1073741675;
LABEL_6:
    --dword_140018838;
  }
  NdisReleaseRWLock(PcgFilterDriverContext, &LockState);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14000b250  mov     [rsp+arg_10], rbx
0x14000b255  push    rdi
0x14000b256  sub     rsp, 20h
0x14000b25a  mov     rcx, cs:PcgFilterDriverContext; Lock
0x14000b261  lea     rdx, [rsp+28h+LockState]; LockState
0x14000b266  xor     eax, eax
0x14000b268  xor     r8d, r8d; Flags
0x14000b26b  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x14000b270  mov     [rsp+28h+LockState.Flags], al
0x14000b274  call    cs:__imp_NdisAcquireRWLockWrite
0x14000b27b  nop     dword ptr [rax+rax+00h]
0x14000b280  add     cs:dword_140018838, 1
0x14000b287  jnz     short loc_14000B290
0x14000b289  mov     ebx, 0C0000095h
0x14000b28e  jmp     short loc_14000B2B6
0x14000b290  mov     rdi, cs:qword_140018828
0x14000b297  xor     ebx, ebx
0x14000b299  lea     rax, qword_140018828
0x14000b2a0  cmp     rdi, rax
0x14000b2a3  jz      short loc_14000B2BC
0x14000b2a5  mov     rcx, rdi
0x14000b2a8  mov     rdi, [rdi]
0x14000b2ab  call    PcpFilterEnableIntercept
0x14000b2b0  mov     ebx, eax
0x14000b2b2  test    eax, eax
0x14000b2b4  jns     short loc_14000B299
0x14000b2b6  dec     cs:dword_140018838
0x14000b2bc  mov     rcx, cs:PcgFilterDriverContext; Lock
0x14000b2c3  lea     rdx, [rsp+28h+LockState]; LockState
0x14000b2c8  call    cs:__imp_NdisReleaseRWLock
0x14000b2cf  nop     dword ptr [rax+rax+00h]
0x14000b2d4  mov     eax, ebx
0x14000b2d6  mov     rbx, [rsp+28h+arg_10]
0x14000b2db  add     rsp, 20h
0x14000b2df  pop     rdi
0x14000b2e0  retn
```
