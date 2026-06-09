# NativeMsh::PwrshCommon::FormatStringWithErrorReporting(ushort const *,ushort * *,ulong *,int,...)

- ea: `0x1800079f4`
- end: `0x180007c23`
- name: `?FormatStringWithErrorReporting@PwrshCommon@NativeMsh@@IEAA_NPEBGPEAPEAGPEAKHZZ`
- size: `559`
- prototype: `char(NativeMsh::PwrshCommon *this, const unsigned __int16 *, unsigned __int16 **, unsigned int *, unsigned int, ...)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800086b8`
- `0x180008890`

## callees

- `0x180001318`
- `0x1800079f4`
- `0x18000b010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180007b2c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007b65`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007bc4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007b2c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007b65`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007bc4`
- `KERNEL32!FormatMessageW` at `0x180007a5d`
- `KERNEL32!FormatMessageW` at `0x180007a98`
- `KERNEL32!FormatMessageW` at `0x180007a5d`
- `KERNEL32!FormatMessageW` at `0x180007a98`
- `KERNEL32!LocalFree` at `0x180007b39`
- `KERNEL32!LocalFree` at `0x180007bd4`
- `KERNEL32!LocalFree` at `0x180007b39`
- `KERNEL32!LocalFree` at `0x180007bd4`
- `KERNEL32!GetLastError` at `0x180007a72`
- `KERNEL32!GetLastError` at `0x180007a72`

## pseudocode

