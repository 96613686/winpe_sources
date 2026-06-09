# HbpLogHypervisorMsrAccessBitmapTelemetryEvent

- ea: `0x140013a60`
- end: `0x140013b2e`
- name: `HbpLogHypervisorMsrAccessBitmapTelemetryEvent`
- size: `206`
- prototype: `char()`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140012524`

## callees

- `0x140001040`
- `0x140001070`
- `0x140002ae0`
- `0x140013a60`

## pseudocode

```c
char HbpLogHypervisorMsrAccessBitmapTelemetryEvent()
{
  char result; // al
  __int64 v1; // r8
  __int64 v2; // r9
  int v3; // [rsp+30h] [rbp-29h] BYREF
  __int64 v4; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+40h] [rbp-19h] BYREF
  int *v6; // [rsp+60h] [rbp+7h]
  __int64 v7; // [rsp+68h] [rbp+Fh]
  _DWORD *v8; // [rsp+70h] [rbp+17h]
  __int64 v9; // [rsp+78h] [rbp+1Fh]
  __int64 v10; // [rsp+80h] [rbp+27h]
  _DWORD v11[2]; // [rsp+88h] [rbp+2Fh] BYREF
  __int64 *v12; // [rsp+90h] [rbp+37h]
  __int64 v13; // [rsp+98h] [rbp+3Fh]

  result = dword_140009088;
  if ( (unsigned int)dword_140009088 > 5 )
  {
    result = tlgKeywordOn((__int64)&dword_140009088, 0x400000000001LL);
    if ( result )
    {
      v11[1] = 0;
      v6 = &v3;
      v3 = v1;
      v8 = v11;
      v7 = 4;
      v12 = &v4;
      v9 = 2;
      v10 = v2;
      v11[0] = v1;
      v4 = 0x2000000;
      v13 = 8;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_140009088,
               (unsigned __int8 *)&word_1400072D2,
               v1,
               v2,
               6u,
               &v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140013a60  push    rbp
0x140013a62  lea     rbp, [rsp-57h]
0x140013a67  sub     rsp, 0B0h
0x140013a6e  mov     rax, cs:__security_cookie
0x140013a75  xor     rax, rsp
0x140013a78  mov     [rbp+57h+var_10], rax
0x140013a7c  mov     eax, cs:dword_140009088
0x140013a82  mov     r9, rdx
0x140013a85  mov     r8d, ecx
0x140013a88  cmp     eax, 5
0x140013a8b  jbe     loc_140013B18
0x140013a91  mov     rdx, 400000000001h
0x140013a9b  lea     rcx, dword_140009088
0x140013aa2  call    _tlgKeywordOn
0x140013aa7  xor     edx, edx
0x140013aa9  test    al, al
0x140013aab  jz      short loc_140013B18
0x140013aad  lea     rax, [rbp+57h+var_80]
0x140013ab1  mov     [rbp+57h+var_24], edx
0x140013ab4  mov     [rbp+57h+var_50], rax
0x140013ab8  lea     rdx, word_1400072D2; int
0x140013abf  lea     rax, [rbp+57h+var_28]
0x140013ac3  mov     [rbp+57h+var_80], r8d
0x140013ac7  mov     [rbp+57h+var_40], rax
0x140013acb  lea     rcx, dword_140009088; int
0x140013ad2  lea     rax, [rbp+57h+var_78]
0x140013ad6  mov     [rbp+57h+var_48], 4
0x140013ade  mov     [rbp+57h+var_20], rax
0x140013ae2  lea     rax, [rbp+57h+var_70]
0x140013ae6  mov     [rsp+0B0h+var_88], rax; __int64
0x140013aeb  mov     [rsp+0B0h+var_90], 6; ULONG
0x140013af3  mov     [rbp+57h+var_38], 2
0x140013afb  mov     [rbp+57h+var_30], r9
0x140013aff  mov     [rbp+57h+var_28], r8d
0x140013b03  mov     [rbp+57h+var_78], 2000000h
0x140013b0b  mov     [rbp+57h+var_18], 8
0x140013b13  call    _tlgWriteTransfer_EtwWriteTransfer
0x140013b18  mov     rcx, [rbp+57h+var_10]
0x140013b1c  xor     rcx, rsp; StackCookie
0x140013b1f  call    __security_check_cookie
0x140013b24  add     rsp, 0B0h
0x140013b2b  pop     rbp
0x140013b2c  retn
```
