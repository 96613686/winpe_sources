# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180008d88`
- end: `0x180008dec`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `17`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008334`
- `0x1800084c8`
- `0x180008988`
- `0x180008df4`
- `0x180008ea4`
- `0x180008ee8`
- `0x1800096b0`
- `0x180009774`
- `0x18000986c`
- `0x18000993c`
- `0x180009d90`
- `0x180009ec0`
- `0x180009f54`
- `0x18000c6b0`
- `0x18000c950`
- `0x18000dda3`
- `0x18000ddd9`

## callees

- `0x180001f70`
- `0x180008d88`

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
0x180008d88  push    rbx
0x180008d8a  sub     rsp, 20h
0x180008d8e  mov     rdx, [rcx+18h]
0x180008d92  mov     rbx, rcx
0x180008d95  cmp     rdx, 7
0x180008d99  jbe     short loc_180008DD5
0x180008d9b  mov     rax, [rcx]
0x180008d9e  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180008da6  cmp     rdx, 1000h
0x180008dad  jb      short loc_180008DCD
0x180008daf  mov     rcx, [rax-8]
0x180008db3  sub     rax, rcx
0x180008db6  sub     rax, 8
0x180008dba  cmp     rax, 1Fh
0x180008dbe  ja      short loc_180008DC6
0x180008dc0  add     rdx, 27h ; '''
0x180008dc4  jmp     short loc_180008DD0
0x180008dc6  mov     ecx, 5
0x180008dcb  int     29h; Win8: RtlFailFast(ecx)
0x180008dcd  mov     rcx, rax; void *
0x180008dd0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008dd5  xor     eax, eax
0x180008dd7  mov     qword ptr [rbx+18h], 7
0x180008ddf  mov     [rbx+10h], rax
0x180008de3  mov     [rbx], ax
0x180008de6  add     rsp, 20h
0x180008dea  pop     rbx
0x180008deb  retn
```
