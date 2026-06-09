# CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,ushort const *,CLKRHashTable>::FindKey(ushort const * const,ISAPI_DLL * *)

- ea: `0x1800051e0`
- end: `0x18000521d`
- name: `?FindKey@?$CTypedHashTable@VISAPI_DLL_HASH@@VISAPI_DLL@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVISAPI_DLL@@@Z`
- size: `61`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005224`

## callees

- `0x1800051e0`

## import_xrefs

- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180005209`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180005209`

## pseudocode

```c
__int64 __fastcall CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,unsigned short const *,CLKRHashTable>::FindKey(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 result; // rax
  __int64 v5; // [rsp+40h] [rbp+18h] BYREF

  if ( !a3 )
    return 4294967200LL;
  *a3 = 0;
  v5 = 0;
  result = CLKRHashTable::FindKey(a1, a2, &v5);
  *a3 = v5;
  return result;
}

```

## disassembly

```asm
0x1800051e0  push    rbx
0x1800051e2  sub     rsp, 20h
0x1800051e6  mov     rbx, r8
0x1800051e9  test    r8, r8
0x1800051ec  jnz     short loc_1800051F4
0x1800051ee  lea     eax, [r8-60h]
0x1800051f2  jmp     short loc_180005217
0x1800051f4  mov     qword ptr [r8], 0
0x1800051fb  lea     r8, [rsp+28h+arg_10]
0x180005200  mov     [rsp+28h+arg_10], 0
0x180005209  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x18000520f  mov     rcx, [rsp+28h+arg_10]
0x180005214  mov     [rbx], rcx
0x180005217  add     rsp, 20h
0x18000521b  pop     rbx
0x18000521c  retn
```
