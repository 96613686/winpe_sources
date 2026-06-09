# Accessor_SIDArray

- ea: `0x18001ec50`
- end: `0x18001ed87`
- name: `Accessor_SIDArray`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001ec50`
- `0x18001f170`
- `0x180020104`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001ed36`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18001ed36`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ed46`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ed46`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001ece3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001ece3`

## pseudocode

```c
__int64 __fastcall Accessor_SIDArray(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  unsigned __int64 VariableNumber; // rbx
  char *v9; // rbp
  __int64 v10; // rax
  _WORD *v12; // rdi
  __int64 v13; // rsi
  LPWSTR v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  _WORD *v17; // rax
  LPWSTR v18; // rcx
  _WORD *v19; // rdx
  LPWSTR StringSid; // [rsp+58h] [rbp+10h] BYREF

  VariableNumber = *(_QWORD *)(a2 + 56);
  v9 = (char *)(*(__int64 (**)(void))a2)();
  if ( v9 )
  {
    if ( *(_QWORD *)(a2 + 32) )
      VariableNumber = GetVariableNumber(a1);
    v10 = AllocEntry_New(a1, 378 * VariableNumber);
    *(_QWORD *)a3 = v10;
    *(_DWORD *)(a3 + 8) = VariableNumber;
    if ( !v10 )
      return 27;
    v12 = (_WORD *)(v10 + 8 * VariableNumber);
    v13 = 0;
    if ( !VariableNumber )
    {
LABEL_15:
      *a4 = 0;
      return 0;
    }
    while ( 1 )
    {
      StringSid = 0;
      if ( !ConvertSidToStringSidW(v9, &StringSid) )
        break;
      v14 = StringSid;
      v15 = 2147483646;
      v16 = 185;
      v17 = v12;
      do
      {
        if ( !v15 )
          break;
        if ( !*v14 )
          break;
        *v17++ = *v14++;
        --v15;
        --v16;
      }
      while ( v16 );
      v18 = StringSid;
      v19 = v17 - 1;
      if ( v16 )
        v19 = v17;
      *v19 = 0;
      LocalFree(v18);
      *(_QWORD *)(*(_QWORD *)a3 + 8 * v13) = v12;
      v12 += 185;
      v9 += GetLengthSid(v9);
      if ( ++v13 >= VariableNumber )
        goto LABEL_15;
    }
  }
  return 13;
}

```

## disassembly

```asm
0x18001ec50  mov     [rsp+arg_0], rbx
0x18001ec55  mov     [rsp+arg_10], rbp
0x18001ec5a  push    rsi
0x18001ec5b  push    rdi
0x18001ec5c  push    r12
0x18001ec5e  push    r14
0x18001ec60  push    r15
0x18001ec62  sub     rsp, 20h
0x18001ec66  mov     rax, [rdx]
0x18001ec69  mov     r15, r9
0x18001ec6c  mov     rbx, [rdx+38h]
0x18001ec70  mov     r14, r8
0x18001ec73  mov     rdi, rdx
0x18001ec76  mov     rsi, rcx
0x18001ec79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec7e  xor     r12d, r12d
0x18001ec81  mov     rbp, rax
0x18001ec84  test    rax, rax
0x18001ec87  jz      loc_18001ED6B
0x18001ec8d  mov     rdx, [rdi+20h]
0x18001ec91  test    rdx, rdx
0x18001ec94  jz      short loc_18001ECA1
0x18001ec96  mov     rcx, rsi
0x18001ec99  call    GetVariableNumber
0x18001ec9e  mov     rbx, rax
0x18001eca1  imul    rdx, rbx, 17Ah
0x18001eca8  mov     rcx, rsi
0x18001ecab  call    AllocEntry_New
0x18001ecb0  mov     [r14], rax
0x18001ecb3  mov     [r14+8], ebx
0x18001ecb7  test    rax, rax
0x18001ecba  jnz     short loc_18001ECC6
0x18001ecbc  mov     eax, 1Bh
0x18001ecc1  jmp     loc_18001ED70
0x18001ecc6  lea     rdi, [rax+rbx*8]
0x18001ecca  mov     rsi, r12
0x18001eccd  test    rbx, rbx
0x18001ecd0  jz      loc_18001ED64
0x18001ecd6  lea     rdx, [rsp+48h+StringSid]; StringSid
0x18001ecdb  mov     [rsp+48h+StringSid], r12
0x18001ece0  mov     rcx, rbp; Sid
0x18001ece3  call    cs:__imp_ConvertSidToStringSidW
0x18001ece9  test    eax, eax
0x18001eceb  jz      short loc_18001ED6B
0x18001eced  mov     r9, [rsp+48h+StringSid]
0x18001ecf2  mov     edx, 7FFFFFFEh
0x18001ecf7  mov     r8d, 0B9h
0x18001ecfd  mov     rax, rdi
0x18001ed00  test    rdx, rdx
0x18001ed03  jz      short loc_18001ED22
0x18001ed05  movzx   ecx, word ptr [r9]
0x18001ed09  test    cx, cx
0x18001ed0c  jz      short loc_18001ED22
0x18001ed0e  mov     [rax], cx
0x18001ed11  add     r9, 2
0x18001ed15  add     rax, 2
0x18001ed19  dec     rdx
0x18001ed1c  sub     r8, 1
0x18001ed20  jnz     short loc_18001ED00
0x18001ed22  mov     rcx, [rsp+48h+StringSid]; hMem
0x18001ed27  lea     rdx, [rax-2]
0x18001ed2b  test    r8, r8
0x18001ed2e  cmovnz  rdx, rax
0x18001ed32  mov     [rdx], r12w
0x18001ed36  call    cs:__imp_LocalFree
0x18001ed3c  mov     rax, [r14]
0x18001ed3f  mov     rcx, rbp; pSid
0x18001ed42  mov     [rax+rsi*8], rdi
0x18001ed46  call    cs:__imp_GetLengthSid
0x18001ed4c  mov     eax, eax
0x18001ed4e  add     rdi, 172h
0x18001ed55  add     rbp, rax
0x18001ed58  inc     rsi
0x18001ed5b  cmp     rsi, rbx
0x18001ed5e  jb      loc_18001ECD6
0x18001ed64  mov     [r15], r12d
0x18001ed67  xor     eax, eax
0x18001ed69  jmp     short loc_18001ED70
0x18001ed6b  mov     eax, 0Dh
0x18001ed70  mov     rbx, [rsp+48h+arg_0]
0x18001ed75  mov     rbp, [rsp+48h+arg_10]
0x18001ed7a  add     rsp, 20h
0x18001ed7e  pop     r15
0x18001ed80  pop     r14
0x18001ed82  pop     r12
0x18001ed84  pop     rdi
0x18001ed85  pop     rsi
0x18001ed86  retn
```
