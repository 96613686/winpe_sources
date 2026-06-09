# QuicLibraryLoadRetryConfig

- ea: `0x140028b3c`
- end: `0x140028c95`
- name: `QuicLibraryLoadRetryConfig`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140024240`

## callees

- `0x140028b3c`
- `0x140028ce4`
- `0x140033e30`
- `0x14003c8e0`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockShared` at `0x140028bcf`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140028bcf`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140028b97`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x140028b97`

## pseudocode

```c
__int64 __fastcall QuicLibraryLoadRetryConfig(HANDLE *a1)
{
  KIRQL v2; // al
  int v3; // edi
  int v4; // eax
  bool v5; // si
  unsigned int v6; // edi
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-60h] BYREF
  int v9; // [rsp+24h] [rbp-5Ch] BYREF
  int v10; // [rsp+28h] [rbp-58h] BYREF
  int v11; // [rsp+2Ch] [rbp-54h] BYREF
  int v12; // [rsp+30h] [rbp-50h] BYREF
  _DWORD v13[2]; // [rsp+38h] [rbp-48h] BYREF
  ULONG v14; // [rsp+40h] [rbp-40h]
  int v15; // [rsp+44h] [rbp-3Ch]
  UCHAR *v16; // [rsp+48h] [rbp-38h]
  _OWORD v17[2]; // [rsp+50h] [rbp-30h] BYREF

  v15 = 0;
  v8 = 0;
  v9 = 0;
  v11 = 4;
  memset(v17, 0, sizeof(v17));
  v12 = 4;
  v10 = 32;
  v2 = ExAcquireSpinLockShared(&dword_14005C5C8);
  v3 = dword_14005C5F4;
  v13[0] = dword_14005C5F0;
  v14 = cbSecret;
  v16 = &pbSecret;
  ExReleaseSpinLockShared(&dword_14005C5C8, v2);
  v4 = CxPlatStorageReadValue(a1, "RetryKeyRotationMs", &v8, &v11);
  if ( v4 >= 0 )
    v3 = v8;
  v5 = v4 >= 0;
  v13[1] = v3;
  v6 = (unsigned int)CxPlatStorageReadValue(a1, "RetryKeyAlgorithm", &v9, &v12) >> 31;
  if ( (int)CxPlatStorageReadValue(a1, "RetrySecret", v17, &v10) >= 0 && !(_BYTE)v6 )
  {
    v13[0] = v9;
    v16 = (UCHAR *)v17;
    v14 = v10;
LABEL_7:
    QuicLibrarySetRetryKeyConfig(v13);
    goto LABEL_8;
  }
  if ( v5 )
    goto LABEL_7;
LABEL_8:
  result = 0;
  memset(v17, 0, sizeof(v17));
  return result;
}

```

## disassembly

```asm
0x140028b3c  mov     [rsp-8+arg_8], rbx
0x140028b41  mov     [rsp-8+arg_10], rsi
0x140028b46  mov     [rsp-8+arg_18], rdi
0x140028b4b  push    rbp
0x140028b4c  mov     rbp, rsp
0x140028b4f  sub     rsp, 80h
0x140028b56  mov     rax, cs:__security_cookie
0x140028b5d  xor     rax, rsp
0x140028b60  mov     [rbp+var_10], rax
0x140028b64  and     [rbp+var_3C], 0
0x140028b68  xorps   xmm0, xmm0
0x140028b6b  and     [rbp+var_60], 0
0x140028b6f  mov     eax, 4
0x140028b74  and     [rbp+var_5C], 0
0x140028b78  mov     rbx, rcx
0x140028b7b  lea     rcx, dword_14005C5C8; SpinLock
0x140028b82  mov     [rbp+var_54], eax
0x140028b85  movups  [rbp+var_30], xmm0
0x140028b89  mov     [rbp+var_50], eax
0x140028b8c  movups  [rbp+var_20], xmm0
0x140028b90  mov     [rbp+var_58], 20h ; ' '
0x140028b97  call    cs:__imp_ExAcquireSpinLockShared
0x140028b9e  nop     dword ptr [rax+rax+00h]
0x140028ba3  mov     ecx, cs:dword_14005C5F0
0x140028ba9  mov     dl, al; OldIrql
0x140028bab  mov     edi, cs:dword_14005C5F4
0x140028bb1  mov     [rbp+var_48], ecx
0x140028bb4  mov     ecx, cs:cbSecret
0x140028bba  mov     [rbp+var_40], ecx
0x140028bbd  lea     rcx, pbSecret
0x140028bc4  mov     [rbp+var_38], rcx
0x140028bc8  lea     rcx, dword_14005C5C8; SpinLock
0x140028bcf  call    cs:__imp_ExReleaseSpinLockShared
0x140028bd6  nop     dword ptr [rax+rax+00h]
0x140028bdb  lea     r9, [rbp+var_54]
0x140028bdf  mov     rcx, rbx
0x140028be2  lea     r8, [rbp+var_60]
0x140028be6  lea     rdx, aRetrykeyrotati; "RetryKeyRotationMs"
0x140028bed  call    CxPlatStorageReadValue
0x140028bf2  test    eax, eax
0x140028bf4  lea     r9, [rbp+var_50]
0x140028bf8  mov     esi, eax
0x140028bfa  lea     r8, [rbp+var_5C]
0x140028bfe  cmovns  edi, [rbp+var_60]
0x140028c02  lea     rdx, aRetrykeyalgori; "RetryKeyAlgorithm"
0x140028c09  shr     esi, 1Fh
0x140028c0c  mov     rcx, rbx
0x140028c0f  xor     sil, 1
0x140028c13  mov     [rbp+var_44], edi
0x140028c16  call    CxPlatStorageReadValue
0x140028c1b  mov     edi, eax
0x140028c1d  lea     r9, [rbp+var_58]
0x140028c21  lea     r8, [rbp+var_30]
0x140028c25  shr     edi, 1Fh
0x140028c28  lea     rdx, aRetrysecret; "RetrySecret"
0x140028c2f  mov     rcx, rbx
0x140028c32  call    CxPlatStorageReadValue
0x140028c37  test    eax, eax
0x140028c39  js      short loc_140028C56
0x140028c3b  test    dil, dil
0x140028c3e  jnz     short loc_140028C56
0x140028c40  mov     eax, [rbp+var_5C]
0x140028c43  mov     [rbp+var_48], eax
0x140028c46  lea     rax, [rbp+var_30]
0x140028c4a  mov     [rbp+var_38], rax
0x140028c4e  mov     eax, [rbp+var_58]
0x140028c51  mov     [rbp+var_40], eax
0x140028c54  jmp     short loc_140028C5B
0x140028c56  test    sil, sil
0x140028c59  jz      short loc_140028C64
0x140028c5b  lea     rcx, [rbp+var_48]
0x140028c5f  call    QuicLibrarySetRetryKeyConfig
0x140028c64  xor     eax, eax
0x140028c66  lea     rdi, [rbp+var_30]
0x140028c6a  lea     ecx, [rax+20h]
0x140028c6d  rep stosb
0x140028c6f  mov     rcx, [rbp+var_10]
0x140028c73  xor     rcx, rsp; StackCookie
0x140028c76  call    __security_check_cookie
0x140028c7b  lea     r11, [rsp+80h+var_s0]
0x140028c83  mov     rbx, [r11+18h]
0x140028c87  mov     rsi, [r11+20h]
0x140028c8b  mov     rdi, [r11+28h]
0x140028c8f  mov     rsp, r11
0x140028c92  pop     rbp
0x140028c93  retn
```
