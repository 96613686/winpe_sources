# DecryptWithSymmetricPopKeyLocal(NgcSymmetricPopKey *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180012b54`
- end: `0x180012c73`
- name: `?DecryptWithSymmetricPopKeyLocal@@YAJPEAVNgcSymmetricPopKey@@PEAEK1K1K1K1KPEAPEAEPEAK@Z`
- size: `287`
- prototype: `__int64 __fastcall(struct NgcSymmetricPopKey *, unsigned __int8 *, __int64, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000f230`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x180012b54`
- `0x180028010`

## string_xrefs

- `0x180012b84`: `onecore\ds\security\ngc\ngcpopkey\lib\symmetricpopkey.cpp`
- `0x180012c23`: `onecore\ds\security\ngc\ngcpopkey\lib\symmetricpopkey.cpp`

## pseudocode

```c
__int64 __fastcall DecryptWithSymmetricPopKeyLocal(
        struct NgcSymmetricPopKey *a1,
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
        unsigned __int8 **a12,
        unsigned int *a13)
{
  int v14; // eax
  int v15; // ebx
  __int64 v16; // rax
  unsigned __int8 *v17; // rcx
  int v19; // [rsp+20h] [rbp-61h]
  unsigned __int8 *v20; // [rsp+60h] [rbp-21h] BYREF
  _QWORD v21[2]; // [rsp+68h] [rbp-19h] BYREF
  char v22; // [rsp+78h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+27h]

  v14 = (*(__int64 (__fastcall **)(struct NgcSymmetricPopKey *, unsigned __int8 *))(*(_QWORD *)a1 + 8LL))(a1, a2);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v20 = 0;
    v16 = *(_QWORD *)a1;
    v21[0] = &v20;
    v21[1] = 0;
    v22 = 1;
    v15 = (*(__int64 (__fastcall **)(struct NgcSymmetricPopKey *, unsigned __int8 *, _QWORD, unsigned __int8 *))(v16 + 40))(
            a1,
            a10,
            a11,
            a6);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v21);
    if ( v15 >= 0 )
    {
      v17 = v20;
      v20 = 0;
      *a12 = v17;
      *a13 = 0;
      v15 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\symmetricpopkey.cpp",
        (const char *)(unsigned int)v15,
        a7);
    }
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v20, 0);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\symmetricpopkey.cpp",
      (const char *)(unsigned int)v14,
      v19);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180012b54  push    rbp
0x180012b56  push    rbx
0x180012b57  push    rsi
0x180012b58  push    rdi
0x180012b59  lea     rbp, [rsp-7]
0x180012b5e  sub     rsp, 88h
0x180012b65  mov     rsi, r9
0x180012b68  mov     rdi, rcx
0x180012b6b  mov     rax, [rcx]
0x180012b6e  mov     rax, [rax+8]
0x180012b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b77  mov     ebx, eax
0x180012b79  test    eax, eax
0x180012b7b  jns     short loc_180012B9A
0x180012b7d  mov     rcx, [rbp+27h]; this
0x180012b81  mov     r9d, eax; char *
0x180012b84  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180012b8b  mov     edx, 0A1h; void *
0x180012b90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012b95  jmp     loc_180012C65
0x180012b9a  mov     [rbp+1Fh+arg_0], 0
0x180012ba1  mov     [rbp+1Fh+var_40], 0
0x180012ba9  mov     rax, [rdi]
0x180012bac  lea     rcx, [rbp+1Fh+var_40]
0x180012bb0  mov     [rbp+1Fh+var_38], rcx
0x180012bb4  mov     [rbp+1Fh+var_30], 0
0x180012bbc  mov     [rbp+1Fh+var_28], 1
0x180012bc0  lea     rcx, [rbp+1Fh+arg_0]
0x180012bc4  mov     [rsp+0A0h+var_50], rcx
0x180012bc9  lea     rcx, [rbp+1Fh+var_30]
0x180012bcd  mov     [rsp+0A0h+var_58], rcx
0x180012bd2  mov     ecx, [rbp+1Fh+arg_40]
0x180012bd5  mov     [rsp+0A0h+var_60], ecx
0x180012bd9  mov     rcx, [rbp+1Fh+arg_38]
0x180012bdd  mov     [rsp+0A0h+var_68], rcx
0x180012be2  mov     ecx, [rbp+1Fh+arg_20]
0x180012be5  mov     [rsp+0A0h+var_70], ecx
0x180012be9  mov     [rsp+0A0h+var_78], rsi
0x180012bee  mov     ecx, [rbp+1Fh+arg_30]
0x180012bf1  mov     [rsp+0A0h+var_80], ecx; int
0x180012bf5  mov     r9, [rbp+1Fh+arg_28]
0x180012bf9  mov     r8d, [rbp+1Fh+arg_50]
0x180012bfd  mov     rdx, [rbp+1Fh+arg_48]
0x180012c01  mov     rcx, rdi
0x180012c04  mov     rax, [rax+28h]
0x180012c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c0d  mov     ebx, eax
0x180012c0f  lea     rcx, [rbp+1Fh+var_38]
0x180012c13  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180012c18  test    ebx, ebx
0x180012c1a  jns     short loc_180012C36
0x180012c1c  mov     rcx, [rbp+27h]; this
0x180012c20  mov     r9d, ebx; char *
0x180012c23  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180012c2a  mov     edx, 0AFh; void *
0x180012c2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c34  jmp     short loc_180012C5A
0x180012c36  mov     rcx, [rbp+1Fh+var_40]
0x180012c3a  mov     [rbp+1Fh+var_40], 0
0x180012c42  mov     rax, [rbp+1Fh+arg_58]
0x180012c49  mov     [rax], rcx
0x180012c4c  mov     rcx, [rbp+1Fh+arg_60]
0x180012c53  mov     eax, [rbp+1Fh+arg_0]
0x180012c56  mov     [rcx], eax
0x180012c58  xor     ebx, ebx
0x180012c5a  xor     edx, edx
0x180012c5c  lea     rcx, [rbp+1Fh+var_40]
0x180012c60  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180012c65  mov     eax, ebx
0x180012c67  add     rsp, 88h
0x180012c6e  pop     rdi
0x180012c6f  pop     rsi
0x180012c70  pop     rbx
0x180012c71  pop     rbp
0x180012c72  retn
```
