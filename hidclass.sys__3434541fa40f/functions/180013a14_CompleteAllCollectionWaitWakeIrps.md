# CompleteAllCollectionWaitWakeIrps

- ea: `0x180013a14`
- end: `0x180013b54`
- name: `CompleteAllCollectionWaitWakeIrps`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015b98`
- `0x18001b4f0`

## callees

- `0x180013a14`

## import_xrefs

- `ntoskrnl!PoSetSystemWake` at `0x180013b46`
- `ntoskrnl!PoSetSystemWake` at `0x180013b46`
- `ntoskrnl!IofCompleteRequest` at `0x180013b1d`
- `ntoskrnl!IofCompleteRequest` at `0x180013b1d`
- `ntoskrnl!KeReleaseSpinLock` at `0x180013acd`
- `ntoskrnl!KeReleaseSpinLock` at `0x180013acd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180013a3f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180013a3f`

## pseudocode

```c
__int64 *__fastcall CompleteAllCollectionWaitWakeIrps(__int64 a1, int a2)
{
  KSPIN_LOCK *v3; // rbx
  KIRQL v5; // r9
  __int64 ****v6; // r8
  __int64 ***v7; // rcx
  __int64 **v8; // rax
  _QWORD *v9; // rax
  __int64 *result; // rax
  __int64 *v11; // rcx
  IRP *v12; // rbx
  __int64 *v13; // [rsp+20h] [rbp-18h] BYREF
  __int64 **v14; // [rsp+28h] [rbp-10h]

  v14 = &v13;
  v3 = (KSPIN_LOCK *)(a1 + 488);
  v13 = (__int64 *)&v13;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 488));
  v6 = (__int64 ****)(a1 + 472);
  while ( 1 )
  {
    v7 = *v6;
    if ( *v6 == (__int64 ***)v6 )
      break;
    if ( v7[1] != (__int64 **)v6 || (v8 = *v7, (*v7)[1] != (__int64 *)v7) )
LABEL_16:
      __fastfail(3u);
    *v6 = (__int64 ***)v8;
    v8[1] = (__int64 *)v6;
    v7[1] = (__int64 **)v7;
    *v7 = (__int64 **)v7;
    if ( _InterlockedExchange64((volatile __int64 *)v7 - 8, 0) )
    {
      v9 = v14;
      if ( *v14 != (__int64 *)&v13 )
        goto LABEL_16;
      v7[1] = v14;
      *v7 = &v13;
      *v9 = v7;
      v14 = (__int64 **)v7;
      _InterlockedExchange64((volatile __int64 *)(v7[2][5][8] + 144), 0);
    }
  }
  KeReleaseSpinLock(v3, v5);
  while ( 1 )
  {
    result = v13;
    if ( v13 == (__int64 *)&v13 )
      break;
    if ( (__int64 **)v13[1] != &v13 )
      goto LABEL_16;
    v11 = (__int64 *)*v13;
    if ( *(__int64 **)(*v13 + 8) != v13 )
      goto LABEL_16;
    v13 = (__int64 *)*v13;
    v11[1] = (__int64)&v13;
    v12 = (IRP *)(result - 21);
    *((_DWORD *)result - 30) = a2;
    if ( *(_BYTE *)(a1 + 380) )
      PoSetSystemWake((PIRP)(result - 21));
    IofCompleteRequest(v12, 0);
  }
  *(_BYTE *)(a1 + 380) = 0;
  return result;
}

