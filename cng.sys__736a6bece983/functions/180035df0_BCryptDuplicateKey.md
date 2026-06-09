# BCryptDuplicateKey

- ea: `0x180035df0`
- end: `0x180036033`
- name: `BCryptDuplicateKey`
- size: `579`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, BCRYPT_KEY_HANDLE *phNewKey, PUCHAR pbKeyObject, ULONG cbKeyObject, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003b10`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x180035df0`
- `0x1800363a0`
- `0x18005c3c0`
- `0x18009f6d0`

## string_xrefs

- `0x180035f12`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180035f76`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180035fc2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180035fe9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDuplicateKey(
        BCRYPT_KEY_HANDLE hKey,
        BCRYPT_KEY_HANDLE *phNewKey,
        PUCHAR pbKeyObject,
        ULONG cbKeyObject,
        ULONG dwFlags)
{
  void *v5; // rdi
  ULONG v6; // ebp
  PUCHAR v7; // rbx
  __int64 v10; // rax
  int v11; // edx
  __int64 v12; // r13
  __int64 v13; // rsi
  _DWORD *v14; // r14
  int v15; // eax
  NTSTATUS v16; // ebx
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rcx
  ULONG v21; // [rsp+40h] [rbp-58h] BYREF
  void *v22; // [rsp+48h] [rbp-50h] BYREF

  v5 = 0;
  v6 = cbKeyObject;
  v22 = 0;
  v7 = pbKeyObject;
  v21 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qqqdD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      30,
      pbKeyObject,
      hKey,
      phNewKey,
      pbKeyObject,
      cbKeyObject,
      dwFlags);
  v10 = ValidateBaseKeyHandle(hKey);
  v12 = v10;
  if ( v10 )
  {
    if ( !phNewKey )
    {
      v16 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 5460);
      return v16;
    }
    v13 = *(_QWORD *)(v10 + 8);
    if ( !v7 )
    {
      if ( !v6 )
      {
        v18 = AllocateObjectBuffer(*(_QWORD *)(v10 + 8), &v22, &v21);
        v16 = v18;
        if ( v18 < 0 )
        {
          DebugTraceError((unsigned int)v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 5475);
          v5 = v22;
          goto LABEL_9;
        }
        v5 = v22;
        v6 = v21;
        v7 = (PUCHAR)v22;
      }
      if ( !v7 )
      {
        v16 = -1073741811;
        v19 = 5492;
        v20 = 3221225485LL;
        goto LABEL_25;
      }
    }
    if ( v6 < 0x3E )
    {
      v16 = -1073741789;
      goto LABEL_9;
    }
    v14 = (_DWORD *)((unsigned __int64)(v7 + 15) & 0xFFFFFFFFFFFFFFF0uLL);
    *v14 = 32;
    v14[1] = 1431655762;
    *((_QWORD *)v14 + 1) = v13;
    *((_QWORD *)v14 + 3) = v5;
    if ( *(_DWORD *)(v13 + 36) != 1 && *(_DWORD *)(v13 + 36) != 7 )
    {
      v16 = -1073741637;
      v19 = 5528;
      v20 = 3221225659LL;
      goto LABEL_25;
    }
    v15 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, unsigned __int64, _QWORD, ULONG))(v13 + 128))(
            *(_QWORD *)(v12 + 16),
            v14 + 4,
            ((unsigned __int64)v14 + 47) & 0xFFFFFFFFFFFFFFF0uLL,
            (_DWORD)v7 - (((_DWORD)v14 + 47) & 0xFFFFFFF0) + v6,
            dwFlags);
    v16 = v15;
    if ( v15 < 0 )
    {
      v19 = 5539;
      v20 = (unsigned int)v15;
LABEL_25:
      DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v19);
      goto LABEL_9;
    }
    v5 = 0;
    *phNewKey = v14;
LABEL_9:
    if ( v5 )
      MSCryptFree(v5);
    if ( v13 && v16 >= 0 )
      _InterlockedIncrement((volatile signed __int32 *)(v13 + 16));
    return v16;
  }
  v16 = -1073741816;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v11,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      (unsigned int)"Status",
      8,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      77);
  return v16;
}

```

