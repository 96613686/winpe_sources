# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140008ea0`
- end: `0x140008f2b`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `139`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1400042a4`
- `0x140004680`
- `0x14000f2b8`
- `0x14000f76c`
- `0x1400107ec`
- `0x140011ac8`
- `0x140013ae0`
- `0x140015863`
- `0x140015991`
- `0x140015ac5`
- `0x140015b30`

## callees

- `0x140008ea0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140008edf`
- `msvcrt!_vsnwprintf` at `0x140008edf`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v4; // edx
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v5 = a2 - 1;
      v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
      if ( v6 < 0 || v6 > v5 )
      {
        v4 = -2147024774;
        a1[v5] = 0;
      }
      else
      {
        v4 = 0;
        if ( v6 == v5 )
          a1[v5] = 0;
      }
    }
    else
    {
      v4 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x140008ea0  mov     [rsp+arg_10], r8
0x140008ea5  mov     qword ptr [rsp+Args], r9
0x140008eaa  push    rbx
0x140008eab  push    rdi
0x140008eac  sub     rsp, 38h
0x140008eb0  mov     rax, rdx
0x140008eb3  mov     rdi, rcx
0x140008eb6  test    rdx, rdx
0x140008eb9  jz      short loc_140008F12
0x140008ebb  cmp     rax, 7FFFFFFFh
0x140008ec1  jbe     short loc_140008ECA
0x140008ec3  mov     edx, 80070057h
0x140008ec8  jmp     short loc_140008F1C
0x140008eca  lea     rbx, [rdx-1]
0x140008ece  mov     [rsp+48h+var_28], 0
0x140008ed7  mov     rdx, rbx; BufferCount
0x140008eda  lea     r9, [rsp+48h+Args]; Args
0x140008edf  call    cs:__imp__vsnwprintf
0x140008ee6  nop     dword ptr [rax+rax+00h]
0x140008eeb  test    eax, eax
0x140008eed  js      short loc_140008F05
0x140008eef  cdqe
0x140008ef1  cmp     rax, rbx
0x140008ef4  ja      short loc_140008F05
0x140008ef6  xor     edx, edx
0x140008ef8  cmp     rax, rbx
0x140008efb  jnz     short loc_140008F21
0x140008efd  xor     eax, eax
0x140008eff  mov     [rdi+rbx*2], ax
0x140008f03  jmp     short loc_140008F21
0x140008f05  xor     eax, eax
0x140008f07  mov     edx, 8007007Ah
0x140008f0c  mov     [rdi+rbx*2], ax
0x140008f10  jmp     short loc_140008F21
0x140008f12  mov     edx, 80070057h
0x140008f17  test    rax, rax
0x140008f1a  jz      short loc_140008F21
0x140008f1c  xor     ecx, ecx
0x140008f1e  mov     [rdi], cx
0x140008f21  mov     eax, edx
0x140008f23  add     rsp, 38h
0x140008f27  pop     rdi
0x140008f28  pop     rbx
0x140008f29  retn
```
