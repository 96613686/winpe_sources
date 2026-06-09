# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000dcb0`
- end: `0x18000dd14`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(char **)`
- caller_count: `21`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000df40`
- `0x180010710`
- `0x180011d60`
- `0x180012108`
- `0x18001219c`
- `0x1800122c4`
- `0x18001382c`
- `0x180013d34`
- `0x180014336`
- `0x180014348`
- `0x180014374`
- `0x1800143fa`
- `0x18001440c`
- `0x18001441e`
- `0x180014430`
- `0x180014442`
- `0x180014454`
- `0x180014466`
- `0x180014478`
- `0x18001448a`
- `0x18001449c`

## callees

- `0x180002c8c`
- `0x18000dcb0`

## pseudocode

```c
void __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  unsigned __int64 v4; // rdx
  char *v5; // rcx

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
  a1[3] = (char *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
}

```

## disassembly

```asm
0x18000dcb0  push    rbx
0x18000dcb2  sub     rsp, 20h
0x18000dcb6  mov     rdx, [rcx+18h]
0x18000dcba  mov     rbx, rcx
0x18000dcbd  cmp     rdx, 7
0x18000dcc1  jbe     short loc_18000DCFD
0x18000dcc3  mov     rax, [rcx]
0x18000dcc6  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18000dcce  cmp     rdx, 1000h
0x18000dcd5  jb      short loc_18000DCF5
0x18000dcd7  mov     rcx, [rax-8]
0x18000dcdb  sub     rax, rcx
0x18000dcde  sub     rax, 8
0x18000dce2  cmp     rax, 1Fh
0x18000dce6  ja      short loc_18000DCEE
0x18000dce8  add     rdx, 27h ; '''
0x18000dcec  jmp     short loc_18000DCF8
0x18000dcee  mov     ecx, 5
0x18000dcf3  int     29h; Win8: RtlFailFast(ecx)
0x18000dcf5  mov     rcx, rax; void *
0x18000dcf8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dcfd  xor     eax, eax
0x18000dcff  mov     qword ptr [rbx+18h], 7
0x18000dd07  mov     [rbx+10h], rax
0x18000dd0b  mov     [rbx], ax
0x18000dd0e  add     rsp, 20h
0x18000dd12  pop     rbx
0x18000dd13  retn
```
