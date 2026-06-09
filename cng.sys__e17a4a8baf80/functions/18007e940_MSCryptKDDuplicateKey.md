# MSCryptKDDuplicateKey

- ea: `0x18007e940`
- end: `0x18007eaed`
- name: `MSCryptKDDuplicateKey`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000e090`
- `0x18000f790`
- `0x180010590`
- `0x18001155c`
- `0x180043fb0`
- `0x1800564d0`
- `0x18007e940`
- `0x18007eb00`

## string_xrefs

- `0x18007e994`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18007ea65`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDDuplicateKey(__int64 a1, _QWORD *a2, __int64 a3, unsigned int a4, int a5)
{
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  unsigned int v14; // ebx
  _DWORD *v15; // rdi
  int v16; // eax
  __int64 v17; // rsi
  __int64 v18; // r9
  unsigned int v20; // [rsp+50h] [rbp-58h] BYREF
  __int64 v21; // [rsp+58h] [rbp-50h] BYREF
  _QWORD v22[9]; // [rsp+60h] [rbp-48h] BYREF

  v21 = 0;
  v22[0] = 0;
  v20 = 0;
  if ( !a5 )
  {
    if ( (int)ValidateKeyDerivationKey(a1, &v21) < 0 )
    {
      v9 = -1073741816;
      v10 = 2227;
      v11 = 3221225480LL;
      goto LABEL_3;
    }
    v12 = MSCryptKDExportKey(a1, 0, L"KeyDataBlob", 0, 0, &v20, 0);
    v9 = v12;
    if ( v12 < 0 )
    {
      v10 = 2245;
      v11 = (unsigned int)v12;
      goto LABEL_3;
    }
    v14 = v20;
    v15 = (_DWORD *)MSCryptAlloc(v20, v13);
    if ( !v15 )
    {
      v9 = -1073741801;
      v10 = 2253;
      v11 = 3221225495LL;
      goto LABEL_3;
    }
    v16 = MSCryptKDExportKey(a1, 0, L"KeyDataBlob", v15, v14, &v20, 0);
    v17 = v20;
    v9 = v16;
    if ( v16 >= 0 )
    {
      v16 = MSCryptKDImportKey(*(_DWORD **)(v21 + 40), 0, L"KeyDataBlob", v22, a3, a4, v15, v20, 0);
      v9 = v16;
      if ( v16 >= 0 )
      {
        v9 = 0;
        *a2 = v22[0];
        goto LABEL_16;
      }
      v18 = 2288;
    }
    else
    {
      v18 = 2267;
    }
    DebugTraceError(
      (unsigned int)v16,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v18);
LABEL_16:
    SymCryptWipeAsm(v15, v17);
    MSCryptFree(v15);
    return v9;
  }
  v9 = -1073741811;
  v10 = 2216;
  v11 = 3221225485LL;
LABEL_3:
  DebugTraceError(
    v11,
    "Status",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
    v10);
  return v9;
}

