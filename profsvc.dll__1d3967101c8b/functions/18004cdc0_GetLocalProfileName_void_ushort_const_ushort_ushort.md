# GetLocalProfileName(void *,ushort const *,ushort * *,ushort * *)

- ea: `0x18004cdc0`
- end: `0x18004d10a`
- name: `?GetLocalProfileName@@YAJPEAXPEBGPEAPEAG2@Z`
- size: `842`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ed00`
- `0x180043c70`

## callees

- `0x1800069d0`
- `0x1800080c8`
- `0x18000fa10`
- `0x1800111a0`
- `0x18001dc80`
- `0x18002d2d8`
- `0x18002f8e0`
- `0x18004cda4`
- `0x18004cdc0`
- `0x1800510f8`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18004ce18`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18004ce18`

## string_xrefs

- `0x18004ce4d`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18004ce9c`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18004cf0e`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18004d071`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18004d061`: `Cannot create the local profile directory name`
- `0x18004d0af`: `Cannot create the local profile directory name, giving up.`

## pseudocode

```c
__int64 __fastcall GetLocalProfileName(
        void *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  int BasicProfileFolderPathAlloc; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  unsigned __int16 *v13; // rbx
  int UserDomainName; // eax
  __int64 v15; // rdx
  int i; // edi
  unsigned __int64 v17; // r9
  unsigned __int64 v18; // r8
  __int64 v19; // rbx
  const char *v20; // rax
  __int64 v21; // rdx
  int v23; // [rsp+20h] [rbp-49h]
  const char *v24; // [rsp+28h] [rbp-41h]
  unsigned __int16 *v25; // [rsp+30h] [rbp-39h] BYREF
  __int64 v26; // [rsp+38h] [rbp-31h]
  __int64 v27; // [rsp+40h] [rbp-29h]
  unsigned __int16 *v28; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int64 v29; // [rsp+50h] [rbp-19h]
  __int64 v30; // [rsp+58h] [rbp-11h]
  unsigned __int16 *v31; // [rsp+60h] [rbp-9h] BYREF
  __int64 v32; // [rsp+68h] [rbp-1h]
  __int64 v33; // [rsp+70h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a3 = 0;
  *a4 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v28);
  v29 = -1;
  v30 = -1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(1, 0, &v28);
  v9 = BasicProfileFolderPathAlloc;
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    v10 = 430;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      v23);
    goto LABEL_41;
  }
  BasicProfileFolderPathAlloc = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
                                  &v28,
                                  L"\\%s",
                                  a2);
  v9 = BasicProfileFolderPathAlloc;
  if ( BasicProfileFolderPathAlloc < 0 )
  {
    v10 = 433;
    goto LABEL_5;
  }
  v25 = 0;
  v26 = 0;
  v27 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v25);
  v26 = -1;
  v27 = -1;
  v11 = ExpandEnvStringAlloc(0, v28, &v25);
  v9 = v11;
  if ( v11 < 0 )
  {
    v12 = 437;
    goto LABEL_8;
  }
  v13 = v25;
  if ( !DirectoryExists(v25) )
    goto LABEL_40;
  if ( a1 )
  {
    v31 = 0;
    v32 = 0;
    v33 = 0;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v31);
    v32 = -1;
    v33 = -1;
    UserDomainName = GetUserDomainName(a1, &v31);
    v9 = UserDomainName;
    if ( UserDomainName < 0 )
    {
      v15 = 446;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)(unsigned int)UserDomainName,
        v23);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v31);
      goto LABEL_9;
    }
    UserDomainName = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
                       &v28,
                       L".%s",
                       v31);
    v9 = UserDomainName;
    if ( UserDomainName < 0 )
    {
      v15 = 449;
      goto LABEL_14;
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v25);
    v26 = -1;
    v27 = -1;
    UserDomainName = ExpandEnvStringAlloc(0, v28, &v25);
    v9 = UserDomainName;
    if ( UserDomainName < 0 )
    {
      v15 = 452;
      goto LABEL_14;
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v31);
    v13 = v25;
  }
  for ( i = 0; ; ++i )
  {
    if ( !DirectoryExists(v13) || i >= 1000 )
    {
      if ( DirectoryExists(v13) )
      {
        v20 = "Cannot create the local profile directory name, giving up.";
        v21 = 471;
        goto LABEL_35;
      }
LABEL_40:
      *a3 = v28;
      *a4 = v13;
      v28 = 0;
      v30 = 0;
      v29 = 0;
      v25 = 0;
      v27 = 0;
      v26 = 0;
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v25);
      v9 = 0;
      goto LABEL_41;
    }
    if ( i <= 0 )
      goto LABEL_31;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_EnsureCount(&v28);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_EnsureCount(&v28);
    v18 = v29;
    if ( v17 >= v29 )
    {
      v20 = "Cannot create the local profile directory name";
      v21 = 461;
LABEL_35:
      v9 = -2147023728;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)0x80070490LL,
        (int)v20,
        v24);
      goto LABEL_9;
    }
    v19 = v29 - v17;
    if ( v29 - v17 > 4 )
    {
      v19 = 4;
LABEL_29:
      memmove_0(&v28[v17], &v28[v17 + v19], 2 * (v29 - v17 - v19));
      v18 = v29 - v19;
      v29 -= v19;
      goto LABEL_30;
    }
    if ( v19 )
      goto LABEL_29;
