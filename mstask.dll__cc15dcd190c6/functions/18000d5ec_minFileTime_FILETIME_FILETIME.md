# minFileTime(_FILETIME,_FILETIME)

- ea: `0x18000d5ec`
- end: `0x18000d61c`
- name: `?minFileTime@@YA?AU_FILETIME@@U1@0@Z`
- size: `48`
- prototype: `struct _FILETIME __fastcall(struct _FILETIME, struct _FILETIME)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800018c0`

## callees

- `0x18000d5ec`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000d603`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000d603`

## pseudocode

```c
FILETIME __fastcall minFileTime(FILETIME a1, FILETIME a2)
{
  bool v2; // sf
  FILETIME result; // rax
  FILETIME v4; // [rsp+30h] [rbp+8h] BYREF
  FILETIME v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = a2;
  v4 = a1;
  v2 = CompareFileTime(&v4, &v5) < 0;
  result = v4;
  if ( !v2 )
    return v5;
  return result;
}

```

## disassembly

```asm
0x18000d5ec  mov     rax, rsp
0x18000d5ef  mov     [rax+10h], rdx
0x18000d5f3  mov     [rax+8], rcx
0x18000d5f7  sub     rsp, 28h
0x18000d5fb  lea     rdx, [rax+10h]; lpFileTime2
0x18000d5ff  lea     rcx, [rax+8]; lpFileTime1
0x18000d603  call    cs:__imp_CompareFileTime
0x18000d609  test    eax, eax
0x18000d60b  mov     rax, [rsp+28h+arg_0]
0x18000d610  js      short loc_18000D617
0x18000d612  mov     rax, [rsp+28h+arg_8]
0x18000d617  add     rsp, 28h
0x18000d61b  retn
```
