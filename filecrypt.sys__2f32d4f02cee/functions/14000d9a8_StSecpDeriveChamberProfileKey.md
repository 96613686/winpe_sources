# StSecpDeriveChamberProfileKey

- ea: `0x14000d9a8`
- end: `0x14000dcd0`
- name: `StSecpDeriveChamberProfileKey`
- size: `808`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000d1a8`

## callees

- `0x140001190`
- `0x140003b80`
- `0x14000d9a8`
- `0x14000dcd8`
- `0x14000e340`
- `0x14000eb20`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000da2b`
- `ntoskrnl!ExAllocatePool2` at `0x14000dad7`
- `ntoskrnl!ExAllocatePool2` at `0x14000db54`
- `ntoskrnl!ExAllocatePool2` at `0x14000dbcc`
- `ntoskrnl!ExAllocatePool2` at `0x14000da2b`
- `ntoskrnl!ExAllocatePool2` at `0x14000dad7`
- `ntoskrnl!ExAllocatePool2` at `0x14000db54`
- `ntoskrnl!ExAllocatePool2` at `0x14000dbcc`
- `ksecdd!BCryptFinishHash` at `0x14000db7d`
- `ksecdd!BCryptFinishHash` at `0x14000dbf5`
- `ksecdd!BCryptFinishHash` at `0x14000db7d`
- `ksecdd!BCryptFinishHash` at `0x14000dbf5`
- `ksecdd!BCryptHashData` at `0x14000dab0`
- `ksecdd!BCryptHashData` at `0x14000db2d`
- `ksecdd!BCryptHashData` at `0x14000dba5`
- `ksecdd!BCryptHashData` at `0x14000dab0`
- `ksecdd!BCryptHashData` at `0x14000db2d`
- `ksecdd!BCryptHashData` at `0x14000dba5`
- `ksecdd!BCryptDuplicateHash` at `0x14000db05`
- `ksecdd!BCryptDuplicateHash` at `0x14000db05`
- `ksecdd!BCryptCreateHash` at `0x14000da72`
- `ksecdd!BCryptCreateHash` at `0x14000da72`
- `ksecdd!BCryptDestroyHash` at `0x14000dc48`
- `ksecdd!BCryptDestroyHash` at `0x14000dc5d`
- `ksecdd!BCryptDestroyHash` at `0x14000dc48`
- `ksecdd!BCryptDestroyHash` at `0x14000dc5d`

## string_xrefs

- `0x14000db1f`: `Install`

## pseudocode

