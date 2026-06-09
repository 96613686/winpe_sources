# lldpQueryTlvs

- ea: `0x1400036c0`
- end: `0x1400037ff`
- name: `lldpQueryTlvs`
- size: `319`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, unsigned __int64, unsigned __int64 *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f230`
- `0x14000fdd0`

## callees

- `0x1400036c0`
- `0x140003810`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x140003769`
- `NDIS!NdisReleaseRWLock` at `0x1400037d9`
- `NDIS!NdisReleaseRWLock` at `0x140003769`
- `NDIS!NdisReleaseRWLock` at `0x1400037d9`
- `NDIS!NdisAcquireRWLockRead` at `0x14000370a`
- `NDIS!NdisAcquireRWLockRead` at `0x14000378a`
- `NDIS!NdisAcquireRWLockRead` at `0x14000370a`
- `NDIS!NdisAcquireRWLockRead` at `0x14000378a`

## pseudocode

```c
__int64 __fastcall lldpQueryTlvs(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        unsigned __int64 *a6,
        __int64 a7)
{
  unsigned int v7; // ebx
  int v11; // edx
  __int64 v12; // rcx
  unsigned __int64 *v13; // rsi
  unsigned __int64 v14; // rbp
  __int64 result; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+78h] [rbp+10h] BYREF

  v7 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v11 = a2 - 1;
  if ( !v11 )
  {
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 976), &LockState, 0);
    v14 = a5;
    v13 = a6;
    lldpQueryMib(a1 + 984, a3, a4, a5, a6, a7);
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 976), &LockState);
    goto LABEL_10;
  }
  if ( v11 == 1 )
  {
    NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 960), &LockState, 0);
    v12 = *(_QWORD *)(a1 + 968);
    v13 = a6;
    v14 = a5;
    if ( v12 )
      lldpQueryMib(v12 + 12, a3, a4, a5, a6, a7);
    else
      v7 = -1073741275;
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 960), &LockState);
    if ( v7 )
      return v7;
LABEL_10:
    result = 3221225507LL;
    if ( *v13 > v14 )
      return result;
    return v7;
  }
  return (unsigned int)-1073741584;
}

```

## disassembly

```asm
0x1400036c0  push    rbx
0x1400036c2  push    rbp
0x1400036c3  push    rsi
0x1400036c4  push    rdi
0x1400036c5  push    r14
0x1400036c7  push    r15
0x1400036c9  sub     rsp, 38h
0x1400036cd  xor     eax, eax
0x1400036cf  xor     ebx, ebx
0x1400036d1  mov     word ptr [rsp+68h+LockState.OldIrql], ax
0x1400036d6  mov     r14, r9
0x1400036d9  mov     [rsp+68h+LockState.Flags], al
0x1400036dd  mov     r15, r8
0x1400036e0  mov     rdi, rcx
0x1400036e3  sub     edx, 1
0x1400036e6  jz      loc_14000377B
0x1400036ec  cmp     edx, 1
0x1400036ef  jz      short loc_1400036FB
0x1400036f1  mov     ebx, 0C00000F0h
0x1400036f6  jmp     loc_1400037EF
0x1400036fb  mov     rcx, [rcx+3C0h]; Lock
0x140003702  lea     rdx, [rsp+68h+LockState]; LockState
0x140003707  xor     r8d, r8d; Flags
0x14000370a  call    cs:__imp_NdisAcquireRWLockRead
0x140003711  nop     dword ptr [rax+rax+00h]
0x140003716  mov     rcx, [rdi+3C8h]
0x14000371d  mov     rsi, [rsp+68h+arg_28]
0x140003725  mov     rbp, [rsp+68h+arg_20]
0x14000372d  test    rcx, rcx
0x140003730  jnz     short loc_140003739
0x140003732  mov     ebx, 0C0000225h
0x140003737  jmp     short loc_14000375D
0x140003739  mov     rax, [rsp+68h+arg_30]
0x140003741  add     rcx, 0Ch
0x140003745  mov     [rsp+68h+var_40], rax
0x14000374a  mov     r9, rbp
0x14000374d  mov     r8, r14
0x140003750  mov     [rsp+68h+var_48], rsi
0x140003755  mov     rdx, r15
0x140003758  call    lldpQueryMib
0x14000375d  mov     rcx, [rdi+3C0h]; Lock
0x140003764  lea     rdx, [rsp+68h+LockState]; LockState
0x140003769  call    cs:__imp_NdisReleaseRWLock
0x140003770  nop     dword ptr [rax+rax+00h]
0x140003775  test    ebx, ebx
0x140003777  jz      short loc_1400037E5
0x140003779  jmp     short loc_1400037EF
0x14000377b  mov     rcx, [rcx+3D0h]; Lock
0x140003782  lea     rdx, [rsp+68h+LockState]; LockState
0x140003787  xor     r8d, r8d; Flags
0x14000378a  call    cs:__imp_NdisAcquireRWLockRead
0x140003791  nop     dword ptr [rax+rax+00h]
0x140003796  mov     rax, [rsp+68h+arg_30]
0x14000379e  lea     rcx, [rdi+3D8h]
0x1400037a5  mov     rbp, [rsp+68h+arg_20]
0x1400037ad  mov     r8, r14
0x1400037b0  mov     rsi, [rsp+68h+arg_28]
0x1400037b8  mov     r9, rbp
0x1400037bb  mov     [rsp+68h+var_40], rax
0x1400037c0  mov     rdx, r15
0x1400037c3  mov     [rsp+68h+var_48], rsi
0x1400037c8  call    lldpQueryMib
0x1400037cd  mov     rcx, [rdi+3D0h]; Lock
0x1400037d4  lea     rdx, [rsp+68h+LockState]; LockState
0x1400037d9  call    cs:__imp_NdisReleaseRWLock
0x1400037e0  nop     dword ptr [rax+rax+00h]
0x1400037e5  mov     eax, 0C0000023h
0x1400037ea  cmp     [rsi], rbp
0x1400037ed  ja      short loc_1400037F1
0x1400037ef  mov     eax, ebx
0x1400037f1  add     rsp, 38h
0x1400037f5  pop     r15
0x1400037f7  pop     r14
0x1400037f9  pop     rdi
0x1400037fa  pop     rsi
0x1400037fb  pop     rbp
0x1400037fc  pop     rbx
0x1400037fd  retn
```
