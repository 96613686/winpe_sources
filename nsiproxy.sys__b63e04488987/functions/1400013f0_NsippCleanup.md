# NsippCleanup

- ea: `0x1400013f0`
- end: `0x1400015c9`
- name: `NsippCleanup`
- size: `473`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140001dd0`

## callees

- `0x1400013f0`
- `0x140006980`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001444`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001444`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001477`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001477`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001515`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400015b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001515`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400015b1`
- `NETIO!NsiSetAllParametersEx` at `0x1400014e3`
- `NETIO!NsiSetAllParametersEx` at `0x1400014e3`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x140001587`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x140001587`

## pseudocode

```c
__int64 __fastcall NsippCleanup(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v3; // rbx
  KIRQL v4; // al
  _QWORD *v5; // rcx
  _QWORD *v6; // rbx
  int v7; // eax
  __int64 v8; // rcx
  _QWORD *v9; // rax
  PVOID P; // [rsp+20h] [rbp-39h] BYREF
  PVOID *p_P; // [rsp+28h] [rbp-31h]
  __int128 v13; // [rsp+30h] [rbp-29h] BYREF
  __int128 v14; // [rsp+40h] [rbp-19h]
  int v15; // [rsp+50h] [rbp-9h]
  _QWORD v16[10]; // [rsp+60h] [rbp+7h] BYREF

  v2 = *(_QWORD *)(a2 + 48);
  memset(v16, 0, 0x48u);
  v15 = 0;
  p_P = &P;
  P = &P;
  v13 = 0;
  v14 = 0;
  v3 = *(_QWORD *)(v2 + 24);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 24));
  *(_BYTE *)(v3 + 16) = 1;
  v5 = *(_QWORD **)v3;
  if ( *(_QWORD *)v3 == v3 )
  {
    p_P = &P;
    P = &P;
  }
  else
  {
    P = *(PVOID *)v3;
    p_P = *(PVOID **)(v3 + 8);
    v5[1] = &P;
    *p_P = &P;
    *(_QWORD *)(v3 + 8) = v3;
    *(_QWORD *)v3 = v3;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 24), v4);
  while ( 1 )
  {
    v6 = P;
    if ( P == &P )
      return 0;
    v7 = *((_DWORD *)P + 4);
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        *(_OWORD *)&v16[5] = *((_OWORD *)P + 3);
        *(_OWORD *)&v16[1] = *(_OWORD *)((char *)P + 24);
        v16[3] = *((_QWORD *)P + 5);
        v16[4] = 0x700000001LL;
        v16[0] = 0;
        v16[7] = 0;
        LODWORD(v16[8]) = 0;
        NsiSetAllParametersEx(v16);
        v8 = *v6;
        if ( *(_QWORD **)(*v6 + 8LL) != v6 )
          goto LABEL_14;
        v9 = (_QWORD *)v6[1];
        if ( (_QWORD *)*v9 != v6 )
          goto LABEL_14;
        goto LABEL_9;
      }
    }
    else
    {
      v13 = *(_OWORD *)((char *)P + 24);
      v14 = *(_OWORD *)((char *)P + 40);
      NsiDeregisterChangeNotificationEx(&v13);
      v8 = *v6;
      if ( *(_QWORD **)(*v6 + 8LL) != v6 || (v9 = (_QWORD *)v6[1], (_QWORD *)*v9 != v6) )
LABEL_14:
        __fastfail(3u);
LABEL_9:
      *v9 = v8;
      *(_QWORD *)(v8 + 8) = v9;
      ExFreePoolWithTag(v6, 0);
    }
  }
}

```

## disassembly

