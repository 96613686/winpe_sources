# SslpImportKemCipherText

- ea: `0x1800222f0`
- end: `0x180022419`
- name: `SslpImportKemCipherText`
- size: `297`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800234b0`

## callees

- `0x180007940`
- `0x18000b654`
- `0x180021a74`
- `0x180022164`
- `0x1800222f0`
- `0x180024fb0`

## string_xrefs

- `0x180022395`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`
- `0x1800223e7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`

## pseudocode

```c
__int64 __fastcall SslpImportKemCipherText(__int64 a1, unsigned int a2, __int64 *a3)
{
  __int64 v5; // r9
  size_t v6; // rsi
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // r9
  void *v11; // rax
  void *v12; // rbp
  __int64 v13; // rax
  __int64 v15; // [rsp+40h] [rbp+8h] BYREF

  v15 = 0;
  if ( !a1 || !a3 )
  {
    v5 = 529;
    goto LABEL_16;
  }
  if ( a2 < 0xC )
  {
    v5 = 536;
LABEL_16:
    v8 = -2146893819;
    DebugTraceError(2148073477LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", v5);
    return v8;
  }
  if ( *(_DWORD *)a1 != 1129008205 || (v6 = *(unsigned int *)(a1 + 8), a2 < v6 + 12) )
  {
    v5 = 547;
    goto LABEL_16;
  }
  v7 = SslpCreateBaseKemKeyStruct(v6 + 12, *(_WORD *)(a1 + 4), 458753, &v15);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v11 = (void *)SafeAllocaAllocateFromHeap(v6);
    v12 = v11;
    if ( v11 )
    {
      memmove(v11, (const void *)(a1 + 12), v6);
      v13 = v15;
      *(_QWORD *)(v15 + 32) = v12;
      *(_DWORD *)(v13 + 40) = v6;
      *a3 = v13;
      return v8;
    }
    v8 = -2146893810;
    v9 = 2148073486LL;
    v10 = 570;
  }
  else
  {
    v9 = (unsigned int)v7;
    v10 = 562;
  }
  DebugTraceError(v9, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", v10);
  if ( v15 )
    SslpFreeKemKey(v15);
  return v8;
}

```

## disassembly

```asm
0x1800222f0  mov     [rsp+arg_8], rbx
0x1800222f5  mov     [rsp+arg_10], rbp
0x1800222fa  push    rsi
0x1800222fb  push    rdi
0x1800222fc  push    r14
0x1800222fe  sub     rsp, 20h
0x180022302  mov     [rsp+38h+arg_0], 0
0x18002230b  mov     r14, r8
0x18002230e  mov     rdi, rcx
0x180022311  test    rcx, rcx
0x180022314  jz      loc_1800223E1
0x18002231a  test    r8, r8
0x18002231d  jz      loc_1800223E1
0x180022323  cmp     edx, 0Ch
0x180022326  jnb     short loc_180022333
0x180022328  mov     r9d, 218h
0x18002232e  jmp     loc_1800223E7
0x180022333  cmp     dword ptr [rcx], 434B4C4Dh
0x180022339  jnz     loc_1800223D9
0x18002233f  mov     esi, [rcx+8]
0x180022342  mov     eax, edx
0x180022344  lea     rcx, [rsi+0Ch]
0x180022348  cmp     rax, rcx
0x18002234b  jb      loc_1800223D9
0x180022351  movzx   edx, word ptr [rdi+4]
0x180022355  lea     r9, [rsp+38h+arg_0]
0x18002235a  mov     r8d, 70001h
0x180022360  call    SslpCreateBaseKemKeyStruct
0x180022365  mov     ebx, eax
0x180022367  test    eax, eax
0x180022369  jns     short loc_180022375
0x18002236b  mov     ecx, eax
0x18002236d  mov     r9d, 232h
0x180022373  jmp     short loc_180022395
0x180022375  mov     rcx, rsi
0x180022378  call    SafeAllocaAllocateFromHeap
0x18002237d  mov     rbp, rax
0x180022380  test    rax, rax
0x180022383  jnz     short loc_1800223B9
0x180022385  mov     ebx, 8009000Eh
0x18002238a  mov     ecx, 8009000Eh
0x18002238f  mov     r9d, 23Ah
0x180022395  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002239c  lea     rdx, aStatus_0; "status"
0x1800223a3  call    DebugTraceError
0x1800223a8  mov     rcx, [rsp+38h+arg_0]
0x1800223ad  test    rcx, rcx
0x1800223b0  jz      short loc_180022404
0x1800223b2  call    SslpFreeKemKey
0x1800223b7  jmp     short loc_180022404
0x1800223b9  lea     rdx, [rdi+0Ch]; Src
0x1800223bd  mov     r8, rsi; Size
0x1800223c0  mov     rcx, rbp; void *
0x1800223c3  call    memmove
0x1800223c8  mov     rax, [rsp+38h+arg_0]
0x1800223cd  mov     [rax+20h], rbp
0x1800223d1  mov     [rax+28h], esi
0x1800223d4  mov     [r14], rax
0x1800223d7  jmp     short loc_180022404
0x1800223d9  mov     r9d, 223h
0x1800223df  jmp     short loc_1800223E7
0x1800223e1  mov     r9d, 211h
0x1800223e7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800223ee  mov     ecx, 80090005h
0x1800223f3  lea     rdx, aStatus_0; "status"
0x1800223fa  mov     ebx, 80090005h
0x1800223ff  call    DebugTraceError
0x180022404  mov     rbp, [rsp+38h+arg_10]
0x180022409  mov     eax, ebx
0x18002240b  mov     rbx, [rsp+38h+arg_8]
0x180022410  add     rsp, 20h
0x180022414  pop     r14
0x180022416  pop     rdi
0x180022417  pop     rsi
0x180022418  retn
```
