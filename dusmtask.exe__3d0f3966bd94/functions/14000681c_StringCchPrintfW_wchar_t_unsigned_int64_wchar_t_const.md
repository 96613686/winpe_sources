# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x14000681c`
- end: `0x1400068bb`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `159`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140003d68`
- `0x14000799e`
- `0x140007a96`
- `0x140007bca`
- `0x140007c35`

## callees

- `0x140001470`
- `0x140001f28`
- `0x14000681c`

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
      v6 = vsnwprintf(a1, a2 - 1, a3, Args);
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
0x14000681c  mov     [rsp+arg_10], r8
0x140006821  mov     qword ptr [rsp+Args], r9
0x140006826  push    rbx
0x140006827  push    rdi
0x140006828  sub     rsp, 38h
0x14000682c  mov     rax, cs:__security_cookie
0x140006833  xor     rax, rsp
0x140006836  mov     [rsp+48h+var_20], rax
0x14000683b  mov     rax, rdx
0x14000683e  mov     rdi, rcx
0x140006841  test    rdx, rdx
0x140006844  jz      short loc_140006896
0x140006846  cmp     rax, 7FFFFFFFh
0x14000684c  jbe     short loc_140006855
0x14000684e  mov     edx, 80070057h
0x140006853  jmp     short loc_1400068A0
0x140006855  lea     rbx, [rdx-1]
0x140006859  mov     [rsp+48h+var_28], 0
0x140006862  mov     rdx, rbx; BufferCount
0x140006865  lea     r9, [rsp+48h+Args]; Args
0x14000686a  call    _vsnwprintf
0x14000686f  test    eax, eax
0x140006871  js      short loc_140006889
0x140006873  cdqe
0x140006875  cmp     rax, rbx
0x140006878  ja      short loc_140006889
0x14000687a  xor     edx, edx
0x14000687c  cmp     rax, rbx
0x14000687f  jnz     short loc_1400068A5
0x140006881  xor     eax, eax
0x140006883  mov     [rdi+rbx*2], ax
0x140006887  jmp     short loc_1400068A5
0x140006889  xor     eax, eax
0x14000688b  mov     edx, 8007007Ah
0x140006890  mov     [rdi+rbx*2], ax
0x140006894  jmp     short loc_1400068A5
0x140006896  mov     edx, 80070057h
0x14000689b  test    rax, rax
0x14000689e  jz      short loc_1400068A5
0x1400068a0  xor     ecx, ecx
0x1400068a2  mov     [rdi], cx
0x1400068a5  mov     eax, edx
0x1400068a7  mov     rcx, [rsp+48h+var_20]
0x1400068ac  xor     rcx, rsp; StackCookie
0x1400068af  call    __security_check_cookie
0x1400068b4  add     rsp, 38h
0x1400068b8  pop     rdi
0x1400068b9  pop     rbx
0x1400068ba  retn
```
