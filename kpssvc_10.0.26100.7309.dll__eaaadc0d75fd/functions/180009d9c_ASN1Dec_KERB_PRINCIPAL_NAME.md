# ASN1Dec_KERB_PRINCIPAL_NAME

- ea: `0x180009d9c`
- end: `0x180009e8a`
- name: `ASN1Dec_KERB_PRINCIPAL_NAME`
- size: `238`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x180003360`
- `0x180003e30`
- `0x180004368`
- `0x1800059c4`
- `0x1800064d0`
- `0x180006c90`
- `0x180007844`
- `0x180007e28`
- `0x180008700`
- `0x180008aa0`
- `0x18000965c`
- `0x1800099e0`
- `0x180009b34`
- `0x18000b570`
- `0x18000b9b0`
- `0x18000bbf0`
- `0x18000bfb0`
- `0x18000c544`
- `0x18000df50`

## callees

- `0x180009d9c`
- `0x180009e90`

## import_xrefs

- `MSASN1!ASN1BERDecEndOfContents` at `0x180009e31`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180009e5d`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180009e31`
- `MSASN1!ASN1BERDecEndOfContents` at `0x180009e5d`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180009dd6`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180009dfb`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180009dd6`
- `MSASN1!ASN1BERDecExplicitTag` at `0x180009dfb`
- `MSASN1!ASN1BERDecS32Val` at `0x180009e15`
- `MSASN1!ASN1BERDecS32Val` at `0x180009e15`

## pseudocode

```c
__int64 __fastcall ASN1Dec_KERB_PRINCIPAL_NAME(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  __int64 v6; // rdx
  __int64 v8; // [rsp+20h] [rbp-20h] BYREF
  __int64 v9; // [rsp+28h] [rbp-18h] BYREF
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  __int64 v11; // [rsp+68h] [rbp+28h] BYREF

  v3 = 0;
  v11 = 0;
  v10 = 0;
  v8 = 0;
  v9 = 0;
  if ( !(unsigned int)ASN1BERDecExplicitTag(a1, 16, &v11, &v10)
    || !(unsigned int)ASN1BERDecExplicitTag(v11, 0x80000000LL, &v8, &v9)
    || !(unsigned int)ASN1BERDecS32Val(v8, 2, a3)
    || !(unsigned int)ASN1BERDecEndOfContents(v11, v8, v9)
    || !(unsigned int)ASN1Dec_KERB_PRINCIPAL_NAME_name_string(v11, v6, a3 + 8) )
  {
    return 0;
  }
  LOBYTE(v3) = (unsigned int)ASN1BERDecEndOfContents(a1, v11, v10) != 0;
  return v3;
}

```

## disassembly

```asm
0x180009d9c  mov     [rsp-8+arg_0], rbx
0x180009da1  mov     [rsp-8+arg_8], rsi
0x180009da6  mov     [rsp-8+arg_10], rdi
0x180009dab  push    rbp
0x180009dac  mov     rbp, rsp
0x180009daf  sub     rsp, 40h
0x180009db3  xor     ebx, ebx
0x180009db5  lea     r9, [rbp+var_10]
0x180009db9  mov     rdi, r8
0x180009dbc  mov     [rbp+arg_18], rbx
0x180009dc0  lea     r8, [rbp+arg_18]
0x180009dc4  mov     [rbp+var_10], rbx
0x180009dc8  mov     rsi, rcx
0x180009dcb  mov     [rbp+var_20], rbx
0x180009dcf  lea     edx, [rbx+10h]
0x180009dd2  mov     [rbp+var_18], rbx
0x180009dd6  call    cs:__imp_ASN1BERDecExplicitTag
0x180009ddd  nop     dword ptr [rax+rax+00h]
0x180009de2  test    eax, eax
0x180009de4  jz      loc_180009E72
0x180009dea  mov     rcx, [rbp+arg_18]
0x180009dee  lea     r9, [rbp+var_18]
0x180009df2  lea     r8, [rbp+var_20]
0x180009df6  mov     edx, 80000000h
0x180009dfb  call    cs:__imp_ASN1BERDecExplicitTag
0x180009e02  nop     dword ptr [rax+rax+00h]
0x180009e07  test    eax, eax
0x180009e09  jz      short loc_180009E72
0x180009e0b  mov     rcx, [rbp+var_20]
0x180009e0f  lea     edx, [rbx+2]
0x180009e12  mov     r8, rdi
0x180009e15  call    cs:__imp_ASN1BERDecS32Val
0x180009e1c  nop     dword ptr [rax+rax+00h]
0x180009e21  test    eax, eax
0x180009e23  jz      short loc_180009E72
0x180009e25  mov     r8, [rbp+var_18]
0x180009e29  mov     rdx, [rbp+var_20]
0x180009e2d  mov     rcx, [rbp+arg_18]
0x180009e31  call    cs:__imp_ASN1BERDecEndOfContents
0x180009e38  nop     dword ptr [rax+rax+00h]
0x180009e3d  test    eax, eax
0x180009e3f  jz      short loc_180009E72
0x180009e41  mov     rcx, [rbp+arg_18]
0x180009e45  lea     r8, [rdi+8]
0x180009e49  call    ASN1Dec_KERB_PRINCIPAL_NAME_name_string
0x180009e4e  test    eax, eax
0x180009e50  jz      short loc_180009E72
0x180009e52  mov     r8, [rbp+var_10]
0x180009e56  mov     rcx, rsi
0x180009e59  mov     rdx, [rbp+arg_18]
0x180009e5d  call    cs:__imp_ASN1BERDecEndOfContents
0x180009e64  nop     dword ptr [rax+rax+00h]
0x180009e69  test    eax, eax
0x180009e6b  setnz   bl
0x180009e6e  mov     eax, ebx
0x180009e70  jmp     short loc_180009E74
0x180009e72  xor     eax, eax
0x180009e74  mov     rbx, [rsp+40h+arg_0]
0x180009e79  mov     rsi, [rsp+40h+arg_8]
0x180009e7e  mov     rdi, [rsp+40h+arg_10]
0x180009e83  add     rsp, 40h
0x180009e87  pop     rbp
0x180009e88  retn
```
