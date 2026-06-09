# SspGetTokenPackage(void *,uchar *,_TOKEN_APPCONTAINER_INFORMATION *,ulong *)

- ea: `0x180021f2c`
- end: `0x180021f9e`
- name: `?SspGetTokenPackage@@YAJPEAXPEAEPEAU_TOKEN_APPCONTAINER_INFORMATION@@PEAK@Z`
- size: `114`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned __int8 *, struct _TOKEN_APPCONTAINER_INFORMATION *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006c90`

## callees

- `0x180021f2c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180021f68`
- `ntdll!NtQueryInformationToken` at `0x180021f8f`
- `ntdll!NtQueryInformationToken` at `0x180021f68`
- `ntdll!NtQueryInformationToken` at `0x180021f8f`

## pseudocode

```c
int __fastcall SspGetTokenPackage(
        HANDLE TokenHandle,
        unsigned __int8 *a2,
        struct _TOKEN_APPCONTAINER_INFORMATION *a3,
        unsigned int *a4)
{
  int result; // eax
  ULONG v9; // r9d
  ULONG ReturnLength[14]; // [rsp+30h] [rbp-38h] BYREF
  int v11; // [rsp+78h] [rbp+10h] BYREF

  *a2 = 0;
  v11 = 0;
  ReturnLength[0] = 4;
  result = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &v11, 4u, ReturnLength);
  if ( result >= 0 )
  {
    if ( v11 )
    {
      v9 = *a4;
      *a2 = 1;
      return NtQueryInformationToken(TokenHandle, TokenAppContainerSid, a3, v9, a4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180021f2c  mov     r11, rsp
0x180021f2f  push    rbx
0x180021f30  push    rbp
0x180021f31  push    rsi
0x180021f32  push    rdi
0x180021f33  sub     rsp, 48h
0x180021f37  mov     rbx, r9
0x180021f3a  mov     byte ptr [rdx], 0
0x180021f3d  mov     r9d, 4; TokenInformationLength
0x180021f43  mov     [rsp+68h+arg_8], 0
0x180021f4b  mov     rbp, r8
0x180021f4e  mov     [r11-38h], r9d
0x180021f52  mov     rdi, rdx
0x180021f55  lea     rax, [r11-38h]
0x180021f59  lea     r8, [r11+10h]; TokenInformation
0x180021f5d  mov     [r11-48h], rax
0x180021f61  lea     edx, [r9+19h]; TokenInformationClass
0x180021f65  mov     rsi, rcx
0x180021f68  call    cs:__imp_NtQueryInformationToken
0x180021f6e  test    eax, eax
0x180021f70  js      short loc_180021F95
0x180021f72  cmp     [rsp+68h+arg_8], 0
0x180021f77  jz      short loc_180021F95
0x180021f79  mov     r9d, [rbx]; TokenInformationLength
0x180021f7c  mov     r8, rbp; TokenInformation
0x180021f7f  mov     edx, 1Fh; TokenInformationClass
0x180021f84  mov     byte ptr [rdi], 1
0x180021f87  mov     rcx, rsi; TokenHandle
0x180021f8a  mov     [rsp+68h+ReturnLength], rbx; ReturnLength
0x180021f8f  call    cs:__imp_NtQueryInformationToken
0x180021f95  add     rsp, 48h
0x180021f99  pop     rdi
0x180021f9a  pop     rsi
0x180021f9b  pop     rbp
0x180021f9c  pop     rbx
0x180021f9d  retn
```
