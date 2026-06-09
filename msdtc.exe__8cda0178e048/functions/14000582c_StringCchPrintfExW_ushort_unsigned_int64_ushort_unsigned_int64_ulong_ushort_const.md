# StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)

- ea: `0x14000582c`
- end: `0x140005a43`
- name: `?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ`
- size: `535`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, unsigned __int16 **, unsigned __int64 *, unsigned int, wchar_t *Format, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005560`

## callees

- `0x1400019cf`
- `0x14000582c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1400059ae`
- `msvcrt!_vsnwprintf` at `0x1400059ae`

## pseudocode

```c
__int64 StringCchPrintfExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 **a3,
        unsigned __int64 *a4,
        unsigned int a5,
        wchar_t *Format,
        ...)
{
  const unsigned __int16 *v9; // r8
  unsigned __int16 *v10; // r15
  unsigned __int64 v11; // r14
  unsigned int v12; // edi
  unsigned __int64 v13; // rbp
  unsigned __int64 v15; // rbp
  int v16; // eax
  va_list Args; // [rsp+B0h] [rbp+38h] BYREF

  va_start(Args, Format);
  if ( (a5 & 0x100) != 0 )
  {
    if ( (a1 || !a2) && a2 <= 0x7FFFFFFF )
    {
      v9 = Format;
      v10 = a1;
      v11 = a2;
      if ( !Format )
        v9 = &qword_140009CD0;
LABEL_11:
      if ( (a5 & 0xFFFFE000) != 0 )
      {
        v12 = -2147024809;
        if ( a2 )
          *a1 = 0;
LABEL_14:
        if ( (a5 & 0x1C00) == 0 || !a2 )
          goto LABEL_25;
        v13 = (2 * a2) >> 1;
        if ( v13 && (a5 & 0x1000) != 0 )
        {
          *a1 = 0;
          v10 = a1;
          v11 = (2 * a2) >> 1;
        }
        if ( (a5 & 0x400) != 0 )
        {
          memset_0(a1, (unsigned __int8)a5, 2 * a2);
          if ( (_BYTE)a5 )
          {
            if ( !v13 )
              goto LABEL_25;
            v11 = 1;
            v10 = &a1[v13 - 1];
            *v10 = 0;
            goto LABEL_23;
          }
          v10 = a1;
          v11 = (2 * a2) >> 1;
        }
        if ( !v13 )
          goto LABEL_25;
LABEL_23:
        if ( (a5 & 0x800) != 0 )
        {
          v10 = a1;
          *a1 = 0;
          v11 = (2 * a2) >> 1;
        }
LABEL_25:
        if ( v12 != -2147024774 )
          return v12;
        goto LABEL_26;
      }
      if ( !a2 )
      {
        v12 = 0;
        if ( *v9 )
        {
          v12 = a1 != 0 ? -2147024774 : -2147024809;
          goto LABEL_14;
        }
LABEL_26:
        if ( a3 )
          *a3 = v10;
        if ( a4 )
          *a4 = v11;
        return v12;
      }
      v15 = a2 - 1;
      v16 = _vsnwprintf(a1, a2 - 1, v9, Args);
      if ( v16 < 0 || v16 > v15 )
      {
        v12 = -2147024774;
      }
      else
      {
        v12 = 0;
        if ( v16 != v15 )
        {
          v15 = v16;
LABEL_40:
          v10 = &a1[v15];
          v11 = a2 - v15;
          if ( (v12 & 0x80000000) != 0 )
            goto LABEL_14;
          if ( (a5 & 0x200) != 0 && v11 > 1 && 2 * v11 > 2 )
            memset_0(v10 + 1, (unsigned __int8)a5, 2 * v11 - 2);
          goto LABEL_26;
        }
      }
      a1[v15] = 0;
      goto LABEL_40;
    }
  }
  else if ( a2 - 1 <= 0x7FFFFFFE )
  {
    v9 = Format;
    v10 = a1;
    v11 = a2;
    goto LABEL_11;
  }
  v12 = -2147024809;
  if ( a2 )
    *a1 = 0;
  return v12;
}

