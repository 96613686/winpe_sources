# windows_wrappers::GetSecurityDescriptor(void *,windows_wrappers::SecurityDescriptor &)

- ea: `0x18002c444`
- end: `0x18002c4f9`
- name: `?GetSecurityDescriptor@windows_wrappers@@YAXPEAXAEAVSecurityDescriptor@1@@Z`
- size: `181`
- prototype: `void __fastcall(HANDLE Handle, void *, struct SecurityDescriptor *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180026b68`
- `0x18002a390`

## callees

- `0x180002f1c`
- `0x18000b4bc`
- `0x18002c444`

## import_xrefs

- `ntdll!NtQuerySecurityObject` at `0x18002c470`
- `ntdll!NtQuerySecurityObject` at `0x18002c4a9`
- `ntdll!NtQuerySecurityObject` at `0x18002c470`
- `ntdll!NtQuerySecurityObject` at `0x18002c4a9`

## pseudocode

```c
void __fastcall windows_wrappers::GetSecurityDescriptor(HANDLE Handle, _QWORD *a2, struct SecurityDescriptor *a3)
{
  unsigned int v5; // eax
  void *v6; // rax
  ULONG v7; // r9d
  NTSTATUS v8; // eax
  int LengthNeeded; // [rsp+20h] [rbp-18h]
  int LengthNeededa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  ULONG Length; // [rsp+50h] [rbp+18h] BYREF

  Length = 0;
  v5 = NtQuerySecurityObject(Handle, 0xFu, 0, 0, &Length);
  if ( v5 != -1073741789 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\windows_api_wrappers.cpp",
      (const char *)v5,
      LengthNeeded);
  v6 = operator new[](Length);
  v7 = Length;
  *a2 = v6;
  v8 = NtQuerySecurityObject(Handle, 0xFu, v6, v7, &Length);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\windows_api_wrappers.cpp",
      (const char *)(unsigned int)v8,
      LengthNeededa);
}

```

## disassembly

```asm
0x18002c444  mov     [rsp+arg_0], rbx
0x18002c449  push    rdi
0x18002c44a  sub     rsp, 30h
0x18002c44e  xor     r9d, r9d; Length
0x18002c451  mov     [rsp+38h+Length], 0
0x18002c459  mov     rdi, rdx
0x18002c45c  lea     rax, [rsp+38h+Length]
0x18002c461  xor     r8d, r8d; SecurityDescriptor
0x18002c464  mov     qword ptr [rsp+38h+LengthNeeded], rax; int
0x18002c469  mov     rbx, rcx
0x18002c46c  lea     edx, [r9+0Fh]; SecurityInformation
0x18002c470  call    cs:__imp_NtQuerySecurityObject
0x18002c477  nop     dword ptr [rax+rax+00h]
0x18002c47c  cmp     eax, 0C0000023h
0x18002c481  jnz     short loc_18002C4C5
0x18002c483  mov     ecx, [rsp+38h+Length]; unsigned __int64
0x18002c487  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002c48c  mov     r9d, [rsp+38h+Length]; Length
0x18002c491  lea     rcx, [rsp+38h+Length]
0x18002c496  mov     qword ptr [rsp+38h+LengthNeeded], rcx; int
0x18002c49b  mov     r8, rax; SecurityDescriptor
0x18002c49e  mov     rcx, rbx; Handle
0x18002c4a1  mov     [rdi], rax
0x18002c4a4  mov     edx, 0Fh; SecurityInformation
0x18002c4a9  call    cs:__imp_NtQuerySecurityObject
0x18002c4b0  nop     dword ptr [rax+rax+00h]
0x18002c4b5  test    eax, eax
0x18002c4b7  js      short loc_18002C4DF
0x18002c4b9  mov     rbx, [rsp+38h+arg_0]
0x18002c4be  add     rsp, 30h
0x18002c4c2  pop     rdi
0x18002c4c3  retn
0x18002c4c5  mov     rcx, [rsp+38h]; this
0x18002c4ca  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\container"...
0x18002c4d1  mov     r9d, eax; char *
0x18002c4d4  mov     edx, 31h ; '1'; void *
0x18002c4d9  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18002c4df  mov     rcx, [rsp+38h]; this
0x18002c4e4  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\container"...
0x18002c4eb  mov     r9d, eax; char *
0x18002c4ee  mov     edx, 3Eh ; '>'; void *
0x18002c4f3  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
