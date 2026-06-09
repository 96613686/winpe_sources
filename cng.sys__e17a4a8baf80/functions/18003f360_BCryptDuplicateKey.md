# BCryptDuplicateKey

- ea: `0x18003f360`
- end: `0x18003f5a3`
- name: `BCryptDuplicateKey`
- size: `579`
- prototype: `NTSTATUS __stdcall(BCRYPT_KEY_HANDLE hKey, BCRYPT_KEY_HANDLE *phNewKey, PUCHAR pbKeyObject, ULONG cbKeyObject, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000dc30`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x18003f360`
- `0x18003f910`
- `0x180065ca0`
- `0x1800a4300`

## string_xrefs

- `0x18003f482`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18003f4e6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18003f532`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18003f559`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x18003f360  push    rbx
0x18003f362  push    rbp
0x18003f363  push    rsi
0x18003f364  push    rdi
0x18003f365  push    r12
0x18003f367  push    r13
0x18003f369  push    r14
0x18003f36b  push    r15
0x18003f36d  sub     rsp, 58h
0x18003f371  xor     edi, edi
0x18003f373  mov     ebp, r9d
0x18003f376  mov     [rsp+98h+var_50], rdi
0x18003f37b  mov     rbx, r8
0x18003f37e  mov     [rsp+98h+var_58], edi
0x18003f382  mov     r15, rdx
0x18003f385  mov     rsi, rcx
0x18003f388  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f38f  lea     r14, WPP_GLOBAL_Control
0x18003f396  mov     r12d, [rsp+98h+dwFlags]
0x18003f39e  cmp     rcx, r14
0x18003f3a1  jnz     loc_18003F4AC
0x18003f3a7  mov     rcx, rsi
0x18003f3aa  call    ValidateBaseKeyHandle
0x18003f3af  mov     r13, rax
0x18003f3b2  test    rax, rax
0x18003f3b5  jz      loc_18003F466
0x18003f3bb  test    r15, r15
0x18003f3be  jz      loc_18003F4E0
0x18003f3c4  mov     rsi, [rax+8]
0x18003f3c8  test    rbx, rbx
0x18003f3cb  jz      loc_18003F508
0x18003f3d1  cmp     ebp, 3Eh ; '>'
0x18003f3d4  jb      loc_18003F571
0x18003f3da  lea     r14, [rbx+0Fh]
0x18003f3de  and     r14, 0FFFFFFFFFFFFFFF0h
0x18003f3e2  mov     dword ptr [r14], 20h ; ' '
0x18003f3e9  mov     dword ptr [r14+4], 55555552h
0x18003f3f1  mov     [r14+8], rsi
0x18003f3f5  mov     [r14+18h], rdi
0x18003f3f9  mov     ecx, [rsi+24h]
0x18003f3fc  sub     ecx, 1
0x18003f3ff  jnz     loc_18003F57B
0x18003f405  mov     rax, [rsi+80h]
0x18003f40c  lea     r8, [r14+2Fh]
0x18003f410  mov     rcx, [r13+10h]
0x18003f414  lea     rdx, [r14+10h]
0x18003f418  and     r8, 0FFFFFFFFFFFFFFF0h
0x18003f41c  mov     dword ptr [rsp+98h+var_78], r12d
0x18003f421  sub     ebx, r8d
0x18003f424  lea     r9d, [rbx+rbp]
0x18003f428  call    _guard_dispatch_icall
0x18003f42d  mov     ebx, eax
0x18003f42f  test    eax, eax
0x18003f431  js      loc_18003F551
0x18003f437  xor     edi, edi
0x18003f439  mov     [r15], r14
0x18003f43c  test    rdi, rdi
0x18003f43f  jnz     loc_18003F596
0x18003f445  test    rsi, rsi
0x18003f448  jz      short loc_18003F452
0x18003f44a  test    ebx, ebx
0x18003f44c  js      short loc_18003F452
0x18003f44e  lock inc dword ptr [rsi+10h]
0x18003f452  mov     eax, ebx
0x18003f454  add     rsp, 58h
0x18003f458  pop     r15
0x18003f45a  pop     r14
0x18003f45c  pop     r13
0x18003f45e  pop     r12
0x18003f460  pop     rdi
0x18003f461  pop     rsi
0x18003f462  pop     rbp
0x18003f463  pop     rbx
0x18003f464  retn
0x18003f466  mov     ebx, 0C0000008h
0x18003f46b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f472  cmp     rcx, r14
0x18003f475  jz      short loc_18003F452
0x18003f477  mov     eax, [rcx+2Ch]
0x18003f47a  test    al, 1
0x18003f47c  jz      short loc_18003F452
0x18003f47e  mov     rcx, [rcx+18h]
0x18003f482  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f489  mov     [rsp+98h+var_68], 154Dh
0x18003f491  lea     r9, aStatus; "Status"
0x18003f498  mov     [rsp+98h+var_70], r8
0x18003f49d  mov     dword ptr [rsp+98h+var_78], 0C0000008h
0x18003f4a5  call    WPP_SF_sDsd
0x18003f4aa  jmp     short loc_18003F452
0x18003f4ac  mov     eax, [rcx+2Ch]
0x18003f4af  test    al, 4
0x18003f4b1  jz      loc_18003F3A7
0x18003f4b7  mov     rcx, [rcx+18h]
0x18003f4bb  mov     edx, 1Eh
0x18003f4c0  mov     [rsp+98h+var_60], r12d
0x18003f4c5  mov     r9, rsi
0x18003f4c8  mov     [rsp+98h+var_68], ebp
0x18003f4cc  mov     [rsp+98h+var_70], rbx
0x18003f4d1  mov     [rsp+98h+var_78], r15
0x18003f4d6  call    WPP_SF_qqqdD
0x18003f4db  jmp     loc_18003F3A7
0x18003f4e0  mov     r9d, 1554h
0x18003f4e6  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f4ed  lea     rdx, aStatus; "Status"
0x18003f4f4  mov     ecx, 0C000000Dh
0x18003f4f9  mov     ebx, 0C000000Dh
0x18003f4fe  call    DebugTraceError
0x18003f503  jmp     loc_18003F452
0x18003f508  test    ebp, ebp
0x18003f50a  jnz     loc_1800A7B9A
0x18003f510  lea     r8, [rsp+98h+var_58]
0x18003f515  mov     rcx, rsi
0x18003f518  lea     rdx, [rsp+98h+var_50]
0x18003f51d  call    AllocateObjectBuffer
0x18003f522  mov     ebx, eax
0x18003f524  test    eax, eax
0x18003f526  jns     loc_1800A7B8E
0x18003f52c  mov     r9d, 1563h
0x18003f532  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f539  lea     rdx, aStatus; "Status"
0x18003f540  mov     ecx, eax
0x18003f542  call    DebugTraceError
0x18003f547  mov     rdi, [rsp+98h+var_50]
0x18003f54c  jmp     loc_18003F43C
0x18003f551  mov     r9d, 15A3h
0x18003f557  mov     ecx, eax
0x18003f559  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f560  lea     rdx, aStatus; "Status"
0x18003f567  call    DebugTraceError
0x18003f56c  jmp     loc_18003F43C
0x18003f571  mov     ebx, 0C0000023h
0x18003f576  jmp     loc_18003F43C
0x18003f57b  cmp     ecx, 6
0x18003f57e  jz      loc_18003F405
0x18003f584  mov     ebx, 0C00000BBh
0x18003f589  mov     r9d, 1598h
0x18003f58f  mov     ecx, 0C00000BBh
0x18003f594  jmp     short loc_18003F559
0x18003f596  mov     rcx, rdi; P
0x18003f599  call    MSCryptFree
0x18003f59e  jmp     loc_18003F445
0x1800a7b8e  mov     rdi, [rsp+98h+var_50]
0x1800a7b93  mov     ebp, [rsp+98h+var_58]
0x1800a7b97  mov     rbx, rdi
0x1800a7b9a  test    rbx, rbx
0x1800a7b9d  jnz     loc_18003F3D1
0x1800a7ba3  mov     ebx, 0C000000Dh
0x1800a7ba8  mov     r9d, 1574h
0x1800a7bae  mov     ecx, 0C000000Dh
0x1800a7bb3  jmp     loc_18003F559
```
