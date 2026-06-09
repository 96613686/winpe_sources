# std::vector<uchar,std::allocator<uchar>>::~vector<uchar,std::allocator<uchar>>(void)

- ea: `0x18001767c`
- end: `0x1800176e0`
- name: `??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(char **)`
- caller_count: `25`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800188f0`
- `0x180019794`
- `0x18001abf0`
- `0x18001e774`
- `0x18002647c`
- `0x180026844`
- `0x180027044`
- `0x180027230`
- `0x180028100`
- `0x18002fc6c`
- `0x18002fdc0`
- `0x180030020`
- `0x180031b06`
- `0x180031bcc`
- `0x180031d63`
- `0x180031f5b`
- `0x18003220a`
- `0x18003222e`
- `0x180032264`
- `0x180032276`
- `0x180032288`
- `0x18003283b`
- `0x18003284d`
- `0x1800328b2`
- `0x180032917`

## callees

- `0x1800025a0`
- `0x18001767c`

## pseudocode

```c
void __fastcall std::vector<unsigned char>::~vector<unsigned char>(char **a1)
{
  char *v1; // rax
  unsigned __int64 v3; // rdx
  char *v4; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v3 = a1[2] - v1;
    if ( v3 < 0x1000 )
    {
      v4 = *a1;
    }
    else
    {
      v4 = (char *)*((_QWORD *)v1 - 1);
      if ( (unsigned __int64)(v1 - v4 - 8) > 0x1F )
        __fastfail(5u);
      v3 += 39LL;
    }
    operator delete(v4, v3);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18001767c  push    rbx
0x18001767e  sub     rsp, 20h
0x180017682  mov     rax, [rcx]
0x180017685  mov     rbx, rcx
0x180017688  test    rax, rax
0x18001768b  jz      short loc_1800176DA
0x18001768d  mov     rdx, [rcx+10h]
0x180017691  sub     rdx, rax; unsigned __int64
0x180017694  cmp     rdx, 1000h
0x18001769b  jb      short loc_1800176BB
0x18001769d  mov     rcx, [rax-8]
0x1800176a1  sub     rax, rcx
0x1800176a4  sub     rax, 8
0x1800176a8  cmp     rax, 1Fh
0x1800176ac  ja      short loc_1800176B4
0x1800176ae  add     rdx, 27h ; '''
0x1800176b2  jmp     short loc_1800176BE
0x1800176b4  mov     ecx, 5
0x1800176b9  int     29h; Win8: RtlFailFast(ecx)
0x1800176bb  mov     rcx, rax; void *
0x1800176be  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800176c3  mov     qword ptr [rbx], 0
0x1800176ca  mov     qword ptr [rbx+8], 0
0x1800176d2  mov     qword ptr [rbx+10h], 0
0x1800176da  add     rsp, 20h
0x1800176de  pop     rbx
0x1800176df  retn
```
