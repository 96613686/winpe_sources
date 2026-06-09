# IsV2Property(ushort const *)

- ea: `0x180001920`
- end: `0x18000198c`
- name: `?IsV2Property@@YAHPEBG@Z`
- size: `108`
- prototype: `__int64 __fastcall(PCNZWCH lpString1)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800016e0`
- `0x1800019a0`
- `0x180001bf0`
- `0x180012ae8`
- `0x180012f0c`
- `0x1800308c0`
- `0x180030c18`
- `0x1800315b4`
- `0x180031af8`
- `0x180033144`

## callees

- `0x180001920`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001966`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001966`

## pseudocode

```c
__int64 __fastcall IsV2Property(PCNZWCH lpString1)
{
  unsigned int v1; // edi
  unsigned int i; // ebx

  v1 = 0;
  for ( i = 0; i < 0xD; ++i )
  {
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, (PCNZWCH)*(&g_CTV2Properties + 2 * i), -1) == 2 )
      return 1;
  }
  return v1;
}

```

## disassembly

```asm
0x180001920  mov     [rsp+arg_0], rbx
0x180001925  mov     [rsp+arg_8], rsi
0x18000192a  push    rdi
0x18000192b  sub     rsp, 30h
0x18000192f  xor     edi, edi
0x180001931  mov     rsi, rcx
0x180001934  xor     ebx, ebx
0x180001936  cmp     ebx, 0Dh
0x180001939  jnb     short loc_18000197A
0x18000193b  lea     rcx, ?g_CTV2Properties@@3PAU_CERT_TYPE_PROP_INFO@@A; _CERT_TYPE_PROP_INFO near * g_CTV2Properties
0x180001942  mov     eax, ebx
0x180001944  or      r9d, 0FFFFFFFFh; cchCount1
0x180001948  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001950  add     rax, rax
0x180001953  mov     r8, rsi; lpString1
0x180001956  lea     edx, [r9+2]; dwCmpFlags
0x18000195a  mov     rax, [rcx+rax*8]
0x18000195e  lea     ecx, [rdx+7Eh]; Locale
0x180001961  mov     [rsp+38h+lpString2], rax; lpString2
0x180001966  call    cs:__imp_CompareStringW
0x18000196c  cmp     eax, 2
0x18000196f  jz      short loc_180001975
0x180001971  inc     ebx
0x180001973  jmp     short loc_180001936
0x180001975  mov     edi, 1
0x18000197a  mov     rbx, [rsp+38h+arg_0]
0x18000197f  mov     eax, edi
0x180001981  mov     rsi, [rsp+38h+arg_8]
0x180001986  add     rsp, 30h
0x18000198a  pop     rdi
0x18000198b  retn
```
