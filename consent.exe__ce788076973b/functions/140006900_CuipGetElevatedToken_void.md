# CuipGetElevatedToken(void * *)

- ea: `0x140006900`
- end: `0x1400069a8`
- name: `?CuipGetElevatedToken@@YAKPEAPEAX@Z`
- size: `168`
- prototype: `ULONG __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14001a080`

## callees

- `0x140006900`

## import_xrefs

- `ntdll!NtClose` at `0x140006983`
- `ntdll!NtClose` at `0x140006983`
- `ntdll!NtQueryInformationToken` at `0x14000693a`
- `ntdll!NtQueryInformationToken` at `0x140006976`
- `ntdll!NtQueryInformationToken` at `0x14000693a`
- `ntdll!NtQueryInformationToken` at `0x140006976`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x140006946`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x140006946`

## pseudocode

```c
ULONG __fastcall CuipGetElevatedToken(void **a1)
{
  HANDLE v2; // rcx
  int v3; // eax
  int TokenInformation; // [rsp+50h] [rbp+8h] BYREF
  ULONG ReturnLength; // [rsp+58h] [rbp+10h] BYREF
  ULONG v7; // [rsp+60h] [rbp+18h] BYREF
  void *v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = 0;
  v2 = *a1;
  v7 = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v3 = NtQueryInformationToken(v2, TokenElevation, &TokenInformation, 4u, &ReturnLength);
  if ( v3 < 0 )
    return RtlNtStatusToDosErrorNoTeb(v3);
  if ( TokenInformation )
    return 0;
  v3 = NtQueryInformationToken(*a1, TokenLinkedToken, &v8, 8u, &v7);
  if ( v3 >= 0 )
  {
    NtClose(*a1);
    *a1 = v8;
    return 0;
  }
  if ( v3 != -1073741729 )
    return RtlNtStatusToDosErrorNoTeb(v3);
  return 740;
}

```

## disassembly

```asm
0x140006900  push    rbx
0x140006902  push    rdi
0x140006903  sub     rsp, 38h
0x140006907  xor     edi, edi
0x140006909  lea     rax, [rsp+48h+arg_8]
0x14000690e  mov     rbx, rcx
0x140006911  mov     [rsp+48h+arg_18], rdi
0x140006916  mov     rcx, [rcx]; TokenHandle
0x140006919  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14000691e  mov     r9d, 4; TokenInformationLength
0x140006924  mov     [rsp+48h+arg_10], edi
0x140006928  mov     edx, 14h; TokenInformationClass
0x14000692d  mov     [rsp+48h+TokenInformation], edi
0x140006931  mov     [rsp+48h+arg_8], edi
0x140006935  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14000693a  call    cs:__imp_NtQueryInformationToken
0x140006940  test    eax, eax
0x140006942  jns     short loc_140006953
0x140006944  mov     ecx, eax; Status
0x140006946  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x14000694c  add     rsp, 38h
0x140006950  pop     rdi
0x140006951  pop     rbx
0x140006952  retn
0x140006953  cmp     [rsp+48h+TokenInformation], edi
0x140006957  jnz     short loc_140006991
0x140006959  mov     rcx, [rbx]; TokenHandle
0x14000695c  lea     rax, [rsp+48h+arg_10]
0x140006961  mov     r9d, 8; TokenInformationLength
0x140006967  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14000696c  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x140006971  mov     edx, 13h; TokenInformationClass
0x140006976  call    cs:__imp_NtQueryInformationToken
0x14000697c  test    eax, eax
0x14000697e  js      short loc_14000699A
0x140006980  mov     rcx, [rbx]; Handle
0x140006983  call    cs:__imp_NtClose
0x140006989  mov     rcx, [rsp+48h+arg_18]
0x14000698e  mov     [rbx], rcx
0x140006991  mov     eax, edi
0x140006993  add     rsp, 38h
0x140006997  pop     rdi
0x140006998  pop     rbx
0x140006999  retn
0x14000699a  cmp     eax, 0C000005Fh
0x14000699f  jnz     short loc_140006944
0x1400069a1  mov     eax, 2E4h
0x1400069a6  jmp     short loc_14000694C
```
