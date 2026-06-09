# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180007f78`
- end: `0x180007fdc`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180010724`
- `0x1800107e0`
- `0x18001084c`
- `0x180010a00`
- `0x1800127c7`
- `0x1800127eb`

## callees

- `0x180001fec`
- `0x180007f78`

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
0x180007f78  push    rbx
0x180007f7a  sub     rsp, 20h
0x180007f7e  mov     rdx, [rcx+18h]
0x180007f82  mov     rbx, rcx
0x180007f85  cmp     rdx, 7
0x180007f89  jbe     short loc_180007FC5
0x180007f8b  mov     rax, [rcx]
0x180007f8e  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180007f96  cmp     rdx, 1000h
0x180007f9d  jb      short loc_180007FBD
0x180007f9f  mov     rcx, [rax-8]
0x180007fa3  sub     rax, rcx
0x180007fa6  sub     rax, 8
0x180007faa  cmp     rax, 1Fh
0x180007fae  ja      short loc_180007FB6
0x180007fb0  add     rdx, 27h ; '''
0x180007fb4  jmp     short loc_180007FC0
0x180007fb6  mov     ecx, 5
0x180007fbb  int     29h; Win8: RtlFailFast(ecx)
0x180007fbd  mov     rcx, rax; void *
0x180007fc0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007fc5  xor     eax, eax
0x180007fc7  mov     qword ptr [rbx+18h], 7
0x180007fcf  mov     [rbx+10h], rax
0x180007fd3  mov     [rbx], ax
0x180007fd6  add     rsp, 20h
0x180007fda  pop     rbx
0x180007fdb  retn
```
