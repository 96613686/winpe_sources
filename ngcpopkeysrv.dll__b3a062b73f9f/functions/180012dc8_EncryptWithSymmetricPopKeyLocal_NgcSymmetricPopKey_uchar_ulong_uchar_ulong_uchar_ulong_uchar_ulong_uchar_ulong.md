# EncryptWithSymmetricPopKeyLocal(NgcSymmetricPopKey *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180012dc8`
- end: `0x180012ee7`
- name: `?EncryptWithSymmetricPopKeyLocal@@YAJPEAVNgcSymmetricPopKey@@PEAEK1K1K1K1KPEAPEAEPEAK@Z`
- size: `287`
- prototype: `__int64 __fastcall(struct NgcSymmetricPopKey *, unsigned __int8 *, __int64, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000dc78`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x180012dc8`
- `0x180028010`

## string_xrefs

- `0x180012df8`: `onecore\ds\security\ngc\ngcpopkey\lib\symmetricpopkey.cpp`
- `0x180012e97`: `onecore\ds\security\ngc\ngcpopkey\lib\symmetricpopkey.cpp`

## pseudocode

```c
__int64 __fastcall EncryptWithSymmetricPopKeyLocal(
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
    v15 = (*(__int64 (__fastcall **)(struct NgcSymmetricPopKey *, unsigned __int8 *, _QWORD, unsigned __int8 *))(v16 + 32))(
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
        (void *)0x86,
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
      (void *)0x78,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\symmetricpopkey.cpp",
      (const char *)(unsigned int)v14,
      v19);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180012dc8  push    rbp
0x180012dca  push    rbx
0x180012dcb  push    rsi
0x180012dcc  push    rdi
0x180012dcd  lea     rbp, [rsp-7]
0x180012dd2  sub     rsp, 88h
0x180012dd9  mov     rsi, r9
0x180012ddc  mov     rdi, rcx
0x180012ddf  mov     rax, [rcx]
0x180012de2  mov     rax, [rax+8]
0x180012de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012deb  mov     ebx, eax
0x180012ded  test    eax, eax
0x180012def  jns     short loc_180012E0E
0x180012df1  mov     rcx, [rbp+27h]; this
0x180012df5  mov     r9d, eax; char *
0x180012df8  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180012dff  mov     edx, 78h ; 'x'; void *
0x180012e04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e09  jmp     loc_180012ED9
0x180012e0e  mov     [rbp+1Fh+arg_0], 0
0x180012e15  mov     [rbp+1Fh+var_40], 0
0x180012e1d  mov     rax, [rdi]
0x180012e20  lea     rcx, [rbp+1Fh+var_40]
0x180012e24  mov     [rbp+1Fh+var_38], rcx
0x180012e28  mov     [rbp+1Fh+var_30], 0
0x180012e30  mov     [rbp+1Fh+var_28], 1
0x180012e34  lea     rcx, [rbp+1Fh+arg_0]
0x180012e38  mov     [rsp+0A0h+var_50], rcx
0x180012e3d  lea     rcx, [rbp+1Fh+var_30]
0x180012e41  mov     [rsp+0A0h+var_58], rcx
0x180012e46  mov     ecx, [rbp+1Fh+arg_40]
0x180012e49  mov     [rsp+0A0h+var_60], ecx
0x180012e4d  mov     rcx, [rbp+1Fh+arg_38]
0x180012e51  mov     [rsp+0A0h+var_68], rcx
0x180012e56  mov     ecx, [rbp+1Fh+arg_20]
0x180012e59  mov     [rsp+0A0h+var_70], ecx
0x180012e5d  mov     [rsp+0A0h+var_78], rsi
0x180012e62  mov     ecx, [rbp+1Fh+arg_30]
0x180012e65  mov     [rsp+0A0h+var_80], ecx; int
0x180012e69  mov     r9, [rbp+1Fh+arg_28]
0x180012e6d  mov     r8d, [rbp+1Fh+arg_50]
0x180012e71  mov     rdx, [rbp+1Fh+arg_48]
0x180012e75  mov     rcx, rdi
0x180012e78  mov     rax, [rax+20h]
0x180012e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e81  mov     ebx, eax
0x180012e83  lea     rcx, [rbp+1Fh+var_38]
0x180012e87  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180012e8c  test    ebx, ebx
0x180012e8e  jns     short loc_180012EAA
0x180012e90  mov     rcx, [rbp+27h]; this
0x180012e94  mov     r9d, ebx; char *
0x180012e97  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180012e9e  mov     edx, 86h; void *
0x180012ea3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ea8  jmp     short loc_180012ECE
0x180012eaa  mov     rcx, [rbp+1Fh+var_40]
0x180012eae  mov     [rbp+1Fh+var_40], 0
0x180012eb6  mov     rax, [rbp+1Fh+arg_58]
0x180012ebd  mov     [rax], rcx
0x180012ec0  mov     rcx, [rbp+1Fh+arg_60]
0x180012ec7  mov     eax, [rbp+1Fh+arg_0]
0x180012eca  mov     [rcx], eax
0x180012ecc  xor     ebx, ebx
0x180012ece  xor     edx, edx
0x180012ed0  lea     rcx, [rbp+1Fh+var_40]
0x180012ed4  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180012ed9  mov     eax, ebx
0x180012edb  add     rsp, 88h
0x180012ee2  pop     rdi
0x180012ee3  pop     rsi
0x180012ee4  pop     rbx
0x180012ee5  pop     rbp
0x180012ee6  retn
```
