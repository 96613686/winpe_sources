# LuafvFetchProfileDataForToken

- ea: `0x1400058cc`
- end: `0x140005a23`
- name: `LuafvFetchProfileDataForToken`
- size: `343`
- prototype: `__int64 __fastcall(void *, const UNICODE_STRING *, const UNICODE_STRING *, void **, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140001e98`

## callees

- `0x1400054e8`
- `0x140005798`
- `0x1400058cc`
- `0x140005a2c`
- `0x140014b6c`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x14000591a`
- `ntoskrnl!SeQueryInformationToken` at `0x14000591a`
- `ntoskrnl!ZwClose` at `0x1400059d1`
- `ntoskrnl!ZwClose` at `0x1400059d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000598c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400059a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000598c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400059a4`

## pseudocode

```c
__int64 __fastcall LuafvFetchProfileDataForToken(
        void *a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        void **a4,
        struct _UNICODE_STRING *a5)
{
  struct _UNICODE_STRING *v5; // r14
  int UserProfilePaths; // ebx
  PWSTR Buffer; // rcx
  PWSTR v11; // rcx
  PWSTR v12; // rcx
  struct _UNICODE_STRING v14[2]; // [rsp+20h] [rbp-28h] BYREF
  PVOID v15; // [rsp+68h] [rbp+20h] BYREF

  v5 = a5;
  v15 = 0;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *v5 = 0;
  v14[0] = 0;
  UserProfilePaths = SeQueryInformationToken(a1, TokenUser, &v15);
  if ( UserProfilePaths >= 0 )
  {
    UserProfilePaths = LuafvConvertSidToUnicodeString(v14, *(_QWORD *)v15);
    if ( UserProfilePaths >= 0 )
    {
      UserProfilePaths = GetUserProfilePaths(v14, (__int64)a2, (__int64)a3);
      if ( UserProfilePaths >= 0 )
      {
        UserProfilePaths = OpenProfileKey((__int64)v14, a4);
        if ( UserProfilePaths >= 0 )
          UserProfilePaths = GetUserDesktopPath(*a4, a3, a2, v5);
      }
    }
  }
  if ( v14[0].Buffer )
    ExFreePoolWithTag(v14[0].Buffer, 0);
  if ( v15 )
    ExFreePoolWithTag(v15, 0);
  if ( UserProfilePaths < 0 )
  {
    Buffer = v5->Buffer;
    if ( Buffer )
    {
      LuafvFreePool(Buffer);
      *v5 = 0;
    }
    if ( *a4 )
    {
      ZwClose(*a4);
      *a4 = 0;
    }
    v11 = a3->Buffer;
    if ( v11 )
    {
      LuafvFreePool(v11);
      *a3 = 0;
    }
    v12 = a2->Buffer;
    if ( v12 )
    {
      LuafvFreePool(v12);
      *a2 = 0;
    }
  }
  return (unsigned int)UserProfilePaths;
}

