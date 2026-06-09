# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x14000ad9c`
- end: `0x14000adf9`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `93`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007adc`
- `0x140007c48`
- `0x14000cc90`
- `0x14000e324`

## callees

- `0x14000ad9c`
- `0x14000ae58`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, size_t a2, size_t *a3, ...)
{
  unsigned int v3; // edx
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringVPrintfWorkerW(a1, a2, a3, (STRSAFE_LPCWSTR)a3, va);
    }
    else
    {
      v3 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x14000ad9c  mov     [rsp+arg_10], r8
0x14000ada1  mov     qword ptr [rsp+arg_18], r9
0x14000ada6  sub     rsp, 48h
0x14000adaa  mov     rax, rdx
0x14000adad  test    rdx, rdx
0x14000adb0  jz      short loc_14000ADE3
0x14000adb2  cmp     rax, 7FFFFFFFh
0x14000adb8  jbe     short loc_14000ADC1
0x14000adba  mov     edx, 80070057h
0x14000adbf  jmp     short loc_14000ADED
0x14000adc1  lea     rdx, [rsp+48h+arg_18]
0x14000adc6  mov     [rsp+48h+var_18], 0
0x14000adcf  mov     [rsp+48h+argList], rdx; argList
0x14000add4  mov     r9, r8; pszFormat
0x14000add7  mov     rdx, rax; cchDest
0x14000adda  call    StringVPrintfWorkerW
0x14000addf  mov     edx, eax
0x14000ade1  jmp     short loc_14000ADF2
0x14000ade3  mov     edx, 80070057h
0x14000ade8  test    rax, rax
0x14000adeb  jz      short loc_14000ADF2
0x14000aded  xor     eax, eax
0x14000adef  mov     [rcx], ax
0x14000adf2  mov     eax, edx
0x14000adf4  add     rsp, 48h
0x14000adf8  retn
```
