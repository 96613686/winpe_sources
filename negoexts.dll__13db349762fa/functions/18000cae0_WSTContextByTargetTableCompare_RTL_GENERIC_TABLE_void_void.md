# WSTContextByTargetTableCompare(_RTL_GENERIC_TABLE *,void *,void *)

- ea: `0x18000cae0`
- end: `0x18000cb19`
- name: `?WSTContextByTargetTableCompare@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_GENERIC_TABLE@@PEAX1@Z`
- size: `57`
- prototype: `RTL_GENERIC_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000cae0`
- `0x18000e8f0`

## pseudocode

```c
__int64 __fastcall WSTContextByTargetTableCompare(
        struct _RTL_GENERIC_TABLE *Table,
        struct _WST_CONTEXT **FirstStruct,
        struct _WST_CONTEXT **SecondStruct)
{
  int v3; // edx
  __int64 result; // rax

  if ( *FirstStruct == *SecondStruct )
    return 2;
  v3 = WSTCompareContexts(*FirstStruct, *SecondStruct);
  if ( v3 > 0 )
    return 1;
  result = 2;
  if ( v3 < 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18000cae0  sub     rsp, 28h
0x18000cae4  mov     rcx, [rdx]; struct _WST_CONTEXT *
0x18000cae7  cmp     rcx, [r8]
0x18000caea  jz      short loc_18000CB0F
0x18000caec  mov     rdx, [r8]; struct _WST_CONTEXT *
0x18000caef  call    ?WSTCompareContexts@@YAHPEAU_WST_CONTEXT@@0@Z; WSTCompareContexts(_WST_CONTEXT *,_WST_CONTEXT *)
0x18000caf4  mov     edx, eax
0x18000caf6  test    eax, eax
0x18000caf8  jle     short loc_18000CB01
0x18000cafa  mov     eax, 1
0x18000caff  jmp     short loc_18000CB14
0x18000cb01  xor     ecx, ecx
0x18000cb03  mov     eax, 2
0x18000cb08  test    edx, edx
0x18000cb0a  cmovs   eax, ecx
0x18000cb0d  jmp     short loc_18000CB14
0x18000cb0f  mov     eax, 2
0x18000cb14  add     rsp, 28h
0x18000cb18  retn
```
