# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800032c0`
- end: `0x18000333c`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `124`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b70`
- `0x18000641c`

## callees

- `0x1800032c0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800032f4`
- `msvcrt!_vsnwprintf` at `0x1800032f4`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned __int64 v4; // rdi
  unsigned int v5; // ebx
  int v6; // eax
  __int64 result; // rax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v4 = a2 - 1;
    v5 = 0;
    v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
    if ( v6 < 0 || v6 > v4 )
    {
      a1[v4] = 0;
      return (unsigned int)-2147024774;
    }
    else if ( v6 == v4 )
    {
      a1[v4] = 0;
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800032c0  mov     [rsp+arg_10], r8
0x1800032c5  mov     qword ptr [rsp+Args], r9
0x1800032ca  push    rbx
0x1800032cb  push    rsi
0x1800032cc  sub     rsp, 38h
0x1800032d0  mov     rsi, rcx
0x1800032d3  test    rdx, rdx
0x1800032d6  jz      short loc_18000332B
0x1800032d8  cmp     rdx, 7FFFFFFFh
0x1800032df  ja      short loc_180003324
0x1800032e1  mov     [rsp+48h+var_18], rdi
0x1800032e6  lea     r9, [rsp+48h+Args]; Args
0x1800032eb  lea     rdi, [rdx-1]
0x1800032ef  xor     ebx, ebx
0x1800032f1  mov     rdx, rdi; BufferCount
0x1800032f4  call    cs:__imp__vsnwprintf
0x1800032fa  test    eax, eax
0x1800032fc  js      short loc_180003319
0x1800032fe  cdqe
0x180003300  cmp     rax, rdi
0x180003303  ja      short loc_180003319
0x180003305  jnz     short loc_18000330B
0x180003307  mov     [rsi+rdi*2], bx
0x18000330b  mov     rdi, [rsp+48h+var_18]
0x180003310  mov     eax, ebx
0x180003312  add     rsp, 38h
0x180003316  pop     rsi
0x180003317  pop     rbx
0x180003318  retn
0x180003319  mov     [rsi+rdi*2], bx
0x18000331d  mov     ebx, 8007007Ah
0x180003322  jmp     short loc_18000330B
0x180003324  mov     eax, 80070057h
0x180003329  jmp     short loc_180003335
0x18000332b  mov     eax, 80070057h
0x180003330  test    rdx, rdx
0x180003333  jz      short loc_180003312
0x180003335  xor     ebx, ebx
0x180003337  mov     [rcx], bx
0x18000333a  jmp     short loc_180003312
```
