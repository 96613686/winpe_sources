# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180001b90`
- end: `0x180001c14`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c20`

## callees

- `0x180001b90`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180001bcf`
- `msvcrt!_vsnwprintf` at `0x180001bcf`

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
0x180001b90  mov     [rsp+arg_10], r8
0x180001b95  mov     qword ptr [rsp+Args], r9
0x180001b9a  push    rbx
0x180001b9b  push    rdi
0x180001b9c  sub     rsp, 38h
0x180001ba0  mov     rax, rdx
0x180001ba3  mov     rdi, rcx
0x180001ba6  test    rdx, rdx
0x180001ba9  jz      short loc_180001BFC
0x180001bab  cmp     rax, 7FFFFFFFh
0x180001bb1  jbe     short loc_180001BBA
0x180001bb3  mov     edx, 80070057h
0x180001bb8  jmp     short loc_180001C06
0x180001bba  lea     rbx, [rdx-1]
0x180001bbe  mov     [rsp+48h+var_28], 0
0x180001bc7  mov     rdx, rbx; BufferCount
0x180001bca  lea     r9, [rsp+48h+Args]; Args
0x180001bcf  call    cs:__imp__vsnwprintf
0x180001bd5  test    eax, eax
0x180001bd7  js      short loc_180001BEF
0x180001bd9  cdqe
0x180001bdb  cmp     rax, rbx
0x180001bde  ja      short loc_180001BEF
0x180001be0  xor     edx, edx
0x180001be2  cmp     rax, rbx
0x180001be5  jnz     short loc_180001C0B
0x180001be7  xor     eax, eax
0x180001be9  mov     [rdi+rbx*2], ax
0x180001bed  jmp     short loc_180001C0B
0x180001bef  xor     eax, eax
0x180001bf1  mov     edx, 8007007Ah
0x180001bf6  mov     [rdi+rbx*2], ax
0x180001bfa  jmp     short loc_180001C0B
0x180001bfc  mov     edx, 80070057h
0x180001c01  test    rax, rax
0x180001c04  jz      short loc_180001C0B
0x180001c06  xor     ecx, ecx
0x180001c08  mov     [rdi], cx
0x180001c0b  mov     eax, edx
0x180001c0d  add     rsp, 38h
0x180001c11  pop     rdi
0x180001c12  pop     rbx
0x180001c13  retn
```
