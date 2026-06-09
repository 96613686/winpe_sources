# aesInitializeCommon

- ea: `0x14000e66c`
- end: `0x14000e7a7`
- name: `aesInitializeCommon`
- size: `315`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002d650`
- `0x14002dc90`

## callees

- `0x14000e66c`
- `0x14000f88c`
- `0x140010160`
- `0x1400261e0`
- `0x14002d1d0`

## import_xrefs

- `cng!BCryptGenerateSymmetricKey` at `0x14000e776`
- `cng!BCryptGenerateSymmetricKey` at `0x14000e776`

## pseudocode

```c
NTSTATUS __fastcall aesInitializeCommon(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 cbSecret; // rdi
  __int64 v7; // r14
  NTSTATUS result; // eax
  int v10; // r11d
  ULONG v11; // r9d
  BCRYPT_ALG_HANDLE v12; // rcx
  UCHAR *v13; // r8
  _BYTE v14[4]; // [rsp+40h] [rbp-40h] BYREF
  char v15; // [rsp+44h] [rbp-3Ch]
  UCHAR v16[16]; // [rsp+48h] [rbp-38h] BYREF
  UCHAR pbSecret[32]; // [rsp+58h] [rbp-28h] BYREF

  cbSecret = a3;
  v7 = a1;
  *(_DWORD *)(a6 + 20) = a3;
  *(_DWORD *)(a6 + 16) = a4;
  *(_OWORD *)(a6 + 40) = 0;
  if ( !a5 )
    return -1073741811;
  result = CDLocateCheckSum(a5, a6);
  if ( result >= 0 )
  {
    v14[3] = v10;
    v14[0] = HIBYTE(v10);
    v15 = -86;
    v14[1] = BYTE2(v10);
    v14[2] = BYTE1(v10);
    fold_40_to_128(v14, v16);
    result = aesDR(v16, a2, (unsigned int)cbSecret, pbSecret);
    if ( result >= 0 )
    {
      v15 = 85;
      fold_40_to_128(v14, v16);
      *(_QWORD *)(a6 + 24) = a6 + v7;
      result = aesDR(v16, a2, (unsigned int)cbSecret, a6 + v7);
      if ( result >= 0 )
      {
        v11 = cshAesKeyObjectSize;
        v12 = cshAesAlgHandle;
        v13 = (UCHAR *)(*(_QWORD *)(a6 + 24) + cbSecret);
        *(_QWORD *)(a6 + 32) = v13;
        return BCryptGenerateSymmetricKey(v12, (BCRYPT_KEY_HANDLE *)(a6 + 8), v13, v11, pbSecret, cbSecret, 0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000e66c  mov     [rsp-18h+arg_0], rbx
0x14000e671  mov     [rsp-18h+arg_18], rsi
0x14000e676  push    rbp
0x14000e677  push    rdi
0x14000e678  push    r14
0x14000e67a  mov     rbp, rsp
0x14000e67d  sub     rsp, 80h
0x14000e684  mov     rax, cs:__security_cookie
0x14000e68b  xor     rax, rsp
0x14000e68e  mov     [rbp+var_8], rax
0x14000e692  mov     rbx, [rbp+arg_28]
0x14000e696  xorps   xmm0, xmm0
0x14000e699  mov     edi, r8d
0x14000e69c  mov     r11d, r9d
0x14000e69f  mov     r14d, ecx
0x14000e6a2  mov     rsi, rdx
0x14000e6a5  mov     ecx, [rbp+arg_20]
0x14000e6a8  mov     [rbx+14h], edi
0x14000e6ab  mov     [rbx+10h], r9d
0x14000e6af  movups  xmmword ptr [rbx+28h], xmm0
0x14000e6b3  test    ecx, ecx
0x14000e6b5  jnz     short loc_14000E6C1
0x14000e6b7  mov     eax, 0C000000Dh
0x14000e6bc  jmp     loc_14000E782
0x14000e6c1  mov     rdx, rbx
0x14000e6c4  call    CDLocateCheckSum
0x14000e6c9  test    eax, eax
0x14000e6cb  js      loc_14000E782
0x14000e6d1  mov     eax, r11d
0x14000e6d4  mov     [rbp+var_3D], r11b
0x14000e6d8  shr     eax, 18h
0x14000e6db  lea     rdx, [rbp+var_38]
0x14000e6df  mov     [rbp+var_40], al
0x14000e6e2  lea     rcx, [rbp+var_40]
0x14000e6e6  mov     eax, r11d
0x14000e6e9  mov     [rbp+var_3C], 0AAh
0x14000e6ed  shr     eax, 10h
0x14000e6f0  mov     [rbp+var_3F], al
0x14000e6f3  mov     eax, r11d
0x14000e6f6  shr     eax, 8
0x14000e6f9  mov     [rbp+var_3E], al
0x14000e6fc  call    fold_40_to_128
0x14000e701  lea     r9, [rbp+var_28]
0x14000e705  mov     r8d, edi
0x14000e708  mov     rdx, rsi
0x14000e70b  lea     rcx, [rbp+var_38]
0x14000e70f  call    aesDR
0x14000e714  test    eax, eax
0x14000e716  js      short loc_14000E782
0x14000e718  lea     rdx, [rbp+var_38]
0x14000e71c  mov     [rbp+var_3C], 55h ; 'U'
0x14000e720  lea     rcx, [rbp+var_40]
0x14000e724  call    fold_40_to_128
0x14000e729  lea     r9, [rbx+r14]
0x14000e72d  mov     r8d, edi
0x14000e730  mov     rdx, rsi
0x14000e733  mov     [rbx+18h], r9
0x14000e737  lea     rcx, [rbp+var_38]
0x14000e73b  call    aesDR
0x14000e740  test    eax, eax
0x14000e742  js      short loc_14000E782
0x14000e744  mov     r9d, cs:cshAesKeyObjectSize; cbKeyObject
0x14000e74b  lea     rax, [rbp+var_28]
0x14000e74f  mov     rcx, cs:cshAesAlgHandle; hAlgorithm
0x14000e756  lea     rdx, [rbx+8]; phKey
0x14000e75a  mov     [rsp+80h+dwFlags], 0; dwFlags
0x14000e762  mov     r8, rdi
0x14000e765  add     r8, [rbx+18h]; pbKeyObject
0x14000e769  mov     [rsp+80h+cbSecret], edi; cbSecret
0x14000e76d  mov     [rbx+20h], r8
0x14000e771  mov     [rsp+80h+pbSecret], rax; pbSecret
0x14000e776  call    cs:__imp_BCryptGenerateSymmetricKey
0x14000e77d  nop     dword ptr [rax+rax+00h]
0x14000e782  mov     rcx, [rbp+var_8]
0x14000e786  xor     rcx, rsp; StackCookie
0x14000e789  call    __security_check_cookie
0x14000e78e  lea     r11, [rsp+80h+var_s0]
0x14000e796  mov     rbx, [r11+20h]
0x14000e79a  mov     rsi, [r11+38h]
0x14000e79e  mov     rsp, r11
0x14000e7a1  pop     r14
0x14000e7a3  pop     rdi
0x14000e7a4  pop     rbp
0x14000e7a5  retn
```
