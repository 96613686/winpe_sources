# DriverAllowedByPluginControlPolicy

- ea: `0x1800066b0`
- end: `0x18000674b`
- name: `DriverAllowedByPluginControlPolicy`
- size: `155`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005f60`

## callees

- `0x1800066b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006717`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006717`
- `api-ms-win-appmodel-runtime-l1-1-2!AppPolicyGetMediaFoundationCodecLoading` at `0x1800066cd`
- `api-ms-win-appmodel-runtime-l1-1-2!AppPolicyGetMediaFoundationCodecLoading` at `0x1800066cd`

## pseudocode

```c
__int64 __fastcall DriverAllowedByPluginControlPolicy(LPCWCH lpString1)
{
  __int64 i; // rbx
  AppPolicyMediaFoundationCodecLoading policy; // [rsp+48h] [rbp+10h] BYREF

  policy = AppPolicyMediaFoundationCodecLoading_All;
  AppPolicyGetMediaFoundationCodecLoading((HANDLE)0xFFFFFFFFFFFFFFFALL, &policy);
  if ( policy != AppPolicyMediaFoundationCodecLoading_InboxOnly )
    return 1;
  for ( i = 0; (unsigned int)i < 8; i = (unsigned int)(i + 1) )
  {
    if ( CompareStringOrdinal(lpString1, -1, off_180014000[i], -1, 1) == 2 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800066b0  push    rsi
0x1800066b2  sub     rsp, 30h
0x1800066b6  mov     rsi, rcx
0x1800066b9  mov     [rsp+38h+policy], 0
0x1800066c1  mov     rcx, 0FFFFFFFFFFFFFFFAh; processToken
0x1800066c8  lea     rdx, [rsp+38h+policy]; policy
0x1800066cd  call    cs:__imp_AppPolicyGetMediaFoundationCodecLoading
0x1800066d3  mov     edx, [rsp+38h+policy]
0x1800066d7  test    edx, edx
0x1800066d9  jz      short loc_180006744
0x1800066db  cmp     edx, 1
0x1800066de  jnz     short loc_180006744
0x1800066e0  mov     [rsp+38h+arg_0], rbx
0x1800066e5  mov     [rsp+38h+arg_10], rdi
0x1800066ea  xor     edi, edi
0x1800066ec  mov     [rsp+38h+arg_18], r14
0x1800066f1  xor     ebx, ebx
0x1800066f3  lea     r14, off_180014000; "msacm.imaadpcm"
0x1800066fa  cmp     ebx, 8
0x1800066fd  jnb     short loc_180006740
0x1800066ff  mov     r8, [r14+rbx*8]; lpString2
0x180006703  mov     r9d, 0FFFFFFFFh; cchCount2
0x180006709  mov     edx, r9d; cchCount1
0x18000670c  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180006714  mov     rcx, rsi; lpString1
0x180006717  call    cs:__imp_CompareStringOrdinal
0x18000671d  cmp     eax, 2
0x180006720  jz      short loc_180006726
0x180006722  inc     ebx
0x180006724  jmp     short loc_1800066FA
0x180006726  mov     eax, 1
0x18000672b  mov     rdi, [rsp+38h+arg_10]
0x180006730  mov     rbx, [rsp+38h+arg_0]
0x180006735  mov     r14, [rsp+38h+arg_18]
0x18000673a  add     rsp, 30h
0x18000673e  pop     rsi
0x18000673f  retn
0x180006740  mov     eax, edi
0x180006742  jmp     short loc_18000672B
0x180006744  mov     eax, 1
0x180006749  jmp     short loc_18000673A
```
