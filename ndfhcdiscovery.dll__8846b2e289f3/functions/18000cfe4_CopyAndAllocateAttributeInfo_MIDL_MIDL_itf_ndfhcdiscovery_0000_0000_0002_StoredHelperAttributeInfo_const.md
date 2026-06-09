# CopyAndAllocateAttributeInfo(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002 *,StoredHelperAttributeInfo const *)

- ea: `0x18000cfe4`
- end: `0x18000d0b4`
- name: `?CopyAndAllocateAttributeInfo@@YAJPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002@@PEBUStoredHelperAttributeInfo@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(unsigned __int16 **, const struct StoredHelperAttributeInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b90c`

## callees

- `0x18000cfe4`
- `0x180010684`
- `0x180011fcc`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x18000d021`
- `KERNEL32!lstrcmpW` at `0x18000d021`

## pseudocode

```c
int __fastcall CopyAndAllocateAttributeInfo(unsigned __int16 **a1, const struct StoredHelperAttributeInfo *a2)
{
  const WCHAR *v2; // rdi
  unsigned __int16 v5; // bp
  ResourceStringLoader *v6; // rcx
  int v7; // eax
  int result; // eax
  const unsigned __int16 *v9; // r8
  const unsigned __int16 *v10; // r8
  unsigned __int16 *v11; // r9
  const unsigned __int16 *v12; // r8
  unsigned __int16 *v13; // r9

  v2 = (const WCHAR *)((char *)a2 + 40);
  *((_DWORD *)a1 + 3) = *(_DWORD *)a2;
  if ( *((_QWORD *)a2 + 8) >= 8u )
    v2 = *(const WCHAR **)v2;
  v5 = 0;
  while ( lstrcmpW(*((LPCWSTR *)&HelperAttributeUtility::s_AttributeTable + 2 * v5), v2) )
  {
    if ( ++v5 >= 0xFu )
    {
      v7 = 0;
      goto LABEL_8;
    }
  }
  v7 = *((_DWORD *)&HelperAttributeUtility::s_AttributeTable + 4 * v5 + 2);
LABEL_8:
  *((_DWORD *)a1 + 2) = v7;
  if ( !v7 )
    return -2147024883;
  v9 = (const unsigned __int16 *)((char *)a2 + 72);
  if ( *((_QWORD *)a2 + 12) >= 8u )
    v9 = *(const unsigned __int16 **)v9;
  result = ResourceStringLoader::LoadStringWithAlloc(v6, a1 + 2, v9);
  if ( result >= 0 )
  {
    v11 = (unsigned __int16 *)((char *)a2 + 8);
    if ( *((_QWORD *)a2 + 4) >= 8u )
      v11 = *(unsigned __int16 **)v11;
    result = UtilAssembleStringsWithAlloc(a1, 0xFFFFu, v10, v11);
    if ( result >= 0 )
    {
      v13 = (unsigned __int16 *)((char *)a2 + 104);
      if ( *((_QWORD *)a2 + 16) >= 8u )
        v13 = *(unsigned __int16 **)v13;
      return UtilAssembleStringsWithAlloc(a1 + 3, 0xFFFFu, v12, v13);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000cfe4  push    rbx
0x18000cfe6  push    rbp
0x18000cfe7  push    rsi
0x18000cfe8  push    rdi
0x18000cfe9  push    r14
0x18000cfeb  push    r15
0x18000cfed  sub     rsp, 38h
0x18000cff1  mov     eax, [rdx]
0x18000cff3  lea     rdi, [rdx+28h]
0x18000cff7  mov     [rcx+0Ch], eax
0x18000cffa  mov     rbx, rdx
0x18000cffd  cmp     qword ptr [rdi+18h], 8
0x18000d002  mov     rsi, rcx
0x18000d005  jb      short loc_18000D00A
0x18000d007  mov     rdi, [rdi]
0x18000d00a  xor     ebp, ebp
0x18000d00c  lea     r15, ?s_AttributeTable@HelperAttributeUtility@@0QBUAttributeTypeTable@@B; AttributeTypeTable const near * const HelperAttributeUtility::s_AttributeTable
0x18000d013  movzx   r14d, bp
0x18000d017  mov     rdx, rdi; lpString2
0x18000d01a  add     r14, r14
0x18000d01d  mov     rcx, [r15+r14*8]; lpString1
0x18000d021  call    cs:__imp_lstrcmpW
0x18000d028  nop     dword ptr [rax+rax+00h]
0x18000d02d  test    eax, eax
0x18000d02f  jz      short loc_18000D03E
0x18000d031  inc     bp
0x18000d034  cmp     bp, 0Fh
0x18000d038  jb      short loc_18000D013
0x18000d03a  xor     eax, eax
0x18000d03c  jmp     short loc_18000D043
0x18000d03e  mov     eax, [r15+r14*8+8]
0x18000d043  mov     [rsi+8], eax
0x18000d046  test    eax, eax
0x18000d048  jnz     short loc_18000D051
0x18000d04a  mov     eax, 8007000Dh
0x18000d04f  jmp     short loc_18000D0A6
0x18000d051  lea     r8, [rbx+48h]
0x18000d055  cmp     qword ptr [r8+18h], 8
0x18000d05a  jb      short loc_18000D05F
0x18000d05c  mov     r8, [r8]; unsigned __int16 *
0x18000d05f  lea     rdx, [rsi+10h]; unsigned __int16 **
0x18000d063  call    ?LoadStringWithAlloc@ResourceStringLoader@@QEAAJPEAPEAGPEBG@Z; ResourceStringLoader::LoadStringWithAlloc(ushort * *,ushort const *)
0x18000d068  test    eax, eax
0x18000d06a  js      short loc_18000D0A6
0x18000d06c  lea     r9, [rbx+8]
0x18000d070  cmp     qword ptr [r9+18h], 8
0x18000d075  jb      short loc_18000D07A
0x18000d077  mov     r9, [r9]; unsigned __int16 *
0x18000d07a  mov     edi, 0FFFFh
0x18000d07f  mov     rcx, rsi; unsigned __int16 **
0x18000d082  mov     edx, edi; unsigned int
0x18000d084  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x18000d089  test    eax, eax
0x18000d08b  js      short loc_18000D0A6
0x18000d08d  lea     r9, [rbx+68h]
0x18000d091  cmp     qword ptr [r9+18h], 8
0x18000d096  jb      short loc_18000D09B
0x18000d098  mov     r9, [r9]; unsigned __int16 *
0x18000d09b  lea     rcx, [rsi+18h]; unsigned __int16 **
0x18000d09f  mov     edx, edi; unsigned int
0x18000d0a1  call    ?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z; UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)
0x18000d0a6  add     rsp, 38h
0x18000d0aa  pop     r15
0x18000d0ac  pop     r14
0x18000d0ae  pop     rdi
0x18000d0af  pop     rsi
0x18000d0b0  pop     rbp
0x18000d0b1  pop     rbx
0x18000d0b2  retn
```
