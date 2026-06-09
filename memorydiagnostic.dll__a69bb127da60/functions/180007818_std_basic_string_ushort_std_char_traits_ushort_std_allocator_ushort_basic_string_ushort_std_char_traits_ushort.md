# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180007818`
- end: `0x18000787c`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `22`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800094d4`
- `0x18000b238`
- `0x180011760`
- `0x1800139d0`
- `0x18001f1c4`
- `0x18001f6ec`
- `0x180020a50`
- `0x180020a62`
- `0x180020a74`
- `0x180020c7b`
- `0x180020c8d`
- `0x180020cbc`
- `0x180020cce`
- `0x18002118e`
- `0x1800211a0`
- `0x1800211c4`
- `0x18002131a`
- `0x180021629`
- `0x18002168f`
- `0x1800216c5`
- `0x180021740`
- `0x1800220f2`

## callees

- `0x180003294`
- `0x180007818`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  char *v4; // rcx
  __int64 result; // rax

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    if ( 2 * v1 + 2 < 0x1000 )
    {
      v4 = *a1;
    }
    else
    {
      v4 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v4 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v4);
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
0x180007818  push    rbx
0x18000781a  sub     rsp, 20h
0x18000781e  mov     rdx, [rcx+18h]
0x180007822  mov     rbx, rcx
0x180007825  cmp     rdx, 7
0x180007829  jbe     short loc_180007865
0x18000782b  mov     rax, [rcx]
0x18000782e  lea     rdx, ds:2[rdx*2]
0x180007836  cmp     rdx, 1000h
0x18000783d  jb      short loc_18000785D
0x18000783f  mov     rcx, [rax-8]
0x180007843  sub     rax, rcx
0x180007846  sub     rax, 8
0x18000784a  cmp     rax, 1Fh
0x18000784e  ja      short loc_180007856
0x180007850  add     rdx, 27h ; '''
0x180007854  jmp     short loc_180007860
0x180007856  mov     ecx, 5
0x18000785b  int     29h; Win8: RtlFailFast(ecx)
0x18000785d  mov     rcx, rax; Block
0x180007860  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007865  xor     eax, eax
0x180007867  mov     qword ptr [rbx+18h], 7
0x18000786f  mov     [rbx+10h], rax
0x180007873  mov     [rbx], ax
0x180007876  add     rsp, 20h
0x18000787a  pop     rbx
0x18000787b  retn
```
