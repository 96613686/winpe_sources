# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180017418`
- end: `0x18001747c`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `28`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180014740`
- `0x1800148b8`
- `0x1800149e8`
- `0x180015de0`
- `0x180016644`
- `0x1800167a0`
- `0x18001a3a0`
- `0x18001fe68`
- `0x180021bac`
- `0x1800240f0`
- `0x18002a2a8`
- `0x18002a83c`
- `0x18002d8f8`
- `0x18002e434`
- `0x180031984`
- `0x180031996`
- `0x1800319a8`
- `0x1800319d4`
- `0x1800319e6`
- `0x180031c91`
- `0x180032095`
- `0x1800320a7`
- `0x1800320f1`
- `0x1800321a8`
- `0x1800324f7`
- `0x180032559`
- `0x180032646`
- `0x180032747`

## callees

- `0x1800025a0`
- `0x180017418`

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
0x180017418  push    rbx
0x18001741a  sub     rsp, 20h
0x18001741e  mov     rdx, [rcx+18h]
0x180017422  mov     rbx, rcx
0x180017425  cmp     rdx, 7
0x180017429  jbe     short loc_180017465
0x18001742b  mov     rax, [rcx]
0x18001742e  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180017436  cmp     rdx, 1000h
0x18001743d  jb      short loc_18001745D
0x18001743f  mov     rcx, [rax-8]
0x180017443  sub     rax, rcx
0x180017446  sub     rax, 8
0x18001744a  cmp     rax, 1Fh
0x18001744e  ja      short loc_180017456
0x180017450  add     rdx, 27h ; '''
0x180017454  jmp     short loc_180017460
0x180017456  mov     ecx, 5
0x18001745b  int     29h; Win8: RtlFailFast(ecx)
0x18001745d  mov     rcx, rax; void *
0x180017460  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017465  xor     eax, eax
0x180017467  mov     qword ptr [rbx+18h], 7
0x18001746f  mov     [rbx+10h], rax
0x180017473  mov     [rbx], ax
0x180017476  add     rsp, 20h
0x18001747a  pop     rbx
0x18001747b  retn
```
