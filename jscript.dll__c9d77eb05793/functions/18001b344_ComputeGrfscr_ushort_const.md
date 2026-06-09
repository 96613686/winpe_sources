# ComputeGrfscr(ushort const *)

- ea: `0x18001b344`
- end: `0x18001b3b9`
- name: `?ComputeGrfscr@@YAKPEBG@Z`
- size: `117`
- prototype: `unsigned int __fastcall(wchar_t *String2)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001af64`
- `0x18007aba0`
- `0x18007bc34`
- `0x180083368`
- `0x180083490`

## callees

- `0x18001b344`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001b38e`
- `msvcrt!_wcsicmp` at `0x18001b3a7`
- `msvcrt!_wcsicmp` at `0x18001b38e`
- `msvcrt!_wcsicmp` at `0x18001b3a7`

## string_xrefs

- `0x18001b3a0`: `STRIP EMBEDDED HTML COMMENTS`

## pseudocode

```c
__int64 __fastcall ComputeGrfscr(wchar_t *String2)
{
  unsigned int v2; // ebx

  v2 = 0;
  if ( String2 )
  {
    if ( *String2 != 34 || String2[1] )
    {
      if ( _wcsicmp(L"</script>", String2) )
      {
        if ( !_wcsicmp(L"STRIP EMBEDDED HTML COMMENTS", String2) )
          return 513;
      }
      else
      {
        return 1;
      }
    }
    else
    {
      return 16;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001b344  mov     [rsp+arg_0], rbx
0x18001b349  mov     [rsp+arg_8], rsi
0x18001b34e  push    rdi
0x18001b34f  sub     rsp, 20h
0x18001b353  xor     esi, esi
0x18001b355  mov     rdi, rcx
0x18001b358  mov     ebx, esi
0x18001b35a  test    rcx, rcx
0x18001b35d  jnz     short loc_18001B371
0x18001b35f  mov     rsi, [rsp+28h+arg_8]
0x18001b364  mov     eax, ebx
0x18001b366  mov     rbx, [rsp+28h+arg_0]
0x18001b36b  add     rsp, 20h
0x18001b36f  pop     rdi
0x18001b370  retn
0x18001b371  cmp     word ptr [rcx], 22h ; '"'
0x18001b375  jnz     short loc_18001B384
0x18001b377  cmp     [rcx+2], si
0x18001b37b  jnz     short loc_18001B384
0x18001b37d  mov     ebx, 10h
0x18001b382  jmp     short loc_18001B35F
0x18001b384  mov     rdx, rdi; String2
0x18001b387  lea     rcx, aScript; "</script>"
0x18001b38e  call    cs:__imp__wcsicmp
0x18001b394  test    eax, eax
0x18001b396  jnz     short loc_18001B39D
0x18001b398  lea     ebx, [rax+1]
0x18001b39b  jmp     short loc_18001B35F
0x18001b39d  mov     rdx, rdi; String2
0x18001b3a0  lea     rcx, aStripEmbeddedH; "STRIP EMBEDDED HTML COMMENTS"
0x18001b3a7  call    cs:__imp__wcsicmp
0x18001b3ad  test    eax, eax
0x18001b3af  mov     ecx, 201h
0x18001b3b4  cmovz   ebx, ecx
0x18001b3b7  jmp     short loc_18001B35F
```
