# GenReadTlsDirectory(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_MODULE *,uchar,ulong)

- ea: `0x18001bca0`
- end: `0x18001bec0`
- name: `?GenReadTlsDirectory@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_MODULE@@EK@Z`
- size: `544`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *, struct _INTERNAL_MODULE *, unsigned __int8, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017b8c`

## callees

- `0x180001710`
- `0x18001bca0`
- `0x18002c010`

## string_xrefs

- `0x18001bd75`: `GenReadTlsDirectory.Read(0x%I64x, %ws) failed, 0x%08x`
- `0x18001bd0c`: `GenReadTlsDirectory(0x%I64x, %ws) unsupported pointer size %u`
- `0x18001be22`: `GenReadTlsDirectory.Index(0x%I64x, %ws) failed, 0x%08x`
- `0x18001be66`: `GenReadTlsDirectory(0x%I64x, %ws) size overflow`

## pseudocode

```c
__int64 __fastcall GenReadTlsDirectory(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        struct _INTERNAL_MODULE *a3,
        unsigned __int8 a4,
        unsigned int a5)
{
  unsigned int v8; // edi
  __int64 v9; // r15
  __int64 v10; // rcx
  void (__fastcall *v11)(__int64, __int64, const char *, __int64, _QWORD, unsigned int); // rax
  const char *v12; // r8
  __int64 v13; // r9
  __int64 v14; // r8
  int v15; // ecx
  unsigned int v16; // eax
  __int128 v18; // [rsp+40h] [rbp-31h] BYREF
  __int64 v19; // [rsp+50h] [rbp-21h]
  __int128 v20; // [rsp+58h] [rbp-19h] BYREF
  __int128 v21; // [rsp+68h] [rbp-9h]
  __int64 v22; // [rsp+78h] [rbp+7h]

  v19 = 0;
  v22 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  if ( a4 == 4 )
  {
    v9 = a5;
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int128 *, int))(**((_QWORD **)a1 + 2) + 240LL))(
           *((_QWORD *)a1 + 2),
           *(_QWORD *)a1,
           a5 + *((_QWORD *)a3 + 1),
           &v18,
           24);
    if ( v8 )
    {
      v10 = *((_QWORD *)a1 + 5);
      v11 = *(void (__fastcall **)(__int64, __int64, const char *, __int64, _QWORD, unsigned int))(*(_QWORD *)v10 + 8LL);
      goto LABEL_6;
    }
    v14 = SDWORD2(v18);
    *(_QWORD *)&v20 = (int)v18;
    *((_QWORD *)&v20 + 1) = SDWORD1(v18);
    *((_QWORD *)&v21 + 1) = SHIDWORD(v18);
    v22 = v19;
    *(_QWORD *)&v21 = SDWORD2(v18);
  }
  else
  {
    if ( a4 != 8 )
    {
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        2,
        "GenReadTlsDirectory(0x%I64x, %ws) unsupported pointer size %u",
        *((_QWORD *)a3 + 1),
        *((_QWORD *)a3 + 15),
        a4);
      return (unsigned int)-2147024809;
    }
    v9 = a5;
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int128 *, int))(**((_QWORD **)a1 + 2) + 240LL))(
           *((_QWORD *)a1 + 2),
           *(_QWORD *)a1,
           a5 + *((_QWORD *)a3 + 1),
           &v20,
           40);
    if ( v8 )
    {
      v10 = *((_QWORD *)a1 + 5);
      v11 = *(void (__fastcall **)(__int64, __int64, const char *, __int64, _QWORD, unsigned int))(*(_QWORD *)v10 + 8LL);
LABEL_6:
      v12 = "GenReadTlsDirectory.Read(0x%I64x, %ws) failed, 0x%08x";
      v13 = v9 + *((_QWORD *)a3 + 1);
LABEL_13:
      v11(v10, 2, v12, v13, *((_QWORD *)a3 + 15), v8);
      return v8;
    }
    v14 = v21;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, char *, int))(**((_QWORD **)a1 + 2) + 240LL))(
         *((_QWORD *)a1 + 2),
         *(_QWORD *)a1,
         v14,
         (char *)a3 + 108,
         4);
  if ( v8 )
  {
    v10 = *((_QWORD *)a1 + 5);
    v12 = "GenReadTlsDirectory.Index(0x%I64x, %ws) failed, 0x%08x";
    v13 = v21;
    v11 = *(void (__fastcall **)(__int64, __int64, const char *, __int64, _QWORD, unsigned int))(*(_QWORD *)v10 + 8LL);
    goto LABEL_13;
  }
  if ( *((_QWORD *)&v20 + 1) - (_QWORD)v20 <= 0xFFFFFFFF )
  {
    v15 = DWORD2(v20) - v20;
    *((_DWORD *)a3 + 28) = DWORD2(v20) - v20;
    if ( v15 )
    {
      v16 = *((_DWORD *)a3 + 27);
      if ( v16 > *((_DWORD *)a2 + 23) )
        *((_DWORD *)a2 + 23) = v16;
    }
  }
  else
  {
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      2,
      "GenReadTlsDirectory(0x%I64x, %ws) size overflow",
      *((_QWORD *)a3 + 1),
      *((_QWORD *)a3 + 15));
  }
  return v8;
}

