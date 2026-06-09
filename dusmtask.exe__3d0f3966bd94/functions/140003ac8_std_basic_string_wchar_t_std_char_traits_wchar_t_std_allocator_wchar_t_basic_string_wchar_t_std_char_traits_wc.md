# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x140003ac8`
- end: `0x140003b2c`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `10`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140006304`
- `0x140007ce8`
- `0x140007cfa`
- `0x140007d0c`
- `0x140007d1e`
- `0x140007d30`
- `0x140007d42`
- `0x140007d54`
- `0x140007d66`
- `0x140007d78`

## callees

- `0x140001754`
- `0x140003ac8`

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
0x140003ac8  push    rbx
0x140003aca  sub     rsp, 20h
0x140003ace  mov     rdx, [rcx+18h]
0x140003ad2  mov     rbx, rcx
0x140003ad5  cmp     rdx, 7
0x140003ad9  jbe     short loc_140003B15
0x140003adb  mov     rax, [rcx]
0x140003ade  lea     rdx, ds:2[rdx*2]
0x140003ae6  cmp     rdx, 1000h
0x140003aed  jb      short loc_140003B0D
0x140003aef  mov     rcx, [rax-8]
0x140003af3  sub     rax, rcx
0x140003af6  sub     rax, 8
0x140003afa  cmp     rax, 1Fh
0x140003afe  ja      short loc_140003B06
0x140003b00  add     rdx, 27h ; '''
0x140003b04  jmp     short loc_140003B10
0x140003b06  mov     ecx, 5
0x140003b0b  int     29h; Win8: RtlFailFast(ecx)
0x140003b0d  mov     rcx, rax; Block
0x140003b10  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003b15  xor     eax, eax
0x140003b17  mov     qword ptr [rbx+18h], 7
0x140003b1f  mov     [rbx+10h], rax
0x140003b23  mov     [rbx], ax
0x140003b26  add     rsp, 20h
0x140003b2a  pop     rbx
0x140003b2b  retn
```
