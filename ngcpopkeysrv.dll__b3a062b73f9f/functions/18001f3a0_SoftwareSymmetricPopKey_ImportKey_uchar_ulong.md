# SoftwareSymmetricPopKey::ImportKey(uchar *,ulong)

- ea: `0x18001f3a0`
- end: `0x18001f4a0`
- name: `?ImportKey@SoftwareSymmetricPopKey@@UEAAJPEAEK@Z`
- size: `256`
- prototype: `__int64 __fastcall(SoftwareSymmetricPopKey *this, NgcUtils *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x18001368c`
- `0x180014b18`
- `0x18001f3a0`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001f45b`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001f45b`
- `bcrypt!BCryptDestroyKey` at `0x18001f428`
- `bcrypt!BCryptDestroyKey` at `0x18001f428`

## string_xrefs

- `0x18001f406`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\softwaresymmetricpopkey.cpp`
- `0x18001f469`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\softwaresymmetricpopkey.cpp`

## pseudocode

```c
__int64 __fastcall SoftwareSymmetricPopKey::ImportKey(SoftwareSymmetricPopKey *this, NgcUtils *a2, unsigned int a3)
{
  int v4; // ebx
  void *v5; // rcx
  NTSTATUS SymmetricKey; // eax
  int pbSecret; // [rsp+20h] [rbp-40h]
  int pbSecreta; // [rsp+20h] [rbp-40h]
  unsigned int *cbSecret; // [rsp+28h] [rbp-38h]
  PUCHAR v11; // [rsp+40h] [rbp-20h] BYREF
  PUCHAR *v12; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v13[2]; // [rsp+50h] [rbp-10h] BYREF
  char v14; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  unsigned __int8 *v16; // [rsp+88h] [rbp+28h] BYREF

  LODWORD(v16) = 0;
  v11 = 0;
  *(_QWORD *)v13 = 0;
  v12 = &v11;
  v14 = 1;
  v4 = NgcUtils::UnprotectData(a2, (const unsigned __int8 *)a3, a3, (unsigned int)v13, &v16, cbSecret);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v12);
  if ( v4 >= 0 )
  {
    v5 = (void *)*((_QWORD *)this + 1);
    if ( v5 )
    {
      BCryptDestroyKey(v5);
      *((_QWORD *)this + 1) = 0;
    }
    SymmetricKey = BCryptGenerateSymmetricKey(
                     (BCRYPT_ALG_HANDLE)0x341,
                     (BCRYPT_KEY_HANDLE *)this + 1,
                     0,
                     0,
                     v11,
                     (ULONG)v16,
                     0);
    if ( SymmetricKey >= 0 )
      v4 = 0;
    else
      v4 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x27,
             (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\softwaresymmetricpopkey.cpp",
             (const char *)(unsigned int)SymmetricKey,
             pbSecreta);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\softwaresymmetricpopkey.cpp",
      (const char *)(unsigned int)v4,
      pbSecret);
  }
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v11, 0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001f3a0  mov     [rsp-8+arg_0], rbx
0x18001f3a5  mov     [rsp-8+arg_8], rdi
0x18001f3aa  push    rbp
0x18001f3ab  mov     rbp, rsp
0x18001f3ae  sub     rsp, 60h
0x18001f3b2  mov     rdi, rcx
0x18001f3b5  mov     dword ptr [rbp+arg_18], 0
0x18001f3bc  mov     rax, rdx
0x18001f3bf  mov     [rbp+var_20], 0
0x18001f3c7  lea     rcx, [rbp+var_20]
0x18001f3cb  mov     qword ptr [rbp+var_10], 0
0x18001f3d3  mov     [rbp+var_18], rcx
0x18001f3d7  lea     r9, [rbp+var_10]; unsigned int
0x18001f3db  lea     rcx, [rbp+arg_18]
0x18001f3df  mov     [rbp+var_8], 1
0x18001f3e3  mov     [rsp+60h+pbSecret], rcx; int
0x18001f3e8  mov     edx, r8d; unsigned __int8 *
0x18001f3eb  mov     rcx, rax; this
0x18001f3ee  call    ?UnprotectData@NgcUtils@@YAJPEBEKKPEAPEAEPEAK@Z; NgcUtils::UnprotectData(uchar const *,ulong,ulong,uchar * *,ulong *)
0x18001f3f3  lea     rcx, [rbp+var_18]
0x18001f3f7  mov     ebx, eax
0x18001f3f9  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001f3fe  test    ebx, ebx
0x18001f400  jns     short loc_18001F41C
0x18001f402  mov     rcx, [rbp+8]; this
0x18001f406  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001f40d  mov     r9d, ebx; char *
0x18001f410  mov     edx, 18h; void *
0x18001f415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f41a  jmp     short loc_18001F483
0x18001f41c  lea     rbx, [rdi+8]
0x18001f420  mov     rcx, [rbx]; hKey
0x18001f423  test    rcx, rcx
0x18001f426  jz      short loc_18001F435
0x18001f428  call    cs:__imp_BCryptDestroyKey
0x18001f42e  mov     qword ptr [rbx], 0
0x18001f435  mov     rcx, [rbp+var_20]
0x18001f439  xor     r9d, r9d; cbKeyObject
0x18001f43c  mov     eax, dword ptr [rbp+arg_18]
0x18001f43f  xor     r8d, r8d; pbKeyObject
0x18001f442  mov     [rsp+60h+dwFlags], 0; dwFlags
0x18001f44a  mov     rdx, rbx; phKey
0x18001f44d  mov     dword ptr [rsp+60h+cbSecret], eax; cbSecret
0x18001f451  mov     [rsp+60h+pbSecret], rcx; int
0x18001f456  mov     ecx, 341h; hAlgorithm
0x18001f45b  call    cs:__imp_BCryptGenerateSymmetricKey
0x18001f461  test    eax, eax
0x18001f463  jns     short loc_18001F481
0x18001f465  mov     rcx, [rbp+8]; this
0x18001f469  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001f470  mov     r9d, eax; char *
0x18001f473  mov     edx, 27h ; '''; void *
0x18001f478  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001f47d  mov     ebx, eax
0x18001f47f  jmp     short loc_18001F483
0x18001f481  xor     ebx, ebx
0x18001f483  xor     edx, edx
0x18001f485  lea     rcx, [rbp+var_20]
0x18001f489  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001f48e  mov     rdi, [rsp+60h+arg_8]
0x18001f493  mov     eax, ebx
0x18001f495  mov     rbx, [rsp+60h+arg_0]
0x18001f49a  add     rsp, 60h
0x18001f49e  pop     rbp
0x18001f49f  retn
```
