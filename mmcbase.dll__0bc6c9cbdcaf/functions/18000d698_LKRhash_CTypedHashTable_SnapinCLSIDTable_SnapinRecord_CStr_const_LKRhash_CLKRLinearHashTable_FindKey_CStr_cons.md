# LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::FindKey(CStr const * const,SnapinRecord * *)

- ea: `0x18000d698`
- end: `0x18000d6df`
- name: `?FindKey@?$CTypedHashTable@VSnapinCLSIDTable@@VSnapinRecord@@PEBVCStr@@VCLKRLinearHashTable@LKRhash@@@LKRhash@@QEBA?AW4LK_RETCODE@2@QEBVCStr@@PEAPEAVSnapinRecord@@@Z`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d2e0`
- `0x18000d7e4`

## callees

- `0x1800015e0`
- `0x18000d698`

## pseudocode

```c
__int64 __fastcall LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::FindKey(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 result; // rax
  struct SnapinCLSIDTable *v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v6 = a1;
  if ( !a3 )
    return 4294967200LL;
  v5 = BookKeeping::s_pSnapinTable;
  *a3 = 0;
  v6 = 0;
  result = LKRhash::CLKRLinearHashTable::FindKey((__int64)v5, a2, &v6);
  *a3 = v6;
  return result;
}

```

## disassembly

```asm
0x18000d698  mov     [rsp+arg_0], rcx
0x18000d69d  push    rbx
0x18000d69e  sub     rsp, 20h
0x18000d6a2  mov     rbx, r8
0x18000d6a5  test    r8, r8
0x18000d6a8  jnz     short loc_18000D6B0
0x18000d6aa  lea     eax, [r8-60h]
0x18000d6ae  jmp     short loc_18000D6D9
0x18000d6b0  mov     rcx, cs:?s_pSnapinTable@BookKeeping@@0PEAVSnapinCLSIDTable@@EA; SnapinCLSIDTable * BookKeeping::s_pSnapinTable
0x18000d6b7  mov     qword ptr [r8], 0
0x18000d6be  lea     r8, [rsp+28h+arg_0]
0x18000d6c3  mov     [rsp+28h+arg_0], 0
0x18000d6cc  call    ?FindKey@CLKRLinearHashTable@LKRhash@@QEBA?AW4LK_RETCODE@2@_KPEAPEBX@Z; LKRhash::CLKRLinearHashTable::FindKey(unsigned __int64,void const * *)
0x18000d6d1  mov     rcx, [rsp+28h+arg_0]
0x18000d6d6  mov     [rbx], rcx
0x18000d6d9  add     rsp, 20h
0x18000d6dd  pop     rbx
0x18000d6de  retn
```
