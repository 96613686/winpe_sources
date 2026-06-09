# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x1400106b4`
- end: `0x140010718`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `13`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140010610`
- `0x140010720`
- `0x140011224`
- `0x140011a10`
- `0x140011aa0`
- `0x140011ab0`
- `0x140011b6c`
- `0x140011ea4`
- `0x14001211c`
- `0x1400124d0`
- `0x140012c08`
- `0x140013da0`
- `0x14001af34`

## callees

- `0x1400018d4`
- `0x1400106b4`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  unsigned __int64 v4; // rdx
  char *v5; // rcx
  __int64 result; // rax

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    v4 = 2 * v1 + 2;
    if ( v4 < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v5 - 8) > 0x1F )
        __fastfail(5u);
      v4 += 39LL;
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
0x1400106b4  push    rbx
0x1400106b6  sub     rsp, 20h
0x1400106ba  mov     rdx, [rcx+18h]
0x1400106be  mov     rbx, rcx
0x1400106c1  cmp     rdx, 7
0x1400106c5  jbe     short loc_140010701
0x1400106c7  mov     rax, [rcx]
0x1400106ca  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x1400106d2  cmp     rdx, 1000h
0x1400106d9  jb      short loc_1400106F9
0x1400106db  mov     rcx, [rax-8]
0x1400106df  sub     rax, rcx
0x1400106e2  sub     rax, 8
0x1400106e6  cmp     rax, 1Fh
0x1400106ea  ja      short loc_1400106F2
0x1400106ec  add     rdx, 27h ; '''
0x1400106f0  jmp     short loc_1400106FC
0x1400106f2  mov     ecx, 5
0x1400106f7  int     29h; Win8: RtlFailFast(ecx)
0x1400106f9  mov     rcx, rax; void *
0x1400106fc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140010701  xor     eax, eax
0x140010703  mov     qword ptr [rbx+18h], 7
0x14001070b  mov     [rbx+10h], rax
0x14001070f  mov     [rbx], ax
0x140010712  add     rsp, 20h
0x140010716  pop     rbx
0x140010717  retn
```
