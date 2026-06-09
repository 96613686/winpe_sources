# myAlloc(unsigned __int64,CERTLIB_ALLOCATOR)

- ea: `0x180020470`
- end: `0x1800204d0`
- name: `?myAlloc@@YAPEAX_KW4CERTLIB_ALLOCATOR@@@Z`
- size: `96`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a000`
- `0x18001a350`
- `0x180020750`
- `0x180020770`
- `0x18002966c`

## callees

- `0x180020470`

## import_xrefs

- `msvcrt!malloc` at `0x180020489`
- `msvcrt!malloc` at `0x180020489`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800204c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800204c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020496`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002049e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002049e`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800204b6`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800204b6`

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
0x180020470  push    rbx
0x180020472  sub     rsp, 20h
0x180020476  sub     edx, 1
0x180020479  jz      short loc_18002049E
0x18002047b  sub     edx, 1
0x18002047e  jz      short loc_180020491
0x180020480  cmp     edx, 2
0x180020483  jz      short loc_180020489
0x180020485  xor     ebx, ebx
0x180020487  jmp     short loc_1800204AC
0x180020489  call    cs:__imp_malloc
0x18002048f  jmp     short loc_1800204A4
0x180020491  mov     rdx, rcx; uBytes
0x180020494  xor     ecx, ecx; uFlags
0x180020496  call    cs:__imp_LocalAlloc
0x18002049c  jmp     short loc_1800204A4
0x18002049e  call    cs:__imp_CoTaskMemAlloc
0x1800204a4  mov     rbx, rax
0x1800204a7  test    rax, rax
0x1800204aa  jnz     short loc_1800204C7
0x1800204ac  mov     edx, 8007000Eh
0x1800204b1  mov     ecx, 6301CAh
0x1800204b6  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800204bc  mov     ecx, 8007000Eh; dwErrCode
0x1800204c1  call    cs:__imp_SetLastError
0x1800204c7  mov     rax, rbx
0x1800204ca  add     rsp, 20h
0x1800204ce  pop     rbx
0x1800204cf  retn
```
