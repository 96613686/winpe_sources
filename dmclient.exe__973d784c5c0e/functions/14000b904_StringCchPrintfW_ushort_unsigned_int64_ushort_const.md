# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x14000b904`
- end: `0x14000b98f`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `139`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x140004ce4`
- `0x14000784c`
- `0x14000e290`
- `0x14000ee98`
- `0x1400101fc`
- `0x1400103f8`
- `0x140010638`
- `0x140010c40`
- `0x1400124a0`
- `0x140013438`
- `0x140013ebc`
- `0x140014e08`
- `0x14001505c`
- `0x1400153dc`
- `0x140015fb4`

## callees

- `0x14000b904`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x14000b943`
- `msvcrt!_vsnwprintf` at `0x14000b943`

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
0x14000b904  mov     [rsp+arg_10], r8
0x14000b909  mov     qword ptr [rsp+Args], r9
0x14000b90e  push    rbx
0x14000b90f  push    rdi
0x14000b910  sub     rsp, 38h
0x14000b914  mov     rax, rdx
0x14000b917  mov     rdi, rcx
0x14000b91a  test    rdx, rdx
0x14000b91d  jz      short loc_14000B976
0x14000b91f  cmp     rax, 7FFFFFFFh
0x14000b925  jbe     short loc_14000B92E
0x14000b927  mov     edx, 80070057h
0x14000b92c  jmp     short loc_14000B980
0x14000b92e  lea     rbx, [rdx-1]
0x14000b932  mov     [rsp+48h+var_28], 0
0x14000b93b  mov     rdx, rbx; BufferCount
0x14000b93e  lea     r9, [rsp+48h+Args]; Args
0x14000b943  call    cs:__imp__vsnwprintf
0x14000b94a  nop     dword ptr [rax+rax+00h]
0x14000b94f  test    eax, eax
0x14000b951  js      short loc_14000B969
0x14000b953  cdqe
0x14000b955  cmp     rax, rbx
0x14000b958  ja      short loc_14000B969
0x14000b95a  xor     edx, edx
0x14000b95c  cmp     rax, rbx
0x14000b95f  jnz     short loc_14000B985
0x14000b961  xor     eax, eax
0x14000b963  mov     [rdi+rbx*2], ax
0x14000b967  jmp     short loc_14000B985
0x14000b969  xor     eax, eax
0x14000b96b  mov     edx, 8007007Ah
0x14000b970  mov     [rdi+rbx*2], ax
0x14000b974  jmp     short loc_14000B985
0x14000b976  mov     edx, 80070057h
0x14000b97b  test    rax, rax
0x14000b97e  jz      short loc_14000B985
0x14000b980  xor     ecx, ecx
0x14000b982  mov     [rdi], cx
0x14000b985  mov     eax, edx
0x14000b987  add     rsp, 38h
0x14000b98b  pop     rdi
0x14000b98c  pop     rbx
0x14000b98d  retn
```
