# SmbMmAllocateExchange

- ea: `0x140001cd0`
- end: `0x140001e2f`
- name: `SmbMmAllocateExchange`
- size: `351`
- prototype: `unsigned __int8 *__fastcall(int)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400017a0`
- `0x1400113f4`
- `0x140035968`
- `0x14003e26c`
- `0x14003e560`
- `0x14003e6b4`
- `0x14004ccf0`
- `0x14004d7f0`

## callees

- `0x140001cd0`
- `0x1400169c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001cef`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001cef`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001de1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001de1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001d86`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001d86`

## pseudocode

```c
unsigned __int8 *__fastcall SmbMmAllocateExchange(int a1)
{
  __int64 v1; // rsi
  unsigned __int8 *v2; // rdi
  unsigned __int8 *v3; // rax
  unsigned __int8 *v4; // rbx
  unsigned int v5; // edi
  KIRQL v6; // al
  __int64 *v7; // r8
  __int64 **v8; // rcx
  int v9; // edx
  __int64 (__fastcall **v11)(PVOID); // rax

  v1 = a1;
  v2 = 0;
  v3 = (unsigned __int8 *)ExAllocateFromNPagedLookasideList(&SmbMmExchangesLookasideList + a1);
  v4 = v3;
  if ( !v3 )
    return v2;
  v5 = ExchangeSizeInBytes[v1];
  memset(v3, 0, v5);
  *((_WORD *)v4 + 1) = v5;
  *((_WORD *)v4 + 30) = 0;
  *((_DWORD *)v4 + 18) = 0;
  *(_WORD *)v4 = v1 | 0xED00;
  *((_QWORD *)v4 + 17) = v4 + 128;
  *((_QWORD *)v4 + 16) = v4 + 128;
  *((_QWORD *)v4 + 33) = v4 + 256;
  *((_QWORD *)v4 + 32) = v4 + 256;
  switch ( *v4 )
  {
    case 0u:
      v11 = &ConstructNetRootExchangeDispatch;
      goto LABEL_10;
    case 2u:
      v11 = &TransactExchangeDispatch;
LABEL_10:
      *((_QWORD *)v4 + 19) = v11;
      break;
    case 3u:
      v11 = &ExtendedSessionSetupExchangeDispatch;
      goto LABEL_10;
    case 4u:
      v11 = &AdminExchangeDispatch;
      goto LABEL_10;
  }
  v6 = KeAcquireSpinLockRaiseToDpc(&SmbMmSpinLock);
  v7 = &SmbMmExchangesInUse[2 * *v4];
  v8 = (__int64 **)v7[1];
  if ( *v8 != v7 )
    __fastfail(3u);
  *((_QWORD *)v4 + 2) = v8;
  *((_QWORD *)v4 + 1) = v7;
  v2 = v4;
  *v8 = (__int64 *)(v4 + 8);
  v7[1] = (__int64)(v4 + 8);
  v9 = SmbMmExchangeId;
  *((_DWORD *)v4 + 14) = SmbMmExchangeId;
  SmbMmExchangeId = v9 + 1;
  KeReleaseSpinLock(&SmbMmSpinLock, v6);
  return v2;
}

```

## disassembly

```asm
0x140001cd0  push    rbx
0x140001cd2  push    rbp
0x140001cd3  push    rsi
0x140001cd4  push    rdi
0x140001cd5  sub     rsp, 28h
0x140001cd9  movsxd  rsi, ecx
0x140001cdc  lea     rax, SmbMmExchangesLookasideList
0x140001ce3  mov     rcx, rsi
0x140001ce6  xor     edi, edi
0x140001ce8  shl     rcx, 7
0x140001cec  add     rcx, rax; Lookaside
0x140001cef  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140001cf6  nop     dword ptr [rax+rax+00h]
0x140001cfb  mov     rbx, rax
0x140001cfe  test    rax, rax
0x140001d01  jz      loc_140001DED
0x140001d07  mov     [rsp+48h+arg_0], r14
0x140001d0c  xor     edx, edx; Val
0x140001d0e  lea     r14, cs:140000000h
0x140001d15  mov     rcx, rax; void *
0x140001d18  mov     edi, rva ExchangeSizeInBytes[r14+rsi*4]
0x140001d20  mov     r8d, edi; Size
0x140001d23  call    memset
0x140001d28  xor     eax, eax
0x140001d2a  mov     [rbx+2], di
0x140001d2e  mov     [rbx+3Ch], ax
0x140001d32  or      si, 0ED00h
0x140001d37  mov     [rbx+48h], eax
0x140001d3a  lea     rax, [rbx+80h]
0x140001d41  mov     [rbx], si
0x140001d44  mov     [rax+8], rax
0x140001d48  mov     [rax], rax
0x140001d4b  lea     rax, [rbx+100h]
0x140001d52  mov     [rax+8], rax
0x140001d56  mov     [rax], rax
0x140001d59  movzx   ecx, byte ptr [rbx]
0x140001d5c  test    ecx, ecx
0x140001d5e  jz      loc_140001E1F
0x140001d64  sub     ecx, 2
0x140001d67  jz      loc_140001DFA
0x140001d6d  sub     ecx, 1
0x140001d70  jz      loc_140001E16
0x140001d76  cmp     ecx, 1
0x140001d79  jz      loc_140001E0D
0x140001d7f  lea     rcx, SmbMmSpinLock; SpinLock
0x140001d86  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001d8d  nop     dword ptr [rax+rax+00h]
0x140001d92  movzx   ecx, byte ptr [rbx]
0x140001d95  lea     r8, rva SmbMmExchangesInUse[r14]
0x140001d9c  mov     r14, [rsp+48h+arg_0]
0x140001da1  shl     rcx, 4
0x140001da5  add     r8, rcx
0x140001da8  mov     rcx, [r8+8]
0x140001dac  cmp     [rcx], r8
0x140001daf  jnz     short loc_140001E28
0x140001db1  mov     [rbx+10h], rcx
0x140001db5  lea     rdx, [rbx+8]
0x140001db9  mov     [rdx], r8
0x140001dbc  mov     rdi, rbx
0x140001dbf  mov     [rcx], rdx
0x140001dc2  lea     rcx, SmbMmSpinLock; SpinLock
0x140001dc9  mov     [r8+8], rdx
0x140001dcd  mov     edx, cs:SmbMmExchangeId
0x140001dd3  mov     [rbx+38h], edx
0x140001dd6  inc     edx
0x140001dd8  mov     cs:SmbMmExchangeId, edx
0x140001dde  movzx   edx, al; NewIrql
0x140001de1  call    cs:__imp_KeReleaseSpinLock
0x140001de8  nop     dword ptr [rax+rax+00h]
0x140001ded  mov     rax, rdi
0x140001df0  add     rsp, 28h
0x140001df4  pop     rdi
0x140001df5  pop     rsi
0x140001df6  pop     rbp
0x140001df7  pop     rbx
0x140001df8  retn
0x140001dfa  lea     rax, TransactExchangeDispatch
0x140001e01  mov     [rbx+98h], rax
0x140001e08  jmp     loc_140001D7F
0x140001e0d  lea     rax, AdminExchangeDispatch
0x140001e14  jmp     short loc_140001E01
0x140001e16  lea     rax, ExtendedSessionSetupExchangeDispatch
0x140001e1d  jmp     short loc_140001E01
0x140001e1f  lea     rax, ConstructNetRootExchangeDispatch
0x140001e26  jmp     short loc_140001E01
0x140001e28  mov     ecx, 3
0x140001e2d  int     29h; Win8: RtlFailFast(ecx)
```