```c
__int64 __fastcall StSecpDeriveChamberProfileKey(const wchar_t *a1, int a2, void *a3, unsigned int a4)
{
  size_t v4; // r14
  int MasterKey; // ebx
  UCHAR *v7; // r12
  UCHAR *v8; // r15
  UCHAR *v9; // rsi
  UCHAR *v10; // rdi
  UCHAR *Pool2; // rax
  size_t v12; // rdx
  UCHAR *v13; // r10
  UCHAR *v14; // rax
  UCHAR *v15; // rax
  UCHAR *v16; // rax
  UCHAR *v17; // rdx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phNewHash; // [rsp+48h] [rbp-18h] BYREF
  PUCHAR pbSecret; // [rsp+50h] [rbp-10h] BYREF
  size_t pcbLength; // [rsp+58h] [rbp-8h] BYREF
  ULONG cbSecret; // [rsp+B8h] [rbp+58h] BYREF

  v4 = a4;
  pbSecret = 0;
  cbSecret = 0;
  phHash = 0;
  phNewHash = 0;
  pcbLength = 0;
  if ( a4 > *(_DWORD *)&g_cbHashOutputLength )
    return (unsigned int)-1073741811;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  MasterKey = StSecpGetMasterKey((__int64)&pbSecret, &cbSecret);
  if ( MasterKey >= 0 )
  {
    Pool2 = (UCHAR *)ExAllocatePool2(64, *(unsigned int *)&g_cbHashObjectLength, 1850963027);
    v7 = Pool2;
    if ( !Pool2 )
      goto LABEL_5;
    MasterKey = BCryptCreateHash(
                  g_HmacHashProvider,
                  &phHash,
                  Pool2,
                  *(ULONG *)&g_cbHashObjectLength,
                  pbSecret,
                  cbSecret,
                  0);
    if ( MasterKey < 0 )
      goto LABEL_23;
    MasterKey = RtlStringCbLengthW(a1, v12, &pcbLength);
    if ( MasterKey < 0 )
      goto LABEL_23;
    MasterKey = BCryptHashData(phHash, v13, pcbLength, 0);
    if ( MasterKey < 0 )
      goto LABEL_23;
    v14 = (UCHAR *)ExAllocatePool2(64, *(unsigned int *)&g_cbHashObjectLength, 1850963027);
    v8 = v14;
    if ( !v14 )
      goto LABEL_5;
    MasterKey = BCryptDuplicateHash(phHash, &phNewHash, v14, *(ULONG *)&g_cbHashObjectLength, 0);
    if ( MasterKey < 0 )
      goto LABEL_23;
    MasterKey = BCryptHashData(phHash, (PUCHAR)L"Install", 0xEu, 0);
    if ( MasterKey < 0 )
      goto LABEL_23;
    v15 = (UCHAR *)ExAllocatePool2(64, *(unsigned int *)&g_cbHashOutputLength, 1850963027);
    v9 = v15;
    if ( !v15 )
      goto LABEL_5;
    MasterKey = BCryptFinishHash(phHash, v15, *(ULONG *)&g_cbHashOutputLength, 0);
    if ( MasterKey < 0 )
      goto LABEL_23;
    MasterKey = BCryptHashData(phNewHash, (PUCHAR)L"Data", 8u, 0);
    if ( MasterKey < 0 )
      goto LABEL_23;
    v16 = (UCHAR *)ExAllocatePool2(64, *(unsigned int *)&g_cbHashOutputLength, 1850963027);
    v10 = v16;
    if ( v16 )
    {
      MasterKey = BCryptFinishHash(phNewHash, v16, *(ULONG *)&g_cbHashOutputLength, 0);
      if ( MasterKey < 0 )
        goto LABEL_23;
      MasterKey = StSecpAddChamberProfileKey(a1);
      if ( MasterKey < 0 )
        goto LABEL_23;
      if ( a2 == 1 )
      {
        v17 = v9;
LABEL_22:
        memmove(a3, v17, v4);
        goto LABEL_23;
      }
      if ( a2 == 2 )
      {
        v17 = v10;
        goto LABEL_22;
      }
    }
    else
    {
LABEL_5:
      MasterKey = -1073741801;
    }
  }
LABEL_23:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phNewHash )
    BCryptDestroyHash(phNewHash);
  if ( v7 )
    StSecpFreeNonPaged(v7, *(unsigned int *)&g_cbHashObjectLength);
  if ( v8 )
    StSecpFreeNonPaged(v8, *(unsigned int *)&g_cbHashObjectLength);
  if ( v9 )
    StSecpFreeNonPaged(v9, *(unsigned int *)&g_cbHashOutputLength);
  if ( v10 )
    StSecpFreeNonPaged(v10, *(unsigned int *)&g_cbHashOutputLength);
  return (unsigned int)MasterKey;
}

```

## disassembly

