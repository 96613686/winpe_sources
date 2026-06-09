# SPSslCombineKeys

- ea: `0x18001e480`
- end: `0x18001e5b5`
- name: `SPSslCombineKeys`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x18000b654`
- `0x18001e480`
- `0x180022ca4`
- `0x180023234`
- `0x18002396c`

## string_xrefs

- `0x18001e4d2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001e573`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslCombineKeys(__int64 a1, unsigned __int16 a2, __int64 a3, __int64 a4, _QWORD *a5, int a6)
{
  int v7; // r10d
  int v8; // r11d
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-28h] BYREF
  __int64 v18; // [rsp+38h] [rbp-20h] BYREF
  __int64 v19; // [rsp+40h] [rbp-18h] BYREF

  v19 = 0;
  v18 = 0;
  v17 = 0;
  if ( !SslpValidateProvHandle(a1) )
  {
    v9 = -2146893786;
    v10 = 7405;
    v11 = 2148073510LL;
LABEL_3:
    DebugTraceError(v11, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v10);
    return v9;
  }
  if ( a6 )
  {
    v9 = -2146893815;
    v10 = 7412;
    v11 = 2148073481LL;
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v9 = -2146893785;
    v10 = 7419;
    v11 = 2148073511LL;
    goto LABEL_3;
  }
  v12 = SslpValidateKeysForHybridCreation(a2, v8, v7, (unsigned int)&v19, (__int64)&v18);
  v9 = v12;
  if ( v12 < 0 )
  {
    v10 = 7431;
    v11 = (unsigned int)v12;
    goto LABEL_3;
  }
  v14 = SslpCreateBaseHybridKeyStruct(v13, a2, v19, v18, &v17);
  v9 = v14;
  if ( v14 >= 0 )
  {
    v15 = 0;
    *a5 = v17;
  }
  else
  {
    DebugTraceError((unsigned int)v14, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 7443);
    v15 = v17;
  }
  if ( v15 )
    SslpFreeHybridKey(v15);
  return v9;
}

```

## disassembly

```asm
0x18001e480  mov     rax, rsp
0x18001e483  mov     [rax+8], rbx
0x18001e487  mov     [rax+10h], rsi
0x18001e48b  push    rdi
0x18001e48c  sub     rsp, 50h
0x18001e490  mov     r10, r9
0x18001e493  mov     qword ptr [rax-18h], 0
0x18001e49b  mov     r11, r8
0x18001e49e  mov     qword ptr [rax-20h], 0
0x18001e4a6  movzx   esi, dx
0x18001e4a9  mov     qword ptr [rax-28h], 0
0x18001e4b1  call    SslpValidateProvHandle
0x18001e4b6  test    rax, rax
0x18001e4b9  jnz     short loc_18001E4E3
0x18001e4bb  mov     ebx, 80090026h
0x18001e4c0  mov     r9d, 1CEDh
0x18001e4c6  mov     ecx, 80090026h
0x18001e4cb  lea     rdx, aStatus_0; "status"
0x18001e4d2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001e4d9  call    DebugTraceError
0x18001e4de  jmp     loc_18001E5A3
0x18001e4e3  cmp     [rsp+58h+arg_28], 0
0x18001e4eb  jz      short loc_18001E4FF
0x18001e4ed  mov     ebx, 80090009h
0x18001e4f2  mov     r9d, 1CF4h
0x18001e4f8  mov     ecx, 80090009h
0x18001e4fd  jmp     short loc_18001E4CB
0x18001e4ff  mov     rdi, [rsp+58h+arg_20]
0x18001e507  test    rdi, rdi
0x18001e50a  jnz     short loc_18001E51E
0x18001e50c  mov     ebx, 80090027h
0x18001e511  mov     r9d, 1CFBh
0x18001e517  mov     ecx, 80090027h
0x18001e51c  jmp     short loc_18001E4CB
0x18001e51e  lea     rax, [rsp+58h+var_20]
0x18001e523  mov     r8, r10
0x18001e526  lea     r9, [rsp+58h+var_18]
0x18001e52b  mov     [rsp+58h+var_38], rax
0x18001e530  mov     rdx, r11
0x18001e533  movzx   ecx, si
0x18001e536  call    SslpValidateKeysForHybridCreation
0x18001e53b  mov     ebx, eax
0x18001e53d  test    eax, eax
0x18001e53f  jns     short loc_18001E54B
0x18001e541  mov     r9d, 1D07h
0x18001e547  mov     ecx, eax
0x18001e549  jmp     short loc_18001E4CB
0x18001e54b  mov     r9, [rsp+58h+var_20]
0x18001e550  lea     rax, [rsp+58h+var_28]
0x18001e555  mov     r8, [rsp+58h+var_18]
0x18001e55a  movzx   edx, si
0x18001e55d  mov     [rsp+58h+var_38], rax
0x18001e562  call    SslpCreateBaseHybridKeyStruct
0x18001e567  mov     ebx, eax
0x18001e569  test    eax, eax
0x18001e56b  jns     short loc_18001E58F
0x18001e56d  mov     r9d, 1D13h
0x18001e573  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001e57a  lea     rdx, aStatus_0; "status"
0x18001e581  mov     ecx, eax
0x18001e583  call    DebugTraceError
0x18001e588  mov     rcx, [rsp+58h+var_28]
0x18001e58d  jmp     short loc_18001E599
0x18001e58f  mov     rax, [rsp+58h+var_28]
0x18001e594  xor     ecx, ecx
0x18001e596  mov     [rdi], rax
0x18001e599  test    rcx, rcx
0x18001e59c  jz      short loc_18001E5A3
0x18001e59e  call    SslpFreeHybridKey
0x18001e5a3  mov     rsi, [rsp+58h+arg_8]
0x18001e5a8  mov     eax, ebx
0x18001e5aa  mov     rbx, [rsp+58h+arg_0]
0x18001e5af  add     rsp, 50h
0x18001e5b3  pop     rdi
0x18001e5b4  retn
```
