# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000a348`
- end: `0x18000a3ac`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000a6a4`
- `0x18000cc33`

## callees

- `0x180001d24`
- `0x18000a348`

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
0x18000a348  push    rbx
0x18000a34a  sub     rsp, 20h
0x18000a34e  mov     rdx, [rcx+18h]
0x18000a352  mov     rbx, rcx
0x18000a355  cmp     rdx, 7
0x18000a359  jbe     short loc_18000A395
0x18000a35b  mov     rax, [rcx]
0x18000a35e  lea     rdx, ds:2[rdx*2]
0x18000a366  cmp     rdx, 1000h
0x18000a36d  jb      short loc_18000A38D
0x18000a36f  mov     rcx, [rax-8]
0x18000a373  sub     rax, rcx
0x18000a376  sub     rax, 8
0x18000a37a  cmp     rax, 1Fh
0x18000a37e  ja      short loc_18000A386
0x18000a380  add     rdx, 27h ; '''
0x18000a384  jmp     short loc_18000A390
0x18000a386  mov     ecx, 5
0x18000a38b  int     29h; Win8: RtlFailFast(ecx)
0x18000a38d  mov     rcx, rax; Block
0x18000a390  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a395  xor     eax, eax
0x18000a397  mov     qword ptr [rbx+18h], 7
0x18000a39f  mov     [rbx+10h], rax
0x18000a3a3  mov     [rbx], ax
0x18000a3a6  add     rsp, 20h
0x18000a3aa  pop     rbx
0x18000a3ab  retn
```
