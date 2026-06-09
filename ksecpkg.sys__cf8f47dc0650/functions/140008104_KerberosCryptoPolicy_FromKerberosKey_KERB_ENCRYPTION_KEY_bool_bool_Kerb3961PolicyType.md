# KerberosCryptoPolicy::FromKerberosKey(_KERB_ENCRYPTION_KEY *,bool,bool,Kerb3961PolicyType)

- ea: `0x140008104`
- end: `0x14000819e`
- name: `?FromKerberosKey@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@PEAU_KERB_ENCRYPTION_KEY@@_N1W4Kerb3961PolicyType@@@Z`
- size: `154`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000561c`
- `0x140005bc4`
- `0x140007600`
- `0x1400078f8`

## callees

- `0x140005ff8`
- `0x14000755c`
- `0x140007f68`
- `0x140008104`
- `0x1400086e0`

## pseudocode

```c
_QWORD *__fastcall KerberosCryptoPolicy::FromKerberosKey(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rdi
  __int64 v6; // rcx
  _BYTE v8[8]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v9; // [rsp+28h] [rbp-10h]
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    KerberosCryptoPolicy::Create(&v10);
    v5 = v10;
    if ( v10 )
    {
      v6 = *(_QWORD *)(v10 + 112);
      v8[0] = 0;
      v9 = 0;
      *(_QWORD *)(v10 + 112) = a2;
      if ( v6 && *(_BYTE *)(v5 + 104) )
        KerbFreeKey(v6, v4);
      *(_BYTE *)(v5 + 104) = 0;
      utl::unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>::~unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>(v8);
      *(_BYTE *)(v5 + 8) = 1;
      *a1 = v5;
      v10 = 0;
    }
    else
    {
      *a1 = 0;
    }
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v10);
  }
  else
  {
    *a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x140008104  mov     [rsp+arg_0], rbx
0x140008109  mov     [rsp+arg_10], rsi
0x14000810e  push    rdi
0x14000810f  sub     rsp, 30h
0x140008113  mov     rsi, rdx
0x140008116  mov     rbx, rcx
0x140008119  test    rdx, rdx
0x14000811c  jnz     short loc_140008123
0x14000811e  mov     [rcx], rdx
0x140008121  jmp     short loc_14000818A
0x140008123  lea     rcx, [rsp+38h+arg_8]
0x140008128  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x14000812d  mov     rdi, [rsp+38h+arg_8]
0x140008132  test    rdi, rdi
0x140008135  jnz     short loc_14000813C
0x140008137  mov     [rbx], rdi
0x14000813a  jmp     short loc_140008180
0x14000813c  mov     rcx, [rdi+70h]
0x140008140  mov     [rsp+38h+var_18], 0
0x140008145  mov     [rsp+38h+var_10], 0
0x14000814e  mov     [rdi+70h], rsi
0x140008152  test    rcx, rcx
0x140008155  jz      short loc_140008162
0x140008157  cmp     byte ptr [rdi+68h], 0
0x14000815b  jz      short loc_140008162
0x14000815d  call    KerbFreeKey
0x140008162  lea     rcx, [rsp+38h+var_18]
0x140008167  mov     byte ptr [rdi+68h], 0
0x14000816b  call    ??1?$unique_ptr@U_KERB_ENCRYPTION_KEY@@UEncryptionKeyDeleter@KerberosCryptoPolicy@@@utl@@QEAA@XZ; utl::unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>::~unique_ptr<_KERB_ENCRYPTION_KEY,KerberosCryptoPolicy::EncryptionKeyDeleter>(void)
0x140008170  mov     byte ptr [rdi+8], 1
0x140008174  mov     [rbx], rdi
0x140008177  mov     [rsp+38h+arg_8], 0
0x140008180  lea     rcx, [rsp+38h+arg_8]
0x140008185  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x14000818a  mov     rsi, [rsp+38h+arg_10]
0x14000818f  mov     rax, rbx
0x140008192  mov     rbx, [rsp+38h+arg_0]
0x140008197  add     rsp, 30h
0x14000819b  pop     rdi
0x14000819c  retn
```
