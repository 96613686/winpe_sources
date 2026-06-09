# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x180006260`
- end: `0x1800062c4`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `17`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006060`
- `0x1800062ec`
- `0x180006388`
- `0x1800065c0`
- `0x180006c04`
- `0x180007828`
- `0x180007c80`
- `0x180007f80`
- `0x1800085ec`
- `0x1800088cc`
- `0x180008ecc`
- `0x18000ad0e`
- `0x18000ad20`
- `0x18000ad62`
- `0x18000aee5`
- `0x18000af41`
- `0x18000b045`

## callees

- `0x1800018f0`
- `0x180006260`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  unsigned __int64 v4; // rdx
  char *v5; // rcx
  __int64 result; // rax

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    v4 = 2 * v1 + 2;
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
  result = 0;
  a1[3] = (char *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180006260  push    rbx
0x180006262  sub     rsp, 20h
0x180006266  mov     rdx, [rcx+18h]
0x18000626a  mov     rbx, rcx
0x18000626d  cmp     rdx, 7
0x180006271  jbe     short loc_1800062AD
0x180006273  mov     rax, [rcx]
0x180006276  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x18000627e  cmp     rdx, 1000h
0x180006285  jb      short loc_1800062A5
0x180006287  mov     rcx, [rax-8]
0x18000628b  sub     rax, rcx
0x18000628e  sub     rax, 8
0x180006292  cmp     rax, 1Fh
0x180006296  ja      short loc_18000629E
0x180006298  add     rdx, 27h ; '''
0x18000629c  jmp     short loc_1800062A8
0x18000629e  mov     ecx, 5
0x1800062a3  int     29h; Win8: RtlFailFast(ecx)
0x1800062a5  mov     rcx, rax; void *
0x1800062a8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800062ad  xor     eax, eax
0x1800062af  mov     qword ptr [rbx+18h], 7
0x1800062b7  mov     [rbx+10h], rax
0x1800062bb  mov     [rbx], ax
0x1800062be  add     rsp, 20h
0x1800062c2  pop     rbx
0x1800062c3  retn
```
