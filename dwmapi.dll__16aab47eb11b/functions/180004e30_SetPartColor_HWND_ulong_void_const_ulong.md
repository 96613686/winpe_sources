# SetPartColor(HWND__ *,ulong,void const *,ulong)

- ea: `0x180004e30`
- end: `0x180004fb1`
- name: `?SetPartColor@@YAJPEAUHWND__@@KPEBXK@Z`
- size: `385`
- prototype: `__int64 __fastcall(HWND, unsigned int, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004610`

## callees

- `0x180004d20`
- `0x180004e30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f2a`
- `USER32!SetWindowCompositionAttribute` at `0x180004e8e`
- `USER32!SetWindowCompositionAttribute` at `0x180004e8e`

## pseudocode

```c
__int64 __fastcall SetPartColor(HWND a1, int a2, int *a3, int a4)
{
  unsigned int v4; // ebx
  int v5; // eax
  int v7; // edx
  signed int LastError; // eax
  int v9[2]; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v10[4]; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = 0;
  *(_QWORD *)v9 = 0;
  if ( a4 != 4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\attribute.cpp",
      (const char *)0x80070057LL,
      v9[0]);
    return 2147942487LL;
  }
  v5 = *a3;
  if ( *a3 != -1 )
  {
    if ( v5 == -2 )
    {
      if ( a2 == 36 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD1,
          (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\attribute.cpp",
          (const char *)0x80070057LL,
          v9[0]);
        return 2147942487LL;
      }
      v9[1] = 1;
    }
    else
    {
      if ( (v5 & 0xFF000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD6,
          (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\attribute.cpp",
          (const char *)0x80070057LL,
          v9[0]);
        return 2147942487LL;
      }
      v9[1] = v5 | 0xFF000000;
    }
  }
  if ( a2 == 34 )
  {
    v9[0] = 0;
  }
  else
  {
    v7 = a2 - 35;
    if ( v7 )
    {
      if ( v7 != 1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEB,
          (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\attribute.cpp",
          (const char *)0x8000FFFFLL,
          v9[0]);
        return 2147549183LL;
      }
      v9[0] = 2;
    }
    else
    {
      v9[0] = 1;
    }
  }
  v10[0] = 28;
  v10[1] = v9;
  v10[2] = 8;
  if ( !(unsigned int)SetWindowCompositionAttribute(a1, v10) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( (v4 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\attribute.cpp",
        (const char *)v4,
        v9[0]);
  }
  return v4;
}

```

## disassembly

```asm
0x180004e30  push    rbx
0x180004e32  sub     rsp, 40h
0x180004e36  xor     ebx, ebx
0x180004e38  mov     qword ptr [rsp+48h+var_28], rbx; int
0x180004e3d  cmp     r9d, 4
0x180004e41  jnz     short loc_180004EB7
0x180004e43  mov     eax, [r8]
0x180004e46  cmp     eax, 0FFFFFFFFh
0x180004e49  jz      short loc_180004E64
0x180004e4b  cmp     eax, 0FFFFFFFEh
0x180004e4e  jz      short loc_180004EA4
0x180004e50  test    eax, 0FF000000h
0x180004e55  jnz     loc_180004F03
0x180004e5b  or      eax, 0FF000000h
0x180004e60  mov     [rsp+48h+var_28+4], eax
0x180004e64  cmp     edx, 22h ; '"'
0x180004e67  jnz     short loc_180004EDE
0x180004e69  mov     [rsp+48h+var_28], ebx; int
0x180004e6d  lea     rax, [rsp+48h+var_28]
0x180004e72  mov     [rsp+48h+var_20], 1Ch
0x180004e7b  lea     rdx, [rsp+48h+var_20]
0x180004e80  mov     [rsp+48h+var_18], rax
0x180004e85  mov     [rsp+48h+var_10], 8
0x180004e8e  call    cs:__imp_SetWindowCompositionAttribute
0x180004e94  test    eax, eax
0x180004e96  jz      loc_180004F2A
0x180004e9c  mov     eax, ebx
0x180004e9e  add     rsp, 40h
0x180004ea2  pop     rbx
0x180004ea3  retn
0x180004ea4  cmp     edx, 24h ; '$'
0x180004ea7  jz      loc_180004F65
0x180004ead  mov     [rsp+48h+var_28+4], 1
0x180004eb5  jmp     short loc_180004E64
0x180004eb7  mov     rcx, [rsp+48h]; this
0x180004ebc  lea     r8, aClientcoreWind; "clientcore\\windows\\dwm\\dwmapi\\attri"...
0x180004ec3  mov     r9d, 80070057h; char *
0x180004ec9  mov     edx, 0C7h; void *
0x180004ece  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ed3  mov     eax, 80070057h
0x180004ed8  add     rsp, 40h
0x180004edc  pop     rbx
0x180004edd  retn
0x180004ede  sub     edx, 23h ; '#'
0x180004ee1  jnz     short loc_180004EED
0x180004ee3  mov     [rsp+48h+var_28], 1
0x180004eeb  jmp     short loc_180004E6D
0x180004eed  cmp     edx, 1
0x180004ef0  jnz     loc_180004F8B
0x180004ef6  mov     [rsp+48h+var_28], 2
0x180004efe  jmp     loc_180004E6D
0x180004f03  mov     rcx, [rsp+48h]; this
0x180004f08  lea     r8, aClientcoreWind; "clientcore\\windows\\dwm\\dwmapi\\attri"...
0x180004f0f  mov     r9d, 80070057h; char *
0x180004f15  mov     edx, 0D6h; void *
0x180004f1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f1f  mov     eax, 80070057h
0x180004f24  add     rsp, 40h
0x180004f28  pop     rbx
0x180004f29  retn
0x180004f2a  call    cs:__imp_GetLastError
0x180004f30  mov     ebx, eax
0x180004f32  test    eax, eax
0x180004f34  jle     short loc_180004F3F
0x180004f36  movzx   ebx, ax
0x180004f39  or      ebx, 80070000h
0x180004f3f  test    ebx, ebx
0x180004f41  jns     loc_180004E9C
0x180004f47  mov     rcx, [rsp+48h]; this
0x180004f4c  lea     r8, aClientcoreWind; "clientcore\\windows\\dwm\\dwmapi\\attri"...
0x180004f53  mov     r9d, ebx; char *
0x180004f56  mov     edx, 0F3h; void *
0x180004f5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f60  jmp     loc_180004E9C
0x180004f65  mov     rcx, [rsp+48h]; this
0x180004f6a  lea     r8, aClientcoreWind; "clientcore\\windows\\dwm\\dwmapi\\attri"...
0x180004f71  mov     r9d, 80070057h; char *
0x180004f77  mov     edx, 0D1h; void *
0x180004f7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f81  mov     eax, 80070057h
0x180004f86  jmp     loc_180004E9E
0x180004f8b  mov     rcx, [rsp+48h]; this
0x180004f90  lea     r8, aClientcoreWind; "clientcore\\windows\\dwm\\dwmapi\\attri"...
0x180004f97  mov     r9d, 8000FFFFh; char *
0x180004f9d  mov     edx, 0EBh; void *
0x180004fa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004fa7  mov     eax, 8000FFFFh
0x180004fac  jmp     loc_180004E9E
```
