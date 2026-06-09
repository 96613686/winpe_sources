# CRTFWrite::printF(char const *,...)

- ea: `0x18001dfe0`
- end: `0x18001e16a`
- name: `?printF@CRTFWrite@@AEAAHPEBDZZ`
- size: `394`
- prototype: `__int64(CRTFWrite *__hidden this, const char *Format, ...)`
- caller_count: `10`
- callee_count: `6`
- tags: ``

## callers

- `0x18001c5e4`
- `0x18001d14c`
- `0x18001d3c8`
- `0x18001d414`
- `0x18001d670`
- `0x18001db58`
- `0x1800453dc`
- `0x18004710c`
- `0x180048ed0`
- `0x18007f990`

## callees

- `0x18001dae4`
- `0x18001dfe0`
- `0x180049a08`
- `0x180093bbe`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x18001e023`
- `msvcrt!_vsnprintf` at `0x18001e023`

## pseudocode

```c
__int64 CRTFWrite::printF(CRTFWrite *this, const char *Format, ...)
{
  int v3; // eax
  char *v4; // rsi
  char v5; // al
  int v6; // esi
  unsigned int v7; // eax
  int v8; // ecx
  __int64 v10; // rcx
  __int64 v11; // [rsp+38h] [rbp-19h] BYREF
  char Buffer[59]; // [rsp+40h] [rbp-11h] BYREF
  char v13; // [rsp+7Bh] [rbp+2Ah] BYREF
  va_list ArgList; // [rsp+C8h] [rbp+77h] BYREF

  va_start(ArgList, Format);
  v11 = 0;
  v3 = _vsnprintf(Buffer, 0x3Bu, Format, ArgList);
  if ( v3 < 0 || (unsigned __int64)v3 > 0x3B )
  {
    v4 = Buffer;
    Buffer[0] = 0;
    v5 = 0;
LABEL_20:
    v13 = 0;
    goto LABEL_5;
  }
  if ( v3 == 59 )
  {
    v5 = Buffer[0];
    v4 = &v13;
    goto LABEL_20;
  }
  v4 = &Buffer[v3];
  v5 = Buffer[0];
LABEL_5:
  v6 = (_DWORD)v4 - (unsigned int)Buffer;
  if ( v5 == 92 || v5 == 123 || v5 == 32 )
    *((_BYTE *)this + 142) = 0;
  if ( *((_BYTE *)this + 142) )
  {
    *((_BYTE *)this + 142) = 0;
    CRTFWrite::PutChar(this, 32);
  }
  v7 = *((_DWORD *)this + 32);
  v8 = v7 + v6;
  if ( v7 + v6 < v7 || (unsigned int)v8 > 0x7FFFFFFF || v8 >= 4096 && !(unsigned int)CRTFWrite::FlushBuffer(this) )
    return 0;
  if ( v6 >= 4096 )
  {
    v10 = *((_QWORD *)this + 9);
    LODWORD(v11) = 0;
    *(_DWORD *)(*((_QWORD *)this + 9) + 8LL) = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, __int64 *))(v10 + 12))(
                                                 *(_QWORD *)v10,
                                                 Buffer,
                                                 (unsigned int)v6,
                                                 &v11);
    *((_DWORD *)this + 33) += v11;
    if ( !*(_DWORD *)(*((_QWORD *)this + 9) + 8LL) )
      return 1;
    *((_DWORD *)this + 12) = 11;
    return 0;
  }
  memmove_0(*((void **)this + 21), Buffer, v6);
  *((_QWORD *)this + 21) += v6;
  *((_DWORD *)this + 32) += v6;
  return 1;
}

