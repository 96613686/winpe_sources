# EncryptWithSymmetricGcmPopKeyLocal(NgcSymmetricPopKey *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180012c7c`
- end: `0x180012dc0`
- name: `?EncryptWithSymmetricGcmPopKeyLocal@@YAJPEAVNgcSymmetricPopKey@@PEAEK1K1K1K1K1K1KPEAPEAEPEAK@Z`
- size: `324`
- prototype: `__int64 __fastcall(struct NgcSymmetricPopKey *this, unsigned __int8 *, __int64, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f8b8`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x180012c7c`
- `0x18001eee0`
- `0x180028010`

## string_xrefs

- `0x180012cac`: `onecore\ds\security\ngc\ngcpopkey\lib\symmetricpopkey.cpp`
- `0x180012d70`: `onecore\ds\security\ngc\ngcpopkey\lib\symmetricpopkey.cpp`

## pseudocode

```c
__int64 __fastcall EncryptWithSymmetricGcmPopKeyLocal(
        struct NgcSymmetricPopKey *this,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 *a8,
        unsigned int a9,
        unsigned __int8 *a10,
        unsigned int a11,
        unsigned __int8 *a12,
        unsigned int a13,
        unsigned __int8 *a14,
        unsigned int a15,
        unsigned __int8 **a16,
        unsigned int *a17)
{
  int v19; // eax
  int v20; // ebx
  unsigned __int8 *v21; // rcx
  unsigned int v23; // [rsp+20h] [rbp-81h]
  unsigned int v24; // [rsp+20h] [rbp-81h]
  unsigned __int8 *v25; // [rsp+80h] [rbp-21h] BYREF
  unsigned __int8 **v26; // [rsp+88h] [rbp-19h] BYREF
  unsigned __int8 *v27; // [rsp+90h] [rbp-11h] BYREF
  char v28; // [rsp+98h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+27h]
  unsigned int v30; // [rsp+D0h] [rbp+2Fh] BYREF

  v19 = (*(__int64 (__fastcall **)(struct NgcSymmetricPopKey *, unsigned __int8 *))(*(_QWORD *)this + 8LL))(this, a2);
  v20 = v19;
  if ( v19 >= 0 )
  {
    v30 = 0;
    v25 = 0;
    v26 = &v25;
    v27 = 0;
    v28 = 1;
    v20 = NgcSymmetricPopKey::EncryptGcm(this, a14, a15, a6, a7, a4, a5, a8, a9, a10, a11, a12, a13, &v27, &v30);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v26);
    if ( v20 >= 0 )
    {
      v21 = v25;
      v25 = 0;
      *a16 = v21;
      *a17 = v30;
      v20 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE0,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\symmetricpopkey.cpp",
        (const char *)(unsigned int)v20,
        v24);
    }
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v25, 0);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\symmetricpopkey.cpp",
      (const char *)(unsigned int)v19,
      v23);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180012c7c  push    rbp