```

## disassembly

```asm
0x18001bca0  push    rbp
0x18001bca2  push    rbx
0x18001bca3  push    rsi
0x18001bca4  push    rdi
0x18001bca5  push    r14
0x18001bca7  push    r15
0x18001bca9  lea     rbp, [rsp-27h]
0x18001bcae  sub     rsp, 98h
0x18001bcb5  mov     rax, cs:__security_cookie
0x18001bcbc  xor     rax, rsp
0x18001bcbf  mov     [rbp+4Fh+var_40], rax
0x18001bcc3  xor     eax, eax
0x18001bcc5  xorps   xmm1, xmm1
0x18001bcc8  mov     [rbp+4Fh+var_70], rax
0x18001bccc  xorps   xmm0, xmm0
0x18001bccf  mov     [rbp+4Fh+var_48], rax
0x18001bcd3  mov     rbx, r8
0x18001bcd6  mov     r14, rdx
0x18001bcd9  mov     rsi, rcx
0x18001bcdc  movups  [rbp+4Fh+var_80], xmm0
0x18001bce0  movups  [rbp+4Fh+var_68], xmm1
0x18001bce4  movups  [rbp+4Fh+var_58], xmm1
0x18001bce8  cmp     r9b, 4
0x18001bcec  jz      loc_18001BD8A
0x18001bcf2  cmp     r9b, 8
0x18001bcf6  jz      short loc_18001BD33
0x18001bcf8  mov     rcx, [rcx+28h]
0x18001bcfc  movzx   edx, r9b
0x18001bd00  mov     r9, [r8+8]
0x18001bd04  mov     [rsp+0C0h+var_98], edx
0x18001bd08  mov     rdx, [r8+78h]
0x18001bd0c  lea     r8, aGenreadtlsdire_0; "GenReadTlsDirectory(0x%I64x, %ws) unsup"...
0x18001bd13  mov     rax, [rcx]
0x18001bd16  mov     [rsp+0C0h+var_A0], rdx
0x18001bd1b  mov     edx, 2
0x18001bd20  mov     rax, [rax+8]
0x18001bd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd29  mov     edi, 80070057h
0x18001bd2e  jmp     loc_18001BEA2
0x18001bd33  mov     rcx, [rcx+10h]
0x18001bd37  lea     r9, [rbp+4Fh+var_68]
0x18001bd3b  mov     r8, [r8+8]
0x18001bd3f  mov     r15d, [rbp+4Fh+arg_20]
0x18001bd43  add     r8, r15
0x18001bd46  mov     dword ptr [rsp+0C0h+var_A0], 28h ; '('
0x18001bd4e  mov     rdx, [rcx]
0x18001bd51  mov     rax, [rdx+0F0h]
0x18001bd58  mov     rdx, [rsi]
0x18001bd5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd60  mov     edi, eax
0x18001bd62  test    eax, eax
0x18001bd64  jz      short loc_18001BD84
0x18001bd66  mov     rcx, [rsi+28h]
0x18001bd6a  mov     r8, [rcx]
0x18001bd6d  mov     rax, [r8+8]
0x18001bd71  mov     r9, [rbx+8]
0x18001bd75  lea     r8, aGenreadtlsdire; "GenReadTlsDirectory.Read(0x%I64x, %ws) "...
0x18001bd7c  add     r9, r15
0x18001bd7f  jmp     loc_18001BE34
0x18001bd84  mov     r8, qword ptr [rbp+4Fh+var_58]
0x18001bd88  jmp     short loc_18001BDF6
0x18001bd8a  mov     rcx, [rcx+10h]
0x18001bd8e  lea     r9, [rbp+4Fh+var_80]
0x18001bd92  mov     r8, [r8+8]
0x18001bd96  mov     r15d, [rbp+4Fh+arg_20]
0x18001bd9a  add     r8, r15
0x18001bd9d  mov     dword ptr [rsp+0C0h+var_A0], 18h
0x18001bda5  mov     rdx, [rcx]
0x18001bda8  mov     rax, [rdx+0F0h]
0x18001bdaf  mov     rdx, [rsi]
0x18001bdb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdb7  mov     edi, eax
0x18001bdb9  test    eax, eax
0x18001bdbb  jz      short loc_18001BDCA
0x18001bdbd  mov     rcx, [rsi+28h]
0x18001bdc1  mov     rdx, [rcx]
0x18001bdc4  mov     rax, [rdx+8]
0x18001bdc8  jmp     short loc_18001BD71
0x18001bdca  movsxd  rax, dword ptr [rbp+4Fh+var_80]
0x18001bdce  movsxd  r8, dword ptr [rbp+4Fh+var_80+8]
0x18001bdd2  mov     qword ptr [rbp+4Fh+var_68], rax
0x18001bdd6  movsxd  rax, dword ptr [rbp+4Fh+var_80+4]
0x18001bdda  mov     qword ptr [rbp+4Fh+var_68+8], rax
0x18001bdde  movsxd  rax, dword ptr [rbp+4Fh+var_80+0Ch]
0x18001bde2  mov     qword ptr [rbp+4Fh+var_58+8], rax
0x18001bde6  mov     eax, dword ptr [rbp+4Fh+var_70]
0x18001bde9  mov     dword ptr [rbp+4Fh+var_48], eax
0x18001bdec  mov     eax, dword ptr [rbp+4Fh+var_70+4]
0x18001bdef  mov     dword ptr [rbp+4Fh+var_48+4], eax
0x18001bdf2  mov     qword ptr [rbp+4Fh+var_58], r8
0x18001bdf6  mov     rcx, [rsi+10h]
0x18001bdfa  lea     r9, [rbx+6Ch]
0x18001bdfe  mov     rdx, [rsi]
0x18001be01  mov     dword ptr [rsp+0C0h+var_A0], 4
0x18001be09  mov     rax, [rcx]
0x18001be0c  mov     rax, [rax+0F0h]
0x18001be13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be18  mov     edi, eax
0x18001be1a  test    eax, eax
0x18001be1c  jz      short loc_18001BE4D
0x18001be1e  mov     rcx, [rsi+28h]
0x18001be22  lea     r8, aGenreadtlsdire_2; "GenReadTlsDirectory.Index(0x%I64x, %ws)"...
0x18001be29  mov     r9, qword ptr [rbp+4Fh+var_58]
0x18001be2d  mov     rax, [rcx]
0x18001be30  mov     rax, [rax+8]
0x18001be34  mov     rdx, [rbx+78h]
0x18001be38  mov     [rsp+0C0h+var_98], edi
0x18001be3c  mov     [rsp+0C0h+var_A0], rdx
0x18001be41  mov     edx, 2
0x18001be46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be4b  jmp     short loc_18001BEA2
0x18001be4d  mov     rcx, qword ptr [rbp+4Fh+var_68+8]
0x18001be51  mov     edx, 0FFFFFFFFh
0x18001be56  mov     rax, rcx
0x18001be59  sub     rax, qword ptr [rbp+4Fh+var_68]
0x18001be5d  cmp     rax, rdx
0x18001be60  jbe     short loc_18001BE8D
0x18001be62  mov     rdx, [rbx+78h]
0x18001be66  lea     r8, aGenreadtlsdire_1; "GenReadTlsDirectory(0x%I64x, %ws) size "...
0x18001be6d  mov     rcx, [rsi+28h]
0x18001be71  mov     r9, [rbx+8]
0x18001be75  mov     [rsp+0C0h+var_A0], rdx
0x18001be7a  mov     edx, 2
0x18001be7f  mov     rax, [rcx]
0x18001be82  mov     rax, [rax+8]
0x18001be86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be8b  jmp     short loc_18001BEA2
0x18001be8d  sub     ecx, dword ptr [rbp+4Fh+var_68]
0x18001be90  mov     [rbx+70h], ecx
0x18001be93  jz      short loc_18001BEA2
0x18001be95  mov     eax, [rbx+6Ch]
0x18001be98  cmp     eax, [r14+5Ch]
0x18001be9c  jbe     short loc_18001BEA2
0x18001be9e  mov     [r14+5Ch], eax
0x18001bea2  mov     eax, edi
0x18001bea4  mov     rcx, [rbp+4Fh+var_40]
0x18001bea8  xor     rcx, rsp; StackCookie
0x18001beab  call    __security_check_cookie
0x18001beb0  add     rsp, 98h
0x18001beb7  pop     r15
0x18001beb9  pop     r14
0x18001bebb  pop     rdi
0x18001bebc  pop     rsi
0x18001bebd  pop     rbx
0x18001bebe  pop     rbp
0x18001bebf  retn
```
