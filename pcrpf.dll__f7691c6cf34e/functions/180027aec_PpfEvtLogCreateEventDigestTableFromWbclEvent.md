# PpfEvtLogCreateEventDigestTableFromWbclEvent

- ea: `0x180027aec`
- end: `0x180027ea9`
- name: `PpfEvtLogCreateEventDigestTableFromWbclEvent`
- size: `957`
- prototype: `__int64 __fastcall(struct _WBCL_Iterator *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180027eb0`

## callees

- `0x180027aec`
- `0x1800290f4`
- `0x18002919c`
- `0x180054ec0`
- `0x18005559c`
- `0x1800570b0`
- `0x180059010`

## string_xrefs

- `0x180027c02`: `PpfEvtLogCreateEventDigestTableFromWbclEvent`
- `0x180027cf6`: `PpfEvtLogCreateEventDigestTableFromWbclEvent`
- `0x180027e4c`: `PpfEvtLogCreateEventDigestTableFromWbclEvent`

## pseudocode

```c
__int64 __fastcall PpfEvtLogCreateEventDigestTableFromWbclEvent(
        struct _WBCL_Iterator *a1,
        _QWORD *a2,
        unsigned int *a3)
{
  unsigned __int16 v3; // r15
  _QWORD *v5; // r13
  int Size; // esi
  unsigned int v7; // ebp
  unsigned __int16 v8; // bx
  __int64 v9; // r9
  int v10; // r9d
  int v11; // edx
  _WORD *v12; // r12
  __int64 v13; // rax
  __int64 v14; // r8
  char v15; // bl
  unsigned __int8 *CurrentElementDigest; // r14
  unsigned __int16 v17; // bx
  size_t v18; // r8
  int v19; // r9d
  unsigned int v20; // r14d
  int v21; // edx
  unsigned __int16 v22; // r15
  char *v23; // rbx
  __int64 v24; // r9
  __int64 v25; // r13
  size_t v26; // r8
  char *v27; // rbx
  unsigned __int8 *Src; // [rsp+40h] [rbp-58h]
  unsigned __int16 v30; // [rsp+A0h] [rbp+8h] BYREF
  _QWORD *v31; // [rsp+A8h] [rbp+10h]
  unsigned int *v32; // [rsp+B0h] [rbp+18h]
  unsigned __int16 v33; // [rsp+B8h] [rbp+20h]

  v32 = a3;
  v31 = a2;
  v3 = WORD1(a1[1].firstElementPtr);
  v30 = 0;
  v33 = v3;
  v5 = a2;
  if ( a1->logFormat == 1 )
  {
    Size = PpfEvtLogValidateDigestAlgIDAndGetSize(v3, &v30);
    if ( Size < 0 )
      return (unsigned int)Size;
    v7 = v30 + 2;
  }
  else
  {
    Size = 0;
    v7 = 0;
    v8 = 0;
    v9 = 1;
    do
    {
      if ( (c_PpfAlgorithmIdToBitmapTable[v8] & *(_DWORD *)&a1->hashAlgorithm) != 0
        && (int)WbclApiSetPreferredHashAlgID(v8, a1, a3, v9) >= 0
        && a1->currentElementPtr
        && a1->currentElementSize )
      {
        if ( WbclGetCurrentElementDigest(a1) )
        {
          Size = PpfEvtLogValidateDigestAlgIDAndGetSize(v8, &v30);
          if ( Size < 0 )
            return (unsigned int)Size;
          v7 += v30 + 2;
        }
        v9 = 1;
      }
      v8 += v9;
    }
    while ( v8 < 0x2Au );
    if ( (unsigned int)WbclApiSetPreferredHashAlgID(v3, a1, a3, v9) )
    {
      v11 = 1546;
LABEL_16:
      Size = -1073741595;
      PpfEvtLogTraceHelper(
        (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
        v11,
        (int)"PpfEvtLogCreateEventDigestTableFromWbclEvent",
        v10,
        "Error: 0x%x",
        229);
      return (unsigned int)Size;
    }
  }
  if ( !v5 )
  {
LABEL_52:
    *v32 = v7;
    return (unsigned int)Size;
  }
  v12 = 0;
  if ( !v7 )
  {
LABEL_51:
    *v5 = v12;
    goto LABEL_52;
  }
  if ( !AllocFn )
  {
    v10 = 1;
    v11 = 1553;
    goto LABEL_16;
  }
  v13 = AllocFn(v7);
  v12 = (_WORD *)v13;
  if ( !v13 )
  {
    Size = -1073741801;
    PpfEvtLogTraceHelper(
      (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
      1558,
      (int)"PpfEvtLogCreateEventDigestTableFromWbclEvent",
      1,
      "Error: 0x%x",
      23);
    return (unsigned int)Size;
  }
  if ( a1->logFormat != 1 )
  {
    v22 = 0;
    v23 = (char *)v13;
    v20 = v7;
    v24 = 1;
    do
    {
      if ( (c_PpfAlgorithmIdToBitmapTable[v22] & *(_DWORD *)&a1->hashAlgorithm) != 0
        && (int)WbclApiSetPreferredHashAlgID(v22, a1, v14, v24) >= 0
        && a1->currentElementPtr
        && a1->currentElementSize )
      {
        Src = WbclGetCurrentElementDigest(a1);
        if ( Src )
        {
          Size = PpfEvtLogValidateDigestAlgIDAndGetSize(v22, &v30);
          if ( Size < 0 )
            goto LABEL_49;
          v25 = v30;
          if ( v20 < (unsigned __int64)v30 + 2 )
          {
            v19 = 1;
            v21 = 1605;
            goto LABEL_48;
          }
          v26 = v30;
          *(_WORD *)v23 = v22;
          v27 = v23 + 2;
          memcpy_0(v27, Src, v26);
          v23 = &v27[v25];
          v20 += -2 - v30;
        }
        v24 = 1;
      }
      v22 += v24;
    }
    while ( v22 < 0x2Au );
    if ( (unsigned int)WbclApiSetPreferredHashAlgID(v33, a1, v14, v24) )
    {
      v21 = 1626;
      goto LABEL_48;
    }
    v5 = v31;
    goto LABEL_46;
  }
  if ( a1->currentElementPtr && a1->currentElementSize )
  {
    v15 = 0;
    CurrentElementDigest = WbclGetCurrentElementDigest(a1);
    if ( CurrentElementDigest )
    {
      v17 = WORD1(a1[1].firstElementPtr);
      Size = PpfEvtLogValidateDigestAlgIDAndGetSize(v17, &v30);
      if ( Size < 0 )
        goto LABEL_49;
      v18 = v30;
      *v12 = v17;
      memcpy_0(v12 + 1, CurrentElementDigest, v18);
      v19 = 1;
      v20 = v7 - v30 - 2;
LABEL_46:
      if ( v20 )
      {
        v21 = 1636;
        goto LABEL_48;
      }
      goto LABEL_51;
    }
  }
  else
  {
    v15 = 87;
  }
  PpfEvtLogTraceHelper(
    (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
    1570,
    (int)"PpfEvtLogCreateEventDigestTableFromWbclEvent",
    1,
    "Failed to get TCG log ver 1.2 digest from Wbcl, hr = 0x%x, Digest is null: %u",
    v15);
  v19 = 1;
  v21 = 1571;
LABEL_48:
  Size = -1073741595;
  PpfEvtLogTraceHelper(
    (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
    v21,
    (int)"PpfEvtLogCreateEventDigestTableFromWbclEvent",
    v19,
    "Error: 0x%x",
    229);
LABEL_49:
  if ( FreeFn )
    FreeFn(v12);
  return (unsigned int)Size;
}

```

