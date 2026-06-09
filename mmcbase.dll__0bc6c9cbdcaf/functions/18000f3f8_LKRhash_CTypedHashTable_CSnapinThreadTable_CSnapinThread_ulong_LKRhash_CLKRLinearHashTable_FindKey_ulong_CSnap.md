# LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::FindKey(ulong,CSnapinThread * *)

- ea: `0x18000f3f8`
- end: `0x18000f436`
- name: `?FindKey@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@QEBA?AW4LK_RETCODE@2@KPEAPEAVCSnapinThread@@@Z`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f6d8`
- `0x18000f9d8`

## callees

- `0x1800015e0`
- `0x18000f3f8`

## pseudocode

```c
__int64 __fastcall LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::FindKey(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3)
{
  __int64 result; // rax
  __int64 v5; // [rsp+40h] [rbp+18h] BYREF

  if ( !a3 )
    return 4294967200LL;
  *a3 = 0;
  v5 = 0;
  result = LKRhash::CLKRLinearHashTable::FindKey(a1, a2, &v5);
  *a3 = v5;
  return result;
}

```

## disassembly

```asm
0x18000f3f8  push    rbx
0x18000f3fa  sub     rsp, 20h
0x18000f3fe  mov     rbx, r8
0x18000f401  test    r8, r8
0x18000f404  jnz     short loc_18000F40C
0x18000f406  lea     eax, [r8-60h]
0x18000f40a  jmp     short loc_18000F430
0x18000f40c  mov     qword ptr [r8], 0
0x18000f413  lea     r8, [rsp+28h+arg_10]
0x18000f418  mov     edx, edx
0x18000f41a  mov     [rsp+28h+arg_10], 0
0x18000f423  call    ?FindKey@CLKRLinearHashTable@LKRhash@@QEBA?AW4LK_RETCODE@2@_KPEAPEBX@Z; LKRhash::CLKRLinearHashTable::FindKey(unsigned __int64,void const * *)
0x18000f428  mov     rcx, [rsp+28h+arg_10]
0x18000f42d  mov     [rbx], rcx
0x18000f430  add     rsp, 20h
0x18000f434  pop     rbx
0x18000f435  retn
```
