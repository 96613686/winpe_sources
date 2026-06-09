# NbtDereferenceClient

- ea: `0x140003d04`
- end: `0x140004030`
- name: `NbtDereferenceClient`
- size: `812`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `8`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140001e64`
- `0x1400031bc`
- `0x140004cb0`
- `0x14000508c`
- `0x140010c90`
- `0x14001c600`
- `0x1400226d0`
- `0x14004d028`

## callees

- `0x140001938`
- `0x140003d04`
- `0x140004038`
- `0x140004880`
- `0x140005fb0`
- `0x140030f80`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140003f6c`
- `ntoskrnl!KeCancelTimer` at `0x140003f6c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003d35`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003d71`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003d35`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003d71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003dbf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003dfe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003ec0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003f12`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003dbf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003dfe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003ec0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003f12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003e5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003e5b`

## pseudocode

```c
void __fastcall NbtDereferenceClient(PVOID P, int a2, __int64 a3)
{
  KIRQL v4; // al
  KIRQL v5; // r12
  __int64 v6; // r13
  __int64 v7; // r14
  __int64 v8; // rsi
  KIRQL v9; // al
  _QWORD *v10; // rcx
  KIRQL v11; // dl
  PVOID *v12; // rax
  _QWORD *v13; // rax
  __int64 v14; // rdi
  void (__fastcall *v15)(__int64, __int64); // rbp
  __int64 v16; // r15
  char *v17; // rdx
  __int64 v18; // rax
  char v19; // al
  bool v20; // zf
  void (__fastcall *v21)(__int64, __int64, _QWORD); // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  char v24; // [rsp+80h] [rbp+8h]
  IRP *Irp; // [rsp+98h] [rbp+20h]

  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      (__int64)P,
      0x4Fu,
      (ULONGLONG)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
      P,
      *((_DWORD *)P + 5),
      *((_DWORD *)P + 5) - 1,
      a2,
      a3);
  v4 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v5 = v4;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 5, 0xFFFFFFFF) == 1 )
  {
    v6 = *((_QWORD *)P + 5);
    v7 = *((_QWORD *)P + 4);
    Irp = (IRP *)*((_QWORD *)P + 3);
    v8 = *(_QWORD *)(v6 + 40);
    v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 56));
    v10 = *(_QWORD **)P;
    v11 = v9;
    if ( *(PVOID *)(*(_QWORD *)P + 8LL) != P || (v12 = (PVOID *)*((_QWORD *)P + 1), *v12 != P) )
      __fastfail(3u);
    *v12 = v10;
    v10[1] = v12;
    v13 = (_QWORD *)(v6 + 24);
    v24 = 1;
    while ( 1 )
    {
      v13 = (_QWORD *)*v13;
      if ( v13 == (_QWORD *)(v6 + 24) )
        break;
      if ( v13[4] == v7 )
      {
        v24 = 0;
        break;
      }
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 56), v11);
    if ( v8 )
    {
      v14 = *(_QWORD *)(v8 + 112);
      v15 = 0;
      v16 = 0;
      if ( v14 )
      {
        v18 = *(_QWORD *)(v14 + 48);
        if ( v18 )
        {
          if ( *(_QWORD *)(v18 + 32) == v7 )
          {
            *(_QWORD *)(v8 + 112) = 0;
            v19 = *(_BYTE *)(v14 + 23);
            if ( v19 == 1 )
            {
              v20 = (*(_BYTE *)(v14 + 256) & 8) == 0;
              v15 = *(void (__fastcall **)(__int64, __int64))(v14 + 72);
              v16 = *(_QWORD *)(v14 + 64);
              *(_QWORD *)(v14 + 72) = 0;
              if ( v20 && !KeCancelTimer((PKTIMER)(v14 + 192)) )
              {
                v21 = *(void (__fastcall **)(__int64, __int64, _QWORD))(v14 + 40);
                if ( v21 )
                {
                  v22 = *(_QWORD *)(v14 + 56);
                  v23 = *(_QWORD *)(v14 + 48);
                  *(_QWORD *)(v14 + 40) = 0;
                  v21(v23, v22, 0);
                }
                *(_BYTE *)(v14 + 23) = 2;
              }
              else
              {
                CleanupCTETimer((_QWORD *)v14);
              }
            }
            else if ( v19 == 2 )
            {
              v15 = *(void (__fastcall **)(__int64, __int64))(v14 + 72);
              if ( v15 )
              {
                v16 = *(_QWORD *)(v14 + 64);
                *(_QWORD *)(v14 + 72) = 0;
              }
              *(_BYTE *)(v14 + 23) = 3;
            }
          }
        }
      }
      if ( v24 )
      {
        if ( *(_DWORD *)(v7 + 340) == 1 )
        {
          *(_DWORD *)(v8 + 160) &= ~1u;
        }
        else
        {
          *(_QWORD *)(v8 + 80) &= ~*(_QWORD *)(v7 + 560);
          *(_QWORD *)(v8 + 104) &= ~*(_QWORD *)(v7 + 560);
          *(_QWORD *)(v8 + 96) |= *(_QWORD *)(v7 + 560);
        }
      }
      KeReleaseSpinLock(&SpinLock, v5);
      v17 = (char *)(v8 + 164);
      if ( *(_BYTE *)(v8 + 164) != 42 && *(_BYTE *)(v8 + 179) == 32 )
      {
        --*(_DWORD *)(v7 + 904);
        CheckSetWakeupPattern(v7, v17, 0, 0);
      }
      if ( v15 )
        v15(v16, 258);
    }
    else
    {
      KeReleaseSpinLock(&SpinLock, v5);
    }
    NbtDereferenceAddress(v6, (__int64)v17, 238, (__int64)"minio\\netbt\\sys\\name.c");
    if ( Irp )
      NTIoComplete(Irp, 0, 0);
    *((_DWORD *)P + 4) += 10;
    ExFreePoolWithTag(P, 0);
  }
  else
  {
    KeReleaseSpinLock(&SpinLock, v4);
  }
}

```

