# CWriterGlobalHelper::EnumToString(ulong,ushort * *,ushort *,ulong)

- ea: `0x18002c12c`
- end: `0x18002c2cb`
- name: `?EnumToString@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAGK@Z`
- size: `415`
- prototype: `__int64 __fastcall(CWriterGlobalHelper *__hidden this, unsigned int, unsigned __int16 **, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18002cdb8`

## callees

- `0x18002c12c`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!_ultow` at `0x18002c1e9`
- `msvcrt!_ultow` at `0x18002c1e9`
- `msvcrt!wcscpy_s` at `0x18002c2a4`
- `msvcrt!wcscpy_s` at `0x18002c2a4`
- `ole32!CoTaskMemAlloc` at `0x18002c217`
- `ole32!CoTaskMemAlloc` at `0x18002c285`
- `ole32!CoTaskMemAlloc` at `0x18002c217`
- `ole32!CoTaskMemAlloc` at `0x18002c285`

## pseudocode

```c
__int64 __fastcall CWriterGlobalHelper::EnumToString(
        CWriterGlobalHelper *this,
        unsigned int a2,
        unsigned __int16 **a3,
        unsigned __int16 *a4)
{
  __int64 v5; // rcx
  __int64 result; // rax
  __int64 v8; // rdx
  rsize_t v9; // rbx
  unsigned __int16 *v10; // rax
  wchar_t *v11; // r8
  __int64 v12; // rax
  unsigned int Value; // [rsp+40h] [rbp-61h] BYREF
  unsigned int v14; // [rsp+48h] [rbp-59h] BYREF
  int v15; // [rsp+50h] [rbp-51h] BYREF
  int v16; // [rsp+58h] [rbp-49h] BYREF
  wchar_t *Source; // [rsp+60h] [rbp-41h] BYREF
  _DWORD v18[4]; // [rsp+68h] [rbp-39h] BYREF
  _QWORD v19[2]; // [rsp+78h] [rbp-29h] BYREF
  __int128 v20; // [rsp+88h] [rbp-19h]
  unsigned int *p_Value; // [rsp+98h] [rbp-9h]
  __int64 v22; // [rsp+A0h] [rbp-1h]
  wchar_t Buffer[20]; // [rsp+A8h] [rbp+7h] BYREF

  Value = a2;
  v15 = 14;
  v19[0] = L"COLUMNMETA";
  v19[1] = &v15;
  p_Value = &Value;
  v14 = 0;
  v5 = *((_QWORD *)this + 1);
  v16 = 2;
  Source = 0;
  v18[0] = 0;
  v18[1] = 1;
  v18[2] = 4;
  v20 = 0;
  v22 = 0;
  result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _DWORD *, _QWORD, _QWORD *, unsigned int *))(*(_QWORD *)v5 + 56LL))(
             v5,
             0,
             3,
             v18,
             0,
             v19,
             &v14);
  if ( (_DWORD)result == -2145318890 )
  {
    _ultow(Value, Buffer, 10);
    v8 = -1;
    do
      ++v8;
    while ( Buffer[v8] );
    v9 = v8 + 1;
    v10 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v8 + 1, 2u));
    *a3 = v10;
    if ( v10 )
    {
      v11 = Buffer;
LABEL_13:
      wcscpy_s(v10, v9, v11);
      return 0;
    }
    return 2147942414LL;
  }
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, int *, _QWORD, wchar_t **))(**((_QWORD **)this + 1)
                                                                                           + 32LL))(
               *((_QWORD *)this + 1),
               v14,
               1,
               &v16,
               0,
               &Source);
    if ( (int)result >= 0 )
    {
      v12 = -1;
      do
        ++v12;
      while ( Source[v12] );
      v9 = v12 + 1;
      v10 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v12 + 1, 2u));
      *a3 = v10;
      if ( v10 )
      {
        v11 = Source;
        goto LABEL_13;
      }
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002c12c  mov     [rsp-8+arg_18], rbx
0x18002c131  push    rbp
0x18002c132  push    rsi
0x18002c133  push    rdi
0x18002c134  lea     rbp, [rsp-3Fh]
0x18002c139  sub     rsp, 0E0h
0x18002c140  mov     rax, cs:__security_cookie
0x18002c147  xor     rax, rsp
0x18002c14a  mov     [rbp+4Fh+var_20], rax
0x18002c14e  xor     esi, esi
0x18002c150  mov     [rbp+4Fh+Value], edx
0x18002c153  lea     rax, aColumnmeta; "COLUMNMETA"
0x18002c15a  mov     [rbp+4Fh+var_A0], 0Eh
0x18002c161  mov     [rbp+4Fh+var_78], rax
0x18002c165  lea     rdx, [rbp+4Fh+var_A8]
0x18002c169  mov     [rsp+0F0h+var_C0], rdx
0x18002c16e  lea     rax, [rbp+4Fh+var_A0]
0x18002c172  mov     [rbp+4Fh+var_70], rax
0x18002c176  lea     rdx, [rbp+4Fh+var_78]
0x18002c17a  mov     [rsp+0F0h+var_C8], rdx
0x18002c17f  lea     rax, [rbp+4Fh+Value]
0x18002c183  mov     [rbp+4Fh+var_58], rax
0x18002c187  lea     r9, [rbp+4Fh+var_88]
0x18002c18b  mov     rbx, rcx
0x18002c18e  mov     [rbp+4Fh+var_A8], esi
0x18002c191  mov     rcx, [rcx+8]
0x18002c195  xorps   xmm0, xmm0
0x18002c198  mov     [rbp+4Fh+var_98], 2
0x18002c19f  mov     rdi, r8
0x18002c1a2  mov     [rbp+4Fh+Source], rsi
0x18002c1a6  lea     r8d, [rsi+3]
0x18002c1aa  mov     [rbp+4Fh+var_88], esi
0x18002c1ad  xor     edx, edx
0x18002c1af  mov     [rbp+4Fh+var_84], 1
0x18002c1b6  mov     [rbp+4Fh+var_80], 4
0x18002c1bd  movdqu  [rbp+4Fh+var_68], xmm0
0x18002c1c2  mov     [rbp+4Fh+var_50], rsi
0x18002c1c6  mov     rax, [rcx]
0x18002c1c9  mov     [rsp+0F0h+var_D0], rsi
0x18002c1ce  mov     rax, [rax+38h]
0x18002c1d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1d7  cmp     eax, 80210816h
0x18002c1dc  jnz     short loc_18002C22B
0x18002c1de  mov     ecx, [rbp+4Fh+Value]; Value
0x18002c1e1  lea     r8d, [rsi+0Ah]; Radix
0x18002c1e5  lea     rdx, [rbp+4Fh+Buffer]; Buffer
0x18002c1e9  call    cs:__imp__ultow
0x18002c1ef  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002c1f3  lea     r8, [rbp+4Fh+Buffer]
0x18002c1f7  mov     rdx, rcx
0x18002c1fa  inc     rdx
0x18002c1fd  cmp     [r8+rdx*2], si
0x18002c202  jnz     short loc_18002C1FA
0x18002c204  lea     rbx, [rdx+1]
0x18002c208  mov     eax, 2
0x18002c20d  mul     rbx
0x18002c210  cmovb   rax, rcx
0x18002c214  mov     rcx, rax; cb
0x18002c217  call    cs:__imp_CoTaskMemAlloc
0x18002c21d  mov     [rdi], rax
0x18002c220  test    rax, rax
0x18002c223  jz      short loc_18002C293
0x18002c225  lea     r8, [rbp+4Fh+Buffer]
0x18002c229  jmp     short loc_18002C29E
0x18002c22b  test    eax, eax
0x18002c22d  js      short loc_18002C2AC
0x18002c22f  mov     rcx, [rbx+8]
0x18002c233  lea     rdx, [rbp+4Fh+Source]
0x18002c237  mov     [rsp+0F0h+var_C8], rdx
0x18002c23c  lea     r9, [rbp+4Fh+var_98]
0x18002c240  mov     edx, [rbp+4Fh+var_A8]
0x18002c243  mov     r8d, 1
0x18002c249  mov     [rsp+0F0h+var_D0], rsi
0x18002c24e  mov     rax, [rcx]
0x18002c251  mov     rax, [rax+20h]
0x18002c255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c25a  test    eax, eax
0x18002c25c  js      short loc_18002C2AC
0x18002c25e  mov     rdx, [rbp+4Fh+Source]
0x18002c262  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002c266  mov     rax, rcx
0x18002c269  inc     rax
0x18002c26c  cmp     [rdx+rax*2], si
0x18002c270  jnz     short loc_18002C269
0x18002c272  lea     rbx, [rax+1]
0x18002c276  mov     eax, 2
0x18002c27b  mul     rbx
0x18002c27e  cmovb   rax, rcx
0x18002c282  mov     rcx, rax; cb
0x18002c285  call    cs:__imp_CoTaskMemAlloc
0x18002c28b  mov     [rdi], rax
0x18002c28e  test    rax, rax
0x18002c291  jnz     short loc_18002C29A
0x18002c293  mov     eax, 8007000Eh
0x18002c298  jmp     short loc_18002C2AC
0x18002c29a  mov     r8, [rbp+4Fh+Source]; Source
0x18002c29e  mov     rdx, rbx; SizeInWords
0x18002c2a1  mov     rcx, rax; Destination
0x18002c2a4  call    cs:__imp_wcscpy_s
0x18002c2aa  xor     eax, eax
0x18002c2ac  mov     rcx, [rbp+4Fh+var_20]
0x18002c2b0  xor     rcx, rsp; StackCookie
0x18002c2b3  call    __security_check_cookie
0x18002c2b8  mov     rbx, [rsp+0F0h+arg_18]
0x18002c2c0  add     rsp, 0E0h
0x18002c2c7  pop     rdi
0x18002c2c8  pop     rsi
0x18002c2c9  pop     rbp
0x18002c2ca  retn
```
