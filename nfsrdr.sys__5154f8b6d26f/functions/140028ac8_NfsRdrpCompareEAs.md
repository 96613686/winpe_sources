# NfsRdrpCompareEAs

- ea: `0x140028ac8`
- end: `0x140028d0b`
- name: `NfsRdrpCompareEAs`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140025be0`

## callees

- `0x140018310`
- `0x14001db18`
- `0x140028ac8`
- `0x14002a2fc`
- `0x14002e330`
- `0x14003aba0`
- `0x14003aca0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140028b52`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140028b97`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140028b52`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140028b97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028c78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028c78`

## string_xrefs

- `0x140028ae9`: `NfsRdrpCompareEAs`

## pseudocode

```c
__int64 __fastcall NfsRdrpCompareEAs(__int64 a1, _QWORD *a2, __int64 a3)
{
  const UNICODE_STRING *v6; // rdx
  int v7; // r8d
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rax
  int v10; // edx
  const UNICODE_STRING *v11; // rdx
  int v12; // ebx
  unsigned __int16 *v13; // r9
  int v14; // eax
  __int64 v15; // r9
  size_t Size; // [rsp+30h] [rbp-30h] BYREF
  void *Buf1; // [rsp+38h] [rbp-28h] BYREF
  char v19[24]; // [rsp+40h] [rbp-20h] BYREF

  strcpy(v19, "NfsRdrpCompareEAs");
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids, v19);
  v6 = (const UNICODE_STRING *)a2[4];
  if ( v6 && *(_WORD *)(a3 + 32) && RtlCompareUnicodeString((PCUNICODE_STRING)(a3 + 32), v6, 1u) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_17;
    v9 = a2[4];
    v10 = 82;
LABEL_16:
    WPP_SF_sZ(v8->AttachedDevice, v10, v7, (unsigned int)v19, v9);
LABEL_17:
    v12 = -1073741419;
    goto LABEL_31;
  }
  v11 = (const UNICODE_STRING *)a2[2];
  if ( v11 && *(_WORD *)(a3 + 48) && RtlCompareUnicodeString((PCUNICODE_STRING)(a3 + 48), v11, 1u) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_17;
    v9 = a2[2];
    v10 = 83;
    goto LABEL_16;
  }
  v13 = (unsigned __int16 *)a2[3];
  v12 = 0;
  if ( v13 && *(_QWORD *)(a3 + 64) )
  {
    v14 = *v13;
    v15 = *((_QWORD *)v13 + 1);
    Buf1 = 0;
    LODWORD(Size) = 0;
    v12 = NfsRdrCryptoHash(a1 + 1352, &Buf1, &Size, v15, v14);
    if ( v12 < 0 )
      goto LABEL_28;
    if ( (_DWORD)Size != *(_DWORD *)(a3 + 72) || memcmp(Buf1, *(const void **)(a3 + 64), (unsigned int)Size) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids, v19);
      v12 = -1073741419;
    }
    ExFreePoolWithTag(Buf1, 0);
    if ( v12 < 0 )
    {
LABEL_28:
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return (unsigned int)v12;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_sD(
          WPP_GLOBAL_Control->AttachedDevice,
          85,
          (unsigned int)WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
          (unsigned int)v19,
          v12);
    }
  }
LABEL_31:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_sD(
      WPP_GLOBAL_Control->AttachedDevice,
      86,
      (unsigned int)WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
      (unsigned int)v19,
      v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140028ac8  mov     [rsp-28h+arg_18], rbx
0x140028acd  push    rbp
0x140028ace  push    rsi
0x140028acf  push    rdi
0x140028ad0  push    r13
0x140028ad2  push    r14
0x140028ad4  mov     rbp, rsp
0x140028ad7  sub     rsp, 60h
0x140028adb  mov     rax, cs:__security_cookie
0x140028ae2  xor     rax, rsp
0x140028ae5  mov     [rbp+var_8], rax
0x140028ae9  movups  xmm0, xmmword ptr cs:aNfsrdrpcompare; "NfsRdrpCompareEAs"
0x140028af0  movzx   eax, word ptr cs:aNfsrdrpcompare+10h; "s"
0x140028af7  mov     rsi, r8
0x140028afa  mov     rdi, rdx
0x140028afd  mov     word ptr [rbp+var_20+10h], ax
0x140028b01  movups  xmmword ptr [rbp+var_20], xmm0
0x140028b05  mov     r14, rcx
0x140028b08  mov     rcx, cs:WPP_GLOBAL_Control
0x140028b0f  lea     r13, WPP_GLOBAL_Control
0x140028b16  cmp     rcx, r13
0x140028b19  jz      short loc_140028B3B
0x140028b1b  mov     eax, [rcx+2Ch]
0x140028b1e  test    al, 8
0x140028b20  jz      short loc_140028B3B
0x140028b22  mov     rcx, [rcx+18h]
0x140028b26  lea     r9, [rbp+var_20]
0x140028b2a  mov     edx, 51h ; 'Q'
0x140028b2f  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140028b36  call    WPP_SF_s
0x140028b3b  mov     rdx, [rdi+20h]; String2
0x140028b3f  test    rdx, rdx
0x140028b42  jz      short loc_140028B80
0x140028b44  lea     rcx, [rsi+20h]; String1
0x140028b48  xor     eax, eax
0x140028b4a  cmp     ax, [rcx]
0x140028b4d  jz      short loc_140028B80
0x140028b4f  mov     r8b, 1; CaseInSensitive
0x140028b52  call    cs:__imp_RtlCompareUnicodeString
0x140028b59  nop     dword ptr [rax+rax+00h]
0x140028b5e  test    eax, eax
0x140028b60  jz      short loc_140028B80
0x140028b62  mov     rcx, cs:WPP_GLOBAL_Control
0x140028b69  cmp     rcx, r13
0x140028b6c  jz      short loc_140028BD5
0x140028b6e  mov     eax, [rcx+2Ch]
0x140028b71  test    al, 1
0x140028b73  jz      short loc_140028BD5
0x140028b75  mov     rax, [rdi+20h]
0x140028b79  mov     edx, 52h ; 'R'
0x140028b7e  jmp     short loc_140028BC3
0x140028b80  mov     rdx, [rdi+10h]; String2
0x140028b84  test    rdx, rdx
0x140028b87  jz      short loc_140028BDF
0x140028b89  lea     rcx, [rsi+30h]; String1
0x140028b8d  xor     eax, eax
0x140028b8f  cmp     ax, [rcx]
0x140028b92  jz      short loc_140028BDF
0x140028b94  mov     r8b, 1; CaseInSensitive
0x140028b97  call    cs:__imp_RtlCompareUnicodeString
0x140028b9e  nop     dword ptr [rax+rax+00h]
0x140028ba3  test    eax, eax
0x140028ba5  jz      short loc_140028BDF
0x140028ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x140028bae  cmp     rcx, r13
0x140028bb1  jz      short loc_140028BD5
0x140028bb3  mov     eax, [rcx+2Ch]
0x140028bb6  test    al, 1
0x140028bb8  jz      short loc_140028BD5
0x140028bba  mov     rax, [rdi+10h]
0x140028bbe  mov     edx, 53h ; 'S'
0x140028bc3  mov     rcx, [rcx+18h]
0x140028bc7  lea     r9, [rbp+var_20]
0x140028bcb  mov     [rsp+60h+var_40], rax
0x140028bd0  call    WPP_SF_sZ
0x140028bd5  mov     ebx, 0C0000195h
0x140028bda  jmp     loc_140028CB8
0x140028bdf  mov     r9, [rdi+18h]
0x140028be3  xor     ebx, ebx
0x140028be5  test    r9, r9
0x140028be8  jz      loc_140028CB8
0x140028bee  cmp     [rsi+40h], rbx
0x140028bf2  jz      loc_140028CB8
0x140028bf8  movzx   eax, word ptr [r9]
0x140028bfc  lea     rcx, [r14+548h]
0x140028c03  mov     r9, [r9+8]
0x140028c07  lea     r8, [rbp+Size]
0x140028c0b  lea     rdx, [rbp+Buf1]
0x140028c0f  mov     dword ptr [rsp+60h+var_40], eax
0x140028c13  mov     [rbp+Buf1], rbx
0x140028c17  mov     dword ptr [rbp+Size], ebx
0x140028c1a  call    NfsRdrCryptoHash
0x140028c1f  mov     ebx, eax
0x140028c21  test    eax, eax
0x140028c23  js      short loc_140028C88
0x140028c25  mov     eax, dword ptr [rbp+Size]
0x140028c28  cmp     eax, [rsi+48h]
0x140028c2b  jnz     short loc_140028C41
0x140028c2d  mov     rdx, [rsi+40h]; Buf2
0x140028c31  mov     r8d, eax; Size
0x140028c34  mov     rcx, [rbp+Buf1]; Buf1
0x140028c38  call    memcmp
0x140028c3d  test    eax, eax
0x140028c3f  jz      short loc_140028C72
0x140028c41  mov     rcx, cs:WPP_GLOBAL_Control
0x140028c48  cmp     rcx, r13
0x140028c4b  jz      short loc_140028C6D
0x140028c4d  mov     eax, [rcx+2Ch]
0x140028c50  test    al, 1
0x140028c52  jz      short loc_140028C6D
0x140028c54  mov     rcx, [rcx+18h]
0x140028c58  lea     r9, [rbp+var_20]
0x140028c5c  mov     edx, 54h ; 'T'
0x140028c61  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140028c68  call    WPP_SF_s
0x140028c6d  mov     ebx, 0C0000195h
0x140028c72  mov     rcx, [rbp+Buf1]; P
0x140028c76  xor     edx, edx; Tag
0x140028c78  call    cs:__imp_ExFreePoolWithTag
0x140028c7f  nop     dword ptr [rax+rax+00h]
0x140028c84  test    ebx, ebx
0x140028c86  jns     short loc_140028CB8
0x140028c88  mov     rcx, cs:WPP_GLOBAL_Control
0x140028c8f  cmp     rcx, r13
0x140028c92  jz      short loc_140028CE8
0x140028c94  mov     eax, [rcx+2Ch]
0x140028c97  test    al, 1
0x140028c99  jz      short loc_140028CB8
0x140028c9b  mov     rcx, [rcx+18h]
0x140028c9f  lea     r9, [rbp+var_20]
0x140028ca3  mov     edx, 55h ; 'U'
0x140028ca8  mov     dword ptr [rsp+60h+var_40], ebx
0x140028cac  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140028cb3  call    WPP_SF_sD
0x140028cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140028cbf  cmp     rcx, r13
0x140028cc2  jz      short loc_140028CE8
0x140028cc4  mov     eax, [rcx+2Ch]
0x140028cc7  test    al, 8
0x140028cc9  jz      short loc_140028CE8
0x140028ccb  mov     rcx, [rcx+18h]
0x140028ccf  lea     r9, [rbp+var_20]
0x140028cd3  mov     edx, 56h ; 'V'
0x140028cd8  mov     dword ptr [rsp+60h+var_40], ebx
0x140028cdc  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140028ce3  call    WPP_SF_sD
0x140028ce8  mov     eax, ebx
0x140028cea  mov     rcx, [rbp+var_8]
0x140028cee  xor     rcx, rsp; StackCookie
0x140028cf1  call    __security_check_cookie
0x140028cf6  mov     rbx, [rsp+60h+arg_18]
0x140028cfe  add     rsp, 60h
0x140028d02  pop     r14
0x140028d04  pop     r13
0x140028d06  pop     rdi
0x140028d07  pop     rsi
0x140028d08  pop     rbp
0x140028d09  retn
```
