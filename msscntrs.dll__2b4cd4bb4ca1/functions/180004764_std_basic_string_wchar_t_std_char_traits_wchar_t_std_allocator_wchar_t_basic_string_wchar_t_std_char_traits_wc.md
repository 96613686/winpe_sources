# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x180004764`
- end: `0x1800047c8`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000c84c`
- `0x18000dd2c`
- `0x18001067c`
- `0x180010a34`
- `0x18001630c`
- `0x180016ee0`

## callees

- `0x180002984`
- `0x180004764`

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
0x180004764  push    rbx
0x180004766  sub     rsp, 20h
0x18000476a  mov     rdx, [rcx+18h]
0x18000476e  mov     rbx, rcx
0x180004771  cmp     rdx, 7
0x180004775  jbe     short loc_1800047B1
0x180004777  mov     rax, [rcx]
0x18000477a  lea     rdx, ds:2[rdx*2]
0x180004782  cmp     rdx, 1000h
0x180004789  jb      short loc_1800047A9
0x18000478b  mov     rcx, [rax-8]
0x18000478f  sub     rax, rcx
0x180004792  sub     rax, 8
0x180004796  cmp     rax, 1Fh
0x18000479a  ja      short loc_1800047A2
0x18000479c  add     rdx, 27h ; '''
0x1800047a0  jmp     short loc_1800047AC
0x1800047a2  mov     ecx, 5
0x1800047a7  int     29h; Win8: RtlFailFast(ecx)
0x1800047a9  mov     rcx, rax; Block
0x1800047ac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800047b1  xor     eax, eax
0x1800047b3  mov     qword ptr [rbx+18h], 7
0x1800047bb  mov     [rbx+10h], rax
0x1800047bf  mov     [rbx], ax
0x1800047c2  add     rsp, 20h
0x1800047c6  pop     rbx
0x1800047c7  retn
```
