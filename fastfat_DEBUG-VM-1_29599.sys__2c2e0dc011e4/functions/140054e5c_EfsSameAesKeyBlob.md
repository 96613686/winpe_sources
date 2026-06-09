# EfsSameAesKeyBlob

- ea: `0x140054e5c`
- end: `0x140054fcc`
- name: `EfsSameAesKeyBlob`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140054fd4`

## callees

- `0x14000cba0`
- `0x14004e610`
- `0x140054e5c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054f7e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054faf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054f7e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140054faf`
- `ksecdd!BCryptExportKey` at `0x140054ee8`
- `ksecdd!BCryptExportKey` at `0x140054f1f`
- `ksecdd!BCryptExportKey` at `0x140054ee8`
- `ksecdd!BCryptExportKey` at `0x140054f1f`

## pseudocode

```c
bool __fastcall EfsSameAesKeyBlob(__int64 a1, __int64 a2, int a3)
{
  _DWORD *KeyBlobBuffer; // r14
  bool v7; // di
  _DWORD *v8; // rax
  _BYTE *v9; // rbx
  _DWORD *v10; // rsi
  ULONG cbOutput; // ebp
  __int64 v12; // rax
  __int64 v13; // rax
  _BYTE *v14; // rcx
  ULONG v16[18]; // [rsp+40h] [rbp-48h] BYREF
  ULONG pcbResult; // [rsp+A8h] [rbp+20h] BYREF

  pcbResult = 0;
  v16[0] = 0;
  KeyBlobBuffer = GetKeyBlobBufferEx(a3, 0);
  if ( !KeyBlobBuffer )
    return 0;
  v8 = GetKeyBlobBufferEx(a3, 0);
  v9 = KeyBlobBuffer + 20;
  v10 = v8;
  v7 = 0;
  if ( v8 )
  {
    cbOutput = *KeyBlobBuffer - 87;
    if ( BCryptExportKey(
           *(BCRYPT_KEY_HANDLE *)(a1 + 8),
           0,
           L"KeyDataBlob",
           (PUCHAR)KeyBlobBuffer + 80,
           cbOutput,
           &pcbResult,
           0) >= 0
      && BCryptExportKey(*(BCRYPT_KEY_HANDLE *)(a2 + 8), 0, L"KeyDataBlob", (PUCHAR)v10 + 80, cbOutput, v16, 0) >= 0
      && pcbResult == v16[0]
      && !memcmp(KeyBlobBuffer + 20, v10 + 20, pcbResult) )
    {
      v7 = 1;
    }
  }
  v12 = pcbResult;
  if ( pcbResult )
  {
    do
    {
      *v9++ = 0;
      --v12;
    }
    while ( v12 );
  }
  ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)KeyBlobBuffer + 9), KeyBlobBuffer);
  if ( v10 )
  {
    v13 = v16[0];
    v14 = v10 + 20;
    if ( v16[0] )
    {
      do
      {
        *v14++ = 0;
        --v13;
      }
      while ( v13 );
    }
    ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v10 + 9), v10);
  }
  return v7;
}

