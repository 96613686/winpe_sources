# aesCTSEncrypt

- ea: `0x180003110`
- end: `0x180003318`
- name: `aesCTSEncrypt`
- size: `520`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE hKey, PUCHAR pbIV)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002d80`
- `0x180005b40`
- `0x180005d80`

## callees

- `0x180003110`
- `0x180004c40`
- `0x1800054be`
- `0x180008415`

## import_xrefs

- `bcrypt!BCryptEncrypt` at `0x1800031ff`
- `bcrypt!BCryptEncrypt` at `0x1800032ac`
- `bcrypt!BCryptEncrypt` at `0x18000330d`
- `bcrypt!BCryptEncrypt` at `0x1800031ff`
- `bcrypt!BCryptEncrypt` at `0x1800032ac`
- `bcrypt!BCryptEncrypt` at `0x18000330d`

## pseudocode

```c
int __fastcall aesCTSEncrypt(BCRYPT_KEY_HANDLE hKey, PUCHAR pbIV, unsigned int a3, UCHAR *pbOutput)
{
  unsigned int v7; // ebx
  int v8; // r8d
  unsigned int v9; // edi
  size_t v10; // r12
  int result; // eax
  int v12; // edi
  ULONG pcbResult; // [rsp+50h] [rbp-78h] BYREF
  UCHAR pbInput[16]; // [rsp+58h] [rbp-70h] BYREF
  __int128 v15; // [rsp+68h] [rbp-60h] BYREF

  if ( a3 < 0x10 )
    return -1073741811;
  if ( a3 == 16 )
  {
    pcbResult = 16;
    *(_OWORD *)pbIV = 0;
    return BCryptEncrypt(hKey, pbOutput, 0x10u, 0, pbIV, 0x10u, pbOutput, 0x10u, &pcbResult, 0);
  }
  else
  {
    v7 = (a3 + 15) >> 4;
    v8 = a3 & 0xF;
    v9 = 16;
    if ( v8 )
      v9 = v8;
    if ( v7 <= 2
      || (pcbResult = 16 * v7 - 32,
          result = BCryptEncrypt(hKey, pbOutput, pcbResult, 0, pbIV, 0x10u, pbOutput, pcbResult, &pcbResult, 0),
          result >= 0) )
    {
      memcpy_0(pbInput, &pbOutput[16 * v7 - 32], v9 + 16);
      v10 = v9;
      memset_0((char *)&v15 + v9, 0, 16 - v9);
      pcbResult = 32;
      result = BCryptEncrypt(hKey, pbInput, 0x20u, 0, pbIV, 0x10u, pbInput, 0x20u, &pcbResult, 0);
      v12 = result;
      if ( result >= 0 )
      {
        *(_OWORD *)&pbOutput[16 * v7 - 32] = v15;
        memcpy_0(&pbOutput[16 * v7 - 16], pbInput, v10);
        return v12;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003110  mov     r11, rsp
0x180003113  push    rsi
0x180003114  push    r14
0x180003116  push    r15
0x180003118  sub     rsp, 0B0h
0x18000311f  mov     rax, cs:__security_cookie
0x180003126  xor     rax, rsp
0x180003129  mov     [rsp+0C8h+var_50], rax
0x18000312e  mov     rsi, r9
0x180003131  mov     r14, rdx
0x180003134  mov     r15, rcx
0x180003137  cmp     r8d, 10h
0x18000313b  jb      loc_1800032BF
0x180003141  mov     [r11-28h], rbp
0x180003145  jz      loc_1800032C9
0x18000314b  mov     [r11-20h], rbx
0x18000314f  lea     ebx, [r8+0Fh]
0x180003153  shr     ebx, 4
0x180003156  and     r8d, 0Fh
0x18000315a  mov     [r11-30h], rdi
0x18000315e  mov     edi, 10h
0x180003163  cmovnz  edi, r8d
0x180003167  xor     ebp, ebp
0x180003169  cmp     ebx, 2
0x18000316c  ja      loc_180003271
0x180003172  mov     [rsp+0C8h+var_38], r12
0x18000317a  lea     r8d, [rdi+10h]; Size
0x18000317e  mov     [rsp+0C8h+var_40], r13
0x180003186  lea     rcx, [rsp+0C8h+pbInput]; void *
0x18000318b  lea     r13d, [rbx-2]
0x18000318f  shl     r13d, 4
0x180003193  add     r13, rsi
0x180003196  mov     rdx, r13; Src
0x180003199  call    memcpy_0
0x18000319e  mov     r8d, 10h
0x1800031a4  mov     r12d, edi
0x1800031a7  lea     rcx, [rsp+0C8h+var_60]
0x1800031ac  sub     r8d, edi; Size
0x1800031af  add     rcx, r12; void *
0x1800031b2  xor     edx, edx; Val
0x1800031b4  call    memset_0
0x1800031b9  mov     [rsp+0C8h+dwFlags], ebp; dwFlags
0x1800031bd  lea     rax, [rsp+0C8h+var_78]
0x1800031c2  mov     [rsp+0C8h+pcbResult], rax; pcbResult
0x1800031c7  lea     rdx, [rsp+0C8h+pbInput]; pbInput
0x1800031cc  mov     [rsp+0C8h+cbOutput], 20h ; ' '; cbOutput
0x1800031d4  lea     rax, [rsp+0C8h+pbInput]
0x1800031d9  mov     [rsp+0C8h+pbOutput], rax; pbOutput
0x1800031de  xor     r9d, r9d; pPaddingInfo
0x1800031e1  mov     [rsp+0C8h+cbIV], 10h; cbIV
0x1800031e9  mov     r8d, 20h ; ' '; cbInput
0x1800031ef  mov     rcx, r15; hKey
0x1800031f2  mov     [rsp+0C8h+pbIV], r14; pbIV
0x1800031f7  mov     [rsp+0C8h+var_78], 20h ; ' '
0x1800031ff  call    cs:__imp_BCryptEncrypt
0x180003205  mov     edi, eax
0x180003207  test    eax, eax
0x180003209  jns     short loc_18000324D
0x18000320b  mov     r12, [rsp+0C8h+var_38]
0x180003213  mov     r13, [rsp+0C8h+var_40]
0x18000321b  mov     rbx, [rsp+0C8h+var_20]
0x180003223  mov     rdi, [rsp+0C8h+var_30]
0x18000322b  mov     rbp, [rsp+0C8h+var_28]
0x180003233  mov     rcx, [rsp+0C8h+var_50]
0x180003238  xor     rcx, rsp; StackCookie
0x18000323b  call    __security_check_cookie
0x180003240  add     rsp, 0B0h
0x180003247  pop     r15
0x180003249  pop     r14
0x18000324b  pop     rsi
0x18000324c  retn
0x18000324d  movups  xmm0, [rsp+0C8h+var_60]
0x180003252  shl     ebx, 4
0x180003255  lea     rdx, [rsp+0C8h+pbInput]; Src
0x18000325a  mov     r8, r12; Size
0x18000325d  movups  xmmword ptr [r13+0], xmm0
0x180003262  lea     ecx, [rbx-10h]
0x180003265  add     rcx, rsi; void *
0x180003268  call    memcpy_0
0x18000326d  mov     eax, edi
0x18000326f  jmp     short loc_18000320B
0x180003271  mov     [rsp+0C8h+dwFlags], ebp; dwFlags
0x180003275  lea     rax, [rsp+0C8h+var_78]
0x18000327a  mov     [rsp+0C8h+pcbResult], rax; pcbResult
0x18000327f  mov     r8d, ebx
0x180003282  shl     r8d, 4
0x180003286  xor     r9d, r9d; pPaddingInfo
0x180003289  add     r8d, 0FFFFFFE0h; cbInput
0x18000328d  mov     rdx, rsi; pbInput
0x180003290  mov     [rsp+0C8h+cbOutput], r8d; cbOutput
0x180003295  mov     [rsp+0C8h+pbOutput], rsi; pbOutput
0x18000329a  mov     [rsp+0C8h+cbIV], 10h; cbIV
0x1800032a2  mov     [rsp+0C8h+pbIV], r14; pbIV
0x1800032a7  mov     [rsp+0C8h+var_78], r8d
0x1800032ac  call    cs:__imp_BCryptEncrypt
0x1800032b2  test    eax, eax
0x1800032b4  js      loc_18000321B
0x1800032ba  jmp     loc_180003172
0x1800032bf  mov     eax, 0C000000Dh
0x1800032c4  jmp     loc_180003233
0x1800032c9  xor     ebp, ebp
0x1800032cb  mov     [rsp+0C8h+var_78], 10h
0x1800032d3  mov     [rsp+0C8h+dwFlags], ebp; dwFlags
0x1800032d7  lea     rax, [rsp+0C8h+var_78]
0x1800032dc  mov     [rsp+0C8h+pcbResult], rax; pcbResult
0x1800032e1  xorps   xmm0, xmm0
0x1800032e4  mov     [rsp+0C8h+cbOutput], 10h; cbOutput
0x1800032ec  xor     r9d, r9d; pPaddingInfo
0x1800032ef  mov     [rsp+0C8h+pbOutput], rsi; pbOutput
0x1800032f4  mov     r8d, 10h; cbInput
0x1800032fa  movups  xmmword ptr [rdx], xmm0
0x1800032fd  mov     [rsp+0C8h+cbIV], 10h; cbIV
0x180003305  mov     rdx, rsi; pbInput
0x180003308  mov     [rsp+0C8h+pbIV], r14; pbIV
0x18000330d  call    cs:__imp_BCryptEncrypt
0x180003313  jmp     loc_18000322B
```
