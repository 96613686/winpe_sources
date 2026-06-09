# UpdateTrafficSecretAndDeriveNewKey(unsigned __int64,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x14000be38`
- end: `0x14000bf6b`
- name: `?UpdateTrafficSecretAndDeriveNewKey@@YAJ_KPEA_K11@Z`
- size: `307`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000acd4`

## callees

- `0x14000be38`

## import_xrefs

- `cng!SslExpandNextGenTrafficKey` at `0x14000be9a`
- `cng!SslExpandNextGenTrafficKey` at `0x14000be9a`
- `cng!SslExpandWriteKey` at `0x14000bebe`
- `cng!SslExpandWriteKey` at `0x14000bebe`
- `cng!SslFreeObject` at `0x14000beda`
- `cng!SslFreeObject` at `0x14000bef0`
- `cng!SslFreeObject` at `0x14000bf31`
- `cng!SslFreeObject` at `0x14000bf48`
- `cng!SslFreeObject` at `0x14000beda`
- `cng!SslFreeObject` at `0x14000bef0`
- `cng!SslFreeObject` at `0x14000bf31`
- `cng!SslFreeObject` at `0x14000bf48`

## pseudocode

```c
__int64 __fastcall UpdateTrafficSecretAndDeriveNewKey(
        __int64 a1,
        unsigned __int64 *a2,
        unsigned __int64 *a3,
        unsigned __int64 *a4)
{
  unsigned int v8; // esi
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v12[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int64 v13; // [rsp+80h] [rbp+38h] BYREF

  v13 = 0;
  v12[0] = 0;
  if ( !a1 || !a2 || !a3 || !a4 )
    return 2148074333LL;
  v8 = SslExpandNextGenTrafficKey(a1, *a2, &v13, 0, 0);
  if ( v8 || (v8 = SslExpandWriteKey(a1, v13, v12, 0, 0)) != 0 )
  {
    v9 = v13;
    v10 = v12[0];
  }
  else
  {
    if ( *a2 )
      SslFreeObject(*a2, 0);
    if ( *a3 )
      SslFreeObject(*a3, 0);
    *a2 = v13;
    *a3 = v12[0];
    v9 = 0;
    v10 = 0;
    *a4 = 0;
    v12[0] = 0;
    v13 = 0;
  }
  if ( v9 )
  {
    SslFreeObject(v9, 0);
    v10 = v12[0];
  }
  if ( v10 )
    SslFreeObject(v10, 0);
  return v8;
}

```

## disassembly

```asm
0x14000be38  push    rbp
0x14000be3a  push    rbx
0x14000be3b  push    rsi
0x14000be3c  push    rdi
0x14000be3d  push    r14
0x14000be3f  push    r15
0x14000be41  mov     rbp, rsp
0x14000be44  sub     rsp, 48h
0x14000be48  mov     [rbp+arg_0], 0
0x14000be50  mov     r15, r9
0x14000be53  mov     [rbp+var_18], 0
0x14000be5b  mov     rdi, r8
0x14000be5e  mov     rbx, rdx
0x14000be61  mov     r14, rcx
0x14000be64  test    rcx, rcx
0x14000be67  jz      loc_14000BF58
0x14000be6d  test    rdx, rdx
0x14000be70  jz      loc_14000BF58
0x14000be76  test    r8, r8
0x14000be79  jz      loc_14000BF58
0x14000be7f  test    r9, r9
0x14000be82  jz      loc_14000BF58
0x14000be88  mov     rdx, [rdx]
0x14000be8b  lea     r8, [rbp+arg_0]
0x14000be8f  xor     r9d, r9d
0x14000be92  mov     [rsp+48h+var_28], 0
0x14000be9a  call    cs:__imp_SslExpandNextGenTrafficKey
0x14000bea1  nop     dword ptr [rax+rax+00h]
0x14000bea6  mov     esi, eax
0x14000bea8  test    eax, eax
0x14000beaa  jnz     short loc_14000BF1F
0x14000beac  mov     rdx, [rbp+arg_0]
0x14000beb0  lea     r8, [rbp+var_18]
0x14000beb4  xor     r9d, r9d
0x14000beb7  mov     [rsp+48h+var_28], eax
0x14000bebb  mov     rcx, r14
0x14000bebe  call    cs:__imp_SslExpandWriteKey
0x14000bec5  nop     dword ptr [rax+rax+00h]
0x14000beca  mov     esi, eax
0x14000becc  test    eax, eax
0x14000bece  jnz     short loc_14000BF1F
0x14000bed0  mov     rcx, [rbx]
0x14000bed3  test    rcx, rcx
0x14000bed6  jz      short loc_14000BEE6
0x14000bed8  xor     edx, edx
0x14000beda  call    cs:__imp_SslFreeObject
0x14000bee1  nop     dword ptr [rax+rax+00h]
0x14000bee6  mov     rcx, [rdi]
0x14000bee9  test    rcx, rcx
0x14000beec  jz      short loc_14000BEFC
0x14000beee  xor     edx, edx
0x14000bef0  call    cs:__imp_SslFreeObject
0x14000bef7  nop     dword ptr [rax+rax+00h]
0x14000befc  mov     rax, [rbp+arg_0]
0x14000bf00  mov     [rbx], rax
0x14000bf03  mov     rax, [rbp+var_18]
0x14000bf07  mov     [rdi], rax
0x14000bf0a  xor     eax, eax
0x14000bf0c  xor     ecx, ecx
0x14000bf0e  mov     qword ptr [r15], 0
0x14000bf15  mov     [rbp+var_18], rcx
0x14000bf19  mov     [rbp+arg_0], rax
0x14000bf1d  jmp     short loc_14000BF27
0x14000bf1f  mov     rax, [rbp+arg_0]
0x14000bf23  mov     rcx, [rbp+var_18]
0x14000bf27  test    rax, rax
0x14000bf2a  jz      short loc_14000BF41
0x14000bf2c  xor     edx, edx
0x14000bf2e  mov     rcx, rax
0x14000bf31  call    cs:__imp_SslFreeObject
0x14000bf38  nop     dword ptr [rax+rax+00h]
0x14000bf3d  mov     rcx, [rbp+var_18]
0x14000bf41  test    rcx, rcx
0x14000bf44  jz      short loc_14000BF54
0x14000bf46  xor     edx, edx
0x14000bf48  call    cs:__imp_SslFreeObject
0x14000bf4f  nop     dword ptr [rax+rax+00h]
0x14000bf54  mov     eax, esi
0x14000bf56  jmp     short loc_14000BF5D
0x14000bf58  mov     eax, 8009035Dh
0x14000bf5d  add     rsp, 48h
0x14000bf61  pop     r15
0x14000bf63  pop     r14
0x14000bf65  pop     rdi
0x14000bf66  pop     rsi
0x14000bf67  pop     rbx
0x14000bf68  pop     rbp
0x14000bf69  retn
```
