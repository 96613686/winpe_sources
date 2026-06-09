# CreateDelayTimeString(_SYSTEMTIME *,ushort *,ulong)

- ea: `0x180012b58`
- end: `0x180012d24`
- name: `?CreateDelayTimeString@@YAJPEAU_SYSTEMTIME@@PEAGK@Z`
- size: `460`
- prototype: `__int64 __fastcall(struct _SYSTEMTIME *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180012664`
- `0x18001aa50`
- `0x18001b094`

## callees

- `0x1800022e0`
- `0x180002cbc`
- `0x180006bd4`
- `0x180006c98`
- `0x180012b58`

## pseudocode

```c
__int64 __fastcall CreateDelayTimeString(struct _SYSTEMTIME *a1, unsigned __int16 *a2)
{
  __int64 result; // rax
  const unsigned __int16 *v5; // r8
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // r8
  unsigned __int16 v9[264]; // [rsp+20h] [rbp-238h] BYREF

  v9[0] = 0;
  memset_0(&v9[1], 0, 0x206u);
  if ( !a1 || !a2 )
    return 2147942487LL;
  result = StringCchPrintfW(a2, 0x104u, L"%d-", a1->wYear, *(_QWORD *)v9);
  if ( (int)result >= 0 )
  {
    v5 = L"0%d-";
    if ( a1->wMonth >= 0xAu )
      v5 = L"%d-";
    result = StringCchPrintfW(v9, 0x104u, v5, a1->wMonth);
    if ( (int)result >= 0 )
    {
      result = StringCchCatW(a2, 0x104u, v9);
      if ( (int)result >= 0 )
      {
        v6 = L"0%dT";
        if ( a1->wDay >= 0xAu )
          v6 = L"%dT";
        result = StringCchPrintfW(v9, 0x104u, v6, a1->wDay);
        if ( (int)result >= 0 )
        {
          result = StringCchCatW(a2, 0x104u, v9);
          if ( (int)result >= 0 )
          {
            v7 = L"0%d:";
            if ( a1->wHour >= 0xAu )
              v7 = L"%d:";
            result = StringCchPrintfW(v9, 0x104u, v7, a1->wHour);
            if ( (int)result >= 0 )
            {
              result = StringCchCatW(a2, 0x104u, v9);
              if ( (int)result >= 0 )
              {
                v8 = L"0%d:00";
                if ( a1->wMinute >= 0xAu )
                  v8 = L"%d:00";
                result = StringCchPrintfW(v9, 0x104u, v8, a1->wMinute);
                if ( (int)result >= 0 )
                {
                  result = StringCchCatW(a2, 0x104u, v9);
                  if ( (int)result >= 0 )
                    return StringCchCatW(a2, 0x104u, L"Z");
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012b58  mov     [rsp+arg_10], rbx
0x180012b5d  mov     [rsp+arg_18], rbp
0x180012b62  push    rsi
0x180012b63  push    rdi
0x180012b64  push    r14
0x180012b66  sub     rsp, 240h
0x180012b6d  mov     rax, cs:__security_cookie
0x180012b74  xor     rax, rsp
0x180012b77  mov     [rsp+258h+var_28], rax
0x180012b7f  mov     rbx, rdx
0x180012b82  mov     rdi, rcx
0x180012b85  xor     eax, eax
0x180012b87  lea     rcx, [rsp+258h+var_236]; void *
0x180012b8c  xor     edx, edx; Val
0x180012b8e  mov     [rsp+258h+var_238], ax
0x180012b93  mov     r8d, 206h; Size
0x180012b99  call    memset_0
0x180012b9e  test    rdi, rdi
0x180012ba1  jz      loc_180012CF7
0x180012ba7  test    rbx, rbx
0x180012baa  jz      loc_180012CF7
0x180012bb0  movzx   r9d, word ptr [rdi]
0x180012bb4  lea     rbp, aD_0; "%d-"
0x180012bbb  mov     esi, 104h
0x180012bc0  mov     r8, rbp; unsigned __int16 *
0x180012bc3  mov     edx, esi; unsigned __int64
0x180012bc5  mov     rcx, rbx; unsigned __int16 *
0x180012bc8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012bcd  test    eax, eax
0x180012bcf  js      loc_180012CFC
0x180012bd5  movzx   eax, word ptr [rdi+2]
0x180012bd9  lea     r8, a0D_0; "0%d-"
0x180012be0  mov     r14d, 0Ah
0x180012be6  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x180012beb  cmp     r14w, ax
0x180012bef  mov     r9d, eax
0x180012bf2  mov     edx, esi; unsigned __int64
0x180012bf4  cmovbe  r8, rbp; unsigned __int16 *
0x180012bf8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012bfd  test    eax, eax
0x180012bff  js      loc_180012CFC
0x180012c05  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x180012c0a  mov     edx, esi; unsigned __int64
0x180012c0c  mov     rcx, rbx; unsigned __int16 *
0x180012c0f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012c14  test    eax, eax
0x180012c16  js      loc_180012CFC
0x180012c1c  movzx   eax, word ptr [rdi+6]
0x180012c20  lea     rcx, aDt; "%dT"
0x180012c27  cmp     r14w, ax
0x180012c2b  lea     r8, a0Dt; "0%dT"
0x180012c32  mov     r9d, eax
0x180012c35  mov     edx, esi; unsigned __int64
0x180012c37  cmovbe  r8, rcx; unsigned __int16 *
0x180012c3b  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x180012c40  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012c45  test    eax, eax
0x180012c47  js      loc_180012CFC
0x180012c4d  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x180012c52  mov     edx, esi; unsigned __int64
0x180012c54  mov     rcx, rbx; unsigned __int16 *
0x180012c57  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012c5c  test    eax, eax
0x180012c5e  js      loc_180012CFC
0x180012c64  movzx   eax, word ptr [rdi+8]
0x180012c68  lea     rcx, aD; "%d:"
0x180012c6f  cmp     r14w, ax
0x180012c73  lea     r8, a0D; "0%d:"
0x180012c7a  mov     r9d, eax
0x180012c7d  mov     edx, esi; unsigned __int64
0x180012c7f  cmovbe  r8, rcx; unsigned __int16 *
0x180012c83  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x180012c88  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012c8d  test    eax, eax
0x180012c8f  js      short loc_180012CFC
0x180012c91  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x180012c96  mov     edx, esi; unsigned __int64
0x180012c98  mov     rcx, rbx; unsigned __int16 *
0x180012c9b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012ca0  test    eax, eax
0x180012ca2  js      short loc_180012CFC
0x180012ca4  movzx   eax, word ptr [rdi+0Ah]
0x180012ca8  lea     rcx, aD00; "%d:00"
0x180012caf  cmp     r14w, ax
0x180012cb3  lea     r8, a0D00; "0%d:00"
0x180012cba  mov     r9d, eax
0x180012cbd  mov     edx, esi; unsigned __int64
0x180012cbf  cmovbe  r8, rcx; unsigned __int16 *
0x180012cc3  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x180012cc8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012ccd  test    eax, eax
0x180012ccf  js      short loc_180012CFC
0x180012cd1  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x180012cd6  mov     edx, esi; unsigned __int64
0x180012cd8  mov     rcx, rbx; unsigned __int16 *
0x180012cdb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012ce0  test    eax, eax
0x180012ce2  js      short loc_180012CFC
0x180012ce4  lea     r8, aZ; "Z"
0x180012ceb  mov     edx, esi; unsigned __int64
0x180012ced  mov     rcx, rbx; unsigned __int16 *
0x180012cf0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012cf5  jmp     short loc_180012CFC
0x180012cf7  mov     eax, 80070057h
0x180012cfc  mov     rcx, [rsp+258h+var_28]
0x180012d04  xor     rcx, rsp; StackCookie
0x180012d07  call    __security_check_cookie
0x180012d0c  lea     r11, [rsp+258h+var_18]
0x180012d14  mov     rbx, [r11+30h]
0x180012d18  mov     rbp, [r11+38h]
0x180012d1c  mov     rsp, r11
0x180012d1f  pop     r14
0x180012d21  pop     rdi
0x180012d22  pop     rsi
0x180012d23  retn
```
