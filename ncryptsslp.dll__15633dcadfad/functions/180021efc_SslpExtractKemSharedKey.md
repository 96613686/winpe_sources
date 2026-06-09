# SslpExtractKemSharedKey

- ea: `0x180021efc`
- end: `0x18002215d`
- name: `SslpExtractKemSharedKey`
- size: `609`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000dea0`
- `0x180022fa8`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x18000b654`
- `0x180021efc`
- `0x180023a78`

## import_xrefs

- `ncrypt!NCryptDecapsulate` at `0x180022088`
- `ncrypt!NCryptDecapsulate` at `0x1800220dd`
- `ncrypt!NCryptDecapsulate` at `0x180022088`
- `ncrypt!NCryptDecapsulate` at `0x1800220dd`
- `ncrypt!NCryptEncapsulate` at `0x180021f99`
- `ncrypt!NCryptEncapsulate` at `0x180022028`
- `ncrypt!NCryptEncapsulate` at `0x180021f99`
- `ncrypt!NCryptEncapsulate` at `0x180022028`

## string_xrefs

- `0x1800220f5`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`
- `0x180022137`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`

## pseudocode

```c
__int64 __fastcall SslpExtractKemSharedKey(__int64 a1, __int64 a2, __int64 *a3, unsigned int *a4)
{
  __int64 v6; // r14
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rsi
  __int64 v12; // r15
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rdi
  __int64 v20; // r9
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  unsigned int v27; // [rsp+40h] [rbp-18h] BYREF
  _DWORD v28[5]; // [rsp+44h] [rbp-14h] BYREF

  v6 = SslpValidateKemKeyHandle(a1);
  v8 = SslpValidateKemKeyHandle(v7);
  v11 = 0;
  v12 = v8;
  v27 = 0;
  if ( !v6 || !v8 || !v9 || !v10 )
  {
    v17 = 620;
    goto LABEL_33;
  }
  v13 = *(_QWORD *)(v6 + 24);
  if ( v13 || *(_QWORD *)(v6 + 32) || *(_DWORD *)(v6 + 40) )
  {
    v23 = *(_QWORD *)(v8 + 32);
    if ( v23 )
    {
      v24 = *(unsigned int *)(v8 + 40);
      if ( (_DWORD)v24 )
      {
        v15 = NCryptDecapsulate(v13, v23, v24, 0, 0, &v27, 0);
        v16 = v15;
        if ( v15 < 0 )
        {
          v17 = 706;
          goto LABEL_10;
        }
        v25 = SafeAllocaAllocateFromHeap(v27);
        v19 = v25;
        if ( !v25 )
        {
          v17 = 714;
          goto LABEL_13;
        }
        v22 = NCryptDecapsulate(
                *(_QWORD *)(v6 + 24),
                *(_QWORD *)(v12 + 32),
                *(unsigned int *)(v12 + 40),
                v25,
                v27,
                &v27,
                0);
        v16 = v22;
        if ( v22 < 0 )
        {
          v20 = 728;
          goto LABEL_28;
        }
LABEL_19:
        *a4 = v27;
        *a3 = v19;
        return v16;
      }
    }
    v17 = 692;
LABEL_33:
    v18 = 2148073511LL;
    v16 = -2146893785;
    goto LABEL_34;
  }
  v14 = *(_QWORD *)(v8 + 24);
  v28[0] = 0;
  v15 = NCryptEncapsulate(v14, 0, 0, &v27, 0, 0, v28, 0);
  v16 = v15;
  if ( v15 < 0 )
  {
    v17 = 646;
LABEL_10:
    v18 = (unsigned int)v15;
LABEL_34:
    DebugTraceError(v18, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", v17);
    return v16;
  }
  v19 = SafeAllocaAllocateFromHeap(v27);
  if ( !v19 )
  {
    v17 = 654;
LABEL_13:
    v16 = -2146893810;
    v18 = 2148073486LL;
    goto LABEL_34;
  }
  v11 = SafeAllocaAllocateFromHeap(v28[0]);
  if ( !v11 )
  {
    v16 = -2146893810;
    v20 = 662;
    v21 = 2148073486LL;
    goto LABEL_29;
  }
  v22 = NCryptEncapsulate(*(_QWORD *)(v12 + 24), v19, v27, &v27, v11, v28[0], v28, 0);
  v16 = v22;
  if ( v22 >= 0 )
  {
    *(_DWORD *)(v6 + 40) = v28[0];
    *(_QWORD *)(v6 + 32) = v11;
    goto LABEL_19;
  }
  v20 = 677;
LABEL_28:
  v21 = (unsigned int)v22;
LABEL_29:
  DebugTraceError(v21, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", v20);
  MSCryptFree(v19);
  if ( v11 )
    MSCryptFree(v11);
  return v16;
}

```

