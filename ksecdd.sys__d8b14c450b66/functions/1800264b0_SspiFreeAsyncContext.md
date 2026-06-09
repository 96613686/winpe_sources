# SspiFreeAsyncContext

- ea: `0x1800264b0`
- end: `0x180026526`
- name: `SspiFreeAsyncContext`
- size: `118`
- prototype: `void __stdcall(SspiAsyncContext *Handle)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800264b0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1800264f7`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1800264f7`

## pseudocode

```c
void __stdcall SspiFreeAsyncContext(SspiAsyncContext *Handle)
{
  unsigned __int64 v1; // r8
  SspiAsyncContext *v2; // r9

  if ( Handle )
  {
    if ( ((unsigned __int8)Handle & 4) != 0 )
    {
      *(_DWORD *)Handle = -1515870811;
      v2 = (SspiAsyncContext *)((char *)Handle + 4);
      v1 = 59;
    }
    else
    {
      v1 = 60;
      v2 = Handle;
    }
    memset(v2, 0xA5u, 8 * (v1 >> 1));
    if ( (v1 & 1) != 0 )
      *((_DWORD *)v2 + v1 - 1) = -1515870811;
    ExFreeToLookasideListEx(&stru_180019690, Handle);
  }
}

```

## disassembly

```asm
0x1800264b0  sub     rsp, 28h
0x1800264b4  mov     rdx, rcx; Entry
0x1800264b7  test    rcx, rcx
0x1800264ba  jz      short loc_180026503
0x1800264bc  mov     [rsp+28h+var_8], rdi
0x1800264c1  test    dl, 4
0x1800264c4  jnz     short loc_180026509
0x1800264c6  mov     r8d, 3Ch ; '<'
0x1800264cc  mov     r9, rcx
0x1800264cf  mov     rcx, r8
0x1800264d2  mov     rax, 0A5A5A5A5A5A5A5A5h
0x1800264dc  shr     rcx, 1
0x1800264df  mov     rdi, r9
0x1800264e2  rep stosq
0x1800264e5  mov     rdi, [rsp+28h+var_8]
0x1800264ea  test    r8b, 1
0x1800264ee  jnz     short loc_18002651B
0x1800264f0  lea     rcx, stru_180019690; Lookaside
0x1800264f7  call    cs:__imp_ExFreeToLookasideListEx
0x1800264fe  nop     dword ptr [rax+rax+00h]
0x180026503  add     rsp, 28h
0x180026507  retn
0x180026509  mov     dword ptr [rcx], 0A5A5A5A5h
0x18002650f  lea     r9, [rcx+4]
0x180026513  mov     r8d, 3Bh ; ';'
0x180026519  jmp     short loc_1800264CF
0x18002651b  mov     dword ptr [r9+r8*4-4], 0A5A5A5A5h
0x180026524  jmp     short loc_1800264F0
```
