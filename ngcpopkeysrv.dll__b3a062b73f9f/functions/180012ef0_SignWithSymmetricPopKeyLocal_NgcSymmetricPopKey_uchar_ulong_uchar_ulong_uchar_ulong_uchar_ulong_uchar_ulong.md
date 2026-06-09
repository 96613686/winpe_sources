# SignWithSymmetricPopKeyLocal(NgcSymmetricPopKey *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180012ef0`
- end: `0x180012ff1`
- name: `?SignWithSymmetricPopKeyLocal@@YAJPEAVNgcSymmetricPopKey@@PEAEK1K1K1KPEAPEAEPEAK@Z`
- size: `257`
- prototype: `__int64 __fastcall(struct NgcSymmetricPopKey *, unsigned __int8 *, __int64, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000fc20`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x180012ef0`
- `0x180028010`

## string_xrefs

- `0x180012f1b`: `onecore\ds\security\ngc\ngcpopkey\lib\symmetricpopkey.cpp`
- `0x180012faa`: `onecore\ds\security\ngc\ngcpopkey\lib\symmetricpopkey.cpp`

## pseudocode

```c
__int64 __fastcall SignWithSymmetricPopKeyLocal(
        struct NgcSymmetricPopKey *a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 *a8,
        unsigned int a9,
        unsigned __int8 **a10,
        unsigned int *a11)
{
  int v12; // eax
  int v13; // ebx
  __int64 v14; // rax
  unsigned __int8 *v15; // rcx
  int v17; // [rsp+20h] [rbp-58h]
  unsigned __int8 *v18; // [rsp+50h] [rbp-28h] BYREF
  _QWORD v19[2]; // [rsp+58h] [rbp-20h] BYREF
  char v20; // [rsp+68h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v12 = (*(__int64 (__fastcall **)(struct NgcSymmetricPopKey *, unsigned __int8 *))(*(_QWORD *)a1 + 8LL))(a1, a2);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v18 = 0;
    v14 = *(_QWORD *)a1;
    v19[0] = &v18;
    v19[1] = 0;
    v20 = 1;
    v13 = (*(__int64 (__fastcall **)(struct NgcSymmetricPopKey *, unsigned __int8 *, _QWORD, unsigned __int8 *))(v14 + 16))(
            a1,
            a8,
            a9,
            a6);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v19);
    if ( v13 >= 0 )
    {
      v15 = v18;
      v18 = 0;
      *a10 = v15;
      *a11 = 0;
      v13 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\symmetricpopkey.cpp",
        (const char *)(unsigned int)v13,
        a7);
    }
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v18, 0);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\symmetricpopkey.cpp",
      (const char *)(unsigned int)v12,
      v17);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180012ef0  push    rbp
0x180012ef2  push    rbx
0x180012ef3  push    rsi
0x180012ef4  push    rdi
0x180012ef5  mov     rbp, rsp
0x180012ef8  sub     rsp, 78h
0x180012efc  mov     rsi, r9
0x180012eff  mov     rdi, rcx
0x180012f02  mov     rax, [rcx]
0x180012f05  mov     rax, [rax+8]
0x180012f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f0e  mov     ebx, eax
0x180012f10  test    eax, eax
0x180012f12  jns     short loc_180012F31
0x180012f14  mov     rcx, [rbp+20h]; this
0x180012f18  mov     r9d, eax; char *
0x180012f1b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180012f22  mov     edx, 31h ; '1'; void *
0x180012f27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f2c  jmp     loc_180012FE6
0x180012f31  mov     [rbp+arg_0], 0
0x180012f38  mov     [rbp+var_28], 0
0x180012f40  mov     rax, [rdi]
0x180012f43  lea     rcx, [rbp+var_28]
0x180012f47  mov     [rbp+var_20], rcx
0x180012f4b  mov     [rbp+var_18], 0
0x180012f53  mov     [rbp+var_10], 1
0x180012f57  lea     rcx, [rbp+arg_0]
0x180012f5b  mov     [rsp+78h+var_38], rcx
0x180012f60  lea     rcx, [rbp+var_18]
0x180012f64  mov     [rsp+78h+var_40], rcx
0x180012f69  mov     ecx, [rbp+arg_20]
0x180012f6c  mov     [rsp+78h+var_48], ecx
0x180012f70  mov     [rsp+78h+var_50], rsi
0x180012f75  mov     ecx, [rbp+arg_30]
0x180012f78  mov     [rsp+78h+var_58], ecx; int
0x180012f7c  mov     r9, [rbp+arg_28]
0x180012f80  mov     r8d, [rbp+arg_40]
0x180012f84  mov     rdx, [rbp+arg_38]
0x180012f88  mov     rcx, rdi
0x180012f8b  mov     rax, [rax+10h]
0x180012f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f94  mov     ebx, eax
0x180012f96  lea     rcx, [rbp+var_20]
0x180012f9a  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180012f9f  test    ebx, ebx
0x180012fa1  jns     short loc_180012FBD
0x180012fa3  mov     rcx, [rbp+20h]; this
0x180012fa7  mov     r9d, ebx; char *
0x180012faa  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180012fb1  mov     edx, 3Dh ; '='; void *
0x180012fb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012fbb  jmp     short loc_180012FDB
0x180012fbd  mov     rcx, [rbp+var_28]
0x180012fc1  mov     [rbp+var_28], 0
0x180012fc9  mov     rax, [rbp+arg_48]
0x180012fcd  mov     [rax], rcx
0x180012fd0  mov     rcx, [rbp+arg_50]
0x180012fd4  mov     eax, [rbp+arg_0]
0x180012fd7  mov     [rcx], eax
0x180012fd9  xor     ebx, ebx
0x180012fdb  xor     edx, edx
0x180012fdd  lea     rcx, [rbp+var_28]
0x180012fe1  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180012fe6  mov     eax, ebx
0x180012fe8  add     rsp, 78h
0x180012fec  pop     rdi
0x180012fed  pop     rsi
0x180012fee  pop     rbx
0x180012fef  pop     rbp
0x180012ff0  retn
```