0x180012c7e  push    rbx
0x180012c7f  push    rsi
0x180012c80  push    rdi
0x180012c81  lea     rbp, [rsp-7]
0x180012c86  sub     rsp, 0A8h
0x180012c8d  mov     rsi, r9
0x180012c90  mov     rdi, rcx
0x180012c93  mov     rax, [rcx]
0x180012c96  mov     rax, [rax+8]
0x180012c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c9f  mov     ebx, eax
0x180012ca1  test    eax, eax
0x180012ca3  jns     short loc_180012CC2
0x180012ca5  mov     rcx, [rbp+27h]; this
0x180012ca9  mov     r9d, eax; char *
0x180012cac  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180012cb3  mov     edx, 0CEh; void *
0x180012cb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012cbd  jmp     loc_180012DB2
0x180012cc2  mov     [rbp+1Fh+arg_0], 0
0x180012cc9  mov     [rbp+1Fh+var_40], 0
0x180012cd1  lea     rax, [rbp+1Fh+var_40]
0x180012cd5  mov     [rbp+1Fh+var_38], rax
0x180012cd9  mov     [rbp+1Fh+var_30], 0
0x180012ce1  mov     [rbp+1Fh+var_28], 1
0x180012ce5  lea     rax, [rbp+1Fh+arg_0]
0x180012ce9  mov     [rsp+0C0h+var_50], rax; unsigned int *
0x180012cee  lea     rax, [rbp+1Fh+var_30]
0x180012cf2  mov     [rsp+0C0h+var_58], rax; unsigned __int8 **
0x180012cf7  mov     eax, [rbp+1Fh+arg_60]
0x180012cfd  mov     [rsp+0C0h+var_60], eax; unsigned int
0x180012d01  mov     rax, [rbp+1Fh+arg_58]
0x180012d08  mov     [rsp+0C0h+var_68], rax; unsigned __int8 *
0x180012d0d  mov     eax, [rbp+1Fh+arg_50]
0x180012d10  mov     [rsp+0C0h+var_70], eax; unsigned int
0x180012d14  mov     rax, [rbp+1Fh+arg_48]
0x180012d18  mov     [rsp+0C0h+var_78], rax; unsigned __int8 *
0x180012d1d  mov     eax, [rbp+1Fh+arg_40]
0x180012d20  mov     [rsp+0C0h+var_80], eax; unsigned int
0x180012d24  mov     rax, [rbp+1Fh+arg_38]
0x180012d28  mov     [rsp+0C0h+var_88], rax; unsigned __int8 *
0x180012d2d  mov     eax, [rbp+1Fh+arg_20]
0x180012d30  mov     [rsp+0C0h+var_90], eax; unsigned int
0x180012d34  mov     [rsp+0C0h+var_98], rsi; unsigned __int8 *
0x180012d39  mov     eax, [rbp+1Fh+arg_30]
0x180012d3c  mov     [rsp+0C0h+var_A0], eax; int
0x180012d40  mov     r9, [rbp+1Fh+arg_28]; unsigned __int8 *
0x180012d44  mov     r8d, [rbp+1Fh+arg_70]; unsigned int
0x180012d4b  mov     rdx, [rbp+1Fh+arg_68]; unsigned __int8 *
0x180012d52  mov     rcx, rdi; this
0x180012d55  call    ?EncryptGcm@NgcSymmetricPopKey@@QEAAJPEAEK0K0K0K0K0KPEAPEAEPEAK@Z; NgcSymmetricPopKey::EncryptGcm(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x180012d5a  mov     ebx, eax
0x180012d5c  lea     rcx, [rbp+1Fh+var_38]
0x180012d60  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180012d65  test    ebx, ebx
0x180012d67  jns     short loc_180012D83
0x180012d69  mov     rcx, [rbp+27h]; this
0x180012d6d  mov     r9d, ebx; char *
0x180012d70  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180012d77  mov     edx, 0E0h; void *
0x180012d7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d81  jmp     short loc_180012DA7
0x180012d83  mov     rcx, [rbp+1Fh+var_40]
0x180012d87  mov     [rbp+1Fh+var_40], 0
0x180012d8f  mov     rax, [rbp+1Fh+arg_78]
0x180012d96  mov     [rax], rcx
0x180012d99  mov     rcx, [rbp+1Fh+arg_80]
0x180012da0  mov     eax, [rbp+1Fh+arg_0]
0x180012da3  mov     [rcx], eax
0x180012da5  xor     ebx, ebx
0x180012da7  xor     edx, edx
0x180012da9  lea     rcx, [rbp+1Fh+var_40]
0x180012dad  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180012db2  mov     eax, ebx
0x180012db4  add     rsp, 0A8h
0x180012dbb  pop     rdi
0x180012dbc  pop     rsi
0x180012dbd  pop     rbx
0x180012dbe  pop     rbp
0x180012dbf  retn
```
