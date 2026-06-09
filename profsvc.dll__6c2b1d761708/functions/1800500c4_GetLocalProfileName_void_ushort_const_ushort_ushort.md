# GetLocalProfileName(void *,ushort const *,ushort * *,ushort * *)

- ea: `0x1800500c4`
- end: `0x180050415`
- name: `?GetLocalProfileName@@YAJPEAXPEBGPEAPEAG2@Z`
- size: `849`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030050`
- `0x180045750`

## callees

- `0x180005c80`
- `0x18000dc10`
- `0x18000e1a0`
- `0x180010b10`
- `0x180021cf0`
- `0x180030ad0`
- `0x180035860`
- `0x1800500a0`
- `0x1800500c4`
- `0x180054128`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18005011c`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18005011c`

## string_xrefs

- `0x180050157`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800501a6`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180050218`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18005037b`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18005036b`: `Cannot create the local profile directory name`
- `0x1800503b9`: `Cannot create the local profile directory name, giving up.`

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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v28);
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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v25);
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
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v31);
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v31);
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
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v25);
    v26 = -1;
    v27 = -1;
    UserDomainName = ExpandEnvStringAlloc(0, v28, &v25);
    v9 = UserDomainName;
    if ( UserDomainName < 0 )
    {
      v15 = 452;
      goto LABEL_14;
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v31);
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v25);
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
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v25);
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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v25);
LABEL_41:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v28);
  return v9;
}

```

## disassembly

