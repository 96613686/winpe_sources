# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x1800082b8`
- end: `0x180008319`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(char **)`
- caller_count: `22`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800085ac`
- `0x1800088dc`
- `0x180008fd8`
- `0x18000a09c`
- `0x18000a400`
- `0x18000c8e0`
- `0x18000ccc0`
- `0x18000cee0`
- `0x18000d200`
- `0x18000d340`
- `0x18000d590`
- `0x18000d7f0`
- `0x180013fee`
- `0x1800140c6`
- `0x1800140d8`
- `0x1800140fc`
- `0x180014120`
- `0x180014168`
- `0x180014274`
- `0x180014298`
- `0x1800142ce`
- `0x18001434c`

## callees

- `0x180001564`
- `0x1800082b8`

## pseudocode

```c
void __fastcall std::string::~string(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  unsigned __int64 v4; // rdx
  char *v5; // rcx

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 0xF )
  {
    v3 = *a1;
    v4 = v1 + 1;
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
  a1[2] = 0;
  a1[3] = (char *)15;
  *(_BYTE *)a1 = 0;
}

```

## disassembly

```asm
0x1800082b8  push    rbx
0x1800082ba  sub     rsp, 20h
0x1800082be  mov     rdx, [rcx+18h]
0x1800082c2  mov     rbx, rcx
0x1800082c5  cmp     rdx, 0Fh
0x1800082c9  jbe     short loc_180008300
0x1800082cb  mov     rax, [rcx]
0x1800082ce  inc     rdx; unsigned __int64
0x1800082d1  cmp     rdx, 1000h
0x1800082d8  jb      short loc_1800082F8
0x1800082da  mov     rcx, [rax-8]
0x1800082de  sub     rax, rcx
0x1800082e1  sub     rax, 8
0x1800082e5  cmp     rax, 1Fh
0x1800082e9  ja      short loc_1800082F1
0x1800082eb  add     rdx, 27h ; '''
0x1800082ef  jmp     short loc_1800082FB
0x1800082f1  mov     ecx, 5
0x1800082f6  int     29h; Win8: RtlFailFast(ecx)
0x1800082f8  mov     rcx, rax; void *
0x1800082fb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008300  mov     qword ptr [rbx+10h], 0
0x180008308  mov     qword ptr [rbx+18h], 0Fh
0x180008310  mov     byte ptr [rbx], 0
0x180008313  add     rsp, 20h
0x180008317  pop     rbx
0x180008318  retn
```
