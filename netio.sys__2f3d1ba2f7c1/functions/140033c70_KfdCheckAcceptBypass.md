# KfdCheckAcceptBypass

- ea: `0x140033c70`
- end: `0x140033e12`
- name: `KfdCheckAcceptBypass`
- size: `418`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140033c70`
- `0x140033e20`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140033cf0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140033d74`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140033cf0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140033d74`
- `ntoskrnl!KeGetCurrentIrql` at `0x140033cb6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140033cb6`
- `NDIS!NdisAcquireRWLockRead` at `0x140033cd4`
- `NDIS!NdisAcquireRWLockRead` at `0x140033cd4`
- `NDIS!NdisReleaseRWLock` at `0x140033da5`
- `NDIS!NdisReleaseRWLock` at `0x140033da5`

## pseudocode

```c
__int64 __fastcall KfdCheckAcceptBypass(__int16 a1, __int64 a2, _DWORD *a3, __int64 a4)
{
  __int64 v7; // rbp
  PNPAGED_LOOKASIDE_LIST v8; // rdi
  KIRQL CurrentIrql; // bl
  __int64 v10; // rdx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v11; // rcx
  PNPAGED_LOOKASIDE_LIST v12; // rbx
  _DWORD *v13; // rdx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v15; // [rsp+20h] [rbp-38h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+60h] [rbp+8h] BYREF

  v15 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  switch ( a1 )
  {
    case '0':
      v7 = 0;
      break;
    case ',':
      v7 = 2;
      break;
    case '.':
      v7 = 3;
      break;
    default:
      v7 = a1 == 50;
      break;
  }
  v8 = gWfpGlobal;
  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v8[13].L.ListEntry.Flink, &LockState, 0);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v10 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v10 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v10 = 4;
  }
  FindAcceptBypassCacheEntry((__int64)(&gWfpGlobal[7].L.Depth + 24 * v7), a2, &v15);
  v11 = v15;
  if ( v15 )
  {
    *a3 = 1;
    *(_DWORD *)a4 = v11[2].Signature;
    *(_QWORD *)(a4 + 16) = v11[3].Linkage.Flink;
  }
  else
  {
    *a3 = 0;
    *(_DWORD *)a4 = 7;
  }
  v12 = gWfpGlobal;
  if ( gWfpPerProContext )
  {
    v13 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v13 == 4 )
      *v13 = 0;
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v12[13].L.ListEntry.Flink, &LockState);
  return 0;
}

