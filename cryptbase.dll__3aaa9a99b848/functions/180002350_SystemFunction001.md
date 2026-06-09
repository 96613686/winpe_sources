# SystemFunction001

- ea: `0x180002350`
- end: `0x1800024eb`
- name: `SystemFunction001`
- size: `411`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180002500`
- `0x180002bdc`
- `0x180002c90`

## callees

- `0x180002350`
- `0x1800029f0`
- `0x1800032f4`
- `0x1800037d0`
- `0x180003b11`
- `0x180003b50`

## pseudocode

```c
__int64 __fastcall SystemFunction001(__int64 a1, _BYTE *a2, __int64 a3)
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
    SymCrypt3DesEncrypt(v19, a1, a3);
  SymCryptWipeAsm(v19, 400);
  return v17 != 0 ? 0xC0000001 : 0;
}

```

## disassembly

```asm
0x180002350  mov     [rsp+arg_8], rbx
0x180002355  mov     [rsp+arg_18], rsi
0x18000235a  push    rdi
0x18000235b  sub     rsp, 1C0h
0x180002362  mov     rax, cs:__security_cookie
0x180002369  xor     rax, rsp
0x18000236c  mov     [rsp+1C8h+var_10], rax
0x180002374  mov     rsi, r8
0x180002377  mov     rbx, rdx
0x18000237a  mov     rdi, rcx
0x18000237d  xor     edx, edx; Val
0x18000237f  mov     r8d, 190h; Size
0x180002385  lea     rcx, [rsp+1C8h+var_1A8]; void *
0x18000238a  call    memset_0
0x18000238f  movzx   ecx, byte ptr [rbx]
0x180002392  mov     r8d, 8
0x180002398  movzx   edx, byte ptr [rbx+1]
0x18000239c  movzx   eax, cl
0x18000239f  shr     al, 1
0x1800023a1  and     cl, 1
0x1800023a4  mov     byte ptr [rsp+1C8h+var_18], al
0x1800023ab  movzx   eax, dl
0x1800023ae  shr     al, 2
0x1800023b1  and     dl, 3
0x1800023b4  shl     cl, 6
0x1800023b7  or      cl, al
0x1800023b9  shl     dl, 5
0x1800023bc  mov     byte ptr [rsp+1C8h+var_18+1], cl
0x1800023c3  movzx   ecx, byte ptr [rbx+2]
0x1800023c7  movzx   eax, cl
0x1800023ca  and     cl, 7
0x1800023cd  shr     al, 3
0x1800023d0  or      dl, al
0x1800023d2  shl     cl, 4
0x1800023d5  mov     byte ptr [rsp+1C8h+var_18+2], dl
0x1800023dc  movzx   edx, byte ptr [rbx+3]
0x1800023e0  movzx   eax, dl
0x1800023e3  and     dl, 0Fh
0x1800023e6  shr     al, 4
0x1800023e9  or      cl, al
0x1800023eb  shl     dl, 3
0x1800023ee  mov     byte ptr [rsp+1C8h+var_18+3], cl
0x1800023f5  movzx   ecx, byte ptr [rbx+4]
0x1800023f9  movzx   eax, cl
0x1800023fc  and     cl, 1Fh
0x1800023ff  shr     al, 5
0x180002402  or      dl, al
0x180002404  shl     cl, 2
0x180002407  mov     byte ptr [rsp+1C8h+var_18+4], dl
0x18000240e  movzx   edx, byte ptr [rbx+5]
0x180002412  movzx   eax, dl
0x180002415  and     dl, 3Fh
0x180002418  shr     al, 6
0x18000241b  add     dl, dl
0x18000241d  or      cl, al
0x18000241f  mov     byte ptr [rsp+1C8h+var_18+5], cl
0x180002426  movzx   ecx, byte ptr [rbx+6]
0x18000242a  movzx   eax, cl
0x18000242d  and     cl, 7Fh
0x180002430  shr     al, 7
0x180002433  or      dl, al
0x180002435  mov     byte ptr [rsp+1C8h+var_18+7], cl
0x18000243c  mov     eax, dword ptr [rsp+1C8h+var_18]
0x180002443  lea     rcx, [rsp+1C8h+var_1A8]
0x180002448  and     eax, 0FF7F7F7Fh
0x18000244d  mov     byte ptr [rsp+1C8h+var_18+6], dl
0x180002454  add     eax, eax
0x180002456  lea     rdx, [rsp+1C8h+var_18]
0x18000245e  mov     dword ptr [rsp+1C8h+var_18], eax
0x180002465  mov     eax, dword ptr [rsp+1C8h+var_18+4]
0x18000246c  and     eax, 0FF7F7F7Fh
0x180002471  add     eax, eax
0x180002473  mov     dword ptr [rsp+1C8h+var_18+4], eax
0x18000247a  call    SymCrypt3DesExpandKey
0x18000247f  mov     ebx, eax
0x180002481  mov     [rsp+1C8h+var_18], 0
0x18000248d  lea     rcx, [rsp+1C8h+var_1A8]
0x180002492  test    eax, eax
0x180002494  jz      short loc_1800024A2
0x180002496  mov     edx, 190h
0x18000249b  call    SymCryptWipeAsm
0x1800024a0  jmp     short loc_1800024AD
0x1800024a2  mov     r8, rsi
0x1800024a5  mov     rdx, rdi
0x1800024a8  call    SymCrypt3DesEncrypt
0x1800024ad  mov     edx, 190h
0x1800024b2  lea     rcx, [rsp+1C8h+var_1A8]
0x1800024b7  call    SymCryptWipeAsm
0x1800024bc  neg     ebx
0x1800024be  sbb     eax, eax
0x1800024c0  and     eax, 0C0000001h
0x1800024c5  mov     rcx, [rsp+1C8h+var_10]
0x1800024cd  xor     rcx, rsp; StackCookie
0x1800024d0  call    __security_check_cookie
0x1800024d5  lea     r11, [rsp+1C8h+var_8]
0x1800024dd  mov     rbx, [r11+18h]
0x1800024e1  mov     rsi, [r11+28h]
0x1800024e5  mov     rsp, r11
0x1800024e8  pop     rdi
0x1800024e9  retn
```
