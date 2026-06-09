# MSCryptKDDuplicateKey

- ea: `0x1800751b0`
- end: `0x18007535d`
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
- `0x18003aa20`
- `0x18004cc10`
- `0x1800751b0`
- `0x180075370`

## string_xrefs

- `0x180075204`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800752d5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDDuplicateKey(__int64 a1, _QWORD *a2, __int64 a3, unsigned int a4, int a5)
{
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // ebx
  _DWORD *v17; // rdi
  int v18; // eax
  __int64 v19; // rsi
  __int64 v20; // r9
  unsigned int v22; // [rsp+50h] [rbp-58h] BYREF
  __int64 v23; // [rsp+58h] [rbp-50h] BYREF
  _QWORD v24[9]; // [rsp+60h] [rbp-48h] BYREF

  v23 = 0;
  v24[0] = 0;
  v22 = 0;
  if ( !a5 )
  {
    if ( (int)ValidateKeyDerivationKey(a1, &v23) < 0 )
    {
      v9 = -1073741816;
      v10 = 2227;
      v11 = 3221225480LL;
      goto LABEL_3;
    }
    v12 = MSCryptKDExportKey(a1, 0, L"KeyDataBlob", 0, 0, &v22, 0);
    v9 = v12;
    if ( v12 < 0 )
    {
      v10 = 2245;
      v11 = (unsigned int)v12;
      goto LABEL_3;
    }
    v16 = v22;
    v17 = (_DWORD *)MSCryptAlloc(v22, v13, v14, v15);
    if ( !v17 )
    {
      v9 = -1073741801;
      v10 = 2253;
      v11 = 3221225495LL;
      goto LABEL_3;
    }
    v18 = MSCryptKDExportKey(a1, 0, L"KeyDataBlob", v17, v16, &v22, 0);
    v19 = v22;
    v9 = v18;
    if ( v18 >= 0 )
    {
      v18 = MSCryptKDImportKey(*(_DWORD **)(v23 + 40), 0, L"KeyDataBlob", v24, a3, a4, v17, v22, 0);
      v9 = v18;
      if ( v18 >= 0 )
      {
        v9 = 0;
        *a2 = v24[0];
        goto LABEL_16;
      }
      v20 = 2288;
    }
    else
    {
      v20 = 2267;
    }
    DebugTraceError(
      (unsigned int)v18,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v20);
LABEL_16:
    SymCryptWipeAsm(v17, v19);
    MSCryptFree(v17);
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
0x1800751b0  push    rbx
0x1800751b2  push    rbp
0x1800751b3  push    rsi
0x1800751b4  push    rdi
0x1800751b5  push    r14
0x1800751b7  push    r15
0x1800751b9  sub     rsp, 78h
0x1800751bd  cmp     [rsp+0A8h+arg_20], 0
0x1800751c5  mov     ebp, r9d
0x1800751c8  mov     r15, r8
0x1800751cb  mov     [rsp+0A8h+var_50], 0
0x1800751d4  mov     r14, rdx
0x1800751d7  mov     [rsp+0A8h+var_48], 0
0x1800751e0  mov     rsi, rcx
0x1800751e3  mov     [rsp+0A8h+var_58], 0
0x1800751eb  jz      short loc_180075215
0x1800751ed  mov     ebx, 0C000000Dh
0x1800751f2  mov     r9d, 8A8h
0x1800751f8  mov     ecx, 0C000000Dh
0x1800751fd  lea     rdx, aStatus; "Status"
0x180075204  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007520b  call    DebugTraceError
0x180075210  jmp     loc_18007534D
0x180075215  lea     rdx, [rsp+0A8h+var_50]
0x18007521a  call    ValidateKeyDerivationKey
0x18007521f  test    eax, eax
0x180075221  jns     short loc_180075235
0x180075223  mov     ebx, 0C0000008h
0x180075228  mov     r9d, 8B3h
0x18007522e  mov     ecx, 0C0000008h
0x180075233  jmp     short loc_1800751FD
0x180075235  lea     rax, [rsp+0A8h+var_58]
0x18007523a  mov     dword ptr [rsp+0A8h+var_78], 0
0x180075242  mov     [rsp+0A8h+var_80], rax
0x180075247  lea     r8, aKeydatablob; "KeyDataBlob"
0x18007524e  xor     r9d, r9d
0x180075251  mov     dword ptr [rsp+0A8h+var_88], 0
0x180075259  xor     edx, edx
0x18007525b  mov     rcx, rsi
0x18007525e  call    MSCryptKDExportKey
0x180075263  mov     ebx, eax
0x180075265  test    eax, eax
0x180075267  jns     short loc_180075273
0x180075269  mov     r9d, 8C5h
0x18007526f  mov     ecx, eax
0x180075271  jmp     short loc_1800751FD
0x180075273  mov     ebx, [rsp+0A8h+var_58]
0x180075277  mov     ecx, ebx
0x180075279  call    MSCryptAlloc
0x18007527e  mov     rdi, rax
0x180075281  test    rax, rax
0x180075284  jnz     short loc_18007529B
0x180075286  mov     ebx, 0C0000017h
0x18007528b  mov     r9d, 8CDh
0x180075291  mov     ecx, 0C0000017h
0x180075296  jmp     loc_1800751FD
0x18007529b  lea     rax, [rsp+0A8h+var_58]
0x1800752a0  mov     dword ptr [rsp+0A8h+var_78], 0
0x1800752a8  mov     [rsp+0A8h+var_80], rax
0x1800752ad  lea     r8, aKeydatablob; "KeyDataBlob"
0x1800752b4  mov     r9, rdi
0x1800752b7  mov     dword ptr [rsp+0A8h+var_88], ebx
0x1800752bb  xor     edx, edx
0x1800752bd  mov     rcx, rsi
0x1800752c0  call    MSCryptKDExportKey
0x1800752c5  mov     esi, [rsp+0A8h+var_58]
0x1800752c9  mov     ebx, eax
0x1800752cb  test    eax, eax
0x1800752cd  jns     short loc_1800752EC
0x1800752cf  mov     r9d, 8DBh
0x1800752d5  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800752dc  mov     ecx, eax
0x1800752de  lea     rdx, aStatus; "Status"
0x1800752e5  call    DebugTraceError
0x1800752ea  jmp     short loc_18007533A
0x1800752ec  mov     rcx, [rsp+0A8h+var_50]
0x1800752f1  lea     r9, [rsp+0A8h+var_48]
0x1800752f6  mov     [rsp+0A8h+var_68], 0
0x1800752fe  lea     r8, aKeydatablob; "KeyDataBlob"
0x180075305  mov     [rsp+0A8h+var_70], esi
0x180075309  xor     edx, edx
0x18007530b  mov     [rsp+0A8h+var_78], rdi
0x180075310  mov     rcx, [rcx+28h]
0x180075314  mov     dword ptr [rsp+0A8h+var_80], ebp
0x180075318  mov     [rsp+0A8h+var_88], r15
0x18007531d  call    MSCryptKDImportKey
0x180075322  mov     ebx, eax
0x180075324  test    eax, eax
0x180075326  jns     short loc_180075330
0x180075328  mov     r9d, 8F0h
0x18007532e  jmp     short loc_1800752D5
0x180075330  mov     rax, [rsp+0A8h+var_48]
0x180075335  xor     ebx, ebx
0x180075337  mov     [r14], rax
0x18007533a  mov     rdx, rsi
0x18007533d  mov     rcx, rdi
0x180075340  call    SymCryptWipeAsm
0x180075345  mov     rcx, rdi; P
0x180075348  call    MSCryptFree
0x18007534d  mov     eax, ebx
0x18007534f  add     rsp, 78h
0x180075353  pop     r15
0x180075355  pop     r14
0x180075357  pop     rdi
0x180075358  pop     rsi
0x180075359  pop     rbp
0x18007535a  pop     rbx
0x18007535b  retn
```