```

## disassembly

```asm
0x14000582c  mov     [rsp+arg_10], r8
0x140005831  push    rbx
0x140005832  push    rbp
0x140005833  push    rsi
0x140005834  push    rdi
0x140005835  push    r12
0x140005837  push    r13
0x140005839  push    r14
0x14000583b  push    r15
0x14000583d  sub     rsp, 38h
0x140005841  mov     r12d, [rsp+78h+arg_20]
0x140005849  xor     eax, eax
0x14000584b  mov     r13, r9
0x14000584e  mov     rbx, rdx
0x140005851  mov     rsi, rcx
0x140005854  bt      r12d, 8
0x140005859  jnb     short loc_140005892
0x14000585b  test    rcx, rcx
0x14000585e  jnz     short loc_140005865
0x140005860  test    rdx, rdx
0x140005863  jnz     short loc_1400058A0
0x140005865  cmp     rbx, 7FFFFFFFh
0x14000586c  ja      short loc_1400058A0
0x14000586e  mov     r8, [rsp+78h+Format]
0x140005876  mov     r15, rsi
0x140005879  mov     r14, rbx
0x14000587c  test    r8, r8
0x14000587f  jnz     short loc_1400058C6
0x140005881  lea     r8, qword_140009CD0
0x140005888  mov     [rsp+78h+Format], r8
0x140005890  jmp     short loc_1400058C6
0x140005892  lea     rax, [rdx-1]
0x140005896  cmp     rax, 7FFFFFFEh
0x14000589c  jbe     short loc_1400058B6
0x14000589e  xor     eax, eax
0x1400058a0  mov     edi, 80070057h
0x1400058a5  test    rbx, rbx
0x1400058a8  jz      loc_140005968
0x1400058ae  mov     [rcx], ax
0x1400058b1  jmp     loc_140005968
0x1400058b6  mov     r8, [rsp+78h+Format]; Format
0x1400058be  mov     r15, rsi
0x1400058c1  mov     r14, rbx
0x1400058c4  xor     eax, eax
0x1400058c6  test    r12d, 0FFFFE000h
0x1400058cd  jz      loc_14000597B
0x1400058d3  mov     edi, 80070057h
0x1400058d8  test    rbx, rbx
0x1400058db  jz      short loc_1400058E2
0x1400058dd  mov     [rcx], ax
0x1400058e0  xor     eax, eax
0x1400058e2  test    r12d, 1C00h
0x1400058e9  jz      short loc_140005947
0x1400058eb  test    rbx, rbx
0x1400058ee  jz      short loc_140005947
0x1400058f0  lea     r8, [rbx+rbx]; Size
0x1400058f4  mov     rbp, r8
0x1400058f7  shr     rbp, 1
0x1400058fa  jz      short loc_14000590E
0x1400058fc  bt      r12d, 0Ch
0x140005901  jnb     short loc_14000590E
0x140005903  mov     [rsi], ax
0x140005906  mov     r15, rsi
0x140005909  xor     eax, eax
0x14000590b  mov     r14, rbp
0x14000590e  bt      r12d, 0Ah
0x140005913  jnb     short loc_140005932
0x140005915  movzx   edx, r12b; Val
0x140005919  mov     rcx, rsi; void *
0x14000591c  call    memset_0
0x140005921  xor     eax, eax
0x140005923  test    r12b, r12b
0x140005926  jnz     loc_140005A23
0x14000592c  mov     r15, rsi
0x14000592f  mov     r14, rbp
0x140005932  test    rbp, rbp
0x140005935  jz      short loc_140005947
0x140005937  bt      r12d, 0Bh
0x14000593c  jnb     short loc_140005947
0x14000593e  mov     r15, rsi
0x140005941  mov     [rsi], ax
0x140005944  mov     r14, rbp
0x140005947  cmp     edi, 8007007Ah
0x14000594d  jnz     short loc_140005968
0x14000594f  mov     rax, [rsp+78h+arg_10]
0x140005957  test    rax, rax
0x14000595a  jz      short loc_14000595F
0x14000595c  mov     [rax], r15
0x14000595f  test    r13, r13
0x140005962  jz      short loc_140005968
0x140005964  mov     [r13+0], r14
0x140005968  mov     eax, edi
0x14000596a  add     rsp, 38h
0x14000596e  pop     r15
0x140005970  pop     r14
0x140005972  pop     r13
0x140005974  pop     r12
0x140005976  pop     rdi
0x140005977  pop     rsi
0x140005978  pop     rbp
0x140005979  pop     rbx
0x14000597a  retn
0x14000597b  test    rbx, rbx
0x14000597e  jnz     short loc_14000599F
0x140005980  mov     edi, eax
0x140005982  cmp     [r8], ax
0x140005986  jz      short loc_14000594F
0x140005988  mov     rax, rsi
0x14000598b  mov     edi, 80070057h
0x140005990  neg     rax
0x140005993  sbb     ecx, ecx
0x140005995  and     ecx, 23h; Buffer
0x140005998  add     edi, ecx
0x14000599a  jmp     loc_1400058E0
0x14000599f  lea     rbp, [rdx-1]
0x1400059a3  mov     rdx, rbp; BufferCount
0x1400059a6  lea     r9, [rsp+78h+Args]; Args
0x1400059ae  call    cs:__imp__vsnwprintf
0x1400059b4  test    eax, eax
0x1400059b6  js      short loc_1400059CB
0x1400059b8  cdqe
0x1400059ba  cmp     rax, rbp
0x1400059bd  ja      short loc_1400059CB
0x1400059bf  xor     edi, edi
0x1400059c1  cmp     rax, rbp
0x1400059c4  jz      short loc_1400059D0
0x1400059c6  mov     rbp, rax
0x1400059c9  jmp     short loc_1400059D6
0x1400059cb  mov     edi, 8007007Ah
0x1400059d0  xor     eax, eax
0x1400059d2  mov     [rsi+rbp*2], ax
0x1400059d6  mov     r14, rbx
0x1400059d9  lea     r15, [rsi+rbp*2]
0x1400059dd  sub     r14, rbp
0x1400059e0  xor     eax, eax
0x1400059e2  test    edi, edi
0x1400059e4  js      loc_1400058E2
0x1400059ea  bt      r12d, 9
0x1400059ef  jnb     loc_14000594F
0x1400059f5  cmp     r14, 1
0x1400059f9  jbe     loc_14000594F
0x1400059ff  lea     r8, [r14+r14]
0x140005a03  cmp     r8, 2
0x140005a07  jbe     loc_14000594F
0x140005a0d  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x140005a11  movzx   edx, r12b; Val
0x140005a15  lea     rcx, [r15+2]; void *
0x140005a19  call    memset_0
0x140005a1e  jmp     loc_14000594F
0x140005a23  test    rbp, rbp
0x140005a26  jz      loc_140005947
0x140005a2c  lea     r15, [rsi-2]
0x140005a30  mov     r14d, 1
0x140005a36  lea     r15, [r15+rbp*2]
0x140005a3a  mov     [r15], ax
0x140005a3e  jmp     loc_140005937
```
