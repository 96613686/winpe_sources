# GenerateShaHashForMsChapV2Key

- ea: `0x1400100ac`
- end: `0x14001024d`
- name: `GenerateShaHashForMsChapV2Key`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140010040`

## callees

- `0x140002c84`
- `0x140002cd8`
- `0x140002d28`
- `0x140005e10`
- `0x1400100ac`

## string_xrefs

- `0x140010189`: `On the client side, this is the send key; on the server side, it is the receive key.`
- `0x140010190`: `On the client side, this is the receive key; on the server side, it is the send key.`

## pseudocode

```c
__int64 __fastcall GenerateShaHashForMsChapV2Key(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _OWORD *a5,
        int a6,
        char a7,
        char a8)
{
  const char *v10; // rax
  const char *v11; // rbx
  __int64 v12; // r8
  __int64 result; // rax
  BCRYPT_HASH_HANDLE phHash; // [rsp+20h] [rbp-59h] BYREF
  _QWORD v15[5]; // [rsp+28h] [rbp-51h] BYREF
  _DWORD v16[10]; // [rsp+50h] [rbp-29h] BYREF
  __int128 v17; // [rsp+78h] [rbp-1h] BYREF

  memset(v15, 0, sizeof(v15));
  phHash = 0;
  memset(v16, 242, sizeof(v16));
  CngRsa32Compat_SHAInit(&phHash);
  CngRsa32Compat_SHAUpdate(&phHash, a1, 16);
  CngRsa32Compat_SHAUpdate(&phHash, a3, 24);
  CngRsa32Compat_SHAUpdate(&phHash, "This is the MPPE Master Key", 27);
  CngRsa32Compat_SHAFinal(&phHash, &v17);
  v10 = "On the client side, this is the send key; on the server side, it is the receive key.";
  v11 = "On the client side, this is the receive key; on the server side, it is the send key.";
  *a5 = v17;
  if ( a8 )
  {
    if ( !a7 )
      v11 = "On the client side, this is the send key; on the server side, it is the receive key.";
  }
  else
  {
    if ( !a7 )
      v10 = "On the client side, this is the receive key; on the server side, it is the send key.";
    v11 = v10;
  }
  CngRsa32Compat_SHAInit(&phHash);
  CngRsa32Compat_SHAUpdate(&phHash, a5, 16);
  CngRsa32Compat_SHAUpdate(&phHash, v15, 40);
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  CngRsa32Compat_SHAUpdate(&phHash, v11, v12);
  CngRsa32Compat_SHAUpdate(&phHash, v16, 40);
  result = CngRsa32Compat_SHAFinal(&phHash, &v17);
  *a5 = v17;
  return result;
}

