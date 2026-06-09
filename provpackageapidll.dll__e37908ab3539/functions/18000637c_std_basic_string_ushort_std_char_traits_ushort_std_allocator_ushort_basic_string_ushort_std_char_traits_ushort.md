# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000637c`
- end: `0x1800063e0`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800060e4`
- `0x180006308`
- `0x1800063e8`
- `0x180012b94`
- `0x180018985`
- `0x180018997`

## callees

- `0x1800020a8`
- `0x18000637c`

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
0x18000637c  push    rbx
0x18000637e  sub     rsp, 20h
0x180006382  mov     rdx, [rcx+18h]
0x180006386  mov     rbx, rcx
0x180006389  cmp     rdx, 7
0x18000638d  jbe     short loc_1800063C9
0x18000638f  mov     rax, [rcx]
0x180006392  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x18000639a  cmp     rdx, 1000h
0x1800063a1  jb      short loc_1800063C1
0x1800063a3  mov     rcx, [rax-8]
0x1800063a7  sub     rax, rcx
0x1800063aa  sub     rax, 8
0x1800063ae  cmp     rax, 1Fh
0x1800063b2  ja      short loc_1800063BA
0x1800063b4  add     rdx, 27h ; '''
0x1800063b8  jmp     short loc_1800063C4
0x1800063ba  mov     ecx, 5
0x1800063bf  int     29h; Win8: RtlFailFast(ecx)
0x1800063c1  mov     rcx, rax; void *
0x1800063c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800063c9  xor     eax, eax
0x1800063cb  mov     qword ptr [rbx+18h], 7
0x1800063d3  mov     [rbx+10h], rax
0x1800063d7  mov     [rbx], ax
0x1800063da  add     rsp, 20h
0x1800063de  pop     rbx
0x1800063df  retn
```