```

## disassembly

```asm
0x18001dfe0  mov     rax, rsp
0x18001dfe3  mov     [rax+10h], rdx
0x18001dfe7  mov     [rax+18h], r8
0x18001dfeb  mov     [rax+20h], r9
0x18001dfef  push    rbp
0x18001dff0  push    rbx
0x18001dff1  push    rsi
0x18001dff2  push    rdi
0x18001dff3  lea     rbp, [rax-5Fh]
0x18001dff7  sub     rsp, 88h
0x18001dffe  mov     rax, cs:__security_cookie
0x18001e005  xor     rax, rsp
0x18001e008  mov     [rbp+57h+var_28], rax
0x18001e00c  xor     ebx, ebx
0x18001e00e  lea     r9, [rbp+57h+ArgList]; ArgList
0x18001e012  mov     rdi, rcx
0x18001e015  mov     [rbp+57h+var_70], rbx
0x18001e019  mov     r8, rdx; Format
0x18001e01c  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18001e020  lea     edx, [rbx+3Bh]; BufferCount
0x18001e023  call    cs:__imp__vsnprintf
0x18001e02a  nop     dword ptr [rax+rax+00h]
0x18001e02f  test    eax, eax
0x18001e031  js      loc_18001E0E8
0x18001e037  cdqe
0x18001e039  cmp     rax, 3Bh ; ';'
0x18001e03d  ja      loc_18001E0E8
0x18001e043  jz      loc_18001E0F9
0x18001e049  lea     rsi, [rbp+57h+Buffer]
0x18001e04d  add     rsi, rax
0x18001e050  mov     al, [rbp+57h+Buffer]
0x18001e053  lea     rcx, [rbp+57h+Buffer]
0x18001e057  mov     dl, 20h ; ' '; char
0x18001e059  sub     esi, ecx
0x18001e05b  cmp     al, 5Ch ; '\'
0x18001e05d  jnz     short loc_18001E0DB
0x18001e05f  mov     [rdi+8Eh], bl
0x18001e065  cmp     [rdi+8Eh], bl
0x18001e06b  jnz     loc_18001E102
0x18001e071  mov     eax, [rdi+80h]
0x18001e077  lea     ecx, [rax+rsi]
0x18001e07a  cmp     ecx, eax
0x18001e07c  jb      short loc_18001E086
0x18001e07e  cmp     ecx, 7FFFFFFFh
0x18001e084  jbe     short loc_18001E0A1
0x18001e086  mov     eax, ebx
0x18001e088  mov     rcx, [rbp+57h+var_28]
0x18001e08c  xor     rcx, rsp; StackCookie
0x18001e08f  call    __security_check_cookie
0x18001e094  add     rsp, 88h
0x18001e09b  pop     rdi
0x18001e09c  pop     rsi
0x18001e09d  pop     rbx
0x18001e09e  pop     rbp
0x18001e09f  retn
0x18001e0a1  cmp     ecx, 1000h
0x18001e0a7  jge     short loc_18001E115
0x18001e0a9  lea     rdx, [rbp+57h+Buffer]; Src
0x18001e0ad  cmp     esi, 1000h
0x18001e0b3  jge     short loc_18001E127
0x18001e0b5  mov     rcx, [rdi+0A8h]; void *
0x18001e0bc  movsxd  rbx, esi
0x18001e0bf  mov     r8, rbx; Size
0x18001e0c2  call    memmove_0
0x18001e0c7  add     [rdi+0A8h], rbx
0x18001e0ce  add     [rdi+80h], esi
0x18001e0d4  mov     eax, 1
0x18001e0d9  jmp     short loc_18001E088
0x18001e0db  cmp     al, 7Bh ; '{'
0x18001e0dd  jz      short loc_18001E05F
0x18001e0df  cmp     al, dl
0x18001e0e1  jnz     short loc_18001E065
0x18001e0e3  jmp     loc_18001E05F
0x18001e0e8  lea     rsi, [rbp+57h+Buffer]
0x18001e0ec  mov     [rbp+57h+Buffer], bl
0x18001e0ef  mov     al, bl
0x18001e0f1  mov     [rbp+57h+var_2D], bl
0x18001e0f4  jmp     loc_18001E053
0x18001e0f9  mov     al, [rbp+57h+Buffer]
0x18001e0fc  lea     rsi, [rbp+57h+var_2D]
0x18001e100  jmp     short loc_18001E0F1
0x18001e102  mov     rcx, rdi; this
0x18001e105  mov     [rdi+8Eh], bl
0x18001e10b  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x18001e110  jmp     loc_18001E071
0x18001e115  mov     rcx, rdi; this
0x18001e118  call    ?FlushBuffer@CRTFWrite@@AEAAHXZ; CRTFWrite::FlushBuffer(void)
0x18001e11d  test    eax, eax
0x18001e11f  jz      loc_18001E086
0x18001e125  jmp     short loc_18001E0A9
0x18001e127  mov     rcx, [rdi+48h]
0x18001e12b  lea     r9, [rbp+57h+var_70]
0x18001e12f  mov     dword ptr [rbp+57h+var_70], ebx
0x18001e132  mov     r8d, esi
0x18001e135  mov     rax, [rcx+0Ch]
0x18001e139  mov     rcx, [rcx]
0x18001e13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e141  mov     rcx, [rdi+48h]
0x18001e145  mov     [rcx+8], eax
0x18001e148  mov     eax, dword ptr [rbp+57h+var_70]
0x18001e14b  add     [rdi+84h], eax
0x18001e151  mov     rax, [rdi+48h]
0x18001e155  cmp     [rax+8], ebx
0x18001e158  jz      loc_18001E0D4
0x18001e15e  mov     dword ptr [rdi+30h], 0Bh
0x18001e165  jmp     loc_18001E086
```
