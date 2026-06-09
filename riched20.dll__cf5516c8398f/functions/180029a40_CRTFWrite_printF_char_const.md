# CRTFWrite::printF(char const *,...)

- ea: `0x180029a40`
- end: `0x180029bc3`
- name: `?printF@CRTFWrite@@AEAAHPEBDZZ`
- size: `387`
- prototype: `__int64(CRTFWrite *__hidden this, const char *Format, ...)`
- caller_count: `10`
- callee_count: `6`
- tags: ``

## callers

- `0x180028064`
- `0x180028bc4`
- `0x180028e40`
- `0x180028e88`
- `0x1800290e0`
- `0x1800295bc`
- `0x1800442dc`
- `0x18004609c`
- `0x180047da8`
- `0x18007d5a0`

## callees

- `0x180029548`
- `0x180029a40`
- `0x180048ba0`
- `0x1800910fe`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180029a83`
- `msvcrt!_vsnprintf` at `0x180029a83`

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
0x180029a40  mov     rax, rsp
0x180029a43  mov     [rax+10h], rdx
0x180029a47  mov     [rax+18h], r8
0x180029a4b  mov     [rax+20h], r9
0x180029a4f  push    rbp
0x180029a50  push    rbx
0x180029a51  push    rsi
0x180029a52  push    rdi
0x180029a53  lea     rbp, [rax-5Fh]
0x180029a57  sub     rsp, 88h
0x180029a5e  mov     rax, cs:__security_cookie
0x180029a65  xor     rax, rsp
0x180029a68  mov     [rbp+57h+var_28], rax
0x180029a6c  xor     ebx, ebx
0x180029a6e  lea     r9, [rbp+57h+ArgList]; ArgList
0x180029a72  mov     rdi, rcx
0x180029a75  mov     [rbp+57h+var_70], rbx
0x180029a79  mov     r8, rdx; Format
0x180029a7c  lea     rcx, [rbp+57h+Buffer]; Buffer
0x180029a80  lea     edx, [rbx+3Bh]; BufferCount
0x180029a83  call    cs:__imp__vsnprintf
0x180029a89  test    eax, eax
0x180029a8b  js      loc_180029B41
0x180029a91  cdqe
0x180029a93  cmp     rax, 3Bh ; ';'
0x180029a97  ja      loc_180029B41
0x180029a9d  jz      loc_180029B52
0x180029aa3  lea     rsi, [rbp+57h+Buffer]
0x180029aa7  add     rsi, rax
0x180029aaa  mov     al, [rbp+57h+Buffer]
0x180029aad  lea     rcx, [rbp+57h+Buffer]
0x180029ab1  mov     dl, 20h ; ' '; char
0x180029ab3  sub     esi, ecx
0x180029ab5  cmp     al, 5Ch ; '\'
0x180029ab7  jnz     short loc_180029B34
0x180029ab9  mov     [rdi+8Eh], bl
0x180029abf  cmp     [rdi+8Eh], bl
0x180029ac5  jnz     loc_180029B5B
0x180029acb  mov     eax, [rdi+80h]
0x180029ad1  lea     ecx, [rax+rsi]
0x180029ad4  cmp     ecx, eax
0x180029ad6  jb      short loc_180029AE0
0x180029ad8  cmp     ecx, 7FFFFFFFh
0x180029ade  jbe     short loc_180029AFA
0x180029ae0  mov     eax, ebx
0x180029ae2  mov     rcx, [rbp+57h+var_28]
0x180029ae6  xor     rcx, rsp; StackCookie
0x180029ae9  call    __security_check_cookie
0x180029aee  add     rsp, 88h
0x180029af5  pop     rdi
0x180029af6  pop     rsi
0x180029af7  pop     rbx
0x180029af8  pop     rbp
0x180029af9  retn
0x180029afa  cmp     ecx, 1000h
0x180029b00  jge     short loc_180029B6E
0x180029b02  lea     rdx, [rbp+57h+Buffer]; Src
0x180029b06  cmp     esi, 1000h
0x180029b0c  jge     short loc_180029B80
0x180029b0e  mov     rcx, [rdi+0A8h]; void *
0x180029b15  movsxd  rbx, esi
0x180029b18  mov     r8, rbx; Size
0x180029b1b  call    memmove_0
0x180029b20  add     [rdi+0A8h], rbx
0x180029b27  add     [rdi+80h], esi
0x180029b2d  mov     eax, 1
0x180029b32  jmp     short loc_180029AE2
0x180029b34  cmp     al, 7Bh ; '{'
0x180029b36  jz      short loc_180029AB9
0x180029b38  cmp     al, dl
0x180029b3a  jnz     short loc_180029ABF
0x180029b3c  jmp     loc_180029AB9
0x180029b41  lea     rsi, [rbp+57h+Buffer]
0x180029b45  mov     [rbp+57h+Buffer], bl
0x180029b48  mov     al, bl
0x180029b4a  mov     [rbp+57h+var_2D], bl
0x180029b4d  jmp     loc_180029AAD
0x180029b52  mov     al, [rbp+57h+Buffer]
0x180029b55  lea     rsi, [rbp+57h+var_2D]
0x180029b59  jmp     short loc_180029B4A
0x180029b5b  mov     rcx, rdi; this
0x180029b5e  mov     [rdi+8Eh], bl
0x180029b64  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x180029b69  jmp     loc_180029ACB
0x180029b6e  mov     rcx, rdi; this
0x180029b71  call    ?FlushBuffer@CRTFWrite@@AEAAHXZ; CRTFWrite::FlushBuffer(void)
0x180029b76  test    eax, eax
0x180029b78  jz      loc_180029AE0
0x180029b7e  jmp     short loc_180029B02
0x180029b80  mov     rcx, [rdi+48h]
0x180029b84  lea     r9, [rbp+57h+var_70]
0x180029b88  mov     dword ptr [rbp+57h+var_70], ebx
0x180029b8b  mov     r8d, esi
0x180029b8e  mov     rax, [rcx+0Ch]
0x180029b92  mov     rcx, [rcx]
0x180029b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b9a  mov     rcx, [rdi+48h]
0x180029b9e  mov     [rcx+8], eax
0x180029ba1  mov     eax, dword ptr [rbp+57h+var_70]
0x180029ba4  add     [rdi+84h], eax
0x180029baa  mov     rax, [rdi+48h]
0x180029bae  cmp     [rax+8], ebx
0x180029bb1  jz      loc_180029B2D
0x180029bb7  mov     dword ptr [rdi+30h], 0Bh
0x180029bbe  jmp     loc_180029AE0
```
