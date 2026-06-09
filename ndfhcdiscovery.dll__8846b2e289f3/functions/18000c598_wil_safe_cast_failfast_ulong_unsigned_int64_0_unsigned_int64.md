# wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)

- ea: `0x18000c598`
- end: `0x18000c5ca`
- name: `??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z`
- size: `50`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b7a0`
- `0x18000b90c`
- `0x18000ba60`
- `0x18000bb4c`
- `0x18000bca0`
- `0x18000d134`

## callees

- `0x18000c598`
- `0x18001065c`
- `0x180010a6c`

## pseudocode

```c
__int64 __fastcall wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(unsigned __int64 a1)
{
  int v1; // eax
  void *v2; // rdx
  unsigned int v3; // r8d
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  v1 = ULongLongToULong(a1, &v7);
  if ( v1 < 0 )
    wil::details::in1diag3::_FailFast_Hr(retaddr, v2, v3, (const char *)(unsigned int)v1, v5);
  return v7;
}

```

## disassembly

```asm
0x18000c598  sub     rsp, 28h
0x18000c59c  lea     rdx, [rsp+28h+arg_8]; unsigned int *
0x18000c5a1  mov     [rsp+28h+arg_8], 0
0x18000c5a9  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000c5ae  test    eax, eax
0x18000c5b0  js      short loc_18000C5BC
0x18000c5b2  mov     eax, [rsp+28h+arg_8]
0x18000c5b6  add     rsp, 28h
0x18000c5ba  retn
0x18000c5bc  mov     rcx, [rsp+28h]; this
0x18000c5c1  mov     r9d, eax; char *
0x18000c5c4  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
