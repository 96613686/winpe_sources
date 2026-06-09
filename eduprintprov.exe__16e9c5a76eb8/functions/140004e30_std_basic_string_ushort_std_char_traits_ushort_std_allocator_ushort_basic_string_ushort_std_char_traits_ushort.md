# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140004e30`
- end: `0x140004e94`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `27`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000529c`
- `0x14000c540`
- `0x14000ca68`
- `0x14000d064`
- `0x14000d2a4`
- `0x14000e150`
- `0x14000e810`
- `0x14000ebec`
- `0x14000f0f0`
- `0x14000fa88`
- `0x140010230`
- `0x1400111bc`
- `0x140011344`
- `0x140011bb0`
- `0x140013243`
- `0x14001325c`
- `0x140013275`
- `0x140013380`
- `0x1400133c7`
- `0x14001340f`
- `0x140013421`
- `0x140013579`
- `0x1400135c1`
- `0x1400135ed`
- `0x140013603`
- `0x1400136c7`
- `0x1400138c9`

## callees

- `0x140002624`
- `0x140004e30`

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
0x140004e30  push    rbx
0x140004e32  sub     rsp, 20h
0x140004e36  mov     rdx, [rcx+18h]
0x140004e3a  mov     rbx, rcx
0x140004e3d  cmp     rdx, 7
0x140004e41  jbe     short loc_140004E7D
0x140004e43  mov     rax, [rcx]
0x140004e46  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x140004e4e  cmp     rdx, 1000h
0x140004e55  jb      short loc_140004E75
0x140004e57  mov     rcx, [rax-8]
0x140004e5b  sub     rax, rcx
0x140004e5e  sub     rax, 8
0x140004e62  cmp     rax, 1Fh
0x140004e66  ja      short loc_140004E6E
0x140004e68  add     rdx, 27h ; '''
0x140004e6c  jmp     short loc_140004E78
0x140004e6e  mov     ecx, 5
0x140004e73  int     29h; Win8: RtlFailFast(ecx)
0x140004e75  mov     rcx, rax; void *
0x140004e78  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004e7d  xor     eax, eax
0x140004e7f  mov     qword ptr [rbx+18h], 7
0x140004e87  mov     [rbx+10h], rax
0x140004e8b  mov     [rbx], ax
0x140004e8e  add     rsp, 20h
0x140004e92  pop     rbx
0x140004e93  retn
```
