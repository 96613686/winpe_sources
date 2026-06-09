# WebCoreSetMetadata(ushort const *,ushort const *)

- ea: `0x1800020b0`
- end: `0x180002160`
- name: `?WebCoreSetMetadata@@YAJPEBG0@Z`
- size: `176`
- prototype: `__int64 __fastcall(wchar_t *String2, wchar_t *Source)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001008`
- `0x1800020b0`
- `0x180002dae`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000213a`
- `msvcrt!wcscpy_s` at `0x18000213a`

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
0x1800020b0  push    rbx
0x1800020b2  push    rbp
0x1800020b3  push    rsi
0x1800020b4  push    rdi
0x1800020b5  sub     rsp, 28h
0x1800020b9  xor     ebx, ebx
0x1800020bb  mov     rdi, rdx
0x1800020be  cmp     cs:?g_hIisW3AdmModule@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hIisW3AdmModule
0x1800020c5  jz      short loc_1800020D1
0x1800020c7  mov     ebx, 80070420h
0x1800020cc  jmp     loc_180002154
0x1800020d1  mov     rdx, rcx; String2
0x1800020d4  lea     rcx, aApplicationpoo; "applicationPool"
0x1800020db  call    wcscmp_0
0x1800020e0  test    eax, eax
0x1800020e2  jnz     short loc_18000214F
0x1800020e4  test    rdi, rdi
0x1800020e7  jz      short loc_180002103
0x1800020e9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800020ed  mov     rax, r8
0x1800020f0  inc     rax
0x1800020f3  cmp     [rdi+rax*2], bx
0x1800020f7  jnz     short loc_1800020F0
0x1800020f9  mov     ecx, 0FFFFFFFFh
0x1800020fe  cmp     rax, rcx
0x180002101  jb      short loc_18000210A
0x180002103  mov     ebx, 80070057h
0x180002108  jmp     short loc_180002154
0x18000210a  lea     rbp, [rax+1]
0x18000210e  mov     eax, 2
0x180002113  mul     rbp
0x180002116  cmovb   rax, r8
0x18000211a  mov     rcx, rax; Size
0x18000211d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002122  mov     rsi, rax
0x180002125  test    rax, rax
0x180002128  jnz     short loc_180002131
0x18000212a  mov     ebx, 8007000Eh
0x18000212f  jmp     short loc_180002154
0x180002131  mov     r8, rdi; Source
0x180002134  mov     rdx, rbp; SizeInWords
0x180002137  mov     rcx, rsi; Destination
0x18000213a  call    cs:__imp_wcscpy_s
0x180002141  nop     dword ptr [rax+rax+00h]
0x180002146  mov     cs:?g_szAppPool@@3PEAGEA, rsi; ushort * g_szAppPool
0x18000214d  jmp     short loc_180002154
0x18000214f  mov     ebx, 80070032h
0x180002154  mov     eax, ebx
0x180002156  add     rsp, 28h
0x18000215a  pop     rdi
0x18000215b  pop     rsi
0x18000215c  pop     rbp
0x18000215d  pop     rbx
0x18000215e  retn
```
