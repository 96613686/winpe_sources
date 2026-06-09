# MSCryptKDDuplicateKey

- ea: `0x1800747a0`
- end: `0x18007494d`
- name: `MSCryptKDDuplicateKey`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003f70`
- `0x180005670`
- `0x180006470`
- `0x18000743c`
- `0x180039f20`
- `0x18004c3d0`
- `0x1800747a0`
- `0x180074960`

## string_xrefs

- `0x1800747f4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800748c5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

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
0x1800747a0  push    rbx
0x1800747a2  push    rbp
0x1800747a3  push    rsi
0x1800747a4  push    rdi
0x1800747a5  push    r14
0x1800747a7  push    r15
0x1800747a9  sub     rsp, 78h
0x1800747ad  cmp     [rsp+0A8h+arg_20], 0
0x1800747b5  mov     ebp, r9d
0x1800747b8  mov     r15, r8
0x1800747bb  mov     [rsp+0A8h+var_50], 0
0x1800747c4  mov     r14, rdx
0x1800747c7  mov     [rsp+0A8h+var_48], 0
0x1800747d0  mov     rsi, rcx
0x1800747d3  mov     [rsp+0A8h+var_58], 0
0x1800747db  jz      short loc_180074805
0x1800747dd  mov     ebx, 0C000000Dh
0x1800747e2  mov     r9d, 8A8h
0x1800747e8  mov     ecx, 0C000000Dh
0x1800747ed  lea     rdx, aStatus; "Status"
0x1800747f4  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800747fb  call    DebugTraceError
0x180074800  jmp     loc_18007493D
0x180074805  lea     rdx, [rsp+0A8h+var_50]
0x18007480a  call    ValidateKeyDerivationKey
0x18007480f  test    eax, eax
0x180074811  jns     short loc_180074825
0x180074813  mov     ebx, 0C0000008h
0x180074818  mov     r9d, 8B3h
0x18007481e  mov     ecx, 0C0000008h
0x180074823  jmp     short loc_1800747ED
0x180074825  lea     rax, [rsp+0A8h+var_58]
0x18007482a  mov     dword ptr [rsp+0A8h+var_78], 0
0x180074832  mov     [rsp+0A8h+var_80], rax
0x180074837  lea     r8, aKeydatablob; "KeyDataBlob"
0x18007483e  xor     r9d, r9d
0x180074841  mov     dword ptr [rsp+0A8h+var_88], 0
0x180074849  xor     edx, edx
0x18007484b  mov     rcx, rsi
0x18007484e  call    MSCryptKDExportKey
0x180074853  mov     ebx, eax
0x180074855  test    eax, eax
0x180074857  jns     short loc_180074863
0x180074859  mov     r9d, 8C5h
0x18007485f  mov     ecx, eax
0x180074861  jmp     short loc_1800747ED
0x180074863  mov     ebx, [rsp+0A8h+var_58]
0x180074867  mov     ecx, ebx
0x180074869  call    MSCryptAlloc
0x18007486e  mov     rdi, rax
0x180074871  test    rax, rax
0x180074874  jnz     short loc_18007488B
0x180074876  mov     ebx, 0C0000017h
0x18007487b  mov     r9d, 8CDh
0x180074881  mov     ecx, 0C0000017h
0x180074886  jmp     loc_1800747ED
0x18007488b  lea     rax, [rsp+0A8h+var_58]
0x180074890  mov     dword ptr [rsp+0A8h+var_78], 0
0x180074898  mov     [rsp+0A8h+var_80], rax
0x18007489d  lea     r8, aKeydatablob; "KeyDataBlob"
0x1800748a4  mov     r9, rdi
0x1800748a7  mov     dword ptr [rsp+0A8h+var_88], ebx
0x1800748ab  xor     edx, edx
0x1800748ad  mov     rcx, rsi
0x1800748b0  call    MSCryptKDExportKey
0x1800748b5  mov     esi, [rsp+0A8h+var_58]
0x1800748b9  mov     ebx, eax
0x1800748bb  test    eax, eax
0x1800748bd  jns     short loc_1800748DC
0x1800748bf  mov     r9d, 8DBh
0x1800748c5  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800748cc  mov     ecx, eax
0x1800748ce  lea     rdx, aStatus; "Status"
0x1800748d5  call    DebugTraceError
0x1800748da  jmp     short loc_18007492A
0x1800748dc  mov     rcx, [rsp+0A8h+var_50]
0x1800748e1  lea     r9, [rsp+0A8h+var_48]
0x1800748e6  mov     [rsp+0A8h+var_68], 0
0x1800748ee  lea     r8, aKeydatablob; "KeyDataBlob"
0x1800748f5  mov     [rsp+0A8h+var_70], esi
0x1800748f9  xor     edx, edx
0x1800748fb  mov     [rsp+0A8h+var_78], rdi
0x180074900  mov     rcx, [rcx+28h]
0x180074904  mov     dword ptr [rsp+0A8h+var_80], ebp
0x180074908  mov     [rsp+0A8h+var_88], r15
0x18007490d  call    MSCryptKDImportKey
0x180074912  mov     ebx, eax
0x180074914  test    eax, eax
0x180074916  jns     short loc_180074920
0x180074918  mov     r9d, 8F0h
0x18007491e  jmp     short loc_1800748C5
0x180074920  mov     rax, [rsp+0A8h+var_48]
0x180074925  xor     ebx, ebx
0x180074927  mov     [r14], rax
0x18007492a  mov     rdx, rsi
0x18007492d  mov     rcx, rdi
0x180074930  call    SymCryptWipeAsm
0x180074935  mov     rcx, rdi; P
0x180074938  call    MSCryptFree
0x18007493d  mov     eax, ebx
0x18007493f  add     rsp, 78h
0x180074943  pop     r15
0x180074945  pop     r14
0x180074947  pop     rdi
0x180074948  pop     rsi
0x180074949  pop     rbp
0x18007494a  pop     rbx
0x18007494b  retn
```
