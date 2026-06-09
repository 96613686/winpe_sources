# CompleteClientReq

- ea: `0x140007c4c`
- end: `0x140007def`
- name: `CompleteClientReq`
- size: `419`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140007a08`
- `0x140009ee0`
- `0x140015818`
- `0x14001ba80`
- `0x140021ff8`
- `0x140025430`
- `0x14002919c`
- `0x14002e420`
- `0x14005006c`

## callees

- `0x140007c4c`
- `0x140009844`
- `0x140030f80`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007c83`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007d71`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007c83`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007d71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007cd5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007dd2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007cd5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007dd2`

## pseudocode

```c
void __fastcall CompleteClientReq(void (__fastcall *a1)(_QWORD *, _QWORD), _QWORD *a2, unsigned int a3)
{
  __int64 *v6; // rsi
  KIRQL v7; // al
  _QWORD *v8; // rcx
  __int64 **v9; // rdx
  __int64 *v10; // rax
  __int64 *v11; // rbx
  __int64 ***v12; // rax
  KIRQL v13; // al
  __int64 v14; // rcx
  int v15; // r8d
  __int64 **v16; // [rsp+50h] [rbp-10h] BYREF
  __int64 ***v17; // [rsp+58h] [rbp-8h]
  KIRQL NewIrql; // [rsp+80h] [rbp+20h] BYREF

  v17 = &v16;
  v16 = (__int64 **)&v16;
  v6 = 0;
  v7 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( a2 )
  {
    v6 = (__int64 *)a2[4];
    v8 = (_QWORD *)a2[31];
    if ( v8 != a2 + 31 )
    {
      v16 = (__int64 **)a2[31];
      v8[1] = &v16;
      v17 = (__int64 ***)a2[32];
      *v17 = (__int64 **)&v16;
      a2[32] = a2 + 31;
      a2[31] = a2 + 31;
    }
  }
  KeReleaseSpinLock(&SpinLock, v7);
  a1(a2, a3);
  while ( 1 )
  {
    v9 = v16;
    if ( v16 == (__int64 **)&v16 )
      break;
    if ( v16[1] != (__int64 *)&v16 || (v10 = *v16, (__int64 **)(*v16)[1] != v16) )
      __fastfail(3u);
    v16 = (__int64 **)*v16;
    v11 = (__int64 *)(v9 - 31);
    v10[1] = (__int64)&v16;
    if ( *(v9 - 27) != v6 && a3 )
    {
      v12 = v17;
      v11[32] = (__int64)v17;
      *v12 = v9;
      if ( *v9 == (__int64 *)&v16 )
        *v9 = (__int64 *)v9;
      v13 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
      v14 = v11[5];
      NewIrql = v13;
      QueryNameOnNet(v14, (_DWORD)Str2, v15, (_DWORD)v11, v11[20], NodeType & 0xF, 0, v11[4], (__int64)&NewIrql);
      KeReleaseSpinLock(&SpinLock, NewIrql);
      return;
    }
    ((void (__fastcall *)(__int64 *, _QWORD))v11[20])(v11, a3);
  }
}

