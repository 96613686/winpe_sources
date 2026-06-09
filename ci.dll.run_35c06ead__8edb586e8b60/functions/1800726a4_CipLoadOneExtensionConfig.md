# CipLoadOneExtensionConfig

- ea: `0x1800726a4`
- end: `0x180072790`
- name: `CipLoadOneExtensionConfig`
- size: `236`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180072350`

## callees

- `0x180071e40`
- `0x180071f2c`
- `0x1800726a4`
- `0x180072a5c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180072745`
- `ntoskrnl!RtlInitUnicodeString` at `0x180072745`
- `ntoskrnl!ExAllocatePool2` at `0x1800726db`
- `ntoskrnl!ExAllocatePool2` at `0x1800726db`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072774`
- `ntoskrnl!ExFreePoolWithTag` at `0x180072774`

## string_xrefs

- `0x18007271c`: `PolicyPath`

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
0x1800726a4  push    rbp
0x1800726a6  push    rbx
0x1800726a7  push    rsi
0x1800726a8  push    rdi
0x1800726a9  push    r14
0x1800726ab  push    r15
0x1800726ad  mov     rbp, rsp
0x1800726b0  sub     rsp, 58h
0x1800726b4  xor     ebx, ebx
0x1800726b6  mov     r14, r8
0x1800726b9  mov     rdi, rdx
0x1800726bc  mov     [rbp+SourceString], rbx
0x1800726c0  mov     r15, rcx
0x1800726c3  mov     [rbp+arg_18], ebx
0x1800726c6  xorps   xmm0, xmm0
0x1800726c9  mov     ecx, 100h
0x1800726ce  lea     edx, [rbx+20h]
0x1800726d1  mov     r8d, 63734943h
0x1800726d7  movups  [rbp+var_18], xmm0
0x1800726db  call    cs:__imp_ExAllocatePool2
0x1800726e2  nop     dword ptr [rax+rax+00h]
0x1800726e7  mov     [rbp+var_20], rax
0x1800726eb  mov     rsi, rax
0x1800726ee  test    rax, rax
0x1800726f1  jnz     short loc_1800726FA
0x1800726f3  mov     edi, 0C0000017h
0x1800726f8  jmp     short loc_18007275E
0x1800726fa  lea     r8, [rbp+var_18]
0x1800726fe  mov     rdx, rdi; Source
0x180072701  mov     rcx, r15; SourceString
0x180072704  call    CipBuildRegistryPath
0x180072709  mov     edi, eax
0x18007270b  test    eax, eax
0x18007270d  js      short loc_18007275E
0x18007270f  mov     rdx, qword ptr [rbp+var_18+8]
0x180072713  lea     rax, [rbp+arg_18]
0x180072717  mov     [rsp+58h+var_30], rax
0x18007271c  lea     r8, aPolicypath; "PolicyPath"
0x180072723  lea     rax, [rbp+SourceString]
0x180072727  mov     r9d, 2
0x18007272d  mov     [rsp+58h+var_38], rax
0x180072732  call    CipGetRegistryValue2
0x180072737  mov     edi, eax
0x180072739  test    eax, eax
0x18007273b  js      short loc_18007275A
0x18007273d  mov     rdx, [rbp+SourceString]; SourceString
0x180072741  lea     rcx, [rsi+10h]; DestinationString
0x180072745  call    cs:__imp_RtlInitUnicodeString
0x18007274c  nop     dword ptr [rax+rax+00h]
0x180072751  mov     [r14], rsi
0x180072754  mov     [rbp+var_20], rbx
0x180072758  jmp     short loc_18007275E
0x18007275a  mov     rbx, [rbp+SourceString]
0x18007275e  lea     rcx, [rbp+var_20]
0x180072762  call    CipFreeExtRegistry
0x180072767  test    rbx, rbx
0x18007276a  jz      short loc_180072780
0x18007276c  mov     edx, 63734943h; Tag
0x180072771  mov     rcx, rbx; P
0x180072774  call    cs:__imp_ExFreePoolWithTag
0x18007277b  nop     dword ptr [rax+rax+00h]
0x180072780  mov     eax, edi
0x180072782  add     rsp, 58h
0x180072786  pop     r15
0x180072788  pop     r14
0x18007278a  pop     rdi
0x18007278b  pop     rsi
0x18007278c  pop     rbx
0x18007278d  pop     rbp
0x18007278e  retn
```
