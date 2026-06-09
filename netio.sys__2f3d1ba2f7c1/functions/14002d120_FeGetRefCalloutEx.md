# FeGetRefCalloutEx

- ea: `0x14002d120`
- end: `0x14002d276`
- name: `FeGetRefCalloutEx`
- size: `342`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14001c31c`
- `0x14002e150`
- `0x140038e00`
- `0x140041b48`
- `0x140044710`
- `0x1400617e8`
- `0x140066ae0`

## callees

- `0x14002d120`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002d186`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002d216`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002d186`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14002d216`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002d14b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002d14b`
- `NDIS!NdisAcquireRWLockRead` at `0x14002d169`
- `NDIS!NdisAcquireRWLockRead` at `0x14002d169`
- `NDIS!NdisReleaseRWLock` at `0x14002d247`
- `NDIS!NdisReleaseRWLock` at `0x14002d247`

## pseudocode

```c
void __fastcall FeGetRefCalloutEx(unsigned int a1, char a2, _QWORD *a3)
{
  PNPAGED_LOOKASIDE_LIST v3; // rdi
  __int64 v6; // rsi
  KIRQL CurrentIrql; // bl
  __int64 v8; // rdx
  unsigned __int8 *v9; // rax
  int v10; // ecx
  PNPAGED_LOOKASIDE_LIST v11; // rbx
  _DWORD *v12; // rdx
  struct _LOCK_STATE_EX LockState; // [rsp+40h] [rbp+8h] BYREF

  v3 = gWfpGlobal;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v6 = a1;
  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v3[1].L.ListHead.Alignment, &LockState, 0);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v8 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v8 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v8 = 4;
  }
  if ( (unsigned int)v6 >= gWfpGlobal[3].L.FreeMisses
    || ((v9 = (unsigned __int8 *)(144 * v6 + *(_QWORD *)&gWfpGlobal[3].L.Tag), *a3 = v9, (a2 & 1) == 0)
      ? (v10 = *((_DWORD *)v9 + 1))
      : (v10 = *((_DWORD *)v9 + 1) | v9[12]),
        !v10) )
  {
    v9 = (unsigned __int8 *)gFeCallout;
    *a3 = gFeCallout;
  }
  _InterlockedIncrement((volatile signed __int32 *)v9 + 16);
  v11 = gWfpGlobal;
  if ( gWfpPerProContext )
  {
    v12 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v12 == 4 )
      *v12 = 0;
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v11[1].L.ListHead.Alignment, &LockState);
}

```

## disassembly

```asm
0x14002d120  mov     [rsp+arg_8], rbx
0x14002d125  mov     [rsp+arg_10], rbp
0x14002d12a  push    rsi
0x14002d12b  push    rdi
0x14002d12c  push    r14
0x14002d12e  sub     rsp, 20h
0x14002d132  mov     rdi, cs:gWfpGlobal
0x14002d139  xor     eax, eax
0x14002d13b  mov     word ptr [rsp+38h+LockState.OldIrql], ax
0x14002d140  mov     r14, r8
0x14002d143  mov     [rsp+38h+LockState.Flags], al
0x14002d147  mov     ebp, edx
0x14002d149  mov     esi, ecx
0x14002d14b  call    cs:__imp_KeGetCurrentIrql
0x14002d152  nop     dword ptr [rax+rax+00h]
0x14002d157  mov     rcx, [rdi+80h]; Lock
0x14002d15e  lea     rdx, [rsp+38h+LockState]; LockState
0x14002d163  xor     r8d, r8d; Flags
0x14002d166  movzx   ebx, al
0x14002d169  call    cs:__imp_NdisAcquireRWLockRead
0x14002d170  nop     dword ptr [rax+rax+00h]
0x14002d175  cmp     bl, 2
0x14002d178  jz      short loc_14002D1BA
0x14002d17a  cmp     cs:gWfpPerProContext, 0
0x14002d182  jz      short loc_14002D1BA
0x14002d184  xor     ecx, ecx; ProcNumber
0x14002d186  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14002d18d  nop     dword ptr [rax+rax+00h]
0x14002d192  imul    eax, cs:gWfpPerProContextSize
0x14002d199  mov     ecx, eax
0x14002d19b  mov     rax, cs:gWfpPerProContext
0x14002d1a2  mov     rdx, [rcx+rax]
0x14002d1a6  mov     rax, ds:0FFFFF78000000008h
0x14002d1b0  mov     [rdx+8], rax
0x14002d1b4  mov     dword ptr [rdx], 4
0x14002d1ba  mov     rdx, cs:gWfpGlobal
0x14002d1c1  cmp     esi, [rdx+1A0h]
0x14002d1c7  jnb     short loc_14002D1F5
0x14002d1c9  mov     rax, [rdx+1A8h]
0x14002d1d0  lea     rcx, [rsi+rsi*8]
0x14002d1d4  shl     rcx, 4
0x14002d1d8  add     rax, rcx
0x14002d1db  mov     [r14], rax
0x14002d1de  mov     edx, [rax+4]
0x14002d1e1  test    bpl, 1
0x14002d1e5  jz      loc_14002D26F
0x14002d1eb  movzx   ecx, byte ptr [rax+0Ch]
0x14002d1ef  or      ecx, edx
0x14002d1f1  test    ecx, ecx
0x14002d1f3  jnz     short loc_14002D1FF
0x14002d1f5  mov     rax, cs:gFeCallout
0x14002d1fc  mov     [r14], rax
0x14002d1ff  lock inc dword ptr [rax+40h]
0x14002d203  cmp     cs:gWfpPerProContext, 0
0x14002d20b  mov     rbx, cs:gWfpGlobal
0x14002d212  jz      short loc_14002D23B
0x14002d214  xor     ecx, ecx; ProcNumber
0x14002d216  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14002d21d  nop     dword ptr [rax+rax+00h]
0x14002d222  imul    eax, cs:gWfpPerProContextSize
0x14002d229  mov     ecx, eax
0x14002d22b  mov     rax, cs:gWfpPerProContext
0x14002d232  mov     rdx, [rcx+rax]
0x14002d236  cmp     dword ptr [rdx], 4
0x14002d239  jz      short loc_14002D267
0x14002d23b  mov     rcx, [rbx+80h]; Lock
0x14002d242  lea     rdx, [rsp+38h+LockState]; LockState
0x14002d247  call    cs:__imp_NdisReleaseRWLock
0x14002d24e  nop     dword ptr [rax+rax+00h]
0x14002d253  mov     rbx, [rsp+38h+arg_8]
0x14002d258  mov     rbp, [rsp+38h+arg_10]
0x14002d25d  add     rsp, 20h
0x14002d261  pop     r14
0x14002d263  pop     rdi
0x14002d264  pop     rsi
0x14002d265  retn
0x14002d267  mov     dword ptr [rdx], 0
0x14002d26d  jmp     short loc_14002D23B
0x14002d26f  mov     ecx, edx
0x14002d271  jmp     loc_14002D1F1
```
