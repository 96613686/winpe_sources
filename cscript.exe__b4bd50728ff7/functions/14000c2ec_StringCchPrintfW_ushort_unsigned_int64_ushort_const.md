# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x14000c2ec`
- end: `0x14000c330`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `68`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b004`
- `0x14000ee7c`
- `0x14000f08c`
- `0x14000f464`
- `0x140015be8`

## callees

- `0x14000c2ec`
- `0x14000c3cc`
- `0x14000c420`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, size_t a2, const unsigned __int16 *a3, ...)
{
  size_t v3; // rdx
  wchar_t *v4; // rcx
  size_t *v5; // r8
  HRESULT v6; // r9d
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  v6 = StringValidateDestW(a1, a2, (const size_t)a3);
  if ( v6 < 0 )
  {
    if ( v3 )
      *v4 = 0;
  }
  else
  {
    return (unsigned int)StringVPrintfWorkerW(v4, v3, v5, (STRSAFE_LPCWSTR)v5, va);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000c2ec  mov     [rsp+arg_10], r8
0x14000c2f1  mov     qword ptr [rsp+arg_18], r9
0x14000c2f6  sub     rsp, 48h
0x14000c2fa  call    StringValidateDestW
0x14000c2ff  mov     r9d, eax
0x14000c302  xor     eax, eax
0x14000c304  test    r9d, r9d
0x14000c307  js      short loc_14000C320
0x14000c309  lea     rax, [rsp+48h+arg_18]
0x14000c30e  mov     r9, r8; pszFormat
0x14000c311  mov     [rsp+48h+argList], rax; argList
0x14000c316  call    StringVPrintfWorkerW
0x14000c31b  mov     r9d, eax
0x14000c31e  jmp     short loc_14000C328
0x14000c320  test    rdx, rdx
0x14000c323  jz      short loc_14000C328
0x14000c325  mov     [rcx], ax
0x14000c328  mov     eax, r9d
0x14000c32b  add     rsp, 48h
0x14000c32f  retn
```
