# I_StreamOpenProtectedMessage

- ea: `0x18000260c`
- end: `0x180002787`
- name: `I_StreamOpenProtectedMessage`
- size: `379`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002790`

## callees

- `0x18000260c`
- `0x1800053ac`
- `0x180005f90`
- `0x180007ae0`
- `0x18000e120`
- `0x1800122c4`
- `0x180020010`

## string_xrefs

- `0x180002667`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x1800026b5`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x180002708`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`

## pseudocode

```c
__int64 __fastcall I_StreamOpenProtectedMessage(__int64 a1, __int64 a2, int a3)
{
  unsigned int v3; // edx
  __int64 v6; // rcx
  _BYTE *v7; // r15
  unsigned int v8; // r14d
  unsigned int ProtectionDescriptor; // eax
  unsigned int v10; // esi
  __int64 v11; // rdi
  unsigned int v12; // eax
  int v13; // edx
  unsigned int ContentEncryptKey; // eax
  _BYTE *v15; // rcx
  __int64 v16; // rdx
  _BYTE *v17; // rax
  __int64 v19; // [rsp+70h] [rbp+40h] BYREF
  __int64 v20; // [rsp+78h] [rbp+48h] BYREF
  _BYTE *v21; // [rsp+88h] [rbp+58h] BYREF

  v20 = a2;
  v3 = *(_DWORD *)(a1 + 156);
  v19 = 0;
  v6 = *(_QWORD *)(a1 + 144);
  v7 = 0;
  v8 = 0;
  v21 = 0;
  LODWORD(v20) = 0;
  ProtectionDescriptor = I_GetProtectionDescriptor(v6, v3, (__int64)&NCryptDefaultAllocPara, &v19);
  v10 = ProtectionDescriptor;
  if ( ProtectionDescriptor )
  {
    DebugTraceError(
      ProtectionDescriptor,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
      1757);
    v11 = v19;
    goto LABEL_15;
  }
  v11 = v19;
  if ( *(_DWORD *)(a1 + 32) )
  {
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int))(a1 + 16))(
            *(_QWORD *)(a1 + 24),
            0,
            0,
            v19,
            a3);
    v10 = v12;
    if ( v12 )
    {
      DebugTraceError(
        v12,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        1776);
      goto LABEL_15;
    }
  }
  v13 = *(_DWORD *)(a1 + 64);
  if ( (v13 & 1) == 0 )
  {
    ContentEncryptKey = I_GetContentEncryptKey(
                          v11,
                          v13,
                          (unsigned int)&NCryptDefaultAllocPara,
                          *(_QWORD *)(a1 + 56),
                          (__int64)&v21,
                          (__int64)&v20);
    v10 = ContentEncryptKey;
    if ( ContentEncryptKey )
    {
      DebugTraceError(
        ContentEncryptKey,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        1792);
      v15 = v21;
      v8 = v20;
      goto LABEL_11;
    }
    v7 = v21;
    v8 = v20;
  }
  *(_QWORD *)(a1 + 136) = v11;
  v11 = 0;
  v15 = 0;
  *(_QWORD *)(a1 + 176) = v7;
  *(_DWORD *)(a1 + 184) = v8;
LABEL_11:
  if ( v15 )
  {
    v16 = v8;
    v17 = v15;
    if ( v8 )
    {
      do
      {
        *v17++ = 0;
        --v16;
      }
      while ( v16 );
    }
    I_DefaultExtrenalFree(v15);
  }
LABEL_15:
  if ( v11 )
    NCryptCloseProtectionDescriptor(v11);
  return v10;
}

```

## disassembly

