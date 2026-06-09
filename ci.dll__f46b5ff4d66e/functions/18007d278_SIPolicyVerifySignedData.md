# SIPolicyVerifySignedData

- ea: `0x18007d278`
- end: `0x18007d3b1`
- name: `SIPolicyVerifySignedData`
- size: `313`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180076d48`
- `0x18007bbcc`
- `0x18007d158`

## callees

- `0x18002bef0`
- `0x18007d278`
- `0x18008d6e0`
- `0x18008de28`
- `0x1800941c8`
- `0x180096fdc`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x18007d312`
- `ntoskrnl!RtlCompareMemory` at `0x18007d312`

## pseudocode

```c
__int64 __fastcall SIPolicyVerifySignedData(
        int a1,
        int a2,
        const void *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  int v9; // ebx
  int v11[4]; // [rsp+50h] [rbp-89h] BYREF
  __int128 v12; // [rsp+60h] [rbp-79h]
  __int128 v13; // [rsp+70h] [rbp-69h]
  int v14; // [rsp+80h] [rbp-59h] BYREF
  void *Source2; // [rsp+88h] [rbp-51h]
  unsigned int v16; // [rsp+90h] [rbp-49h]
  __int64 v17; // [rsp+98h] [rbp-41h]

  *(_OWORD *)v11 = 0;
  v12 = 0;
  v13 = 0;
  v9 = MinCrypK_VerifySignedDataKModeEx(a1, a2, 0, 0, a5, (int)v11, &v14, 0, 0);
  if ( v9 >= 0 )
  {
    if ( v14 == 9
      && RtlCompareMemory(a3, Source2, 9u) == 9
      && (int)MinAsn1ExtractContent(v17, v16, a7, a6) >= 0
      && (!a5 || (*(_DWORD *)(a5 + 4) & 0x20) == 0 || (v11[2] & 0x4000) != 0)
      && v11[0]
      && (_QWORD)v12
      && (v11[2] & 0xFFFF0000) == 0 )
    {
      if ( a8 )
        v9 = SIPolicyConvertChainInfo(v12, a8);
    }
    else
    {
      v9 = -1073740760;
    }
  }
  if ( v11[0] )
    I_MincryptFreeChainInfo(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18007d278  push    rbp
0x18007d27a  push    rbx
0x18007d27b  push    rsi
0x18007d27c  push    rdi
0x18007d27d  push    r12
0x18007d27f  push    r14
0x18007d281  push    r15
0x18007d283  lea     rbp, [rsp-7]
0x18007d288  sub     rsp, 0E0h
0x18007d28f  mov     rax, cs:__security_cookie
0x18007d296  xor     rax, rsp
0x18007d299  mov     [rbp+37h+var_40], rax
0x18007d29d  mov     rdi, [rbp+37h+arg_20]
0x18007d2a1  lea     rax, [rbp+37h+var_90]
0x18007d2a5  mov     r15, [rbp+37h+arg_28]
0x18007d2a9  xorps   xmm0, xmm0
0x18007d2ac  mov     r12, [rbp+37h+arg_30]
0x18007d2b0  mov     r14, r8
0x18007d2b3  mov     rsi, [rbp+37h+arg_38]
0x18007d2b7  xor     r9d, r9d; int
0x18007d2ba  mov     [rsp+110h+var_D0], 0; __int64
0x18007d2c3  xor     r8d, r8d; int
0x18007d2c6  mov     [rsp+110h+var_D8], 0; __int64
0x18007d2cf  mov     [rsp+110h+var_E0], rax; void *
0x18007d2d4  lea     rax, [rsp+110h+var_C0]
0x18007d2d9  mov     qword ptr [rsp+110h+var_E8], rax; int
0x18007d2de  mov     [rsp+110h+var_F0], rdi; __int64
0x18007d2e3  movups  xmmword ptr [rsp+110h+var_C0], xmm0
0x18007d2e8  movups  [rbp+37h+var_B0], xmm0
0x18007d2ec  movups  [rbp+37h+var_A0], xmm0
0x18007d2f0  call    MinCrypK_VerifySignedDataKModeEx
0x18007d2f5  mov     ebx, eax
0x18007d2f7  test    eax, eax
0x18007d2f9  js      loc_18007D380
0x18007d2ff  cmp     [rbp+37h+var_90], 9
0x18007d303  jnz     short loc_18007D37B
0x18007d305  mov     rdx, [rbp+37h+Source2]; Source2
0x18007d309  mov     r8d, 9; Length
0x18007d30f  mov     rcx, r14; Source1
0x18007d312  call    cs:__imp_RtlCompareMemory
0x18007d319  nop     dword ptr [rax+rax+00h]
0x18007d31e  cmp     rax, 9
0x18007d322  jnz     short loc_18007D37B
0x18007d324  mov     edx, [rbp+37h+var_80]
0x18007d327  mov     r9, r15
0x18007d32a  mov     rcx, [rbp+37h+var_78]
0x18007d32e  mov     r8, r12
0x18007d331  call    MinAsn1ExtractContent
0x18007d336  test    eax, eax
0x18007d338  js      short loc_18007D37B
0x18007d33a  test    rdi, rdi
0x18007d33d  jz      short loc_18007D350
0x18007d33f  mov     eax, [rdi+4]
0x18007d342  test    al, 20h
0x18007d344  jz      short loc_18007D350
0x18007d346  test    [rsp+110h+var_C0+8], 4000h
0x18007d34e  jz      short loc_18007D37B
0x18007d350  cmp     [rsp+110h+var_C0], 0
0x18007d355  jz      short loc_18007D37B
0x18007d357  mov     rcx, qword ptr [rbp+37h+var_B0]
0x18007d35b  test    rcx, rcx
0x18007d35e  jz      short loc_18007D37B
0x18007d360  test    [rsp+110h+var_C0+8], 0FFFF0000h
0x18007d368  jnz     short loc_18007D37B
0x18007d36a  test    rsi, rsi
0x18007d36d  jz      short loc_18007D380
0x18007d36f  mov     rdx, rsi
0x18007d372  call    SIPolicyConvertChainInfo
0x18007d377  mov     ebx, eax
0x18007d379  jmp     short loc_18007D380
0x18007d37b  mov     ebx, 0C0000428h
0x18007d380  cmp     [rsp+110h+var_C0], 0
0x18007d385  jz      short loc_18007D390
0x18007d387  mov     rcx, qword ptr [rbp+37h+var_B0]
0x18007d38b  call    I_MincryptFreeChainInfo
0x18007d390  mov     eax, ebx
0x18007d392  mov     rcx, [rbp+37h+var_40]
0x18007d396  xor     rcx, rsp; StackCookie
0x18007d399  call    __security_check_cookie
0x18007d39e  add     rsp, 0E0h
0x18007d3a5  pop     r15
0x18007d3a7  pop     r14
0x18007d3a9  pop     r12
0x18007d3ab  pop     rdi
0x18007d3ac  pop     rsi
0x18007d3ad  pop     rbx
0x18007d3ae  pop     rbp
0x18007d3af  retn
```
