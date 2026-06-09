# CCabStream::CopyTo(IStream *,_ULARGE_INTEGER,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x18000b1f0`
- end: `0x18000b2d3`
- name: `?CopyTo@CCabStream@@UEAAJPEAUIStream@@T_ULARGE_INTEGER@@PEAT3@2@Z`
- size: `227`
- prototype: `__int64 __fastcall(CCabStream *__hidden this, struct IStream *, union _ULARGE_INTEGER, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002620`
- `0x18000b1f0`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CCabStream::CopyTo(
        CCabStream *this,
        struct IStream *a2,
        union _ULARGE_INTEGER a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *a5)
{
  unsigned int v8; // edi
  int v9; // ecx
  DWORD LowPart; // edi
  unsigned int v11; // r14d
  int v13; // [rsp+30h] [rbp-48h] BYREF

  v13 = 0;
  if ( a4 )
    a4->QuadPart = 0;
  if ( a5 )
    a5->QuadPart = 0;
  v8 = *((_DWORD *)this + 6);
  v9 = 0;
  if ( *((_DWORD *)this + 7) < v8 )
  {
    LowPart = v8 - *((_DWORD *)this + 7);
    if ( a3.LowPart <= LowPart )
      LowPart = a3.LowPart;
    for ( ; LowPart; LowPart -= v11 )
    {
      v11 = LowPart;
      if ( LowPart > 0xF000 )
        v11 = 61440;
      v9 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, int *))(*(_QWORD *)a2 + 32LL))(
             a2,
             *((_QWORD *)this + 2) + *((unsigned int *)this + 7),
             v11,
             &v13);
      if ( v9 < 0 )
        break;
      *((_DWORD *)this + 7) += v11;
      if ( a4 )
      {
        a4->LowPart += v11;
        a4->HighPart = 0;
      }
      if ( a5 )
      {
        a5->LowPart += v13;
        a5->HighPart = 0;
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b1f0  push    rbx
0x18000b1f2  push    rbp
0x18000b1f3  push    rsi
0x18000b1f4  push    rdi
0x18000b1f5  push    r13
0x18000b1f7  push    r14
0x18000b1f9  push    r15
0x18000b1fb  sub     rsp, 40h
0x18000b1ff  mov     rax, cs:__security_cookie
0x18000b206  xor     rax, rsp
0x18000b209  mov     [rsp+78h+var_40], rax
0x18000b20e  mov     rbx, [rsp+78h+arg_20]
0x18000b216  mov     rsi, r9
0x18000b219  mov     [rsp+78h+var_48], 0
0x18000b221  mov     r15, rdx
0x18000b224  mov     rbp, rcx
0x18000b227  test    r9, r9
0x18000b22a  jz      short loc_18000B233
0x18000b22c  mov     qword ptr [r9], 0
0x18000b233  test    rbx, rbx
0x18000b236  jz      short loc_18000B23F
0x18000b238  mov     qword ptr [rbx], 0
0x18000b23f  mov     edi, [rbp+18h]
0x18000b242  xor     ecx, ecx
0x18000b244  cmp     [rbp+1Ch], edi
0x18000b247  jnb     short loc_18000B2B5
0x18000b249  sub     edi, [rbp+1Ch]
0x18000b24c  cmp     r8d, edi
0x18000b24f  cmovbe  edi, r8d
0x18000b253  test    edi, edi
0x18000b255  jz      short loc_18000B2B5
0x18000b257  mov     r13d, 0F000h
0x18000b25d  mov     rax, [r15]
0x18000b260  lea     r9, [rsp+78h+var_48]
0x18000b265  mov     edx, [rbp+1Ch]
0x18000b268  cmp     edi, r13d
0x18000b26b  mov     r14d, edi
0x18000b26e  mov     rcx, r15
0x18000b271  cmova   r14d, r13d
0x18000b275  add     rdx, [rbp+10h]
0x18000b279  mov     rax, [rax+20h]
0x18000b27d  mov     r8d, r14d
0x18000b280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b285  mov     ecx, eax
0x18000b287  test    eax, eax
0x18000b289  js      short loc_18000B2B5
0x18000b28b  add     [rbp+1Ch], r14d
0x18000b28f  test    rsi, rsi
0x18000b292  jz      short loc_18000B29E
0x18000b294  add     [rsi], r14d
0x18000b297  mov     dword ptr [rsi+4], 0
0x18000b29e  test    rbx, rbx
0x18000b2a1  jz      short loc_18000B2B0
0x18000b2a3  mov     eax, [rsp+78h+var_48]
0x18000b2a7  add     [rbx], eax
0x18000b2a9  mov     dword ptr [rbx+4], 0
0x18000b2b0  sub     edi, r14d
0x18000b2b3  jnz     short loc_18000B25D
0x18000b2b5  mov     eax, ecx
0x18000b2b7  mov     rcx, [rsp+78h+var_40]
0x18000b2bc  xor     rcx, rsp; StackCookie
0x18000b2bf  call    __security_check_cookie
0x18000b2c4  add     rsp, 40h
0x18000b2c8  pop     r15
0x18000b2ca  pop     r14
0x18000b2cc  pop     r13
0x18000b2ce  pop     rdi
0x18000b2cf  pop     rsi
0x18000b2d0  pop     rbp
0x18000b2d1  pop     rbx
0x18000b2d2  retn
```