## disassembly

```asm
0x140003d04  mov     [rsp+arg_8], rbx
0x140003d09  push    rbp
0x140003d0a  push    rsi
0x140003d0b  push    rdi
0x140003d0c  push    r12
0x140003d0e  push    r13
0x140003d10  push    r14
0x140003d12  push    r15
0x140003d14  sub     rsp, 40h
0x140003d18  mov     r10d, edx
0x140003d1b  mov     rbx, rcx
0x140003d1e  test    byte ptr cs:xmmword_140038420+9, 40h
0x140003d25  jnz     loc_140003FB4
0x140003d2b  lea     rbp, SpinLock
0x140003d32  mov     rcx, rbp; SpinLock
0x140003d35  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003d3c  nop     dword ptr [rax+rax+00h]
0x140003d41  mov     r12b, al
0x140003d44  or      edx, 0FFFFFFFFh
0x140003d47  lock xadd [rbx+14h], edx
0x140003d4c  cmp     edx, 1
0x140003d4f  jnz     loc_140003EBA
0x140003d55  mov     r13, [rbx+28h]
0x140003d59  mov     rax, [rbx+18h]
0x140003d5d  mov     r14, [rbx+20h]
0x140003d61  mov     [rsp+78h+Irp], rax
0x140003d69  mov     rsi, [r13+28h]
0x140003d6d  lea     rcx, [r13+38h]; SpinLock
0x140003d71  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003d78  nop     dword ptr [rax+rax+00h]
0x140003d7d  mov     rcx, [rbx]
0x140003d80  mov     dl, al; NewIrql
0x140003d82  cmp     [rcx+8], rbx
0x140003d86  jnz     loc_140003F23
0x140003d8c  mov     rax, [rbx+8]
0x140003d90  cmp     [rax], rbx
0x140003d93  jnz     loc_140003F23
0x140003d99  mov     [rax], rcx
0x140003d9c  mov     [rcx+8], rax
0x140003da0  lea     rcx, [r13+18h]
0x140003da4  mov     rax, rcx
0x140003da7  mov     [rsp+78h+arg_0], 1
0x140003daf  mov     rax, [rax]
0x140003db2  cmp     rax, rcx
0x140003db5  jnz     loc_140003EF5
0x140003dbb  lea     rcx, [r13+38h]; SpinLock
0x140003dbf  call    cs:__imp_KeReleaseSpinLock
0x140003dc6  nop     dword ptr [rax+rax+00h]
0x140003dcb  test    rsi, rsi
0x140003dce  jz      loc_140003F0C
0x140003dd4  mov     rdi, [rsi+70h]
0x140003dd8  xor     ebp, ebp
0x140003dda  xor     r15d, r15d
0x140003ddd  test    rdi, rdi
0x140003de0  jnz     loc_140003F2A
0x140003de6  cmp     [rsp+78h+arg_0], 0
0x140003dee  jnz     loc_140003E80
0x140003df4  mov     dl, r12b; NewIrql
0x140003df7  lea     rcx, SpinLock; SpinLock
0x140003dfe  call    cs:__imp_KeReleaseSpinLock
0x140003e05  nop     dword ptr [rax+rax+00h]
0x140003e0a  lea     rdx, [rsi+0A4h]
0x140003e11  cmp     byte ptr [rdx], 2Ah ; '*'
0x140003e14  jnz     loc_140003ECE
0x140003e1a  test    rbp, rbp
0x140003e1d  jnz     loc_14000401B
0x140003e23  lea     r9, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x140003e2a  mov     r8d, 2DEEh
0x140003e30  mov     rcx, r13
0x140003e33  call    NbtDereferenceAddress
0x140003e38  mov     rax, [rsp+78h+Irp]
0x140003e40  test    rax, rax
0x140003e43  jz      short loc_140003E52
0x140003e45  xor     r8d, r8d
0x140003e48  xor     edx, edx
0x140003e4a  mov     rcx, rax; Irp
0x140003e4d  call    NTIoComplete
0x140003e52  add     dword ptr [rbx+10h], 0Ah
0x140003e56  xor     edx, edx; Tag
0x140003e58  mov     rcx, rbx; P
0x140003e5b  call    cs:__imp_ExFreePoolWithTag
0x140003e62  nop     dword ptr [rax+rax+00h]
0x140003e67  mov     rbx, [rsp+78h+arg_8]
0x140003e6f  add     rsp, 40h
0x140003e73  pop     r15
0x140003e75  pop     r14
0x140003e77  pop     r13
0x140003e79  pop     r12
0x140003e7b  pop     rdi
0x140003e7c  pop     rsi
0x140003e7d  pop     rbp
0x140003e7e  retn
0x140003e80  cmp     dword ptr [r14+154h], 1
0x140003e88  jz      loc_140003FA8
0x140003e8e  mov     rax, [r14+230h]
0x140003e95  not     rax
0x140003e98  and     [rsi+50h], rax
0x140003e9c  mov     rax, [r14+230h]
0x140003ea3  not     rax
0x140003ea6  and     [rsi+68h], rax
0x140003eaa  mov     rax, [r14+230h]
0x140003eb1  or      [rsi+60h], rax
0x140003eb5  jmp     loc_140003DF4
0x140003eba  mov     dl, r12b; NewIrql
0x140003ebd  mov     rcx, rbp; SpinLock
0x140003ec0  call    cs:__imp_KeReleaseSpinLock
0x140003ec7  nop     dword ptr [rax+rax+00h]
0x140003ecc  jmp     short loc_140003E67
0x140003ece  cmp     byte ptr [rsi+0B3h], 20h ; ' '
0x140003ed5  jnz     loc_140003E1A
0x140003edb  dec     dword ptr [r14+388h]
0x140003ee2  xor     r9d, r9d
0x140003ee5  xor     r8d, r8d
0x140003ee8  mov     rcx, r14
0x140003eeb  call    CheckSetWakeupPattern
0x140003ef0  jmp     loc_140003E1A
0x140003ef5  cmp     [rax+20h], r14
0x140003ef9  jnz     loc_140003DAF
0x140003eff  mov     [rsp+78h+arg_0], 0
0x140003f07  jmp     loc_140003DBB
0x140003f0c  mov     dl, r12b; NewIrql
0x140003f0f  mov     rcx, rbp; SpinLock
0x140003f12  call    cs:__imp_KeReleaseSpinLock
0x140003f19  nop     dword ptr [rax+rax+00h]
0x140003f1e  jmp     loc_140003E23
0x140003f23  mov     ecx, 3
0x140003f28  int     29h; Win8: RtlFailFast(ecx)
0x140003f2a  mov     rax, [rdi+30h]
0x140003f2e  test    rax, rax
0x140003f31  jz      loc_140003DE6
0x140003f37  cmp     [rax+20h], r14
0x140003f3b  jnz     loc_140003DE6
0x140003f41  mov     [rsi+70h], rbp
0x140003f45  mov     al, [rdi+17h]
0x140003f48  cmp     al, 1
0x140003f4a  jnz     short loc_140003F89
0x140003f4c  test    byte ptr [rdi+100h], 8
0x140003f53  mov     rbp, [rdi+48h]
0x140003f57  mov     r15, [rdi+40h]
0x140003f5b  mov     qword ptr [rdi+48h], 0
0x140003f63  jnz     short loc_140003F7C
0x140003f65  lea     rcx, [rdi+0C0h]; PKTIMER
0x140003f6c  call    cs:__imp_KeCancelTimer
0x140003f73  nop     dword ptr [rax+rax+00h]
0x140003f78  test    al, al
0x140003f7a  jz      short loc_140003FE8
0x140003f7c  mov     rcx, rdi; Entry
0x140003f7f  call    CleanupCTETimer
0x140003f84  jmp     loc_140003DE6
0x140003f89  cmp     al, 2
0x140003f8b  jnz     loc_140003DE6
0x140003f91  mov     rbp, [rdi+48h]
0x140003f95  test    rbp, rbp
0x140003f98  jz      short loc_140004012
0x140003f9a  mov     r15, [rdi+40h]
0x140003f9e  mov     qword ptr [rdi+48h], 0
0x140003fa6  jmp     short loc_140004012
0x140003fa8  and     dword ptr [rsi+0A0h], 0FFFFFFFEh
0x140003faf  jmp     loc_140003DF4
0x140003fb4  mov     r9d, [rcx+14h]
0x140003fb8  mov     edx, 4Fh ; 'O'
0x140003fbd  mov     [rsp+78h+var_40], r8
0x140003fc2  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x140003fc9  mov     [rsp+78h+var_48], r10d
0x140003fce  lea     eax, [r9-1]
0x140003fd2  mov     [rsp+78h+var_50], eax
0x140003fd6  mov     [rsp+78h+var_58], r9d
0x140003fdb  mov     r9, rbx
0x140003fde  call    WPP_SF_qddds
0x140003fe3  jmp     loc_140003D2B
0x140003fe8  mov     rax, [rdi+28h]
0x140003fec  test    rax, rax
0x140003fef  jz      short loc_140004009
0x140003ff1  mov     rdx, [rdi+38h]
0x140003ff5  xor     r8d, r8d
0x140003ff8  mov     rcx, [rdi+30h]
0x140003ffc  mov     qword ptr [rdi+28h], 0
0x140004004  call    _guard_dispatch_icall
0x140004009  mov     byte ptr [rdi+17h], 2
0x14000400d  jmp     loc_140003DE6
0x140004012  mov     byte ptr [rdi+17h], 3
0x140004016  jmp     loc_140003DE6
0x14000401b  mov     edx, 102h
0x140004020  mov     rcx, r15
0x140004023  mov     rax, rbp
0x140004026  call    _guard_dispatch_icall
0x14000402b  jmp     loc_140003E23
```
