# TxfDeleteTxfRmcb

- ea: `0x140196e80`
- end: `0x140197035`
- name: `TxfDeleteTxfRmcb`
- size: `437`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `29`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140017480`
- `0x140052bf0`
- `0x1400f8510`
- `0x1400f9610`
- `0x1400fb118`
- `0x14012b270`
- `0x140140b00`
- `0x140154d60`
- `0x140167d70`
- `0x140167f00`
- `0x140168588`
- `0x140188078`
- `0x140188d34`
- `0x14018acf8`
- `0x1401968a0`
- `0x140196b20`
- `0x140198300`
- `0x1401cf610`
- `0x1401cf6b4`
- `0x1401dc638`
- `0x1401f4270`
- `0x1401f50d8`
- `0x1402149d0`
- `0x14021c6d0`
- `0x14021e8d4`
- `0x14023035c`
- `0x140259f00`
- `0x14025ccec`
- `0x140274640`

## callees

- `0x140140fac`
- `0x140196e80`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140196fdf`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140196fdf`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f2b`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f42`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f59`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f70`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f87`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f2b`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f42`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f59`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f70`
- `ntoskrnl!ExDeleteResourceLite` at `0x140196f87`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140196ecb`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140196ecb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402cacce`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402cacce`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140196f18`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140196f18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140196fad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019701c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140196fad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14019701c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140196ea2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140196ea2`

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
0x140196e80  push    rbx
0x140196e82  push    rbp
0x140196e83  push    rsi
0x140196e84  push    rdi
0x140196e85  sub     rsp, 38h
0x140196e89  mov     rdi, [rcx+10h]
0x140196e8d  mov     rbx, rcx
0x140196e90  xorps   xmm0, xmm0
0x140196e93  movups  [rsp+58h+Buffer], xmm0
0x140196e98  lea     rbp, [rdi+1870h]
0x140196e9f  mov     rcx, rbp; FastMutex
0x140196ea2  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140196ea9  nop     dword ptr [rax+rax+00h]
0x140196eae  mov     rax, [rbx+58h]
0x140196eb2  lea     rsi, [rdi+1680h]
0x140196eb9  mov     rcx, rsi; Table
0x140196ebc  mov     qword ptr [rsp+58h+Buffer], rax
0x140196ec1  lea     rdx, [rsp+58h+Buffer]; Buffer
0x140196ec6  mov     byte ptr [rsp+58h+Buffer+8], 1
0x140196ecb  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140196ed2  nop     dword ptr [rax+rax+00h]
0x140196ed7  test    rax, rax
0x140196eda  jnz     loc_140196FD0
0x140196ee0  mov     rax, [rbx]
0x140196ee3  cmp     [rax+8], rbx
0x140196ee7  jnz     loc_140196FC9
0x140196eed  mov     rdx, [rbx+8]
0x140196ef1  cmp     [rdx], rbx
0x140196ef4  jnz     loc_140196FC9
0x140196efa  mov     [rdx], rax
0x140196efd  mov     [rax+8], rdx
0x140196f01  cmp     rbx, [rdi+1868h]
0x140196f08  jnz     short loc_140196F15
0x140196f0a  mov     qword ptr [rdi+1868h], 0
0x140196f15  mov     rcx, rbp; FastMutex
0x140196f18  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140196f1f  nop     dword ptr [rax+rax+00h]
0x140196f24  mov     rcx, [rbx+0A0h]; Resource
0x140196f2b  call    cs:__imp_ExDeleteResourceLite
0x140196f32  nop     dword ptr [rax+rax+00h]
0x140196f37  mov     rcx, [rbx+18h]
0x140196f3b  add     rcx, 390h; Resource
0x140196f42  call    cs:__imp_ExDeleteResourceLite
0x140196f49  nop     dword ptr [rax+rax+00h]
0x140196f4e  mov     rcx, [rbx+18h]
0x140196f52  add     rcx, 3F8h; Resource
0x140196f59  call    cs:__imp_ExDeleteResourceLite
0x140196f60  nop     dword ptr [rax+rax+00h]
0x140196f65  mov     rcx, [rbx+18h]
0x140196f69  add     rcx, 498h; Resource
0x140196f70  call    cs:__imp_ExDeleteResourceLite
0x140196f77  nop     dword ptr [rax+rax+00h]
0x140196f7c  mov     rcx, [rbx+18h]
0x140196f80  add     rcx, 140h; Resource
0x140196f87  call    cs:__imp_ExDeleteResourceLite
0x140196f8e  nop     dword ptr [rax+rax+00h]
0x140196f93  lea     rsi, [rbx+68h]
0x140196f97  mov     rdi, [rsi]
0x140196f9a  cmp     rdi, rsi
0x140196f9d  jnz     short loc_140196FC3
0x140196f9f  mov     rcx, [rbx+18h]; P
0x140196fa3  test    rcx, rcx
0x140196fa6  jnz     short loc_14019701A
0x140196fa8  xor     edx, edx; Tag
0x140196faa  mov     rcx, rbx; P
0x140196fad  call    cs:__imp_ExFreePoolWithTag
0x140196fb4  nop     dword ptr [rax+rax+00h]
0x140196fb9  add     rsp, 38h
0x140196fbd  pop     rdi
0x140196fbe  pop     rsi
0x140196fbf  pop     rbp
0x140196fc0  pop     rbx
0x140196fc1  retn
0x140196fc3  cmp     [rdi+8], rsi
0x140196fc7  jz      short loc_140196FF0
0x140196fc9  mov     ecx, 3
0x140196fce  int     29h; Win8: RtlFailFast(ecx)
0x140196fd0  cmp     [rax], rbx
0x140196fd3  jnz     loc_140196EE0
0x140196fd9  mov     rdx, rax; Buffer
0x140196fdc  mov     rcx, rsi; Table
0x140196fdf  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140196fe6  nop     dword ptr [rax+rax+00h]
0x140196feb  jmp     loc_140196EE0
0x140196ff0  mov     rax, [rdi]
0x140196ff3  cmp     [rax+8], rdi
0x140196ff7  jnz     short loc_140196FC9
0x140196ff9  mov     [rsi], rax
0x140196ffc  mov     [rax+8], rsi
0x140197000  mov     rcx, [rdi+20h]
0x140197004  test    rcx, rcx
0x140197007  jz      loc_1402CACC4
0x14019700d  xor     edx, edx
0x14019700f  call    TxfDereferenceTxfFcb
0x140197014  nop
0x140197015  jmp     loc_1402CACC4
0x14019701a  xor     edx, edx; Tag
0x14019701c  call    cs:__imp_ExFreePoolWithTag
0x140197023  nop     dword ptr [rax+rax+00h]
0x140197028  mov     qword ptr [rbx+18h], 0
0x140197030  jmp     loc_140196FA8
0x1402cacc4  mov     rdx, rdi; Entry
0x1402cacc7  lea     rcx, TxfDeletedLinkLookasideList; Lookaside
0x1402cacce  call    cs:__imp_ExFreeToLookasideListEx
0x1402cacd5  nop     dword ptr [rax+rax+00h]
0x1402cacda  nop
0x1402cacdb  jmp     loc_140196F97
```