```asm
0x1800500c4  push    rbp
0x1800500c6  push    rbx
0x1800500c7  push    rsi
0x1800500c8  push    rdi
0x1800500c9  push    r12
0x1800500cb  push    r13
0x1800500cd  push    r14
0x1800500cf  push    r15
0x1800500d1  lea     rbp, [rsp-1Fh]
0x1800500d6  sub     rsp, 88h
0x1800500dd  xor     r12d, r12d
0x1800500e0  mov     rdi, rcx
0x1800500e3  mov     [r8], r12
0x1800500e6  lea     rcx, [rbp+57h+var_78]
0x1800500ea  mov     [r9], r12
0x1800500ed  mov     r14, r9
0x1800500f0  mov     r15, r8
0x1800500f3  mov     [rbp+57h+var_78], r12
0x1800500f7  mov     rsi, rdx
0x1800500fa  mov     [rbp+57h+var_70], r12
0x1800500fe  mov     [rbp+57h+var_68], r12
0x180050102  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180050107  xor     edx, edx
0x180050109  lea     r8, [rbp+57h+var_78]
0x18005010d  or      r13, 0FFFFFFFFFFFFFFFFh
0x180050111  mov     [rbp+57h+var_70], r13
0x180050115  mov     [rbp+57h+var_68], r13
0x180050119  lea     ecx, [rdx+1]
0x18005011c  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x180050123  nop     dword ptr [rax+rax+00h]
0x180050128  mov     ebx, eax
0x18005012a  test    eax, eax
0x18005012c  jns     short loc_180050135
0x18005012e  mov     edx, 1AEh
0x180050133  jmp     short loc_180050153
0x180050135  mov     r8, rsi
0x180050138  lea     rdx, aS_1; "\\%s"
0x18005013f  lea     rcx, [rbp+57h+var_78]
0x180050143  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180050148  mov     ebx, eax
0x18005014a  test    eax, eax
0x18005014c  jns     short loc_18005016B
0x18005014e  mov     edx, 1B1h; void *
0x180050153  mov     rcx, [rbp+5Fh]; this
0x180050157  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18005015e  mov     r9d, eax; char *
0x180050161  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050166  jmp     loc_1800503F5
0x18005016b  lea     rcx, [rbp+57h+var_90]
0x18005016f  mov     [rbp+57h+var_90], r12
0x180050173  mov     [rbp+57h+var_88], r12
0x180050177  mov     [rbp+57h+var_80], r12
0x18005017b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180050180  mov     rdx, [rbp+57h+var_78]; unsigned __int16 *
0x180050184  lea     r8, [rbp+57h+var_90]; unsigned __int16 **
0x180050188  xor     ecx, ecx; void *
0x18005018a  mov     [rbp+57h+var_88], r13
0x18005018e  mov     [rbp+57h+var_80], r13
0x180050192  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x180050197  mov     ebx, eax
0x180050199  test    eax, eax
0x18005019b  jns     short loc_1800501C3
0x18005019d  mov     edx, 1B5h; void *
0x1800501a2  mov     rcx, [rbp+5Fh]; this
0x1800501a6  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800501ad  mov     r9d, eax; char *
0x1800501b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800501b5  lea     rcx, [rbp+57h+var_90]
0x1800501b9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800501be  jmp     loc_1800503F5
0x1800501c3  mov     rbx, [rbp+57h+var_90]
0x1800501c7  mov     rcx, rbx; unsigned __int16 *
0x1800501ca  call    ?DirectoryExists@@YA_NPEBG@Z; DirectoryExists(ushort const *)
0x1800501cf  test    al, al
0x1800501d1  jz      loc_1800503C7
0x1800501d7  test    rdi, rdi
0x1800501da  jz      loc_18005028D
0x1800501e0  lea     rcx, [rbp+57h+var_60]
0x1800501e4  mov     [rbp+57h+var_60], r12
0x1800501e8  mov     [rbp+57h+var_58], r12
0x1800501ec  mov     [rbp+57h+var_50], r12
0x1800501f0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800501f5  lea     rdx, [rbp+57h+var_60]; unsigned __int16 **
0x1800501f9  mov     [rbp+57h+var_58], r13
0x1800501fd  mov     rcx, rdi; void *
0x180050200  mov     [rbp+57h+var_50], r13
0x180050204  call    ?GetUserDomainName@@YAJPEAXPEAPEAG@Z; GetUserDomainName(void *,ushort * *)
0x180050209  mov     ebx, eax
0x18005020b  test    eax, eax
0x18005020d  jns     short loc_180050232
0x18005020f  mov     edx, 1BEh; void *
0x180050214  mov     rcx, [rbp+5Fh]; this
0x180050218  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18005021f  mov     r9d, eax; char *
0x180050222  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050227  lea     rcx, [rbp+57h+var_60]
0x18005022b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180050230  jmp     short loc_1800501B5
0x180050232  mov     r8, [rbp+57h+var_60]
0x180050236  lea     rdx, aS; ".%s"
0x18005023d  lea     rcx, [rbp+57h+var_78]
0x180050241  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180050246  mov     ebx, eax
0x180050248  test    eax, eax
0x18005024a  jns     short loc_180050253
0x18005024c  mov     edx, 1C1h
0x180050251  jmp     short loc_180050214
0x180050253  lea     rcx, [rbp+57h+var_90]
0x180050257  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18005025c  mov     rdx, [rbp+57h+var_78]; unsigned __int16 *
0x180050260  lea     r8, [rbp+57h+var_90]; unsigned __int16 **
0x180050264  xor     ecx, ecx; void *
0x180050266  mov     [rbp+57h+var_88], r13
0x18005026a  mov     [rbp+57h+var_80], r13
0x18005026e  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x180050273  mov     ebx, eax
0x180050275  test    eax, eax
0x180050277  jns     short loc_180050280
0x180050279  mov     edx, 1C4h
0x18005027e  jmp     short loc_180050214
0x180050280  lea     rcx, [rbp+57h+var_60]
0x180050284  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180050289  mov     rbx, [rbp+57h+var_90]
0x18005028d  mov     edi, r12d
0x180050290  mov     rcx, rbx; unsigned __int16 *
0x180050293  call    ?DirectoryExists@@YA_NPEBG@Z; DirectoryExists(ushort const *)
0x180050298  test    al, al
0x18005029a  jz      loc_1800503AD
0x1800502a0  cmp     edi, 3E8h
0x1800502a6  jge     loc_1800503AD
0x1800502ac  test    edi, edi
0x1800502ae  jle     short loc_180050321
0x1800502b0  lea     rcx, [rbp+57h+var_78]
0x1800502b4  call    ?_EnsureCount@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_EnsureCount(void)
0x1800502b9  mov     r9, [rbp+57h+var_70]
0x1800502bd  lea     rcx, [rbp+57h+var_78]
0x1800502c1  add     r9, 0FFFFFFFFFFFFFFFCh
0x1800502c5  call    ?_EnsureCount@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_EnsureCount(void)
0x1800502ca  mov     r8, [rbp+57h+var_70]
0x1800502ce  cmp     r9, r8
0x1800502d1  jnb     loc_18005036B
0x1800502d7  mov     rbx, r8
0x1800502da  sub     rbx, r9
0x1800502dd  cmp     rbx, 4
0x1800502e1  ja      short loc_1800502EA
0x1800502e3  test    rbx, rbx
0x1800502e6  jz      short loc_180050318
0x1800502e8  jmp     short loc_1800502EF
0x1800502ea  mov     ebx, 4
0x1800502ef  mov     rcx, [rbp+57h+var_78]
0x1800502f3  lea     rax, [r9+rbx]
0x1800502f7  sub     r8, r9
0x1800502fa  sub     r8, rbx
0x1800502fd  add     r8, r8; Size
0x180050300  lea     rdx, [rcx+rax*2]; Src
0x180050304  lea     rcx, [rcx+r9*2]; void *
0x180050308  call    memmove_0
0x18005030d  mov     r8, [rbp+57h+var_70]
0x180050311  sub     r8, rbx
0x180050314  mov     [rbp+57h+var_70], r8
0x180050318  mov     rax, [rbp+57h+var_78]
0x18005031c  mov     [rax+r8*2], r12w
0x180050321  mov     r8d, edi
0x180050324  lea     rdx, a3d; ".%.3d"
0x18005032b  lea     rcx, [rbp+57h+var_78]
0x18005032f  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180050334  mov     ebx, eax
0x180050336  test    eax, eax
0x180050338  js      short loc_1800503A3
0x18005033a  lea     rcx, [rbp+57h+var_90]
0x18005033e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180050343  mov     rdx, [rbp+57h+var_78]; unsigned __int16 *
0x180050347  lea     r8, [rbp+57h+var_90]; unsigned __int16 **
0x18005034b  xor     ecx, ecx; void *
0x18005034d  mov     [rbp+57h+var_88], r13
0x180050351  mov     [rbp+57h+var_80], r13
0x180050355  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x18005035a  mov     ebx, eax
0x18005035c  test    eax, eax
0x18005035e  js      short loc_180050399
0x180050360  mov     rbx, [rbp+57h+var_90]
0x180050364  inc     edi
0x180050366  jmp     loc_180050290
0x18005036b  lea     rax, aCannotCreateTh; "Cannot create the local profile directo"...
0x180050372  mov     edx, 1CDh; void *
0x180050377  mov     rcx, [rbp+5Fh]; this
0x18005037b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180050382  mov     ebx, 80070490h
0x180050387  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18005038c  mov     r9d, ebx; char *
0x18005038f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180050394  jmp     loc_1800501B5
0x180050399  mov     edx, 1D3h
0x18005039e  jmp     loc_1800501A2
0x1800503a3  mov     edx, 1D0h
0x1800503a8  jmp     loc_1800501A2
0x1800503ad  mov     rcx, rbx; unsigned __int16 *
0x1800503b0  call    ?DirectoryExists@@YA_NPEBG@Z; DirectoryExists(ushort const *)
0x1800503b5  test    al, al
0x1800503b7  jz      short loc_1800503C7
0x1800503b9  lea     rax, aCannotCreateTh_0; "Cannot create the local profile directo"...
0x1800503c0  mov     edx, 1D7h
0x1800503c5  jmp     short loc_180050377
0x1800503c7  mov     rax, [rbp+57h+var_78]
0x1800503cb  lea     rcx, [rbp+57h+var_90]
0x1800503cf  mov     [r15], rax
0x1800503d2  mov     [r14], rbx
0x1800503d5  mov     [rbp+57h+var_78], r12
0x1800503d9  mov     [rbp+57h+var_68], r12
0x1800503dd  mov     [rbp+57h+var_70], r12
0x1800503e1  mov     [rbp+57h+var_90], r12
0x1800503e5  mov     [rbp+57h+var_80], r12
0x1800503e9  mov     [rbp+57h+var_88], r12
0x1800503ed  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800503f2  mov     ebx, r12d
0x1800503f5  lea     rcx, [rbp+57h+var_78]
0x1800503f9  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800503fe  mov     eax, ebx
0x180050400  add     rsp, 88h
0x180050407  pop     r15
0x180050409  pop     r14
0x18005040b  pop     r13
0x18005040d  pop     r12
0x18005040f  pop     rdi
0x180050410  pop     rsi
0x180050411  pop     rbx
0x180050412  pop     rbp
0x180050413  retn
```
