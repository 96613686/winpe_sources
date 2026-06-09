# CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::FindKey(OUTPUT_KEY * const,OUTPUT_ENTRY * *)

- ea: `0x180006628`
- end: `0x180006670`
- name: `?FindKey@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEAVOUTPUT_KEY@@PEAPEAVOUTPUT_ENTRY@@@Z`
- size: `72`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f20`
- `0x180004220`

## callees

- `0x180006628`

## import_xrefs

- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000665c`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000665c`

## pseudocode

```c
__int64 __fastcall CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::FindKey(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 result; // rax
  PVOID v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = a1;
  if ( !a3 )
    return 4294967200LL;
  v5 = g_pOutputCache;
  *a3 = 0;
  v6 = 0;
  result = CLKRHashTable::FindKey(v5, a2, &v6);
  *a3 = v6;
  return result;
}

```

## disassembly

```asm
0x180006628  mov     [rsp+arg_0], rcx
0x18000662d  push    rbx
0x18000662e  sub     rsp, 20h
0x180006632  mov     rbx, r8
0x180006635  test    r8, r8
0x180006638  jnz     short loc_180006640
0x18000663a  lea     eax, [r8-60h]
0x18000663e  jmp     short loc_18000666A
0x180006640  mov     rcx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x180006647  mov     qword ptr [r8], 0
0x18000664e  lea     r8, [rsp+28h+arg_0]
0x180006653  mov     [rsp+28h+arg_0], 0
0x18000665c  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180006662  mov     rcx, [rsp+28h+arg_0]
0x180006667  mov     [rbx], rcx
0x18000666a  add     rsp, 20h
0x18000666e  pop     rbx
0x18000666f  retn
```
