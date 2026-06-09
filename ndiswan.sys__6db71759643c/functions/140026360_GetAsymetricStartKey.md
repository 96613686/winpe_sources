# GetAsymetricStartKey

- ea: `0x140026360`
- end: `0x14002645e`
- name: `GetAsymetricStartKey`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400247c4`

## callees

- `0x140008ffc`
- `0x140009120`
- `0x1400091a0`
- `0x1400161f0`
- `0x140016400`
- `0x140026360`

## string_xrefs

- `0x140026390`: `On the client side, this is the send key; on the server side, it is the receive key.`
- `0x14002637b`: `On the client side, this is the receive key; on the server side, it is the send key.`

## pseudocode

```c
void *__fastcall GetAsymetricStartKey(__int64 a1, char a2)
{
  const char *v2; // rbx
  BCRYPT_HASH_HANDLE *v3; // rsi
  int v4; // r8d
  const char *v5; // rax
  __int64 v7; // r8
  __int128 Src; // [rsp+20h] [rbp-48h] BYREF
  int v10; // [rsp+30h] [rbp-38h]

  v2 = "On the client side, this is the receive key; on the server side, it is the send key.";
  v3 = *(BCRYPT_HASH_HANDLE **)(a1 + 40);
  v4 = *(_DWORD *)a1 & 1;
  v10 = 0;
  v5 = "On the client side, this is the send key; on the server side, it is the receive key.";
  Src = 0;
  if ( a2 )
  {
    if ( !v4 )
      v2 = "On the client side, this is the send key; on the server side, it is the receive key.";
  }
  else
  {
    if ( !v4 )
      v5 = "On the client side, this is the receive key; on the server side, it is the send key.";
    v2 = v5;
  }
  CngRsa32Compat_SHAInit_Ex(v3);
  CngRsa32Compat_SHAUpdate_Ex(v3, a1 + 4, 16);
  CngRsa32Compat_SHAUpdate_Ex(v3, &SHApad1, 40);
  v7 = -1;
  do
    ++v7;
  while ( v2[v7] );
  CngRsa32Compat_SHAUpdate_Ex(v3, v2, v7);
  CngRsa32Compat_SHAUpdate_Ex(v3, &SHApad2, 40);
  CngRsa32Compat_SHAFinal_Ex(v3, &Src);
  memmove((void *)(a1 + 4), &Src, *(unsigned int *)(a1 + 36));
  return memmove((void *)(a1 + 20), &Src, *(unsigned int *)(a1 + 36));
}

```

## disassembly

```asm
0x140026360  push    rbx
0x140026362  push    rbp
0x140026363  push    rsi
0x140026364  push    rdi
0x140026365  sub     rsp, 48h
0x140026369  mov     rax, cs:__security_cookie
0x140026370  xor     rax, rsp
0x140026373  mov     [rsp+68h+var_30], rax
0x140026378  mov     r8d, [rcx]
0x14002637b  lea     rbx, aOnTheClientSid; "On the client side, this is the receive"...
0x140026382  mov     rsi, [rcx+28h]
0x140026386  xor     eax, eax
0x140026388  and     r8d, 1
0x14002638c  mov     [rsp+68h+var_38], eax
0x140026390  lea     rax, aOnTheClientSid_0; "On the client side, this is the send ke"...
0x140026397  xorps   xmm0, xmm0
0x14002639a  mov     rdi, rcx
0x14002639d  movups  [rsp+68h+Src], xmm0
0x1400263a2  test    dl, dl
0x1400263a4  jz      short loc_1400263AF
0x1400263a6  test    r8d, r8d
0x1400263a9  cmovz   rbx, rax
0x1400263ad  jmp     short loc_1400263B9
0x1400263af  test    r8d, r8d
0x1400263b2  cmovz   rax, rbx
0x1400263b6  mov     rbx, rax
0x1400263b9  mov     rcx, rsi; phHash
0x1400263bc  call    CngRsa32Compat_SHAInit_Ex
0x1400263c1  mov     r8d, 10h
0x1400263c7  lea     rdx, [rdi+4]
0x1400263cb  mov     rcx, rsi
0x1400263ce  call    CngRsa32Compat_SHAUpdate_Ex
0x1400263d3  mov     r8d, 28h ; '('
0x1400263d9  lea     rdx, SHApad1
0x1400263e0  mov     rcx, rsi
0x1400263e3  call    CngRsa32Compat_SHAUpdate_Ex
0x1400263e8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400263ec  inc     r8
0x1400263ef  cmp     byte ptr [rbx+r8], 0
0x1400263f4  jnz     short loc_1400263EC
0x1400263f6  mov     rdx, rbx
0x1400263f9  mov     rcx, rsi
0x1400263fc  call    CngRsa32Compat_SHAUpdate_Ex
0x140026401  mov     r8d, 28h ; '('
0x140026407  lea     rdx, SHApad2
0x14002640e  mov     rcx, rsi
0x140026411  call    CngRsa32Compat_SHAUpdate_Ex
0x140026416  lea     rdx, [rsp+68h+Src]
0x14002641b  mov     rcx, rsi
0x14002641e  call    CngRsa32Compat_SHAFinal_Ex
0x140026423  mov     r8d, [rdi+24h]; Size
0x140026427  lea     rdx, [rsp+68h+Src]; Src
0x14002642c  lea     rcx, [rdi+4]; void *
0x140026430  call    memmove
0x140026435  mov     r8d, [rdi+24h]; Size
0x140026439  lea     rcx, [rdi+14h]; void *
0x14002643d  lea     rdx, [rsp+68h+Src]; Src
0x140026442  call    memmove
0x140026447  mov     rcx, [rsp+68h+var_30]
0x14002644c  xor     rcx, rsp; StackCookie
0x14002644f  call    __security_check_cookie
0x140026454  add     rsp, 48h
0x140026458  pop     rdi
0x140026459  pop     rsi
0x14002645a  pop     rbp
0x14002645b  pop     rbx
0x14002645c  retn
```