```

## disassembly

```asm
0x140054e5c  mov     rax, rsp
0x140054e5f  push    rbx
0x140054e60  push    rbp
0x140054e61  push    rsi
0x140054e62  push    rdi
0x140054e63  push    r14
0x140054e65  push    r15
0x140054e67  sub     rsp, 58h
0x140054e6b  mov     r15, rdx
0x140054e6e  mov     dword ptr [rax+20h], 0
0x140054e75  mov     rdi, rcx
0x140054e78  mov     dword ptr [rax-48h], 0
0x140054e7f  xor     edx, edx
0x140054e81  mov     ecx, r8d
0x140054e84  mov     ebx, r8d
0x140054e87  call    GetKeyBlobBufferEx
0x140054e8c  mov     r14, rax
0x140054e8f  test    rax, rax
0x140054e92  jnz     short loc_140054E9C
0x140054e94  xor     dil, dil
0x140054e97  jmp     loc_140054FBB
0x140054e9c  xor     edx, edx
0x140054e9e  mov     ecx, ebx
0x140054ea0  call    GetKeyBlobBufferEx
0x140054ea5  lea     rbx, [r14+50h]
0x140054ea9  mov     rsi, rax
0x140054eac  test    rax, rax
0x140054eaf  jnz     short loc_140054EB9
0x140054eb1  xor     dil, dil
0x140054eb4  jmp     loc_140054F5F
0x140054eb9  mov     ebp, [r14]
0x140054ebc  lea     rax, [rsp+88h+arg_18]
0x140054ec4  mov     rcx, [rdi+8]; hKey
0x140054ec8  lea     r8, pszBlobType; "KeyDataBlob"
0x140054ecf  mov     [rsp+88h+dwFlags], 0; dwFlags
0x140054ed7  add     ebp, 0FFFFFFA9h
0x140054eda  mov     [rsp+88h+pcbResult], rax; pcbResult
0x140054edf  mov     r9, rbx; pbOutput
0x140054ee2  xor     edx, edx; hExportKey
0x140054ee4  mov     [rsp+88h+cbOutput], ebp; cbOutput
0x140054ee8  call    cs:__imp_BCryptExportKey
0x140054eef  nop     dword ptr [rax+rax+00h]
0x140054ef4  test    eax, eax
0x140054ef6  js      short loc_140054EB1
0x140054ef8  mov     rcx, [r15+8]; hKey
0x140054efc  lea     rax, [rsp+88h+var_48]
0x140054f01  mov     [rsp+88h+dwFlags], 0; dwFlags
0x140054f09  lea     r9, [rsi+50h]; pbOutput
0x140054f0d  mov     [rsp+88h+pcbResult], rax; pcbResult
0x140054f12  lea     r8, pszBlobType; "KeyDataBlob"
0x140054f19  xor     edx, edx; hExportKey
0x140054f1b  mov     [rsp+88h+cbOutput], ebp; cbOutput
0x140054f1f  call    cs:__imp_BCryptExportKey
0x140054f26  nop     dword ptr [rax+rax+00h]
0x140054f2b  test    eax, eax
0x140054f2d  js      short loc_140054EB1
0x140054f2f  mov     eax, [rsp+88h+var_48]
0x140054f33  cmp     [rsp+88h+arg_18], eax
0x140054f3a  jnz     loc_140054EB1
0x140054f40  mov     r8d, [rsp+88h+arg_18]; Size
0x140054f48  lea     rdx, [rsi+50h]; Buf2
0x140054f4c  mov     rcx, rbx; Buf1
0x140054f4f  call    memcmp
0x140054f54  test    eax, eax
0x140054f56  jnz     loc_140054EB1
0x140054f5c  mov     dil, 1
0x140054f5f  mov     eax, [rsp+88h+arg_18]
0x140054f66  test    rax, rax
0x140054f69  jz      short loc_140054F77
0x140054f6b  mov     byte ptr [rbx], 0
0x140054f6e  inc     rbx
0x140054f71  sub     rax, 1
0x140054f75  jnz     short loc_140054F6B
0x140054f77  mov     rcx, [r14+48h]; Lookaside
0x140054f7b  mov     rdx, r14; Entry
0x140054f7e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140054f85  nop     dword ptr [rax+rax+00h]
0x140054f8a  test    rsi, rsi
0x140054f8d  jz      short loc_140054FBB
0x140054f8f  mov     eax, [rsp+88h+var_48]
0x140054f93  lea     rcx, [rsi+50h]
0x140054f97  test    rax, rax
0x140054f9a  jz      short loc_140054FA8
0x140054f9c  mov     byte ptr [rcx], 0
0x140054f9f  inc     rcx
0x140054fa2  sub     rax, 1
0x140054fa6  jnz     short loc_140054F9C
0x140054fa8  mov     rcx, [rsi+48h]; Lookaside
0x140054fac  mov     rdx, rsi; Entry
0x140054faf  call    cs:__imp_ExFreeToNPagedLookasideList
0x140054fb6  nop     dword ptr [rax+rax+00h]
0x140054fbb  mov     al, dil
0x140054fbe  add     rsp, 58h
0x140054fc2  pop     r15
0x140054fc4  pop     r14
0x140054fc6  pop     rdi
0x140054fc7  pop     rsi
0x140054fc8  pop     rbp
0x140054fc9  pop     rbx
0x140054fca  retn
```
