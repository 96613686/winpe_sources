# NbtDereferenceConnection

- ea: `0x140010988`
- end: `0x140010be2`
- name: `NbtDereferenceConnection`
- size: `602`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `20`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400010f0`
- `0x14000efd4`
- `0x1400103e8`
- `0x1400104d8`
- `0x140010680`
- `0x140010c90`
- `0x140011998`
- `0x14001212c`
- `0x1400133c0`
- `0x140014610`
- `0x1400182a0`
- `0x140018ea0`
- `0x14001e8f4`
- `0x14001f310`
- `0x140020900`
- `0x140025260`
- `0x140027c20`
- `0x140029d28`
- `0x14002a8c0`
- `0x14004cf5c`

## callees

- `0x140010988`
- `0x140010be8`
- `0x140013184`
- `0x140041e1c`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140010af2`
- `ntoskrnl!IofCompleteRequest` at `0x140010af2`
- `ntoskrnl!IoFreeMdl` at `0x1400109d9`
- `ntoskrnl!IoFreeMdl` at `0x1400109d9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140010ae1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140010ae1`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140010ac8`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140010ac8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400109b2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010a2c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010a45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400109b2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010a2c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010a45`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010a19`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010a6d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010a83`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010b12`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010a19`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010a6d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010a83`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010b12`

## pseudocode

```c
void __fastcall NbtDereferenceConnection(PVOID P, int a2, char a3, __int64 a4)
{
  KIRQL v5; // al
  KIRQL v6; // bp
  __int64 v7; // rbx
  __int64 v8; // r14
  KIRQL v9; // bp
  KIRQL v10; // al
  int v11; // r8d
  unsigned int v12; // edx
  KIRQL v13; // r15
  __int64 v14; // rdx
  __int64 *v15; // rcx
  __int64 v16; // rax
  int Irql; // [rsp+88h] [rbp+10h] BYREF

  Irql = a2;
  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      (_DWORD)P,
      82,
      (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
      (_DWORD)P,
      *((_DWORD *)P + 5),
      *((_DWORD *)P + 5) - 1,
      a3,
      a4);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 31);
  v6 = v5;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 5, 0xFFFFFFFF) == 1 )
  {
    IoFreeMdl(*((PMDL *)P + 28));
    v7 = *((_QWORD *)P + 20);
    *((_QWORD *)P + 28) = 0;
    if ( v7 )
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 184) + 48LL) + 24LL) = 0;
    v8 = *((_QWORD *)P + 4);
    KeReleaseSpinLock((PKSPIN_LOCK)P + 31, v6);
    v9 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 848));
    v12 = *(_DWORD *)(v8 + 896);
    v13 = v10;
    if ( v12 > dword_140039698 && v12 > *(_DWORD *)(v8 + 900) >> 1 )
    {
      v14 = *((_QWORD *)P + 4) + 416LL;
      v15 = *(__int64 **)v14;
      if ( *(_QWORD *)(*(_QWORD *)v14 + 8LL) != v14 || (v16 = *v15, *(__int64 **)(*v15 + 8) != v15) )
        __fastfail(3u);
      *(_QWORD *)v14 = v16;
      *(_QWORD *)(v16 + 8) = v14;
      _InterlockedDecrement((volatile signed __int32 *)(v8 + 896));
      NbtDereferenceLowerConnection((_DWORD)v15, v14, v11, 12299, (__int64)"minio\\netbt\\sys\\name.c");
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 848), v13);
    KeReleaseSpinLock(&SpinLock, v9);
    FreeConnectionObj(P);
    if ( v7 )
    {
      LOBYTE(Irql) = 0;
      *(_DWORD *)(v7 + 48) = 0;
      *(_QWORD *)(v7 + 56) = 0;
      if ( SBYTE2(xmmword_140038420) < 0 )
        WPP_SF_qdd(1047, 70, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, v7, 0, 0);
      IoAcquireCancelSpinLock((PKIRQL)&Irql);
      _InterlockedExchange64((volatile __int64 *)(v7 + 104), 0);
      IoReleaseCancelSpinLock(Irql);
      IofCompleteRequest((PIRP)v7, 2);
    }
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)P + 31, v5);
  }
}

```

## disassembly

