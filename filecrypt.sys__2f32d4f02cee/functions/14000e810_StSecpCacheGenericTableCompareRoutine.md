# StSecpCacheGenericTableCompareRoutine

- ea: `0x14000e810`
- end: `0x14000e83a`
- name: `StSecpCacheGenericTableCompareRoutine`
- size: `42`
- prototype: `RTL_GENERIC_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001560`
- `0x14000e810`

## pseudocode

```c
__int64 __fastcall StSecpCacheGenericTableCompareRoutine(
        struct _RTL_GENERIC_TABLE *Table,
        const wchar_t **FirstStruct,
        const wchar_t **SecondStruct)
{
  int v3; // ecx

  v3 = wcsicmp(FirstStruct[1], SecondStruct[1]);
  if ( v3 >= 0 )
    return (unsigned int)(v3 <= 0) + 1;
  else
    return 0;
}

```

## disassembly

```asm
0x14000e810  sub     rsp, 28h
0x14000e814  mov     rcx, [rdx+8]; Str1
0x14000e818  mov     rdx, [r8+8]; Str2
0x14000e81c  call    _wcsicmp
0x14000e821  mov     ecx, eax
0x14000e823  test    eax, eax
0x14000e825  jns     short loc_14000E82B
0x14000e827  xor     eax, eax
0x14000e829  jmp     short loc_14000E834
0x14000e82b  xor     eax, eax
0x14000e82d  test    ecx, ecx
0x14000e82f  setle   al
0x14000e832  inc     eax
0x14000e834  add     rsp, 28h
0x14000e838  retn
```
