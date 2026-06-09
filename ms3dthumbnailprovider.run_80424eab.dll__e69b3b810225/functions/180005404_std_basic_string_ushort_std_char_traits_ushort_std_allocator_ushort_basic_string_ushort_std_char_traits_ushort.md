# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180005404`
- end: `0x180005468`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800060b0`
- `0x18000a529`

## callees

- `0x180001f44`
- `0x180005404`

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
0x180005404  push    rbx
0x180005406  sub     rsp, 20h
0x18000540a  mov     rdx, [rcx+18h]
0x18000540e  mov     rbx, rcx
0x180005411  cmp     rdx, 7
0x180005415  jbe     short loc_180005451
0x180005417  mov     rax, [rcx]
0x18000541a  lea     rdx, ds:2[rdx*2]
0x180005422  cmp     rdx, 1000h
0x180005429  jb      short loc_180005449
0x18000542b  mov     rcx, [rax-8]
0x18000542f  sub     rax, rcx
0x180005432  sub     rax, 8
0x180005436  cmp     rax, 1Fh
0x18000543a  ja      short loc_180005442
0x18000543c  add     rdx, 27h ; '''
0x180005440  jmp     short loc_18000544C
0x180005442  mov     ecx, 5
0x180005447  int     29h; Win8: RtlFailFast(ecx)
0x180005449  mov     rcx, rax; Block
0x18000544c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005451  xor     eax, eax
0x180005453  mov     qword ptr [rbx+18h], 7
0x18000545b  mov     [rbx+10h], rax
0x18000545f  mov     [rbx], ax
0x180005462  add     rsp, 20h
0x180005466  pop     rbx
0x180005467  retn
```