```

## disassembly

```asm
0x140033c70  mov     [rsp+arg_8], rbx
0x140033c75  mov     [rsp+arg_10], rbp
0x140033c7a  push    rsi
0x140033c7b  push    rdi
0x140033c7c  push    r12
0x140033c7e  push    r14
0x140033c80  push    r15
0x140033c82  sub     rsp, 30h
0x140033c86  xor     eax, eax
0x140033c88  xor     r12d, r12d
0x140033c8b  mov     [rsp+58h+var_38], r12
0x140033c90  mov     rsi, r9
0x140033c93  mov     word ptr [rsp+58h+LockState.OldIrql], ax
0x140033c98  mov     r14, r8
0x140033c9b  mov     [rsp+58h+LockState.Flags], al
0x140033c9f  mov     r15, rdx
0x140033ca2  cmp     cx, 30h ; '0'
0x140033ca6  jnz     loc_140033DDB
0x140033cac  mov     ebp, r12d
0x140033caf  mov     rdi, cs:gWfpGlobal
0x140033cb6  call    cs:__imp_KeGetCurrentIrql
0x140033cbd  nop     dword ptr [rax+rax+00h]
0x140033cc2  mov     rcx, [rdi+6C0h]; Lock
0x140033cc9  lea     rdx, [rsp+58h+LockState]; LockState
0x140033cce  xor     r8d, r8d; Flags
0x140033cd1  movzx   ebx, al
0x140033cd4  call    cs:__imp_NdisAcquireRWLockRead
0x140033cdb  nop     dword ptr [rax+rax+00h]
0x140033ce0  cmp     bl, 2
0x140033ce3  jz      short loc_140033D24
0x140033ce5  cmp     cs:gWfpPerProContext, r12
0x140033cec  jz      short loc_140033D24
0x140033cee  xor     ecx, ecx; ProcNumber
0x140033cf0  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140033cf7  nop     dword ptr [rax+rax+00h]
0x140033cfc  imul    eax, cs:gWfpPerProContextSize
0x140033d03  mov     ecx, eax
0x140033d05  mov     rax, cs:gWfpPerProContext
0x140033d0c  mov     rdx, [rcx+rax]
0x140033d10  mov     rax, ds:0FFFFF78000000008h
0x140033d1a  mov     [rdx+8], rax
0x140033d1e  mov     dword ptr [rdx], 4
0x140033d24  lea     rcx, [rbp+13h]
0x140033d28  mov     rdx, r15
0x140033d2b  lea     rcx, [rcx+rcx*2]
0x140033d2f  shl     rcx, 4
0x140033d33  lea     r8, [rsp+58h+var_38]
0x140033d38  add     rcx, cs:gWfpGlobal
0x140033d3f  call    FindAcceptBypassCacheEntry
0x140033d44  mov     rcx, [rsp+58h+var_38]
0x140033d49  test    rcx, rcx
0x140033d4c  jz      short loc_140033DCB
0x140033d4e  mov     dword ptr [r14], 1
0x140033d55  mov     eax, [rcx+40h]
0x140033d58  mov     [rsi], eax
0x140033d5a  mov     rax, [rcx+48h]
0x140033d5e  mov     [rsi+10h], rax
0x140033d62  cmp     cs:gWfpPerProContext, r12
0x140033d69  mov     rbx, cs:gWfpGlobal
0x140033d70  jz      short loc_140033D99
0x140033d72  xor     ecx, ecx; ProcNumber
0x140033d74  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140033d7b  nop     dword ptr [rax+rax+00h]
0x140033d80  imul    eax, cs:gWfpPerProContextSize
0x140033d87  mov     ecx, eax
0x140033d89  mov     rax, cs:gWfpPerProContext
0x140033d90  mov     rdx, [rcx+rax]
0x140033d94  cmp     dword ptr [rdx], 4
0x140033d97  jz      short loc_140033DD6
0x140033d99  mov     rcx, [rbx+6C0h]; Lock
0x140033da0  lea     rdx, [rsp+58h+LockState]; LockState
0x140033da5  call    cs:__imp_NdisReleaseRWLock
0x140033dac  nop     dword ptr [rax+rax+00h]
0x140033db1  mov     rbx, [rsp+58h+arg_8]
0x140033db6  xor     eax, eax
0x140033db8  mov     rbp, [rsp+58h+arg_10]
0x140033dbd  add     rsp, 30h
0x140033dc1  pop     r15
0x140033dc3  pop     r14
0x140033dc5  pop     r12
0x140033dc7  pop     rdi
0x140033dc8  pop     rsi
0x140033dc9  retn
0x140033dcb  mov     [r14], r12d
0x140033dce  mov     dword ptr [rsi], 7
0x140033dd4  jmp     short loc_140033D62
0x140033dd6  mov     [rdx], r12d
0x140033dd9  jmp     short loc_140033D99
0x140033ddb  cmp     cx, 2Ch ; ','
0x140033ddf  jnz     short loc_140033DEB
0x140033de1  mov     ebp, 2
0x140033de6  jmp     loc_140033CAF
0x140033deb  cmp     cx, 2Eh ; '.'
0x140033def  jnz     short loc_140033DFB
0x140033df1  mov     ebp, 3
0x140033df6  jmp     loc_140033CAF
0x140033dfb  mov     rbp, r12
0x140033dfe  cmp     cx, 32h ; '2'
0x140033e02  jnz     loc_140033CAF
0x140033e08  mov     ebp, 1
0x140033e0d  jmp     loc_140033CAF
```