LABEL_30:
    v28[v18] = 0;
LABEL_31:
    v11 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
            &v28,
            L".%.3d",
            (unsigned int)i);
    v9 = v11;
    if ( v11 < 0 )
      break;
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v25);
    v26 = -1;
    v27 = -1;
    v11 = ExpandEnvStringAlloc(0, v28, &v25);
    v9 = v11;
    if ( v11 < 0 )
    {
      v12 = 467;
      goto LABEL_8;
    }
    v13 = v25;
  }
  v12 = 464;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
    (const char *)(unsigned int)v11,
    v23);
LABEL_9:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v25);
LABEL_41:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v28);
  return v9;
}

```

## disassembly

```asm
0x18004cdc0  push    rbp
0x18004cdc2  push    rbx
0x18004cdc3  push    rsi
0x18004cdc4  push    rdi
0x18004cdc5  push    r12
0x18004cdc7  push    r13
0x18004cdc9  push    r14
0x18004cdcb  push    r15
0x18004cdcd  lea     rbp, [rsp-1Fh]
0x18004cdd2  sub     rsp, 88h
0x18004cdd9  xor     r12d, r12d
0x18004cddc  mov     rdi, rcx
0x18004cddf  mov     [r8], r12
0x18004cde2  lea     rcx, [rbp+57h+var_78]
0x18004cde6  mov     [r9], r12
0x18004cde9  mov     r14, r9
0x18004cdec  mov     r15, r8
0x18004cdef  mov     [rbp+57h+var_78], r12
0x18004cdf3  mov     rsi, rdx
0x18004cdf6  mov     [rbp+57h+var_70], r12
0x18004cdfa  mov     [rbp+57h+var_68], r12
0x18004cdfe  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004ce03  xor     edx, edx
0x18004ce05  lea     r8, [rbp+57h+var_78]
0x18004ce09  or      r13, 0FFFFFFFFFFFFFFFFh
0x18004ce0d  mov     [rbp+57h+var_70], r13
0x18004ce11  mov     [rbp+57h+var_68], r13
0x18004ce15  lea     ecx, [rdx+1]
0x18004ce18  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x18004ce1e  mov     ebx, eax
0x18004ce20  test    eax, eax
0x18004ce22  jns     short loc_18004CE2B
0x18004ce24  mov     edx, 1AEh
0x18004ce29  jmp     short loc_18004CE49
0x18004ce2b  mov     r8, rsi
0x18004ce2e  lea     rdx, aS_1; "\\%s"
0x18004ce35  lea     rcx, [rbp+57h+var_78]
0x18004ce39  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18004ce3e  mov     ebx, eax
0x18004ce40  test    eax, eax
0x18004ce42  jns     short loc_18004CE61
0x18004ce44  mov     edx, 1B1h; void *
0x18004ce49  mov     rcx, [rbp+5Fh]; this
0x18004ce4d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004ce54  mov     r9d, eax; char *
0x18004ce57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ce5c  jmp     loc_18004D0EB
0x18004ce61  lea     rcx, [rbp+57h+var_90]
0x18004ce65  mov     [rbp+57h+var_90], r12
0x18004ce69  mov     [rbp+57h+var_88], r12
0x18004ce6d  mov     [rbp+57h+var_80], r12
0x18004ce71  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004ce76  mov     rdx, [rbp+57h+var_78]; unsigned __int16 *
0x18004ce7a  lea     r8, [rbp+57h+var_90]; unsigned __int16 **
0x18004ce7e  xor     ecx, ecx; void *
0x18004ce80  mov     [rbp+57h+var_88], r13
0x18004ce84  mov     [rbp+57h+var_80], r13
0x18004ce88  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x18004ce8d  mov     ebx, eax
0x18004ce8f  test    eax, eax
0x18004ce91  jns     short loc_18004CEB9
0x18004ce93  mov     edx, 1B5h; void *
0x18004ce98  mov     rcx, [rbp+5Fh]; this
0x18004ce9c  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004cea3  mov     r9d, eax; char *
0x18004cea6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ceab  lea     rcx, [rbp+57h+var_90]
0x18004ceaf  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004ceb4  jmp     loc_18004D0EB
0x18004ceb9  mov     rbx, [rbp+57h+var_90]
0x18004cebd  mov     rcx, rbx; unsigned __int16 *
0x18004cec0  call    ?DirectoryExists@@YA_NPEBG@Z; DirectoryExists(ushort const *)
0x18004cec5  test    al, al
0x18004cec7  jz      loc_18004D0BD
0x18004cecd  test    rdi, rdi
0x18004ced0  jz      loc_18004CF83
0x18004ced6  lea     rcx, [rbp+57h+var_60]
0x18004ceda  mov     [rbp+57h+var_60], r12
0x18004cede  mov     [rbp+57h+var_58], r12
0x18004cee2  mov     [rbp+57h+var_50], r12
0x18004cee6  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004ceeb  lea     rdx, [rbp+57h+var_60]; unsigned __int16 **
0x18004ceef  mov     [rbp+57h+var_58], r13
0x18004cef3  mov     rcx, rdi; void *
0x18004cef6  mov     [rbp+57h+var_50], r13
0x18004cefa  call    ?GetUserDomainName@@YAJPEAXPEAPEAG@Z; GetUserDomainName(void *,ushort * *)
0x18004ceff  mov     ebx, eax
0x18004cf01  test    eax, eax
0x18004cf03  jns     short loc_18004CF28
0x18004cf05  mov     edx, 1BEh; void *
0x18004cf0a  mov     rcx, [rbp+5Fh]; this
0x18004cf0e  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004cf15  mov     r9d, eax; char *
0x18004cf18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cf1d  lea     rcx, [rbp+57h+var_60]
0x18004cf21  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004cf26  jmp     short loc_18004CEAB
0x18004cf28  mov     r8, [rbp+57h+var_60]
0x18004cf2c  lea     rdx, aS; ".%s"
0x18004cf33  lea     rcx, [rbp+57h+var_78]
0x18004cf37  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18004cf3c  mov     ebx, eax
0x18004cf3e  test    eax, eax
0x18004cf40  jns     short loc_18004CF49
0x18004cf42  mov     edx, 1C1h
0x18004cf47  jmp     short loc_18004CF0A
0x18004cf49  lea     rcx, [rbp+57h+var_90]
0x18004cf4d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004cf52  mov     rdx, [rbp+57h+var_78]; unsigned __int16 *
0x18004cf56  lea     r8, [rbp+57h+var_90]; unsigned __int16 **
0x18004cf5a  xor     ecx, ecx; void *
0x18004cf5c  mov     [rbp+57h+var_88], r13
0x18004cf60  mov     [rbp+57h+var_80], r13
0x18004cf64  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x18004cf69  mov     ebx, eax
0x18004cf6b  test    eax, eax
0x18004cf6d  jns     short loc_18004CF76
0x18004cf6f  mov     edx, 1C4h
0x18004cf74  jmp     short loc_18004CF0A
0x18004cf76  lea     rcx, [rbp+57h+var_60]
0x18004cf7a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004cf7f  mov     rbx, [rbp+57h+var_90]
0x18004cf83  mov     edi, r12d
0x18004cf86  mov     rcx, rbx; unsigned __int16 *
0x18004cf89  call    ?DirectoryExists@@YA_NPEBG@Z; DirectoryExists(ushort const *)
0x18004cf8e  test    al, al
0x18004cf90  jz      loc_18004D0A3
0x18004cf96  cmp     edi, 3E8h
0x18004cf9c  jge     loc_18004D0A3
0x18004cfa2  test    edi, edi
0x18004cfa4  jle     short loc_18004D017
0x18004cfa6  lea     rcx, [rbp+57h+var_78]
0x18004cfaa  call    ?_EnsureCount@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_EnsureCount(void)
0x18004cfaf  mov     r9, [rbp+57h+var_70]
0x18004cfb3  lea     rcx, [rbp+57h+var_78]
0x18004cfb7  add     r9, 0FFFFFFFFFFFFFFFCh
0x18004cfbb  call    ?_EnsureCount@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_EnsureCount(void)
0x18004cfc0  mov     r8, [rbp+57h+var_70]
0x18004cfc4  cmp     r9, r8
0x18004cfc7  jnb     loc_18004D061
0x18004cfcd  mov     rbx, r8
0x18004cfd0  sub     rbx, r9
0x18004cfd3  cmp     rbx, 4
0x18004cfd7  ja      short loc_18004CFE0
0x18004cfd9  test    rbx, rbx
0x18004cfdc  jz      short loc_18004D00E
0x18004cfde  jmp     short loc_18004CFE5
0x18004cfe0  mov     ebx, 4
0x18004cfe5  mov     rcx, [rbp+57h+var_78]
0x18004cfe9  lea     rax, [r9+rbx]
0x18004cfed  sub     r8, r9
0x18004cff0  sub     r8, rbx
0x18004cff3  add     r8, r8; Size
0x18004cff6  lea     rdx, [rcx+rax*2]; Src
0x18004cffa  lea     rcx, [rcx+r9*2]; void *
0x18004cffe  call    memmove_0
0x18004d003  mov     r8, [rbp+57h+var_70]
0x18004d007  sub     r8, rbx
0x18004d00a  mov     [rbp+57h+var_70], r8
0x18004d00e  mov     rax, [rbp+57h+var_78]
0x18004d012  mov     [rax+r8*2], r12w
0x18004d017  mov     r8d, edi
0x18004d01a  lea     rdx, a3d; ".%.3d"
0x18004d021  lea     rcx, [rbp+57h+var_78]
0x18004d025  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18004d02a  mov     ebx, eax
0x18004d02c  test    eax, eax
0x18004d02e  js      short loc_18004D099
0x18004d030  lea     rcx, [rbp+57h+var_90]
0x18004d034  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004d039  mov     rdx, [rbp+57h+var_78]; unsigned __int16 *
0x18004d03d  lea     r8, [rbp+57h+var_90]; unsigned __int16 **
0x18004d041  xor     ecx, ecx; void *
0x18004d043  mov     [rbp+57h+var_88], r13
0x18004d047  mov     [rbp+57h+var_80], r13
0x18004d04b  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x18004d050  mov     ebx, eax
0x18004d052  test    eax, eax
0x18004d054  js      short loc_18004D08F
0x18004d056  mov     rbx, [rbp+57h+var_90]
0x18004d05a  inc     edi
0x18004d05c  jmp     loc_18004CF86
0x18004d061  lea     rax, aCannotCreateTh; "Cannot create the local profile directo"...
0x18004d068  mov     edx, 1CDh; void *
0x18004d06d  mov     rcx, [rbp+5Fh]; this
0x18004d071  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004d078  mov     ebx, 80070490h
0x18004d07d  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004d082  mov     r9d, ebx; char *
0x18004d085  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004d08a  jmp     loc_18004CEAB
0x18004d08f  mov     edx, 1D3h
0x18004d094  jmp     loc_18004CE98
0x18004d099  mov     edx, 1D0h
0x18004d09e  jmp     loc_18004CE98
0x18004d0a3  mov     rcx, rbx; unsigned __int16 *
0x18004d0a6  call    ?DirectoryExists@@YA_NPEBG@Z; DirectoryExists(ushort const *)
0x18004d0ab  test    al, al
0x18004d0ad  jz      short loc_18004D0BD
0x18004d0af  lea     rax, aCannotCreateTh_0; "Cannot create the local profile directo"...
0x18004d0b6  mov     edx, 1D7h
0x18004d0bb  jmp     short loc_18004D06D
0x18004d0bd  mov     rax, [rbp+57h+var_78]
0x18004d0c1  lea     rcx, [rbp+57h+var_90]
0x18004d0c5  mov     [r15], rax
0x18004d0c8  mov     [r14], rbx
0x18004d0cb  mov     [rbp+57h+var_78], r12
0x18004d0cf  mov     [rbp+57h+var_68], r12
0x18004d0d3  mov     [rbp+57h+var_70], r12
0x18004d0d7  mov     [rbp+57h+var_90], r12
0x18004d0db  mov     [rbp+57h+var_80], r12
0x18004d0df  mov     [rbp+57h+var_88], r12
0x18004d0e3  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004d0e8  mov     ebx, r12d
0x18004d0eb  lea     rcx, [rbp+57h+var_78]
0x18004d0ef  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004d0f4  mov     eax, ebx
0x18004d0f6  add     rsp, 88h
0x18004d0fd  pop     r15
0x18004d0ff  pop     r14
0x18004d101  pop     r13
0x18004d103  pop     r12
0x18004d105  pop     rdi
0x18004d106  pop     rsi
0x18004d107  pop     rbx
0x18004d108  pop     rbp
0x18004d109  retn
```
