# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180009ff4`
- end: `0x18000a078`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003828`
- `0x180003bf8`
- `0x180010f58`
- `0x1800117a8`
- `0x180011fb4`
- `0x180012228`

## callees

- `0x180009ff4`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000a033`
- `msvcrt!_vsnwprintf` at `0x18000a033`

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
0x180009ff4  mov     [rsp+arg_10], r8
0x180009ff9  mov     qword ptr [rsp+Args], r9
0x180009ffe  push    rbx
0x180009fff  push    rdi
0x18000a000  sub     rsp, 38h
0x18000a004  mov     rax, rdx
0x18000a007  mov     rdi, rcx
0x18000a00a  test    rdx, rdx
0x18000a00d  jz      short loc_18000A060
0x18000a00f  cmp     rax, 7FFFFFFFh
0x18000a015  jbe     short loc_18000A01E
0x18000a017  mov     edx, 80070057h
0x18000a01c  jmp     short loc_18000A06A
0x18000a01e  lea     rbx, [rdx-1]
0x18000a022  mov     [rsp+48h+var_28], 0
0x18000a02b  mov     rdx, rbx; BufferCount
0x18000a02e  lea     r9, [rsp+48h+Args]; Args
0x18000a033  call    cs:__imp__vsnwprintf
0x18000a039  test    eax, eax
0x18000a03b  js      short loc_18000A053
0x18000a03d  cdqe
0x18000a03f  cmp     rax, rbx
0x18000a042  ja      short loc_18000A053
0x18000a044  xor     edx, edx
0x18000a046  cmp     rax, rbx
0x18000a049  jnz     short loc_18000A06F
0x18000a04b  xor     eax, eax
0x18000a04d  mov     [rdi+rbx*2], ax
0x18000a051  jmp     short loc_18000A06F
0x18000a053  xor     eax, eax
0x18000a055  mov     edx, 8007007Ah
0x18000a05a  mov     [rdi+rbx*2], ax
0x18000a05e  jmp     short loc_18000A06F
0x18000a060  mov     edx, 80070057h
0x18000a065  test    rax, rax
0x18000a068  jz      short loc_18000A06F
0x18000a06a  xor     ecx, ecx
0x18000a06c  mov     [rdi], cx
0x18000a06f  mov     eax, edx
0x18000a071  add     rsp, 38h
0x18000a075  pop     rdi
0x18000a076  pop     rbx
0x18000a077  retn
```