```

## disassembly

```asm
0x18007e940  push    rbx
0x18007e942  push    rbp
0x18007e943  push    rsi
0x18007e944  push    rdi
0x18007e945  push    r14
0x18007e947  push    r15
0x18007e949  sub     rsp, 78h
0x18007e94d  cmp     [rsp+0A8h+arg_20], 0
0x18007e955  mov     ebp, r9d
0x18007e958  mov     r15, r8
0x18007e95b  mov     [rsp+0A8h+var_50], 0
0x18007e964  mov     r14, rdx
0x18007e967  mov     [rsp+0A8h+var_48], 0
0x18007e970  mov     rsi, rcx
0x18007e973  mov     [rsp+0A8h+var_58], 0
0x18007e97b  jz      short loc_18007E9A5
0x18007e97d  mov     ebx, 0C000000Dh
0x18007e982  mov     r9d, 8A8h
0x18007e988  mov     ecx, 0C000000Dh
0x18007e98d  lea     rdx, aStatus; "Status"
0x18007e994  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007e99b  call    DebugTraceError
0x18007e9a0  jmp     loc_18007EADD
0x18007e9a5  lea     rdx, [rsp+0A8h+var_50]
0x18007e9aa  call    ValidateKeyDerivationKey
0x18007e9af  test    eax, eax
0x18007e9b1  jns     short loc_18007E9C5
0x18007e9b3  mov     ebx, 0C0000008h
0x18007e9b8  mov     r9d, 8B3h
0x18007e9be  mov     ecx, 0C0000008h
0x18007e9c3  jmp     short loc_18007E98D
0x18007e9c5  lea     rax, [rsp+0A8h+var_58]
0x18007e9ca  mov     dword ptr [rsp+0A8h+var_78], 0
0x18007e9d2  mov     [rsp+0A8h+var_80], rax
0x18007e9d7  lea     r8, aKeydatablob; "KeyDataBlob"
0x18007e9de  xor     r9d, r9d
0x18007e9e1  mov     dword ptr [rsp+0A8h+var_88], 0
0x18007e9e9  xor     edx, edx
0x18007e9eb  mov     rcx, rsi
0x18007e9ee  call    MSCryptKDExportKey
0x18007e9f3  mov     ebx, eax
0x18007e9f5  test    eax, eax
0x18007e9f7  jns     short loc_18007EA03
0x18007e9f9  mov     r9d, 8C5h
0x18007e9ff  mov     ecx, eax
0x18007ea01  jmp     short loc_18007E98D
0x18007ea03  mov     ebx, [rsp+0A8h+var_58]
0x18007ea07  mov     ecx, ebx
0x18007ea09  call    MSCryptAlloc
0x18007ea0e  mov     rdi, rax
0x18007ea11  test    rax, rax
0x18007ea14  jnz     short loc_18007EA2B
0x18007ea16  mov     ebx, 0C0000017h
0x18007ea1b  mov     r9d, 8CDh
0x18007ea21  mov     ecx, 0C0000017h
0x18007ea26  jmp     loc_18007E98D
0x18007ea2b  lea     rax, [rsp+0A8h+var_58]
0x18007ea30  mov     dword ptr [rsp+0A8h+var_78], 0
0x18007ea38  mov     [rsp+0A8h+var_80], rax
0x18007ea3d  lea     r8, aKeydatablob; "KeyDataBlob"
0x18007ea44  mov     r9, rdi
0x18007ea47  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18007ea4b  xor     edx, edx
0x18007ea4d  mov     rcx, rsi
0x18007ea50  call    MSCryptKDExportKey
0x18007ea55  mov     esi, [rsp+0A8h+var_58]
0x18007ea59  mov     ebx, eax
0x18007ea5b  test    eax, eax
0x18007ea5d  jns     short loc_18007EA7C
0x18007ea5f  mov     r9d, 8DBh
0x18007ea65  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007ea6c  mov     ecx, eax
0x18007ea6e  lea     rdx, aStatus; "Status"
0x18007ea75  call    DebugTraceError
0x18007ea7a  jmp     short loc_18007EACA
0x18007ea7c  mov     rcx, [rsp+0A8h+var_50]
0x18007ea81  lea     r9, [rsp+0A8h+var_48]
0x18007ea86  mov     [rsp+0A8h+var_68], 0
0x18007ea8e  lea     r8, aKeydatablob; "KeyDataBlob"
0x18007ea95  mov     [rsp+0A8h+var_70], esi
0x18007ea99  xor     edx, edx
0x18007ea9b  mov     [rsp+0A8h+var_78], rdi
0x18007eaa0  mov     rcx, [rcx+28h]
0x18007eaa4  mov     dword ptr [rsp+0A8h+var_80], ebp
0x18007eaa8  mov     [rsp+0A8h+var_88], r15
0x18007eaad  call    MSCryptKDImportKey
0x18007eab2  mov     ebx, eax
0x18007eab4  test    eax, eax
0x18007eab6  jns     short loc_18007EAC0
0x18007eab8  mov     r9d, 8F0h
0x18007eabe  jmp     short loc_18007EA65
0x18007eac0  mov     rax, [rsp+0A8h+var_48]
0x18007eac5  xor     ebx, ebx
0x18007eac7  mov     [r14], rax
0x18007eaca  mov     rdx, rsi
0x18007eacd  mov     rcx, rdi
0x18007ead0  call    SymCryptWipeAsm
0x18007ead5  mov     rcx, rdi; P
0x18007ead8  call    MSCryptFree
0x18007eadd  mov     eax, ebx
0x18007eadf  add     rsp, 78h
0x18007eae3  pop     r15
0x18007eae5  pop     r14
0x18007eae7  pop     rdi
0x18007eae8  pop     rsi
0x18007eae9  pop     rbp
0x18007eaea  pop     rbx
0x18007eaeb  retn
```
