# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000fb28`
- end: `0x18000fb8c`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000fb94`
- `0x180010a14`
- `0x180010af0`
- `0x180011e7d`
- `0x180011ed7`

## callees

- `0x180001d14`
- `0x18000fb28`

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
0x18000fb28  push    rbx
0x18000fb2a  sub     rsp, 20h
0x18000fb2e  mov     rdx, [rcx+18h]
0x18000fb32  mov     rbx, rcx
0x18000fb35  cmp     rdx, 7
0x18000fb39  jbe     short loc_18000FB75
0x18000fb3b  mov     rax, [rcx]
0x18000fb3e  lea     rdx, ds:2[rdx*2]
0x18000fb46  cmp     rdx, 1000h
0x18000fb4d  jb      short loc_18000FB6D
0x18000fb4f  mov     rcx, [rax-8]
0x18000fb53  sub     rax, rcx
0x18000fb56  sub     rax, 8
0x18000fb5a  cmp     rax, 1Fh
0x18000fb5e  ja      short loc_18000FB66
0x18000fb60  add     rdx, 27h ; '''
0x18000fb64  jmp     short loc_18000FB70
0x18000fb66  mov     ecx, 5
0x18000fb6b  int     29h; Win8: RtlFailFast(ecx)
0x18000fb6d  mov     rcx, rax; Block
0x18000fb70  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fb75  xor     eax, eax
0x18000fb77  mov     qword ptr [rbx+18h], 7
0x18000fb7f  mov     [rbx+10h], rax
0x18000fb83  mov     [rbx], ax
0x18000fb86  add     rsp, 20h
0x18000fb8a  pop     rbx
0x18000fb8b  retn
```
