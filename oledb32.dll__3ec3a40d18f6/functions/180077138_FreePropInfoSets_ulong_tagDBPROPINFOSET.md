# FreePropInfoSets(ulong,tagDBPROPINFOSET *)

- ea: `0x180077138`
- end: `0x1800771a5`
- name: `?FreePropInfoSets@@YAXKPEAUtagDBPROPINFOSET@@@Z`
- size: `109`
- prototype: `void __fastcall(unsigned int, struct tagDBPROPINFOSET *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001d6d8`
- `0x180063754`

## callees

- `0x180077138`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180077171`
- `OLEAUT32!__imp_VariantClear` at `0x180077171`
- `ole32!CoTaskMemFree` at `0x180077185`
- `ole32!CoTaskMemFree` at `0x180077185`
- `ole32!CoTaskMemFree` at `0x18007719e`

## pseudocode

```c
void __fastcall FreePropInfoSets(unsigned int a1, struct tagDBPROPINFOSET *a2)
{
  unsigned int i; // edi
  __int64 v5; // r14
  __int64 v6; // rsi

  for ( i = 0; i < a1; ++i )
  {
    v5 = 0;
    v6 = i;
    if ( a2[v6].cPropertyInfos )
    {
      do
      {
        VariantClear(&a2[v6].rgPropertyInfos[v5].vValues);
        v5 = (unsigned int)(v5 + 1);
      }
      while ( (unsigned int)v5 < a2[v6].cPropertyInfos );
    }
    CoTaskMemFree(a2[v6].rgPropertyInfos);
  }
  CoTaskMemFree(a2);
}

```

## disassembly

```asm
0x180077138  push    rbx
0x18007713a  push    rbp
0x18007713b  push    rsi
0x18007713c  push    rdi
0x18007713d  push    r14
0x18007713f  sub     rsp, 20h
0x180077143  xor     edi, edi
0x180077145  mov     rbx, rdx
0x180077148  mov     ebp, ecx
0x18007714a  test    ecx, ecx
0x18007714c  jz      short loc_180077191
0x18007714e  mov     esi, edi
0x180077150  xor     r14d, r14d
0x180077153  shl     rsi, 5
0x180077157  cmp     [rsi+rbx+8], r14d
0x18007715c  jbe     short loc_180077181
0x18007715e  mov     rax, [rsi+rbx]
0x180077162  lea     rcx, [r14+r14*2]
0x180077166  shl     rcx, 4
0x18007716a  add     rax, 18h
0x18007716e  add     rcx, rax; pvarg
0x180077171  call    cs:__imp_VariantClear
0x180077177  inc     r14d
0x18007717a  cmp     r14d, [rsi+rbx+8]
0x18007717f  jb      short loc_18007715E
0x180077181  mov     rcx, [rsi+rbx]; pv
0x180077185  call    cs:__imp_CoTaskMemFree
0x18007718b  inc     edi
0x18007718d  cmp     edi, ebp
0x18007718f  jb      short loc_18007714E
0x180077191  mov     rcx, rbx
0x180077194  add     rsp, 20h
0x180077198  pop     r14
0x18007719a  pop     rdi
0x18007719b  pop     rsi
0x18007719c  pop     rbp
0x18007719d  pop     rbx
0x18007719e  jmp     cs:__imp_CoTaskMemFree
```
