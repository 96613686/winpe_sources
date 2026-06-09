# TspLog

- ea: `0x180007df8`
- end: `0x180007ff0`
- name: `TspLog`
- size: `504`
- prototype: `__int64(_QWORD, const char *, ...)`
- caller_count: `70`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ca4`
- `0x180001d2c`
- `0x180001e40`
- `0x180001f48`
- `0x180001fe4`
- `0x180002080`
- `0x1800021ac`
- `0x180002494`
- `0x180002508`
- `0x180002600`
- `0x1800026b8`
- `0x18000274c`
- `0x1800029dc`
- `0x180002ad0`
- `0x180002b6c`
- `0x180002d40`
- `0x180003174`
- `0x180003294`
- `0x180003310`
- `0x18000338c`
- `0x180003488`
- `0x180003720`
- `0x1800037a8`
- `0x18000381c`
- `0x180003890`
- `0x1800039f8`
- `0x180003af0`
- `0x180003ba8`
- `0x180004184`
- `0x180004310`
- `0x180004400`
- `0x180004520`
- `0x180004670`
- `0x180004880`
- `0x1800049a0`
- `0x180004b60`
- `0x180004bc0`
- `0x180004d30`
- `0x180004ec0`
- `0x180004fe0`
- `0x1800051d0`
- `0x180005320`
- `0x180005440`
- `0x180005550`
- `0x1800058b0`
- `0x180005a10`
- `0x180005bc0`
- `0x180005d00`
- `0x180005db0`
- `0x180006140`

## callees

- `0x180001400`
- `0x180007df8`

## import_xrefs

- `rtutils!TraceVprintfExA` at `0x180007fc6`
- `rtutils!TraceVprintfExA` at `0x180007fc6`

## pseudocode

```c
int TspLog(int a1, CHAR *a2, ...)
{
  __int64 v4; // r11
  __int64 v5; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  CHAR *v8; // rcx
  __int64 v9; // rax
  const char *v10; // r9
  __int64 v11; // rax
  const char *v12; // r9
  __int64 v13; // rax
  const char *v14; // r9
  CHAR *v15; // rax
  __int64 v16; // rdx
  CHAR *v17; // rax
  CHAR *v18; // rax
  __int64 v19; // r9
  CHAR *v20; // rcx
  __int64 v21; // r8
  CHAR szFormat[256]; // [rsp+30h] [rbp-138h] BYREF
  va_list va; // [rsp+180h] [rbp+18h] BYREF

  va_start(va, a2);
  szFormat[0] = 0;
  v4 = 2147483646;
  switch ( a1 )
  {
    case 1:
      v13 = 2147483646;
      v14 = "!!! ";
      v7 = 256;
      v8 = szFormat;
      do
      {
        if ( !v13 )
          break;
        if ( !*v14 )
          break;
        *v8++ = *v14++;
        --v13;
        --v7;
      }
      while ( v7 );
      break;
    case 2:
      v11 = 2147483646;
      v12 = "!!  ";
      v7 = 256;
      v8 = szFormat;
      do
      {
        if ( !v11 )
          break;
        if ( !*v12 )
          break;
        *v8++ = *v12++;
        --v11;
        --v7;
      }
      while ( v7 );
      break;
    case 4:
      v9 = 2147483646;
      v10 = "!   ";
      v7 = 256;
      v8 = szFormat;
      do
      {
        if ( !v9 )
          break;
        if ( !*v10 )
          break;
        *v8++ = *v10++;
        --v9;
        --v7;
      }
      while ( v7 );
      break;
    case 8:
      v5 = 2147483646;
      v6 = "    ";
      v7 = 256;
      v8 = szFormat;
      do
      {
        if ( !v5 )
          break;
        if ( !*v6 )
          break;
        *v8++ = *v6++;
        --v5;
        --v7;
      }
      while ( v7 );
      break;
    default:
      goto LABEL_27;
  }
  v15 = v8 - 1;
  if ( v7 )
    v15 = v8;
  *v15 = 0;
LABEL_27:
  v16 = 256;
  v17 = szFormat;
  do
  {
    if ( !*v17 )
      break;
    ++v17;
    --v16;
  }
  while ( v16 );
  v18 = (CHAR *)-v16;
  v19 = (256 - v16) & -(__int64)(v16 != 0);
  if ( v16 )
  {
    v20 = &szFormat[v19];
    v21 = 256 - v19;
    if ( 256 != v19 )
    {
      do
      {
        if ( !v4 )
          break;
        if ( !*a2 )
          break;
        *v20++ = *a2++;
        --v4;
        --v21;
      }
      while ( v21 );
    }
    v18 = v20 - 1;
    if ( v21 )
      v18 = v20;
    *v18 = 0;
  }
  if ( gdwTraceID != -1 )
    LODWORD(v18) = TraceVprintfExA(gdwTraceID, (a1 << 16) | 6, szFormat, va);
  return (int)v18;
}

