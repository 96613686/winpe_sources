# SIPolicyVerifySignedData

- ea: `0x18007f2a8`
- end: `0x18007f3e1`
- name: `SIPolicyVerifySignedData`
- size: `313`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800785d8`
- `0x18007db90`
- `0x18007f188`

## callees

- `0x18002c0d0`
- `0x18007f2a8`
- `0x18008eddc`
- `0x180094670`
- `0x180094db8`
- `0x18009b158`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x18007f342`
- `ntoskrnl!RtlCompareMemory` at `0x18007f342`

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
0x18007f2a8  push    rbp
0x18007f2aa  push    rbx
0x18007f2ab  push    rsi
0x18007f2ac  push    rdi
0x18007f2ad  push    r12
0x18007f2af  push    r14
0x18007f2b1  push    r15
0x18007f2b3  lea     rbp, [rsp-7]
0x18007f2b8  sub     rsp, 0E0h
0x18007f2bf  mov     rax, cs:__security_cookie
0x18007f2c6  xor     rax, rsp
0x18007f2c9  mov     [rbp+37h+var_40], rax
0x18007f2cd  mov     rdi, [rbp+37h+arg_20]
0x18007f2d1  lea     rax, [rbp+37h+var_90]
0x18007f2d5  mov     r15, [rbp+37h+arg_28]
0x18007f2d9  xorps   xmm0, xmm0
0x18007f2dc  mov     r12, [rbp+37h+arg_30]
0x18007f2e0  mov     r14, r8
0x18007f2e3  mov     rsi, [rbp+37h+arg_38]
0x18007f2e7  xor     r9d, r9d; int
0x18007f2ea  mov     [rsp+110h+var_D0], 0; __int64
0x18007f2f3  xor     r8d, r8d; int
0x18007f2f6  mov     [rsp+110h+var_D8], 0; __int64
0x18007f2ff  mov     [rsp+110h+var_E0], rax; void *
0x18007f304  lea     rax, [rsp+110h+var_C0]
0x18007f309  mov     qword ptr [rsp+110h+var_E8], rax; int
0x18007f30e  mov     [rsp+110h+var_F0], rdi; __int64
0x18007f313  movups  xmmword ptr [rsp+110h+var_C0], xmm0
0x18007f318  movups  [rbp+37h+var_B0], xmm0
0x18007f31c  movups  [rbp+37h+var_A0], xmm0
0x18007f320  call    MinCrypK_VerifySignedDataKModeEx
0x18007f325  mov     ebx, eax
0x18007f327  test    eax, eax
0x18007f329  js      loc_18007F3B0
0x18007f32f  cmp     [rbp+37h+var_90], 9
0x18007f333  jnz     short loc_18007F3AB
0x18007f335  mov     rdx, [rbp+37h+Source2]; Source2
0x18007f339  mov     r8d, 9; Length
0x18007f33f  mov     rcx, r14; Source1
0x18007f342  call    cs:__imp_RtlCompareMemory
0x18007f349  nop     dword ptr [rax+rax+00h]
0x18007f34e  cmp     rax, 9
0x18007f352  jnz     short loc_18007F3AB
0x18007f354  mov     edx, [rbp+37h+var_80]
0x18007f357  mov     r9, r15
0x18007f35a  mov     rcx, [rbp+37h+var_78]
0x18007f35e  mov     r8, r12
0x18007f361  call    MinAsn1ExtractContent
0x18007f366  test    eax, eax
0x18007f368  js      short loc_18007F3AB
0x18007f36a  test    rdi, rdi
0x18007f36d  jz      short loc_18007F380
0x18007f36f  mov     eax, [rdi+4]
0x18007f372  test    al, 20h
0x18007f374  jz      short loc_18007F380
0x18007f376  test    [rsp+110h+var_C0+8], 4000h
0x18007f37e  jz      short loc_18007F3AB
0x18007f380  cmp     [rsp+110h+var_C0], 0
0x18007f385  jz      short loc_18007F3AB
0x18007f387  mov     rcx, qword ptr [rbp+37h+var_B0]
0x18007f38b  test    rcx, rcx
0x18007f38e  jz      short loc_18007F3AB
0x18007f390  test    [rsp+110h+var_C0+8], 0FFFF0000h
0x18007f398  jnz     short loc_18007F3AB
0x18007f39a  test    rsi, rsi
0x18007f39d  jz      short loc_18007F3B0
0x18007f39f  mov     rdx, rsi
0x18007f3a2  call    SIPolicyConvertChainInfo
0x18007f3a7  mov     ebx, eax
0x18007f3a9  jmp     short loc_18007F3B0
0x18007f3ab  mov     ebx, 0C0000428h
0x18007f3b0  cmp     [rsp+110h+var_C0], 0
0x18007f3b5  jz      short loc_18007F3C0
0x18007f3b7  mov     rcx, qword ptr [rbp+37h+var_B0]
0x18007f3bb  call    I_MincryptFreeChainInfo
0x18007f3c0  mov     eax, ebx
0x18007f3c2  mov     rcx, [rbp+37h+var_40]
0x18007f3c6  xor     rcx, rsp; StackCookie
0x18007f3c9  call    __security_check_cookie
0x18007f3ce  add     rsp, 0E0h
0x18007f3d5  pop     r15
0x18007f3d7  pop     r14
0x18007f3d9  pop     r12
0x18007f3db  pop     rdi
0x18007f3dc  pop     rsi
0x18007f3dd  pop     rbx
0x18007f3de  pop     rbp
0x18007f3df  retn
```