## disassembly

```asm
0x180027aec  mov     r11, rsp
0x180027aef  mov     [r11+18h], r8
0x180027af3  mov     [r11+10h], rdx
0x180027af7  push    rbx
0x180027af8  push    rbp
0x180027af9  push    rsi
0x180027afa  push    rdi
0x180027afb  push    r12
0x180027afd  push    r13
0x180027aff  push    r14
0x180027b01  push    r15
0x180027b03  sub     rsp, 58h
0x180027b07  movzx   r15d, word ptr [rcx+2Ch]
0x180027b0c  xor     eax, eax
0x180027b0e  mov     rdi, rcx
0x180027b11  mov     [r11+8], ax
0x180027b16  xor     r14d, r14d
0x180027b19  mov     [rsp+98h+arg_18], r15w
0x180027b22  mov     r13, rdx
0x180027b25  lea     rcx, c_PpfAlgorithmIdToBitmapTable
0x180027b2c  lea     ebx, [rax+1]
0x180027b2f  cmp     [rdi+1Ah], bx
0x180027b33  jnz     short loc_180027B5C
0x180027b35  lea     rdx, [r11+8]
0x180027b39  movzx   ecx, r15w
0x180027b3d  call    PpfEvtLogValidateDigestAlgIDAndGetSize
0x180027b42  mov     esi, eax
0x180027b44  test    eax, eax
0x180027b46  js      loc_180027E95
0x180027b4c  movzx   ebp, [rsp+98h+arg_0]
0x180027b54  add     ebp, 2
0x180027b57  jmp     loc_180027C24
0x180027b5c  xor     esi, esi
0x180027b5e  xor     ebp, ebp
0x180027b60  xor     ebx, ebx
0x180027b62  lea     r9d, [rsi+1]
0x180027b66  movzx   eax, bx
0x180027b69  mov     eax, [rcx+rax*4]
0x180027b6c  test    [rdi+28h], eax
0x180027b6f  jz      short loc_180027BD1
0x180027b71  mov     rdx, rdi
0x180027b74  movzx   ecx, bx
0x180027b77  call    WbclApiSetPreferredHashAlgID
0x180027b7c  test    eax, eax
0x180027b7e  js      short loc_180027BCA
0x180027b80  cmp     qword ptr [rdi+0Ch], 0
0x180027b85  jz      short loc_180027BCA
0x180027b87  cmp     dword ptr [rdi+14h], 0
0x180027b8b  jz      short loc_180027BCA
0x180027b8d  mov     rcx, rdi; struct _WBCL_Iterator *
0x180027b90  call    ?WbclGetCurrentElementDigest@@YAPEAEPEAU_WBCL_Iterator@@@Z; WbclGetCurrentElementDigest(_WBCL_Iterator *)
0x180027b95  mov     r14, rax
0x180027b98  test    rax, rax
0x180027b9b  jz      short loc_180027BC4
0x180027b9d  lea     rdx, [rsp+98h+arg_0]
0x180027ba5  movzx   ecx, bx
0x180027ba8  call    PpfEvtLogValidateDigestAlgIDAndGetSize
0x180027bad  mov     esi, eax
0x180027baf  test    eax, eax
0x180027bb1  js      loc_180027E95
0x180027bb7  movzx   ecx, [rsp+98h+arg_0]
0x180027bbf  add     ecx, 2
0x180027bc2  add     ebp, ecx
0x180027bc4  mov     r9d, 1
0x180027bca  lea     rcx, c_PpfAlgorithmIdToBitmapTable
0x180027bd1  add     bx, r9w
0x180027bd5  cmp     bx, 2Ah ; '*'
0x180027bd9  jb      short loc_180027B66
0x180027bdb  mov     rdx, rdi
0x180027bde  movzx   ecx, r15w
0x180027be2  call    WbclApiSetPreferredHashAlgID
0x180027be7  test    eax, eax
0x180027be9  jz      short loc_180027C1F
0x180027beb  mov     edx, 60Ah; int
0x180027bf0  mov     eax, 0C00000E5h
0x180027bf5  mov     esi, eax
0x180027bf7  mov     dword ptr [rsp+98h+var_70], eax; char
0x180027bfb  lea     rax, aError0xX; "Error: 0x%x"
0x180027c02  lea     r8, aPpfevtlogcreat_1; "PpfEvtLogCreateEventDigestTableFromWbcl"...
0x180027c09  mov     [rsp+98h+Format], rax; Format
0x180027c0e  lea     rcx, aMinkernelNgscb_1; "minkernel\\ngscb\\ppfevtlog\\ppfevtlog."...
0x180027c15  call    PpfEvtLogTraceHelper
0x180027c1a  jmp     loc_180027E95
0x180027c1f  mov     ebx, 1
0x180027c24  test    r13, r13
0x180027c27  jz      loc_180027E8B
0x180027c2d  xor     r12d, r12d
0x180027c30  test    ebp, ebp
0x180027c32  jz      loc_180027E87
0x180027c38  mov     rax, cs:_AllocFn
0x180027c3f  test    rax, rax
0x180027c42  jnz     short loc_180027C4E
0x180027c44  mov     r9d, ebx
0x180027c47  mov     edx, 611h
0x180027c4c  jmp     short loc_180027BF0
0x180027c4e  mov     ecx, ebp
0x180027c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c55  mov     r12, rax
0x180027c58  test    rax, rax
0x180027c5b  jnz     short loc_180027C70
0x180027c5d  mov     esi, 0C0000017h
0x180027c62  mov     r9d, ebx
0x180027c65  mov     dword ptr [rsp+98h+var_70], esi
0x180027c69  mov     edx, 616h
0x180027c6e  jmp     short loc_180027BFB
0x180027c70  cmp     [rdi+1Ah], bx
0x180027c74  jnz     loc_180027D3D
0x180027c7a  cmp     qword ptr [rdi+0Ch], 0
0x180027c7f  jz      short loc_180027CEF
0x180027c81  cmp     dword ptr [rdi+14h], 0
0x180027c85  jz      short loc_180027CEF
0x180027c87  mov     rcx, rdi; struct _WBCL_Iterator *
0x180027c8a  xor     ebx, ebx
0x180027c8c  call    ?WbclGetCurrentElementDigest@@YAPEAEPEAU_WBCL_Iterator@@@Z; WbclGetCurrentElementDigest(_WBCL_Iterator *)
0x180027c91  mov     r14, rax
0x180027c94  test    rax, rax
0x180027c97  jz      short loc_180027CF4
0x180027c99  movzx   ebx, word ptr [rdi+2Ch]
0x180027c9d  lea     rdx, [rsp+98h+arg_0]
0x180027ca5  movzx   ecx, bx
0x180027ca8  call    PpfEvtLogValidateDigestAlgIDAndGetSize
0x180027cad  mov     esi, eax
0x180027caf  test    eax, eax
0x180027cb1  js      loc_180027E71
0x180027cb7  movzx   r8d, [rsp+98h+arg_0]; Size
0x180027cc0  lea     rcx, [r12+2]; void *
0x180027cc5  mov     rdx, r14; Src
0x180027cc8  mov     [r12], bx
0x180027ccd  call    memcpy_0
0x180027cd2  movzx   eax, [rsp+98h+arg_0]
0x180027cda  mov     r14d, ebp
0x180027cdd  sub     r14d, eax
0x180027ce0  mov     r9d, 1
0x180027ce6  sub     r14d, 2
0x180027cea  jmp     loc_180027E3D
0x180027cef  mov     ebx, 80070057h
0x180027cf4  xor     eax, eax
0x180027cf6  lea     r8, aPpfevtlogcreat_1; "PpfEvtLogCreateEventDigestTableFromWbcl"...
0x180027cfd  test    r14, r14
0x180027d00  lea     rcx, aMinkernelNgscb_1; "minkernel\\ngscb\\ppfevtlog\\ppfevtlog."...
0x180027d07  mov     edx, 622h; int
0x180027d0c  setnz   al
0x180027d0f  mov     [rsp+98h+var_68], eax
0x180027d13  lea     rax, aFailedToGetTcg; "Failed to get TCG log ver 1.2 digest fr"...
0x180027d1a  mov     dword ptr [rsp+98h+var_70], ebx; char
0x180027d1e  mov     ebx, 1
0x180027d23  mov     r9d, ebx; int
0x180027d26  mov     [rsp+98h+Format], rax; Format
0x180027d2b  call    PpfEvtLogTraceHelper
0x180027d30  mov     r9d, ebx
0x180027d33  mov     edx, 623h
0x180027d38  jmp     loc_180027E47
0x180027d3d  xor     r15d, r15d
0x180027d40  lea     rcx, c_PpfAlgorithmIdToBitmapTable
0x180027d47  mov     rbx, r12
0x180027d4a  mov     r14d, ebp
0x180027d4d  lea     r9d, [r15+1]
0x180027d51  movzx   eax, r15w
0x180027d55  mov     eax, [rcx+rax*4]
0x180027d58  test    [rdi+28h], eax
0x180027d5b  jz      loc_180027DFE
0x180027d61  mov     rdx, rdi
0x180027d64  movzx   ecx, r15w
0x180027d68  call    WbclApiSetPreferredHashAlgID
0x180027d6d  test    eax, eax
0x180027d6f  js      loc_180027DF7
0x180027d75  cmp     qword ptr [rdi+0Ch], 0
0x180027d7a  jz      short loc_180027DF7
0x180027d7c  cmp     dword ptr [rdi+14h], 0
0x180027d80  jz      short loc_180027DF7
0x180027d82  mov     rcx, rdi; struct _WBCL_Iterator *
0x180027d85  call    ?WbclGetCurrentElementDigest@@YAPEAEPEAU_WBCL_Iterator@@@Z; WbclGetCurrentElementDigest(_WBCL_Iterator *)
0x180027d8a  mov     [rsp+98h+Src], rax
0x180027d8f  test    rax, rax
0x180027d92  jz      short loc_180027DF1
0x180027d94  lea     rdx, [rsp+98h+arg_0]
0x180027d9c  movzx   ecx, r15w
0x180027da0  call    PpfEvtLogValidateDigestAlgIDAndGetSize
0x180027da5  mov     esi, eax
0x180027da7  test    eax, eax
0x180027da9  js      loc_180027E71
0x180027daf  movzx   r13d, [rsp+98h+arg_0]
0x180027db8  mov     ecx, r14d
0x180027dbb  lea     rdx, [r13+2]
0x180027dbf  cmp     rcx, rdx
0x180027dc2  jb      short loc_180027E28
0x180027dc4  mov     rdx, [rsp+98h+Src]; Src
0x180027dc9  mov     r8d, r13d; Size
0x180027dcc  mov     [rbx], r15w
0x180027dd0  add     rbx, 2
0x180027dd4  mov     rcx, rbx; void *
0x180027dd7  call    memcpy_0
0x180027ddc  movzx   eax, [rsp+98h+arg_0]
0x180027de4  mov     ecx, 0FFFFFFFEh
0x180027de9  sub     ecx, eax
0x180027deb  add     rbx, r13
0x180027dee  add     r14d, ecx
0x180027df1  mov     r9d, 1
0x180027df7  lea     rcx, c_PpfAlgorithmIdToBitmapTable
0x180027dfe  add     r15w, r9w
0x180027e02  cmp     r15w, 2Ah ; '*'
0x180027e07  jb      loc_180027D51
0x180027e0d  movzx   ecx, [rsp+98h+arg_18]
0x180027e15  mov     rdx, rdi
0x180027e18  call    WbclApiSetPreferredHashAlgID
0x180027e1d  test    eax, eax
0x180027e1f  jz      short loc_180027E35
0x180027e21  mov     edx, 65Ah
0x180027e26  jmp     short loc_180027E47
0x180027e28  mov     r9d, 1
0x180027e2e  mov     edx, 645h
0x180027e33  jmp     short loc_180027E47
0x180027e35  mov     r13, [rsp+98h+arg_8]
0x180027e3d  test    r14d, r14d
0x180027e40  jz      short loc_180027E87
0x180027e42  mov     edx, 664h; int
0x180027e47  mov     eax, 0C00000E5h
0x180027e4c  lea     r8, aPpfevtlogcreat_1; "PpfEvtLogCreateEventDigestTableFromWbcl"...
0x180027e53  mov     dword ptr [rsp+98h+var_70], eax; char
0x180027e57  lea     rcx, aMinkernelNgscb_1; "minkernel\\ngscb\\ppfevtlog\\ppfevtlog."...
0x180027e5e  mov     esi, eax
0x180027e60  lea     rax, aError0xX; "Error: 0x%x"
0x180027e67  mov     [rsp+98h+Format], rax; Format
0x180027e6c  call    PpfEvtLogTraceHelper
0x180027e71  mov     rax, cs:_FreeFn
0x180027e78  test    rax, rax
0x180027e7b  jz      short loc_180027E95
0x180027e7d  mov     rcx, r12
0x180027e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e85  jmp     short loc_180027E95
0x180027e87  mov     [r13+0], r12
0x180027e8b  mov     rax, [rsp+98h+arg_10]
0x180027e93  mov     [rax], ebp
0x180027e95  mov     eax, esi
0x180027e97  add     rsp, 58h
0x180027e9b  pop     r15
0x180027e9d  pop     r14
0x180027e9f  pop     r13
0x180027ea1  pop     r12
0x180027ea3  pop     rdi
0x180027ea4  pop     rsi
0x180027ea5  pop     rbp
0x180027ea6  pop     rbx
0x180027ea7  retn
```