```

## disassembly

```asm
0x180007df8  mov     r11, rsp
0x180007dfb  mov     [r11+10h], rdx
0x180007dff  mov     [r11+18h], r8
0x180007e03  mov     [r11+20h], r9
0x180007e07  push    rbx
0x180007e08  push    rbp
0x180007e09  push    rdi
0x180007e0a  push    r14
0x180007e0c  sub     rsp, 148h
0x180007e13  mov     rax, cs:__security_cookie
0x180007e1a  xor     rax, rsp
0x180007e1d  mov     [rsp+168h+var_38], rax
0x180007e25  mov     eax, ecx
0x180007e27  mov     [rsp+168h+var_148], 0
0x180007e30  mov     ebp, 1
0x180007e35  mov     [rsp+168h+szFormat], 0
0x180007e3a  lea     r14, [r11+18h]
0x180007e3e  mov     rdi, rdx
0x180007e41  mov     ebx, ecx
0x180007e43  mov     r11d, 7FFFFFFEh
0x180007e49  mov     r8d, 100h
0x180007e4f  sub     eax, ebp
0x180007e51  jz      loc_180007F0A
0x180007e57  sub     eax, ebp
0x180007e59  jz      short loc_180007ED8
0x180007e5b  sub     eax, 2
0x180007e5e  jz      short loc_180007EA6
0x180007e60  cmp     eax, 4
0x180007e63  jnz     loc_180007F48
0x180007e69  mov     eax, r11d
0x180007e6c  lea     r9, asc_18000AAFC; "    "
0x180007e73  mov     edx, r8d
0x180007e76  lea     rcx, [rsp+168h+szFormat]
0x180007e7b  test    rax, rax
0x180007e7e  jz      loc_180007F3A
0x180007e84  mov     r10b, [r9]
0x180007e87  test    r10b, r10b
0x180007e8a  jz      loc_180007F3A
0x180007e90  mov     [rcx], r10b
0x180007e93  add     r9, rbp
0x180007e96  add     rcx, rbp
0x180007e99  sub     rax, rbp
0x180007e9c  sub     rdx, rbp
0x180007e9f  jnz     short loc_180007E7B
0x180007ea1  jmp     loc_180007F3A
0x180007ea6  mov     rax, r11
0x180007ea9  lea     r9, asc_18000AAF4; "!   "
0x180007eb0  mov     rdx, r8
0x180007eb3  lea     rcx, [rsp+168h+szFormat]
0x180007eb8  test    rax, rax
0x180007ebb  jz      short loc_180007F3A
0x180007ebd  mov     r10b, [r9]
0x180007ec0  test    r10b, r10b
0x180007ec3  jz      short loc_180007F3A
0x180007ec5  mov     [rcx], r10b
0x180007ec8  add     r9, rbp
0x180007ecb  add     rcx, rbp
0x180007ece  sub     rax, rbp
0x180007ed1  sub     rdx, rbp
0x180007ed4  jnz     short loc_180007EB8
0x180007ed6  jmp     short loc_180007F3A
0x180007ed8  mov     rax, r11
0x180007edb  lea     r9, asc_18000AAEC; "!!  "
0x180007ee2  mov     rdx, r8
0x180007ee5  lea     rcx, [rsp+168h+szFormat]
0x180007eea  test    rax, rax
0x180007eed  jz      short loc_180007F3A
0x180007eef  mov     r10b, [r9]
0x180007ef2  test    r10b, r10b
0x180007ef5  jz      short loc_180007F3A
0x180007ef7  mov     [rcx], r10b
0x180007efa  add     r9, rbp
0x180007efd  add     rcx, rbp
0x180007f00  sub     rax, rbp
0x180007f03  sub     rdx, rbp
0x180007f06  jnz     short loc_180007EEA
0x180007f08  jmp     short loc_180007F3A
0x180007f0a  mov     rax, r11
0x180007f0d  lea     r9, asc_18000AAE4; "!!! "
0x180007f14  mov     rdx, r8
0x180007f17  lea     rcx, [rsp+168h+szFormat]
0x180007f1c  test    rax, rax
0x180007f1f  jz      short loc_180007F3A
0x180007f21  mov     r10b, [r9]
0x180007f24  test    r10b, r10b
0x180007f27  jz      short loc_180007F3A
0x180007f29  mov     [rcx], r10b
0x180007f2c  add     r9, rbp
0x180007f2f  add     rcx, rbp
0x180007f32  sub     rax, rbp
0x180007f35  sub     rdx, rbp
0x180007f38  jnz     short loc_180007F1C
0x180007f3a  test    rdx, rdx
0x180007f3d  lea     rax, [rcx-1]
0x180007f41  cmovnz  rax, rcx
0x180007f45  mov     byte ptr [rax], 0
0x180007f48  mov     rdx, r8
0x180007f4b  lea     rax, [rsp+168h+szFormat]
0x180007f50  cmp     byte ptr [rax], 0
0x180007f53  jz      short loc_180007F5D
0x180007f55  add     rax, rbp
0x180007f58  sub     rdx, rbp
0x180007f5b  jnz     short loc_180007F50
0x180007f5d  mov     rcx, r8
0x180007f60  mov     rax, rdx
0x180007f63  sub     rcx, rdx
0x180007f66  neg     rax
0x180007f69  sbb     r9, r9
0x180007f6c  and     r9, rcx
0x180007f6f  test    rdx, rdx
0x180007f72  jz      short loc_180007FAB
0x180007f74  lea     rcx, [rsp+168h+szFormat]
0x180007f79  lea     rcx, [rcx+r9]
0x180007f7d  sub     r8, r9
0x180007f80  jz      short loc_180007F9D
0x180007f82  test    r11, r11
0x180007f85  jz      short loc_180007F9D
0x180007f87  mov     al, [rdi]
0x180007f89  test    al, al
0x180007f8b  jz      short loc_180007F9D
0x180007f8d  mov     [rcx], al
0x180007f8f  add     rdi, rbp
0x180007f92  add     rcx, rbp
0x180007f95  sub     r11, rbp
0x180007f98  sub     r8, rbp
0x180007f9b  jnz     short loc_180007F82
0x180007f9d  test    r8, r8
0x180007fa0  lea     rax, [rcx-1]
0x180007fa4  cmovnz  rax, rcx
0x180007fa8  mov     byte ptr [rax], 0
0x180007fab  mov     ecx, cs:gdwTraceID; dwTraceID
0x180007fb1  cmp     ecx, 0FFFFFFFFh
0x180007fb4  jz      short loc_180007FD2
0x180007fb6  shl     ebx, 10h
0x180007fb9  lea     r8, [rsp+168h+szFormat]; lpszFormat
0x180007fbe  or      ebx, 6
0x180007fc1  mov     r9, r14; arglist
0x180007fc4  mov     edx, ebx; dwFlags
0x180007fc6  call    cs:__imp_TraceVprintfExA
0x180007fcd  nop     dword ptr [rax+rax+00h]
0x180007fd2  mov     rcx, [rsp+168h+var_38]
0x180007fda  xor     rcx, rsp; StackCookie
0x180007fdd  call    __security_check_cookie
0x180007fe2  add     rsp, 148h
0x180007fe9  pop     r14
0x180007feb  pop     rdi
0x180007fec  pop     rbp
0x180007fed  pop     rbx
0x180007fee  retn
```
