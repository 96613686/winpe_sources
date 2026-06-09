# W3_RESTRICTION_LIST::CreateList(INativeSectionException * *)

- ea: `0x180012068`
- end: `0x180012147`
- name: `?CreateList@W3_RESTRICTION_LIST@@SAJPEAPEAVINativeSectionException@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180012188`

## callees

- `0x180001020`
- `0x180001d8c`
- `0x180011d90`
- `0x180012068`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001212f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001212f`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800120f6`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800120f6`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180012083`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180012083`

## pseudocode

```c
__int64 __fastcall W3_RESTRICTION_LIST::CreateList(struct INativeSectionException **a1)
{
  int v2; // edi
  CLKRHashTable *v3; // rax
  W3_RESTRICTION_LIST *v4; // rbx
  unsigned int v5; // edx

  v2 = 0;
  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
  if ( !W3_RESTRICTION_LIST::sm_pRestrictionList )
  {
    v3 = (CLKRHashTable *)operator new(0x58u);
    v4 = v3;
    if ( v3 )
    {
      CLKRHashTable::CLKRHashTable(
        v3,
        "W3_RESTRICTION_LIST",
        (unsigned __int64 (*)(const void *))TOKEN_KEY::GetUserNameW,
        (unsigned int (*)(unsigned __int64))CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
        (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<W3_RESTRICTION_LIST,W3_IMAGE_RECORD,unsigned short const *,CLKRHashTable>::_EqualKeys,
        (void (*)(const void *, int))CTypedHashTable<W3_RESTRICTION_LIST,W3_IMAGE_RECORD,unsigned short const *,CLKRHashTable>::_AddRefRecord,
        4.0,
        1u,
        0,
        0);
      *((_DWORD *)v4 + 20) = 1;
      v2 = W3_RESTRICTION_LIST::Create(v4, a1);
      if ( v2 >= 0 )
        W3_RESTRICTION_LIST::sm_pRestrictionList = v4;
      else
        W3_RESTRICTION_LIST::`scalar deleting destructor'(v4, v5);
    }
    else
    {
      v2 = -2147024888;
    }
  }
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)W3_RESTRICTION_LIST::sm_pRestrictionLock);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180012068  mov     [rsp+arg_0], rbx
0x18001206d  mov     [rsp+arg_8], rsi
0x180012072  push    rdi
0x180012073  sub     rsp, 50h
0x180012077  mov     rsi, rcx
0x18001207a  xor     edi, edi
0x18001207c  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x180012083  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180012089  cmp     cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA, rdi; W3_RESTRICTION_LIST * W3_RESTRICTION_LIST::sm_pRestrictionList
0x180012090  jnz     loc_180012128
0x180012096  lea     ecx, [rdi+58h]; Size
0x180012099  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001209e  mov     rbx, rax
0x1800120a1  test    rax, rax
0x1800120a4  jz      short loc_180012123
0x1800120a6  movsd   xmm0, cs:__real@4010000000000000
0x1800120ae  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VW3_RESTRICTION_LIST@@VW3_IMAGE_RECORD@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<W3_RESTRICTION_LIST,W3_IMAGE_RECORD,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x1800120b5  mov     [rsp+58h+var_10], dil
0x1800120ba  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VISAPI_DLL_HASH@@VISAPI_DLL@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x1800120c1  mov     [rsp+58h+var_18], edi
0x1800120c5  lea     r8, ?GetUserNameW@TOKEN_KEY@@UEBAPEBGXZ; TOKEN_KEY::GetUserNameW(void)
0x1800120cc  mov     edi, 1
0x1800120d1  lea     rdx, aW3RestrictionL; "W3_RESTRICTION_LIST"
0x1800120d8  mov     [rsp+58h+var_20], edi
0x1800120dc  mov     rcx, rbx
0x1800120df  movsd   [rsp+58h+var_28], xmm0
0x1800120e5  mov     [rsp+58h+var_30], rax
0x1800120ea  lea     rax, ?_EqualKeys@?$CTypedHashTable@VW3_RESTRICTION_LIST@@VW3_IMAGE_RECORD@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<W3_RESTRICTION_LIST,W3_IMAGE_RECORD,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x1800120f1  mov     [rsp+58h+var_38], rax
0x1800120f6  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x1800120fc  mov     rdx, rsi; struct INativeSectionException **
0x1800120ff  mov     [rbx+50h], edi
0x180012102  mov     rcx, rbx; this
0x180012105  call    ?Create@W3_RESTRICTION_LIST@@AEAAJPEAPEAVINativeSectionException@@@Z; W3_RESTRICTION_LIST::Create(INativeSectionException * *)
0x18001210a  mov     edi, eax
0x18001210c  test    eax, eax
0x18001210e  jns     short loc_18001211A
0x180012110  mov     rcx, rbx; this
0x180012113  call    ??_GW3_RESTRICTION_LIST@@QEAAPEAXI@Z; W3_RESTRICTION_LIST::`scalar deleting destructor'(uint)
0x180012118  jmp     short loc_180012128
0x18001211a  mov     cs:?sm_pRestrictionList@W3_RESTRICTION_LIST@@0PEAV1@EA, rbx; W3_RESTRICTION_LIST * W3_RESTRICTION_LIST::sm_pRestrictionList
0x180012121  jmp     short loc_180012128
0x180012123  mov     edi, 80070008h
0x180012128  mov     rcx, cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x18001212f  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180012135  mov     rbx, [rsp+58h+arg_0]
0x18001213a  mov     eax, edi
0x18001213c  mov     rsi, [rsp+58h+arg_8]
0x180012141  add     rsp, 50h
0x180012145  pop     rdi
0x180012146  retn
```
