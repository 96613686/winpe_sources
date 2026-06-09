# HvSocketUpdateProviderProperties

- ea: `0x14001b140`
- end: `0x14001b1ee`
- name: `HvSocketUpdateProviderProperties`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x140009cf8`
- `0x14001b140`
- `0x14002052c`
- `0x1400267c8`

## string_xrefs

- `0x14001b174`: `Failed to set HvSocket provider wildcard descriptors.`
- `0x14001b183`: `HvSocketUpdateProviderProperties`
- `0x14001b1d4`: `HvSocketUpdateProviderProperties`

## pseudocode

```c
__int64 __fastcall HvSocketUpdateProviderProperties(__int64 a1, __int64 a2)
{
  unsigned int v2; // r8d
  __int64 v5; // rdx
  int updated; // eax
  GUID v7; // xmm1
  int v8; // eax
  unsigned int v9; // ebx
  GUID v11; // [rsp+20h] [rbp-28h] BYREF
  GUID v12; // [rsp+30h] [rbp-18h] BYREF

  v2 = *(_DWORD *)(a2 + 32);
  if ( v2 >= 0x18 )
  {
    v5 = a2 + 40;
    if ( v5 )
    {
      updated = VmbusTlUpdateWildcardDescriptorList(a1, v5, v2);
      if ( updated < 0 && (unsigned int)dword_140013058 > 2 )
        HvsocketTraceError(
          "HvSocketUpdateProviderProperties",
          522,
          (unsigned int)updated,
          "Failed to set HvSocket provider wildcard descriptors.");
    }
  }
  v7 = *(GUID *)a2;
  v11 = *(GUID *)(a2 + 16);
  v12 = v7;
  v8 = HvSocketProviderUpdateAddresses(a1, &v12, &v11);
  v9 = v8;
  if ( v8 < 0 && (unsigned int)dword_140013058 > 2 )
    HvsocketTraceError(
      "HvSocketUpdateProviderProperties",
      531,
      (unsigned int)v8,
      "Failed to set HvSocket provider addressses.");
  return v9;
}

```

## disassembly

```asm
0x14001b140  mov     [rsp+arg_0], rbx
0x14001b145  push    rdi
0x14001b146  sub     rsp, 40h
0x14001b14a  mov     r8d, [rdx+20h]
0x14001b14e  mov     rbx, rdx
0x14001b151  mov     rdi, rcx
0x14001b154  cmp     r8d, 18h
0x14001b158  jb      short loc_14001B18F
0x14001b15a  add     rdx, 28h ; '('
0x14001b15e  jz      short loc_14001B18F
0x14001b160  call    VmbusTlUpdateWildcardDescriptorList
0x14001b165  test    eax, eax
0x14001b167  jns     short loc_14001B18F
0x14001b169  mov     ecx, cs:dword_140013058
0x14001b16f  cmp     ecx, 2
0x14001b172  jbe     short loc_14001B18F
0x14001b174  lea     r9, aFailedToSetHvs; "Failed to set HvSocket provider wildcar"...
0x14001b17b  mov     r8d, eax
0x14001b17e  mov     edx, 20Ah
0x14001b183  lea     rcx, aHvsocketupdate_1; "HvSocketUpdateProviderProperties"
0x14001b18a  call    HvsocketTraceError
0x14001b18f  movups  xmm0, xmmword ptr [rbx+10h]
0x14001b193  lea     r8, [rsp+48h+var_28]
0x14001b198  mov     rcx, rdi
0x14001b19b  movups  xmm1, xmmword ptr [rbx]
0x14001b19e  lea     rdx, [rsp+48h+var_18]
0x14001b1a3  movdqu  [rsp+48h+var_28], xmm0
0x14001b1a9  movdqu  xmmword ptr [rsp+48h+var_18.Data1], xmm1
0x14001b1af  call    HvSocketProviderUpdateAddresses
0x14001b1b4  mov     ebx, eax
0x14001b1b6  test    eax, eax
0x14001b1b8  jns     short loc_14001B1E0
0x14001b1ba  mov     edx, cs:dword_140013058
0x14001b1c0  cmp     edx, 2
0x14001b1c3  jbe     short loc_14001B1E0
0x14001b1c5  lea     r9, aFailedToSetHvs_0; "Failed to set HvSocket provider address"...
0x14001b1cc  mov     r8d, eax
0x14001b1cf  mov     edx, 213h
0x14001b1d4  lea     rcx, aHvsocketupdate_1; "HvSocketUpdateProviderProperties"
0x14001b1db  call    HvsocketTraceError
0x14001b1e0  mov     eax, ebx
0x14001b1e2  mov     rbx, [rsp+48h+arg_0]
0x14001b1e7  add     rsp, 40h
0x14001b1eb  pop     rdi
0x14001b1ec  retn
```
