# std::vector<uchar,std::allocator<uchar>>::~vector<uchar,std::allocator<uchar>>(void)

- ea: `0x18000c45c`
- end: `0x18000c4c0`
- name: `??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(char **)`
- caller_count: `39`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000b854`
- `0x18000bd1c`
- `0x18000bedc`
- `0x18000bf50`
- `0x18000c1d8`
- `0x18000c278`
- `0x18000c284`
- `0x18000c2ac`
- `0x18000c2dc`
- `0x18000c314`
- `0x18000c354`
- `0x18000c8ec`
- `0x18000cdbc`
- `0x18000dab8`
- `0x18000e100`
- `0x18000e8dc`
- `0x18000ebf0`
- `0x18000ec58`
- `0x18000edb0`
- `0x18000ee44`
- `0x18000eef0`
- `0x18000efe0`
- `0x18000f1ac`
- `0x18000f814`
- `0x18000fe14`
- `0x180010870`
- `0x18001155c`
- `0x180011600`
- `0x180011e90`
- `0x180015f1b`
- `0x18001600a`
- `0x180016186`
- `0x180016272`
- `0x180016284`
- `0x180016296`
- `0x1800162a8`
- `0x1800162ba`
- `0x180016338`
- `0x180016380`

## callees

- `0x180001bb4`
- `0x18000c45c`

## pseudocode

```c
void __fastcall std::vector<unsigned char>::~vector<unsigned char>(char **a1)
{
  char *v1; // rax
  char *v3; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    if ( (unsigned __int64)(a1[2] - v1) < 0x1000 )
    {
      v3 = *a1;
    }
    else
    {
      v3 = (char *)*((_QWORD *)v1 - 1);
      if ( (unsigned __int64)(v1 - v3 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v3);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18000c45c  push    rbx
0x18000c45e  sub     rsp, 20h
0x18000c462  mov     rax, [rcx]
0x18000c465  mov     rbx, rcx
0x18000c468  test    rax, rax
0x18000c46b  jz      short loc_18000C4BA
0x18000c46d  mov     rdx, [rcx+10h]
0x18000c471  sub     rdx, rax
0x18000c474  cmp     rdx, 1000h
0x18000c47b  jb      short loc_18000C49B
0x18000c47d  mov     rcx, [rax-8]
0x18000c481  sub     rax, rcx
0x18000c484  sub     rax, 8
0x18000c488  cmp     rax, 1Fh
0x18000c48c  ja      short loc_18000C494
0x18000c48e  add     rdx, 27h ; '''
0x18000c492  jmp     short loc_18000C49E
0x18000c494  mov     ecx, 5
0x18000c499  int     29h; Win8: RtlFailFast(ecx)
0x18000c49b  mov     rcx, rax; Block
0x18000c49e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c4a3  mov     qword ptr [rbx], 0
0x18000c4aa  mov     qword ptr [rbx+8], 0
0x18000c4b2  mov     qword ptr [rbx+10h], 0
0x18000c4ba  add     rsp, 20h
0x18000c4be  pop     rbx
0x18000c4bf  retn
```
