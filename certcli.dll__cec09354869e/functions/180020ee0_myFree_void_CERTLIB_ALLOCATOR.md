# myFree(void *,CERTLIB_ALLOCATOR)

- ea: `0x180020ee0`
- end: `0x180020f14`
- name: `?myFree@@YAXPEAXW4CERTLIB_ALLOCATOR@@@Z`
- size: `52`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a000`
- `0x18001a350`
- `0x180020760`
- `0x180020770`
- `0x18002966c`

## callees

- `0x180020ee0`

## import_xrefs

- `msvcrt!free` at `0x180020ef7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020f02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020f09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020f09`

## pseudocode

```c
void __fastcall myFree(void *a1, int a2)
{
  int v2; // edx
  int v3; // edx

  v2 = a2 - 1;
  if ( v2 )
  {
    v3 = v2 - 1;
    if ( v3 )
    {
      if ( v3 == 2 )
        free(a1);
    }
    else
    {
      LocalFree(a1);
    }
  }
  else
  {
    CoTaskMemFree(a1);
  }
}

```

## disassembly

```asm
0x180020ee0  sub     rsp, 28h
0x180020ee4  sub     edx, 1
0x180020ee7  jz      short loc_180020F09
0x180020ee9  sub     edx, 1
0x180020eec  jz      short loc_180020EFE
0x180020eee  cmp     edx, 2
0x180020ef1  jnz     short loc_180020F0F
0x180020ef3  add     rsp, 28h
0x180020ef7  jmp     cs:__imp_free
0x180020efe  add     rsp, 28h
0x180020f02  jmp     cs:__imp_LocalFree
0x180020f09  call    cs:__imp_CoTaskMemFree
0x180020f0f  add     rsp, 28h
0x180020f13  retn
```
