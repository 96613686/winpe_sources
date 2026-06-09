# SmbConstructNetRootExchangeCopyDataHandler

- ea: `0x14000fde0`
- end: `0x14000fed4`
- name: `SmbConstructNetRootExchangeCopyDataHandler`
- size: `244`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140005fe0`
- `0x14000dfd8`
- `0x14000fde0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000fe1e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000fe1e`

## pseudocode

```c
__int64 __fastcall SmbConstructNetRootExchangeCopyDataHandler(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // edi
  __int64 v5; // rcx
  PVOID v7; // rax
  unsigned int v8; // eax
  unsigned int v10; // [rsp+70h] [rbp+18h] BYREF

  v3 = 0;
  v5 = *(_QWORD *)(a1 + 384);
  v10 = 0;
  if ( (*(_BYTE *)(v5 + 10) & 5) != 0 )
    v7 = *(PVOID *)(v5 + 24);
  else
    v7 = MmMapLockedPagesSpecifyCache((PMDL)v5, 0, MmCached, 0, 0, 0x40000000u);
  if ( v7 )
  {
    v8 = SmbCeParseConstructNetRootResponse(a1, (__int64)v7, a3, a3, &v10);
    *(_DWORD *)(a1 + 48) = v8;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids, v8);
    if ( *(_DWORD *)(a1 + 48) == -1073741802 )
      *(_DWORD *)(a1 + 48) = -1073741629;
  }
  else
  {
    v3 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids, v10);
  return v3;
}

```

## disassembly

```asm
0x14000fde0  push    rbx
0x14000fde2  push    rsi
0x14000fde3  push    rdi
0x14000fde4  push    r14
0x14000fde6  sub     rsp, 38h
0x14000fdea  xor     edi, edi
0x14000fdec  mov     rbx, rcx
0x14000fdef  mov     rcx, [rcx+180h]; MemoryDescriptorList
0x14000fdf6  mov     esi, r8d
0x14000fdf9  mov     [rsp+58h+arg_10], edi
0x14000fdfd  test    byte ptr [rcx+0Ah], 5
0x14000fe01  jz      short loc_14000FE09
0x14000fe03  mov     rax, [rcx+18h]
0x14000fe07  jmp     short loc_14000FE2A
0x14000fe09  xor     r9d, r9d; RequestedAddress
0x14000fe0c  mov     [rsp+58h+Priority], 40000000h; Priority
0x14000fe14  xor     edx, edx; AccessMode
0x14000fe16  mov     [rsp+58h+BugCheckOnFailure], edi; BugCheckOnFailure
0x14000fe1a  lea     r8d, [r9+1]; CacheType
0x14000fe1e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000fe25  nop     dword ptr [rax+rax+00h]
0x14000fe2a  lea     r14, WPP_GLOBAL_Control
0x14000fe31  test    rax, rax
0x14000fe34  jz      short loc_14000FE93
0x14000fe36  lea     rcx, [rsp+58h+arg_10]
0x14000fe3b  mov     r9d, esi
0x14000fe3e  mov     qword ptr [rsp+58h+BugCheckOnFailure], rcx
0x14000fe43  mov     r8d, esi
0x14000fe46  mov     rcx, rbx
0x14000fe49  mov     rdx, rax
0x14000fe4c  call    SmbCeParseConstructNetRootResponse
0x14000fe51  mov     [rbx+30h], eax
0x14000fe54  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000fe5b  cmp     rcx, r14
0x14000fe5e  jz      short loc_14000FE81
0x14000fe60  test    dword ptr [rcx+2Ch], 400h
0x14000fe67  jz      short loc_14000FE81
0x14000fe69  mov     rcx, [rcx+18h]
0x14000fe6d  lea     r8, WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids
0x14000fe74  mov     edx, 17h
0x14000fe79  mov     r9d, eax
0x14000fe7c  call    WPP_SF_d
0x14000fe81  cmp     dword ptr [rbx+30h], 0C0000016h
0x14000fe88  jnz     short loc_14000FE98
0x14000fe8a  mov     dword ptr [rbx+30h], 0C00000C3h
0x14000fe91  jmp     short loc_14000FE98
0x14000fe93  mov     edi, 0C000009Ah
0x14000fe98  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000fe9f  cmp     rcx, r14
0x14000fea2  jz      short loc_14000FEC7
0x14000fea4  test    dword ptr [rcx+2Ch], 400h
0x14000feab  jz      short loc_14000FEC7
0x14000fead  mov     r9d, [rsp+58h+arg_10]
0x14000feb2  lea     r8, WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids
0x14000feb9  mov     rcx, [rcx+18h]
0x14000febd  mov     edx, 18h
0x14000fec2  call    WPP_SF_d
0x14000fec7  mov     eax, edi
0x14000fec9  add     rsp, 38h
0x14000fecd  pop     r14
0x14000fecf  pop     rdi
0x14000fed0  pop     rsi
0x14000fed1  pop     rbx
0x14000fed2  retn
```
