# CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)

- ea: `0x180003440`
- end: `0x180003471`
- name: `?_CalcKeyHash@?$CTypedHashTable@VISAPI_DLL_HASH@@VISAPI_DLL@@PEBGVCLKRHashTable@@@@CAK_K@Z`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003440`

## pseudocode

```c
__int64 __fastcall CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,unsigned short const *,CLKRHashTable>::_CalcKeyHash(
        __int16 *a1)
{
  __int16 *v1; // rdx
  __int64 result; // rax
  __int16 i; // cx

  v1 = a1;
  result = -1;
  do
    ++result;
  while ( a1[result] );
  for ( i = *a1; i; i = *v1 )
  {
    ++v1;
    result = (i & 0xFFDFu) + 101 * (_DWORD)result;
  }
  return result;
}

```

## disassembly

```asm
0x180003440  mov     rdx, rcx
0x180003443  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003447  inc     rax
0x18000344a  cmp     word ptr [rcx+rax*2], 0
0x18000344f  jnz     short loc_180003447
0x180003451  movzx   ecx, word ptr [rcx]
0x180003454  jmp     short loc_18000346B
0x180003456  movzx   ecx, cx
0x180003459  lea     rdx, [rdx+2]
0x18000345d  and     ecx, 0FFDFh
0x180003463  imul    eax, 65h ; 'e'
0x180003466  add     eax, ecx
0x180003468  movzx   ecx, word ptr [rdx]
0x18000346b  test    cx, cx
0x18000346e  jnz     short loc_180003456
0x180003470  retn
```
