# UxpSslAllocateReceiverBuffer

- ea: `0x1c0157ac8`
- end: `0x1c0157b54`
- name: `UxpSslAllocateReceiverBuffer`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c01565b0`

## callees

- `0x1c0001118`
- `0x1c001b610`
- `0x1c001b640`
- `0x1c0157ac8`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0158443`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c015850e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0158443`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c015850e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c01583d2`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c015849d`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c01583d2`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c015849d`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c015856a`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c015856a`

## pseudocode

```c
_DWORD *__fastcall UxpSslAllocateReceiverBuffer(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned int v5; // ecx
  __int64 v6; // rbx
  unsigned int v7; // r8d
  unsigned int v8; // eax
  __int64 v9; // rdi
  __int64 v10; // rcx
  unsigned int v11; // r8d
  unsigned int v12; // eax
  _DWORD *PoolWithTagPriority; // rbx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 (__fastcall *v17)(__int64, __int64, __int64, __int64); // rax
  int v18; // eax
  _QWORD *v19; // rbx
  unsigned int v20; // r8d
  unsigned int v21; // eax
  __int64 v22; // rdi
  PVOID v23; // rcx
  unsigned int v24; // r8d
  unsigned int v25; // eax
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 (__fastcall *v29)(__int64, __int64, __int64, __int64); // rax

  v2 = a2;
  if ( a1 )
  {
    v5 = a2 + *(_DWORD *)(a1 + 48);
    if ( v5 < a2 )
      return 0;
    v2 = v5;
  }
  if ( v2 <= UxSslSmallReceiveBufferSize )
  {
    if ( UxCompactMode )
    {
      v6 = qword_1C0074480;
      v7 = KeGetCurrentNodeNumber() + 1;
      v8 = *(_DWORD *)v6 - 1;
      if ( v7 < *(_DWORD *)v6 )
        v8 = v7;
      v9 = *(_QWORD *)(*(_QWORD *)(v6 + 32) + 8LL * v8);
      if ( *(_BYTE *)(v9 + 112) )
        goto LABEL_20;
      v10 = v6;
    }
    else
    {
      v10 = qword_1C0074480;
      v11 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v12 = *(_DWORD *)qword_1C0074480 - 1;
      if ( v11 < *(_DWORD *)qword_1C0074480 )
        v12 = v11;
      v9 = *(_QWORD *)(*(_QWORD *)(qword_1C0074480 + 32) + 8LL * v12);
      if ( *(_BYTE *)(v9 + 112) )
        goto LABEL_20;
    }
    PplpLazyInitializeLookasideList(v10, v9);
LABEL_20:
    ++*(_DWORD *)(v9 + 20);
    PoolWithTagPriority = ExpInterlockedPopEntrySList((PSLIST_HEADER)v9);
    if ( !PoolWithTagPriority )
    {
      v14 = *(unsigned int *)(v9 + 40);
      v15 = *(unsigned int *)(v9 + 44);
      v16 = *(unsigned int *)(v9 + 36);
      v17 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v9 + 48);
      ++*(_DWORD *)(v9 + 24);
      PoolWithTagPriority = (_DWORD *)v17(v16, v15, v14, v9);
    }
    v2 = UxSslSmallReceiveBufferSize;
    v18 = 0;
    goto LABEL_5;
  }
  if ( v2 <= UxSslReceiverBufferSize )
  {
    if ( UxCompactMode )
    {
      v19 = P;
      v20 = KeGetCurrentNodeNumber() + 1;
      v21 = *(_DWORD *)v19 - 1;
      if ( v20 < *(_DWORD *)v19 )
        v21 = v20;
      v22 = *(_QWORD *)(v19[4] + 8LL * v21);
      if ( *(_BYTE *)(v22 + 112) )
        goto LABEL_33;
      v23 = v19;
    }
    else
    {
      v23 = P;
      v24 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v25 = *(_DWORD *)P - 1;
      if ( v24 < *(_DWORD *)P )
        v25 = v24;
      v22 = *(_QWORD *)(*((_QWORD *)P + 4) + 8LL * v25);
      if ( *(_BYTE *)(v22 + 112) )
        goto LABEL_33;
    }
    PplpLazyInitializeLookasideList(v23, v22);
LABEL_33:
    ++*(_DWORD *)(v22 + 20);
    PoolWithTagPriority = ExpInterlockedPopEntrySList((PSLIST_HEADER)v22);
    if ( !PoolWithTagPriority )
    {
      v26 = *(unsigned int *)(v22 + 40);
      v27 = *(unsigned int *)(v22 + 44);
      v28 = *(unsigned int *)(v22 + 36);
      v29 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v22 + 48);
      ++*(_DWORD *)(v22 + 24);
      PoolWithTagPriority = (_DWORD *)v29(v28, v27, v26, v22);
    }
    v2 = UxSslReceiverBufferSize;
    v18 = 1;
    goto LABEL_5;
  }
  if ( v2 >= v2 + 56 )
    PoolWithTagPriority = 0;
  else
    PoolWithTagPriority = ExAllocatePoolWithTagPriority((POOL_TYPE)512, v2 + 56LL, 0x42537855u, LowPoolPriority);
  v18 = 2;
