# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180007b54`
- end: `0x180007bd8`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x18000312c`
- `0x1800039c8`
- `0x180004358`
- `0x180004d68`
- `0x1800055f4`
- `0x180006664`
- `0x180007170`
- `0x180007504`
- `0x180007c90`
- `0x180007e34`
- `0x180008250`
- `0x1800084d8`
- `0x1800189a0`

## callees

- `0x180007b54`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180007b93`
- `msvcrt!_vsnwprintf` at `0x180007b93`

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
0x180007b54  mov     [rsp+arg_10], r8
0x180007b59  mov     qword ptr [rsp+Args], r9
0x180007b5e  push    rbx
0x180007b5f  push    rdi
0x180007b60  sub     rsp, 38h
0x180007b64  mov     rax, rdx
0x180007b67  mov     rdi, rcx
0x180007b6a  test    rdx, rdx
0x180007b6d  jz      short loc_180007BC0
0x180007b6f  cmp     rax, 7FFFFFFFh
0x180007b75  jbe     short loc_180007B7E
0x180007b77  mov     edx, 80070057h
0x180007b7c  jmp     short loc_180007BCA
0x180007b7e  lea     rbx, [rdx-1]
0x180007b82  mov     [rsp+48h+var_28], 0
0x180007b8b  mov     rdx, rbx; BufferCount
0x180007b8e  lea     r9, [rsp+48h+Args]; Args
0x180007b93  call    cs:__imp__vsnwprintf
0x180007b99  test    eax, eax
0x180007b9b  js      short loc_180007BB3
0x180007b9d  cdqe
0x180007b9f  cmp     rax, rbx
0x180007ba2  ja      short loc_180007BB3
0x180007ba4  xor     edx, edx
0x180007ba6  cmp     rax, rbx
0x180007ba9  jnz     short loc_180007BCF
0x180007bab  xor     eax, eax
0x180007bad  mov     [rdi+rbx*2], ax
0x180007bb1  jmp     short loc_180007BCF
0x180007bb3  xor     eax, eax
0x180007bb5  mov     edx, 8007007Ah
0x180007bba  mov     [rdi+rbx*2], ax
0x180007bbe  jmp     short loc_180007BCF
0x180007bc0  mov     edx, 80070057h
0x180007bc5  test    rax, rax
0x180007bc8  jz      short loc_180007BCF
0x180007bca  xor     ecx, ecx
0x180007bcc  mov     [rdi], cx
0x180007bcf  mov     eax, edx
0x180007bd1  add     rsp, 38h
0x180007bd5  pop     rdi
0x180007bd6  pop     rbx
0x180007bd7  retn
```
