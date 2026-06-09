# SspiFreeAsyncContext

- ea: `0x180026500`
- end: `0x180026576`
- name: `SspiFreeAsyncContext`
- size: `118`
- prototype: `void __stdcall(SspiAsyncContext *Handle)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180026500`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x180026547`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x180026547`

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
0x180026500  sub     rsp, 28h
0x180026504  mov     rdx, rcx; Entry
0x180026507  test    rcx, rcx
0x18002650a  jz      short loc_180026553
0x18002650c  mov     [rsp+28h+var_8], rdi
0x180026511  test    dl, 4
0x180026514  jnz     short loc_180026559
0x180026516  mov     r8d, 3Ch ; '<'
0x18002651c  mov     r9, rcx
0x18002651f  mov     rcx, r8
0x180026522  mov     rax, 0A5A5A5A5A5A5A5A5h
0x18002652c  shr     rcx, 1
0x18002652f  mov     rdi, r9
0x180026532  rep stosq
0x180026535  mov     rdi, [rsp+28h+var_8]
0x18002653a  test    r8b, 1
0x18002653e  jnz     short loc_18002656B
0x180026540  lea     rcx, stru_180019690; Lookaside
0x180026547  call    cs:__imp_ExFreeToLookasideListEx
0x18002654e  nop     dword ptr [rax+rax+00h]
0x180026553  add     rsp, 28h
0x180026557  retn
0x180026559  mov     dword ptr [rcx], 0A5A5A5A5h
0x18002655f  lea     r9, [rcx+4]
0x180026563  mov     r8d, 3Bh ; ';'
0x180026569  jmp     short loc_18002651F
0x18002656b  mov     dword ptr [r9+r8*4-4], 0A5A5A5A5h
0x180026574  jmp     short loc_180026540
```
