# FreeGlobalData

- ea: `0x140002004`
- end: `0x140002087`
- name: `FreeGlobalData`
- size: `131`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400038f8`
- `0x1400040b8`
- `0x140004764`
- `0x14000496c`
- `0x140004cf0`
- `0x140005ef0`
- `0x14000672c`
- `0x1400073d4`
- `0x140008cbc`
- `0x14000957c`
- `0x140009c68`
- `0x140009f80`
- `0x14000a4e4`

## callees

- `0x140002004`
- `0x14000d2d0`
- `0x14000f2c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002028`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002028`

## pseudocode

```c
__int64 __fastcall FreeGlobalData(__int64 a1)
{
  HKEY *v2; // rdi

  if ( *(_DWORD *)(a1 + 20) == 1 )
  {
    v2 = (HKEY *)(a1 + 8);
    if ( a1 != -8 )
    {
      if ( *v2 )
      {
        RegCloseKey(*v2);
        *v2 = 0;
      }
    }
  }
  FreeMemory((void **)(a1 + 80));
  FreeMemory((void **)(a1 + 88));
  FreeMemory((void **)(a1 + 72));
  FreeMemory((void **)(a1 + 120));
  FreeMemory((void **)(a1 + 96));
  FreeMemory((void **)(a1 + 104));
  return DestroyDynamicArray(a1 + 128);
}

```

## disassembly

```asm
0x140002004  mov     [rsp+arg_0], rbx
0x140002009  push    rdi
0x14000200a  sub     rsp, 20h
0x14000200e  cmp     dword ptr [rcx+14h], 1
0x140002012  mov     rbx, rcx
0x140002015  jnz     short loc_14000203B
0x140002017  lea     rdi, [rcx+8]
0x14000201b  test    rdi, rdi
0x14000201e  jz      short loc_14000203B
0x140002020  mov     rcx, [rdi]; hKey
0x140002023  test    rcx, rcx
0x140002026  jz      short loc_14000203B
0x140002028  call    cs:__imp_RegCloseKey
0x14000202f  nop     dword ptr [rax+rax+00h]
0x140002034  mov     qword ptr [rdi], 0
0x14000203b  lea     rcx, [rbx+50h]
0x14000203f  call    FreeMemory
0x140002044  lea     rcx, [rbx+58h]
0x140002048  call    FreeMemory
0x14000204d  lea     rcx, [rbx+48h]
0x140002051  call    FreeMemory
0x140002056  lea     rcx, [rbx+78h]
0x14000205a  call    FreeMemory
0x14000205f  lea     rcx, [rbx+60h]
0x140002063  call    FreeMemory
0x140002068  lea     rcx, [rbx+68h]
0x14000206c  call    FreeMemory
0x140002071  lea     rcx, [rbx+80h]
0x140002078  mov     rbx, [rsp+28h+arg_0]
0x14000207d  add     rsp, 20h
0x140002081  pop     rdi
0x140002082  jmp     DestroyDynamicArray
```
