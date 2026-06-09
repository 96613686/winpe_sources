# DecodePassword

- ea: `0x18000d7d0`
- end: `0x18000d884`
- name: `DecodePassword`
- size: `180`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180006a50`
- `0x180008cf0`
- `0x180012974`
- `0x180014bd8`
- `0x180017050`
- `0x18001b060`
- `0x18001b3ec`

## callees

- `0x18000d7d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d83e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d83e`
- `CRYPT32!CryptUnprotectData` at `0x18000d834`
- `CRYPT32!CryptUnprotectData` at `0x18000d834`

## pseudocode

```c
DWORD __fastcall DecodePassword(DATA_BLOB *a1, DWORD *a2, BYTE **a3)
{
  DATA_BLOB pDataOut; // [rsp+40h] [rbp-18h] BYREF

  if ( !a1 || !a2 || !a3 )
    return -2147024809;
  *a2 = 0;
  *a3 = 0;
  if ( a1->pbData && a1->cbData )
  {
    pDataOut = 0;
    if ( !CryptUnprotectData(a1, 0, 0, 0, 0, 5u, &pDataOut) )
      return GetLastError();
    *a2 = pDataOut.cbData;
    *a3 = pDataOut.pbData;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d7d0  mov     [rsp+arg_8], rbx
0x18000d7d5  push    rdi
0x18000d7d6  sub     rsp, 50h
0x18000d7da  mov     rbx, r8
0x18000d7dd  mov     rdi, rdx
0x18000d7e0  test    rcx, rcx
0x18000d7e3  jz      loc_18000D874
0x18000d7e9  test    rdx, rdx
0x18000d7ec  jz      loc_18000D874
0x18000d7f2  test    rbx, rbx
0x18000d7f5  jz      short loc_18000D874
0x18000d7f7  xor     edx, edx; ppszDataDescr
0x18000d7f9  mov     [rsp+58h+arg_0], rsi
0x18000d7fe  mov     esi, edx
0x18000d800  mov     [rdi], edx
0x18000d802  mov     [r8], rdx
0x18000d805  cmp     [rcx+8], rdx
0x18000d809  jz      short loc_18000D862
0x18000d80b  cmp     [rcx], edx
0x18000d80d  jz      short loc_18000D862
0x18000d80f  lea     rax, [rsp+58h+var_18]
0x18000d814  xorps   xmm0, xmm0
0x18000d817  mov     [rsp+58h+pDataOut], rax; pDataOut
0x18000d81c  xor     r9d, r9d; pvReserved
0x18000d81f  mov     [rsp+58h+dwFlags], 5; dwFlags
0x18000d827  xor     r8d, r8d; pOptionalEntropy
0x18000d82a  mov     [rsp+58h+pPromptStruct], rdx; pPromptStruct
0x18000d82f  movups  xmmword ptr [rsp+58h+var_18.cbData], xmm0
0x18000d834  call    cs:__imp_CryptUnprotectData
0x18000d83a  test    eax, eax
0x18000d83c  jnz     short loc_18000D854
0x18000d83e  call    cs:__imp_GetLastError
0x18000d844  mov     rsi, [rsp+58h+arg_0]
0x18000d849  mov     rbx, [rsp+58h+arg_8]
0x18000d84e  add     rsp, 50h
0x18000d852  pop     rdi
0x18000d853  retn
0x18000d854  mov     ecx, [rsp+58h+var_18.cbData]
0x18000d858  mov     [rdi], ecx
0x18000d85a  mov     rcx, [rsp+58h+var_18.pbData]
0x18000d85f  mov     [rbx], rcx
0x18000d862  mov     eax, esi
0x18000d864  mov     rsi, [rsp+58h+arg_0]
0x18000d869  mov     rbx, [rsp+58h+arg_8]
0x18000d86e  add     rsp, 50h
0x18000d872  pop     rdi
0x18000d873  retn
0x18000d874  mov     rbx, [rsp+58h+arg_8]
0x18000d879  mov     eax, 80070057h
0x18000d87e  add     rsp, 50h
0x18000d882  pop     rdi
0x18000d883  retn
```
