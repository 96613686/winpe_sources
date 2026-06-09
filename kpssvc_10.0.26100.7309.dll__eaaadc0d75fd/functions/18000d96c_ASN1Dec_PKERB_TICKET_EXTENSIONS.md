# ASN1Dec_PKERB_TICKET_EXTENSIONS

- ea: `0x18000d96c`
- end: `0x18000db6c`
- name: `ASN1Dec_PKERB_TICKET_EXTENSIONS`
- size: `512`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004368`
- `0x1800059c4`
- `0x1800064d0`
- `0x180007e28`
- `0x18000bbf0`

## callees

- `0x18000d96c`

## import_xrefs

- `MSASN1!ASN1BERDecPeekTag` at `0x18000d9d4`
- `MSASN1!ASN1BERDecPeekTag` at `0x18000d9d4`
- `MSASN1!ASN1BERDecOctetString` at `0x18000dad4`
- `MSASN1!ASN1BERDecOctetString` at `0x18000dad4`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x18000db32`
- `MSASN1!ASN1BERDecNotEndOfContents` at `0x18000db32`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000da8e`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000daf4`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000db13`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000db54`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000da8e`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000daf4`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000db13`
- `MSASN1!ASN1BERDecEndOfContents` at `0x18000db54`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000d9a1`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000da29`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000da4e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000dab3`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000d9a1`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000da29`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000da4e`
- `MSASN1!ASN1BERDecExplicitTag` at `0x18000dab3`
- `MSASN1!ASN1BERDecS32Val` at `0x18000da6e`
- `MSASN1!ASN1BERDecS32Val` at `0x18000da6e`
- `MSASN1!ASN1DecAlloc` at `0x18000d9ed`
- `MSASN1!ASN1DecAlloc` at `0x18000d9ed`

## pseudocode

```c
__int64 __fastcall ASN1Dec_PKERB_TICKET_EXTENSIONS(__int64 a1, __int64 a2, __int64 *a3)
{
  unsigned int v3; // ebx
  __int64 v7; // rax
  __int64 v8; // r14
  __int64 v9; // rsi
  __int64 v10; // [rsp+20h] [rbp-30h] BYREF
  __int64 v11; // [rsp+28h] [rbp-28h] BYREF
  __int64 v12; // [rsp+30h] [rbp-20h] BYREF
  __int64 v13; // [rsp+38h] [rbp-18h] BYREF
  __int64 v14; // [rsp+40h] [rbp-10h] BYREF
  int v15; // [rsp+88h] [rbp+38h] BYREF
  __int64 v16; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  v16 = 0;
  v13 = 0;
  v15 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, 16, &v16, &v13) )
    return 0;
  while ( (unsigned int)ASN1BERDecNotEndOfContents(v16, v13) )
  {
    if ( !(unsigned int)ASN1BERDecPeekTag(v16, &v15) )
      return 0;
    v7 = ASN1DecAlloc(v16, 32);
    *a3 = v7;
    if ( !v7 )
      return 0;
    v8 = v16;
    v11 = 0;
    v14 = 0;
    v10 = 0;
    v9 = v7 + 8;
    v12 = 0;
    if ( !(unsigned int)ASN1BERDecExplicitTag(v16, 16, &v11, &v14)
      || !(unsigned int)ASN1BERDecExplicitTag(v11, 0x80000000LL, &v10, &v12)
      || !(unsigned int)ASN1BERDecS32Val(v10, 2, v9)
      || !(unsigned int)ASN1BERDecEndOfContents(v11, v10, v12)
      || !(unsigned int)ASN1BERDecExplicitTag(v11, 2147483649LL, &v10, &v12)
      || !(unsigned int)ASN1BERDecOctetString(v10, 4, v9 + 8)
      || !(unsigned int)ASN1BERDecEndOfContents(v11, v10, v12)
      || !(unsigned int)ASN1BERDecEndOfContents(v8, v11, v14) )
    {
      return 0;
    }
    a3 = (__int64 *)*a3;
  }
  *a3 = 0;
  LOBYTE(v3) = (unsigned int)ASN1BERDecEndOfContents(a1, v16, v13) != 0;
  return v3;
}

