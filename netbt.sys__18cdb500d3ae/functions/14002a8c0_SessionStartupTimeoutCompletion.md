# SessionStartupTimeoutCompletion

- ea: `0x14002a8c0`
- end: `0x14002ab77`
- name: `SessionStartupTimeoutCompletion`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140024db0`

## callees

- `0x140004880`
- `0x140007ed8`
- `0x14000b810`
- `0x140010988`
- `0x140011998`
- `0x140025078`
- `0x14002a8c0`
- `0x140040214`
- `0x14004102c`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a908`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a97f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a995`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a908`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a97f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002a995`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002aa32`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002aa54`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002aaf3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ab2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ab3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ab52`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002aa32`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002aa54`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002aaf3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ab2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ab3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ab52`

## pseudocode

```c
void __fastcall SessionStartupTimeoutCompletion(__int64 a1, NTSTATUS a2)
{
  KIRQL v4; // al
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rbx
  KIRQL v8; // si
  __int64 v9; // rbp
  KIRQL v10; // r13
  KIRQL v11; // al
  IRP *v12; // rcx
  int v13; // eax
  _DWORD *v14; // rcx
  int v15; // edx
  KIRQL NewIrql; // [rsp+80h] [rbp+8h]
  KIRQL v17; // [rsp+90h] [rbp+18h]
  IRP *Irp; // [rsp+98h] [rbp+20h]

  if ( (BYTE2(xmmword_140038420) & 8) != 0 )
    WPP_SF_qD(1043, 61, WPP_8017b60c53a232e581eda6237e04704c_Traceguids, a1, a2);
  v4 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v7 = *(_QWORD *)(a1 + 96);
  v8 = v4;
  NewIrql = v4;
  *(_QWORD *)(a1 + 152) = 0;
  if ( !v7 )
    goto LABEL_21;
  v9 = *(_QWORD *)(v7 + 24);
  if ( !v9 || a1 != *(_QWORD *)(v7 + 184) )
    goto LABEL_21;
  if ( (BYTE2(xmmword_140038420) & 8) != 0 )
    WPP_SF_qdqq(v5, 62, v6, a1, a2, v7, *(_QWORD *)(v7 + 24));
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 248));
  v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v9 + 104));
  v17 = v11;
  if ( *(_DWORD *)(v7 + 48) != 6 || (v12 = *(IRP **)(v7 + 152), (Irp = v12) == 0) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v9 + 104), v11);
    KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 248), v10);
LABEL_21:
    KeReleaseSpinLock(&SpinLock, v8);
    return;
  }
  *(_DWORD *)(v7 + 48) = 1;
  *(_QWORD *)(v7 + 152) = 0;
  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
  {
    WPP_SF_qddds(
      (_DWORD)v12,
      10,
      (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
      v7,
      *(_DWORD *)(v7 + 20),
      *(_DWORD *)(v7 + 20) + 1,
      202,
      (__int64)"minio\\netbt\\sys\\name.c");
    v11 = v17;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v7 + 20));
  *(_QWORD *)(v9 + 24) = 0;
  *(_BYTE *)(v9 + 124) = 11;
  KeReleaseSpinLock((PKSPIN_LOCK)(v9 + 104), v11);
  QueueCleanup((PVOID)v7);
  KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 248), v10);
  RelistConnection(v7);
  v13 = *(_DWORD *)(a1 + 136);
  if ( v13 )
  {
    *(_DWORD *)(a1 + 136) = v13 - 1;
  }
  else
  {
    v14 = *(_DWORD **)(a1 + 48);
    if ( v14[4] == -87097344 && (v14[18] & 0x10) != 0 && v14[5] == 2 )
      NbtDereferenceName(v14, (__int64)"minio\\netbt\\sys\\name.c");
    NbtDereferenceName(*(PVOID *)(a1 + 48), (__int64)"minio\\netbt\\sys\\name.c");
    FreeTracker(a1, 5);
  }
  *(_QWORD *)(v7 + 184) = 0;
  KeReleaseSpinLock(&SpinLock, NewIrql);
  NbtDereferenceConnection((PVOID)v7, v15, 2, (__int64)"minio\\netbt\\sys\\name.c");
  NTIoComplete(Irp, a2, 0);
}

