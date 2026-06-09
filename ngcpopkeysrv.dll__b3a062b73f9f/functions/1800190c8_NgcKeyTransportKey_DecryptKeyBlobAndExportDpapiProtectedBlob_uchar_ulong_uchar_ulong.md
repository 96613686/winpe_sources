# NgcKeyTransportKey::DecryptKeyBlobAndExportDpapiProtectedBlob(uchar *,ulong,uchar * *,ulong *)

- ea: `0x1800190c8`
- end: `0x180019234`
- name: `?DecryptKeyBlobAndExportDpapiProtectedBlob@NgcKeyTransportKey@@QEAAJPEAEKPEAPEAEPEAK@Z`
- size: `364`
- prototype: `__int64 __fastcall(NgcKeyTransportKey *this, unsigned __int8 *, __int64, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800127d4`

## callees

- `0x180006415`
- `0x18000b0fc`
- `0x18000dad8`
- `0x18001070c`
- `0x180014828`
- `0x180018d9c`
- `0x1800190c8`
- `0x180028010`

## string_xrefs

- `0x180019133`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`
- `0x18001919b`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\keytranskeybase.cpp`

## pseudocode

```c
__int64 __fastcall NgcKeyTransportKey::DecryptKeyBlobAndExportDpapiProtectedBlob(
        NgcKeyTransportKey *this,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  __int64 v7; // rax
  int v8; // ebx
  unsigned int v9; // r8d
  unsigned int v10; // edi
  unsigned int v11; // esi
  unsigned __int8 *v12; // rbx
  int v14; // [rsp+20h] [rbp-58h]
  unsigned int *v15; // [rsp+28h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-48h] BYREF
  void *Src; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int8 *v18; // [rsp+40h] [rbp-38h] BYREF
  NgcUtils *v19; // [rsp+48h] [rbp-30h] BYREF
  void *p_Src; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v21[2]; // [rsp+58h] [rbp-20h] BYREF
  char v22; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]
  unsigned __int8 *v24; // [rsp+B0h] [rbp+38h] BYREF

  LODWORD(v24) = 0;
  v19 = 0;
  v7 = *(_QWORD *)this;
  p_Src = &v19;
  *(_QWORD *)v21 = 0;
  v22 = 1;
  v8 = (*(__int64 (__fastcall **)(NgcKeyTransportKey *, unsigned __int8 *, __int64, unsigned int *))(v7 + 48))(
         this,
         a2,
         a3,
         v21);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_Src);
  if ( v8 >= 0 )
  {
    LODWORD(Size) = 0;
    Src = 0;
    p_Src = &Src;
    *(_QWORD *)v21 = 0;
    v22 = 1;
    v8 = NgcUtils::ProtectData(
           v19,
           (const unsigned __int8 *)(unsigned int)v24,
           v9,
           (unsigned int)v21,
           (unsigned __int8 **)&Size,
           v15);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_Src);
    if ( v8 >= 0 )
    {
      v10 = Size;
      v11 = Size + 8;
      wil::make_unique_hlocal<unsigned char [0]>(&v18, (unsigned int)(Size + 8));
      v12 = v18;
      *(_DWORD *)v18 = 1;
      *((_DWORD *)v12 + 1) = (*(__int64 (__fastcall **)(NgcKeyTransportKey *))(*(_QWORD *)this + 16LL))(this);
      memcpy_0(v12 + 8, Src, v10);
      *a4 = v18;
      *a5 = v11;
      v18 = 0;
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &Src,
        0);
      v8 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13A,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
        (const char *)(unsigned int)v8,
        v14);
      wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &Src,
        0);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x131,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\keytranskeybase.cpp",
      (const char *)(unsigned int)v8,
      (int)&v24);
  }
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v19, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800190c8  push    rbp
0x1800190ca  push    rbx
0x1800190cb  push    rsi
0x1800190cc  push    rdi
0x1800190cd  push    r14
0x1800190cf  push    r15
0x1800190d1  mov     rbp, rsp
0x1800190d4  sub     rsp, 78h
0x1800190d8  mov     r15, r9
0x1800190db  mov     r14, rcx
0x1800190de  mov     dword ptr [rbp+arg_0], 0
0x1800190e5  mov     [rbp+var_30], 0
0x1800190ed  mov     rax, [rcx]
0x1800190f0  lea     rcx, [rbp+var_30]
0x1800190f4  mov     [rbp+var_28], rcx
0x1800190f8  mov     qword ptr [rbp+var_20], 0
0x180019100  mov     [rbp+var_18], 1
0x180019104  lea     rcx, [rbp+arg_0]
0x180019108  mov     [rsp+78h+var_58], rcx; int
0x18001910d  lea     r9, [rbp+var_20]
0x180019111  mov     rcx, r14
0x180019114  mov     rax, [rax+30h]
0x180019118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001911d  mov     ebx, eax
0x18001911f  lea     rcx, [rbp+var_28]
0x180019123  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180019128  test    ebx, ebx
0x18001912a  jns     short loc_180019149
0x18001912c  mov     rcx, [rbp+30h]; this
0x180019130  mov     r9d, ebx; char *
0x180019133  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001913a  mov     edx, 131h; void *
0x18001913f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019144  jmp     loc_18001921A
0x180019149  mov     dword ptr [rbp+Size], 0
0x180019150  mov     [rbp+Src], 0
0x180019158  lea     rax, [rbp+Src]
0x18001915c  mov     [rbp+var_28], rax
0x180019160  mov     qword ptr [rbp+var_20], 0
0x180019168  mov     [rbp+var_18], 1
0x18001916c  lea     rax, [rbp+Size]
0x180019170  mov     [rsp+78h+var_58], rax; int
0x180019175  lea     r9, [rbp+var_20]; unsigned int
0x180019179  mov     edx, dword ptr [rbp+arg_0]; unsigned __int8 *
0x18001917c  mov     rcx, [rbp+var_30]; this
0x180019180  call    ?ProtectData@NgcUtils@@YAJPEBEKKPEAPEAEPEAK@Z; NgcUtils::ProtectData(uchar const *,ulong,ulong,uchar * *,ulong *)
0x180019185  mov     ebx, eax
0x180019187  lea     rcx, [rbp+var_28]
0x18001918b  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180019190  test    ebx, ebx
0x180019192  jns     short loc_1800191BA
0x180019194  mov     rcx, [rbp+30h]; this
0x180019198  mov     r9d, ebx; char *
0x18001919b  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x1800191a2  mov     edx, 13Ah; void *
0x1800191a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800191ac  nop
0x1800191ad  xor     edx, edx
0x1800191af  lea     rcx, [rbp+Src]
0x1800191b3  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x1800191b8  jmp     short loc_18001921A
0x1800191ba  mov     edi, dword ptr [rbp+Size]
0x1800191bd  lea     esi, [rdi+8]
0x1800191c0  mov     edx, esi
0x1800191c2  lea     rcx, [rbp+var_38]
0x1800191c6  call    ??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<uchar [0]>(unsigned __int64)
0x1800191cb  nop
0x1800191cc  mov     rbx, [rbp+var_38]
0x1800191d0  mov     dword ptr [rbx], 1
0x1800191d6  mov     rax, [r14]
0x1800191d9  mov     rcx, r14
0x1800191dc  mov     rax, [rax+10h]
0x1800191e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191e5  mov     [rbx+4], eax
0x1800191e8  mov     r8d, edi; Size
0x1800191eb  lea     rcx, [rbx+8]; void *
0x1800191ef  mov     rdx, [rbp+Src]; Src
0x1800191f3  call    memcpy_0
0x1800191f8  mov     rax, [rbp+var_38]
0x1800191fc  mov     [r15], rax
0x1800191ff  mov     rax, [rbp+arg_20]
0x180019203  mov     [rax], esi
0x180019205  mov     [rbp+var_38], 0
0x18001920d  xor     edx, edx
0x18001920f  lea     rcx, [rbp+Src]
0x180019213  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180019218  xor     ebx, ebx
0x18001921a  xor     edx, edx
0x18001921c  lea     rcx, [rbp+var_30]
0x180019220  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180019225  mov     eax, ebx
0x180019227  add     rsp, 78h
0x18001922b  pop     r15
0x18001922d  pop     r14
0x18001922f  pop     rdi
0x180019230  pop     rsi
0x180019231  pop     rbx
0x180019232  pop     rbp
0x180019233  retn
```