```

## disassembly

```asm
0x18000d96c  mov     [rsp-28h+arg_0], rbx
0x18000d971  mov     [rsp-28h+arg_8], edx
0x18000d975  push    rbp
0x18000d976  push    rsi
0x18000d977  push    rdi
0x18000d978  push    r14
0x18000d97a  push    r15
0x18000d97c  mov     rbp, rsp
0x18000d97f  sub     rsp, 50h
0x18000d983  xor     ebx, ebx
0x18000d985  lea     r9, [rbp+var_18]
0x18000d989  mov     rdi, r8
0x18000d98c  mov     [rbp+arg_18], rbx
0x18000d990  lea     r8, [rbp+arg_18]
0x18000d994  mov     [rbp+var_18], rbx
0x18000d998  mov     r15, rcx
0x18000d99b  mov     [rbp+arg_8], ebx
0x18000d99e  lea     edx, [rbx+10h]
0x18000d9a1  call    cs:__imp_ASN1BERDecExplicitTag
0x18000d9a8  nop     dword ptr [rax+rax+00h]
0x18000d9ad  test    eax, eax
0x18000d9af  jnz     loc_18000DB2A
0x18000d9b5  xor     eax, eax
0x18000d9b7  mov     rbx, [rsp+50h+arg_0]
0x18000d9bf  add     rsp, 50h
0x18000d9c3  pop     r15
0x18000d9c5  pop     r14
0x18000d9c7  pop     rdi
0x18000d9c8  pop     rsi
0x18000d9c9  pop     rbp
0x18000d9ca  retn
0x18000d9cc  mov     rcx, [rbp+arg_18]
0x18000d9d0  lea     rdx, [rbp+arg_8]
0x18000d9d4  call    cs:__imp_ASN1BERDecPeekTag
0x18000d9db  nop     dword ptr [rax+rax+00h]
0x18000d9e0  test    eax, eax
0x18000d9e2  jz      short loc_18000D9B5
0x18000d9e4  mov     rcx, [rbp+arg_18]
0x18000d9e8  mov     edx, 20h ; ' '
0x18000d9ed  call    cs:__imp_ASN1DecAlloc
0x18000d9f4  nop     dword ptr [rax+rax+00h]
0x18000d9f9  mov     [rdi], rax
0x18000d9fc  test    rax, rax
0x18000d9ff  jz      short loc_18000D9B5
0x18000da01  mov     r14, [rbp+arg_18]
0x18000da05  lea     r9, [rbp+var_10]
0x18000da09  mov     rcx, r14
0x18000da0c  mov     [rbp+var_28], rbx
0x18000da10  lea     r8, [rbp+var_28]
0x18000da14  mov     [rbp+var_10], rbx
0x18000da18  mov     edx, 10h
0x18000da1d  mov     [rbp+var_30], rbx
0x18000da21  lea     rsi, [rax+8]
0x18000da25  mov     [rbp+var_20], rbx
0x18000da29  call    cs:__imp_ASN1BERDecExplicitTag
0x18000da30  nop     dword ptr [rax+rax+00h]
0x18000da35  test    eax, eax
0x18000da37  jz      loc_18000D9B5
0x18000da3d  mov     rcx, [rbp+var_28]
0x18000da41  lea     r9, [rbp+var_20]
0x18000da45  lea     r8, [rbp+var_30]
0x18000da49  mov     edx, 80000000h
0x18000da4e  call    cs:__imp_ASN1BERDecExplicitTag
0x18000da55  nop     dword ptr [rax+rax+00h]
0x18000da5a  test    eax, eax
0x18000da5c  jz      loc_18000D9B5
0x18000da62  mov     rcx, [rbp+var_30]
0x18000da66  mov     r8, rsi
0x18000da69  mov     edx, 2
0x18000da6e  call    cs:__imp_ASN1BERDecS32Val
0x18000da75  nop     dword ptr [rax+rax+00h]
0x18000da7a  test    eax, eax
0x18000da7c  jz      loc_18000D9B5
0x18000da82  mov     r8, [rbp+var_20]
0x18000da86  mov     rdx, [rbp+var_30]
0x18000da8a  mov     rcx, [rbp+var_28]
0x18000da8e  call    cs:__imp_ASN1BERDecEndOfContents
0x18000da95  nop     dword ptr [rax+rax+00h]
0x18000da9a  test    eax, eax
0x18000da9c  jz      loc_18000D9B5
0x18000daa2  mov     rcx, [rbp+var_28]
0x18000daa6  lea     r9, [rbp+var_20]
0x18000daaa  lea     r8, [rbp+var_30]
0x18000daae  mov     edx, 80000001h
0x18000dab3  call    cs:__imp_ASN1BERDecExplicitTag
0x18000daba  nop     dword ptr [rax+rax+00h]
0x18000dabf  test    eax, eax
0x18000dac1  jz      loc_18000D9B5
0x18000dac7  mov     rcx, [rbp+var_30]
0x18000dacb  lea     r8, [rsi+8]
0x18000dacf  mov     edx, 4
0x18000dad4  call    cs:__imp_ASN1BERDecOctetString
0x18000dadb  nop     dword ptr [rax+rax+00h]
0x18000dae0  test    eax, eax
0x18000dae2  jz      loc_18000D9B5
0x18000dae8  mov     r8, [rbp+var_20]
0x18000daec  mov     rdx, [rbp+var_30]
0x18000daf0  mov     rcx, [rbp+var_28]
0x18000daf4  call    cs:__imp_ASN1BERDecEndOfContents
0x18000dafb  nop     dword ptr [rax+rax+00h]
0x18000db00  test    eax, eax
0x18000db02  jz      loc_18000D9B5
0x18000db08  mov     r8, [rbp+var_10]
0x18000db0c  mov     rcx, r14
0x18000db0f  mov     rdx, [rbp+var_28]
0x18000db13  call    cs:__imp_ASN1BERDecEndOfContents
0x18000db1a  nop     dword ptr [rax+rax+00h]
0x18000db1f  test    eax, eax
0x18000db21  jz      loc_18000D9B5
0x18000db27  mov     rdi, [rdi]
0x18000db2a  mov     rdx, [rbp+var_18]
0x18000db2e  mov     rcx, [rbp+arg_18]
0x18000db32  call    cs:__imp_ASN1BERDecNotEndOfContents
0x18000db39  nop     dword ptr [rax+rax+00h]
0x18000db3e  test    eax, eax
0x18000db40  jnz     loc_18000D9CC
0x18000db46  mov     [rdi], rbx
0x18000db49  mov     rcx, r15
0x18000db4c  mov     r8, [rbp+var_18]
0x18000db50  mov     rdx, [rbp+arg_18]
0x18000db54  call    cs:__imp_ASN1BERDecEndOfContents
0x18000db5b  nop     dword ptr [rax+rax+00h]
0x18000db60  test    eax, eax
0x18000db62  setnz   bl
0x18000db65  mov     eax, ebx
0x18000db67  jmp     loc_18000D9B7
```
