# FreeGlobalData

- ea: `0x140001fec`
- end: `0x140002069`
- name: `FreeGlobalData`
- size: `125`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000375c`
- `0x140003ec4`
- `0x140004518`
- `0x140004708`
- `0x140004a38`
- `0x140005bac`
- `0x140006394`
- `0x140006f9c`
- `0x140008788`
- `0x140008fe8`
- `0x1400096a8`
- `0x14000998c`
- `0x140009ec0`

## callees

- `0x140001fec`
- `0x14000c9c0`
- `0x14000e634`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002010`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002010`

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
0x140001fec  mov     [rsp+arg_0], rbx
0x140001ff1  push    rdi
0x140001ff2  sub     rsp, 20h
0x140001ff6  cmp     dword ptr [rcx+14h], 1
0x140001ffa  mov     rbx, rcx
0x140001ffd  jnz     short loc_14000201D
0x140001fff  lea     rdi, [rcx+8]
0x140002003  test    rdi, rdi
0x140002006  jz      short loc_14000201D
0x140002008  mov     rcx, [rdi]; hKey
0x14000200b  test    rcx, rcx
0x14000200e  jz      short loc_14000201D
0x140002010  call    cs:__imp_RegCloseKey
0x140002016  mov     qword ptr [rdi], 0
0x14000201d  lea     rcx, [rbx+50h]
0x140002021  call    FreeMemory
0x140002026  lea     rcx, [rbx+58h]
0x14000202a  call    FreeMemory
0x14000202f  lea     rcx, [rbx+48h]
0x140002033  call    FreeMemory
0x140002038  lea     rcx, [rbx+78h]
0x14000203c  call    FreeMemory
0x140002041  lea     rcx, [rbx+60h]
0x140002045  call    FreeMemory
0x14000204a  lea     rcx, [rbx+68h]
0x14000204e  call    FreeMemory
0x140002053  lea     rcx, [rbx+80h]
0x14000205a  mov     rbx, [rsp+28h+arg_0]
0x14000205f  add     rsp, 20h
0x140002063  pop     rdi
0x140002064  jmp     DestroyDynamicArray
```
