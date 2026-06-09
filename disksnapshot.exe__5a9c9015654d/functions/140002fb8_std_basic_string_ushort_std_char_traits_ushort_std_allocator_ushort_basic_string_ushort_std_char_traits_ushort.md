# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140002fb8`
- end: `0x14000301c`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `22`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400032c4`
- `0x1400059b4`
- `0x140005e10`
- `0x140006424`
- `0x140006c30`
- `0x1400082d0`
- `0x140008590`
- `0x14000a604`
- `0x14000b144`
- `0x14000ba74`
- `0x14000c62f`
- `0x14000c641`
- `0x14000c653`
- `0x14000c665`
- `0x14000c883`
- `0x14000c9ac`
- `0x14000ca4b`
- `0x14000ca5d`
- `0x14000ca6f`
- `0x14000ca81`
- `0x14000ca93`
- `0x14000caa5`

## callees

- `0x140001cb8`
- `0x140002fb8`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  const struct std::nothrow_t *v4; // rdx
  char *v5; // rcx
  __int64 result; // rax

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    v4 = (const struct std::nothrow_t *)(2 * v1 + 2);
    if ( (unsigned __int64)v4 < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v5 - 8) > 0x1F )
        __fastfail(5u);
      v4 = (const struct std::nothrow_t *)((char *)v4 + 39);
    }
    operator delete(v5, v4);
  }
  result = 0;
  a1[3] = (char *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x140002fb8  push    rbx
0x140002fba  sub     rsp, 20h
0x140002fbe  mov     rdx, [rcx+18h]
0x140002fc2  mov     rbx, rcx
0x140002fc5  cmp     rdx, 7
0x140002fc9  jbe     short loc_140003005
0x140002fcb  mov     rax, [rcx]
0x140002fce  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x140002fd6  cmp     rdx, 1000h
0x140002fdd  jb      short loc_140002FFD
0x140002fdf  mov     rcx, [rax-8]
0x140002fe3  sub     rax, rcx
0x140002fe6  sub     rax, 8
0x140002fea  cmp     rax, 1Fh
0x140002fee  ja      short loc_140002FF6
0x140002ff0  add     rdx, 27h ; '''
0x140002ff4  jmp     short loc_140003000
0x140002ff6  mov     ecx, 5
0x140002ffb  int     29h; Win8: RtlFailFast(ecx)
0x140002ffd  mov     rcx, rax; void *
0x140003000  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140003005  xor     eax, eax
0x140003007  mov     qword ptr [rbx+18h], 7
0x14000300f  mov     [rbx+10h], rax
0x140003013  mov     [rbx], ax
0x140003016  add     rsp, 20h
0x14000301a  pop     rbx
0x14000301b  retn
```