## disassembly

```asm
0x180035df0  push    rbx
0x180035df2  push    rbp
0x180035df3  push    rsi
0x180035df4  push    rdi
0x180035df5  push    r12
0x180035df7  push    r13
0x180035df9  push    r14
0x180035dfb  push    r15
0x180035dfd  sub     rsp, 58h
0x180035e01  xor     edi, edi
0x180035e03  mov     ebp, r9d
0x180035e06  mov     [rsp+98h+var_50], rdi
0x180035e0b  mov     rbx, r8
0x180035e0e  mov     [rsp+98h+var_58], edi
0x180035e12  mov     r15, rdx
0x180035e15  mov     rsi, rcx
0x180035e18  mov     rcx, cs:WPP_GLOBAL_Control
0x180035e1f  lea     r14, WPP_GLOBAL_Control
0x180035e26  mov     r12d, [rsp+98h+dwFlags]
0x180035e2e  cmp     rcx, r14
0x180035e31  jnz     loc_180035F3C
0x180035e37  mov     rcx, rsi
0x180035e3a  call    ValidateBaseKeyHandle
0x180035e3f  mov     r13, rax
0x180035e42  test    rax, rax
0x180035e45  jz      loc_180035EF6
0x180035e4b  test    r15, r15
0x180035e4e  jz      loc_180035F70
0x180035e54  mov     rsi, [rax+8]
0x180035e58  test    rbx, rbx
0x180035e5b  jz      loc_180035F98
0x180035e61  cmp     ebp, 3Eh ; '>'
0x180035e64  jb      loc_180036001
0x180035e6a  lea     r14, [rbx+0Fh]
0x180035e6e  and     r14, 0FFFFFFFFFFFFFFF0h
0x180035e72  mov     dword ptr [r14], 20h ; ' '
0x180035e79  mov     dword ptr [r14+4], 55555552h
0x180035e81  mov     [r14+8], rsi
0x180035e85  mov     [r14+18h], rdi
0x180035e89  mov     ecx, [rsi+24h]
0x180035e8c  sub     ecx, 1
0x180035e8f  jnz     loc_18003600B
0x180035e95  mov     rax, [rsi+80h]
0x180035e9c  lea     r8, [r14+2Fh]
0x180035ea0  mov     rcx, [r13+10h]
0x180035ea4  lea     rdx, [r14+10h]
0x180035ea8  and     r8, 0FFFFFFFFFFFFFFF0h
0x180035eac  mov     dword ptr [rsp+98h+var_78], r12d
0x180035eb1  sub     ebx, r8d
0x180035eb4  lea     r9d, [rbx+rbp]
0x180035eb8  call    _guard_dispatch_icall
0x180035ebd  mov     ebx, eax
0x180035ebf  test    eax, eax
0x180035ec1  js      loc_180035FE1
0x180035ec7  xor     edi, edi
0x180035ec9  mov     [r15], r14
0x180035ecc  test    rdi, rdi
0x180035ecf  jnz     loc_180036026
0x180035ed5  test    rsi, rsi
0x180035ed8  jz      short loc_180035EE2
0x180035eda  test    ebx, ebx
0x180035edc  js      short loc_180035EE2
0x180035ede  lock inc dword ptr [rsi+10h]
0x180035ee2  mov     eax, ebx
0x180035ee4  add     rsp, 58h
0x180035ee8  pop     r15
0x180035eea  pop     r14
0x180035eec  pop     r13
0x180035eee  pop     r12
0x180035ef0  pop     rdi
0x180035ef1  pop     rsi
0x180035ef2  pop     rbp
0x180035ef3  pop     rbx
0x180035ef4  retn
0x180035ef6  mov     ebx, 0C0000008h
0x180035efb  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f02  cmp     rcx, r14
0x180035f05  jz      short loc_180035EE2
0x180035f07  mov     eax, [rcx+2Ch]
0x180035f0a  test    al, 1
0x180035f0c  jz      short loc_180035EE2
0x180035f0e  mov     rcx, [rcx+18h]
0x180035f12  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180035f19  mov     [rsp+98h+var_68], 154Dh
0x180035f21  lea     r9, aStatus; "Status"
0x180035f28  mov     [rsp+98h+var_70], r8
0x180035f2d  mov     dword ptr [rsp+98h+var_78], 0C0000008h
0x180035f35  call    WPP_SF_sDsd
0x180035f3a  jmp     short loc_180035EE2
0x180035f3c  mov     eax, [rcx+2Ch]
0x180035f3f  test    al, 4
0x180035f41  jz      loc_180035E37
0x180035f47  mov     rcx, [rcx+18h]
0x180035f4b  mov     edx, 1Eh
0x180035f50  mov     [rsp+98h+var_60], r12d
0x180035f55  mov     r9, rsi
0x180035f58  mov     [rsp+98h+var_68], ebp
0x180035f5c  mov     [rsp+98h+var_70], rbx
0x180035f61  mov     [rsp+98h+var_78], r15
0x180035f66  call    WPP_SF_qqqdD
0x180035f6b  jmp     loc_180035E37
0x180035f70  mov     r9d, 1554h
0x180035f76  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180035f7d  lea     rdx, aStatus; "Status"
0x180035f84  mov     ecx, 0C000000Dh
0x180035f89  mov     ebx, 0C000000Dh
0x180035f8e  call    DebugTraceError
0x180035f93  jmp     loc_180035EE2
0x180035f98  test    ebp, ebp
0x180035f9a  jnz     loc_1800A2C2C
0x180035fa0  lea     r8, [rsp+98h+var_58]
0x180035fa5  mov     rcx, rsi
0x180035fa8  lea     rdx, [rsp+98h+var_50]
0x180035fad  call    AllocateObjectBuffer
0x180035fb2  mov     ebx, eax
0x180035fb4  test    eax, eax
0x180035fb6  jns     loc_1800A2C20
0x180035fbc  mov     r9d, 1563h
0x180035fc2  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180035fc9  lea     rdx, aStatus; "Status"
0x180035fd0  mov     ecx, eax
0x180035fd2  call    DebugTraceError
0x180035fd7  mov     rdi, [rsp+98h+var_50]
0x180035fdc  jmp     loc_180035ECC
0x180035fe1  mov     r9d, 15A3h
0x180035fe7  mov     ecx, eax
0x180035fe9  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180035ff0  lea     rdx, aStatus; "Status"
0x180035ff7  call    DebugTraceError
0x180035ffc  jmp     loc_180035ECC
0x180036001  mov     ebx, 0C0000023h
0x180036006  jmp     loc_180035ECC
0x18003600b  cmp     ecx, 6
0x18003600e  jz      loc_180035E95
0x180036014  mov     ebx, 0C00000BBh
0x180036019  mov     r9d, 1598h
0x18003601f  mov     ecx, 0C00000BBh
0x180036024  jmp     short loc_180035FE9
0x180036026  mov     rcx, rdi; P
0x180036029  call    MSCryptFree
0x18003602e  jmp     loc_180035ED5
0x1800a2c20  mov     rdi, [rsp+98h+var_50]
0x1800a2c25  mov     ebp, [rsp+98h+var_58]
0x1800a2c29  mov     rbx, rdi
0x1800a2c2c  test    rbx, rbx
0x1800a2c2f  jnz     loc_180035E61
0x1800a2c35  mov     ebx, 0C000000Dh
0x1800a2c3a  mov     r9d, 1574h
0x1800a2c40  mov     ecx, 0C000000Dh
0x1800a2c45  jmp     loc_180035FE9
```
