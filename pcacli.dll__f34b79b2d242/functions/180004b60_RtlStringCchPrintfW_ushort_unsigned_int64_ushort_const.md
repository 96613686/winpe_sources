# RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180004b60`
- end: `0x180004bde`
- name: `?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `126`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004790`
- `0x1800092ac`

## callees

- `0x180004b60`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180004b94`
- `msvcrt!_vsnwprintf` at `0x180004b94`

## pseudocode

```c
__int64 RtlStringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned __int64 v4; // rbx
  unsigned int v5; // edi
  int v6; // eax
  __int64 result; // rax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( !a2 )
    return 3221225485LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 3221225485LL;
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
      return (unsigned int)-2147483643;
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
0x180004b60  mov     [rsp+arg_10], r8
0x180004b65  mov     qword ptr [rsp+Args], r9
0x180004b6a  push    rsi
0x180004b6b  push    rdi
0x180004b6c  sub     rsp, 38h
0x180004b70  mov     rsi, rcx
0x180004b73  test    rdx, rdx
0x180004b76  jz      short loc_180004BCD
0x180004b78  cmp     rdx, 7FFFFFFFh
0x180004b7f  ja      short loc_180004BC0
0x180004b81  mov     [rsp+48h+var_18], rbx
0x180004b86  lea     r9, [rsp+48h+Args]; Args
0x180004b8b  lea     rbx, [rdx-1]
0x180004b8f  xor     edi, edi
0x180004b91  mov     rdx, rbx; BufferCount
0x180004b94  call    cs:__imp__vsnwprintf
0x180004b9a  test    eax, eax
0x180004b9c  js      short loc_180004BB5
0x180004b9e  cdqe
0x180004ba0  cmp     rax, rbx
0x180004ba3  ja      short loc_180004BB5
0x180004ba5  jz      short loc_180004BC7
0x180004ba7  mov     rbx, [rsp+48h+var_18]
0x180004bac  mov     eax, edi
0x180004bae  add     rsp, 38h
0x180004bb2  pop     rdi
0x180004bb3  pop     rsi
0x180004bb4  retn
0x180004bb5  mov     [rsi+rbx*2], di
0x180004bb9  mov     edi, 80000005h
0x180004bbe  jmp     short loc_180004BA7
0x180004bc0  mov     eax, 0C000000Dh
0x180004bc5  jmp     short loc_180004BD7
0x180004bc7  mov     [rsi+rbx*2], di
0x180004bcb  jmp     short loc_180004BA7
0x180004bcd  mov     eax, 0C000000Dh
0x180004bd2  test    rdx, rdx
0x180004bd5  jz      short loc_180004BAE
0x180004bd7  xor     edi, edi
0x180004bd9  mov     [rcx], di
0x180004bdc  jmp     short loc_180004BAE
```