```asm
0x1400013f0  mov     [rsp-8+arg_0], rbx
0x1400013f5  mov     [rsp-8+arg_8], rdi
0x1400013fa  push    rbp
0x1400013fb  lea     rbp, [rsp-57h]
0x140001400  sub     rsp, 0B0h
0x140001407  mov     rbx, [rdx+30h]
0x14000140b  lea     rcx, [rbp+57h+var_50]; void *
0x14000140f  xor     edx, edx; Val
0x140001411  mov     r8d, 48h ; 'H'; Size
0x140001417  call    memset
0x14000141c  xor     eax, eax
0x14000141e  xorps   xmm0, xmm0
0x140001421  mov     [rbp+57h+var_60], eax
0x140001424  lea     rax, [rbp+57h+P]
0x140001428  mov     [rbp+57h+var_88], rax
0x14000142c  lea     rax, [rbp+57h+P]
0x140001430  mov     [rbp+57h+P], rax
0x140001434  movups  [rbp+57h+var_80], xmm0
0x140001438  movups  [rbp+57h+var_70], xmm0
0x14000143c  mov     rbx, [rbx+18h]
0x140001440  lea     rcx, [rbx+18h]; SpinLock
0x140001444  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000144b  nop     dword ptr [rax+rax+00h]
0x140001450  mov     byte ptr [rbx+10h], 1
0x140001454  movzx   edx, al; NewIrql
0x140001457  mov     rcx, [rbx]
0x14000145a  cmp     rcx, rbx
0x14000145d  jnz     loc_14000153E
0x140001463  lea     rax, [rbp+57h+P]
0x140001467  mov     [rbp+57h+var_88], rax
0x14000146b  lea     rax, [rbp+57h+P]
0x14000146f  mov     [rbp+57h+P], rax
0x140001473  lea     rcx, [rbx+18h]; SpinLock
0x140001477  call    cs:__imp_KeReleaseSpinLock
0x14000147e  nop     dword ptr [rax+rax+00h]
0x140001483  mov     rbx, [rbp+57h+P]
0x140001487  lea     rax, [rbp+57h+P]
0x14000148b  cmp     rbx, rax
0x14000148e  jz      loc_140001526
0x140001494  mov     eax, [rbx+10h]
0x140001497  test    eax, eax
0x140001499  jz      loc_140001569
0x14000149f  cmp     eax, 1
0x1400014a2  jnz     short loc_140001483
0x1400014a4  mov     [rbp+57h+var_2C], 7
0x1400014ab  lea     rcx, [rbp+57h+var_50]
0x1400014af  movups  xmm0, xmmword ptr [rbx+30h]
0x1400014b3  movups  [rbp+57h+var_28], xmm0
0x1400014b7  movups  xmm1, xmmword ptr [rbx+18h]
0x1400014bb  movups  [rbp+57h+var_48], xmm1
0x1400014bf  movsd   xmm0, qword ptr [rbx+28h]
0x1400014c4  movsd   [rbp+57h+var_38], xmm0
0x1400014c9  mov     [rbp+57h+var_30], eax
0x1400014cc  mov     [rbp+57h+var_50], 0
0x1400014d4  mov     [rbp+57h+var_18], 0
0x1400014dc  mov     [rbp+57h+var_10], 0
0x1400014e3  call    cs:__imp_NsiSetAllParametersEx
0x1400014ea  nop     dword ptr [rax+rax+00h]
0x1400014ef  mov     rcx, [rbx]
0x1400014f2  cmp     [rcx+8], rbx
0x1400014f6  jnz     loc_1400015C2
0x1400014fc  mov     rax, [rbx+8]
0x140001500  cmp     [rax], rbx
0x140001503  jnz     loc_1400015C2
0x140001509  mov     [rax], rcx
0x14000150c  xor     edx, edx; Tag
0x14000150e  mov     [rcx+8], rax
0x140001512  mov     rcx, rbx; P
0x140001515  call    cs:__imp_ExFreePoolWithTag
0x14000151c  nop     dword ptr [rax+rax+00h]
0x140001521  jmp     loc_140001483
0x140001526  lea     r11, [rsp+0B0h+var_s0]
0x14000152e  xor     eax, eax
0x140001530  mov     rbx, [r11+10h]
0x140001534  mov     rdi, [r11+18h]
0x140001538  mov     rsp, r11
0x14000153b  pop     rbp
0x14000153c  retn
0x14000153e  mov     [rbp+57h+P], rcx
0x140001542  mov     rax, [rbx+8]
0x140001546  mov     [rbp+57h+var_88], rax
0x14000154a  lea     rax, [rbp+57h+P]
0x14000154e  mov     [rcx+8], rax
0x140001552  lea     rcx, [rbp+57h+P]
0x140001556  mov     rax, [rbp+57h+var_88]
0x14000155a  mov     [rax], rcx
0x14000155d  mov     [rbx+8], rbx
0x140001561  mov     [rbx], rbx
0x140001564  jmp     loc_140001473
0x140001569  movups  xmm0, xmmword ptr [rbx+18h]
0x14000156d  lea     rcx, [rbp+57h+var_80]
0x140001571  movups  [rbp+57h+var_80], xmm0
0x140001575  movsd   xmm1, qword ptr [rbx+28h]
0x14000157a  movsd   qword ptr [rbp+57h+var_70], xmm1
0x14000157f  mov     rax, [rbx+30h]
0x140001583  mov     qword ptr [rbp+57h+var_70+8], rax
0x140001587  call    cs:__imp_NsiDeregisterChangeNotificationEx
0x14000158e  nop     dword ptr [rax+rax+00h]
0x140001593  mov     rcx, [rbx]
0x140001596  cmp     [rcx+8], rbx
0x14000159a  jnz     short loc_1400015C2
0x14000159c  mov     rax, [rbx+8]
0x1400015a0  cmp     [rax], rbx
0x1400015a3  jnz     short loc_1400015C2
0x1400015a5  mov     [rax], rcx
0x1400015a8  xor     edx, edx; Tag
0x1400015aa  mov     [rcx+8], rax
0x1400015ae  mov     rcx, rbx; P
0x1400015b1  call    cs:__imp_ExFreePoolWithTag
0x1400015b8  nop     dword ptr [rax+rax+00h]
0x1400015bd  jmp     loc_140001483
0x1400015c2  mov     ecx, 3
0x1400015c7  int     29h; Win8: RtlFailFast(ecx)
```
