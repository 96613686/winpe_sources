# DecryptWithSymmetricGcmPopKeyLocal(NgcSymmetricPopKey *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180012a08`
- end: `0x180012b4c`
- name: `?DecryptWithSymmetricGcmPopKeyLocal@@YAJPEAVNgcSymmetricPopKey@@PEAEK1K1K1K1K1K1KPEAPEAEPEAK@Z`
- size: `324`
- prototype: `__int64 __fastcall(struct NgcSymmetricPopKey *this, unsigned __int8 *, __int64, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000eae0`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x180012a08`
- `0x18001ebe0`
- `0x180028010`

## string_xrefs

- `0x180012a38`: `onecore\ds\security\ngc\ngcpopkey\lib\symmetricpopkey.cpp`
- `0x180012afc`: `onecore\ds\security\ngc\ngcpopkey\lib\symmetricpopkey.cpp`

## pseudocode

```c
__int64 __fastcall DecryptWithSymmetricGcmPopKeyLocal(
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
    v20 = NgcSymmetricPopKey::DecryptGcm(this, a14, a15, a6, a7, a4, a5, a8, a9, a10, a11, a12, a13, &v27, &v30);
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
        (void *)0x111,
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
      (void *)0xFF,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\lib\\symmetricpopkey.cpp",
      (const char *)(unsigned int)v19,
      v23);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180012a08  push    rbp
0x180012a0a  push    rbx
0x180012a0b  push    rsi
0x180012a0c  push    rdi
0x180012a0d  lea     rbp, [rsp-7]
0x180012a12  sub     rsp, 0A8h
0x180012a19  mov     rsi, r9
0x180012a1c  mov     rdi, rcx
0x180012a1f  mov     rax, [rcx]
0x180012a22  mov     rax, [rax+8]
0x180012a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a2b  mov     ebx, eax
0x180012a2d  test    eax, eax
0x180012a2f  jns     short loc_180012A4E
0x180012a31  mov     rcx, [rbp+27h]; this
0x180012a35  mov     r9d, eax; char *
0x180012a38  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180012a3f  mov     edx, 0FFh; void *
0x180012a44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a49  jmp     loc_180012B3E
0x180012a4e  mov     [rbp+1Fh+arg_0], 0
0x180012a55  mov     [rbp+1Fh+var_40], 0
0x180012a5d  lea     rax, [rbp+1Fh+var_40]
0x180012a61  mov     [rbp+1Fh+var_38], rax
0x180012a65  mov     [rbp+1Fh+var_30], 0
0x180012a6d  mov     [rbp+1Fh+var_28], 1
0x180012a71  lea     rax, [rbp+1Fh+arg_0]
0x180012a75  mov     [rsp+0C0h+var_50], rax; unsigned int *
0x180012a7a  lea     rax, [rbp+1Fh+var_30]
0x180012a7e  mov     [rsp+0C0h+var_58], rax; unsigned __int8 **
0x180012a83  mov     eax, [rbp+1Fh+arg_60]
0x180012a89  mov     [rsp+0C0h+var_60], eax; unsigned int
0x180012a8d  mov     rax, [rbp+1Fh+arg_58]
0x180012a94  mov     [rsp+0C0h+var_68], rax; unsigned __int8 *
0x180012a99  mov     eax, [rbp+1Fh+arg_50]
0x180012a9c  mov     [rsp+0C0h+var_70], eax; unsigned int
0x180012aa0  mov     rax, [rbp+1Fh+arg_48]
0x180012aa4  mov     [rsp+0C0h+var_78], rax; unsigned __int8 *
0x180012aa9  mov     eax, [rbp+1Fh+arg_40]
0x180012aac  mov     [rsp+0C0h+var_80], eax; unsigned int
0x180012ab0  mov     rax, [rbp+1Fh+arg_38]
0x180012ab4  mov     [rsp+0C0h+var_88], rax; unsigned __int8 *
0x180012ab9  mov     eax, [rbp+1Fh+arg_20]
0x180012abc  mov     [rsp+0C0h+var_90], eax; unsigned int
0x180012ac0  mov     [rsp+0C0h+var_98], rsi; unsigned __int8 *
0x180012ac5  mov     eax, [rbp+1Fh+arg_30]
0x180012ac8  mov     [rsp+0C0h+var_A0], eax; int
0x180012acc  mov     r9, [rbp+1Fh+arg_28]; unsigned __int8 *
0x180012ad0  mov     r8d, [rbp+1Fh+arg_70]; unsigned int
0x180012ad7  mov     rdx, [rbp+1Fh+arg_68]; unsigned __int8 *
0x180012ade  mov     rcx, rdi; this
0x180012ae1  call    ?DecryptGcm@NgcSymmetricPopKey@@QEAAJPEAEK0K0K0K0K0KPEAPEAEPEAK@Z; NgcSymmetricPopKey::DecryptGcm(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x180012ae6  mov     ebx, eax
0x180012ae8  lea     rcx, [rbp+1Fh+var_38]
0x180012aec  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180012af1  test    ebx, ebx
0x180012af3  jns     short loc_180012B0F
0x180012af5  mov     rcx, [rbp+27h]; this
0x180012af9  mov     r9d, ebx; char *
0x180012afc  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180012b03  mov     edx, 111h; void *
0x180012b08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012b0d  jmp     short loc_180012B33
0x180012b0f  mov     rcx, [rbp+1Fh+var_40]
0x180012b13  mov     [rbp+1Fh+var_40], 0
0x180012b1b  mov     rax, [rbp+1Fh+arg_78]
0x180012b22  mov     [rax], rcx
0x180012b25  mov     rcx, [rbp+1Fh+arg_80]
0x180012b2c  mov     eax, [rbp+1Fh+arg_0]
0x180012b2f  mov     [rcx], eax
0x180012b31  xor     ebx, ebx
0x180012b33  xor     edx, edx
0x180012b35  lea     rcx, [rbp+1Fh+var_40]
0x180012b39  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180012b3e  mov     eax, ebx
0x180012b40  add     rsp, 0A8h
0x180012b47  pop     rdi
0x180012b48  pop     rsi
0x180012b49  pop     rbx
0x180012b4a  pop     rbp
0x180012b4b  retn
```
