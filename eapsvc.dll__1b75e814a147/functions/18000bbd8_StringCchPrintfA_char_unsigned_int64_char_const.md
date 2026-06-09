# StringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x18000bbd8`
- end: `0x18000bc51`
- name: `?StringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `121`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `26`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a380`
- `0x18000ac8c`
- `0x18000f184`
- `0x18000f2c8`
- `0x18000f57c`
- `0x18000f77c`
- `0x180010520`
- `0x18001064c`
- `0x180011698`
- `0x180011cb0`
- `0x1800122b8`
- `0x180012968`
- `0x180012b30`
- `0x180012cf8`
- `0x1800133a8`
- `0x180013578`
- `0x180013aac`
- `0x180013ba0`
- `0x1800142dc`
- `0x1800147b4`
- `0x1800148c4`
- `0x1800158ac`
- `0x180015a7b`
- `0x180015c13`
- `0x180015ce1`
- `0x180015ee1`

## callees

- `0x18000293c`
- `0x18000bbd8`

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
0x18000bbd8  mov     [rsp+arg_10], r8
0x18000bbdd  mov     qword ptr [rsp+ArgList], r9
0x18000bbe2  push    rbx
0x18000bbe3  push    rdi
0x18000bbe4  sub     rsp, 38h
0x18000bbe8  mov     rdi, rcx
0x18000bbeb  test    rdx, rdx
0x18000bbee  jz      short loc_18000BC3D
0x18000bbf0  cmp     rdx, 7FFFFFFFh
0x18000bbf7  jbe     short loc_18000BC00
0x18000bbf9  mov     eax, 80070057h
0x18000bbfe  jmp     short loc_18000BC47
0x18000bc00  lea     rbx, [rdx-1]
0x18000bc04  mov     [rsp+48h+var_28], 0
0x18000bc0d  mov     rdx, rbx; BufferCount
0x18000bc10  lea     r9, [rsp+48h+ArgList]; ArgList
0x18000bc15  call    _vsnprintf
0x18000bc1a  test    eax, eax
0x18000bc1c  js      short loc_18000BC32
0x18000bc1e  movsxd  rcx, eax
0x18000bc21  cmp     rcx, rbx
0x18000bc24  ja      short loc_18000BC32
0x18000bc26  xor     eax, eax
0x18000bc28  cmp     rcx, rbx
0x18000bc2b  jnz     short loc_18000BC4A
0x18000bc2d  mov     [rbx+rdi], al
0x18000bc30  jmp     short loc_18000BC4A
0x18000bc32  mov     byte ptr [rbx+rdi], 0
0x18000bc36  mov     eax, 8007007Ah
0x18000bc3b  jmp     short loc_18000BC4A
0x18000bc3d  mov     eax, 80070057h
0x18000bc42  test    rdx, rdx
0x18000bc45  jz      short loc_18000BC4A
0x18000bc47  mov     byte ptr [rcx], 0
0x18000bc4a  add     rsp, 38h
0x18000bc4e  pop     rdi
0x18000bc4f  pop     rbx
0x18000bc50  retn
```
