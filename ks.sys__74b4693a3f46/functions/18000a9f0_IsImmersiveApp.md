# IsImmersiveApp

- ea: `0x18000a9f0`
- end: `0x18000aa79`
- name: `IsImmersiveApp`
- size: `137`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180040370`
- `0x180050254`

## callees

- `0x18000a9f0`
- `0x18000fb04`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x18000aa5f`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x18000aa5f`
- `ntoskrnl!PsReferencePrimaryToken` at `0x18000aa04`
- `ntoskrnl!PsReferencePrimaryToken` at `0x18000aa04`

## pseudocode

```c
bool __fastcall IsImmersiveApp(struct _KPROCESS *a1)
{
  bool v1; // bl
  __int64 v2; // rdx
  PACCESS_TOKEN v3; // rdi
  int v5; // [rsp+48h] [rbp+10h] BYREF
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF
  __int64 v7; // [rsp+58h] [rbp+20h] BYREF

  v1 = 0;
  v5 = 0;
  v3 = PsReferencePrimaryToken(a1);
  if ( v3 )
  {
    v6 = 0;
    v7 = 0;
    if ( (int)AppModelPolicy_GetPolicy_Internal(v3, v2, &v5, &v7, &v6) >= 0 )
      v1 = (unsigned int)(v5 - 196609) <= 1;
    PsDereferencePrimaryToken(v3);
  }
  return v1;
}

```

## disassembly

```asm
0x18000a9f0  mov     [rsp+arg_0], rbx
0x18000a9f5  push    rdi
0x18000a9f6  sub     rsp, 30h
0x18000a9fa  xor     bl, bl
0x18000a9fc  mov     [rsp+38h+arg_8], 0
0x18000aa04  call    cs:__imp_PsReferencePrimaryToken
0x18000aa0b  nop     dword ptr [rax+rax+00h]
0x18000aa10  mov     rdi, rax
0x18000aa13  test    rax, rax
0x18000aa16  jz      short loc_18000AA6B
0x18000aa18  lea     rax, [rsp+38h+arg_10]
0x18000aa1d  mov     [rsp+38h+arg_10], 0
0x18000aa26  lea     r9, [rsp+38h+arg_18]
0x18000aa2b  mov     [rsp+38h+var_18], rax
0x18000aa30  lea     r8, [rsp+38h+arg_8]
0x18000aa35  mov     [rsp+38h+arg_18], 0
0x18000aa3e  mov     rcx, rdi
0x18000aa41  call    ?AppModelPolicy_GetPolicy_Internal@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@PEAU_PS_PKG_CLAIM@@PEA_K@Z; AppModelPolicy_GetPolicy_Internal(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *,_PS_PKG_CLAIM *,unsigned __int64 *)
0x18000aa46  or      eax, 10000000h
0x18000aa4b  jl      short loc_18000AA5C
0x18000aa4d  mov     eax, [rsp+38h+arg_8]
0x18000aa51  add     eax, 0FFFCFFFFh
0x18000aa56  cmp     eax, 1
0x18000aa59  setbe   bl
0x18000aa5c  mov     rcx, rdi; PrimaryToken
0x18000aa5f  call    cs:__imp_PsDereferencePrimaryToken
0x18000aa66  nop     dword ptr [rax+rax+00h]
0x18000aa6b  mov     al, bl
0x18000aa6d  mov     rbx, [rsp+38h+arg_0]
0x18000aa72  add     rsp, 30h
0x18000aa76  pop     rdi
0x18000aa77  retn
```
