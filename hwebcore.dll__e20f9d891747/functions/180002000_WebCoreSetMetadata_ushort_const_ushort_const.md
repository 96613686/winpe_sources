# WebCoreSetMetadata(ushort const *,ushort const *)

- ea: `0x180002000`
- end: `0x1800020a6`
- name: `?WebCoreSetMetadata@@YAJPEBG0@Z`
- size: `166`
- prototype: `__int64 __fastcall(wchar_t *String2, wchar_t *Source)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001008`
- `0x180002000`
- `0x180002bae`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180002087`
- `msvcrt!wcscpy_s` at `0x180002087`

## pseudocode

```c
__int64 __fastcall WebCoreSetMetadata(wchar_t *String2, wchar_t *Source)
{
  unsigned int v2; // ebx
  unsigned __int64 v4; // rax
  rsize_t v5; // rbp
  wchar_t *v6; // rax
  wchar_t *v7; // rsi

  v2 = 0;
  if ( g_hIisW3AdmModule )
  {
    return (unsigned int)-2147023840;
  }
  else if ( !wcscmp_0(L"applicationPool", String2) )
  {
    if ( !Source )
      return (unsigned int)-2147024809;
    v4 = -1;
    do
      ++v4;
    while ( Source[v4] );
    if ( v4 < 0xFFFFFFFF )
    {
      v5 = v4 + 1;
      v6 = (wchar_t *)operator new(saturated_mul(v4 + 1, 2u));
      v7 = v6;
      if ( v6 )
      {
        wcscpy_s(v6, v5, Source);
        g_szAppPool = v7;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2147024846;
  }
  return v2;
}

```

## disassembly

```asm
0x180002000  push    rbx
0x180002002  push    rbp
0x180002003  push    rsi
0x180002004  push    rdi
0x180002005  sub     rsp, 28h
0x180002009  xor     ebx, ebx
0x18000200b  mov     rdi, rdx
0x18000200e  cmp     cs:?g_hIisW3AdmModule@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hIisW3AdmModule
0x180002015  jz      short loc_18000201E
0x180002017  mov     ebx, 80070420h
0x18000201c  jmp     short loc_18000209B
0x18000201e  mov     rdx, rcx; String2
0x180002021  lea     rcx, aApplicationpoo; "applicationPool"
0x180002028  call    wcscmp_0
0x18000202d  test    eax, eax
0x18000202f  jnz     short loc_180002096
0x180002031  test    rdi, rdi
0x180002034  jz      short loc_180002050
0x180002036  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000203a  mov     rax, r8
0x18000203d  inc     rax
0x180002040  cmp     [rdi+rax*2], bx
0x180002044  jnz     short loc_18000203D
0x180002046  mov     ecx, 0FFFFFFFFh
0x18000204b  cmp     rax, rcx
0x18000204e  jb      short loc_180002057
0x180002050  mov     ebx, 80070057h
0x180002055  jmp     short loc_18000209B
0x180002057  lea     rbp, [rax+1]
0x18000205b  mov     eax, 2
0x180002060  mul     rbp
0x180002063  cmovb   rax, r8
0x180002067  mov     rcx, rax; Size
0x18000206a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000206f  mov     rsi, rax
0x180002072  test    rax, rax
0x180002075  jnz     short loc_18000207E
0x180002077  mov     ebx, 8007000Eh
0x18000207c  jmp     short loc_18000209B
0x18000207e  mov     r8, rdi; Source
0x180002081  mov     rdx, rbp; SizeInWords
0x180002084  mov     rcx, rsi; Destination
0x180002087  call    cs:__imp_wcscpy_s
0x18000208d  mov     cs:?g_szAppPool@@3PEAGEA, rsi; ushort * g_szAppPool
0x180002094  jmp     short loc_18000209B
0x180002096  mov     ebx, 80070032h
0x18000209b  mov     eax, ebx
0x18000209d  add     rsp, 28h
0x1800020a1  pop     rdi
0x1800020a2  pop     rsi
0x1800020a3  pop     rbp
0x1800020a4  pop     rbx
0x1800020a5  retn
```
