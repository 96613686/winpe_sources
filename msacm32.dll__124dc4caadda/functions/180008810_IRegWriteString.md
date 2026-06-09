# IRegWriteString

- ea: `0x180008810`
- end: `0x180008851`
- name: `IRegWriteString`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180011434`
- `0x180012020`

## callees

- `0x180008810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008846`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008846`

## pseudocode

```c
LSTATUS __fastcall IRegWriteString(HKEY a1, const WCHAR *a2, const BYTE *lpData)
{
  __int64 v3; // rax

  v3 = -1;
  while ( *(_WORD *)&lpData[2 * v3++ + 2] != 0 )
    ;
  return RegSetValueExW(a1, a2, 0, 1u, lpData, 2 * v3 + 2);
}

```

## disassembly

```asm
0x180008810  sub     rsp, 38h
0x180008814  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000881b  nop     dword ptr [rax+rax+00h]
0x180008820  cmp     word ptr [r8+rax*2+2], 0
0x180008827  lea     rax, [rax+1]
0x18000882b  jnz     short loc_180008820
0x18000882d  lea     eax, ds:2[rax*2]
0x180008834  mov     r9d, 1; dwType
0x18000883a  mov     [rsp+38h+cbData], eax; cbData
0x18000883e  mov     [rsp+38h+lpData], r8; lpData
0x180008843  xor     r8d, r8d; Reserved
0x180008846  call    cs:__imp_RegSetValueExW
0x18000884c  add     rsp, 38h
0x180008850  retn
```
