# TpmSymmetricPopKey::ImportKey(uchar *,ulong)

- ea: `0x18001e330`
- end: `0x18001e4e8`
- name: `?ImportKey@TpmSymmetricPopKey@@UEAAJPEAEK@Z`
- size: `440`
- prototype: `__int64 __fastcall(TpmSymmetricPopKey *this, unsigned __int8 *, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180004de0`
- `0x180006415`
- `0x18000b0fc`
- `0x18000dad8`
- `0x1800106cc`
- `0x18001070c`
- `0x180013270`
- `0x180014b18`
- `0x180014f80`
- `0x180014fc4`
- `0x18001e330`
- `0x18001e4f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e428`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e428`

## string_xrefs

- `0x18001e3b3`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\tpmsymmetricpopkey.cpp`
- `0x18001e458`: `onecore\ds\security\ngc\ngcpopkey\symmetricpopkey\tpmsymmetricpopkey.cpp`

## pseudocode

```c
__int64 __fastcall TpmSymmetricPopKey::ImportKey(TpmSymmetricPopKey *this, unsigned __int8 *a2, __int64 a3)
{
  int v4; // ebx
  __int64 v5; // rdx
  const unsigned __int16 *v6; // rdi
  int v7; // eax
  int v8; // ecx
  unsigned int v9; // eax
  unsigned int v10; // ecx
  void *v11; // rcx
  unsigned __int8 *v12; // r14
  __int64 v13; // rax
  int v15; // [rsp+20h] [rbp-50h]
  unsigned __int8 *v16; // [rsp+30h] [rbp-40h] BYREF
  const unsigned __int16 *v17; // [rsp+38h] [rbp-38h] BYREF
  const unsigned __int16 **v18; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v19[2]; // [rsp+48h] [rbp-28h] BYREF
  char v20; // [rsp+50h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  LODWORD(v16) = 0;
  v17 = 0;
  v18 = &v17;
  *(_QWORD *)v19 = 0;
  v20 = 1;
  v4 = NgcUtils::UnprotectData(a2, (const unsigned __int8 *)(unsigned int)a3, a3, (BYTE **)v19, &v16);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v18);
  if ( v4 < 0 )
  {
    v5 = 173;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\tpmsymmetricpopkey.cpp",
      (const char *)(unsigned int)v4,
      v15);
    goto LABEL_24;
  }
  if ( (unsigned int)v16 < 0xC )
  {
    v5 = 176;
LABEL_5:
    v4 = -2146893821;
    goto LABEL_6;
  }
  v6 = v17;
  if ( *(_DWORD *)v17 != 1 )
  {
    v5 = 177;
    goto LABEL_5;
  }
  v7 = *((_DWORD *)v17 + 1);
  if ( !v7 )
  {
    v5 = 178;
    goto LABEL_5;
  }
  v8 = *((_DWORD *)v17 + 2);
  if ( !v8 )
  {
    v5 = 179;
    goto LABEL_5;
  }
  v9 = v7 + 12;
  if ( v9 < 0xC )
  {
    v5 = 182;
    goto LABEL_5;
  }
  v10 = v9 + v8;
  if ( v10 < v9 )
  {
    v5 = 183;
    goto LABEL_5;
  }
  if ( v10 != (_DWORD)v16 )
  {
    v5 = 184;
    goto LABEL_5;
  }
  v11 = (void *)*((_QWORD *)this + 1);
  if ( v11 )
  {
    LocalFree(v11);
    *((_QWORD *)this + 1) = 0;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&v16, *((unsigned int *)v6 + 2));
  v12 = v16;
  if ( v16 )
  {
    memcpy_0(v16, (char *)v6 + *((unsigned int *)v6 + 1) + 12, *((unsigned int *)v6 + 2));
    v13 = std::wstring::wstring(&v18, v6 + 6);
    std::wstring::operator=((char *)this + 24, v13);
    std::wstring::_Tidy_deallocate(&v18);
    v16 = 0;
    *((_QWORD *)this + 1) = v12;
    *((_DWORD *)this + 4) = *((_DWORD *)v6 + 2);
    *((_BYTE *)this + 56) = IsMsaPerDeviceTpmTransportKey(v6 + 6);
    v4 = 0;
  }
  else
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\symmetricpopkey\\tpmsymmetricpopkey.cpp",
      (const char *)0x8007000ELL,
      v15);
  }
LABEL_24:
  wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v17, 0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001e330  push    rbp
0x18001e332  push    rbx
0x18001e333  push    rsi
0x18001e334  push    rdi
0x18001e335  push    r14
0x18001e337  mov     rbp, rsp
0x18001e33a  sub     rsp, 70h
0x18001e33e  mov     rax, cs:__security_cookie
0x18001e345  xor     rax, rsp
0x18001e348  mov     [rbp+var_10], rax
0x18001e34c  mov     rax, rdx
0x18001e34f  mov     rsi, rcx
0x18001e352  mov     dword ptr [rbp+var_40], 0
0x18001e359  mov     [rbp+var_38], 0
0x18001e361  lea     rcx, [rbp+var_38]
0x18001e365  mov     [rbp+var_30], rcx
0x18001e369  mov     qword ptr [rbp+var_28], 0
0x18001e371  mov     [rbp+var_20], 1
0x18001e375  lea     rcx, [rbp+var_40]
0x18001e379  mov     qword ptr [rsp+70h+var_50], rcx; int
0x18001e37e  lea     r9, [rbp+var_28]; unsigned int
0x18001e382  mov     edx, r8d; unsigned __int8 *
0x18001e385  mov     rcx, rax; this
0x18001e388  call    ?UnprotectData@NgcUtils@@YAJPEBEKKPEAPEAEPEAK@Z; NgcUtils::UnprotectData(uchar const *,ulong,ulong,uchar * *,ulong *)
0x18001e38d  mov     ebx, eax
0x18001e38f  lea     rcx, [rbp+var_30]
0x18001e393  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001e398  test    ebx, ebx
0x18001e39a  jns     short loc_18001E3A3
0x18001e39c  mov     edx, 0ADh
0x18001e3a1  jmp     short loc_18001E3B3
0x18001e3a3  cmp     dword ptr [rbp+var_40], 0Ch
0x18001e3a7  jnb     short loc_18001E3CB
0x18001e3a9  mov     edx, 0B0h; void *
0x18001e3ae  mov     ebx, 80090003h
0x18001e3b3  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001e3ba  mov     r9d, ebx; char *
0x18001e3bd  mov     rcx, [rbp+28h]; this
0x18001e3c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e3c6  jmp     loc_18001E4C4
0x18001e3cb  mov     rdi, [rbp+var_38]
0x18001e3cf  cmp     dword ptr [rdi], 1
0x18001e3d2  jz      short loc_18001E3DB
0x18001e3d4  mov     edx, 0B1h
0x18001e3d9  jmp     short loc_18001E3AE
0x18001e3db  mov     eax, [rdi+4]
0x18001e3de  test    eax, eax
0x18001e3e0  jnz     short loc_18001E3E9
0x18001e3e2  mov     edx, 0B2h
0x18001e3e7  jmp     short loc_18001E3AE
0x18001e3e9  mov     ecx, [rdi+8]
0x18001e3ec  test    ecx, ecx
0x18001e3ee  jnz     short loc_18001E3F7
0x18001e3f0  mov     edx, 0B3h
0x18001e3f5  jmp     short loc_18001E3AE
0x18001e3f7  add     eax, 0Ch
0x18001e3fa  cmp     eax, 0Ch
0x18001e3fd  jnb     short loc_18001E406
0x18001e3ff  mov     edx, 0B6h
0x18001e404  jmp     short loc_18001E3AE
0x18001e406  add     ecx, eax
0x18001e408  cmp     ecx, eax
0x18001e40a  jnb     short loc_18001E413
0x18001e40c  mov     edx, 0B7h
0x18001e411  jmp     short loc_18001E3AE
0x18001e413  cmp     ecx, dword ptr [rbp+var_40]
0x18001e416  jz      short loc_18001E41F
0x18001e418  mov     edx, 0B8h
0x18001e41d  jmp     short loc_18001E3AE
0x18001e41f  mov     rcx, [rsi+8]; hMem
0x18001e423  test    rcx, rcx
0x18001e426  jz      short loc_18001E436
0x18001e428  call    cs:__imp_LocalFree
0x18001e42e  mov     qword ptr [rsi+8], 0
0x18001e436  mov     edx, [rdi+8]
0x18001e439  lea     rcx, [rbp+var_40]
0x18001e43d  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18001e442  nop
0x18001e443  mov     r14, [rbp+var_40]
0x18001e447  test    r14, r14
0x18001e44a  jnz     short loc_18001E46C
0x18001e44c  mov     rcx, [rbp+28h]; this
0x18001e450  mov     ebx, 8007000Eh
0x18001e455  mov     r9d, ebx; char *
0x18001e458  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001e45f  mov     edx, 0C3h; void *
0x18001e464  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e469  nop
0x18001e46a  jmp     short loc_18001E4C4
0x18001e46c  mov     r8d, [rdi+8]; Size
0x18001e470  mov     edx, [rdi+4]
0x18001e473  add     rdx, 0Ch
0x18001e477  add     rdx, rdi; Src
0x18001e47a  mov     rcx, r14; void *
0x18001e47d  call    memcpy_0
0x18001e482  lea     rdx, [rdi+0Ch]
0x18001e486  lea     rcx, [rbp+var_30]
0x18001e48a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001e48f  lea     rcx, [rsi+18h]
0x18001e493  mov     rdx, rax
0x18001e496  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001e49b  lea     rcx, [rbp+var_30]
0x18001e49f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e4a4  mov     [rbp+var_40], 0
0x18001e4ac  mov     [rsi+8], r14
0x18001e4b0  mov     eax, [rdi+8]
0x18001e4b3  mov     [rsi+10h], eax
0x18001e4b6  lea     rcx, [rdi+0Ch]; unsigned __int16 *
0x18001e4ba  call    ?IsMsaPerDeviceTpmTransportKey@@YA_NPEBG@Z; IsMsaPerDeviceTpmTransportKey(ushort const *)
0x18001e4bf  mov     [rsi+38h], al
0x18001e4c2  xor     ebx, ebx
0x18001e4c4  xor     edx, edx
0x18001e4c6  lea     rcx, [rbp+var_38]
0x18001e4ca  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x18001e4cf  mov     eax, ebx
0x18001e4d1  mov     rcx, [rbp+var_10]
0x18001e4d5  xor     rcx, rsp; StackCookie
0x18001e4d8  call    __security_check_cookie
0x18001e4dd  add     rsp, 70h
0x18001e4e1  pop     r14
0x18001e4e3  pop     rdi
0x18001e4e4  pop     rsi
0x18001e4e5  pop     rbx
0x18001e4e6  pop     rbp
0x18001e4e7  retn
```
