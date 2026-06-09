# TestKdf

- ea: `0x18007e2f0`
- end: `0x18007e47b`
- name: `TestKdf`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18007e484`
- `0x18007e4ac`

## callees

- `0x18000c0a0`
- `0x18001155c`
- `0x180011ee0`
- `0x180041010`
- `0x180043480`
- `0x180043e70`
- `0x18007e2f0`
- `0x1800a4260`

## string_xrefs

- `0x18007e34c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\msprim\algself.c`
- `0x18007e41f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\msprim\algself.c`

## pseudocode

```c
__int64 __fastcall TestKdf(const wchar_t *a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11; // r8d
  __int64 v12; // rax
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  int v15[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v16[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v17[3]; // [rsp+58h] [rbp-A8h] BYREF
  int v18[160]; // [rsp+70h] [rbp-90h] BYREF

  *(_QWORD *)v16 = 0;
  *(_QWORD *)v15 = 0;
  v14 = 0;
  v5 = MSCryptKDOpenProvider(v16, a1, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    DebugTraceError(
      (unsigned int)v5,
      "status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\msprim\\algself.c",
      122);
    goto LABEL_15;
  }
  v7 = MSCryptKDGenerateSymmetricKey(*(_DWORD **)v16, v15, (__int64)v18, 0x280u, g_kdfTestKey, 0x10u, 0);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = 133;
LABEL_5:
    v9 = (unsigned int)v7;
    goto LABEL_12;
  }
  v14 = 16;
  v7 = MSCryptKDKeyDerivation(*(__int64 *)v15, (__int64)&g_kdfParameters, v17, 0x10u, &v14, 0);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = 146;
    goto LABEL_5;
  }
  v12 = *a5 - v17[0];
  if ( *a5 == v17[0] )
    v12 = a5[1] - v17[1];
  if ( !v12 )
    goto LABEL_13;
  v6 = -1073741595;
  v8 = 153;
  v9 = 3221225701LL;
LABEL_12:
  DebugTraceError(v9, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\msprim\\algself.c", v8);
LABEL_13:
  if ( *(_QWORD *)v15 )
    MSCryptKDDestroyKey(*(__int64 *)v15, v10, v11);
LABEL_15:
  if ( *(_QWORD *)v16 )
    MSCryptKDCloseProvider(*(_QWORD *)v16, 0);
  return v6;
}

```

## disassembly

```asm
0x18007e2f0  mov     [rsp-8+arg_0], rbx
0x18007e2f5  push    rbp
0x18007e2f6  lea     rbp, [rsp-200h]
0x18007e2fe  sub     rsp, 300h
0x18007e305  mov     rax, cs:__security_cookie
0x18007e30c  xor     rax, rsp
0x18007e30f  mov     [rbp+200h+var_10], rax
0x18007e316  mov     rdx, rcx
0x18007e319  mov     qword ptr [rsp+300h+var_2B0], 0
0x18007e322  lea     rcx, [rsp+300h+var_2B0]
0x18007e327  mov     qword ptr [rsp+300h+var_2B8], 0
0x18007e330  xor     r8d, r8d
0x18007e333  mov     [rsp+300h+var_2C0], 0
0x18007e33b  call    MSCryptKDOpenProvider
0x18007e340  mov     ebx, eax
0x18007e342  test    eax, eax
0x18007e344  jns     short loc_18007E366
0x18007e346  mov     r9d, 7Ah ; 'z'
0x18007e34c  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e353  lea     rdx, aStatus_0; "status"
0x18007e35a  mov     ecx, eax
0x18007e35c  call    DebugTraceError
0x18007e361  jmp     loc_18007E444
0x18007e366  mov     rcx, qword ptr [rsp+300h+var_2B0]; int
0x18007e36b  lea     rax, g_kdfTestKey
0x18007e372  mov     [rsp+300h+var_2D0], 0; int
0x18007e37a  lea     r8, [rsp+300h+var_290]; int
0x18007e37f  mov     [rsp+300h+var_2D8], 10h; int
0x18007e387  lea     rdx, [rsp+300h+var_2B8]; int
0x18007e38c  mov     r9d, 280h; int
0x18007e392  mov     [rsp+300h+Src], rax; Src
0x18007e397  call    MSCryptKDGenerateSymmetricKey
0x18007e39c  mov     ebx, eax
0x18007e39e  test    eax, eax
0x18007e3a0  jns     short loc_18007E3AC
0x18007e3a2  mov     r9d, 85h
0x18007e3a8  mov     ecx, eax
0x18007e3aa  jmp     short loc_18007E41F
0x18007e3ac  mov     rcx, qword ptr [rsp+300h+var_2B8]
0x18007e3b1  lea     rax, [rsp+300h+var_2C0]
0x18007e3b6  mov     [rsp+300h+var_2D8], 0
0x18007e3be  lea     r8, [rsp+300h+var_2A8]
0x18007e3c3  mov     r9d, 10h
0x18007e3c9  mov     [rsp+300h+Src], rax
0x18007e3ce  lea     rdx, g_kdfParameters
0x18007e3d5  mov     [rsp+300h+var_2C0], 10h
0x18007e3dd  call    MSCryptKDKeyDerivation
0x18007e3e2  mov     ebx, eax
0x18007e3e4  test    eax, eax
0x18007e3e6  jns     short loc_18007E3F0
0x18007e3e8  mov     r9d, 92h
0x18007e3ee  jmp     short loc_18007E3A8
0x18007e3f0  mov     rcx, [rbp+200h+arg_20]
0x18007e3f7  mov     rax, [rcx]
0x18007e3fa  sub     rax, [rsp+300h+var_2A8]
0x18007e3ff  jnz     short loc_18007E40A
0x18007e401  mov     rax, [rcx+8]
0x18007e405  sub     rax, [rsp+300h+var_2A0]
0x18007e40a  test    rax, rax
0x18007e40d  jz      short loc_18007E432
0x18007e40f  mov     ebx, 0C00000E5h
0x18007e414  mov     r9d, 99h
0x18007e41a  mov     ecx, 0C00000E5h
0x18007e41f  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e426  lea     rdx, aStatus_0; "status"
0x18007e42d  call    DebugTraceError
0x18007e432  cmp     qword ptr [rsp+300h+var_2B8], 0
0x18007e438  jz      short loc_18007E444
0x18007e43a  mov     rcx, qword ptr [rsp+300h+var_2B8]
0x18007e43f  call    MSCryptKDDestroyKey
0x18007e444  cmp     qword ptr [rsp+300h+var_2B0], 0
0x18007e44a  jz      short loc_18007E458
0x18007e44c  mov     rcx, qword ptr [rsp+300h+var_2B0]
0x18007e451  xor     edx, edx
0x18007e453  call    MSCryptKDCloseProvider
0x18007e458  mov     eax, ebx
0x18007e45a  mov     rcx, [rbp+200h+var_10]
0x18007e461  xor     rcx, rsp; StackCookie
0x18007e464  call    __security_check_cookie
0x18007e469  mov     rbx, [rsp+300h+arg_0]
0x18007e471  add     rsp, 300h
0x18007e478  pop     rbp
0x18007e479  retn
```
