# NgcSymmetricPopKey::VerifySignature(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)

- ea: `0x18001f1d0`
- end: `0x18001f2bd`
- name: `?VerifySignature@NgcSymmetricPopKey@@UEAAJPEAEK0K0K0K@Z`
- size: `237`
- prototype: `__int64 __fastcall(NgcSymmetricPopKey *this, unsigned __int8 *, __int64, unsigned __int8 *, unsigned int Size, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180006409`
- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x18001f1d0`
- `0x180028010`

## string_xrefs

- `0x18001f274`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\symmetricpopkeybase.cpp`

## pseudocode

```c
__int64 __fastcall NgcSymmetricPopKey::VerifySignature(
        NgcSymmetricPopKey *this,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned int Size,
        unsigned __int8 *a6,
        unsigned int a7)
{
  __int64 v8; // rax
  int v9; // ebx
  __int64 v10; // rdx
  void *Buf2; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v13[2]; // [rsp+58h] [rbp-18h] BYREF
  char v14; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  Buf2 = 0;
  v8 = *(_QWORD *)this;
  v13[0] = &Buf2;
  v13[1] = 0;
  v14 = 1;
  v9 = (*(__int64 (__fastcall **)(NgcSymmetricPopKey *, unsigned __int8 *, __int64, unsigned __int8 *))(v8 + 16))(
         this,
         a2,
         a3,
         a6);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v13);
  if ( v9 >= 0 )
  {
    if ( Size )
    {
      v10 = 81;
    }
    else
    {
      if ( !memcmp_0(a4, Buf2, 0) )
      {
        v9 = 0;
        goto LABEL_10;
      }
      v10 = 82;
    }
    v9 = -2146893818;
  }
  else
  {
    v10 = 79;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\symmetricpopkeybase.cpp",
    (const char *)(unsigned int)v9,
    a7);
LABEL_10:
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&Buf2, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001f1d0  mov     r11, rsp
0x18001f1d3  mov     [r11+10h], rbx
0x18001f1d7  mov     [r11+18h], rdi
0x18001f1db  push    rbp
0x18001f1dc  mov     rbp, rsp
0x18001f1df  sub     rsp, 70h
0x18001f1e3  mov     rdi, r9
0x18001f1e6  mov     r10, rcx
0x18001f1e9  mov     [rbp+arg_0], 0
0x18001f1f0  mov     [rbp+Buf2], 0
0x18001f1f8  mov     rax, [rcx]
0x18001f1fb  lea     rcx, [rbp+Buf2]
0x18001f1ff  mov     [rbp+var_18], rcx
0x18001f203  mov     [rbp+var_10], 0
0x18001f20b  mov     [rbp+var_8], 1
0x18001f20f  lea     rcx, [rbp+arg_0]
0x18001f213  mov     [r11-38h], rcx
0x18001f217  lea     rcx, [rbp+var_10]
0x18001f21b  mov     [r11-40h], rcx
0x18001f21f  mov     ecx, [rbp+arg_40]
0x18001f222  mov     [rsp+70h+var_40], ecx
0x18001f226  mov     rcx, [rbp+arg_38]
0x18001f22a  mov     [r11-50h], rcx
0x18001f22e  mov     ecx, [rbp+arg_30]
0x18001f231  mov     [rsp+70h+var_50], ecx; int
0x18001f235  mov     r9, [rbp+arg_28]
0x18001f239  mov     rcx, r10
0x18001f23c  mov     rax, [rax+10h]
0x18001f240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f245  mov     ebx, eax
0x18001f247  lea     rcx, [rbp+var_18]
0x18001f24b  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001f250  test    ebx, ebx
0x18001f252  jns     short loc_18001F25B
0x18001f254  mov     edx, 4Fh ; 'O'
0x18001f259  jmp     short loc_18001F26D
0x18001f25b  mov     eax, dword ptr [rbp+Size]
0x18001f25e  cmp     eax, [rbp+arg_0]
0x18001f261  jz      short loc_18001F282
0x18001f263  mov     edx, 51h ; 'Q'; void *
0x18001f268  mov     ebx, 80090006h
0x18001f26d  mov     rcx, [rbp+8]; this
0x18001f271  mov     r9d, ebx; char *
0x18001f274  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001f27b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f280  jmp     short loc_18001F29E
0x18001f282  mov     r8, rax; Size
0x18001f285  mov     rdx, [rbp+Buf2]; Buf2
0x18001f289  mov     rcx, rdi; Buf1
0x18001f28c  call    memcmp_0
0x18001f291  test    eax, eax
0x18001f293  jz      short loc_18001F29C
0x18001f295  mov     edx, 52h ; 'R'
0x18001f29a  jmp     short loc_18001F268
0x18001f29c  xor     ebx, ebx
0x18001f29e  xor     edx, edx
0x18001f2a0  lea     rcx, [rbp+Buf2]
0x18001f2a4  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001f2a9  mov     eax, ebx
0x18001f2ab  lea     r11, [rsp+70h+var_s0]
0x18001f2b0  mov     rbx, [r11+18h]
0x18001f2b4  mov     rdi, [r11+20h]
0x18001f2b8  mov     rsp, r11
0x18001f2bb  pop     rbp
0x18001f2bc  retn
```