LABEL_5:
  if ( PoolWithTagPriority )
  {
    PoolWithTagPriority[2] = 0;
    PoolWithTagPriority[8] = 0;
    PoolWithTagPriority[12] = 0;
    *PoolWithTagPriority = 1112766549;
    PoolWithTagPriority[4] = v18;
    PoolWithTagPriority[13] = v2;
    PoolWithTagPriority[1] = 1;
    *((_BYTE *)PoolWithTagPriority + 12) = 0;
    *((_QWORD *)PoolWithTagPriority + 3) = PoolWithTagPriority + 14;
    *((_QWORD *)PoolWithTagPriority + 5) = PoolWithTagPriority + 14;
    if ( a1 )
    {
      PoolWithTagPriority[12] = *(_DWORD *)(a1 + 48);
      memmove(PoolWithTagPriority + 14, *(const void **)(a1 + 40), *(unsigned int *)(a1 + 48));
    }
  }
  return PoolWithTagPriority;
}

```

## disassembly

```asm
0x1c0157ac8  mov     [rsp+arg_0], rbx
0x1c0157acd  mov     [rsp+arg_8], rsi
0x1c0157ad2  push    rdi
0x1c0157ad3  sub     rsp, 30h
0x1c0157ad7  mov     edi, edx
0x1c0157ad9  mov     rsi, rcx
0x1c0157adc  test    rcx, rcx
0x1c0157adf  jnz     loc_1C01583B4
0x1c0157ae5  cmp     edi, cs:UxSslSmallReceiveBufferSize
0x1c0157aeb  ja      loc_1C0158481
0x1c0157af1  cmp     cs:UxCompactMode, 0
0x1c0157af8  jnz     loc_1C01583CB
0x1c0157afe  jmp     loc_1C0158406
0x1c0157b03  test    rbx, rbx
0x1c0157b06  jz      short loc_1C0157B40
0x1c0157b08  and     dword ptr [rbx+8], 0
0x1c0157b0c  lea     rcx, [rbx+38h]; void *
0x1c0157b10  and     dword ptr [rbx+20h], 0
0x1c0157b14  and     dword ptr [rbx+30h], 0
0x1c0157b18  mov     dword ptr [rbx], 42537855h
0x1c0157b1e  mov     [rbx+10h], eax
0x1c0157b21  mov     [rbx+34h], edi
0x1c0157b24  mov     dword ptr [rbx+4], 1
0x1c0157b2b  mov     byte ptr [rbx+0Ch], 0
0x1c0157b2f  mov     [rbx+18h], rcx
0x1c0157b33  mov     [rbx+28h], rcx
0x1c0157b37  test    rsi, rsi
0x1c0157b3a  jnz     loc_1C0158587
0x1c0157b40  mov     rax, rbx
0x1c0157b43  mov     rbx, [rsp+38h+arg_0]
0x1c0157b48  mov     rsi, [rsp+38h+arg_8]
0x1c0157b4d  add     rsp, 30h
0x1c0157b51  pop     rdi
0x1c0157b52  retn
0x1c01583b4  mov     ecx, [rcx+30h]
0x1c01583b7  add     ecx, edx
0x1c01583b9  cmp     ecx, edx
0x1c01583bb  jnb     short loc_1C01583C4
0x1c01583bd  xor     eax, eax
0x1c01583bf  jmp     loc_1C0157B43
0x1c01583c4  mov     edi, ecx
0x1c01583c6  jmp     loc_1C0157AE5
0x1c01583cb  mov     rbx, cs:qword_1C0074480
0x1c01583d2  call    cs:__imp_KeGetCurrentNodeNumber
0x1c01583d9  nop     dword ptr [rax+rax+00h]
0x1c01583de  mov     edx, [rbx]
0x1c01583e0  movzx   r8d, ax
0x1c01583e4  inc     r8d
0x1c01583e7  cmp     r8d, edx
0x1c01583ea  lea     eax, [rdx-1]
0x1c01583ed  cmovb   eax, r8d
0x1c01583f1  mov     edx, eax
0x1c01583f3  mov     rax, [rbx+20h]
0x1c01583f7  mov     rdi, [rax+rdx*8]
0x1c01583fb  cmp     byte ptr [rdi+70h], 0
0x1c01583ff  jnz     short loc_1C015843D
0x1c0158401  mov     rcx, rbx
0x1c0158404  jmp     short loc_1C0158435
0x1c0158406  mov     eax, gs:1A4h
0x1c015840e  mov     rcx, cs:qword_1C0074480
0x1c0158415  lea     r8d, [rax+1]
0x1c0158419  mov     edx, [rcx]
0x1c015841b  cmp     r8d, edx
0x1c015841e  lea     eax, [rdx-1]
0x1c0158421  cmovb   eax, r8d
0x1c0158425  mov     edx, eax
0x1c0158427  mov     rax, [rcx+20h]
0x1c015842b  mov     rdi, [rax+rdx*8]
0x1c015842f  cmp     byte ptr [rdi+70h], 0
0x1c0158433  jnz     short loc_1C015843D
0x1c0158435  mov     rdx, rdi
0x1c0158438  call    PplpLazyInitializeLookasideList
0x1c015843d  inc     dword ptr [rdi+14h]
0x1c0158440  mov     rcx, rdi; ListHead
0x1c0158443  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c015844a  nop     dword ptr [rax+rax+00h]
0x1c015844f  mov     rbx, rax
0x1c0158452  test    rax, rax
0x1c0158455  jnz     short loc_1C0158474
0x1c0158457  mov     r8d, [rdi+28h]
0x1c015845b  mov     r9, rdi
0x1c015845e  mov     edx, [rdi+2Ch]
0x1c0158461  mov     ecx, [rdi+24h]
0x1c0158464  mov     rax, [rdi+30h]
0x1c0158468  inc     dword ptr [rdi+18h]
0x1c015846b  call    cs:__guard_dispatch_icall_fptr
0x1c0158471  mov     rbx, rax
0x1c0158474  mov     edi, cs:UxSslSmallReceiveBufferSize
0x1c015847a  xor     eax, eax
0x1c015847c  jmp     loc_1C0157B03
0x1c0158481  cmp     edi, cs:UxSslReceiverBufferSize
0x1c0158487  ja      loc_1C015854F
0x1c015848d  cmp     cs:UxCompactMode, 0
0x1c0158494  jz      short loc_1C01584D1
0x1c0158496  mov     rbx, cs:P
0x1c015849d  call    cs:__imp_KeGetCurrentNodeNumber
0x1c01584a4  nop     dword ptr [rax+rax+00h]
0x1c01584a9  mov     edx, [rbx]
0x1c01584ab  movzx   r8d, ax
0x1c01584af  inc     r8d
0x1c01584b2  cmp     r8d, edx
0x1c01584b5  lea     eax, [rdx-1]
0x1c01584b8  cmovb   eax, r8d
0x1c01584bc  mov     edx, eax
0x1c01584be  mov     rax, [rbx+20h]
0x1c01584c2  mov     rdi, [rax+rdx*8]
0x1c01584c6  cmp     byte ptr [rdi+70h], 0
0x1c01584ca  jnz     short loc_1C0158508
0x1c01584cc  mov     rcx, rbx
0x1c01584cf  jmp     short loc_1C0158500
0x1c01584d1  mov     eax, gs:1A4h
0x1c01584d9  mov     rcx, cs:P
0x1c01584e0  lea     r8d, [rax+1]
0x1c01584e4  mov     edx, [rcx]
0x1c01584e6  cmp     r8d, edx
0x1c01584e9  lea     eax, [rdx-1]
0x1c01584ec  cmovb   eax, r8d
0x1c01584f0  mov     edx, eax
0x1c01584f2  mov     rax, [rcx+20h]
0x1c01584f6  mov     rdi, [rax+rdx*8]
0x1c01584fa  cmp     byte ptr [rdi+70h], 0
0x1c01584fe  jnz     short loc_1C0158508
0x1c0158500  mov     rdx, rdi
0x1c0158503  call    PplpLazyInitializeLookasideList
0x1c0158508  inc     dword ptr [rdi+14h]
0x1c015850b  mov     rcx, rdi; ListHead
0x1c015850e  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0158515  nop     dword ptr [rax+rax+00h]
0x1c015851a  mov     rbx, rax
0x1c015851d  test    rax, rax
0x1c0158520  jnz     short loc_1C015853F
0x1c0158522  mov     r8d, [rdi+28h]
0x1c0158526  mov     r9, rdi
0x1c0158529  mov     edx, [rdi+2Ch]
0x1c015852c  mov     ecx, [rdi+24h]
0x1c015852f  mov     rax, [rdi+30h]
0x1c0158533  inc     dword ptr [rdi+18h]
0x1c0158536  call    cs:__guard_dispatch_icall_fptr
0x1c015853c  mov     rbx, rax
0x1c015853f  mov     edi, cs:UxSslReceiverBufferSize
0x1c0158545  mov     eax, 1
0x1c015854a  jmp     loc_1C0157B03
0x1c015854f  lea     eax, [rdi+38h]
0x1c0158552  cmp     edi, eax
0x1c0158554  ja      short loc_1C015857B
0x1c0158556  mov     edx, edi
0x1c0158558  xor     r9d, r9d; Priority
0x1c015855b  add     rdx, 38h ; '8'; NumberOfBytes
0x1c015855f  mov     ecx, 200h; PoolType
0x1c0158564  mov     r8d, 42537855h; Tag
0x1c015856a  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c0158571  nop     dword ptr [rax+rax+00h]
0x1c0158576  mov     rbx, rax
0x1c0158579  jmp     short loc_1C015857D
0x1c015857b  xor     ebx, ebx
0x1c015857d  mov     eax, 2
0x1c0158582  jmp     loc_1C0157B03
0x1c0158587  mov     eax, [rsi+30h]
0x1c015858a  mov     [rbx+30h], eax
0x1c015858d  mov     r8d, [rsi+30h]; Size
0x1c0158591  mov     rdx, [rsi+28h]; Src
0x1c0158595  call    memmove
0x1c015859a  nop
0x1c015859b  jmp     loc_1C0157B40
```
