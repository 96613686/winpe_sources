# CipLoadOneExtensionConfig

- ea: `0x180071114`
- end: `0x180071200`
- name: `CipLoadOneExtensionConfig`
- size: `236`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180070dc0`

## callees

- `0x1800708b0`
- `0x18007099c`
- `0x180071114`
- `0x1800714cc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800711b5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800711b5`
- `ntoskrnl!ExAllocatePool2` at `0x18007114b`
- `ntoskrnl!ExAllocatePool2` at `0x18007114b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800711e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800711e4`

## string_xrefs

- `0x18007118c`: `PolicyPath`

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
0x180071114  push    rbp
0x180071116  push    rbx
0x180071117  push    rsi
0x180071118  push    rdi
0x180071119  push    r14
0x18007111b  push    r15
0x18007111d  mov     rbp, rsp
0x180071120  sub     rsp, 58h
0x180071124  xor     ebx, ebx
0x180071126  mov     r14, r8
0x180071129  mov     rdi, rdx
0x18007112c  mov     [rbp+SourceString], rbx
0x180071130  mov     r15, rcx
0x180071133  mov     [rbp+arg_18], ebx
0x180071136  xorps   xmm0, xmm0
0x180071139  mov     ecx, 100h
0x18007113e  lea     edx, [rbx+20h]
0x180071141  mov     r8d, 63734943h
0x180071147  movups  [rbp+var_18], xmm0
0x18007114b  call    cs:__imp_ExAllocatePool2
0x180071152  nop     dword ptr [rax+rax+00h]
0x180071157  mov     [rbp+var_20], rax
0x18007115b  mov     rsi, rax
0x18007115e  test    rax, rax
0x180071161  jnz     short loc_18007116A
0x180071163  mov     edi, 0C0000017h
0x180071168  jmp     short loc_1800711CE
0x18007116a  lea     r8, [rbp+var_18]
0x18007116e  mov     rdx, rdi; Source
0x180071171  mov     rcx, r15; SourceString
0x180071174  call    CipBuildRegistryPath
0x180071179  mov     edi, eax
0x18007117b  test    eax, eax
0x18007117d  js      short loc_1800711CE
0x18007117f  mov     rdx, qword ptr [rbp+var_18+8]
0x180071183  lea     rax, [rbp+arg_18]
0x180071187  mov     [rsp+58h+var_30], rax
0x18007118c  lea     r8, aPolicypath; "PolicyPath"
0x180071193  lea     rax, [rbp+SourceString]
0x180071197  mov     r9d, 2
0x18007119d  mov     [rsp+58h+var_38], rax
0x1800711a2  call    CipGetRegistryValue2
0x1800711a7  mov     edi, eax
0x1800711a9  test    eax, eax
0x1800711ab  js      short loc_1800711CA
0x1800711ad  mov     rdx, [rbp+SourceString]; SourceString
0x1800711b1  lea     rcx, [rsi+10h]; DestinationString
0x1800711b5  call    cs:__imp_RtlInitUnicodeString
0x1800711bc  nop     dword ptr [rax+rax+00h]
0x1800711c1  mov     [r14], rsi
0x1800711c4  mov     [rbp+var_20], rbx
0x1800711c8  jmp     short loc_1800711CE
0x1800711ca  mov     rbx, [rbp+SourceString]
0x1800711ce  lea     rcx, [rbp+var_20]
0x1800711d2  call    CipFreeExtRegistry
0x1800711d7  test    rbx, rbx
0x1800711da  jz      short loc_1800711F0
0x1800711dc  mov     edx, 63734943h; Tag
0x1800711e1  mov     rcx, rbx; P
0x1800711e4  call    cs:__imp_ExFreePoolWithTag
0x1800711eb  nop     dword ptr [rax+rax+00h]
0x1800711f0  mov     eax, edi
0x1800711f2  add     rsp, 58h
0x1800711f6  pop     r15
0x1800711f8  pop     r14
0x1800711fa  pop     rdi
0x1800711fb  pop     rsi
0x1800711fc  pop     rbx
0x1800711fd  pop     rbp
0x1800711fe  retn
```