```

## disassembly

```asm
0x140007c4c  mov     [rsp-18h+arg_8], rbx
0x140007c51  mov     [rsp-18h+arg_10], rsi
0x140007c56  push    rbp
0x140007c57  push    rdi
0x140007c58  push    r14
0x140007c5a  mov     rbp, rsp
0x140007c5d  sub     rsp, 60h
0x140007c61  lea     rax, [rbp+var_10]
0x140007c65  mov     r14, rcx
0x140007c68  mov     [rbp+var_8], rax
0x140007c6c  lea     rcx, SpinLock; SpinLock
0x140007c73  lea     rax, [rbp+var_10]
0x140007c77  mov     edi, r8d
0x140007c7a  mov     [rbp+var_10], rax
0x140007c7e  mov     rbx, rdx
0x140007c81  xor     esi, esi
0x140007c83  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007c8a  nop     dword ptr [rax+rax+00h]
0x140007c8f  test    rbx, rbx
0x140007c92  jz      short loc_140007CCC
0x140007c94  mov     rsi, [rbx+20h]
0x140007c98  lea     rdx, [rbx+0F8h]
0x140007c9f  mov     rcx, [rdx]
0x140007ca2  cmp     rcx, rdx
0x140007ca5  jz      short loc_140007CCC
0x140007ca7  mov     [rbp+var_10], rcx
0x140007cab  lea     r8, [rbp+var_10]
0x140007caf  mov     [rcx+8], r8
0x140007cb3  lea     r8, [rbp+var_10]
0x140007cb7  mov     rcx, [rbx+100h]
0x140007cbe  mov     [rbp+var_8], rcx
0x140007cc2  mov     [rcx], r8
0x140007cc5  mov     [rdx+8], rdx
0x140007cc9  mov     [rdx], rdx
0x140007ccc  mov     dl, al; NewIrql
0x140007cce  lea     rcx, SpinLock; SpinLock
0x140007cd5  call    cs:__imp_KeReleaseSpinLock
0x140007cdc  nop     dword ptr [rax+rax+00h]
0x140007ce1  mov     rax, r14
0x140007ce4  mov     edx, edi
0x140007ce6  mov     rcx, rbx
0x140007ce9  call    _guard_dispatch_icall
0x140007cee  mov     rdx, [rbp+var_10]
0x140007cf2  lea     rax, [rbp+var_10]
0x140007cf6  cmp     rdx, rax
0x140007cf9  jnz     short loc_140007D11
0x140007cfb  lea     r11, [rsp+60h+var_s0]
0x140007d00  mov     rbx, [r11+28h]
0x140007d04  mov     rsi, [r11+30h]
0x140007d08  mov     rsp, r11
0x140007d0b  pop     r14
0x140007d0d  pop     rdi
0x140007d0e  pop     rbp
0x140007d0f  retn
0x140007d11  lea     rax, [rbp+var_10]
0x140007d15  cmp     [rdx+8], rax
0x140007d19  jnz     short loc_140007D24
0x140007d1b  mov     rax, [rdx]
0x140007d1e  cmp     [rax+8], rdx
0x140007d22  jz      short loc_140007D2B
0x140007d24  mov     ecx, 3
0x140007d29  int     29h; Win8: RtlFailFast(ecx)
0x140007d2b  mov     [rbp+var_10], rax
0x140007d2f  lea     rcx, [rbp+var_10]
0x140007d33  lea     rbx, [rdx-0F8h]
0x140007d3a  mov     [rax+8], rcx
0x140007d3e  cmp     [rbx+20h], rsi
0x140007d42  jz      loc_140007DE3
0x140007d48  test    edi, edi
0x140007d4a  jz      loc_140007DE3
0x140007d50  mov     rax, [rbp+var_8]
0x140007d54  mov     [rbx+100h], rax
0x140007d5b  mov     [rax], rdx
0x140007d5e  lea     rax, [rbp+var_10]
0x140007d62  cmp     [rdx], rax
0x140007d65  jnz     short loc_140007D6A
0x140007d67  mov     [rdx], rdx
0x140007d6a  lea     rcx, SpinLock; SpinLock
0x140007d71  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007d78  nop     dword ptr [rax+rax+00h]
0x140007d7d  movzx   edx, cs:NodeType
0x140007d84  mov     r9, rbx
0x140007d87  mov     rcx, [rbx+28h]
0x140007d8b  and     edx, 0Fh
0x140007d8e  mov     [rbp+NewIrql], al
0x140007d91  lea     rax, [rbp+NewIrql]
0x140007d95  mov     [rsp+60h+var_20], rax
0x140007d9a  mov     rax, [rbx+20h]
0x140007d9e  mov     [rsp+60h+var_28], rax
0x140007da3  mov     rax, [rbx+0A0h]
0x140007daa  mov     [rsp+60h+var_30], 0
0x140007db3  mov     [rsp+60h+var_38], edx
0x140007db7  mov     rdx, cs:Str2
0x140007dbe  mov     [rsp+60h+var_40], rax
0x140007dc3  call    QueryNameOnNet
0x140007dc8  mov     dl, [rbp+NewIrql]; NewIrql
0x140007dcb  lea     rcx, SpinLock; SpinLock
0x140007dd2  call    cs:__imp_KeReleaseSpinLock
0x140007dd9  nop     dword ptr [rax+rax+00h]
0x140007dde  jmp     loc_140007CFB
0x140007de3  mov     rax, [rbx+0A0h]
0x140007dea  jmp     loc_140007CE4
```
