# CCertTypeInfo::IsPropertyV3OrRepurposed(ushort const *)

- ea: `0x18000f3a0`
- end: `0x18000f419`
- name: `?IsPropertyV3OrRepurposed@CCertTypeInfo@@QEAAHPEBG@Z`
- size: `121`
- prototype: `__int64 __fastcall(CCertTypeInfo *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800113e0`

## callees

- `0x18000f3a0`
- `0x180038286`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f3e4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f3e4`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::IsPropertyV3OrRepurposed(CCertTypeInfo *this, const unsigned __int16 *a2)
{
  unsigned int v2; // edi
  unsigned int v5; // ebx

  v2 = 0;
  v5 = 1;
  while ( v2 < 6 )
  {
    if ( CompareStringW(0x7Fu, 1u, a2, -1, (PCNZWCH)*(&g_CTV3Properties + 2 * v2), -1) == 2 )
      return v5;
    ++v2;
  }
  if ( *((_DWORD *)this + 22) <= 2u || wcscmp_0(a2, L"msPKI-RA-Application-Policies") )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x18000f3a0  push    rbx
0x18000f3a2  push    rbp
0x18000f3a3  push    rsi
0x18000f3a4  push    rdi
0x18000f3a5  sub     rsp, 38h
0x18000f3a9  xor     edi, edi
0x18000f3ab  mov     rsi, rdx
0x18000f3ae  mov     rbp, rcx
0x18000f3b1  lea     ebx, [rdi+1]
0x18000f3b4  cmp     edi, 6
0x18000f3b7  jnb     short loc_18000F3F3
0x18000f3b9  lea     rcx, ?g_CTV3Properties@@3PAU_CERT_TYPE_PROP_INFO@@A; _CERT_TYPE_PROP_INFO near * g_CTV3Properties
0x18000f3c0  mov     eax, edi
0x18000f3c2  add     rax, rax
0x18000f3c5  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000f3cd  or      r9d, 0FFFFFFFFh; cchCount1
0x18000f3d1  mov     r8, rsi; lpString1
0x18000f3d4  mov     edx, ebx; dwCmpFlags
0x18000f3d6  mov     rax, [rcx+rax*8]
0x18000f3da  mov     ecx, 7Fh; Locale
0x18000f3df  mov     [rsp+58h+lpString2], rax; lpString2
0x18000f3e4  call    cs:__imp_CompareStringW
0x18000f3ea  cmp     eax, 2
0x18000f3ed  jz      short loc_18000F40E
0x18000f3ef  add     edi, ebx
0x18000f3f1  jmp     short loc_18000F3B4
0x18000f3f3  cmp     dword ptr [rbp+58h], 2
0x18000f3f7  jbe     short loc_18000F40C
0x18000f3f9  lea     rdx, aMspkiRaApplica; "msPKI-RA-Application-Policies"
0x18000f400  mov     rcx, rsi; String1
0x18000f403  call    wcscmp_0
0x18000f408  test    eax, eax
0x18000f40a  jz      short loc_18000F40E
0x18000f40c  xor     ebx, ebx
0x18000f40e  mov     eax, ebx
0x18000f410  add     rsp, 38h
0x18000f414  pop     rdi
0x18000f415  pop     rsi
0x18000f416  pop     rbp
0x18000f417  pop     rbx
0x18000f418  retn
```
