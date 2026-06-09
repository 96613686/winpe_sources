# ComputeGrfscr(ushort const *)

- ea: `0x1800183f8`
- end: `0x18001847a`
- name: `?ComputeGrfscr@@YAKPEBG@Z`
- size: `130`
- prototype: `unsigned int __fastcall(wchar_t *String2)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018000`
- `0x18007c370`
- `0x18007d498`
- `0x18008502c`
- `0x180085154`

## callees

- `0x1800183f8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180018443`
- `msvcrt!_wcsicmp` at `0x180018462`
- `msvcrt!_wcsicmp` at `0x180018443`
- `msvcrt!_wcsicmp` at `0x180018462`

## string_xrefs

- `0x18001845b`: `STRIP EMBEDDED HTML COMMENTS`

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
0x1800183f8  mov     [rsp+arg_0], rbx
0x1800183fd  mov     [rsp+arg_8], rsi
0x180018402  push    rdi
0x180018403  sub     rsp, 20h
0x180018407  xor     esi, esi
0x180018409  mov     rdi, rcx
0x18001840c  mov     ebx, esi
0x18001840e  test    rcx, rcx
0x180018411  jnz     short loc_180018426
0x180018413  mov     rsi, [rsp+28h+arg_8]
0x180018418  mov     eax, ebx
0x18001841a  mov     rbx, [rsp+28h+arg_0]
0x18001841f  add     rsp, 20h
0x180018423  pop     rdi
0x180018424  retn
0x180018426  cmp     word ptr [rcx], 22h ; '"'
0x18001842a  jnz     short loc_180018439
0x18001842c  cmp     [rcx+2], si
0x180018430  jnz     short loc_180018439
0x180018432  mov     ebx, 10h
0x180018437  jmp     short loc_180018413
0x180018439  mov     rdx, rdi; String2
0x18001843c  lea     rcx, aScript; "</script>"
0x180018443  call    cs:__imp__wcsicmp
0x18001844a  nop     dword ptr [rax+rax+00h]
0x18001844f  test    eax, eax
0x180018451  jnz     short loc_180018458
0x180018453  lea     ebx, [rax+1]
0x180018456  jmp     short loc_180018413
0x180018458  mov     rdx, rdi; String2
0x18001845b  lea     rcx, aStripEmbeddedH; "STRIP EMBEDDED HTML COMMENTS"
0x180018462  call    cs:__imp__wcsicmp
0x180018469  nop     dword ptr [rax+rax+00h]
0x18001846e  test    eax, eax
0x180018470  mov     ecx, 201h
0x180018475  cmovz   ebx, ecx
0x180018478  jmp     short loc_180018413
```
