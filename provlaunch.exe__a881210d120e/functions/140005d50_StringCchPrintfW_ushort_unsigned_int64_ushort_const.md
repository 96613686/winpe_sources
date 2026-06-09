# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140005d50`
- end: `0x140005dd4`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140003830`
- `0x14000a5e6`
- `0x14000a6de`
- `0x14000a812`
- `0x14000a87d`

## callees

- `0x140005d50`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140005d8f`
- `msvcrt!_vsnwprintf` at `0x140005d8f`

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
0x140005d50  mov     [rsp+arg_10], r8
0x140005d55  mov     qword ptr [rsp+Args], r9
0x140005d5a  push    rbx
0x140005d5b  push    rdi
0x140005d5c  sub     rsp, 38h
0x140005d60  mov     rax, rdx
0x140005d63  mov     rdi, rcx
0x140005d66  test    rdx, rdx
0x140005d69  jz      short loc_140005DBC
0x140005d6b  cmp     rax, 7FFFFFFFh
0x140005d71  jbe     short loc_140005D7A
0x140005d73  mov     edx, 80070057h
0x140005d78  jmp     short loc_140005DC6
0x140005d7a  lea     rbx, [rdx-1]
0x140005d7e  mov     [rsp+48h+var_28], 0
0x140005d87  mov     rdx, rbx; BufferCount
0x140005d8a  lea     r9, [rsp+48h+Args]; Args
0x140005d8f  call    cs:__imp__vsnwprintf
0x140005d95  test    eax, eax
0x140005d97  js      short loc_140005DAF
0x140005d99  cdqe
0x140005d9b  cmp     rax, rbx
0x140005d9e  ja      short loc_140005DAF
0x140005da0  xor     edx, edx
0x140005da2  cmp     rax, rbx
0x140005da5  jnz     short loc_140005DCB
0x140005da7  xor     eax, eax
0x140005da9  mov     [rdi+rbx*2], ax
0x140005dad  jmp     short loc_140005DCB
0x140005daf  xor     eax, eax
0x140005db1  mov     edx, 8007007Ah
0x140005db6  mov     [rdi+rbx*2], ax
0x140005dba  jmp     short loc_140005DCB
0x140005dbc  mov     edx, 80070057h
0x140005dc1  test    rax, rax
0x140005dc4  jz      short loc_140005DCB
0x140005dc6  xor     ecx, ecx
0x140005dc8  mov     [rdi], cx
0x140005dcb  mov     eax, edx
0x140005dcd  add     rsp, 38h
0x140005dd1  pop     rdi
0x140005dd2  pop     rbx
0x140005dd3  retn
```
