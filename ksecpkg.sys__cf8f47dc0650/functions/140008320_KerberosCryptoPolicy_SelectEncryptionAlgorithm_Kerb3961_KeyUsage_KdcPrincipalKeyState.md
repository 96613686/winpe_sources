# KerberosCryptoPolicy::SelectEncryptionAlgorithm(Kerb3961::KeyUsage,KdcPrincipalKeyState)

- ea: `0x140008320`
- end: `0x1400083d2`
- name: `?SelectEncryptionAlgorithm@KerberosCryptoPolicy@@QEAAPEAUEncryptionAlgorithm@Kerb3961@@W4KeyUsage@3@W4KdcPrincipalKeyState@@@Z`
- size: `178`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000561c`
- `0x140005bc4`
- `0x140007600`
- `0x1400078f8`

## callees

- `0x140008248`
- `0x140008320`
- `0x1400083d8`
- `0x140010240`

## pseudocode

```c
__int64 __fastcall KerberosCryptoPolicy::SelectEncryptionAlgorithm(__int64 a1, __int64 a2)
{
  unsigned int *v2; // rax
  __int64 v5; // rdi
  __int64 v6; // r9
  __int64 *v7; // rcx
  __int64 (__fastcall *v8)(__int64 *, _BYTE *, __int64, __int64, __int128 *); // r10
  __int64 v9; // rax
  __int128 *v10; // rax
  _BYTE v12[24]; // [rsp+30h] [rbp-18h] BYREF

  v2 = *(unsigned int **)(a1 + 112);
  if ( v2 && *v2 )
  {
    v5 = KerberosCryptoPolicy::OpenEncryptionAlgorithm((__int64 **)a1, *v2, a2);
  }
  else
  {
    v6 = a1 + 16;
    v7 = *(__int64 **)a1;
    v8 = *(__int64 (__fastcall **)(__int64 *, _BYTE *, __int64, __int64, __int128 *))(*v7 + 152);
    if ( (`KerberosCryptoPolicy::GetSecondPartner'::`2'::`local static guard' & 1) == 0 )
    {
      `KerberosCryptoPolicy::GetSecondPartner'::`2'::`local static guard' |= 1u;
      `KerberosCryptoPolicy::GetSecondPartner'::`2'::none = 0;
    }
    v9 = *(_QWORD *)(a1 + 48);
    if ( v9 )
      v10 = (__int128 *)(v9 + 16);
    else
      v10 = &`KerberosCryptoPolicy::GetSecondPartner'::`2'::none;
    v5 = *(_QWORD *)v8(v7, v12, a2, v6, v10);
  }
  if ( !v5 )
    KerberosCryptoPolicy::TraceKeyUsageRequirements(a1, a2);
  return v5;
}

```

## disassembly

```asm
0x140008320  mov     [rsp+arg_0], rbx
0x140008325  mov     [rsp+arg_8], rsi
0x14000832a  push    rdi
0x14000832b  sub     rsp, 40h
0x14000832f  mov     rax, [rcx+70h]
0x140008333  mov     rsi, rdx
0x140008336  mov     rbx, rcx
0x140008339  test    rax, rax
0x14000833c  jz      short loc_140008351
0x14000833e  mov     edx, [rax]
0x140008340  test    edx, edx
0x140008342  jz      short loc_140008351
0x140008344  mov     r8, rsi
0x140008347  call    ?OpenEncryptionAlgorithm@KerberosCryptoPolicy@@QEBAPEAUEncryptionAlgorithm@Kerb3961@@KW4KeyUsage@3@@Z; KerberosCryptoPolicy::OpenEncryptionAlgorithm(ulong,Kerb3961::KeyUsage)
0x14000834c  mov     rdi, rax
0x14000834f  jmp     short loc_1400083AE
0x140008351  lea     r9, [rcx+10h]
0x140008355  mov     rcx, [rcx]
0x140008358  mov     rax, [rcx]
0x14000835b  mov     r10, [rax+98h]
0x140008362  mov     eax, cs:??_B?1??GetSecondPartner@KerberosCryptoPolicy@@AEAAAEAUCipherPartnerHandle@Kerb3961@@XZ@51; `KerberosCryptoPolicy::GetSecondPartner(void)'::`2'::`local static guard'{2}'
0x140008368  test    al, 1
0x14000836a  jnz     short loc_140008380
0x14000836c  or      eax, 1
0x14000836f  xorps   xmm0, xmm0
0x140008372  mov     cs:??_B?1??GetSecondPartner@KerberosCryptoPolicy@@AEAAAEAUCipherPartnerHandle@Kerb3961@@XZ@51, eax; `KerberosCryptoPolicy::GetSecondPartner(void)'::`2'::`local static guard'{2}'
0x140008378  movdqu  cs:?none@?1??GetSecondPartner@KerberosCryptoPolicy@@AEAAAEAUCipherPartnerHandle@Kerb3961@@XZ@4U34@A, xmm0; Kerb3961::CipherPartnerHandle `KerberosCryptoPolicy::GetSecondPartner(void)'::`2'::none
0x140008380  mov     rax, [rbx+30h]
0x140008384  test    rax, rax
0x140008387  jz      short loc_14000838F
0x140008389  add     rax, 10h
0x14000838d  jmp     short loc_140008396
0x14000838f  lea     rax, ?none@?1??GetSecondPartner@KerberosCryptoPolicy@@AEAAAEAUCipherPartnerHandle@Kerb3961@@XZ@4U34@A; Kerb3961::CipherPartnerHandle `KerberosCryptoPolicy::GetSecondPartner(void)'::`2'::none
0x140008396  mov     [rsp+48h+var_28], rax
0x14000839b  lea     rdx, [rsp+48h+var_18]
0x1400083a0  mov     rax, r10
0x1400083a3  mov     r8, rsi
0x1400083a6  call    _guard_dispatch_icall
0x1400083ab  mov     rdi, [rax]
0x1400083ae  test    rdi, rdi
0x1400083b1  jnz     short loc_1400083BE
0x1400083b3  mov     rdx, rsi
0x1400083b6  mov     rcx, rbx
0x1400083b9  call    ?TraceKeyUsageRequirements@KerberosCryptoPolicy@@AEBAXW4KeyUsage@Kerb3961@@PEBD@Z; KerberosCryptoPolicy::TraceKeyUsageRequirements(Kerb3961::KeyUsage,char const *)
0x1400083be  mov     rbx, [rsp+48h+arg_0]
0x1400083c3  mov     rax, rdi
0x1400083c6  mov     rsi, [rsp+48h+arg_8]
0x1400083cb  add     rsp, 40h
0x1400083cf  pop     rdi
0x1400083d0  retn
```