```asm
0x18000260c  mov     [rsp-38h+arg_8], rdx
0x180002611  push    rbp
0x180002612  push    rbx
0x180002613  push    rsi
0x180002614  push    rdi
0x180002615  push    r12
0x180002617  push    r14
0x180002619  push    r15
0x18000261b  mov     rbp, rsp
0x18000261e  sub     rsp, 30h
0x180002622  mov     edx, [rcx+9Ch]
0x180002628  lea     r9, [rbp+arg_0]
0x18000262c  mov     r12d, r8d
0x18000262f  mov     [rbp+arg_0], 0
0x180002637  mov     rbx, rcx
0x18000263a  lea     r8, NCryptDefaultAllocPara
0x180002641  mov     rcx, [rcx+90h]
0x180002648  xor     r15d, r15d
0x18000264b  xor     r14d, r14d
0x18000264e  mov     [rbp+arg_18], r15
0x180002652  mov     dword ptr [rbp+arg_8], r14d
0x180002656  call    I_GetProtectionDescriptor
0x18000265b  mov     esi, eax
0x18000265d  test    eax, eax
0x18000265f  jz      short loc_180002685
0x180002661  mov     r9d, 6DDh
0x180002667  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000266e  lea     rdx, aStatus; "Status"
0x180002675  mov     ecx, eax
0x180002677  call    DebugTraceError
0x18000267c  mov     rdi, [rbp+arg_0]
0x180002680  jmp     loc_180002769
0x180002685  mov     rdi, [rbp+arg_0]
0x180002689  cmp     [rbx+20h], r14d
0x18000268d  jz      short loc_1800026CF
0x18000268f  mov     rcx, [rbx+18h]
0x180002693  mov     r9, rdi
0x180002696  mov     rax, [rbx+10h]
0x18000269a  xor     r8d, r8d
0x18000269d  xor     edx, edx
0x18000269f  mov     dword ptr [rsp+30h+var_10], r12d
0x1800026a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026a9  mov     esi, eax
0x1800026ab  test    eax, eax
0x1800026ad  jz      short loc_1800026CF
0x1800026af  mov     r9d, 6F0h
0x1800026b5  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800026bc  lea     rdx, aStatus; "Status"
0x1800026c3  mov     ecx, eax
0x1800026c5  call    DebugTraceError
0x1800026ca  jmp     loc_180002769
0x1800026cf  mov     edx, [rbx+40h]
0x1800026d2  test    dl, 1
0x1800026d5  jnz     short loc_18000272F
0x1800026d7  mov     r9, [rbx+38h]
0x1800026db  lea     rax, [rbp+arg_8]
0x1800026df  mov     [rsp+30h+var_8], rax
0x1800026e4  lea     r8, NCryptDefaultAllocPara
0x1800026eb  lea     rax, [rbp+arg_18]
0x1800026ef  mov     rcx, rdi
0x1800026f2  mov     [rsp+30h+var_10], rax
0x1800026f7  call    I_GetContentEncryptKey
0x1800026fc  mov     esi, eax
0x1800026fe  test    eax, eax
0x180002700  jz      short loc_180002727
0x180002702  mov     r9d, 700h
0x180002708  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000270f  lea     rdx, aStatus; "Status"
0x180002716  mov     ecx, eax
0x180002718  call    DebugTraceError
0x18000271d  mov     rcx, [rbp+arg_18]
0x180002721  mov     r14d, dword ptr [rbp+arg_8]
0x180002725  jmp     short loc_180002748
0x180002727  mov     r15, [rbp+arg_18]
0x18000272b  mov     r14d, dword ptr [rbp+arg_8]
0x18000272f  mov     [rbx+88h], rdi
0x180002736  xor     edi, edi
0x180002738  xor     ecx, ecx; hMem
0x18000273a  mov     [rbx+0B0h], r15
0x180002741  mov     [rbx+0B8h], r14d
0x180002748  test    rcx, rcx
0x18000274b  jz      short loc_180002769
0x18000274d  mov     edx, r14d
0x180002750  mov     rax, rcx
0x180002753  test    r14d, r14d
0x180002756  jz      short loc_180002764
0x180002758  mov     byte ptr [rax], 0
0x18000275b  inc     rax
0x18000275e  sub     rdx, 1
0x180002762  jnz     short loc_180002758
0x180002764  call    I_DefaultExtrenalFree
0x180002769  test    rdi, rdi
0x18000276c  jz      short loc_180002776
0x18000276e  mov     rcx, rdi
0x180002771  call    NCryptCloseProtectionDescriptor
0x180002776  mov     eax, esi
0x180002778  add     rsp, 30h
0x18000277c  pop     r15
0x18000277e  pop     r14
0x180002780  pop     r12
0x180002782  pop     rdi
0x180002783  pop     rsi
0x180002784  pop     rbx
0x180002785  pop     rbp
0x180002786  retn
```
