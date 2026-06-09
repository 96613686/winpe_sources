# CreateDirectoryJunctionsForSystemWorker(void)

- ea: `0x18000feb0`
- end: `0x18001037d`
- name: `?CreateDirectoryJunctionsForSystemWorker@@YAJXZ`
- size: `1229`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004594`
- `0x18000ad78`
- `0x18000c440`
- `0x18000eed0`
- `0x18000ef6c`
- `0x18000f4fc`
- `0x18000f9f8`
- `0x18000feb0`
- `0x18001054c`
- `0x180011748`
- `0x180011810`
- `0x18001b914`
- `0x18001cb60`
- `0x18001cdac`
- `0x18001ce58`
- `0x18001d050`
- `0x180022830`

## import_xrefs

- `USERENV!__imp_CreateDirectoryJunctionsForUserProfile` at `0x18000ff41`
- `USERENV!__imp_CreateDirectoryJunctionsForUserProfile` at `0x18000ff41`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18000ff0f`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18000ff92`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18000ffc5`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18000ff0f`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18000ff92`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18000ffc5`

## string_xrefs

- `0x18000ff1f`: `onecore\ds\security\gina\profile\profext\dirjunc.cpp`
- `0x18001007c`: `CommonFilesDir`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CreateDirectoryJunctionsForSystemWorker(void)
{
  unsigned __int64 v0; // rdi
  int BasicProfileFolderPathAlloc; // eax
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // r9
  const unsigned __int16 *v6; // rsi
  unsigned __int64 v7; // rbx
  int v8; // eax
  unsigned int v9; // r14d
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int16 *v14; // rbx
  int v15; // eax
  int v16; // esi
  int v17; // eax
  unsigned int i; // edi
  int v19; // eax
  int SymLink; // eax
  wil::details::in1diag3 *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rdx
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpFileName[3]; // [rsp+30h] [rbp-D0h] BYREF
  char v28[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v29[16]; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hEvent; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v33[3]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v34[3]; // [rsp+90h] [rbp-70h] BYREF
  char v35[8]; // [rsp+A8h] [rbp-58h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v37[3]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v38; // [rsp+D8h] [rbp-28h] BYREF
  char v39[24]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v40[3]; // [rsp+108h] [rbp+8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  hEvent = 0;
  v31 = 0;
  v32 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&hEvent);
  v0 = -1;
  v31 = -1;
  v32 = -1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(2, 0, &hEvent);
  if ( BasicProfileFolderPathAlloc >= 0 )
    CreateDirectoryJunctionsForUserProfile(hEvent);
  else
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      v25);
  `eh vector constructor iterator'(
    v34,
    0x18u,
    6u,
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>,
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::~NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v35);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v2 = GetBasicProfileFolderPathAlloc(1, 0, v35);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 195;
LABEL_8:
    v5 = (unsigned int)v2;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
      (const char *)v5,
      v26);
    goto LABEL_59;
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v37);
  v37[1] = (unsigned __int16 *)-1LL;
  v37[2] = (unsigned __int16 *)-1LL;
  v2 = GetBasicProfileFolderPathAlloc(4, 0, v37);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 196;
    goto LABEL_8;
  }
  v6 = v37[0];
  if ( v37[0] )
  {
    v7 = -1;
    do
      ++v7;
    while ( v37[0][v7] );
    if ( v7 > 2 )
      v7 = 2;
    v8 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_EnsureCapacity(
           v34,
           2);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC7,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
        (const char *)(unsigned int)v8,
        v26);
      v3 = v9;
      goto LABEL_59;
    }
    StringCchCopyNW(v34[0], 3u, v6, v7);
    v34[1] = (unsigned __int16 *)v7;
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v34);
  }
  if ( v34[0][1] != 58 )
  {
    v3 = -2147418113;
    v5 = 2147549183LL;
    v4 = 200;
    goto LABEL_9;
  }
  v2 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
         v39,
         v10,
         v11,
         L"CommonFilesDir");
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 202;
    goto LABEL_8;
  }
  v2 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
         &v38,
         v12,
         v13,
         L"ProgramFilesDir");
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 203;
    goto LABEL_8;
  }
  v14 = v38;
  if ( v38[1] != 58 )
  {
    v3 = -2147418113;
    v5 = 2147549183LL;
    v4 = 204;
    goto LABEL_9;
  }
  if ( !v38 )
  {
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v40);
    goto LABEL_36;
  }
  do
    ++v0;
  while ( v38[v0] );
  if ( v0 > 2 )
    v0 = 2;
  v15 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_EnsureCapacity(
          v40,
          2);
  v16 = v15;
  if ( v15 >= 0 )
  {
    StringCchCopyNW(v40[0], 3u, v14, v0);
    v40[1] = (unsigned __int16 *)v0;
LABEL_36:
    CSystemACLApplicator::CSystemACLApplicator((CSystemACLApplicator *)v28);
    v17 = CSystemACLApplicator::Init((CSystemACLApplicator *)v28);
    v3 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD2,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
        (const char *)(unsigned int)v17,
        v26);
      wil::unique_any_array_ptr<unsigned char,std::default_delete<unsigned char [0]>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<unsigned char,std::default_delete<unsigned char [0]>,wil::empty_deleter,unsigned __int64>(v29);
      goto LABEL_59;
    }
    for ( i = 0; ; ++i )
    {
      if ( i >= 0x11 )
      {
        wil::unique_any_array_ptr<unsigned char,std::default_delete<unsigned char [0]>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<unsigned char,std::default_delete<unsigned char [0]>,wil::empty_deleter,unsigned __int64>(v29);
        v3 = 0;
        goto LABEL_59;
      }
      memset(lpFileName, 0, sizeof(lpFileName));
      v16 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
              lpFileName,
              L"%s%s",
              v34[3 * dword_1800311F4[10 * i]],
              (&off_1800311F8)[5 * i]);
      if ( v16 < 0 )
      {
        v23 = 215;
        goto LABEL_56;
      }
      v16 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Concat(
              lpFileName,
              &_ImageBase);
      if ( v16 < 0 )
      {
        v23 = 216;
LABEL_56:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
          (const char *)(unsigned int)v16,
          v26);
        goto LABEL_57;
      }
      memset(v33, 0, sizeof(v33));
      v19 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
              v33,
              L"%s%s",
              v34[3 * dword_180031204[10 * i]],
              (&off_180031208)[5 * i]);
      v16 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDB,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
          (const char *)(unsigned int)v19,
          v26);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v33);
