# CMGetProfileHeader

- ea: `0x180018abc`
- end: `0x180018af1`
- name: `CMGetProfileHeader`
- size: `53`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c0c`
- `0x180005974`
- `0x18001de14`
- `0x18001e97c`
- `0x18001edd4`

## callees

- `0x180018abc`

## import_xrefs

- `mscms!GetColorProfileHeader` at `0x180018ace`
- `mscms!GetColorProfileHeader` at `0x180018ace`

## pseudocode

```c
__int64 __fastcall CMGetProfileHeader(void *a1, PROFILEHEADER *a2)
{
  unsigned int v3; // edi
  BOOL ColorProfileHeader; // eax

  v3 = 2011;
  ColorProfileHeader = GetColorProfileHeader(a1, a2);
  if ( a2->phSignature == 1633907568 && ColorProfileHeader )
    return 0;
  return v3;
}

```

## disassembly

```asm
0x180018abc  mov     [rsp+arg_0], rbx
0x180018ac1  push    rdi
0x180018ac2  sub     rsp, 20h
0x180018ac6  mov     rbx, rdx
0x180018ac9  mov     edi, 7DBh
0x180018ace  call    cs:__imp_GetColorProfileHeader
0x180018ad4  cmp     dword ptr [rbx+24h], 61637370h
0x180018adb  jnz     short loc_180018AE4
0x180018add  xor     ecx, ecx
0x180018adf  test    eax, eax
0x180018ae1  cmovnz  edi, ecx
0x180018ae4  mov     rbx, [rsp+28h+arg_0]
0x180018ae9  mov     eax, edi
0x180018aeb  add     rsp, 20h
0x180018aef  pop     rdi
0x180018af0  retn
```
