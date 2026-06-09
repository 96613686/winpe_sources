# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180002b70`
- end: `0x180002bf4`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001cb4`

## callees

- `0x180002b70`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180002baf`
- `msvcrt!_vsnwprintf` at `0x180002baf`

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
0x180002b70  mov     [rsp+arg_10], r8
0x180002b75  mov     qword ptr [rsp+Args], r9
0x180002b7a  push    rbx
0x180002b7b  push    rdi
0x180002b7c  sub     rsp, 38h
0x180002b80  mov     rax, rdx
0x180002b83  mov     rdi, rcx
0x180002b86  test    rdx, rdx
0x180002b89  jz      short loc_180002BDC
0x180002b8b  cmp     rax, 7FFFFFFFh
0x180002b91  jbe     short loc_180002B9A
0x180002b93  mov     edx, 80070057h
0x180002b98  jmp     short loc_180002BE6
0x180002b9a  lea     rbx, [rdx-1]
0x180002b9e  mov     [rsp+48h+var_28], 0
0x180002ba7  mov     rdx, rbx; BufferCount
0x180002baa  lea     r9, [rsp+48h+Args]; Args
0x180002baf  call    cs:__imp__vsnwprintf
0x180002bb5  test    eax, eax
0x180002bb7  js      short loc_180002BCF
0x180002bb9  cdqe
0x180002bbb  cmp     rax, rbx
0x180002bbe  ja      short loc_180002BCF
0x180002bc0  xor     edx, edx
0x180002bc2  cmp     rax, rbx
0x180002bc5  jnz     short loc_180002BEB
0x180002bc7  xor     eax, eax
0x180002bc9  mov     [rdi+rbx*2], ax
0x180002bcd  jmp     short loc_180002BEB
0x180002bcf  xor     eax, eax
0x180002bd1  mov     edx, 8007007Ah
0x180002bd6  mov     [rdi+rbx*2], ax
0x180002bda  jmp     short loc_180002BEB
0x180002bdc  mov     edx, 80070057h
0x180002be1  test    rax, rax
0x180002be4  jz      short loc_180002BEB
0x180002be6  xor     ecx, ecx
0x180002be8  mov     [rdi], cx
0x180002beb  mov     eax, edx
0x180002bed  add     rsp, 38h
0x180002bf1  pop     rdi
0x180002bf2  pop     rbx
0x180002bf3  retn
```
