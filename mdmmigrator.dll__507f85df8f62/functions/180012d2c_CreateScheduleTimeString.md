# CreateScheduleTimeString

- ea: `0x180012d2c`
- end: `0x180012ecb`
- name: `CreateScheduleTimeString`
- size: `415`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180012664`
- `0x18001aa50`

## callees

- `0x1800022e0`
- `0x180002cbc`
- `0x180006bd4`
- `0x180006c98`
- `0x180012d2c`

## pseudocode

```c
__int64 __fastcall CreateScheduleTimeString(_WORD *a1, unsigned __int16 *a2)
{
  int v4; // edx
  unsigned __int16 v6; // [rsp+20h] [rbp-228h] BYREF
  _BYTE v7[526]; // [rsp+22h] [rbp-226h] BYREF

  v6 = 0;
  memset_0(v7, 0, 0x206u);
  if ( a1 && a2 )
  {
    v4 = StringCchPrintfW(a2, 0x104u, L"P");
    if ( v4 < 0 )
      return (unsigned int)v4;
    if ( !*a1 )
    {
      if ( a1[1] )
        a1[3] = 31;
      if ( !a1[3]
        || (v4 = StringCchPrintfW(&v6, 0x104u, L"%dD", (unsigned __int16)a1[3]), v4 >= 0)
        && (v4 = StringCchCatW(a2, 260, &v6), v4 >= 0) )
      {
        if ( a1[4] || a1[5] )
        {
          v4 = StringCchCatW(a2, 260, L"T");
          if ( v4 >= 0 )
          {
            if ( !a1[4]
              || (v4 = StringCchPrintfW(&v6, 0x104u, L"%dH", (unsigned __int16)a1[4]), v4 >= 0)
              && (v4 = StringCchCatW(a2, 260, &v6), v4 >= 0) )
            {
              if ( a1[5] )
              {
                v4 = StringCchPrintfW(&v6, 0x104u, L"%dM", (unsigned __int16)a1[5]);
                if ( v4 >= 0 )
                  return (unsigned int)StringCchCatW(a2, 260, &v6);
              }
            }
          }
        }
      }
      return (unsigned int)v4;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180012d2c  mov     [rsp+arg_10], rbx
0x180012d31  mov     [rsp+arg_18], rsi
0x180012d36  push    rdi
0x180012d37  sub     rsp, 240h
0x180012d3e  mov     rax, cs:__security_cookie
0x180012d45  xor     rax, rsp
0x180012d48  mov     [rsp+248h+var_18], rax
0x180012d50  mov     rdi, rdx
0x180012d53  mov     rbx, rcx
0x180012d56  xor     eax, eax
0x180012d58  lea     rcx, [rsp+248h+var_226]; void *
0x180012d5d  xor     edx, edx; Val
0x180012d5f  mov     [rsp+248h+var_228], ax
0x180012d64  mov     r8d, 206h; Size
0x180012d6a  call    memset_0
0x180012d6f  test    rbx, rbx
0x180012d72  jz      loc_180012EA1
0x180012d78  test    rdi, rdi
0x180012d7b  jz      loc_180012EA1
0x180012d81  mov     esi, 104h
0x180012d86  lea     r8, aP; "P"
0x180012d8d  mov     edx, esi; unsigned __int64
0x180012d8f  mov     rcx, rdi; unsigned __int16 *
0x180012d92  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012d97  mov     edx, eax
0x180012d99  test    eax, eax
0x180012d9b  js      loc_180012E9D
0x180012da1  xor     ecx, ecx
0x180012da3  cmp     cx, [rbx]
0x180012da6  jnz     loc_180012EA1
0x180012dac  cmp     cx, [rbx+2]
0x180012db0  jz      short loc_180012DB8
0x180012db2  mov     word ptr [rbx+6], 1Fh
0x180012db8  xor     eax, eax
0x180012dba  cmp     ax, [rbx+6]
0x180012dbe  jz      short loc_180012DFD
0x180012dc0  movzx   r9d, word ptr [rbx+6]
0x180012dc5  lea     r8, aDd; "%dD"
0x180012dcc  mov     rdx, rsi; unsigned __int64
0x180012dcf  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x180012dd4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012dd9  mov     edx, eax
0x180012ddb  test    eax, eax
0x180012ddd  js      loc_180012E9D
0x180012de3  lea     r8, [rsp+248h+var_228]; unsigned __int16 *
0x180012de8  mov     rdx, rsi; unsigned __int64
0x180012deb  mov     rcx, rdi; unsigned __int16 *
0x180012dee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012df3  mov     edx, eax
0x180012df5  test    eax, eax
0x180012df7  js      loc_180012E9D
0x180012dfd  xor     eax, eax
0x180012dff  cmp     ax, [rbx+8]
0x180012e03  jnz     short loc_180012E0F
0x180012e05  cmp     ax, [rbx+0Ah]
0x180012e09  jz      loc_180012E9D
0x180012e0f  lea     r8, aT; "T"
0x180012e16  mov     rdx, rsi; unsigned __int64
0x180012e19  mov     rcx, rdi; unsigned __int16 *
0x180012e1c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012e21  mov     edx, eax
0x180012e23  test    eax, eax
0x180012e25  js      short loc_180012E9D
0x180012e27  xor     eax, eax
0x180012e29  cmp     ax, [rbx+8]
0x180012e2d  jz      short loc_180012E64
0x180012e2f  movzx   r9d, word ptr [rbx+8]
0x180012e34  lea     r8, aDh; "%dH"
0x180012e3b  mov     rdx, rsi; unsigned __int64
0x180012e3e  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x180012e43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012e48  mov     edx, eax
0x180012e4a  test    eax, eax
0x180012e4c  js      short loc_180012E9D
0x180012e4e  lea     r8, [rsp+248h+var_228]; unsigned __int16 *
0x180012e53  mov     rdx, rsi; unsigned __int64
0x180012e56  mov     rcx, rdi; unsigned __int16 *
0x180012e59  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012e5e  mov     edx, eax
0x180012e60  test    eax, eax
0x180012e62  js      short loc_180012E9D
0x180012e64  xor     eax, eax
0x180012e66  cmp     ax, [rbx+0Ah]
0x180012e6a  jz      short loc_180012E9D
0x180012e6c  movzx   r9d, word ptr [rbx+0Ah]
0x180012e71  lea     r8, aDm; "%dM"
0x180012e78  mov     rdx, rsi; unsigned __int64
0x180012e7b  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x180012e80  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012e85  mov     edx, eax
0x180012e87  test    eax, eax
0x180012e89  js      short loc_180012E9D
0x180012e8b  lea     r8, [rsp+248h+var_228]; unsigned __int16 *
0x180012e90  mov     rdx, rsi; unsigned __int64
0x180012e93  mov     rcx, rdi; unsigned __int16 *
0x180012e96  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012e9b  mov     edx, eax
0x180012e9d  mov     eax, edx
0x180012e9f  jmp     short loc_180012EA6
0x180012ea1  mov     eax, 80070057h
0x180012ea6  mov     rcx, [rsp+248h+var_18]
0x180012eae  xor     rcx, rsp; StackCookie
0x180012eb1  call    __security_check_cookie
0x180012eb6  lea     r11, [rsp+248h+var_8]
0x180012ebe  mov     rbx, [r11+20h]
0x180012ec2  mov     rsi, [r11+28h]
0x180012ec6  mov     rsp, r11
0x180012ec9  pop     rdi
0x180012eca  retn
```
