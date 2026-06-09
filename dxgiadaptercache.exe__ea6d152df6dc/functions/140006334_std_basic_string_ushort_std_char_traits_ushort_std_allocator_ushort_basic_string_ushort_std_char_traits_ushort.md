# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140006334`
- end: `0x140006398`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `14`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140004798`
- `0x140004d34`
- `0x140004f00`
- `0x1400051f8`
- `0x14000625c`
- `0x1400062d8`
- `0x1400066ac`
- `0x140006700`
- `0x14000893c`
- `0x14000e174`
- `0x14000eafc`
- `0x1400115e4`
- `0x140011a9a`
- `0x140011b25`

## callees

- `0x140002578`
- `0x140006334`

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
0x140006334  push    rbx
0x140006336  sub     rsp, 20h
0x14000633a  mov     rdx, [rcx+18h]
0x14000633e  mov     rbx, rcx
0x140006341  cmp     rdx, 7
0x140006345  jbe     short loc_140006381
0x140006347  mov     rax, [rcx]
0x14000634a  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x140006352  cmp     rdx, 1000h
0x140006359  jb      short loc_140006379
0x14000635b  mov     rcx, [rax-8]
0x14000635f  sub     rax, rcx
0x140006362  sub     rax, 8
0x140006366  cmp     rax, 1Fh
0x14000636a  ja      short loc_140006372
0x14000636c  add     rdx, 27h ; '''
0x140006370  jmp     short loc_14000637C
0x140006372  mov     ecx, 5
0x140006377  int     29h; Win8: RtlFailFast(ecx)
0x140006379  mov     rcx, rax; void *
0x14000637c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006381  xor     eax, eax
0x140006383  mov     qword ptr [rbx+18h], 7
0x14000638b  mov     [rbx+10h], rax
0x14000638f  mov     [rbx], ax
0x140006392  add     rsp, 20h
0x140006396  pop     rbx
0x140006397  retn
```