```c
char NativeMsh::PwrshCommon::FormatStringWithErrorReporting(
        NativeMsh::PwrshCommon *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned int *a4,
        unsigned int a5,
        ...)
{
  DWORD v8; // eax
  unsigned int v9; // r15d
  DWORD LastError; // eax
  DWORD v11; // eax
  DWORD v12; // r14d
  unsigned __int64 v13; // rsi
  _WORD *v14; // rax
  _WORD *v15; // rdi
  _WORD *v16; // rcx
  __int64 v17; // rax
  _WORD *v18; // rdx
  _WORD *v19; // rcx
  char v20; // bl
  unsigned __int64 v22; // rdi
  unsigned __int16 *v23; // rax
  unsigned __int16 *v24; // rdx
  unsigned __int16 *v25; // rcx
  __int64 v26; // rax
  unsigned __int16 *v27; // rcx
  WCHAR lpBuffer[4]; // [rsp+40h] [rbp-28h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp-20h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-18h] BYREF
  va_list va; // [rsp+D8h] [rbp+70h] BYREF

  va_start(va, a5);
  *(_QWORD *)Buffer = 0;
  va_copy(Arguments, va);
  if ( !a2 || !a3 || !a4 )
    return 0;
  v8 = FormatMessageW(0x500u, a2, 0, 0, Buffer, 0, &Arguments);
  v9 = v8;
  if ( v8 )
  {
    v22 = v8 + 1;
    v23 = (unsigned __int16 *)operator new[](saturated_mul(v22, 2u));
    *a3 = v23;
    v24 = v23;
    if ( v23 )
    {
      if ( v22 )
      {
        if ( v22 <= 0x7FFFFFFF )
        {
          v25 = *(unsigned __int16 **)Buffer;
          v26 = 2147483646;
          v20 = 1;
          do
          {
            if ( !v26 )
              break;
            if ( !*v25 )
              break;
            *v24++ = *v25++;
            --v26;
            --v22;
          }
          while ( v22 );
          v27 = v24 - 1;
          if ( v22 )
            v27 = v24;
          *v27 = 0;
          if ( v22 )
          {
            *a4 = v9;
            goto LABEL_30;
          }
        }
        else
        {
          *v23 = 0;
        }
      }
      if ( *a3 )
      {
        operator delete[](*a3);
        *a3 = 0;
      }
    }
    v20 = 0;
LABEL_30:
    LocalFree(*(HLOCAL *)Buffer);
    return v20;
  }
  *(_QWORD *)lpBuffer = 0;
  LastError = GetLastError();
  v11 = FormatMessageW(0x1100u, 0, LastError, 0, lpBuffer, 0, 0);
  v12 = v11;
  if ( v11 )
  {
    v13 = v11 + 1;
    v14 = operator new[](saturated_mul(v13, 2u));
    v15 = v14;
    if ( v14 )
    {
      if ( v13 )
      {
        if ( v13 <= 0x7FFFFFFF )
        {
          v16 = *(_WORD **)lpBuffer;
          v17 = 2147483646;
          v18 = v15;
          do
          {
            if ( !v17 )
              break;
            if ( !*v16 )
              break;
            *v18++ = *v16++;
            --v17;
            --v13;
          }
          while ( v13 );
          v19 = v18 - 1;
          if ( v13 )
            v19 = v18;
          *v19 = 0;
          if ( v13 )
            goto LABEL_18;
        }
        else
        {
          *v14 = 0;
        }
      }
      v12 = 0;
      operator delete[](v15);
      v15 = 0;
    }
LABEL_18:
    LocalFree(*(HLOCAL *)lpBuffer);
    if ( v12 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _WORD *))(**((_QWORD **)this + 1) + 8LL))(
        *((_QWORD *)this + 1),
        0,
        a5,
        v15);
      if ( v15 )
        operator delete[](v15);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800079f4  push    rbp
0x1800079f6  push    rbx
0x1800079f7  push    rsi
0x1800079f8  push    rdi
0x1800079f9  push    r12
0x1800079fb  push    r13
0x1800079fd  push    r14
0x1800079ff  push    r15
0x180007a01  mov     rbp, rsp
0x180007a04  sub     rsp, 68h
0x180007a08  xor     r12d, r12d
0x180007a0b  lea     rax, [rbp+arg_28]
0x180007a0f  mov     qword ptr [rbp+Buffer], r12
0x180007a13  mov     r14, r9
0x180007a16  mov     [rbp+var_18], rax
0x180007a1a  mov     rsi, r8
0x180007a1d  mov     r13, rcx
0x180007a20  test    rdx, rdx
0x180007a23  jz      loc_180007B6B
0x180007a29  test    r8, r8
0x180007a2c  jz      loc_180007B6B
0x180007a32  test    r9, r9
0x180007a35  jz      loc_180007B6B
0x180007a3b  lea     rax, [rbp+var_18]
0x180007a3f  xor     r9d, r9d; dwLanguageId
0x180007a42  mov     [rsp+68h+Arguments], rax; Arguments
0x180007a47  xor     r8d, r8d; dwMessageId
0x180007a4a  lea     rax, [rbp+Buffer]
0x180007a4e  mov     [rsp+68h+nSize], r12d; nSize
0x180007a53  mov     ecx, 500h; dwFlags
0x180007a58  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x180007a5d  call    cs:__imp_FormatMessageW
0x180007a63  mov     r15d, eax
0x180007a66  test    eax, eax
0x180007a68  jnz     loc_180007B81
0x180007a6e  mov     qword ptr [rbp+var_28], r12
0x180007a72  call    cs:__imp_GetLastError
0x180007a78  mov     [rsp+68h+Arguments], r12; Arguments
0x180007a7d  xor     r9d, r9d; dwLanguageId
0x180007a80  mov     r8d, eax; dwMessageId
0x180007a83  mov     [rsp+68h+nSize], r12d; nSize
0x180007a88  lea     rax, [rbp+var_28]
0x180007a8c  xor     edx, edx; lpSource
0x180007a8e  mov     ecx, 1100h; dwFlags
0x180007a93  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x180007a98  call    cs:__imp_FormatMessageW
0x180007a9e  mov     r14d, eax
0x180007aa1  test    eax, eax
0x180007aa3  jz      loc_180007B6B
0x180007aa9  lea     esi, [rax+1]
0x180007aac  lea     rcx, [r12-1]
0x180007ab1  lea     eax, [r12+2]
0x180007ab6  mul     rsi
0x180007ab9  cmovb   rax, rcx
0x180007abd  mov     rcx, rax; unsigned __int64
0x180007ac0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007ac5  mov     rdi, rax
0x180007ac8  test    rax, rax
0x180007acb  jz      short loc_180007B35
0x180007acd  test    rsi, rsi
0x180007ad0  jz      short loc_180007B26
0x180007ad2  cmp     rsi, 7FFFFFFFh
0x180007ad9  jbe     short loc_180007AE1
0x180007adb  mov     [rax], r12w
0x180007adf  jmp     short loc_180007B26
0x180007ae1  mov     rcx, qword ptr [rbp+var_28]
0x180007ae5  mov     eax, 7FFFFFFEh
0x180007aea  mov     rdx, rdi
0x180007aed  mov     ebx, 1
0x180007af2  test    rax, rax
0x180007af5  jz      short loc_180007B15
0x180007af7  movzx   r8d, word ptr [rcx]
0x180007afb  test    r8w, r8w
0x180007aff  jz      short loc_180007B15
0x180007b01  mov     [rdx], r8w
0x180007b05  add     rcx, 2
0x180007b09  add     rdx, 2
0x180007b0d  sub     rax, rbx
0x180007b10  sub     rsi, rbx
0x180007b13  jnz     short loc_180007AF2
0x180007b15  test    rsi, rsi
0x180007b18  lea     rcx, [rdx-2]
0x180007b1c  cmovnz  rcx, rdx
0x180007b20  mov     [rcx], r12w
0x180007b24  jnz     short loc_180007B35
0x180007b26  mov     rcx, rdi
0x180007b29  mov     r14d, r12d
0x180007b2c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007b32  mov     rdi, r12
0x180007b35  mov     rcx, qword ptr [rbp+var_28]; hMem
0x180007b39  call    cs:__imp_LocalFree
0x180007b3f  test    r14d, r14d
0x180007b42  jz      short loc_180007B6B
0x180007b44  mov     rcx, [r13+8]
0x180007b48  mov     r9, rdi
0x180007b4b  mov     r8d, [rbp+arg_20]
0x180007b4f  xor     edx, edx
0x180007b51  mov     rax, [rcx]
0x180007b54  mov     rax, [rax+8]
0x180007b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b5d  test    rdi, rdi
0x180007b60  jz      short loc_180007B6B
0x180007b62  mov     rcx, rdi
0x180007b65  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007b6b  mov     bl, r12b
0x180007b6e  mov     al, bl
0x180007b70  add     rsp, 68h
0x180007b74  pop     r15
0x180007b76  pop     r14
0x180007b78  pop     r13
0x180007b7a  pop     r12
0x180007b7c  pop     rdi
0x180007b7d  pop     rsi
0x180007b7e  pop     rbx
0x180007b7f  pop     rbp
0x180007b80  retn
0x180007b81  lea     edi, [rax+1]
0x180007b84  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007b8b  mov     eax, 2
0x180007b90  mul     rdi
0x180007b93  cmovb   rax, rcx
0x180007b97  mov     rcx, rax; unsigned __int64
0x180007b9a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007b9f  mov     [rsi], rax
0x180007ba2  mov     rdx, rax
0x180007ba5  test    rax, rax
0x180007ba8  jz      short loc_180007BCD
0x180007baa  test    rdi, rdi
0x180007bad  jz      short loc_180007BBC
0x180007baf  cmp     rdi, 7FFFFFFFh
0x180007bb6  jbe     short loc_180007BDC
0x180007bb8  mov     [rax], r12w
0x180007bbc  mov     rcx, [rsi]
0x180007bbf  test    rcx, rcx
0x180007bc2  jz      short loc_180007BCD
0x180007bc4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007bca  mov     [rsi], r12
0x180007bcd  mov     bl, r12b
0x180007bd0  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x180007bd4  call    cs:__imp_LocalFree
0x180007bda  jmp     short loc_180007B6E
0x180007bdc  mov     rcx, qword ptr [rbp+Buffer]
0x180007be0  mov     eax, 7FFFFFFEh
0x180007be5  mov     ebx, 1
0x180007bea  test    rax, rax
0x180007bed  jz      short loc_180007C0D
0x180007bef  movzx   r8d, word ptr [rcx]
0x180007bf3  test    r8w, r8w
0x180007bf7  jz      short loc_180007C0D
0x180007bf9  mov     [rdx], r8w
0x180007bfd  add     rcx, 2
0x180007c01  add     rdx, 2
0x180007c05  sub     rax, rbx
0x180007c08  sub     rdi, rbx
0x180007c0b  jnz     short loc_180007BEA
0x180007c0d  test    rdi, rdi
0x180007c10  lea     rcx, [rdx-2]
0x180007c14  cmovnz  rcx, rdx
0x180007c18  mov     [rcx], r12w
0x180007c1c  jz      short loc_180007BBC
0x180007c1e  mov     [r14], r15d
0x180007c21  jmp     short loc_180007BD0
```
