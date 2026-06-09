# WPP_SF__sid_SdLSiS

- ea: `0x1800b16e8`
- end: `0x1800b1883`
- name: `WPP_SF__sid_SdLSiS`
- size: `411`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a6fc`

## callees

- `0x1800b16e8`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x1800b1869`
- `ntdll!EtwTraceMessage` at `0x1800b1869`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b179e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b17c6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b179e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b17c6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b17ad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b17ad`

## pseudocode

```c
__int64 __fastcall WPP_SF__sid_SdLSiS(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char *a4,
        const wchar_t *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v10; // rdx
  char *v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rax
  const wchar_t *v14; // rdi
  bool v15; // zf
  DWORD LengthSid; // r15d

  v10 = -1;
  v11 = a4;
  if ( a10 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(a10 + 2 * v12) );
  }
  if ( a8 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(a8 + 2 * v13) );
  }
  v14 = a5;
  v15 = a5 == 0;
  if ( a5 )
  {
    do
      ++v10;
    while ( a5[v10] );
    v15 = a5 == 0;
  }
  if ( v15 )
    v14 = L"NULL";
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v11);
  }
  else
  {
    LengthSid = 5;
    if ( !v11 )
    {
LABEL_17:
      v11 = "NULL";
      return EtwTraceMessage(a1, 43, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids, 60, v11, LengthSid, v14);
    }
  }
  if ( !IsValidSid(v11) )
    goto LABEL_17;
  return EtwTraceMessage(a1, 43, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids, 60, v11, LengthSid, v14);
}

```

## disassembly

```asm
0x1800b16e8  mov     [rsp+arg_0], rcx
0x1800b16ed  push    rbx
0x1800b16ee  push    rbp
0x1800b16ef  push    rsi
0x1800b16f0  push    rdi
0x1800b16f1  push    r12
0x1800b16f3  push    r13
0x1800b16f5  push    r14
0x1800b16f7  push    r15
0x1800b16f9  sub     rsp, 0A8h
0x1800b1700  mov     rsi, [rsp+0E8h+arg_48]
0x1800b1708  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800b170c  xor     ecx, ecx
0x1800b170e  mov     rbx, r9
0x1800b1711  mov     r14d, 0Ah
0x1800b1717  test    rsi, rsi
0x1800b171a  jz      short loc_1800B1732
0x1800b171c  mov     rax, rdx
0x1800b171f  inc     rax
0x1800b1722  cmp     [rsi+rax*2], cx
0x1800b1726  jnz     short loc_1800B171F
0x1800b1728  lea     r13, ds:2[rax*2]
0x1800b1730  jmp     short loc_1800B1735
0x1800b1732  mov     r13, r14
0x1800b1735  mov     rbp, [rsp+0E8h+arg_38]
0x1800b173d  lea     r8, aNull_1; "NULL"
0x1800b1744  test    rsi, rsi
0x1800b1747  cmovz   rsi, r8
0x1800b174b  test    rbp, rbp
0x1800b174e  jz      short loc_1800B1767
0x1800b1750  mov     rax, rdx
0x1800b1753  inc     rax
0x1800b1756  cmp     [rbp+rax*2+0], cx
0x1800b175b  jnz     short loc_1800B1753
0x1800b175d  lea     r12, ds:2[rax*2]
0x1800b1765  jmp     short loc_1800B176A
0x1800b1767  mov     r12, r14
0x1800b176a  mov     rdi, [rsp+0E8h+arg_20]
0x1800b1772  test    rbp, rbp
0x1800b1775  cmovz   rbp, r8
0x1800b1779  test    rdi, rdi
0x1800b177c  jz      short loc_1800B1792
0x1800b177e  inc     rdx
0x1800b1781  cmp     [rdi+rdx*2], cx
0x1800b1785  jnz     short loc_1800B177E
0x1800b1787  lea     r14, ds:2[rdx*2]
0x1800b178f  test    rdi, rdi
0x1800b1792  cmovz   rdi, r8
0x1800b1796  test    rbx, rbx
0x1800b1799  jz      short loc_1800B17B8
0x1800b179b  mov     rcx, rbx; pSid
0x1800b179e  call    cs:__imp_IsValidSid
0x1800b17a4  xor     ecx, ecx
0x1800b17a6  test    eax, eax
0x1800b17a8  jz      short loc_1800B17B8
0x1800b17aa  mov     rcx, rbx; pSid
0x1800b17ad  call    cs:__imp_GetLengthSid
0x1800b17b3  mov     r15d, eax
0x1800b17b6  jmp     short loc_1800B17C3
0x1800b17b8  mov     r15d, 5
0x1800b17be  test    rbx, rbx
0x1800b17c1  jz      short loc_1800B17D2
0x1800b17c3  mov     rcx, rbx; pSid
0x1800b17c6  call    cs:__imp_IsValidSid
0x1800b17cc  xor     ecx, ecx
0x1800b17ce  test    eax, eax
0x1800b17d0  jnz     short loc_1800B17D9
0x1800b17d2  lea     rbx, aNull; "NULL"
0x1800b17d9  mov     [rsp+0E8h+var_58], rcx
0x1800b17e1  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x1800b17e8  mov     [rsp+0E8h+var_60], r13
0x1800b17f0  lea     rcx, [rsp+0E8h+arg_40]
0x1800b17f8  mov     [rsp+0E8h+var_68], rsi
0x1800b1800  mov     r9d, 3Ch ; '<'
0x1800b1806  mov     [rsp+0E8h+var_70], 8
0x1800b180f  mov     [rsp+0E8h+var_78], rcx
0x1800b1814  lea     rcx, [rsp+0E8h+arg_30]
0x1800b181c  mov     [rsp+0E8h+var_80], r12
0x1800b1821  mov     [rsp+0E8h+var_88], rbp
0x1800b1826  lea     edx, [r9-38h]
0x1800b182a  mov     [rsp+0E8h+var_90], rdx
0x1800b182f  mov     [rsp+0E8h+var_98], rcx
0x1800b1834  lea     rcx, [rsp+0E8h+arg_28]
0x1800b183c  mov     [rsp+0E8h+var_A0], rdx
0x1800b1841  lea     edx, [r9-11h]
0x1800b1845  mov     [rsp+0E8h+var_A8], rcx
0x1800b184a  mov     rcx, [rsp+0E8h+arg_0]
0x1800b1852  mov     [rsp+0E8h+var_B0], r14
0x1800b1857  mov     eax, r15d
0x1800b185a  mov     [rsp+0E8h+var_B8], rdi
0x1800b185f  mov     [rsp+0E8h+var_C0], rax
0x1800b1864  mov     [rsp+0E8h+var_C8], rbx
0x1800b1869  call    cs:__imp_EtwTraceMessage
0x1800b186f  add     rsp, 0A8h
0x1800b1876  pop     r15
0x1800b1878  pop     r14
0x1800b187a  pop     r13
0x1800b187c  pop     r12
0x1800b187e  pop     rdi
0x1800b187f  pop     rsi
0x1800b1880  pop     rbp
0x1800b1881  pop     rbx
0x1800b1882  retn
```
