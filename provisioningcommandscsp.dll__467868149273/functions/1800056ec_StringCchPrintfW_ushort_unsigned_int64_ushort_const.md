# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800056ec`
- end: `0x180005777`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `139`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031d4`
- `0x18000d181`
- `0x18000d279`
- `0x18000d3ad`
- `0x18000d418`

## callees

- `0x1800056ec`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000572b`
- `msvcrt!_vsnwprintf` at `0x18000572b`

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
0x1800056ec  mov     [rsp+arg_10], r8
0x1800056f1  mov     qword ptr [rsp+Args], r9
0x1800056f6  push    rbx
0x1800056f7  push    rdi
0x1800056f8  sub     rsp, 38h
0x1800056fc  mov     rax, rdx
0x1800056ff  mov     rdi, rcx
0x180005702  test    rdx, rdx
0x180005705  jz      short loc_18000575E
0x180005707  cmp     rax, 7FFFFFFFh
0x18000570d  jbe     short loc_180005716
0x18000570f  mov     edx, 80070057h
0x180005714  jmp     short loc_180005768
0x180005716  lea     rbx, [rdx-1]
0x18000571a  mov     [rsp+48h+var_28], 0
0x180005723  mov     rdx, rbx; BufferCount
0x180005726  lea     r9, [rsp+48h+Args]; Args
0x18000572b  call    cs:__imp__vsnwprintf
0x180005732  nop     dword ptr [rax+rax+00h]
0x180005737  test    eax, eax
0x180005739  js      short loc_180005751
0x18000573b  cdqe
0x18000573d  cmp     rax, rbx
0x180005740  ja      short loc_180005751
0x180005742  xor     edx, edx
0x180005744  cmp     rax, rbx
0x180005747  jnz     short loc_18000576D
0x180005749  xor     eax, eax
0x18000574b  mov     [rdi+rbx*2], ax
0x18000574f  jmp     short loc_18000576D
0x180005751  xor     eax, eax
0x180005753  mov     edx, 8007007Ah
0x180005758  mov     [rdi+rbx*2], ax
0x18000575c  jmp     short loc_18000576D
0x18000575e  mov     edx, 80070057h
0x180005763  test    rax, rax
0x180005766  jz      short loc_18000576D
0x180005768  xor     ecx, ecx
0x18000576a  mov     [rdi], cx
0x18000576d  mov     eax, edx
0x18000576f  add     rsp, 38h
0x180005773  pop     rdi
0x180005774  pop     rbx
0x180005775  retn
```