```

## disassembly

```asm
0x1400058cc  mov     rax, rsp
0x1400058cf  mov     [rax+8], rbx
0x1400058d3  mov     [rax+10h], rbp
0x1400058d7  push    rsi
0x1400058d8  push    rdi
0x1400058d9  push    r14
0x1400058db  sub     rsp, 30h
0x1400058df  mov     r14, [rsp+48h+arg_20]
0x1400058e4  xorps   xmm1, xmm1
0x1400058e7  xorps   xmm0, xmm0
0x1400058ea  mov     qword ptr [rax+20h], 0
0x1400058f2  movups  xmmword ptr [rdx], xmm1
0x1400058f5  mov     rbp, r8
0x1400058f8  mov     rsi, rdx
0x1400058fb  movups  xmmword ptr [r8], xmm0
0x1400058ff  lea     r8, [rax+20h]; TokenInformation
0x140005903  mov     qword ptr [r9], 0
0x14000590a  mov     edx, 1; TokenInformationClass
0x14000590f  mov     rdi, r9
0x140005912  movups  xmmword ptr [r14], xmm1
0x140005916  movups  xmmword ptr [rax-28h], xmm0
0x14000591a  call    cs:__imp_SeQueryInformationToken
0x140005921  nop     dword ptr [rax+rax+00h]
0x140005926  mov     ebx, eax
0x140005928  test    eax, eax
0x14000592a  js      short loc_140005980
0x14000592c  mov     rdx, [rsp+48h+arg_18]
0x140005931  lea     rcx, [rsp+48h+var_28]
0x140005936  mov     rdx, [rdx]
0x140005939  call    LuafvConvertSidToUnicodeString
0x14000593e  mov     ebx, eax
0x140005940  test    eax, eax
0x140005942  js      short loc_140005980
0x140005944  mov     r8, rbp
0x140005947  lea     rcx, [rsp+48h+var_28]
0x14000594c  mov     rdx, rsi
0x14000594f  call    GetUserProfilePaths
0x140005954  mov     ebx, eax
0x140005956  test    eax, eax
0x140005958  js      short loc_140005980
0x14000595a  mov     rdx, rdi
0x14000595d  lea     rcx, [rsp+48h+var_28]
0x140005962  call    OpenProfileKey
0x140005967  mov     ebx, eax
0x140005969  test    eax, eax
0x14000596b  js      short loc_140005980
0x14000596d  mov     rcx, [rdi]
0x140005970  mov     r9, r14
0x140005973  mov     r8, rsi
0x140005976  mov     rdx, rbp
0x140005979  call    GetUserDesktopPath
0x14000597e  mov     ebx, eax
0x140005980  mov     rcx, [rsp+48h+P]; P
0x140005985  test    rcx, rcx
0x140005988  jz      short loc_140005998
0x14000598a  xor     edx, edx; Tag
0x14000598c  call    cs:__imp_ExFreePoolWithTag
0x140005993  nop     dword ptr [rax+rax+00h]
0x140005998  mov     rcx, [rsp+48h+arg_18]; P
0x14000599d  test    rcx, rcx
0x1400059a0  jz      short loc_1400059B0
0x1400059a2  xor     edx, edx; Tag
0x1400059a4  call    cs:__imp_ExFreePoolWithTag
0x1400059ab  nop     dword ptr [rax+rax+00h]
0x1400059b0  test    ebx, ebx
0x1400059b2  jns     short loc_140005A0D
0x1400059b4  mov     rcx, [r14+8]
0x1400059b8  test    rcx, rcx
0x1400059bb  jz      short loc_1400059C9
0x1400059bd  call    LuafvFreePool
0x1400059c2  xorps   xmm0, xmm0
0x1400059c5  movups  xmmword ptr [r14], xmm0
0x1400059c9  mov     rcx, [rdi]; Handle
0x1400059cc  test    rcx, rcx
0x1400059cf  jz      short loc_1400059E4
0x1400059d1  call    cs:__imp_ZwClose
0x1400059d8  nop     dword ptr [rax+rax+00h]
0x1400059dd  mov     qword ptr [rdi], 0
0x1400059e4  mov     rcx, [rbp+8]
0x1400059e8  test    rcx, rcx
0x1400059eb  jz      short loc_1400059F9
0x1400059ed  call    LuafvFreePool
0x1400059f2  xorps   xmm0, xmm0
0x1400059f5  movups  xmmword ptr [rbp+0], xmm0
0x1400059f9  mov     rcx, [rsi+8]
0x1400059fd  test    rcx, rcx
0x140005a00  jz      short loc_140005A0D
0x140005a02  call    LuafvFreePool
0x140005a07  xorps   xmm0, xmm0
0x140005a0a  movups  xmmword ptr [rsi], xmm0
0x140005a0d  mov     rbp, [rsp+48h+arg_8]
0x140005a12  mov     eax, ebx
0x140005a14  mov     rbx, [rsp+48h+arg_0]
0x140005a19  add     rsp, 30h
0x140005a1d  pop     r14
0x140005a1f  pop     rdi
0x140005a20  pop     rsi
0x140005a21  retn
```
