# myFree(void *,CERTLIB_ALLOCATOR)

- ea: `0x18001e44c`
- end: `0x18001e480`
- name: `?myFree@@YAXPEAXW4CERTLIB_ALLOCATOR@@@Z`
- size: `52`
- prototype: `void __fastcall(void *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ab18`
- `0x18001e070`

## callees

- `0x18001e44c`

## import_xrefs

- `msvcrt!free` at `0x18001e463`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e46e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e475`

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
0x18001e44c  sub     rsp, 28h
0x18001e450  sub     edx, 1
0x18001e453  jz      short loc_18001E475
0x18001e455  sub     edx, 1
0x18001e458  jz      short loc_18001E46A
0x18001e45a  cmp     edx, 2
0x18001e45d  jnz     short loc_18001E47B
0x18001e45f  add     rsp, 28h
0x18001e463  jmp     cs:__imp_free
0x18001e46a  add     rsp, 28h
0x18001e46e  jmp     cs:__imp_LocalFree
0x18001e475  call    cs:__imp_CoTaskMemFree
0x18001e47b  add     rsp, 28h
0x18001e47f  retn
```