```

## disassembly

```asm
0x180013a14  push    rbp
0x180013a16  push    rbx
0x180013a17  push    rsi
0x180013a18  push    rdi
0x180013a19  mov     rbp, rsp
0x180013a1c  sub     rsp, 38h
0x180013a20  lea     rax, [rbp+var_18]
0x180013a24  mov     rdi, rcx
0x180013a27  mov     [rbp+var_10], rax
0x180013a2b  lea     rbx, [rcx+1E8h]
0x180013a32  lea     rax, [rbp+var_18]
0x180013a36  mov     rcx, rbx; SpinLock
0x180013a39  mov     [rbp+var_18], rax
0x180013a3d  mov     esi, edx
0x180013a3f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180013a46  nop     dword ptr [rax+rax+00h]
0x180013a4b  mov     r9b, al
0x180013a4e  lea     r8, [rdi+1D8h]
0x180013a55  mov     rcx, [r8]
0x180013a58  cmp     rcx, r8
0x180013a5b  jz      short loc_180013AC7
0x180013a5d  cmp     [rcx+8], r8
0x180013a61  jnz     loc_180013B3C
0x180013a67  mov     rax, [rcx]
0x180013a6a  cmp     [rax+8], rcx
0x180013a6e  jnz     loc_180013B3C
0x180013a74  mov     [r8], rax
0x180013a77  mov     [rax+8], r8
0x180013a7b  xor     eax, eax
0x180013a7d  mov     [rcx+8], rcx
0x180013a81  mov     [rcx], rcx
0x180013a84  xchg    rax, [rcx-40h]
0x180013a88  test    rax, rax
0x180013a8b  jz      short loc_180013A55
0x180013a8d  mov     rax, [rbp+var_10]
0x180013a91  lea     rdx, [rbp+var_18]
0x180013a95  cmp     [rax], rdx
0x180013a98  jnz     loc_180013B3C
0x180013a9e  mov     [rcx+8], rax
0x180013aa2  lea     rdx, [rbp+var_18]
0x180013aa6  mov     [rcx], rdx
0x180013aa9  mov     [rax], rcx
0x180013aac  mov     [rbp+var_10], rcx
0x180013ab0  mov     rax, [rcx+10h]
0x180013ab4  mov     rcx, [rax+28h]
0x180013ab8  xor     eax, eax
0x180013aba  mov     rdx, [rcx+40h]
0x180013abe  xchg    rax, [rdx+90h]
0x180013ac5  jmp     short loc_180013A55
0x180013ac7  mov     dl, r9b; NewIrql
0x180013aca  mov     rcx, rbx; SpinLock
0x180013acd  call    cs:__imp_KeReleaseSpinLock
0x180013ad4  nop     dword ptr [rax+rax+00h]
0x180013ad9  mov     rax, [rbp+var_18]
0x180013add  lea     rcx, [rbp+var_18]
0x180013ae1  cmp     rax, rcx
0x180013ae4  jz      short loc_180013B2B
0x180013ae6  lea     rcx, [rbp+var_18]
0x180013aea  cmp     [rax+8], rcx
0x180013aee  jnz     short loc_180013B3C
0x180013af0  mov     rcx, [rax]
0x180013af3  cmp     [rcx+8], rax
0x180013af7  jnz     short loc_180013B3C
0x180013af9  mov     [rbp+var_18], rcx
0x180013afd  lea     rdx, [rbp+var_18]
0x180013b01  mov     [rcx+8], rdx
0x180013b05  lea     rbx, [rax-0A8h]
0x180013b0c  mov     [rbx+30h], esi
0x180013b0f  cmp     byte ptr [rdi+17Ch], 0
0x180013b16  jnz     short loc_180013B43
0x180013b18  xor     edx, edx; PriorityBoost
0x180013b1a  mov     rcx, rbx; Irp
0x180013b1d  call    cs:__imp_IofCompleteRequest
0x180013b24  nop     dword ptr [rax+rax+00h]
0x180013b29  jmp     short loc_180013AD9
0x180013b2b  mov     byte ptr [rdi+17Ch], 0
0x180013b32  add     rsp, 38h
0x180013b36  pop     rdi
0x180013b37  pop     rsi
0x180013b38  pop     rbx
0x180013b39  pop     rbp
0x180013b3a  retn
0x180013b3c  mov     ecx, 3
0x180013b41  int     29h; Win8: RtlFailFast(ecx)
0x180013b43  mov     rcx, rbx; Irp
0x180013b46  call    cs:__imp_PoSetSystemWake
0x180013b4d  nop     dword ptr [rax+rax+00h]
0x180013b52  jmp     short loc_180013B18
```
