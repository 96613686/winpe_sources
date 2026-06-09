# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x180008d20`
- end: `0x180008d81`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(char **)`
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800085fc`
- `0x180008c40`
- `0x180008ea4`
- `0x1800096b0`
- `0x18000a59c`
- `0x18000da97`
- `0x18000db56`
- `0x18000db68`
- `0x18000dcd6`
- `0x18000dd02`
- `0x18000dd14`
- `0x18000dd26`

## callees

- `0x180001f70`
- `0x180008d20`

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
0x180008d20  push    rbx
0x180008d22  sub     rsp, 20h
0x180008d26  mov     rdx, [rcx+18h]
0x180008d2a  mov     rbx, rcx
0x180008d2d  cmp     rdx, 0Fh
0x180008d31  jbe     short loc_180008D68
0x180008d33  mov     rax, [rcx]
0x180008d36  inc     rdx; unsigned __int64
0x180008d39  cmp     rdx, 1000h
0x180008d40  jb      short loc_180008D60
0x180008d42  mov     rcx, [rax-8]
0x180008d46  sub     rax, rcx
0x180008d49  sub     rax, 8
0x180008d4d  cmp     rax, 1Fh
0x180008d51  ja      short loc_180008D59
0x180008d53  add     rdx, 27h ; '''
0x180008d57  jmp     short loc_180008D63
0x180008d59  mov     ecx, 5
0x180008d5e  int     29h; Win8: RtlFailFast(ecx)
0x180008d60  mov     rcx, rax; void *
0x180008d63  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008d68  mov     qword ptr [rbx+10h], 0
0x180008d70  mov     qword ptr [rbx+18h], 0Fh
0x180008d78  mov     byte ptr [rbx], 0
0x180008d7b  add     rsp, 20h
0x180008d7f  pop     rbx
0x180008d80  retn
```