## disassembly

```asm
0x180021efc  push    rbp
0x180021efe  push    rbx
0x180021eff  push    rsi
0x180021f00  push    rdi
0x180021f01  push    r12
0x180021f03  push    r13
0x180021f05  push    r14
0x180021f07  push    r15
0x180021f09  mov     rbp, rsp
0x180021f0c  sub     rsp, 58h
0x180021f10  mov     r12, r9
0x180021f13  mov     r13, r8
0x180021f16  call    SslpValidateKemKeyHandle
0x180021f1b  mov     rcx, rdx
0x180021f1e  mov     r14, rax
0x180021f21  call    SslpValidateKemKeyHandle
0x180021f26  xor     esi, esi
0x180021f28  mov     r15, rax
0x180021f2b  mov     [rbp+var_18], esi
0x180021f2e  test    r14, r14
0x180021f31  jz      loc_180022127
0x180021f37  test    rax, rax
0x180021f3a  jz      loc_180022127
0x180021f40  test    r8, r8
0x180021f43  jz      loc_180022127
0x180021f49  test    r9, r9
0x180021f4c  jz      loc_180022127
0x180021f52  mov     rcx, [r14+18h]
0x180021f56  test    rcx, rcx
0x180021f59  jnz     loc_18002205A
0x180021f5f  cmp     [r14+20h], rsi
0x180021f63  jnz     loc_18002205A
0x180021f69  cmp     [r14+28h], esi
0x180021f6d  jnz     loc_18002205A
0x180021f73  mov     rcx, [r15+18h]
0x180021f77  lea     rax, [rbp+var_14]
0x180021f7b  mov     [rsp+58h+var_20], esi
0x180021f7f  lea     r9, [rbp+var_18]
0x180021f83  mov     [rsp+58h+var_28], rax
0x180021f88  xor     r8d, r8d
0x180021f8b  mov     dword ptr [rsp+58h+var_30], esi
0x180021f8f  xor     edx, edx
0x180021f91  mov     [rsp+58h+var_38], rsi
0x180021f96  mov     [rbp+var_14], esi
0x180021f99  call    cs:__imp_NCryptEncapsulate
0x180021f9f  mov     ebx, eax
0x180021fa1  test    eax, eax
0x180021fa3  jns     short loc_180021FB2
0x180021fa5  mov     r9d, 286h
0x180021fab  mov     ecx, eax
0x180021fad  jmp     loc_180022137
0x180021fb2  mov     ecx, [rbp+var_18]
0x180021fb5  call    SafeAllocaAllocateFromHeap
0x180021fba  mov     rdi, rax
0x180021fbd  test    rax, rax
0x180021fc0  jnz     short loc_180021FD7
0x180021fc2  mov     r9d, 28Eh
0x180021fc8  mov     ebx, 8009000Eh
0x180021fcd  mov     ecx, 8009000Eh
0x180021fd2  jmp     loc_180022137
0x180021fd7  mov     ecx, [rbp+var_14]
0x180021fda  call    SafeAllocaAllocateFromHeap
0x180021fdf  mov     rsi, rax
0x180021fe2  test    rax, rax
0x180021fe5  jnz     short loc_180021FFC
0x180021fe7  mov     ebx, 8009000Eh
0x180021fec  mov     r9d, 296h
0x180021ff2  mov     ecx, 8009000Eh
0x180021ff7  jmp     loc_1800220F5
0x180021ffc  mov     r8d, [rbp+var_18]
0x180022000  lea     rax, [rbp+var_14]
0x180022004  mov     rcx, [r15+18h]
0x180022008  lea     r9, [rbp+var_18]
0x18002200c  mov     [rsp+58h+var_20], 0
0x180022014  mov     rdx, rdi
0x180022017  mov     [rsp+58h+var_28], rax
0x18002201c  mov     eax, [rbp+var_14]
0x18002201f  mov     dword ptr [rsp+58h+var_30], eax
0x180022023  mov     [rsp+58h+var_38], rsi
0x180022028  call    cs:__imp_NCryptEncapsulate
0x18002202e  mov     ebx, eax
0x180022030  test    eax, eax
0x180022032  jns     short loc_18002203F
0x180022034  mov     r9d, 2A5h
0x18002203a  jmp     loc_1800220F3
0x18002203f  mov     eax, [rbp+var_14]
0x180022042  mov     [r14+28h], eax
0x180022046  mov     [r14+20h], rsi
0x18002204a  mov     eax, [rbp+var_18]
0x18002204d  mov     [r12], eax
0x180022051  mov     [r13+0], rdi
0x180022055  jmp     loc_18002214A
0x18002205a  mov     rdx, [rax+20h]
0x18002205e  test    rdx, rdx
0x180022061  jz      loc_18002211F
0x180022067  mov     r8d, [rax+28h]
0x18002206b  test    r8d, r8d
0x18002206e  jz      loc_18002211F
0x180022074  lea     rax, [rbp+var_18]
0x180022078  mov     dword ptr [rsp+58h+var_28], esi
0x18002207c  mov     [rsp+58h+var_30], rax
0x180022081  xor     r9d, r9d
0x180022084  mov     dword ptr [rsp+58h+var_38], esi
0x180022088  call    cs:__imp_NCryptDecapsulate
0x18002208e  mov     ebx, eax
0x180022090  test    eax, eax
0x180022092  jns     short loc_18002209F
0x180022094  mov     r9d, 2C2h
0x18002209a  jmp     loc_180021FAB
0x18002209f  mov     ecx, [rbp+var_18]
0x1800220a2  call    SafeAllocaAllocateFromHeap
0x1800220a7  mov     rdi, rax
0x1800220aa  test    rax, rax
0x1800220ad  jnz     short loc_1800220BA
0x1800220af  mov     r9d, 2CAh
0x1800220b5  jmp     loc_180021FC8
0x1800220ba  mov     r8d, [r15+28h]
0x1800220be  lea     rax, [rbp+var_18]
0x1800220c2  mov     rdx, [r15+20h]
0x1800220c6  mov     r9, rdi
0x1800220c9  mov     rcx, [r14+18h]
0x1800220cd  mov     dword ptr [rsp+58h+var_28], esi
0x1800220d1  mov     [rsp+58h+var_30], rax
0x1800220d6  mov     eax, [rbp+var_18]
0x1800220d9  mov     dword ptr [rsp+58h+var_38], eax
0x1800220dd  call    cs:__imp_NCryptDecapsulate
0x1800220e3  mov     ebx, eax
0x1800220e5  test    eax, eax
0x1800220e7  jns     loc_18002204A
0x1800220ed  mov     r9d, 2D8h
0x1800220f3  mov     ecx, eax
0x1800220f5  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800220fc  lea     rdx, aStatus_0; "status"
0x180022103  call    DebugTraceError
0x180022108  mov     rcx, rdi
0x18002210b  call    MSCryptFree
0x180022110  test    rsi, rsi
0x180022113  jz      short loc_18002214A
0x180022115  mov     rcx, rsi
0x180022118  call    MSCryptFree
0x18002211d  jmp     short loc_18002214A
0x18002211f  mov     r9d, 2B4h
0x180022125  jmp     short loc_18002212D
0x180022127  mov     r9d, 26Ch
0x18002212d  mov     ecx, 80090027h
0x180022132  mov     ebx, 80090027h
0x180022137  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002213e  lea     rdx, aStatus_0; "status"
0x180022145  call    DebugTraceError
0x18002214a  mov     eax, ebx
0x18002214c  add     rsp, 58h
0x180022150  pop     r15
0x180022152  pop     r14
0x180022154  pop     r13
0x180022156  pop     r12
0x180022158  pop     rdi
0x180022159  pop     rsi
0x18002215a  pop     rbx
0x18002215b  pop     rbp
0x18002215c  retn
```
