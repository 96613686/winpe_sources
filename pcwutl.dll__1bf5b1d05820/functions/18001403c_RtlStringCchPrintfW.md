# RtlStringCchPrintfW

- ea: `0x18001403c`
- end: `0x1800140c0`
- name: `RtlStringCchPrintfW`
- size: `132`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180012fa0`
- `0x180016590`
- `0x180016880`

## callees

- `0x18001403c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18001407b`
- `msvcrt!_vsnwprintf` at `0x18001407b`

## pseudocode

```c
__int64 RtlStringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
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
        v4 = -2147483643;
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
      v4 = -1073741811;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return v4;
}

```

## disassembly

```asm
0x18001403c  mov     [rsp+arg_10], r8
0x180014041  mov     qword ptr [rsp+Args], r9
0x180014046  push    rbx
0x180014047  push    rdi
0x180014048  sub     rsp, 38h
0x18001404c  mov     rax, rdx
0x18001404f  mov     rdi, rcx
0x180014052  test    rdx, rdx
0x180014055  jz      short loc_1800140A8
0x180014057  cmp     rax, 7FFFFFFFh
0x18001405d  jbe     short loc_180014066
0x18001405f  mov     edx, 0C000000Dh
0x180014064  jmp     short loc_1800140B2
0x180014066  lea     rbx, [rdx-1]
0x18001406a  mov     [rsp+48h+var_28], 0
0x180014073  mov     rdx, rbx; BufferCount
0x180014076  lea     r9, [rsp+48h+Args]; Args
0x18001407b  call    cs:__imp__vsnwprintf
0x180014081  test    eax, eax
0x180014083  js      short loc_18001409B
0x180014085  cdqe
0x180014087  cmp     rax, rbx
0x18001408a  ja      short loc_18001409B
0x18001408c  xor     edx, edx
0x18001408e  cmp     rax, rbx
0x180014091  jnz     short loc_1800140B7
0x180014093  xor     eax, eax
0x180014095  mov     [rdi+rbx*2], ax
0x180014099  jmp     short loc_1800140B7
0x18001409b  xor     eax, eax
0x18001409d  mov     edx, 80000005h
0x1800140a2  mov     [rdi+rbx*2], ax
0x1800140a6  jmp     short loc_1800140B7
0x1800140a8  mov     edx, 0C000000Dh
0x1800140ad  test    rax, rax
0x1800140b0  jz      short loc_1800140B7
0x1800140b2  xor     ecx, ecx
0x1800140b4  mov     [rdi], cx
0x1800140b7  mov     eax, edx
0x1800140b9  add     rsp, 38h
0x1800140bd  pop     rdi
0x1800140be  pop     rbx
0x1800140bf  retn
```