```

## disassembly

```asm
0x14002a8c0  mov     [rsp+arg_8], rbx
0x14002a8c5  push    rbp
0x14002a8c6  push    rsi
0x14002a8c7  push    rdi
0x14002a8c8  push    r12
0x14002a8ca  push    r13
0x14002a8cc  push    r14
0x14002a8ce  push    r15
0x14002a8d0  sub     rsp, 40h
0x14002a8d4  mov     r14d, edx
0x14002a8d7  mov     rdi, rcx
0x14002a8da  test    byte ptr cs:xmmword_140038420+2, 8
0x14002a8e1  jz      short loc_14002A901
0x14002a8e3  mov     edx, 3Dh ; '='
0x14002a8e8  mov     dword ptr [rsp+78h+var_58], r14d
0x14002a8ed  mov     ecx, 413h
0x14002a8f2  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x14002a8f9  mov     r9, rdi
0x14002a8fc  call    WPP_SF_qD
0x14002a901  lea     rcx, SpinLock; SpinLock
0x14002a908  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002a90f  nop     dword ptr [rax+rax+00h]
0x14002a914  mov     rbx, [rdi+60h]
0x14002a918  mov     sil, al
0x14002a91b  mov     [rsp+78h+NewIrql], al
0x14002a922  mov     qword ptr [rdi+98h], 0
0x14002a92d  test    rbx, rbx
0x14002a930  jz      loc_14002AB48
0x14002a936  mov     rbp, [rbx+18h]
0x14002a93a  test    rbp, rbp
0x14002a93d  jz      loc_14002AB48
0x14002a943  cmp     rdi, [rbx+0B8h]
0x14002a94a  jnz     loc_14002AB48
0x14002a950  test    byte ptr cs:xmmword_140038420+2, 8
0x14002a957  jz      short loc_14002A975
0x14002a959  mov     [rsp+78h+var_48], rbp
0x14002a95e  mov     edx, 3Eh ; '>'
0x14002a963  mov     [rsp+78h+var_50], rbx
0x14002a968  mov     r9, rdi
0x14002a96b  mov     dword ptr [rsp+78h+var_58], r14d
0x14002a970  call    WPP_SF_qdqq
0x14002a975  lea     r15, [rbx+0F8h]
0x14002a97c  mov     rcx, r15; SpinLock
0x14002a97f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002a986  nop     dword ptr [rax+rax+00h]
0x14002a98b  lea     r12, [rbp+68h]
0x14002a98f  mov     r13b, al
0x14002a992  mov     rcx, r12; SpinLock
0x14002a995  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002a99c  nop     dword ptr [rax+rax+00h]
0x14002a9a1  cmp     dword ptr [rbx+30h], 6
0x14002a9a5  mov     [rsp+78h+arg_10], al
0x14002a9ac  jnz     loc_14002AB25
0x14002a9b2  mov     rcx, [rbx+98h]
0x14002a9b9  mov     [rsp+78h+Irp], rcx
0x14002a9c1  test    rcx, rcx
0x14002a9c4  jz      loc_14002AB25
0x14002a9ca  xor     esi, esi
0x14002a9cc  mov     dword ptr [rbx+30h], 1
0x14002a9d3  mov     [rbx+98h], rsi
0x14002a9da  test    byte ptr cs:xmmword_140038420+9, 40h
0x14002a9e1  lea     r9, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x14002a9e8  jz      short loc_14002AA21
0x14002a9ea  mov     r8d, [rbx+14h]
0x14002a9ee  lea     edx, [rsi+0Ah]
0x14002a9f1  mov     [rsp+78h+var_40], r9
0x14002a9f6  mov     r9, rbx
0x14002a9f9  mov     dword ptr [rsp+78h+var_48], 17CAh
0x14002aa01  lea     eax, [r8+1]
0x14002aa05  mov     dword ptr [rsp+78h+var_50], eax
0x14002aa09  mov     dword ptr [rsp+78h+var_58], r8d
0x14002aa0e  lea     r8, WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids
0x14002aa15  call    WPP_SF_qddds
0x14002aa1a  mov     al, [rsp+78h+arg_10]
0x14002aa21  lock inc dword ptr [rbx+14h]
0x14002aa25  mov     dl, al; NewIrql
0x14002aa27  mov     [rbp+18h], rsi
0x14002aa2b  mov     rcx, r12; SpinLock
0x14002aa2e  mov     byte ptr [rbp+7Ch], 0Bh
0x14002aa32  call    cs:__imp_KeReleaseSpinLock
0x14002aa39  nop     dword ptr [rax+rax+00h]
0x14002aa3e  lea     rdx, [rsp+78h+NewIrql]
0x14002aa46  mov     rcx, rbx; P
0x14002aa49  call    QueueCleanup
0x14002aa4e  mov     dl, r13b; NewIrql
0x14002aa51  mov     rcx, r15; SpinLock
0x14002aa54  call    cs:__imp_KeReleaseSpinLock
0x14002aa5b  nop     dword ptr [rax+rax+00h]
0x14002aa60  mov     rcx, rbx
0x14002aa63  call    RelistConnection
0x14002aa68  mov     eax, [rdi+88h]
0x14002aa6e  lea     rbp, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x14002aa75  test    eax, eax
0x14002aa77  jnz     short loc_14002AAD6
0x14002aa79  mov     rcx, [rdi+30h]; P
0x14002aa7d  cmp     dword ptr [rcx+10h], 0FACF0000h
0x14002aa84  jnz     short loc_14002AAAB
0x14002aa86  mov     eax, [rcx+48h]
0x14002aa89  test    al, 10h
0x14002aa8b  jz      short loc_14002AAAB
0x14002aa8d  cmp     dword ptr [rcx+14h], 2
0x14002aa91  jnz     short loc_14002AAAB
0x14002aa93  mov     r9d, 17EBh
0x14002aa99  mov     [rsp+78h+var_58], rbp; __int64
0x14002aa9e  mov     r8b, 1
0x14002aaa1  mov     edx, 1
0x14002aaa6  call    NbtDereferenceName
0x14002aaab  mov     rcx, [rdi+30h]; P
0x14002aaaf  mov     r9d, 17F2h
0x14002aab5  mov     r8b, 1
0x14002aab8  mov     [rsp+78h+var_58], rbp; __int64
0x14002aabd  mov     edx, 9
0x14002aac2  call    NbtDereferenceName
0x14002aac7  mov     edx, 5
0x14002aacc  mov     rcx, rdi
0x14002aacf  call    FreeTracker
0x14002aad4  jmp     short loc_14002AADE
0x14002aad6  dec     eax
0x14002aad8  mov     [rdi+88h], eax
0x14002aade  mov     dl, [rsp+78h+NewIrql]; NewIrql
0x14002aae5  lea     rcx, SpinLock; SpinLock
0x14002aaec  mov     [rbx+0B8h], rsi
0x14002aaf3  call    cs:__imp_KeReleaseSpinLock
0x14002aafa  nop     dword ptr [rax+rax+00h]
0x14002aaff  mov     r9, rbp
0x14002ab02  mov     r8d, 1802h
0x14002ab08  mov     rcx, rbx; P
0x14002ab0b  call    NbtDereferenceConnection
0x14002ab10  mov     rcx, [rsp+78h+Irp]; Irp
0x14002ab18  xor     r8d, r8d
0x14002ab1b  mov     edx, r14d
0x14002ab1e  call    NTIoComplete
0x14002ab23  jmp     short loc_14002AB5E
0x14002ab25  mov     dl, al; NewIrql
0x14002ab27  mov     rcx, r12; SpinLock
0x14002ab2a  call    cs:__imp_KeReleaseSpinLock
0x14002ab31  nop     dword ptr [rax+rax+00h]
0x14002ab36  mov     dl, r13b; NewIrql
0x14002ab39  mov     rcx, r15; SpinLock
0x14002ab3c  call    cs:__imp_KeReleaseSpinLock
0x14002ab43  nop     dword ptr [rax+rax+00h]
0x14002ab48  mov     dl, sil; NewIrql
0x14002ab4b  lea     rcx, SpinLock; SpinLock
0x14002ab52  call    cs:__imp_KeReleaseSpinLock
0x14002ab59  nop     dword ptr [rax+rax+00h]
0x14002ab5e  mov     rbx, [rsp+78h+arg_8]
0x14002ab66  add     rsp, 40h
0x14002ab6a  pop     r15
0x14002ab6c  pop     r14
0x14002ab6e  pop     r13
0x14002ab70  pop     r12
0x14002ab72  pop     rdi
0x14002ab73  pop     rsi
0x14002ab74  pop     rbp
0x14002ab75  retn
```
