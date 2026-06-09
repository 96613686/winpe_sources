# SymCryptEcurveAllocate

- ea: `0x140003454`
- end: `0x140003577`
- name: `SymCryptEcurveAllocate`
- size: `291`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003598`
- `0x14001b440`
- `0x14001c418`
- `0x14003a798`

## callees

- `0x140003454`
- `0x140004b1c`
- `0x1400203a0`
- `0x14002c2c0`
- `0x140057978`
- `0x14009a3d0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003504`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003540`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003504`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003540`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003515`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003551`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003515`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003551`

## pseudocode

```c
__int64 __fastcall SymCryptEcurveAllocate(__int64 a1)
{
  int v1; // ebp
  __int64 v2; // rsi
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 v6; // rdi
  __int64 v7; // rbx
  _OWORD v9[3]; // [rsp+30h] [rbp-68h] BYREF

  v1 = a1;
  v2 = 0;
  memset(v9, 0, 44);
  if ( (unsigned __int8)SymCryptEcurveValidateAndComputeSizes(a1, v9) )
  {
    v3 = SymCryptCallbackAlloc(HIDWORD(v9[0]));
    if ( v3 )
    {
      v4 = SymCryptCallbackAlloc(DWORD1(v9[2]));
      v5 = v4;
      if ( !v4 )
        goto LABEL_11;
      v2 = SymCryptEcurveInitialize(v1, 0, (unsigned int)v9, v3, v4);
      if ( v2 )
        v3 = 0;
      SymCryptWipeAsm(v5, DWORD1(v9[2]));
      v6 = v5 - *(unsigned int *)(v5 - 4);
      if ( v6 )
      {
        if ( *(_QWORD *)(v6 - 16) )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v6 - 16), (PVOID)(v6 - 16));
        else
          ExFreePoolWithTag((PVOID)(v6 - 16), *(_DWORD *)(v6 - 16 + 8));
      }
      if ( v3 )
      {
LABEL_11:
        v7 = v3 - *(unsigned int *)(v3 - 4);
        if ( v7 )
        {
          if ( *(_QWORD *)(v7 - 16) )
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v7 - 16), (PVOID)(v7 - 16));
          else
            ExFreePoolWithTag((PVOID)(v7 - 16), *(_DWORD *)(v7 - 16 + 8));
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140003454  push    rbx
0x140003456  push    rbp
0x140003457  push    rsi
0x140003458  push    rdi
0x140003459  sub     rsp, 78h
0x14000345d  mov     rax, cs:__security_cookie
0x140003464  xor     rax, rsp
0x140003467  mov     [rsp+98h+var_38], rax
0x14000346c  xorps   xmm0, xmm0
0x14000346f  lea     rdx, [rsp+98h+var_68]
0x140003474  movups  [rsp+98h+var_58], xmm0
0x140003479  mov     rbp, rcx
0x14000347c  xor     esi, esi
0x14000347e  movups  [rsp+98h+var_58+0Ch], xmm0
0x140003483  movups  [rsp+98h+var_68], xmm0
0x140003488  call    SymCryptEcurveValidateAndComputeSizes
0x14000348d  test    al, al
0x14000348f  jz      loc_14000355D
0x140003495  mov     ecx, dword ptr [rsp+98h+var_68+0Ch]
0x140003499  call    SymCryptCallbackAlloc
0x14000349e  mov     rbx, rax
0x1400034a1  test    rax, rax
0x1400034a4  jz      loc_14000355D
0x1400034aa  mov     ecx, [rsp+98h+var_44]
0x1400034ae  call    SymCryptCallbackAlloc
0x1400034b3  mov     rdi, rax
0x1400034b6  test    rax, rax
0x1400034b9  jz      short loc_140003526
0x1400034bb  mov     r9, rbx
0x1400034be  mov     [rsp+98h+var_78], rax
0x1400034c3  lea     r8, [rsp+98h+var_68]
0x1400034c8  xor     edx, edx
0x1400034ca  mov     rcx, rbp
0x1400034cd  call    SymCryptEcurveInitialize
0x1400034d2  xor     ecx, ecx
0x1400034d4  mov     rsi, rax
0x1400034d7  test    rax, rax
0x1400034da  cmovnz  rbx, rcx
0x1400034de  mov     edx, [rsp+98h+var_44]
0x1400034e2  mov     rcx, rdi
0x1400034e5  call    SymCryptWipeAsm
0x1400034ea  mov     ecx, [rdi-4]
0x1400034ed  sub     rdi, rcx
0x1400034f0  jz      short loc_140003521
0x1400034f2  lea     rcx, [rdi-10h]; P
0x1400034f6  mov     rax, [rcx]
0x1400034f9  test    rax, rax
0x1400034fc  jz      short loc_140003512
0x1400034fe  mov     rdx, rcx; Entry
0x140003501  mov     rcx, rax; Lookaside
0x140003504  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000350b  nop     dword ptr [rax+rax+00h]
0x140003510  jmp     short loc_140003521
0x140003512  mov     edx, [rcx+8]; Tag
0x140003515  call    cs:__imp_ExFreePoolWithTag
0x14000351c  nop     dword ptr [rax+rax+00h]
0x140003521  test    rbx, rbx
0x140003524  jz      short loc_14000355D
0x140003526  mov     eax, [rbx-4]
0x140003529  sub     rbx, rax
0x14000352c  jz      short loc_14000355D
0x14000352e  lea     rcx, [rbx-10h]; P
0x140003532  mov     rax, [rcx]
0x140003535  test    rax, rax
0x140003538  jz      short loc_14000354E
0x14000353a  mov     rdx, rcx; Entry
0x14000353d  mov     rcx, rax; Lookaside
0x140003540  call    cs:__imp_ExFreeToNPagedLookasideList
0x140003547  nop     dword ptr [rax+rax+00h]
0x14000354c  jmp     short loc_14000355D
0x14000354e  mov     edx, [rcx+8]; Tag
0x140003551  call    cs:__imp_ExFreePoolWithTag
0x140003558  nop     dword ptr [rax+rax+00h]
0x14000355d  mov     rax, rsi
0x140003560  mov     rcx, [rsp+98h+var_38]
0x140003565  xor     rcx, rsp; StackCookie
0x140003568  call    __security_check_cookie
0x14000356d  add     rsp, 78h
0x140003571  pop     rdi
0x140003572  pop     rsi
0x140003573  pop     rbp
0x140003574  pop     rbx
0x140003575  retn
```
