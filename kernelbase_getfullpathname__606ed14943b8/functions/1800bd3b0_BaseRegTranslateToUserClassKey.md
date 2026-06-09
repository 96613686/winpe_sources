# BaseRegTranslateToUserClassKey

- ea: `0x1800bd3b0`
- end: `0x1800bd4ff`
- name: `BaseRegTranslateToUserClassKey`
- size: `335`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18005cc70`
- `0x1800bce60`
- `0x1800bd240`
- `0x180113c4c`

## callees

- `0x1800bd3b0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800bd446`
- `ntdll!RtlFreeUnicodeString` at `0x1800bd446`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800bd47a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800bd4dc`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800bd47a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800bd4dc`
- `ntdll!RtlAppendUnicodeToString` at `0x1800bd45c`
- `ntdll!RtlAppendUnicodeToString` at `0x1800bd45c`
- `ntdll!RtlCopyUnicodeString` at `0x1800bd435`
- `ntdll!RtlCopyUnicodeString` at `0x1800bd4c8`
- `ntdll!RtlCopyUnicodeString` at `0x1800bd435`
- `ntdll!RtlCopyUnicodeString` at `0x1800bd4c8`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800bd4b4`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800bd4b4`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800bd41d`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800bd41d`

## string_xrefs

- `0x1800bd49b`: `\Registry\User`

## pseudocode

```c
int __fastcall BaseRegTranslateToUserClassKey(__int64 a1, struct _UNICODE_STRING *a2, USHORT *a3)
{
  __int64 v3; // r10
  _WORD *v4; // r9
  __int16 v7; // dx
  __int64 v8; // r8
  bool v9; // zf
  int result; // eax
  struct _UNICODE_STRING KeyPath; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING Source; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  v3 = *(unsigned __int16 *)(a1 + 4);
  v4 = *(_WORD **)(a1 + 16);
  Source = 0;
  if ( v4[v3 + 2] )
  {
    v7 = 1;
    v8 = 1;
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
  DestinationString = 0;
  KeyPath = 0;
  Source.Buffer = &v4[v3 - v8 + 2];
  v9 = (*(_BYTE *)a1 & 1) == 0;
  Source.Length = *v4 + 2 * (v7 - v3);
  if ( v9 )
  {
    result = RtlFormatCurrentUserKeyPath(&KeyPath);
    if ( result < 0 )
      return result;
    RtlCopyUnicodeString(a2, &KeyPath);
    RtlFreeUnicodeString(&KeyPath);
  }
  else
  {
    KeyPath.Buffer = v4 + 16;
    KeyPath.Length = *(_WORD *)(a1 + 6) - 44;
    RtlInitUnicodeStringEx(&DestinationString, L"\\Registry\\User");
    RtlCopyUnicodeString(a2, &DestinationString);
    result = RtlAppendUnicodeStringToString(a2, &KeyPath);
    if ( result < 0 )
      return result;
  }
  result = RtlAppendUnicodeToString(a2, L"_Classes");
  if ( result >= 0 )
  {
    *a3 = a2->Length;
    return RtlAppendUnicodeStringToString(a2, &Source);
  }
  return result;
}

```

## disassembly

```asm
0x1800bd3b0  mov     [rsp+arg_0], rbx
0x1800bd3b5  push    rdi
0x1800bd3b6  sub     rsp, 50h
0x1800bd3ba  movzx   r10d, word ptr [rcx+4]
0x1800bd3bf  xorps   xmm0, xmm0
0x1800bd3c2  mov     r9, [rcx+10h]
0x1800bd3c6  mov     rdi, r8
0x1800bd3c9  movups  xmmword ptr [rsp+58h+Source.Length], xmm0
0x1800bd3ce  mov     rbx, rdx
0x1800bd3d1  cmp     word ptr [r9+r10*2+4], 0
0x1800bd3d8  jz      loc_1800BD4F2
0x1800bd3de  mov     edx, 1
0x1800bd3e3  mov     r8d, edx
0x1800bd3e6  sub     dx, r10w
0x1800bd3ea  mov     rax, r10
0x1800bd3ed  sub     rax, r8
0x1800bd3f0  add     dx, dx
0x1800bd3f3  add     rax, 2
0x1800bd3f7  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x1800bd3fc  movups  xmmword ptr [rsp+58h+KeyPath.Length], xmm0
0x1800bd401  lea     rax, [r9+rax*2]
0x1800bd405  mov     [rsp+58h+Source.Buffer], rax
0x1800bd40a  add     dx, [r9]
0x1800bd40e  test    byte ptr [rcx], 1
0x1800bd411  mov     [rsp+58h+Source.Length], dx
0x1800bd416  jnz     short loc_1800BD492
0x1800bd418  lea     rcx, [rsp+58h+KeyPath]; KeyPath
0x1800bd41d  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x1800bd424  nop     dword ptr [rax+rax+00h]
0x1800bd429  test    eax, eax
0x1800bd42b  js      short loc_1800BD486
0x1800bd42d  lea     rdx, [rsp+58h+KeyPath]; SourceString
0x1800bd432  mov     rcx, rbx; DestinationString
0x1800bd435  call    cs:__imp_RtlCopyUnicodeString
0x1800bd43c  nop     dword ptr [rax+rax+00h]
0x1800bd441  lea     rcx, [rsp+58h+KeyPath]; UnicodeString
0x1800bd446  call    cs:__imp_RtlFreeUnicodeString
0x1800bd44d  nop     dword ptr [rax+rax+00h]
0x1800bd452  lea     rdx, aClasses_0; "_Classes"
0x1800bd459  mov     rcx, rbx; Destination
0x1800bd45c  call    cs:__imp_RtlAppendUnicodeToString
0x1800bd463  nop     dword ptr [rax+rax+00h]
0x1800bd468  test    eax, eax
0x1800bd46a  js      short loc_1800BD486
0x1800bd46c  movzx   eax, word ptr [rbx]
0x1800bd46f  lea     rdx, [rsp+58h+Source]; Source
0x1800bd474  mov     rcx, rbx; Destination
0x1800bd477  mov     [rdi], ax
0x1800bd47a  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800bd481  nop     dword ptr [rax+rax+00h]
0x1800bd486  mov     rbx, [rsp+58h+arg_0]
0x1800bd48b  add     rsp, 50h
0x1800bd48f  pop     rdi
0x1800bd490  retn
0x1800bd492  lea     rax, [r9+20h]
0x1800bd496  mov     [rsp+58h+KeyPath.Buffer], rax
0x1800bd49b  lea     rdx, aRegistryUser; "\\Registry\\User"
0x1800bd4a2  movzx   eax, word ptr [rcx+6]
0x1800bd4a6  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1800bd4ab  sub     ax, 2Ch ; ','
0x1800bd4af  mov     [rsp+58h+KeyPath.Length], ax
0x1800bd4b4  call    cs:__imp_RtlInitUnicodeStringEx
0x1800bd4bb  nop     dword ptr [rax+rax+00h]
0x1800bd4c0  lea     rdx, [rsp+58h+DestinationString]; SourceString
0x1800bd4c5  mov     rcx, rbx; DestinationString
0x1800bd4c8  call    cs:__imp_RtlCopyUnicodeString
0x1800bd4cf  nop     dword ptr [rax+rax+00h]
0x1800bd4d4  lea     rdx, [rsp+58h+KeyPath]; Source
0x1800bd4d9  mov     rcx, rbx; Destination
0x1800bd4dc  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800bd4e3  nop     dword ptr [rax+rax+00h]
0x1800bd4e8  test    eax, eax
0x1800bd4ea  jns     loc_1800BD452
0x1800bd4f0  jmp     short loc_1800BD486
0x1800bd4f2  xor     eax, eax
0x1800bd4f4  movzx   edx, ax
0x1800bd4f7  xor     r8d, r8d
0x1800bd4fa  jmp     loc_1800BD3E6
```
