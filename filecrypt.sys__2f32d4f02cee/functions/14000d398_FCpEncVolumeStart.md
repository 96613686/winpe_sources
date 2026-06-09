# FCpEncVolumeStart

- ea: `0x14000d398`
- end: `0x14000d4c1`
- name: `FCpEncVolumeStart`
- size: `297`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140012310`

## callees

- `0x14000d370`
- `0x14000d398`

## import_xrefs

- `ksecdd!BCryptSetProperty` at `0x14000d48b`
- `ksecdd!BCryptSetProperty` at `0x14000d48b`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000d3cc`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000d3cc`
- `ksecdd!BCryptGetProperty` at `0x14000d408`
- `ksecdd!BCryptGetProperty` at `0x14000d453`
- `ksecdd!BCryptGetProperty` at `0x14000d408`
- `ksecdd!BCryptGetProperty` at `0x14000d453`

## pseudocode

```c
__int64 __fastcall FCpEncVolumeStart(__int64 a1)
{
  NTSTATUS Property; // ebx
  int v3; // ecx
  BCRYPT_ALG_HANDLE v4; // rcx
  int pbOutput; // [rsp+40h] [rbp+8h] BYREF
  ULONG pcbResult; // [rsp+48h] [rbp+10h] BYREF

  pcbResult = 0;
  pbOutput = 0;
  Property = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)a1, L"AES", 0, 1u);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(*(BCRYPT_HANDLE *)a1, L"BlockLength", (PUCHAR)(a1 + 12), 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      v3 = *(_DWORD *)(a1 + 12);
      if ( !v3 || ((v3 - 1) & v3) != 0 )
      {
        Property = -1073741453;
      }
      else
      {
        Property = BCryptGetProperty(*(BCRYPT_HANDLE *)a1, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
        if ( Property >= 0 )
        {
          v4 = *(BCRYPT_ALG_HANDLE *)a1;
          *(_DWORD *)(a1 + 8) = pbOutput;
          Property = BCryptSetProperty(v4, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
          if ( Property >= 0 )
            return 0;
        }
      }
    }
  }
  FCpEncVolumeCleanup(a1);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x14000d398  mov     rax, rsp
0x14000d39b  mov     [rax+18h], rbx
0x14000d39f  mov     [rax+20h], rsi
0x14000d3a3  mov     [rax+10h], edx
0x14000d3a6  push    rdi
0x14000d3a7  sub     rsp, 30h
0x14000d3ab  mov     r9d, 1; dwFlags
0x14000d3b1  mov     dword ptr [rax+10h], 0
0x14000d3b8  xor     r8d, r8d; pszImplementation
0x14000d3bb  mov     dword ptr [rax+8], 0
0x14000d3c2  lea     rdx, pszAlgId; "AES"
0x14000d3c9  mov     rdi, rcx
0x14000d3cc  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000d3d3  nop     dword ptr [rax+rax+00h]
0x14000d3d8  mov     ebx, eax
0x14000d3da  test    eax, eax
0x14000d3dc  js      loc_14000D4A6
0x14000d3e2  mov     rcx, [rdi]; hObject
0x14000d3e5  lea     rax, [rsp+38h+arg_8]
0x14000d3ea  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14000d3f2  lea     r8, [rdi+0Ch]; pbOutput
0x14000d3f6  mov     r9d, 4; cbOutput
0x14000d3fc  mov     [rsp+38h+pcbResult], rax; pcbResult
0x14000d401  lea     rdx, pszProperty; "BlockLength"
0x14000d408  call    cs:__imp_BCryptGetProperty
0x14000d40f  nop     dword ptr [rax+rax+00h]
0x14000d414  mov     ebx, eax
0x14000d416  test    eax, eax
0x14000d418  js      loc_14000D4A6
0x14000d41e  mov     ecx, [rdi+0Ch]
0x14000d421  test    ecx, ecx
0x14000d423  jz      short loc_14000D4A1
0x14000d425  lea     eax, [rcx-1]
0x14000d428  test    ecx, eax
0x14000d42a  jnz     short loc_14000D4A1
0x14000d42c  mov     rcx, [rdi]; hObject
0x14000d42f  lea     rax, [rsp+38h+arg_8]
0x14000d434  mov     [rsp+38h+dwFlags], 0; dwFlags
0x14000d43c  lea     r8, [rsp+38h+pbOutput]; pbOutput
0x14000d441  mov     r9d, 4; cbOutput
0x14000d447  mov     [rsp+38h+pcbResult], rax; pcbResult
0x14000d44c  lea     rdx, aObjectlength; "ObjectLength"
0x14000d453  call    cs:__imp_BCryptGetProperty
0x14000d45a  nop     dword ptr [rax+rax+00h]
0x14000d45f  mov     ebx, eax
0x14000d461  test    eax, eax
0x14000d463  js      short loc_14000D4A6
0x14000d465  mov     eax, [rsp+38h+pbOutput]
0x14000d469  lea     r8, pbInput; "ChainingModeCBC"
0x14000d470  mov     rcx, [rdi]; hObject
0x14000d473  lea     rdx, aChainingmode; "ChainingMode"
0x14000d47a  mov     r9d, 20h ; ' '; cbInput
0x14000d480  mov     [rdi+8], eax
0x14000d483  mov     dword ptr [rsp+38h+pcbResult], 0; dwFlags
0x14000d48b  call    cs:__imp_BCryptSetProperty
0x14000d492  nop     dword ptr [rax+rax+00h]
0x14000d497  mov     ebx, eax
0x14000d499  test    eax, eax
0x14000d49b  js      short loc_14000D4A6
0x14000d49d  xor     eax, eax
0x14000d49f  jmp     short loc_14000D4B0
0x14000d4a1  mov     ebx, 0C0000173h
0x14000d4a6  mov     rcx, rdi
0x14000d4a9  call    FCpEncVolumeCleanup
0x14000d4ae  mov     eax, ebx
0x14000d4b0  mov     rbx, [rsp+38h+arg_10]
0x14000d4b5  mov     rsi, [rsp+38h+arg_18]
0x14000d4ba  add     rsp, 30h
0x14000d4be  pop     rdi
0x14000d4bf  retn
```
