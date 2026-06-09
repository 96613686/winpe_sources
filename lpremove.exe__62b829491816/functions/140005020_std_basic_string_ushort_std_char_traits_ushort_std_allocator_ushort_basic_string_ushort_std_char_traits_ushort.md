# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140005020`
- end: `0x140005084`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `34`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140003260`
- `0x140004358`
- `0x140004924`
- `0x140004fd8`
- `0x140004fe8`
- `0x14000513c`
- `0x140005960`
- `0x1400081a8`
- `0x140008558`
- `0x14000c36c`
- `0x14000cd48`
- `0x14000d124`
- `0x14000dd80`
- `0x14000de70`
- `0x14000df20`
- `0x14000e114`
- `0x14000e25c`
- `0x14000e3b8`
- `0x14000ea80`
- `0x14000eac8`
- `0x14000eeb8`
- `0x14000f490`
- `0x14000f530`
- `0x14000f8d0`
- `0x14000fefe`
- `0x14000ff10`
- `0x14000ff3c`
- `0x14000ff8a`
- `0x14000ff9c`
- `0x14000ffae`
- `0x1400103c9`
- `0x1400105cf`
- `0x14001066e`
- `0x140010680`

## callees

- `0x1400021b4`
- `0x140005020`

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
0x140005020  push    rbx
0x140005022  sub     rsp, 20h
0x140005026  mov     rdx, [rcx+18h]
0x14000502a  mov     rbx, rcx
0x14000502d  cmp     rdx, 7
0x140005031  jbe     short loc_14000506D
0x140005033  mov     rax, [rcx]
0x140005036  lea     rdx, ds:2[rdx*2]
0x14000503e  cmp     rdx, 1000h
0x140005045  jb      short loc_140005065
0x140005047  mov     rcx, [rax-8]
0x14000504b  sub     rax, rcx
0x14000504e  sub     rax, 8
0x140005052  cmp     rax, 1Fh
0x140005056  ja      short loc_14000505E
0x140005058  add     rdx, 27h ; '''
0x14000505c  jmp     short loc_140005068
0x14000505e  mov     ecx, 5
0x140005063  int     29h; Win8: RtlFailFast(ecx)
0x140005065  mov     rcx, rax; Block
0x140005068  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000506d  xor     eax, eax
0x14000506f  mov     qword ptr [rbx+18h], 7
0x140005077  mov     [rbx+10h], rax
0x14000507b  mov     [rbx], ax
0x14000507e  add     rsp, 20h
0x140005082  pop     rbx
0x140005083  retn
```
