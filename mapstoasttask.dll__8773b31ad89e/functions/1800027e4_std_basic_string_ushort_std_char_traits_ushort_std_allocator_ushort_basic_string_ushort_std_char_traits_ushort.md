# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x1800027e4`
- end: `0x180002848`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `11`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800044a8`
- `0x180005e60`
- `0x1800097b0`
- `0x1800097d4`
- `0x180009bb4`
- `0x180009bc6`
- `0x180009bd8`
- `0x180009bea`
- `0x180009bfc`
- `0x180009c0e`
- `0x180009c20`

## callees

- `0x180001624`
- `0x1800027e4`

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
0x1800027e4  push    rbx
0x1800027e6  sub     rsp, 20h
0x1800027ea  mov     rdx, [rcx+18h]
0x1800027ee  mov     rbx, rcx
0x1800027f1  cmp     rdx, 7
0x1800027f5  jbe     short loc_180002831
0x1800027f7  mov     rax, [rcx]
0x1800027fa  lea     rdx, ds:2[rdx*2]
0x180002802  cmp     rdx, 1000h
0x180002809  jb      short loc_180002829
0x18000280b  mov     rcx, [rax-8]
0x18000280f  sub     rax, rcx
0x180002812  sub     rax, 8
0x180002816  cmp     rax, 1Fh
0x18000281a  ja      short loc_180002822
0x18000281c  add     rdx, 27h ; '''
0x180002820  jmp     short loc_18000282C
0x180002822  mov     ecx, 5
0x180002827  int     29h; Win8: RtlFailFast(ecx)
0x180002829  mov     rcx, rax; Block
0x18000282c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002831  xor     eax, eax
0x180002833  mov     qword ptr [rbx+18h], 7
0x18000283b  mov     [rbx+10h], rax
0x18000283f  mov     [rbx], ax
0x180002842  add     rsp, 20h
0x180002846  pop     rbx
0x180002847  retn
```
