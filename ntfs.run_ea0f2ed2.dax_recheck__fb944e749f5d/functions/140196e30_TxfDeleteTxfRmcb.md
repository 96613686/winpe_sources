# TxfDeleteTxfRmcb

- ea: `0x140196e30`
- end: `0x140196fe5`
- name: `TxfDeleteTxfRmcb`
- size: `437`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `29`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140017480`
- `0x140052b80`
- `0x1400f84c0`
- `0x1400f95c0`
- `0x1400fb0c8`
- `0x14012b220`
- `0x140140ab0`
- `0x140154d10`
- `0x140167d20`
- `0x140167eb0`
- `0x140168538`
- `0x140188028`
- `0x140188ce4`
- `0x14018aca8`
- `0x140196850`
- `0x140196ad0`
- `0x1401982b0`
- `0x1401cf5c0`
- `0x1401cf664`
- `0x1401dc5e8`
- `0x1401f4220`
- `0x1401f5088`
- `0x140214980`
- `0x14021c680`
- `0x14021e884`
- `0x14023030c`
- `0x140259eb0`
- `0x14025cc9c`
- `0x1402745f0`

## callees

- `0x140140f5c`
- `0x140196e30`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140196f8f`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140196f8f`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196edb`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196ef2`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f09`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f20`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f37`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196edb`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196ef2`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f09`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f20`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f37`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140196e7b`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140196e7b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402cac7e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402cac7e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140196ec8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140196ec8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140196f5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140196fcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140196f5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140196fcc`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140196e52`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140196e52`

## pseudocode

```c
void __fastcall TxfDeleteTxfRmcb(char *P)
{
  __int64 v1; // rdi
  PVOID *v3; // rax
  _QWORD *v4; // rax
  PVOID *v5; // rdx
  _QWORD **v6; // rsi
  _QWORD *v7; // rdi
  void *v8; // rcx
  _QWORD *v9; // rax
  void *v10; // rcx
  __int128 Buffer; // [rsp+20h] [rbp-38h] BYREF

  v1 = *((_QWORD *)P + 2);
  Buffer = 0;
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v1 + 6256));
  *(_QWORD *)&Buffer = *((_QWORD *)P + 11);
  BYTE8(Buffer) = 1;
  v3 = (PVOID *)RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(v1 + 5760), &Buffer);
  if ( v3 && *v3 == P )
    RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(v1 + 5760), v3);
  v4 = *(_QWORD **)P;
  if ( *(char **)(*(_QWORD *)P + 8LL) != P || (v5 = (PVOID *)*((_QWORD *)P + 1), *v5 != P) )
