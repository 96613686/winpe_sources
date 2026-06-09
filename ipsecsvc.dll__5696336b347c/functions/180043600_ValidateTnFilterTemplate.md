# ValidateTnFilterTemplate

- ea: `0x180043600`
- end: `0x18004375e`
- name: `ValidateTnFilterTemplate`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180034b38`

## callees

- `0x180043480`
- `0x180043588`
- `0x180043600`
- `0x1800438f0`
- `0x180043918`
- `0x180043940`
- `0x18004397c`
- `0x180043a54`
- `0x180043eb4`

## pseudocode

```c
__int64 __fastcall ValidateTnFilterTemplate(__int64 a1)
{
  __int128 *v2; // rdi
  bool v3; // zf
  __int64 v4; // rcx
  __int64 result; // rax
  __int64 v6; // xmm1_8
  __int128 v7; // xmm0
  __int64 v8; // xmm1_8
  int v9; // ecx
  __int128 v10; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+30h] [rbp-38h]
  __int128 v12; // [rsp+40h] [rbp-28h] BYREF
  __int64 v13; // [rsp+50h] [rbp-18h]

  if ( !a1 )
    return 87;
  v2 = (__int128 *)(a1 + 48);
  v3 = *(_DWORD *)a1 == 0;
  v4 = a1 + 48;
  if ( v3 )
  {
    result = VerifyV4Addresses(v4);
    if ( (_DWORD)result )
      return result;
    result = VerifyV4Addresses(a1 + 80);
    if ( (_DWORD)result )
      return result;
    v6 = *(_QWORD *)(a1 + 96);
    v10 = *(_OWORD *)(a1 + 80);
    v7 = *v2;
    v11 = v6;
    v8 = *((_QWORD *)v2 + 2);
    v12 = v7;
    v13 = v8;
    if ( !(unsigned int)HtoNAddressesConflict(&v12, &v10) )
    {
      result = ValidateV4Addr(a1 + 136);
      if ( (_DWORD)result )
        return result;
      result = VerifyV4Addresses(a1 + 168);
      goto LABEL_13;
    }
    return 87;
  }
  result = VerifyV6Addresses(v4);
  if ( (_DWORD)result )
    return result;
  result = VerifyV6Addresses(a1 + 80);
  if ( (_DWORD)result )
    return result;
  if ( (unsigned int)V6AddressesConflict(v2, a1 + 80) )
    return 87;
  result = ValidateV6Addr(a1 + 136);
  if ( (_DWORD)result )
    return result;
  result = VerifyV6Addresses(a1 + 168);
