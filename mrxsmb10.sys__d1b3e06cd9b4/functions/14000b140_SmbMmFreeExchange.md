# SmbMmFreeExchange

- ea: `0x14000b140`
- end: `0x14000b201`
- name: `SmbMmFreeExchange`
- size: `193`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400017a0`
- `0x1400113f4`
- `0x14003e06c`
- `0x14003e26c`
- `0x14003e560`
- `0x14003e6b4`
- `0x14004ccf0`
- `0x14004d7f0`

## callees

- `0x14000b140`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b1ca`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b1ca`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b1a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b1a1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b16d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b16d`

## pseudocode

```c
void __fastcall SmbMmFreeExchange(_BYTE *Entry)
{
  __int64 v2; // rdi
  KIRQL v3; // al
  _BYTE **v4; // r9
  PVOID *v5; // r8

  if ( Entry )
  {
    v2 = (unsigned __int8)*Entry;
    if ( Entry[255] )
    {
      CngRsa32Compat_MD5Final(Entry + 272);
      Entry[255] = 0;
    }
    v3 = KeAcquireSpinLockRaiseToDpc(&SmbMmSpinLock);
    v4 = (_BYTE **)*((_QWORD *)Entry + 1);
    if ( v4[1] != Entry + 8 || (v5 = (PVOID *)*((_QWORD *)Entry + 2), *v5 != Entry + 8) )
      __fastfail(3u);
    *v5 = v4;
    v4[1] = v5;
    KeReleaseSpinLock(&SmbMmSpinLock, v3);
    if ( (*((_DWORD *)Entry + 18) & 0x800) == 0 )
      ExFreeToNPagedLookasideList(&SmbMmExchangesLookasideList + v2, Entry);
  }
}

```

## disassembly

```asm
0x14000b140  test    rcx, rcx
0x14000b143  jz      locret_14000B1E0
0x14000b149  push    rbx
0x14000b14a  sub     rsp, 20h
0x14000b14e  cmp     byte ptr [rcx+0FFh], 0
0x14000b155  mov     rbx, rcx
0x14000b158  mov     [rsp+28h+arg_0], rdi
0x14000b15d  movzx   edi, byte ptr [rcx]
0x14000b160  jnz     loc_14000B1E9
0x14000b166  lea     rcx, SmbMmSpinLock; SpinLock
0x14000b16d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b174  nop     dword ptr [rax+rax+00h]
0x14000b179  mov     r9, [rbx+8]
0x14000b17d  lea     rdx, [rbx+8]
0x14000b181  cmp     [r9+8], rdx
0x14000b185  jnz     short loc_14000B1E2
0x14000b187  mov     r8, [rdx+8]
0x14000b18b  cmp     [r8], rdx
0x14000b18e  jnz     short loc_14000B1E2
0x14000b190  mov     [r8], r9
0x14000b193  lea     rcx, SmbMmSpinLock; SpinLock
0x14000b19a  movzx   edx, al; NewIrql
0x14000b19d  mov     [r9+8], r8
0x14000b1a1  call    cs:__imp_KeReleaseSpinLock
0x14000b1a8  nop     dword ptr [rax+rax+00h]
0x14000b1ad  test    dword ptr [rbx+48h], 800h
0x14000b1b4  jnz     short loc_14000B1D6
0x14000b1b6  lea     rax, SmbMmExchangesLookasideList
0x14000b1bd  mov     rcx, rdi
0x14000b1c0  shl     rcx, 7
0x14000b1c4  mov     rdx, rbx; Entry
0x14000b1c7  add     rcx, rax; Lookaside
0x14000b1ca  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b1d1  nop     dword ptr [rax+rax+00h]
0x14000b1d6  mov     rdi, [rsp+28h+arg_0]
0x14000b1db  add     rsp, 20h
0x14000b1df  pop     rbx
0x14000b1e0  retn
0x14000b1e2  mov     ecx, 3
0x14000b1e7  int     29h; Win8: RtlFailFast(ecx)
0x14000b1e9  add     rcx, 110h
0x14000b1f0  call    CngRsa32Compat_MD5Final
0x14000b1f5  mov     byte ptr [rbx+0FFh], 0
0x14000b1fc  jmp     loc_14000B166
```