LABEL_12:
    __fastfail(3u);
  *v5 = v4;
  v4[1] = v5;
  if ( P == *(char **)(v1 + 6248) )
    *(_QWORD *)(v1 + 6248) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v1 + 6256));
  ExDeleteResourceLite(*((PERESOURCE *)P + 20));
  ExDeleteResourceLite((PERESOURCE)(*((_QWORD *)P + 3) + 912LL));
  ExDeleteResourceLite((PERESOURCE)(*((_QWORD *)P + 3) + 1016LL));
  ExDeleteResourceLite((PERESOURCE)(*((_QWORD *)P + 3) + 1176LL));
  ExDeleteResourceLite((PERESOURCE)(*((_QWORD *)P + 3) + 320LL));
  v6 = (_QWORD **)(P + 104);
  while ( 1 )
  {
    v7 = *v6;
    if ( *v6 == v6 )
      break;
    if ( (_QWORD **)v7[1] != v6 )
      goto LABEL_12;
    v9 = (_QWORD *)*v7;
    if ( *(_QWORD **)(*v7 + 8LL) != v7 )
      goto LABEL_12;
    *v6 = v9;
    v9[1] = v6;
    v10 = (void *)v7[4];
    if ( v10 )
      TxfDereferenceTxfFcb(v10);
    ExFreeToLookasideListEx(&TxfDeletedLinkLookasideList, v7);
  }
  v8 = (void *)*((_QWORD *)P + 3);
  if ( v8 )
  {
    ExFreePoolWithTag(v8, 0);
    *((_QWORD *)P + 3) = 0;
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140196e30  push    rbx
0x140196e32  push    rbp
0x140196e33  push    rsi
0x140196e34  push    rdi
0x140196e35  sub     rsp, 38h
0x140196e39  mov     rdi, [rcx+10h]
0x140196e3d  mov     rbx, rcx
0x140196e40  xorps   xmm0, xmm0
0x140196e43  movups  [rsp+58h+Buffer], xmm0
0x140196e48  lea     rbp, [rdi+1870h]
0x140196e4f  mov     rcx, rbp; FastMutex
0x140196e52  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140196e59  nop     dword ptr [rax+rax+00h]
0x140196e5e  mov     rax, [rbx+58h]
0x140196e62  lea     rsi, [rdi+1680h]
0x140196e69  mov     rcx, rsi; Table
0x140196e6c  mov     qword ptr [rsp+58h+Buffer], rax
0x140196e71  lea     rdx, [rsp+58h+Buffer]; Buffer
0x140196e76  mov     byte ptr [rsp+58h+Buffer+8], 1
0x140196e7b  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140196e82  nop     dword ptr [rax+rax+00h]
0x140196e87  test    rax, rax
0x140196e8a  jnz     loc_140196F80
0x140196e90  mov     rax, [rbx]
0x140196e93  cmp     [rax+8], rbx
0x140196e97  jnz     loc_140196F79
0x140196e9d  mov     rdx, [rbx+8]
0x140196ea1  cmp     [rdx], rbx
0x140196ea4  jnz     loc_140196F79
0x140196eaa  mov     [rdx], rax
0x140196ead  mov     [rax+8], rdx
0x140196eb1  cmp     rbx, [rdi+1868h]
0x140196eb8  jnz     short loc_140196EC5
0x140196eba  mov     qword ptr [rdi+1868h], 0
0x140196ec5  mov     rcx, rbp; FastMutex
0x140196ec8  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140196ecf  nop     dword ptr [rax+rax+00h]
0x140196ed4  mov     rcx, [rbx+0A0h]; Resource
0x140196edb  call    cs:__imp_ExDeleteResourceLite
0x140196ee2  nop     dword ptr [rax+rax+00h]
0x140196ee7  mov     rcx, [rbx+18h]
0x140196eeb  add     rcx, 390h; Resource
0x140196ef2  call    cs:__imp_ExDeleteResourceLite
0x140196ef9  nop     dword ptr [rax+rax+00h]
0x140196efe  mov     rcx, [rbx+18h]
0x140196f02  add     rcx, 3F8h; Resource
0x140196f09  call    cs:__imp_ExDeleteResourceLite
0x140196f10  nop     dword ptr [rax+rax+00h]
0x140196f15  mov     rcx, [rbx+18h]
0x140196f19  add     rcx, 498h; Resource
0x140196f20  call    cs:__imp_ExDeleteResourceLite
0x140196f27  nop     dword ptr [rax+rax+00h]
0x140196f2c  mov     rcx, [rbx+18h]
0x140196f30  add     rcx, 140h; Resource
0x140196f37  call    cs:__imp_ExDeleteResourceLite
0x140196f3e  nop     dword ptr [rax+rax+00h]
0x140196f43  lea     rsi, [rbx+68h]
0x140196f47  mov     rdi, [rsi]
0x140196f4a  cmp     rdi, rsi
0x140196f4d  jnz     short loc_140196F73
0x140196f4f  mov     rcx, [rbx+18h]; P
0x140196f53  test    rcx, rcx
0x140196f56  jnz     short loc_140196FCA
0x140196f58  xor     edx, edx; Tag
0x140196f5a  mov     rcx, rbx; P
0x140196f5d  call    cs:__imp_ExFreePoolWithTag
0x140196f64  nop     dword ptr [rax+rax+00h]
0x140196f69  add     rsp, 38h
0x140196f6d  pop     rdi
0x140196f6e  pop     rsi
0x140196f6f  pop     rbp
0x140196f70  pop     rbx
0x140196f71  retn
0x140196f73  cmp     [rdi+8], rsi
0x140196f77  jz      short loc_140196FA0
0x140196f79  mov     ecx, 3
0x140196f7e  int     29h; Win8: RtlFailFast(ecx)
0x140196f80  cmp     [rax], rbx
0x140196f83  jnz     loc_140196E90
0x140196f89  mov     rdx, rax; Buffer
0x140196f8c  mov     rcx, rsi; Table
0x140196f8f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140196f96  nop     dword ptr [rax+rax+00h]
0x140196f9b  jmp     loc_140196E90
0x140196fa0  mov     rax, [rdi]
0x140196fa3  cmp     [rax+8], rdi
0x140196fa7  jnz     short loc_140196F79
0x140196fa9  mov     [rsi], rax
0x140196fac  mov     [rax+8], rsi
0x140196fb0  mov     rcx, [rdi+20h]
0x140196fb4  test    rcx, rcx
0x140196fb7  jz      loc_1402CAC74
0x140196fbd  xor     edx, edx
0x140196fbf  call    TxfDereferenceTxfFcb
0x140196fc4  nop
0x140196fc5  jmp     loc_1402CAC74
0x140196fca  xor     edx, edx; Tag
0x140196fcc  call    cs:__imp_ExFreePoolWithTag
0x140196fd3  nop     dword ptr [rax+rax+00h]
0x140196fd8  mov     qword ptr [rbx+18h], 0
0x140196fe0  jmp     loc_140196F58
0x1402cac74  mov     rdx, rdi; Entry
0x1402cac77  lea     rcx, TxfDeletedLinkLookasideList; Lookaside
0x1402cac7e  call    cs:__imp_ExFreeToLookasideListEx
0x1402cac85  nop     dword ptr [rax+rax+00h]
0x1402cac8a  nop
0x1402cac8b  jmp     loc_140196F47
```
