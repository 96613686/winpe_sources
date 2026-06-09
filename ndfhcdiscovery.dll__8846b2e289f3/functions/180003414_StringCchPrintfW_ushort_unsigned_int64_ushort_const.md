# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180003414`
- end: `0x18000349f`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `139`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bdf4`
- `0x18000ea98`
- `0x18000ebf8`
- `0x18000f5d8`
- `0x18000f970`
- `0x18000fd18`
- `0x18000fe80`
- `0x180010684`
- `0x180011a10`

## callees

- `0x180003414`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180003453`
- `msvcrt!_vsnwprintf` at `0x180003453`

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
0x180003414  mov     [rsp+arg_10], r8
0x180003419  mov     qword ptr [rsp+Args], r9
0x18000341e  push    rbx
0x18000341f  push    rdi
0x180003420  sub     rsp, 38h
0x180003424  mov     rax, rdx
0x180003427  mov     rdi, rcx
0x18000342a  test    rdx, rdx
0x18000342d  jz      short loc_180003486
0x18000342f  cmp     rax, 7FFFFFFFh
0x180003435  jbe     short loc_18000343E
0x180003437  mov     edx, 80070057h
0x18000343c  jmp     short loc_180003490
0x18000343e  lea     rbx, [rdx-1]
0x180003442  mov     [rsp+48h+var_28], 0
0x18000344b  mov     rdx, rbx; BufferCount
0x18000344e  lea     r9, [rsp+48h+Args]; Args
0x180003453  call    cs:__imp__vsnwprintf
0x18000345a  nop     dword ptr [rax+rax+00h]
0x18000345f  test    eax, eax
0x180003461  js      short loc_180003479
0x180003463  cdqe
0x180003465  cmp     rax, rbx
0x180003468  ja      short loc_180003479
0x18000346a  xor     edx, edx
0x18000346c  cmp     rax, rbx
0x18000346f  jnz     short loc_180003495
0x180003471  xor     eax, eax
0x180003473  mov     [rdi+rbx*2], ax
0x180003477  jmp     short loc_180003495
0x180003479  xor     eax, eax
0x18000347b  mov     edx, 8007007Ah
0x180003480  mov     [rdi+rbx*2], ax
0x180003484  jmp     short loc_180003495
0x180003486  mov     edx, 80070057h
0x18000348b  test    rax, rax
0x18000348e  jz      short loc_180003495
0x180003490  xor     ecx, ecx
0x180003492  mov     [rdi], cx
0x180003495  mov     eax, edx
0x180003497  add     rsp, 38h
0x18000349b  pop     rdi
0x18000349c  pop     rbx
0x18000349d  retn
```
