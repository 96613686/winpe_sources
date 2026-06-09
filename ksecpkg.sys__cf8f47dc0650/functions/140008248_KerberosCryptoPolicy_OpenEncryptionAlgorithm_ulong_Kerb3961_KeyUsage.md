# KerberosCryptoPolicy::OpenEncryptionAlgorithm(ulong,Kerb3961::KeyUsage)

- ea: `0x140008248`
- end: `0x140008318`
- name: `?OpenEncryptionAlgorithm@KerberosCryptoPolicy@@QEBAPEAUEncryptionAlgorithm@Kerb3961@@KW4KeyUsage@3@@Z`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140008320`

## callees

- `0x140008248`
- `0x1400083d8`
- `0x140010240`

## pseudocode

```c
__int64 __fastcall KerberosCryptoPolicy::OpenEncryptionAlgorithm(__int64 **a1, unsigned int a2, __int64 a3)
{
  bool v5; // al
  __int64 *v6; // r10
  __int64 v7; // rcx
  __int64 *v8; // rax
  __int64 (__fastcall *v9)(__int64 *, _BYTE *, _QWORD, __int64, __int64, __int128 *); // r11
  __int64 *v10; // rax
  __int128 *v11; // rax
  __int64 v12; // rdi
  _BYTE v14[24]; // [rsp+40h] [rbp-18h] BYREF

  v5 = KerberosCryptoPolicy::isolatedMode || *((_BYTE *)a1 + 8);
  v6 = *a1;
  v7 = **a1;
  if ( v5 )
  {
    v8 = (__int64 *)(*(__int64 (__fastcall **)(__int64 *, _BYTE *, _QWORD, __int64))(v7 + 120))(v6, v14, a2, a3);
  }
  else
  {
    v9 = *(__int64 (__fastcall **)(__int64 *, _BYTE *, _QWORD, __int64, __int64, __int128 *))(v7 + 104);
    if ( (`KerberosCryptoPolicy::GetSecondPartner'::`2'::`local static guard' & 1) == 0 )
    {
      `KerberosCryptoPolicy::GetSecondPartner'::`2'::`local static guard' |= 1u;
      `KerberosCryptoPolicy::GetSecondPartner'::`2'::none = 0;
    }
    v10 = a1[6];
    if ( v10 )
      v11 = (__int128 *)(v10 + 2);
    else
      v11 = &`KerberosCryptoPolicy::GetSecondPartner'::`2'::none;
    v8 = (__int64 *)v9(v6, v14, a2, a3, (__int64)(a1 + 2), v11);
  }
  v12 = *v8;
  if ( !*v8 )
    KerberosCryptoPolicy::TraceKeyUsageRequirements(a1, a3);
  return v12;
}

```

## disassembly

```asm
0x140008248  mov     [rsp+arg_0], rbx
0x14000824d  mov     [rsp+arg_8], rsi
0x140008252  push    rdi
0x140008253  sub     rsp, 50h
0x140008257  cmp     cs:?isolatedMode@KerberosCryptoPolicy@@0_NA, 0; bool KerberosCryptoPolicy::isolatedMode
0x14000825e  mov     rsi, r8
0x140008261  mov     rbx, rcx
0x140008264  jnz     short loc_140008270
0x140008266  cmp     byte ptr [rcx+8], 0
0x14000826a  jnz     short loc_140008270
0x14000826c  xor     al, al
0x14000826e  jmp     short loc_140008272
0x140008270  mov     al, 1
0x140008272  mov     r10, [rcx]
0x140008275  mov     rcx, [r10]
0x140008278  test    al, al
0x14000827a  jz      short loc_140008295
0x14000827c  mov     rax, [rcx+78h]
0x140008280  mov     r8d, edx
0x140008283  lea     rdx, [rsp+58h+var_18]
0x140008288  mov     rcx, r10
0x14000828b  mov     r9, rsi
0x14000828e  call    _guard_dispatch_icall
0x140008293  jmp     short loc_1400082F1
0x140008295  mov     eax, cs:??_B?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@51; `KerberosCryptoPolicy::GetSecondPartner(void)'::`2'::`local static guard'{2}'
0x14000829b  mov     r11, [rcx+68h]
0x14000829f  test    al, 1
0x1400082a1  jnz     short loc_1400082B7
0x1400082a3  or      eax, 1
0x1400082a6  xorps   xmm0, xmm0
0x1400082a9  mov     cs:??_B?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@51, eax; `KerberosCryptoPolicy::GetSecondPartner(void)'::`2'::`local static guard'{2}'
0x1400082af  movdqu  cs:?none@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@4U34@A, xmm0; Kerb3961::CipherPartnerHandle `KerberosCryptoPolicy::GetSecondPartner(void)'::`2'::none
0x1400082b7  mov     rax, [rbx+30h]
0x1400082bb  test    rax, rax
0x1400082be  jz      short loc_1400082C6
0x1400082c0  add     rax, 10h
0x1400082c4  jmp     short loc_1400082CD
0x1400082c6  lea     rax, ?none@?1??GetSecondPartner@KerberosCryptoPolicy@@AEBAAEBUCipherPartnerHandle@Kerb3961@@XZ@4U34@A; Kerb3961::CipherPartnerHandle `KerberosCryptoPolicy::GetSecondPartner(void)'::`2'::none
0x1400082cd  mov     [rsp+58h+var_30], rax
0x1400082d2  lea     rcx, [rbx+10h]
0x1400082d6  mov     [rsp+58h+var_38], rcx
0x1400082db  mov     r8d, edx
0x1400082de  mov     rcx, r10
0x1400082e1  lea     rdx, [rsp+58h+var_18]
0x1400082e6  mov     r9, rsi
0x1400082e9  mov     rax, r11
0x1400082ec  call    _guard_dispatch_icall
0x1400082f1  mov     rdi, [rax]
0x1400082f4  test    rdi, rdi
0x1400082f7  jnz     short loc_140008304
0x1400082f9  mov     rdx, rsi
0x1400082fc  mov     rcx, rbx
0x1400082ff  call    ?TraceKeyUsageRequirements@KerberosCryptoPolicy@@AEBAXW4KeyUsage@Kerb3961@@PEBD@Z; KerberosCryptoPolicy::TraceKeyUsageRequirements(Kerb3961::KeyUsage,char const *)
0x140008304  mov     rbx, [rsp+58h+arg_0]
0x140008309  mov     rax, rdi
0x14000830c  mov     rsi, [rsp+58h+arg_8]
0x140008311  add     rsp, 50h
0x140008315  pop     rdi
0x140008316  retn
```