```asm
0x14000d9a8  mov     [rsp-38h+arg_8], rbx
0x14000d9ad  mov     [rsp-38h+arg_10], r8
0x14000d9b2  mov     [rsp-38h+psz], rcx
0x14000d9b7  push    rbp
0x14000d9b8  push    rsi
0x14000d9b9  push    rdi
0x14000d9ba  push    r12
0x14000d9bc  push    r13
0x14000d9be  push    r14
0x14000d9c0  push    r15
0x14000d9c2  mov     rbp, rsp
0x14000d9c5  sub     rsp, 60h
0x14000d9c9  xor     eax, eax
0x14000d9cb  mov     r14d, r9d
0x14000d9ce  cmp     r9d, cs:g_cbHashOutputLength
0x14000d9d5  mov     r13d, edx
0x14000d9d8  mov     [rbp+var_10], rax
0x14000d9dc  mov     [rbp+arg_18], eax
0x14000d9df  mov     [rbp+phHash], rax
0x14000d9e3  mov     [rbp+phNewHash], rax
0x14000d9e7  mov     [rbp+pcbLength], rax
0x14000d9eb  jbe     short loc_14000D9F7
0x14000d9ed  mov     ebx, 0C000000Dh
0x14000d9f2  jmp     loc_14000DCB5
0x14000d9f7  lea     rdx, [rbp+arg_18]
0x14000d9fb  mov     r12, rax
0x14000d9fe  lea     rcx, [rbp+var_10]
0x14000da02  mov     r15, rax
0x14000da05  mov     rsi, rax
0x14000da08  mov     rdi, rax
0x14000da0b  call    StSecpGetMasterKey
0x14000da10  mov     ebx, eax
0x14000da12  test    eax, eax
0x14000da14  js      loc_14000DC3F
0x14000da1a  mov     edx, cs:g_cbHashObjectLength
0x14000da20  mov     ecx, 40h ; '@'
0x14000da25  mov     r8d, 6E537453h
0x14000da2b  call    cs:__imp_ExAllocatePool2
0x14000da32  nop     dword ptr [rax+rax+00h]
0x14000da37  mov     r12, rax
0x14000da3a  test    rax, rax
0x14000da3d  jnz     short loc_14000DA49
0x14000da3f  mov     ebx, 0C0000017h
0x14000da44  jmp     loc_14000DC3F
0x14000da49  mov     eax, [rbp+arg_18]
0x14000da4c  lea     rdx, [rbp+phHash]; phHash
0x14000da50  mov     r9d, cs:g_cbHashObjectLength; cbHashObject
0x14000da57  mov     r8, r12; pbHashObject
0x14000da5a  mov     rcx, cs:g_HmacHashProvider; hAlgorithm
0x14000da61  mov     [rsp+60h+dwFlags], esi; dwFlags
0x14000da65  mov     [rsp+60h+cbSecret], eax; cbSecret
0x14000da69  mov     rax, [rbp+var_10]
0x14000da6d  mov     [rsp+60h+pbSecret], rax; pbSecret
0x14000da72  call    cs:__imp_BCryptCreateHash
0x14000da79  nop     dword ptr [rax+rax+00h]
0x14000da7e  mov     ebx, eax
0x14000da80  test    eax, eax
0x14000da82  js      loc_14000DC3F
0x14000da88  mov     r10, [rbp+psz]
0x14000da8c  lea     r8, [rbp+pcbLength]; pcbLength
0x14000da90  mov     rcx, r10; psz
0x14000da93  call    RtlStringCbLengthW
0x14000da98  mov     ebx, eax
0x14000da9a  test    eax, eax
0x14000da9c  js      loc_14000DC3F
0x14000daa2  mov     r8d, dword ptr [rbp+pcbLength]; cbInput
0x14000daa6  xor     r9d, r9d; dwFlags
0x14000daa9  mov     rcx, [rbp+phHash]; hHash
0x14000daad  mov     rdx, r10; pbInput
0x14000dab0  call    cs:__imp_BCryptHashData
0x14000dab7  nop     dword ptr [rax+rax+00h]
0x14000dabc  mov     ebx, eax
0x14000dabe  test    eax, eax
0x14000dac0  js      loc_14000DC3F
0x14000dac6  mov     edx, cs:g_cbHashObjectLength
0x14000dacc  mov     ecx, 40h ; '@'
0x14000dad1  mov     r8d, 6E537453h
0x14000dad7  call    cs:__imp_ExAllocatePool2
0x14000dade  nop     dword ptr [rax+rax+00h]
0x14000dae3  mov     r15, rax
0x14000dae6  test    rax, rax
0x14000dae9  jz      loc_14000DA3F
0x14000daef  mov     r9d, cs:g_cbHashObjectLength; cbHashObject
0x14000daf6  lea     rdx, [rbp+phNewHash]; phNewHash
0x14000dafa  mov     rcx, [rbp+phHash]; hHash
0x14000dafe  mov     r8, rax; pbHashObject
0x14000db01  mov     dword ptr [rsp+60h+pbSecret], esi; dwFlags
0x14000db05  call    cs:__imp_BCryptDuplicateHash
0x14000db0c  nop     dword ptr [rax+rax+00h]
0x14000db11  mov     ebx, eax
0x14000db13  test    eax, eax
0x14000db15  js      loc_14000DC3F
0x14000db1b  mov     rcx, [rbp+phHash]; hHash
0x14000db1f  lea     rdx, aInstall; "Install"
0x14000db26  xor     r9d, r9d; dwFlags
0x14000db29  lea     r8d, [r9+0Eh]; cbInput
0x14000db2d  call    cs:__imp_BCryptHashData
0x14000db34  nop     dword ptr [rax+rax+00h]
0x14000db39  mov     ebx, eax
0x14000db3b  test    eax, eax
0x14000db3d  js      loc_14000DC3F
0x14000db43  mov     edx, cs:g_cbHashOutputLength
0x14000db49  mov     ecx, 40h ; '@'
0x14000db4e  mov     r8d, 6E537453h
0x14000db54  call    cs:__imp_ExAllocatePool2
0x14000db5b  nop     dword ptr [rax+rax+00h]
0x14000db60  mov     rsi, rax
0x14000db63  test    rax, rax
0x14000db66  jz      loc_14000DA3F
0x14000db6c  mov     r8d, cs:g_cbHashOutputLength; cbOutput
0x14000db73  xor     r9d, r9d; dwFlags
0x14000db76  mov     rcx, [rbp+phHash]; hHash
0x14000db7a  mov     rdx, rax; pbOutput
0x14000db7d  call    cs:__imp_BCryptFinishHash
0x14000db84  nop     dword ptr [rax+rax+00h]
0x14000db89  mov     ebx, eax
0x14000db8b  test    eax, eax
0x14000db8d  js      loc_14000DC3F
0x14000db93  mov     rcx, [rbp+phNewHash]; hHash
0x14000db97  lea     rdx, aData; "Data"
0x14000db9e  xor     r9d, r9d; dwFlags
0x14000dba1  lea     r8d, [r9+8]; cbInput
0x14000dba5  call    cs:__imp_BCryptHashData
0x14000dbac  nop     dword ptr [rax+rax+00h]
0x14000dbb1  mov     ebx, eax
0x14000dbb3  test    eax, eax
0x14000dbb5  js      loc_14000DC3F
0x14000dbbb  mov     edx, cs:g_cbHashOutputLength
0x14000dbc1  mov     ecx, 40h ; '@'
0x14000dbc6  mov     r8d, 6E537453h
0x14000dbcc  call    cs:__imp_ExAllocatePool2
0x14000dbd3  nop     dword ptr [rax+rax+00h]
0x14000dbd8  mov     rdi, rax
0x14000dbdb  test    rax, rax
0x14000dbde  jz      loc_14000DA3F
0x14000dbe4  mov     r8d, cs:g_cbHashOutputLength; cbOutput
0x14000dbeb  xor     r9d, r9d; dwFlags
0x14000dbee  mov     rcx, [rbp+phNewHash]; hHash
0x14000dbf2  mov     rdx, rax; pbOutput
0x14000dbf5  call    cs:__imp_BCryptFinishHash
0x14000dbfc  nop     dword ptr [rax+rax+00h]
0x14000dc01  mov     ebx, eax
0x14000dc03  test    eax, eax
0x14000dc05  js      short loc_14000DC3F
0x14000dc07  mov     rcx, [rbp+psz]; pszSrc
0x14000dc0b  mov     r9d, r14d
0x14000dc0e  mov     r8, rdi
0x14000dc11  mov     rdx, rsi
0x14000dc14  call    StSecpAddChamberProfileKey
0x14000dc19  mov     ebx, eax
0x14000dc1b  test    eax, eax
0x14000dc1d  js      short loc_14000DC3F
0x14000dc1f  cmp     r13d, 1
0x14000dc23  jnz     short loc_14000DC2A
0x14000dc25  mov     rdx, rsi
0x14000dc28  jmp     short loc_14000DC33
0x14000dc2a  cmp     r13d, 2
0x14000dc2e  jnz     short loc_14000DC3F
0x14000dc30  mov     rdx, rdi; Src
0x14000dc33  mov     rcx, [rbp+arg_10]; void *
0x14000dc37  mov     r8, r14; Size
0x14000dc3a  call    memmove
0x14000dc3f  mov     rcx, [rbp+phHash]; hHash
0x14000dc43  test    rcx, rcx
0x14000dc46  jz      short loc_14000DC54
0x14000dc48  call    cs:__imp_BCryptDestroyHash
0x14000dc4f  nop     dword ptr [rax+rax+00h]
0x14000dc54  mov     rcx, [rbp+phNewHash]; hHash
0x14000dc58  test    rcx, rcx
0x14000dc5b  jz      short loc_14000DC69
0x14000dc5d  call    cs:__imp_BCryptDestroyHash
0x14000dc64  nop     dword ptr [rax+rax+00h]
0x14000dc69  test    r12, r12
0x14000dc6c  jz      short loc_14000DC7C
0x14000dc6e  mov     edx, cs:g_cbHashObjectLength
0x14000dc74  mov     rcx, r12
0x14000dc77  call    StSecpFreeNonPaged
0x14000dc7c  test    r15, r15
0x14000dc7f  jz      short loc_14000DC8F
0x14000dc81  mov     edx, cs:g_cbHashObjectLength
0x14000dc87  mov     rcx, r15
0x14000dc8a  call    StSecpFreeNonPaged
0x14000dc8f  test    rsi, rsi
0x14000dc92  jz      short loc_14000DCA2
0x14000dc94  mov     edx, cs:g_cbHashOutputLength
0x14000dc9a  mov     rcx, rsi
0x14000dc9d  call    StSecpFreeNonPaged
0x14000dca2  test    rdi, rdi
0x14000dca5  jz      short loc_14000DCB5
0x14000dca7  mov     edx, cs:g_cbHashOutputLength
0x14000dcad  mov     rcx, rdi
0x14000dcb0  call    StSecpFreeNonPaged
0x14000dcb5  mov     eax, ebx
0x14000dcb7  mov     rbx, [rsp+60h+arg_8]
0x14000dcbf  add     rsp, 60h
0x14000dcc3  pop     r15
0x14000dcc5  pop     r14
0x14000dcc7  pop     r13
0x14000dcc9  pop     r12
0x14000dccb  pop     rdi
0x14000dccc  pop     rsi
0x14000dccd  pop     rbp
0x14000dcce  retn
```
