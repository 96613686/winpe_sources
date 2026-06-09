# myAlloc(unsigned __int64,CERTLIB_ALLOCATOR)

- ea: `0x18001dca8`
- end: `0x18001dd07`
- name: `?myAlloc@@YAPEAX_KW4CERTLIB_ALLOCATOR@@@Z`
- size: `95`
- prototype: `void *__fastcall(size_t, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ab18`
- `0x18001e060`

## callees

- `0x180008400`
- `0x18001dca8`

## import_xrefs

- `msvcrt!malloc` at `0x18001dcc1`
- `msvcrt!malloc` at `0x18001dcc1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dcce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001dcce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dcf8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dcf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001dcd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001dcd6`

## pseudocode

```c
void *__fastcall myAlloc(size_t a1, int a2)
{
  int v2; // edx
  int v3; // edx
  void *v4; // rbx
  void *v5; // rax

  v2 = a2 - 1;
  if ( v2 )
  {
    v3 = v2 - 1;
    if ( v3 )
    {
      if ( v3 != 2 )
      {
        v4 = 0;
LABEL_9:
        CSPrintErrorLineFile(0x6301CAu, -2147024882);
        SetLastError(0x8007000E);
        return v4;
      }
      v5 = malloc(a1);
    }
    else
    {
      v5 = LocalAlloc(0, a1);
    }
  }
  else
  {
    v5 = CoTaskMemAlloc(a1);
  }
  v4 = v5;
  if ( !v5 )
    goto LABEL_9;
  return v4;
}

```

## disassembly

```asm
0x18001dca8  push    rbx
0x18001dcaa  sub     rsp, 20h
0x18001dcae  sub     edx, 1
0x18001dcb1  jz      short loc_18001DCD6
0x18001dcb3  sub     edx, 1
0x18001dcb6  jz      short loc_18001DCC9
0x18001dcb8  cmp     edx, 2
0x18001dcbb  jz      short loc_18001DCC1
0x18001dcbd  xor     ebx, ebx
0x18001dcbf  jmp     short loc_18001DCE4
0x18001dcc1  call    cs:__imp_malloc
0x18001dcc7  jmp     short loc_18001DCDC
0x18001dcc9  mov     rdx, rcx; uBytes
0x18001dccc  xor     ecx, ecx; uFlags
0x18001dcce  call    cs:__imp_LocalAlloc
0x18001dcd4  jmp     short loc_18001DCDC
0x18001dcd6  call    cs:__imp_CoTaskMemAlloc
0x18001dcdc  mov     rbx, rax
0x18001dcdf  test    rax, rax
0x18001dce2  jnz     short loc_18001DCFE
0x18001dce4  mov     edx, 8007000Eh; int
0x18001dce9  mov     ecx, 6301CAh; unsigned int
0x18001dcee  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001dcf3  mov     ecx, 8007000Eh; dwErrCode
0x18001dcf8  call    cs:__imp_SetLastError
0x18001dcfe  mov     rax, rbx
0x18001dd01  add     rsp, 20h
0x18001dd05  pop     rbx
0x18001dd06  retn
```