LABEL_13:
  if ( !(_DWORD)result )
  {
    result = VerifyProtocols(*(_QWORD *)(a1 + 112));
    if ( !(_DWORD)result )
    {
      result = VerifyPortsForProtocol(*(_QWORD *)(a1 + 120), *(_QWORD *)(a1 + 112));
      if ( !(_DWORD)result )
      {
        result = VerifyPortsForProtocol(*(_QWORD *)(a1 + 128), *(_QWORD *)(a1 + 112));
        if ( !(_DWORD)result )
        {
          v9 = *(_DWORD *)(a1 + 208);
          if ( (v9 & 0xFFFFFFF3) != 0 || v9 == 12 )
            return 87;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180043600  mov     [rsp+arg_0], rbx
0x180043605  mov     [rsp+arg_8], rsi
0x18004360a  push    rdi
0x18004360b  sub     rsp, 60h
0x18004360f  mov     rbx, rcx
0x180043612  test    rcx, rcx
0x180043615  jz      loc_180043749
0x18004361b  xor     r8d, r8d
0x18004361e  lea     rdi, [rcx+30h]
0x180043622  cmp     [rcx], r8d
0x180043625  mov     rcx, rdi
0x180043628  jnz     loc_1800436B3
0x18004362e  call    VerifyV4Addresses
0x180043633  test    eax, eax
0x180043635  jnz     loc_18004374E
0x18004363b  lea     r8d, [rax+1]
0x18004363f  lea     rcx, [rbx+50h]
0x180043643  call    VerifyV4Addresses
0x180043648  test    eax, eax
0x18004364a  jnz     loc_18004374E
0x180043650  movups  xmm0, xmmword ptr [rbx+50h]
0x180043654  lea     rdx, [rsp+68h+var_48]
0x180043659  movsd   xmm1, qword ptr [rbx+60h]
0x18004365e  lea     rcx, [rsp+68h+var_28]
0x180043663  movaps  [rsp+68h+var_48], xmm0
0x180043668  movups  xmm0, xmmword ptr [rdi]
0x18004366b  movsd   [rsp+68h+var_38], xmm1
0x180043671  movsd   xmm1, qword ptr [rdi+10h]
0x180043676  movaps  [rsp+68h+var_28], xmm0
0x18004367b  movsd   [rsp+68h+var_18], xmm1
0x180043681  call    HtoNAddressesConflict
0x180043686  test    eax, eax
0x180043688  jnz     loc_180043749
0x18004368e  lea     rcx, [rbx+88h]
0x180043695  call    ValidateV4Addr
0x18004369a  test    eax, eax
0x18004369c  jnz     loc_18004374E
0x1800436a2  lea     rcx, [rbx+0A8h]
0x1800436a9  xor     r8d, r8d
0x1800436ac  call    VerifyV4Addresses
0x1800436b1  jmp     short loc_180043700
0x1800436b3  call    VerifyV6Addresses
0x1800436b8  test    eax, eax
0x1800436ba  jnz     loc_18004374E
0x1800436c0  lea     r8d, [rax+1]
0x1800436c4  lea     rcx, [rbx+50h]
0x1800436c8  call    VerifyV6Addresses
0x1800436cd  test    eax, eax
0x1800436cf  jnz     short loc_18004374E
0x1800436d1  lea     rdx, [rbx+50h]
0x1800436d5  mov     rcx, rdi
0x1800436d8  call    V6AddressesConflict
0x1800436dd  test    eax, eax
0x1800436df  jnz     short loc_180043749
0x1800436e1  lea     rcx, [rbx+88h]
0x1800436e8  call    ValidateV6Addr
0x1800436ed  test    eax, eax
0x1800436ef  jnz     short loc_18004374E
0x1800436f1  lea     rcx, [rbx+0A8h]
0x1800436f8  xor     r8d, r8d
0x1800436fb  call    VerifyV6Addresses
0x180043700  test    eax, eax
0x180043702  jnz     short loc_18004374E
0x180043704  mov     rcx, [rbx+70h]
0x180043708  call    VerifyProtocols
0x18004370d  test    eax, eax
0x18004370f  jnz     short loc_18004374E
0x180043711  mov     rdx, [rbx+70h]
0x180043715  mov     rcx, [rbx+78h]
0x180043719  call    VerifyPortsForProtocol
0x18004371e  test    eax, eax
0x180043720  jnz     short loc_18004374E
0x180043722  mov     rdx, [rbx+70h]
0x180043726  mov     rcx, [rbx+80h]
0x18004372d  call    VerifyPortsForProtocol
0x180043732  test    eax, eax
0x180043734  jnz     short loc_18004374E
0x180043736  mov     ecx, [rbx+0D0h]
0x18004373c  test    ecx, 0FFFFFFF3h
0x180043742  jnz     short loc_180043749
0x180043744  cmp     ecx, 0Ch
0x180043747  jnz     short loc_18004374E
0x180043749  mov     eax, 57h ; 'W'
0x18004374e  mov     rbx, [rsp+68h+arg_0]
0x180043753  mov     rsi, [rsp+68h+arg_8]
0x180043758  add     rsp, 60h
0x18004375c  pop     rdi
0x18004375d  retn
```