LABEL_57:
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
        wil::unique_any_array_ptr<unsigned char,std::default_delete<unsigned char [0]>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<unsigned char,std::default_delete<unsigned char [0]>,wil::empty_deleter,unsigned __int64>(v29);
        goto LABEL_34;
      }
      if ( byte_1800311F0[40 * i] )
      {
        SymLink = CreateSymLink(lpFileName[0], v33[0], (const struct CAACLApplicator *)v28);
        if ( SymLink != -2147024713 )
        {
          v21 = retaddr;
          if ( SymLink < 0 )
          {
            v22 = 226;
LABEL_51:
            wil::details::in1diag3::_Log_Hr(
              v21,
              (void *)v22,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
              (const char *)(unsigned int)SymLink,
              v26);
          }
        }
      }
      else
      {
        SymLink = CreateDirectoryJunction(
                    (char *)lpFileName[0],
                    v33[0],
                    v33[0],
                    (const struct CAACLApplicator *)v28,
                    0,
                    *(&off_180031210 + 5 * i));
        if ( SymLink != -2147024713 && SymLink != -2147024893 )
        {
          v21 = retaddr;
          if ( SymLink < 0 )
          {
            v22 = 235;
            goto LABEL_51;
          }
        }
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v33);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpFileName);
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCF,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
    (const char *)(unsigned int)v15,
    v26);
LABEL_34:
  v3 = v16;
LABEL_59:
  `eh vector destructor iterator'(
    v34,
    0x18u,
    6u,
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::~NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&hEvent);
  return v3;
}

```

## disassembly

