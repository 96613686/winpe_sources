# CipLoadOneExtensionConfig

- ea: `0x1800723c4`
- end: `0x1800724b0`
- name: `CipLoadOneExtensionConfig`
- size: `236`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180072070`

## callees

- `0x180071b60`
- `0x180071c4c`
- `0x1800723c4`
- `0x18007277c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180072465`
- `ntoskrnl!RtlInitUnicodeString` at `0x180072465`
- `ntoskrnl!ExAllocatePool2` at `0x1800723fb`
- `ntoskrnl!ExAllocatePool2` at `0x1800723fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072494`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072494`

## string_xrefs

- `0x18007243c`: `PolicyPath`

## pseudocode

```c
__int64 __fastcall CipLoadOneExtensionConfig(
        PCUNICODE_STRING SourceString,
        PCUNICODE_STRING Source,
        struct _UNICODE_STRING **a3)
{
  WCHAR *v3; // rbx
  struct _UNICODE_STRING *v7; // rsi
  int RegistryValue2; // edi
  __int64 v9; // rcx
  PCWSTR SourceStringa; // [rsp+30h] [rbp-28h] BYREF
  __int64 Pool2; // [rsp+38h] [rbp-20h] BYREF
  __int128 v13; // [rsp+40h] [rbp-18h]
  int v14; // [rsp+A8h] [rbp+50h] BYREF

  v3 = 0;
  SourceStringa = 0;
  v14 = 0;
  v13 = 0;
  Pool2 = ExAllocatePool2(256, 32, 1668499779);
  v7 = (struct _UNICODE_STRING *)Pool2;
  if ( Pool2 )
  {
    RegistryValue2 = CipBuildRegistryPath(SourceString, Source);
    if ( RegistryValue2 >= 0 )
    {
      RegistryValue2 = CipGetRegistryValue2(v9, *((_WORD **)&v13 + 1), (__int64)L"PolicyPath", 2, &SourceStringa, &v14);
      if ( RegistryValue2 < 0 )
      {
        v3 = (WCHAR *)SourceStringa;
      }
      else
      {
        RtlInitUnicodeString(v7 + 1, SourceStringa);
        *a3 = v7;
        Pool2 = 0;
      }
    }
  }
  else
  {
    RegistryValue2 = -1073741801;
  }
  CipFreeExtRegistry(&Pool2);
  if ( v3 )
    ExFreePoolWithTag(v3, 0x63734943u);
  return (unsigned int)RegistryValue2;
}

```

## disassembly

```asm
0x1800723c4  push    rbp
0x1800723c6  push    rbx
0x1800723c7  push    rsi
0x1800723c8  push    rdi
0x1800723c9  push    r14
0x1800723cb  push    r15
0x1800723cd  mov     rbp, rsp
0x1800723d0  sub     rsp, 58h
0x1800723d4  xor     ebx, ebx
0x1800723d6  mov     r14, r8
0x1800723d9  mov     rdi, rdx
0x1800723dc  mov     [rbp+SourceString], rbx
0x1800723e0  mov     r15, rcx
0x1800723e3  mov     [rbp+arg_18], ebx
0x1800723e6  xorps   xmm0, xmm0
0x1800723e9  mov     ecx, 100h
0x1800723ee  lea     edx, [rbx+20h]
0x1800723f1  mov     r8d, 63734943h
0x1800723f7  movups  [rbp+var_18], xmm0
0x1800723fb  call    cs:__imp_ExAllocatePool2
0x180072402  nop     dword ptr [rax+rax+00h]
0x180072407  mov     [rbp+var_20], rax
0x18007240b  mov     rsi, rax
0x18007240e  test    rax, rax
0x180072411  jnz     short loc_18007241A
0x180072413  mov     edi, 0C0000017h
0x180072418  jmp     short loc_18007247E
0x18007241a  lea     r8, [rbp+var_18]
0x18007241e  mov     rdx, rdi; Source
0x180072421  mov     rcx, r15; SourceString
0x180072424  call    CipBuildRegistryPath
0x180072429  mov     edi, eax
0x18007242b  test    eax, eax
0x18007242d  js      short loc_18007247E
0x18007242f  mov     rdx, qword ptr [rbp+var_18+8]
0x180072433  lea     rax, [rbp+arg_18]
0x180072437  mov     [rsp+58h+var_30], rax
0x18007243c  lea     r8, aPolicypath; "PolicyPath"
0x180072443  lea     rax, [rbp+SourceString]
0x180072447  mov     r9d, 2
0x18007244d  mov     [rsp+58h+var_38], rax
0x180072452  call    CipGetRegistryValue2
0x180072457  mov     edi, eax
0x180072459  test    eax, eax
0x18007245b  js      short loc_18007247A
0x18007245d  mov     rdx, [rbp+SourceString]; SourceString
0x180072461  lea     rcx, [rsi+10h]; DestinationString
0x180072465  call    cs:__imp_RtlInitUnicodeString
0x18007246c  nop     dword ptr [rax+rax+00h]
0x180072471  mov     [r14], rsi
0x180072474  mov     [rbp+var_20], rbx
0x180072478  jmp     short loc_18007247E
0x18007247a  mov     rbx, [rbp+SourceString]
0x18007247e  lea     rcx, [rbp+var_20]
0x180072482  call    CipFreeExtRegistry
0x180072487  test    rbx, rbx
0x18007248a  jz      short loc_1800724A0
0x18007248c  mov     edx, 63734943h; Tag
0x180072491  mov     rcx, rbx; P
0x180072494  call    cs:__imp_ExFreePoolWithTag
0x18007249b  nop     dword ptr [rax+rax+00h]
0x1800724a0  mov     eax, edi
0x1800724a2  add     rsp, 58h
0x1800724a6  pop     r15
0x1800724a8  pop     r14
0x1800724aa  pop     rdi
0x1800724ab  pop     rsi
0x1800724ac  pop     rbx
0x1800724ad  pop     rbp
0x1800724ae  retn
```