```asm
0x140010988  mov     [rsp+Irql], edx
0x14001098c  push    rbx
0x14001098d  push    rbp
0x14001098e  push    rsi
0x14001098f  push    rdi
0x140010990  push    r14
0x140010992  push    r15
0x140010994  sub     rsp, 48h
0x140010998  mov     rdi, rcx
0x14001099b  test    byte ptr cs:xmmword_140038420+9, 40h
0x1400109a2  jnz     loc_140010B80
0x1400109a8  lea     rsi, [rdi+0F8h]
0x1400109af  mov     rcx, rsi; SpinLock
0x1400109b2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400109b9  nop     dword ptr [rax+rax+00h]
0x1400109be  mov     bpl, al
0x1400109c1  or      edx, 0FFFFFFFFh
0x1400109c4  lock xadd [rdi+14h], edx
0x1400109c9  cmp     edx, 1
0x1400109cc  jnz     loc_140010B0C
0x1400109d2  mov     rcx, [rdi+0E0h]; Mdl
0x1400109d9  call    cs:__imp_IoFreeMdl
0x1400109e0  nop     dword ptr [rax+rax+00h]
0x1400109e5  mov     rbx, [rdi+0A0h]
0x1400109ec  mov     qword ptr [rdi+0E0h], 0
0x1400109f7  test    rbx, rbx
0x1400109fa  jz      short loc_140010A0F
0x1400109fc  mov     rax, [rbx+0B8h]
0x140010a03  mov     rcx, [rax+30h]
0x140010a07  mov     qword ptr [rcx+18h], 0
0x140010a0f  mov     r14, [rdi+20h]
0x140010a13  mov     dl, bpl; NewIrql
0x140010a16  mov     rcx, rsi; SpinLock
0x140010a19  call    cs:__imp_KeReleaseSpinLock
0x140010a20  nop     dword ptr [rax+rax+00h]
0x140010a25  lea     rcx, SpinLock; SpinLock
0x140010a2c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010a33  nop     dword ptr [rax+rax+00h]
0x140010a38  lea     rsi, [r14+350h]
0x140010a3f  mov     bpl, al
0x140010a42  mov     rcx, rsi; SpinLock
0x140010a45  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010a4c  nop     dword ptr [rax+rax+00h]
0x140010a51  mov     edx, [r14+380h]
0x140010a58  mov     r15b, al
0x140010a5b  cmp     edx, cs:dword_140039698
0x140010a61  ja      loc_140010B20
0x140010a67  mov     dl, r15b; NewIrql
0x140010a6a  mov     rcx, rsi; SpinLock
0x140010a6d  call    cs:__imp_KeReleaseSpinLock
0x140010a74  nop     dword ptr [rax+rax+00h]
0x140010a79  mov     dl, bpl; NewIrql
0x140010a7c  lea     rcx, SpinLock; SpinLock
0x140010a83  call    cs:__imp_KeReleaseSpinLock
0x140010a8a  nop     dword ptr [rax+rax+00h]
0x140010a8f  mov     rcx, rdi; P
0x140010a92  call    FreeConnectionObj
0x140010a97  test    rbx, rbx
0x140010a9a  jz      short loc_140010AFE
0x140010a9c  mov     byte ptr [rsp+78h+Irql], 0
0x140010aa4  mov     dword ptr [rbx+30h], 0
0x140010aab  mov     qword ptr [rbx+38h], 0
0x140010ab3  cmp     byte ptr cs:xmmword_140038420+2, 0
0x140010aba  jl      loc_140010BB4
0x140010ac0  lea     rcx, [rsp+78h+Irql]; Irql
0x140010ac8  call    cs:__imp_IoAcquireCancelSpinLock
0x140010acf  nop     dword ptr [rax+rax+00h]
0x140010ad4  xor     eax, eax
0x140010ad6  xchg    rax, [rbx+68h]
0x140010ada  mov     cl, byte ptr [rsp+78h+Irql]; Irql
0x140010ae1  call    cs:__imp_IoReleaseCancelSpinLock
0x140010ae8  nop     dword ptr [rax+rax+00h]
0x140010aed  mov     dl, 2; PriorityBoost
0x140010aef  mov     rcx, rbx; Irp
0x140010af2  call    cs:__imp_IofCompleteRequest
0x140010af9  nop     dword ptr [rax+rax+00h]
0x140010afe  add     rsp, 48h
0x140010b02  pop     r15
0x140010b04  pop     r14
0x140010b06  pop     rdi
0x140010b07  pop     rsi
0x140010b08  pop     rbp
0x140010b09  pop     rbx
0x140010b0a  retn
0x140010b0c  mov     dl, bpl; NewIrql
0x140010b0f  mov     rcx, rsi; SpinLock
0x140010b12  call    cs:__imp_KeReleaseSpinLock
0x140010b19  nop     dword ptr [rax+rax+00h]
0x140010b1e  jmp     short loc_140010AFE
0x140010b20  mov     ecx, [r14+384h]
0x140010b27  shr     ecx, 1
0x140010b29  cmp     edx, ecx
0x140010b2b  jbe     loc_140010A67
0x140010b31  mov     rdx, [rdi+20h]
0x140010b35  add     rdx, 1A0h
0x140010b3c  mov     rcx, [rdx]
0x140010b3f  cmp     [rcx+8], rdx
0x140010b43  jnz     short loc_140010B79
0x140010b45  mov     rax, [rcx]
0x140010b48  cmp     [rax+8], rcx
0x140010b4c  jnz     short loc_140010B79
0x140010b4e  mov     [rdx], rax
0x140010b51  mov     r9d, 300Bh
0x140010b57  mov     [rax+8], rdx
0x140010b5b  lea     rax, aMinioNetbtSysN_5; "minio\\netbt\\sys\\name.c"
0x140010b62  lock dec dword ptr [r14+380h]
0x140010b6a  mov     [rsp+78h+var_58], rax
0x140010b6f  call    NbtDereferenceLowerConnection
0x140010b74  jmp     loc_140010A67
0x140010b79  mov     ecx, 3
0x140010b7e  int     29h; Win8: RtlFailFast(ecx)
0x140010b80  mov     r10d, [rcx+14h]
0x140010b84  mov     edx, 52h ; 'R'
0x140010b89  mov     [rsp+78h+var_40], r9
0x140010b8e  mov     r9, rdi
0x140010b91  mov     [rsp+78h+var_48], r8d
0x140010b96  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x140010b9d  lea     eax, [r10-1]
0x140010ba1  mov     [rsp+78h+var_50], eax
0x140010ba5  mov     dword ptr [rsp+78h+var_58], r10d
0x140010baa  call    WPP_SF_qddds
0x140010baf  jmp     loc_1400109A8
0x140010bb4  mov     edx, 46h ; 'F'
0x140010bb9  mov     [rsp+78h+var_50], 0
0x140010bc1  mov     ecx, 417h
0x140010bc6  mov     dword ptr [rsp+78h+var_58], 0
0x140010bce  mov     r9, rbx
0x140010bd1  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x140010bd8  call    WPP_SF_qdd
0x140010bdd  jmp     loc_140010AC0
```