```

## disassembly

```asm
0x1400100ac  mov     [rsp-8+arg_8], rbx
0x1400100b1  mov     [rsp-8+arg_18], rsi
0x1400100b6  push    rbp
0x1400100b7  push    rdi
0x1400100b8  push    r14
0x1400100ba  lea     rbp, [rsp-27h]
0x1400100bf  sub     rsp, 0A0h
0x1400100c6  mov     rax, cs:__security_cookie
0x1400100cd  xor     rax, rsp
0x1400100d0  mov     [rbp+37h+var_20], rax
0x1400100d4  mov     rsi, [rbp+37h+arg_20]
0x1400100d8  xor     r14d, r14d
0x1400100db  mov     rbx, rcx
0x1400100de  mov     [rbp+37h+var_88], r14
0x1400100e2  lea     rcx, [rbp+37h+phHash]; phHash
0x1400100e6  mov     [rbp+37h+var_80], r14
0x1400100ea  mov     [rbp+37h+var_78], r14
0x1400100ee  mov     rdi, r8
0x1400100f1  mov     [rbp+37h+var_70], r14
0x1400100f5  mov     [rbp+37h+var_68], r14
0x1400100f9  mov     [rbp+37h+phHash], r14
0x1400100fd  mov     [rbp+37h+var_60], 0F2F2F2F2h
0x140010104  mov     [rbp+37h+var_5C], 0F2F2F2F2h
0x14001010b  mov     [rbp+37h+var_58], 0F2F2F2F2h
0x140010112  mov     [rbp+37h+var_54], 0F2F2F2F2h
0x140010119  mov     [rbp+37h+var_50], 0F2F2F2F2h
0x140010120  mov     [rbp+37h+var_4C], 0F2F2F2F2h
0x140010127  mov     [rbp+37h+var_48], 0F2F2F2F2h
0x14001012e  mov     [rbp+37h+var_44], 0F2F2F2F2h
0x140010135  mov     [rbp+37h+var_40], 0F2F2F2F2h
0x14001013c  mov     [rbp+37h+var_3C], 0F2F2F2F2h
0x140010143  call    CngRsa32Compat_SHAInit
0x140010148  lea     r8d, [r14+10h]
0x14001014c  mov     rdx, rbx
0x14001014f  lea     rcx, [rbp+37h+phHash]
0x140010153  call    CngRsa32Compat_SHAUpdate
0x140010158  lea     r8d, [r14+18h]
0x14001015c  mov     rdx, rdi
0x14001015f  lea     rcx, [rbp+37h+phHash]
0x140010163  call    CngRsa32Compat_SHAUpdate
0x140010168  lea     r8d, [r14+1Bh]
0x14001016c  lea     rdx, aThisIsTheMppeM; "This is the MPPE Master Key"
0x140010173  lea     rcx, [rbp+37h+phHash]
0x140010177  call    CngRsa32Compat_SHAUpdate
0x14001017c  lea     rdx, [rbp+37h+var_38]
0x140010180  lea     rcx, [rbp+37h+phHash]
0x140010184  call    CngRsa32Compat_SHAFinal
0x140010189  lea     rax, aOnTheClientSid_0; "On the client side, this is the send ke"...
0x140010190  lea     rbx, aOnTheClientSid; "On the client side, this is the receive"...
0x140010197  movups  xmm0, [rbp+37h+var_38]
0x14001019b  movdqu  xmmword ptr [rsi], xmm0
0x14001019f  cmp     [rbp+37h+arg_38], r14b
0x1400101a3  jz      short loc_1400101AF
0x1400101a5  cmp     [rbp+37h+arg_30], r14b
0x1400101a9  cmovz   rbx, rax
0x1400101ad  jmp     short loc_1400101BA
0x1400101af  cmp     [rbp+37h+arg_30], r14b
0x1400101b3  cmovz   rax, rbx
0x1400101b7  mov     rbx, rax
0x1400101ba  lea     rcx, [rbp+37h+phHash]; phHash
0x1400101be  call    CngRsa32Compat_SHAInit
0x1400101c3  mov     r8d, 10h
0x1400101c9  lea     rcx, [rbp+37h+phHash]
0x1400101cd  mov     rdx, rsi
0x1400101d0  call    CngRsa32Compat_SHAUpdate
0x1400101d5  mov     edi, 28h ; '('
0x1400101da  lea     rdx, [rbp+37h+var_88]
0x1400101de  mov     r8d, edi
0x1400101e1  lea     rcx, [rbp+37h+phHash]
0x1400101e5  call    CngRsa32Compat_SHAUpdate
0x1400101ea  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400101ee  inc     r8
0x1400101f1  cmp     [rbx+r8], r14b
0x1400101f5  jnz     short loc_1400101EE
0x1400101f7  mov     rdx, rbx
0x1400101fa  lea     rcx, [rbp+37h+phHash]
0x1400101fe  call    CngRsa32Compat_SHAUpdate
0x140010203  mov     r8d, edi
0x140010206  lea     rdx, [rbp+37h+var_60]
0x14001020a  lea     rcx, [rbp+37h+phHash]
0x14001020e  call    CngRsa32Compat_SHAUpdate
0x140010213  lea     rdx, [rbp+37h+var_38]
0x140010217  lea     rcx, [rbp+37h+phHash]
0x14001021b  call    CngRsa32Compat_SHAFinal
0x140010220  movups  xmm0, [rbp+37h+var_38]
0x140010224  movdqu  xmmword ptr [rsi], xmm0
0x140010228  mov     rcx, [rbp+37h+var_20]
0x14001022c  xor     rcx, rsp; StackCookie
0x14001022f  call    __security_check_cookie
0x140010234  lea     r11, [rsp+0B0h+var_10]
0x14001023c  mov     rbx, [r11+28h]
0x140010240  mov     rsi, [r11+38h]
0x140010244  mov     rsp, r11
0x140010247  pop     r14
0x140010249  pop     rdi
0x14001024a  pop     rbp
0x14001024b  retn
```
