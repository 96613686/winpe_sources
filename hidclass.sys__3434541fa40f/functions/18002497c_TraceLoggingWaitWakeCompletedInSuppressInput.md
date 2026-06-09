# TraceLoggingWaitWakeCompletedInSuppressInput

- ea: `0x18002497c`
- end: `0x180024b04`
- name: `TraceLoggingWaitWakeCompletedInSuppressInput`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001b4f0`

## callees

- `0x1800142c4`
- `0x180019664`
- `0x18002497c`
- `0x180027ba0`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingWaitWakeCompletedInSuppressInput(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned __int16 a6,
        int a7,
        char a8)
{
  NTSTATUS result; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r10
  int v12; // r11d
  __int16 v13; // ax
  __int16 v14; // ax
  char v15; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v16; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v17; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v18; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned __int16 v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+60h] [rbp-A0h] BYREF
  __int16 *v24; // [rsp+80h] [rbp-80h]
  __int64 v25; // [rsp+88h] [rbp-78h]
  __int16 *v26; // [rsp+90h] [rbp-70h]
  __int64 v27; // [rsp+98h] [rbp-68h]
  int *v28; // [rsp+A0h] [rbp-60h]
  __int64 v29; // [rsp+A8h] [rbp-58h]
  __int64 *v30; // [rsp+B0h] [rbp-50h]
  __int64 v31; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+C8h] [rbp-38h]
  __int64 v34; // [rsp+D0h] [rbp-30h]
  int v35; // [rsp+D8h] [rbp-28h]
  int v36; // [rsp+DCh] [rbp-24h]
  unsigned __int16 *v37; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+E8h] [rbp-18h]
  __int64 v39; // [rsp+F0h] [rbp-10h]
  int v40; // [rsp+F8h] [rbp-8h]
  int v41; // [rsp+FCh] [rbp-4h]
  int *v42; // [rsp+100h] [rbp+0h]
  __int64 v43; // [rsp+108h] [rbp+8h]
  char *v44; // [rsp+110h] [rbp+10h]
  __int64 v45; // [rsp+118h] [rbp+18h]

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn(&dword_1800310D8, 0x400000000000LL, a3);
    if ( (_BYTE)result )
    {
      if ( v11 )
        v13 = *(_WORD *)(v11 + 108);
      else
        v13 = 0;
      v16 = v13;
      v24 = &v16;
      v25 = 2;
      if ( v11 )
        v14 = *(_WORD *)(v11 + 110);
      else
        v14 = 0;
      v17 = v14;
      v32 = &v18;
      v26 = &v17;
      v22 = v9;
      v28 = &v20;
      v34 = v10;
      v30 = &v22;
      v18 = a6;
      v19 = a6;
      v35 = 2 * a6;
      v37 = &v19;
      v39 = a5;
      v21 = a7;
      v42 = &v21;
      v15 = a8;
      v44 = &v15;
      v40 = v35;
      v27 = 2;
      v20 = v12;
      v29 = 4;
      v31 = 8;
      v33 = 2;
      v36 = 0;
      v38 = 2;
      v41 = 0;
      v43 = 4;
      v45 = 1;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)byte_18002CF85,
               0,
               0,
               0xCu,
               &v23);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002497c  push    rbp
0x18002497e  lea     rbp, [rsp-30h]
0x180024983  sub     rsp, 130h
0x18002498a  mov     rax, cs:__security_cookie
0x180024991  xor     rax, rsp
0x180024994  mov     [rbp+30h+var_10], rax
0x180024998  mov     eax, cs:dword_1800310D8
0x18002499e  mov     r11d, edx
0x1800249a1  mov     r10, rcx
0x1800249a4  cmp     eax, 5
0x1800249a7  jbe     loc_180024AEE
0x1800249ad  mov     rdx, 400000000000h
0x1800249b7  lea     rcx, dword_1800310D8
0x1800249be  call    _tlgKeywordOn
0x1800249c3  test    al, al
0x1800249c5  jz      loc_180024AEE
0x1800249cb  test    r10, r10
0x1800249ce  jz      short loc_1800249D7
0x1800249d0  movzx   eax, word ptr [r10+6Ch]
0x1800249d5  jmp     short loc_1800249D9
0x1800249d7  xor     eax, eax
0x1800249d9  mov     [rsp+130h+var_FC], ax
0x1800249de  lea     rax, [rsp+130h+var_FC]
0x1800249e3  mov     [rbp+30h+var_B0], rax
0x1800249e7  mov     [rbp+30h+var_A8], 2
0x1800249ef  test    r10, r10
0x1800249f2  jz      short loc_1800249FB
0x1800249f4  movzx   eax, word ptr [r10+6Eh]
0x1800249f9  jmp     short loc_1800249FD
0x1800249fb  xor     eax, eax
0x1800249fd  mov     [rsp+130h+var_F8], ax
0x180024a02  lea     rcx, [rsp+130h+var_F4]
0x180024a07  mov     [rbp+30h+var_70], rcx
0x180024a0b  lea     rax, [rsp+130h+var_F8]
0x180024a10  mov     [rbp+30h+var_A0], rax
0x180024a14  lea     rdx, byte_18002CF85
0x180024a1b  lea     rax, [rsp+130h+var_EC]
0x180024a20  mov     [rsp+130h+var_E0], r8
0x180024a25  mov     [rbp+30h+var_90], rax
0x180024a29  xor     r8d, r8d
0x180024a2c  lea     rax, [rsp+130h+var_E0]
0x180024a31  mov     [rbp+30h+var_60], r9
0x180024a35  mov     [rbp+30h+var_80], rax
0x180024a39  xor     r9d, r9d
0x180024a3c  movzx   eax, [rbp+30h+arg_28]
0x180024a40  mov     ecx, eax
0x180024a42  mov     [rsp+130h+var_F4], ax
0x180024a47  mov     [rsp+130h+var_F0], ax
0x180024a4c  add     ecx, ecx
0x180024a4e  lea     rax, [rsp+130h+var_F0]
0x180024a53  mov     [rbp+30h+var_58], ecx
0x180024a56  mov     [rbp+30h+var_50], rax
0x180024a5a  mov     rax, [rbp+30h+arg_20]
0x180024a5e  mov     [rbp+30h+var_40], rax
0x180024a62  mov     eax, [rbp+30h+arg_30]
0x180024a65  mov     [rsp+130h+var_E8], eax
0x180024a69  lea     rax, [rsp+130h+var_E8]
0x180024a6e  mov     [rbp+30h+var_30], rax
0x180024a72  mov     al, [rbp+30h+arg_38]
0x180024a75  mov     [rsp+130h+var_100], al
0x180024a79  lea     rax, [rsp+130h+var_100]
0x180024a7e  mov     [rbp+30h+var_20], rax
0x180024a82  lea     rax, [rsp+130h+var_D0]
0x180024a87  mov     [rbp+30h+var_38], ecx
0x180024a8a  lea     rcx, dword_1800310D8
0x180024a91  mov     [rsp+130h+var_108], rax
0x180024a96  mov     [rsp+130h+var_110], 0Ch
0x180024a9e  mov     [rbp+30h+var_98], 2
0x180024aa6  mov     [rsp+130h+var_EC], r11d
0x180024aab  mov     [rbp+30h+var_88], 4
0x180024ab3  mov     [rbp+30h+var_78], 8
0x180024abb  mov     [rbp+30h+var_68], 2
0x180024ac3  mov     [rbp+30h+var_54], 0
0x180024aca  mov     [rbp+30h+var_48], 2
0x180024ad2  mov     [rbp+30h+var_34], 0
0x180024ad9  mov     [rbp+30h+var_28], 4
0x180024ae1  mov     [rbp+30h+var_18], 1
0x180024ae9  call    _tlgWriteTransfer_EtwWriteTransfer
0x180024aee  mov     rcx, [rbp+30h+var_10]
0x180024af2  xor     rcx, rsp; StackCookie
0x180024af5  call    __security_check_cookie
0x180024afa  add     rsp, 130h
0x180024b01  pop     rbp
0x180024b02  retn
```
