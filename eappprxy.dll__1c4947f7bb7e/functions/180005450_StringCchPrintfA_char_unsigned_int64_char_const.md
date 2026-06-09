# StringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x180005450`
- end: `0x1800054ca`
- name: `?StringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `122`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x180006100`
- `0x1800069e0`
- `0x180006d20`
- `0x180007090`
- `0x180007330`
- `0x1800075c0`
- `0x180007a80`
- `0x180007d40`
- `0x1800080c0`
- `0x180008850`
- `0x180008cf0`
- `0x180009230`
- `0x1800096e0`
- `0x180009b90`
- `0x180009e10`
- `0x18000a1b0`
- `0x18000a550`
- `0x18000a8f0`

## callees

- `0x18000223c`
- `0x180005450`

## pseudocode

```c
__int64 StringCchPrintfA(char *a1, unsigned __int64 a2, const char *a3, ...)
{
  __int64 result; // rax
  unsigned __int64 v5; // rbx
  int v6; // eax
  __int64 v7; // rcx
  va_list ArgList; // [rsp+68h] [rbp+20h] BYREF

  va_start(ArgList, a3);
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = a2 - 1;
    v6 = vsnprintf(a1, a2 - 1, a3, ArgList);
    if ( v6 < 0 || (v7 = v6, v6 > v5) )
    {
      a1[v5] = 0;
      return 2147942522LL;
    }
    else
    {
      result = 0;
      if ( v7 == v5 )
        a1[v5] = 0;
    }
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005450  mov     [rsp+arg_10], r8
0x180005455  mov     qword ptr [rsp+ArgList], r9
0x18000545a  push    rbx
0x18000545b  push    rdi
0x18000545c  sub     rsp, 38h
0x180005460  mov     rdi, rcx
0x180005463  test    rdx, rdx
0x180005466  jz      short loc_1800054B5
0x180005468  cmp     rdx, 7FFFFFFFh
0x18000546f  jbe     short loc_180005478
0x180005471  mov     eax, 80070057h
0x180005476  jmp     short loc_1800054BF
0x180005478  lea     rbx, [rdx-1]
0x18000547c  mov     [rsp+48h+var_28], 0
0x180005485  mov     rdx, rbx; BufferCount
0x180005488  lea     r9, [rsp+48h+ArgList]; ArgList
0x18000548d  call    _vsnprintf
0x180005492  test    eax, eax
0x180005494  js      short loc_1800054AA
0x180005496  movsxd  rcx, eax
0x180005499  cmp     rcx, rbx
0x18000549c  ja      short loc_1800054AA
0x18000549e  xor     eax, eax
0x1800054a0  cmp     rcx, rbx
0x1800054a3  jnz     short loc_1800054C2
0x1800054a5  mov     [rbx+rdi], al
0x1800054a8  jmp     short loc_1800054C2
0x1800054aa  mov     byte ptr [rbx+rdi], 0
0x1800054ae  mov     eax, 8007007Ah
0x1800054b3  jmp     short loc_1800054C2
0x1800054b5  mov     eax, 80070057h
0x1800054ba  test    rdx, rdx
0x1800054bd  jz      short loc_1800054C2
0x1800054bf  mov     byte ptr [rcx], 0
0x1800054c2  add     rsp, 38h
0x1800054c6  pop     rdi
0x1800054c7  pop     rbx
0x1800054c8  retn
```