```asm
0x18000feb0  push    rbp
0x18000feb2  push    rbx
0x18000feb3  push    rsi
0x18000feb4  push    rdi
0x18000feb5  push    r12
0x18000feb7  push    r13
0x18000feb9  push    r14
0x18000febb  push    r15
0x18000febd  lea     rbp, [rsp-38h]
0x18000fec2  sub     rsp, 138h
0x18000fec9  mov     rax, cs:__security_cookie
0x18000fed0  xor     rax, rsp
0x18000fed3  mov     [rbp+70h+var_50], rax
0x18000fed7  xor     r15d, r15d
0x18000feda  mov     [rsp+170h+hEvent], r15
0x18000fedf  mov     [rsp+170h+var_108], r15
0x18000fee4  mov     [rsp+170h+var_100], r15
0x18000fee9  lea     rcx, [rsp+170h+hEvent]
0x18000feee  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000fef3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000fef7  mov     [rsp+170h+var_108], rdi
0x18000fefc  mov     [rsp+170h+var_100], rdi
0x18000ff01  lea     r8, [rsp+170h+hEvent]
0x18000ff06  xor     edx, edx
0x18000ff08  lea     r13d, [r15+2]
0x18000ff0c  mov     ecx, r13d
0x18000ff0f  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x18000ff16  nop     dword ptr [rax+rax+00h]
0x18000ff1b  mov     rcx, [rbp+78h]; this
0x18000ff1f  lea     r12, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ff26  test    eax, eax
0x18000ff28  jns     short loc_18000FF3C
0x18000ff2a  mov     r9d, eax; char *
0x18000ff2d  mov     r8, r12; unsigned int
0x18000ff30  mov     edx, 0BDh; void *
0x18000ff35  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ff3a  jmp     short loc_18000FF4D
0x18000ff3c  mov     rcx, [rsp+170h+hEvent]; hEvent
0x18000ff41  call    cs:__imp_CreateDirectoryJunctionsForUserProfile
0x18000ff48  nop     dword ptr [rax+rax+00h]
0x18000ff4d  lea     rax, ??1?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::~NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>(void)
0x18000ff54  mov     [rsp+170h+var_150], rax; int
0x18000ff59  lea     r9, ??0?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; void (*)(void *)
0x18000ff60  mov     edx, 18h; unsigned __int64
0x18000ff65  lea     r8d, [rdx-12h]; unsigned __int64
0x18000ff69  lea     rcx, [rbp+70h+var_E0]; void *
0x18000ff6d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000ff72  nop
0x18000ff73  lea     rcx, [rbp+70h+var_C8]
0x18000ff77  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000ff7c  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000ff84  movdqa  [rbp+70h+var_C0], xmm0
0x18000ff89  lea     r8, [rbp+70h+var_C8]
0x18000ff8d  xor     edx, edx
0x18000ff8f  lea     ecx, [rdx+1]
0x18000ff92  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x18000ff99  nop     dword ptr [rax+rax+00h]
0x18000ff9e  mov     ebx, eax
0x18000ffa0  test    eax, eax
0x18000ffa2  jns     short loc_18000FFAB
0x18000ffa4  mov     edx, 0C3h
0x18000ffa9  jmp     short loc_18000FFDC
0x18000ffab  lea     rcx, [rbp+70h+var_B0]
0x18000ffaf  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000ffb4  mov     [rbp+70h+var_A8], rdi
0x18000ffb8  mov     [rbp+70h+var_A0], rdi
0x18000ffbc  lea     r8, [rbp+70h+var_B0]
0x18000ffc0  xor     edx, edx
0x18000ffc2  lea     ecx, [rdx+4]
0x18000ffc5  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x18000ffcc  nop     dword ptr [rax+rax+00h]
0x18000ffd1  mov     ebx, eax
0x18000ffd3  test    eax, eax
0x18000ffd5  jns     short loc_18000FFF0
0x18000ffd7  mov     edx, 0C4h; void *
0x18000ffdc  mov     r9d, eax; char *
0x18000ffdf  mov     r8, r12; unsigned int
0x18000ffe2  mov     rcx, [rbp+78h]; this
0x18000ffe6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ffeb  jmp     loc_180010336
0x18000fff0  mov     rsi, [rbp+70h+var_B0]
0x18000fff4  test    rsi, rsi
0x18000fff7  jz      short loc_180010056
0x18000fff9  mov     rbx, rdi
0x18000fffc  inc     rbx
0x18000ffff  cmp     [rsi+rbx*2], r15w
0x180010004  jnz     short loc_18000FFFC
0x180010006  cmp     rbx, r13
0x180010009  cmova   rbx, r13
0x18001000d  mov     rdx, r13
0x180010010  lea     rcx, [rbp+70h+var_E0]
0x180010014  call    ?_EnsureCapacity@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180010019  mov     r14d, eax
0x18001001c  test    eax, eax
0x18001001e  js      short loc_18001003A
0x180010020  mov     r9, rbx; unsigned __int64
0x180010023  mov     r8, rsi; unsigned __int16 *
0x180010026  mov     edx, 3; unsigned __int64
0x18001002b  mov     rcx, [rbp+70h+var_E0]; unsigned __int16 *
0x18001002f  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180010034  mov     [rbp+70h+var_D8], rbx
0x180010038  jmp     short loc_18001005F
0x18001003a  mov     rcx, [rbp+78h]; this
0x18001003e  mov     r9d, r14d; char *
0x180010041  mov     r8, r12; unsigned int
0x180010044  mov     edx, 0C7h; void *
0x180010049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001004e  mov     ebx, r14d
0x180010051  jmp     loc_180010336
0x180010056  lea     rcx, [rbp+70h+var_E0]
0x18001005a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001005f  mov     rax, [rbp+70h+var_E0]
0x180010063  cmp     word ptr [rax+2], 3Ah ; ':'
0x180010068  jz      short loc_18001007C
0x18001006a  mov     ebx, 8000FFFFh
0x18001006f  mov     r9d, ebx
0x180010072  mov     edx, 0C8h
0x180010077  jmp     loc_18000FFDF
0x18001007c  lea     r9, aCommonfilesdir; "CommonFilesDir"
0x180010083  lea     rcx, [rbp+70h+var_80]
0x180010087  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18001008c  mov     ebx, eax
0x18001008e  test    eax, eax
0x180010090  jns     short loc_18001009C
0x180010092  mov     edx, 0CAh
0x180010097  jmp     loc_18000FFDC
0x18001009c  lea     r9, aProgramfilesdi; "ProgramFilesDir"
0x1800100a3  lea     rcx, [rbp+70h+var_98]
0x1800100a7  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x1800100ac  mov     ebx, eax
0x1800100ae  test    eax, eax
0x1800100b0  jns     short loc_1800100BC
0x1800100b2  mov     edx, 0CBh
0x1800100b7  jmp     loc_18000FFDC
0x1800100bc  mov     rbx, [rbp+70h+var_98]
0x1800100c0  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1800100c5  jz      short loc_1800100D9
0x1800100c7  mov     ebx, 8000FFFFh
0x1800100cc  mov     r9d, ebx
0x1800100cf  mov     edx, 0CCh
0x1800100d4  jmp     loc_18000FFDF
0x1800100d9  test    rbx, rbx
0x1800100dc  jz      short loc_180010136
0x1800100de  inc     rdi
0x1800100e1  cmp     [rbx+rdi*2], r15w
0x1800100e6  jnz     short loc_1800100DE
0x1800100e8  cmp     rdi, r13
0x1800100eb  cmova   rdi, r13
0x1800100ef  mov     rdx, r13
0x1800100f2  lea     rcx, [rbp+70h+var_68]
0x1800100f6  call    ?_EnsureCapacity@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1800100fb  mov     esi, eax
0x1800100fd  test    eax, eax
0x1800100ff  js      short loc_18001011B
0x180010101  mov     r9, rdi; unsigned __int64
0x180010104  mov     r8, rbx; unsigned __int16 *
0x180010107  mov     edx, 3; unsigned __int64
0x18001010c  mov     rcx, [rbp+70h+var_68]; unsigned __int16 *
0x180010110  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180010115  mov     [rbp+70h+var_60], rdi
0x180010119  jmp     short loc_18001013F
0x18001011b  mov     rcx, [rbp+78h]; this
0x18001011f  mov     r9d, esi; char *
0x180010122  mov     r8, r12; unsigned int
0x180010125  mov     edx, 0CFh; void *
0x18001012a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001012f  mov     ebx, esi
0x180010131  jmp     loc_180010336
0x180010136  lea     rcx, [rbp+70h+var_68]
0x18001013a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001013f  lea     rcx, [rsp+170h+var_128]; this
0x180010144  call    ??0CSystemACLApplicator@@QEAA@XZ; CSystemACLApplicator::CSystemACLApplicator(void)
0x180010149  nop
0x18001014a  lea     rcx, [rsp+170h+var_128]; this
0x18001014f  call    ?Init@CSystemACLApplicator@@UEAAJXZ; CSystemACLApplicator::Init(void)
0x180010154  mov     ebx, eax
0x180010156  test    eax, eax
0x180010158  jns     short loc_18001017E
0x18001015a  mov     rcx, [rbp+78h]; this
0x18001015e  mov     r9d, eax; char *
0x180010161  mov     r8, r12; unsigned int
0x180010164  mov     edx, 0D2h; void *
0x180010169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001016e  nop
0x18001016f  lea     rcx, [rsp+170h+var_120]
0x180010174  call    ??1?$unique_any_array_ptr@EU?$default_delete@$$BY0A@E@std@@Uempty_deleter@wil@@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,std::default_delete<uchar [0]>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<uchar,std::default_delete<uchar [0]>,wil::empty_deleter,unsigned __int64>(void)
0x180010179  jmp     loc_180010336
0x18001017e  mov     edi, r15d
0x180010181  lea     r14, __ImageBase
0x180010188  mov     r13d, 800700B7h
0x18001018e  cmp     edi, 11h
0x180010191  jnb     loc_180010329
0x180010197  mov     [rsp+170h+lpFileName], r15
0x18001019c  mov     [rsp+170h+var_138], r15
0x1800101a1  mov     [rsp+170h+var_130], r15
0x1800101a6  mov     eax, edi
0x1800101a8  lea     rbx, [rax+rax*4]
0x1800101ac  movsxd  rax, rva dword_1800311F4[r14+rbx*8]
0x1800101b4  lea     r8, [rax+rax*2]
0x1800101b8  mov     r9, rva off_1800311F8[r14+rbx*8]; "\\" ...
0x1800101c0  mov     r8, [rbp+r8*8+70h+var_E0]
0x1800101c5  lea     rdx, aSS_0; "%s%s"
0x1800101cc  lea     rcx, [rsp+170h+lpFileName]
0x1800101d1  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800101d6  mov     esi, eax
0x1800101d8  test    eax, eax
0x1800101da  js      loc_1800102FA
0x1800101e0  mov     r8d, rva dword_180031200[r14+rbx*8]
0x1800101e8  mov     rdx, r14
0x1800101eb  lea     rcx, [rsp+170h+lpFileName]
0x1800101f0  call    ?Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Concat(HINSTANCE__ *,uint,ushort)
0x1800101f5  mov     esi, eax
0x1800101f7  test    eax, eax
0x1800101f9  js      loc_1800102F3
0x1800101ff  mov     [rsp+170h+var_F8], r15
0x180010204  mov     [rbp+70h+var_F0], r15
0x180010208  mov     [rbp+70h+var_E8], r15
0x18001020c  movsxd  rax, rva dword_180031204[r14+rbx*8]
0x180010214  lea     r8, [rax+rax*2]
0x180010218  mov     r9, rva off_180031208[r14+rbx*8]
0x180010220  mov     r8, [rbp+r8*8+70h+var_E0]
0x180010225  lea     rdx, aSS_0; "%s%s"
0x18001022c  lea     rcx, [rsp+170h+var_F8]
0x180010231  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180010236  mov     esi, eax
0x180010238  test    eax, eax
0x18001023a  js      loc_1800102D2
0x180010240  mov     rdx, [rsp+170h+var_F8]; unsigned __int16 *
0x180010245  mov     rcx, [rsp+170h+lpFileName]; char *
0x18001024a  cmp     rva byte_1800311F0[r14+rbx*8], r15b
0x180010252  jz      short loc_180010272
0x180010254  lea     r8, [rsp+170h+var_128]; struct CAACLApplicator *
0x180010259  call    ?CreateSymLink@@YAJPEBG0AEBVCAACLApplicator@@@Z; CreateSymLink(ushort const *,ushort const *,CAACLApplicator const &)
0x18001025e  cmp     eax, r13d
0x180010261  jz      short loc_1800102B6
0x180010263  mov     rcx, [rbp+78h]
0x180010267  test    eax, eax
0x180010269  jns     short loc_1800102B6
0x18001026b  mov     edx, 0E2h
0x180010270  jmp     short loc_1800102AA
0x180010272  mov     rax, rva off_180031210[r14+rbx*8]
0x18001027a  mov     [rsp+170h+var_148], rax; struct _GUID *
0x18001027f  mov     dword ptr [rsp+170h+var_150], r15d; int
0x180010284  lea     r9, [rsp+170h+var_128]; struct CAACLApplicator *
0x180010289  mov     r8, rdx; unsigned __int16 *
0x18001028c  call    ?CreateDirectoryJunction@@YAJPEBG00AEBVCAACLApplicator@@HAEBU_GUID@@@Z; CreateDirectoryJunction(ushort const *,ushort const *,ushort const *,CAACLApplicator const &,int,_GUID const &)
0x180010291  cmp     eax, r13d
0x180010294  jz      short loc_1800102B6
0x180010296  cmp     eax, 80070003h
0x18001029b  jz      short loc_1800102B6
0x18001029d  mov     rcx, [rbp+78h]; this
0x1800102a1  test    eax, eax
0x1800102a3  jns     short loc_1800102B6
0x1800102a5  mov     edx, 0EBh; void *
0x1800102aa  mov     r9d, eax; char *
0x1800102ad  mov     r8, r12; unsigned int
0x1800102b0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800102b5  nop
0x1800102b6  lea     rcx, [rsp+170h+var_F8]
0x1800102bb  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800102c0  nop
0x1800102c1  lea     rcx, [rsp+170h+lpFileName]
0x1800102c6  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800102cb  inc     edi
0x1800102cd  jmp     loc_18001018E
0x1800102d2  mov     rcx, [rbp+78h]; this
0x1800102d6  mov     r9d, esi; char *
0x1800102d9  mov     r8, r12; unsigned int
0x1800102dc  mov     edx, 0DBh; void *
0x1800102e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800102e6  nop
0x1800102e7  lea     rcx, [rsp+170h+var_F8]
0x1800102ec  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800102f1  jmp     short loc_18001030F
0x1800102f3  mov     edx, 0D8h
0x1800102f8  jmp     short loc_1800102FF
0x1800102fa  mov     edx, 0D7h; void *
0x1800102ff  mov     r8, r12; unsigned int
0x180010302  mov     r9d, esi; char *
0x180010305  mov     rcx, [rbp+78h]; this
0x180010309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001030e  nop
0x18001030f  lea     rcx, [rsp+170h+lpFileName]
0x180010314  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180010319  nop
0x18001031a  lea     rcx, [rsp+170h+var_120]
0x18001031f  call    ??1?$unique_any_array_ptr@EU?$default_delete@$$BY0A@E@std@@Uempty_deleter@wil@@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,std::default_delete<uchar [0]>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<uchar,std::default_delete<uchar [0]>,wil::empty_deleter,unsigned __int64>(void)
0x180010324  jmp     loc_18001012F
0x180010329  lea     rcx, [rsp+170h+var_120]
0x18001032e  call    ??1?$unique_any_array_ptr@EU?$default_delete@$$BY0A@E@std@@Uempty_deleter@wil@@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,std::default_delete<uchar [0]>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<uchar,std::default_delete<uchar [0]>,wil::empty_deleter,unsigned __int64>(void)
0x180010333  mov     ebx, r15d
0x180010336  lea     r9, ??1?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA@XZ; void (*)(void *)
0x18001033d  mov     edx, 18h; unsigned __int64
0x180010342  lea     r8d, [rdx-12h]; unsigned __int64
0x180010346  lea     rcx, [rbp+70h+var_E0]; void *
0x18001034a  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001034f  nop
0x180010350  lea     rcx, [rsp+170h+hEvent]
0x180010355  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001035a  mov     eax, ebx
  ... truncated ...
```
