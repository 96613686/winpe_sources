# FMyPrimitiveHash

- ea: `0x18000d9f0`
- end: `0x18000db07`
- name: `FMyPrimitiveHash`
- size: `279`
- prototype: `__int64 __usercall@<rax>(BCRYPT_HANDLE hObject@<rcx>, PUCHAR pbInput@<rdx>, ULONG cbInput@<r8d>, UCHAR pbOutput, PUCHAR, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003b41c`

## callees

- `0x18000d9f0`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x18000dac6`
- `bcrypt!BCryptFinishHash` at `0x18000dac6`
- `bcrypt!BCryptDestroyHash` at `0x18000dae5`
- `bcrypt!BCryptDestroyHash` at `0x18000dae5`
- `bcrypt!BCryptHashData` at `0x18000da5a`
- `bcrypt!BCryptHashData` at `0x18000da5a`
- `bcrypt!BCryptCreateHash` at `0x18000da38`
- `bcrypt!BCryptCreateHash` at `0x18000da38`
- `bcrypt!BCryptGetProperty` at `0x18000da94`
- `bcrypt!BCryptGetProperty` at `0x18000da94`

## pseudocode

```c
_BOOL8 __fastcall FMyPrimitiveHash(
        BCRYPT_HANDLE hObject,
        PUCHAR pbInput,
        ULONG cbInput,
        __int64 a4,
        ULONG pbOutput,
        PUCHAR a6,
        unsigned int a7)
{
  BOOL v10; // ebx
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+88h] [rbp+20h] BYREF
  int v14; // [rsp+8Ch] [rbp+24h]

  v14 = HIDWORD(a4);
  pbOutput = 0;
  pcbResult = 0;
  v10 = 0;
  hHash = 0;
  if ( BCryptCreateHash(hObject, &hHash, 0, 0, 0, 0, 0) >= 0
    && BCryptHashData(hHash, pbInput, cbInput, 0) >= 0
    && BCryptGetProperty(hObject, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0) >= 0
    && pbOutput <= a7 )
  {
    v10 = BCryptFinishHash(hHash, a6, pbOutput, 0) >= 0;
  }
  if ( hHash )
    BCryptDestroyHash(hHash);
  return v10;
}

```

## disassembly

```asm
0x18000d9f0  mov     rax, rsp
0x18000d9f3  mov     [rax+8], rbx
0x18000d9f7  mov     [rax+10h], rbp
0x18000d9fb  mov     [rax+20h], r9
0x18000d9ff  push    rsi
0x18000da00  push    rdi
0x18000da01  push    r14
0x18000da03  sub     rsp, 50h
0x18000da07  xor     r14d, r14d
0x18000da0a  mov     esi, r8d
0x18000da0d  mov     [rax-38h], r14d
0x18000da11  mov     rbp, rdx
0x18000da14  mov     [rax-40h], r14d
0x18000da18  lea     rdx, [rax-28h]; phHash
0x18000da1c  xor     r9d, r9d; cbHashObject
0x18000da1f  mov     [rax-48h], r14
0x18000da23  xor     r8d, r8d; pbHashObject
0x18000da26  mov     [rax+28h], r14d
0x18000da2a  mov     rdi, rcx
0x18000da2d  mov     [rax+20h], r14d
0x18000da31  mov     ebx, r14d
0x18000da34  mov     [rax-28h], r14
0x18000da38  call    cs:__imp_BCryptCreateHash
0x18000da3f  nop     dword ptr [rax+rax+00h]
0x18000da44  test    eax, eax
0x18000da46  js      loc_18000DADB
0x18000da4c  mov     rcx, [rsp+68h+hHash]; hHash
0x18000da51  xor     r9d, r9d; dwFlags
0x18000da54  mov     r8d, esi; cbInput
0x18000da57  mov     rdx, rbp; pbInput
0x18000da5a  call    cs:__imp_BCryptHashData
0x18000da61  nop     dword ptr [rax+rax+00h]
0x18000da66  test    eax, eax
0x18000da68  js      short loc_18000DADB
0x18000da6a  lea     rax, [rsp+68h+arg_18]
0x18000da72  mov     [rsp+68h+dwFlags], r14d; dwFlags
0x18000da77  mov     r9d, 4; cbOutput
0x18000da7d  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18000da82  lea     r8, [rsp+68h+pbOutput]; pbOutput
0x18000da8a  mov     rcx, rdi; hObject
0x18000da8d  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000da94  call    cs:__imp_BCryptGetProperty
0x18000da9b  nop     dword ptr [rax+rax+00h]
0x18000daa0  test    eax, eax
0x18000daa2  js      short loc_18000DADB
0x18000daa4  mov     r8d, [rsp+68h+pbOutput]; cbOutput
0x18000daac  cmp     r8d, [rsp+68h+arg_30]
0x18000dab4  ja      short loc_18000DADB
0x18000dab6  mov     rdx, [rsp+68h+arg_28]; pbOutput
0x18000dabe  xor     r9d, r9d; dwFlags
0x18000dac1  mov     rcx, [rsp+68h+hHash]; hHash
0x18000dac6  call    cs:__imp_BCryptFinishHash
0x18000dacd  nop     dword ptr [rax+rax+00h]
0x18000dad2  test    eax, eax
0x18000dad4  js      short loc_18000DADB
0x18000dad6  mov     ebx, 1
0x18000dadb  mov     rcx, [rsp+68h+hHash]; hHash
0x18000dae0  test    rcx, rcx
0x18000dae3  jz      short loc_18000DAF1
0x18000dae5  call    cs:__imp_BCryptDestroyHash
0x18000daec  nop     dword ptr [rax+rax+00h]
0x18000daf1  mov     rbp, [rsp+68h+arg_8]
0x18000daf6  mov     eax, ebx
0x18000daf8  mov     rbx, [rsp+68h+arg_0]
0x18000dafd  add     rsp, 50h
0x18000db01  pop     r14
0x18000db03  pop     rdi
0x18000db04  pop     rsi
0x18000db05  retn
```
