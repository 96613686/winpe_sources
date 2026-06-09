# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000ca54`
- end: `0x18000cad8`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008688`
- `0x18000c02c`
- `0x18000e578`
- `0x180013504`

## callees

- `0x18000ca54`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000ca93`
- `msvcrt!_vsnwprintf` at `0x18000ca93`

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
0x18000ca54  mov     [rsp+arg_10], r8
0x18000ca59  mov     qword ptr [rsp+Args], r9
0x18000ca5e  push    rbx
0x18000ca5f  push    rdi
0x18000ca60  sub     rsp, 38h
0x18000ca64  mov     rax, rdx
0x18000ca67  mov     rdi, rcx
0x18000ca6a  test    rdx, rdx
0x18000ca6d  jz      short loc_18000CAC0
0x18000ca6f  cmp     rax, 7FFFFFFFh
0x18000ca75  jbe     short loc_18000CA7E
0x18000ca77  mov     edx, 80070057h
0x18000ca7c  jmp     short loc_18000CACA
0x18000ca7e  lea     rbx, [rdx-1]
0x18000ca82  mov     [rsp+48h+var_28], 0
0x18000ca8b  mov     rdx, rbx; BufferCount
0x18000ca8e  lea     r9, [rsp+48h+Args]; Args
0x18000ca93  call    cs:__imp__vsnwprintf
0x18000ca99  test    eax, eax
0x18000ca9b  js      short loc_18000CAB3
0x18000ca9d  cdqe
0x18000ca9f  cmp     rax, rbx
0x18000caa2  ja      short loc_18000CAB3
0x18000caa4  xor     edx, edx
0x18000caa6  cmp     rax, rbx
0x18000caa9  jnz     short loc_18000CACF
0x18000caab  xor     eax, eax
0x18000caad  mov     [rdi+rbx*2], ax
0x18000cab1  jmp     short loc_18000CACF
0x18000cab3  xor     eax, eax
0x18000cab5  mov     edx, 8007007Ah
0x18000caba  mov     [rdi+rbx*2], ax
0x18000cabe  jmp     short loc_18000CACF
0x18000cac0  mov     edx, 80070057h
0x18000cac5  test    rax, rax
0x18000cac8  jz      short loc_18000CACF
0x18000caca  xor     ecx, ecx
0x18000cacc  mov     [rdi], cx
0x18000cacf  mov     eax, edx
0x18000cad1  add     rsp, 38h
0x18000cad5  pop     rdi
0x18000cad6  pop     rbx
0x18000cad7  retn
```
