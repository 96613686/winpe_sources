# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x140002f2c`
- end: `0x140002fb7`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `139`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1400026e0`
- `0x140002790`
- `0x1400028a0`
- `0x140002950`
- `0x140002a0c`
- `0x140002ac4`
- `0x140002b74`
- `0x14000f390`
- `0x14000fbbc`

## callees

- `0x140002f2c`

## import_xrefs

- `ntoskrnl!_vsnwprintf` at `0x140002f6b`
- `ntoskrnl!_vsnwprintf` at `0x140002f6b`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
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
0x140002f2c  mov     [rsp+arg_10], r8
0x140002f31  mov     qword ptr [rsp+Args], r9
0x140002f36  push    rbx
0x140002f37  push    rdi
0x140002f38  sub     rsp, 38h
0x140002f3c  mov     rax, rdx
0x140002f3f  mov     rdi, rcx
0x140002f42  test    rdx, rdx
0x140002f45  jz      short loc_140002F9E
0x140002f47  cmp     rax, 7FFFFFFFh
0x140002f4d  jbe     short loc_140002F56
0x140002f4f  mov     edx, 80070057h
0x140002f54  jmp     short loc_140002FA8
0x140002f56  lea     rbx, [rdx-1]
0x140002f5a  mov     [rsp+48h+var_28], 0
0x140002f63  mov     rdx, rbx; Count
0x140002f66  lea     r9, [rsp+48h+Args]; Args
0x140002f6b  call    cs:__imp__vsnwprintf
0x140002f72  nop     dword ptr [rax+rax+00h]
0x140002f77  test    eax, eax
0x140002f79  js      short loc_140002F91
0x140002f7b  cdqe
0x140002f7d  cmp     rax, rbx
0x140002f80  ja      short loc_140002F91
0x140002f82  xor     edx, edx
0x140002f84  cmp     rax, rbx
0x140002f87  jnz     short loc_140002FAD
0x140002f89  xor     eax, eax
0x140002f8b  mov     [rdi+rbx*2], ax
0x140002f8f  jmp     short loc_140002FAD
0x140002f91  xor     eax, eax
0x140002f93  mov     edx, 8007007Ah
0x140002f98  mov     [rdi+rbx*2], ax
0x140002f9c  jmp     short loc_140002FAD
0x140002f9e  mov     edx, 80070057h
0x140002fa3  test    rax, rax
0x140002fa6  jz      short loc_140002FAD
0x140002fa8  xor     ecx, ecx
0x140002faa  mov     [rdi], cx
0x140002fad  mov     eax, edx
0x140002faf  add     rsp, 38h
0x140002fb3  pop     rdi
0x140002fb4  pop     rbx
0x140002fb5  retn
```
