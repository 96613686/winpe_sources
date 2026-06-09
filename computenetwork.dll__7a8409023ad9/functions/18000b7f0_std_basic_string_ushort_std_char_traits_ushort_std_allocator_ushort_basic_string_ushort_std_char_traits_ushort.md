# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000b7f0`
- end: `0x18000b854`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000b8c4`
- `0x18000bac0`
- `0x18000e2eb`
- `0x18000e301`
- `0x18000e317`
- `0x18000e32d`

## callees

- `0x1800019d0`
- `0x18000b7f0`

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
0x18000b7f0  push    rbx
0x18000b7f2  sub     rsp, 20h
0x18000b7f6  mov     rdx, [rcx+18h]
0x18000b7fa  mov     rbx, rcx
0x18000b7fd  cmp     rdx, 7
0x18000b801  jbe     short loc_18000B83D
0x18000b803  mov     rax, [rcx]
0x18000b806  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18000b80e  cmp     rdx, 1000h
0x18000b815  jb      short loc_18000B835
0x18000b817  mov     rcx, [rax-8]
0x18000b81b  sub     rax, rcx
0x18000b81e  sub     rax, 8
0x18000b822  cmp     rax, 1Fh
0x18000b826  ja      short loc_18000B82E
0x18000b828  add     rdx, 27h ; '''
0x18000b82c  jmp     short loc_18000B838
0x18000b82e  mov     ecx, 5
0x18000b833  int     29h; Win8: RtlFailFast(ecx)
0x18000b835  mov     rcx, rax; void *
0x18000b838  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b83d  xor     eax, eax
0x18000b83f  mov     qword ptr [rbx+18h], 7
0x18000b847  mov     [rbx+10h], rax
0x18000b84b  mov     [rbx], ax
0x18000b84e  add     rsp, 20h
0x18000b852  pop     rbx
0x18000b853  retn
```
