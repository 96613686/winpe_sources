# SystemFunction002

- ea: `0x180001a50`
- end: `0x180001beb`
- name: `SystemFunction002`
- size: `411`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180001820`
- `0x180002ae4`
- `0x180002b3c`

## callees

- `0x180001a50`
- `0x1800029f0`
- `0x180002e10`
- `0x1800037d0`
- `0x180003b11`
- `0x180003b50`

## pseudocode

```c
__int64 __fastcall SystemFunction002(__int64 a1, _BYTE *a2, __int64 a3)
{
  unsigned __int8 v6; // dl
  char v7; // cl
  unsigned __int8 v8; // al
  char v9; // cl
  unsigned __int8 v10; // al
  char v11; // dl
  unsigned __int8 v12; // al
  char v13; // cl
  unsigned __int8 v14; // al
  char v15; // dl
  unsigned __int8 v16; // al
  int v17; // ebx
  _BYTE v19[400]; // [rsp+20h] [rbp-1A8h] BYREF
  __int64 v20; // [rsp+1B0h] [rbp-18h] BYREF

  memset_0(v19, 0, sizeof(v19));
  v6 = a2[1];
  v7 = *a2 & 1;
  LOBYTE(v20) = *a2 >> 1;
  BYTE1(v20) = (v6 >> 2) | (v7 << 6);
  v8 = a2[2];
  v9 = 16 * (v8 & 7);
  BYTE2(v20) = (v8 >> 3) | (32 * (v6 & 3));
  v10 = a2[3];
  v11 = 8 * (v10 & 0xF);
  BYTE3(v20) = (v10 >> 4) | v9;
  v12 = a2[4];
  v13 = 4 * (v12 & 0x1F);
  BYTE4(v20) = (v12 >> 5) | v11;
  v14 = a2[5];
  v15 = v14 & 0x3F;
  BYTE5(v20) = (v14 >> 6) | v13;
  v16 = a2[6];
  HIBYTE(v20) = v16 & 0x7F;
  BYTE6(v20) = (v16 >> 7) | (2 * v15);
  LODWORD(v20) = 2 * (v20 & 0xFF7F7F7F);
  HIDWORD(v20) = 2 * (HIDWORD(v20) & 0xFF7F7F7F);
  v17 = SymCrypt3DesExpandKey(v19, &v20, 8);
  v20 = 0;
  if ( v17 )
    SymCryptWipeAsm(v19, 400);
  else
    SymCrypt3DesDecrypt(v19, a1, a3);
  SymCryptWipeAsm(v19, 400);
  return v17 != 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x180001a50  mov     [rsp+arg_8], rbx
0x180001a55  mov     [rsp+arg_18], rsi
0x180001a5a  push    rdi
0x180001a5b  sub     rsp, 1C0h
0x180001a62  mov     rax, cs:__security_cookie
0x180001a69  xor     rax, rsp
0x180001a6c  mov     [rsp+1C8h+var_10], rax
0x180001a74  mov     rsi, r8
0x180001a77  mov     rbx, rdx
0x180001a7a  mov     rdi, rcx
0x180001a7d  xor     edx, edx; Val
0x180001a7f  mov     r8d, 190h; Size
0x180001a85  lea     rcx, [rsp+1C8h+var_1A8]; void *
0x180001a8a  call    memset_0
0x180001a8f  movzx   ecx, byte ptr [rbx]
0x180001a92  mov     r8d, 8
0x180001a98  movzx   edx, byte ptr [rbx+1]
0x180001a9c  movzx   eax, cl
0x180001a9f  shr     al, 1
0x180001aa1  and     cl, 1
0x180001aa4  mov     byte ptr [rsp+1C8h+var_18], al
0x180001aab  movzx   eax, dl
0x180001aae  shr     al, 2
0x180001ab1  and     dl, 3
0x180001ab4  shl     cl, 6
0x180001ab7  or      cl, al
0x180001ab9  shl     dl, 5
0x180001abc  mov     byte ptr [rsp+1C8h+var_18+1], cl
0x180001ac3  movzx   ecx, byte ptr [rbx+2]
0x180001ac7  movzx   eax, cl
0x180001aca  and     cl, 7
0x180001acd  shr     al, 3
0x180001ad0  or      dl, al
0x180001ad2  shl     cl, 4
0x180001ad5  mov     byte ptr [rsp+1C8h+var_18+2], dl
0x180001adc  movzx   edx, byte ptr [rbx+3]
0x180001ae0  movzx   eax, dl
0x180001ae3  and     dl, 0Fh
0x180001ae6  shr     al, 4
0x180001ae9  or      cl, al
0x180001aeb  shl     dl, 3
0x180001aee  mov     byte ptr [rsp+1C8h+var_18+3], cl
0x180001af5  movzx   ecx, byte ptr [rbx+4]
0x180001af9  movzx   eax, cl
0x180001afc  and     cl, 1Fh
0x180001aff  shr     al, 5
0x180001b02  or      dl, al
0x180001b04  shl     cl, 2
0x180001b07  mov     byte ptr [rsp+1C8h+var_18+4], dl
0x180001b0e  movzx   edx, byte ptr [rbx+5]
0x180001b12  movzx   eax, dl
0x180001b15  and     dl, 3Fh
0x180001b18  shr     al, 6
0x180001b1b  add     dl, dl
0x180001b1d  or      cl, al
0x180001b1f  mov     byte ptr [rsp+1C8h+var_18+5], cl
0x180001b26  movzx   ecx, byte ptr [rbx+6]
0x180001b2a  movzx   eax, cl
0x180001b2d  and     cl, 7Fh
0x180001b30  shr     al, 7
0x180001b33  or      dl, al
0x180001b35  mov     byte ptr [rsp+1C8h+var_18+7], cl
0x180001b3c  mov     eax, dword ptr [rsp+1C8h+var_18]
0x180001b43  lea     rcx, [rsp+1C8h+var_1A8]
0x180001b48  and     eax, 0FF7F7F7Fh
0x180001b4d  mov     byte ptr [rsp+1C8h+var_18+6], dl
0x180001b54  add     eax, eax
0x180001b56  lea     rdx, [rsp+1C8h+var_18]
0x180001b5e  mov     dword ptr [rsp+1C8h+var_18], eax
0x180001b65  mov     eax, dword ptr [rsp+1C8h+var_18+4]
0x180001b6c  and     eax, 0FF7F7F7Fh
0x180001b71  add     eax, eax
0x180001b73  mov     dword ptr [rsp+1C8h+var_18+4], eax
0x180001b7a  call    SymCrypt3DesExpandKey
0x180001b7f  mov     ebx, eax
0x180001b81  mov     [rsp+1C8h+var_18], 0
0x180001b8d  lea     rcx, [rsp+1C8h+var_1A8]
0x180001b92  test    eax, eax
0x180001b94  jz      short loc_180001BA2
0x180001b96  mov     edx, 190h
0x180001b9b  call    SymCryptWipeAsm
0x180001ba0  jmp     short loc_180001BAD
0x180001ba2  mov     r8, rsi
0x180001ba5  mov     rdx, rdi
0x180001ba8  call    SymCrypt3DesDecrypt
0x180001bad  mov     edx, 190h
0x180001bb2  lea     rcx, [rsp+1C8h+var_1A8]
0x180001bb7  call    SymCryptWipeAsm
0x180001bbc  neg     ebx
0x180001bbe  sbb     eax, eax
0x180001bc0  and     eax, 0C0000001h
0x180001bc5  mov     rcx, [rsp+1C8h+var_10]
0x180001bcd  xor     rcx, rsp; StackCookie
0x180001bd0  call    __security_check_cookie
0x180001bd5  lea     r11, [rsp+1C8h+var_8]
0x180001bdd  mov     rbx, [r11+18h]
0x180001be1  mov     rsi, [r11+28h]
0x180001be5  mov     rsp, r11
0x180001be8  pop     rdi
0x180001be9  retn
```
