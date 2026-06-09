# NgcKeyTransportKey::GetKeyBlobForServer(uchar * *,ulong *)

- ea: `0x1800192ec`
- end: `0x1800193ce`
- name: `?GetKeyBlobForServer@NgcKeyTransportKey@@QEAAJPEAPEAEPEAK@Z`
- size: `226`
- prototype: `__int64 __fastcall(NCRYPT_KEY_HANDLE *this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800122c8`

## callees

- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x180013e3c`
- `0x1800192ec`
- `0x180028010`

## string_xrefs

- `0x18001937f`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcKeyTransportKey::GetKeyBlobForServer(
        NCRYPT_KEY_HANDLE *this,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  const WCHAR *v6; // rax
  int v7; // esi
  unsigned __int8 *v9; // rax
  int v10; // [rsp+20h] [rbp-30h]
  unsigned int *v11; // [rsp+28h] [rbp-28h]
  unsigned __int8 **v12; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v13[2]; // [rsp+38h] [rbp-18h] BYREF
  char v14; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned __int8 *v16; // [rsp+70h] [rbp+20h] BYREF
  unsigned __int8 *v17; // [rsp+88h] [rbp+38h] BYREF

  if ( this[1] )
  {
    LODWORD(v16) = 0;
    v17 = 0;
    v12 = &v17;
    *(_QWORD *)v13 = 0;
    v14 = 1;
    v6 = (const WCHAR *)(*(__int64 (__fastcall **)(NCRYPT_KEY_HANDLE *))(*this + 32))(this);
    v7 = NgcUtils::ExportNCryptKey(this[1], v6, 0, (unsigned int)v13, &v16, v11);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v12);
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
        (const char *)(unsigned int)v7,
        v10);
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v17,
        0);
      return (unsigned int)v7;
    }
    v9 = v17;
    v17 = 0;
    *a2 = v9;
    *a3 = (unsigned int)v16;
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v17, 0);
  }
  else
  {
    *a2 = 0;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800192ec  mov     [rsp-18h+arg_8], rbx
0x1800192f1  push    rbp
0x1800192f2  push    rsi
0x1800192f3  push    rdi
0x1800192f4  mov     rbp, rsp
0x1800192f7  sub     rsp, 50h
0x1800192fb  mov     rbx, r8
0x1800192fe  mov     rdi, rdx
0x180019301  mov     rsi, rcx
0x180019304  cmp     qword ptr [rcx+8], 0
0x180019309  jnz     short loc_18001931E
0x18001930b  mov     qword ptr [rdx], 0
0x180019312  mov     dword ptr [r8], 0
0x180019319  jmp     loc_1800193BF
0x18001931e  mov     dword ptr [rbp+arg_0], 0
0x180019325  mov     [rbp+arg_18], 0
0x18001932d  lea     rax, [rbp+arg_18]
0x180019331  mov     [rbp+var_20], rax
0x180019335  mov     qword ptr [rbp+var_18], 0
0x18001933d  mov     [rbp+var_10], 1
0x180019341  mov     rax, [rcx]
0x180019344  mov     rax, [rax+20h]
0x180019348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001934d  lea     rcx, [rbp+arg_0]
0x180019351  mov     [rsp+50h+var_30], rcx; int
0x180019356  lea     r9, [rbp+var_18]; unsigned int
0x18001935a  xor     r8d, r8d; dwFlags
0x18001935d  mov     rdx, rax; pszBlobType
0x180019360  mov     rcx, [rsi+8]; hKey
0x180019364  call    ?ExportNCryptKey@NgcUtils@@YAJ_KPEBGKPEAPEAEPEAK@Z; NgcUtils::ExportNCryptKey(unsigned __int64,ushort const *,ulong,uchar * *,ulong *)
0x180019369  mov     esi, eax
0x18001936b  lea     rcx, [rbp+var_20]
0x18001936f  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180019374  test    esi, esi
0x180019376  jns     short loc_1800193A0
0x180019378  mov     rcx, [rbp+18h]; this
0x18001937c  mov     r9d, esi; char *
0x18001937f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180019386  mov     edx, 40h ; '@'; void *
0x18001938b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019390  nop
0x180019391  xor     edx, edx
0x180019393  lea     rcx, [rbp+arg_18]
0x180019397  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001939c  mov     eax, esi
0x18001939e  jmp     short loc_1800193C1
0x1800193a0  mov     rax, [rbp+arg_18]
0x1800193a4  mov     [rbp+arg_18], 0
0x1800193ac  mov     [rdi], rax
0x1800193af  mov     eax, dword ptr [rbp+arg_0]
0x1800193b2  mov     [rbx], eax
0x1800193b4  xor     edx, edx
0x1800193b6  lea     rcx, [rbp+arg_18]
0x1800193ba  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x1800193bf  xor     eax, eax
0x1800193c1  mov     rbx, [rsp+50h+arg_8]
0x1800193c6  add     rsp, 50h
0x1800193ca  pop     rdi
0x1800193cb  pop     rsi
0x1800193cc  pop     rbp
0x1800193cd  retn
```
