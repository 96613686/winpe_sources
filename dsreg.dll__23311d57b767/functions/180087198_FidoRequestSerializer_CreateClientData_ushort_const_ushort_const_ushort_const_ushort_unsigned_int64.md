# FidoRequestSerializer::CreateClientData(ushort const *,ushort const *,ushort const *,ushort * *,unsigned __int64 *)

- ea: `0x180087198`
- end: `0x18008750d`
- name: `?CreateClientData@FidoRequestSerializer@@SAJPEBG00PEAPEAGPEA_K@Z`
- size: `885`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180089574`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180009780`
- `0x180012cf0`
- `0x1800307c4`
- `0x18003334c`
- `0x18007c57c`
- `0x18007cc9c`
- `0x18007cd1c`
- `0x18007cdd0`
- `0x180087198`
- `0x18008c820`

## string_xrefs

- `0x180087436`: `PrintJsonField`
- `0x1800874a1`: `PrintJsonEnd`
- `0x180087410`: `PrintJsonStart`
- `0x180087306`: `authToken`
- `0x180087325`: `authToken`
- `0x1800871f7`: `accessToken`
- `0x180087289`: `FidoRequestSerializer::CreateClientData`
- `0x1800872a3`: `FidoRequestSerializer::CreateClientData`
- `0x1800872cf`: `FidoRequestSerializer::CreateClientData`
- `0x1800872e9`: `FidoRequestSerializer::CreateClientData`
- `0x180087312`: `FidoRequestSerializer::CreateClientData`
- `0x1800873d8`: `FidoRequestSerializer::CreateClientData`
- `0x1800874ab`: `FidoRequestSerializer::CreateClientData`

## pseudocode

```c
__int64 __fastcall FidoRequestSerializer::CreateClientData(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  __int64 v7; // rax
  unsigned __int16 *v8; // rdi
  unsigned __int64 *v9; // rsi
  unsigned int v10; // ebx
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // r10
  int v13; // eax
  const wchar_t *v14; // r8
  int v15; // r9d
  int v16; // r9d
  int v17; // r9d
  unsigned __int16 *v18; // rax
  _BYTE *v19; // rcx
  __int64 v20; // rdi
  _BYTE *v21; // rax
  __int64 v23; // [rsp+20h] [rbp-91h] BYREF
  const unsigned __int16 *v24; // [rsp+28h] [rbp-89h]
  __int64 v25; // [rsp+30h] [rbp-81h]
  const unsigned __int16 *v26; // [rsp+38h] [rbp-79h]
  unsigned __int64 v27; // [rsp+40h] [rbp-71h] BYREF
  __int64 v28; // [rsp+48h] [rbp-69h] BYREF
  const wchar_t *v29; // [rsp+50h] [rbp-61h]
  __int64 v30; // [rsp+58h] [rbp-59h]
  const unsigned __int16 *v31; // [rsp+60h] [rbp-51h]
  unsigned __int64 v32; // [rsp+68h] [rbp-49h] BYREF
  __int64 v33; // [rsp+70h] [rbp-41h] BYREF
  const wchar_t *v34; // [rsp+78h] [rbp-39h]
  __int64 v35; // [rsp+80h] [rbp-31h]
  const wchar_t *v36; // [rsp+88h] [rbp-29h]
  __int64 v37; // [rsp+90h] [rbp-21h]
  __int64 v38; // [rsp+98h] [rbp-19h] BYREF
  const wchar_t *v39; // [rsp+A0h] [rbp-11h]
  __int64 v40; // [rsp+A8h] [rbp-9h]
  const unsigned __int16 *v41; // [rsp+B0h] [rbp-1h]
  __int64 v42; // [rsp+B8h] [rbp+7h]
  unsigned __int16 *v43; // [rsp+110h] [rbp+5Fh] BYREF

  v35 = 7;
  v43 = 0;
  v34 = L"version";
  v33 = 0x100000000LL;
  v36 = L"1";
  v24 = L"upn";
  v37 = 1;
  v29 = L"accessToken";
  v23 = 0x200000000LL;
  v39 = L"rpid";
  v7 = -1;
  v8 = 0;
  v25 = 3;
  v27 = 0;
  v28 = 0x400000000LL;
  v30 = 11;
  v32 = 0;
  v38 = 0x800000000LL;
  v40 = 4;
  v41 = a1;
  do
    ++v7;
  while ( a1[v7] );
  v9 = a5;
  v42 = v7;
  if ( a5 )
    *a5 = 0;
  if ( !a4 )
  {
    v10 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"FidoRequestSerializer::CreateClientData", L"pBuffer");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"FidoRequestSerializer::CreateClientData", L"pBuffer");
LABEL_37:
    if ( v9 )
      *v9 = 0;
    return v10;
  }
  *a4 = 0;
  if ( (unsigned int)IsEmptyString(a2) )
  {
    v10 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null or empty.",
      L"FidoRequestSerializer::CreateClientData",
      &stru_1800FB3F8);
    v11 = (const unsigned __int16 *)&stru_1800FB3F8;
LABEL_9:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"FidoRequestSerializer::CreateClientData", v11);
    goto LABEL_32;
  }
  if ( (unsigned int)IsEmptyString(a3) )
  {
    v10 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null or empty.",
      L"FidoRequestSerializer::CreateClientData",
      L"authToken");
    v11 = L"authToken";
    goto LABEL_9;
  }
  v26 = v12;
  if ( v12 )
  {
    v13 = StringLen(v12, &v27);
    v10 = v13;
    if ( v13 < 0 )
      goto LABEL_14;
  }
  v31 = a3;
  if ( a3 )
  {
    v13 = StringLen(a3, &v32);
    v10 = v13;
    if ( v13 < 0 )
    {
LABEL_14:
      v14 = L"L\"StringLenNullSafe\"";
LABEL_31:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"FidoRequestSerializer::CreateClientData",
        v14,
        (unsigned int)v13,
        v23,
        v24,
        v25,
        v26,
        v27,
        v28,
        v29,
        v30,
        v31,
        v32,
        v33,
        v34,
        v35,
        v36,
        v37,
        v38,
        v39,
        v40,
        v41,
        v42);
LABEL_32:
      v19 = *a4;
      if ( *a4 )
      {
        v20 = 2LL * (_QWORD)v8;
        if ( v20 )
        {
          v21 = *a4;
          do
          {
            *v21++ = 0;
            --v20;
          }
          while ( v20 );
        }
      }
      SafeFree(v19);
      *a4 = 0;
      goto LABEL_37;
    }
  }
  else
  {
    v10 = 0;
  }
  AddJsonFieldLength(-1, (struct struct_json_field *)&v33, (unsigned __int64 *)&v43);
  AddJsonFieldLength(v15, (struct struct_json_field *)&v23, (unsigned __int64 *)&v43);
  AddJsonFieldLength(v16, (struct struct_json_field *)&v28, (unsigned __int64 *)&v43);
  AddJsonFieldLength(v17, (struct struct_json_field *)&v38, (unsigned __int64 *)&v43);
  v8 = v43;
  if ( !v43 )
    return v10;
  v18 = (unsigned __int16 *)SafeAlloc(2LL * (_QWORD)v43);
  *a4 = v18;
  if ( !v18 )
  {
    v10 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"FidoRequestSerializer::CreateClientData");
    goto LABEL_32;
  }
  a5 = (unsigned __int64 *)v8;
  v43 = v18;
  v13 = PrintJsonStart(&v43, (unsigned __int64 *)&a5);
  v10 = v13;
  if ( v13 < 0 )
  {
    v14 = L"PrintJsonStart";
    goto LABEL_31;
  }
  v13 = PrintJsonField(&v43, (unsigned __int64 *)&a5, (struct struct_json_field *)&v33, 0);
  v10 = v13;
  if ( v13 < 0
    || (v13 = PrintJsonField(&v43, (unsigned __int64 *)&a5, (struct struct_json_field *)&v23, 1), v10 = v13, v13 < 0)
    || (v13 = PrintJsonField(&v43, (unsigned __int64 *)&a5, (struct struct_json_field *)&v28, 1), v10 = v13, v13 < 0)
    || (v13 = PrintJsonField(&v43, (unsigned __int64 *)&a5, (struct struct_json_field *)&v38, 1), v10 = v13, v13 < 0) )
  {
    v14 = L"PrintJsonField";
    goto LABEL_31;
  }
  v13 = PrintJsonEnd(&v43, (unsigned __int64 *)&a5);
  v10 = v13;
  if ( v13 < 0 )
  {
    v14 = L"PrintJsonEnd";
    goto LABEL_31;
  }
  if ( v9 )
    *v9 = (char *)v8 - (char *)a5;
  return v10;
}

```

## disassembly

```asm
0x180087198  push    rbp
0x18008719a  push    rbx
0x18008719b  push    rsi
0x18008719c  push    rdi
0x18008719d  push    r12
0x18008719f  push    r13
0x1800871a1  push    r14
0x1800871a3  push    r15
0x1800871a5  lea     rbp, [rsp-17h]
0x1800871aa  sub     rsp, 0C8h
0x1800871b1  xor     r12d, r12d
0x1800871b4  mov     [rbp+4Fh+var_80], 7
0x1800871bc  lea     rax, aVersion; "version"
0x1800871c3  mov     [rbp+4Fh+arg_0], r12
0x1800871c7  mov     [rbp+4Fh+var_88], rax
0x1800871cb  mov     r10, rdx
0x1800871ce  lea     rax, a1; "1"
0x1800871d5  mov     [rbp+4Fh+var_90], r12d
0x1800871d9  mov     [rbp+4Fh+var_78], rax
0x1800871dd  lea     r13d, [r12+1]
0x1800871e2  lea     rax, aUpn_1; "upn"
0x1800871e9  mov     [rbp+4Fh+var_8C], r13d
0x1800871ed  mov     [rsp+100h+var_D8], rax
0x1800871f2  lea     edx, [r12+4]
0x1800871f7  lea     rax, aAccesstoken; "accessToken"
0x1800871fe  mov     [rbp+4Fh+var_70], r13
0x180087202  mov     [rbp+4Fh+var_B0], rax
0x180087206  mov     r15, r9
0x180087209  lea     rax, aRpid_0; "rpid"
0x180087210  mov     [rsp+100h+var_E0], r12d
0x180087215  mov     [rbp+4Fh+var_60], rax
0x180087219  mov     r14, r8
0x18008721c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180087220  mov     [rsp+100h+var_DC], 2
0x180087228  mov     edi, r12d
0x18008722b  mov     [rsp+100h+var_D0], 3
0x180087234  mov     [rbp+4Fh+var_C0], r12
0x180087238  mov     [rbp+4Fh+var_B8], r12d
0x18008723c  mov     [rbp+4Fh+var_B4], edx
0x18008723f  mov     [rbp+4Fh+var_A8], 0Bh
0x180087247  mov     [rbp+4Fh+var_98], r12
0x18008724b  mov     [rbp+4Fh+var_68], r12d
0x18008724f  mov     [rbp+4Fh+var_64], 8
0x180087256  mov     [rbp+4Fh+var_58], rdx
0x18008725a  mov     [rbp+4Fh+var_50], rcx
0x18008725e  inc     rax
0x180087261  cmp     [rcx+rax*2], r12w
0x180087266  jnz     short loc_18008725E
0x180087268  mov     rsi, [rbp+4Fh+arg_20]
0x18008726c  mov     [rbp+4Fh+var_48], rax
0x180087270  test    rsi, rsi
0x180087273  jz      short loc_180087278
0x180087275  mov     [rsi], r12
0x180087278  test    r15, r15
0x18008727b  jnz     short loc_1800872B4
0x18008727d  lea     r8, aPbuffer; "pBuffer"
0x180087284  mov     ebx, 80070057h
0x180087289  lea     rdx, aFidorequestser_0; "FidoRequestSerializer::CreateClientData"
0x180087290  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180087297  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008729c  lea     rdx, aPbuffer; "pBuffer"
0x1800872a3  lea     rcx, aFidorequestser_0; "FidoRequestSerializer::CreateClientData"
0x1800872aa  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800872af  jmp     loc_1800874E1
0x1800872b4  mov     rcx, r10; unsigned __int16 *
0x1800872b7  mov     [r9], r12
0x1800872ba  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800872bf  test    eax, eax
0x1800872c1  jz      short loc_1800872FA
0x1800872c3  lea     r8, stru_1800FB3F8
0x1800872ca  mov     ebx, 80070057h
0x1800872cf  lea     rdx, aFidorequestser_0; "FidoRequestSerializer::CreateClientData"
0x1800872d6  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x1800872dd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800872e2  lea     rdx, stru_1800FB3F8; unsigned __int16 *
0x1800872e9  lea     rcx, aFidorequestser_0; "FidoRequestSerializer::CreateClientData"
0x1800872f0  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800872f5  jmp     loc_1800874BE
0x1800872fa  mov     rcx, r14; unsigned __int16 *
0x1800872fd  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180087302  test    eax, eax
0x180087304  jz      short loc_18008732E
0x180087306  lea     r8, aAuthtoken; "authToken"
0x18008730d  mov     ebx, 80070057h
0x180087312  lea     rdx, aFidorequestser_0; "FidoRequestSerializer::CreateClientData"
0x180087319  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x180087320  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180087325  lea     rdx, aAuthtoken; "authToken"
0x18008732c  jmp     short loc_1800872E9
0x18008732e  mov     [rbp+4Fh+var_C8], r10
0x180087332  test    r10, r10
0x180087335  jz      short loc_180087355
0x180087337  lea     rdx, [rbp+4Fh+var_C0]; unsigned __int64 *
0x18008733b  mov     rcx, r10; unsigned __int16 *
0x18008733e  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x180087343  mov     ebx, eax
0x180087345  test    eax, eax
0x180087347  jns     short loc_180087355
0x180087349  lea     r8, aLStringlennull; "L\"StringLenNullSafe\""
0x180087350  jmp     loc_1800874A8
0x180087355  mov     [rbp+4Fh+var_A0], r14
0x180087359  test    r14, r14
0x18008735c  jz      short loc_180087372
0x18008735e  lea     rdx, [rbp+4Fh+var_98]; unsigned __int64 *
0x180087362  mov     rcx, r14; unsigned __int16 *
0x180087365  call    ?StringLen@@YAJPEBGPEA_K@Z; StringLen(ushort const *,unsigned __int64 *)
0x18008736a  mov     ebx, eax
0x18008736c  test    eax, eax
0x18008736e  jns     short loc_180087375
0x180087370  jmp     short loc_180087349
0x180087372  mov     ebx, r12d
0x180087375  or      r9d, 0FFFFFFFFh
0x180087379  lea     r8, [rbp+4Fh+arg_0]; unsigned __int64 *
0x18008737d  mov     ecx, r9d; unsigned int
0x180087380  lea     rdx, [rbp+4Fh+var_90]; struct struct_json_field *
0x180087384  call    ?AddJsonFieldLength@@YAXKAEAUstruct_json_field@@AEA_K@Z; AddJsonFieldLength(ulong,struct_json_field &,unsigned __int64 &)
0x180087389  mov     ecx, r9d; unsigned int
0x18008738c  lea     r8, [rbp+4Fh+arg_0]; unsigned __int64 *
0x180087390  lea     rdx, [rsp+100h+var_E0]; struct struct_json_field *
0x180087395  call    ?AddJsonFieldLength@@YAXKAEAUstruct_json_field@@AEA_K@Z; AddJsonFieldLength(ulong,struct_json_field &,unsigned __int64 &)
0x18008739a  mov     ecx, r9d; unsigned int
0x18008739d  lea     r8, [rbp+4Fh+arg_0]; unsigned __int64 *
0x1800873a1  lea     rdx, [rbp+4Fh+var_B8]; struct struct_json_field *
0x1800873a5  call    ?AddJsonFieldLength@@YAXKAEAUstruct_json_field@@AEA_K@Z; AddJsonFieldLength(ulong,struct_json_field &,unsigned __int64 &)
0x1800873aa  mov     ecx, r9d; unsigned int
0x1800873ad  lea     r8, [rbp+4Fh+arg_0]; unsigned __int64 *
0x1800873b1  lea     rdx, [rbp+4Fh+var_68]; struct struct_json_field *
0x1800873b5  call    ?AddJsonFieldLength@@YAXKAEAUstruct_json_field@@AEA_K@Z; AddJsonFieldLength(ulong,struct_json_field &,unsigned __int64 &)
0x1800873ba  mov     rdi, [rbp+4Fh+arg_0]
0x1800873be  test    rdi, rdi
0x1800873c1  jz      loc_1800874F7
0x1800873c7  lea     rcx, [rdi+rdi]; unsigned __int64
0x1800873cb  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x1800873d0  mov     [r15], rax
0x1800873d3  test    rax, rax
0x1800873d6  jnz     short loc_1800873F5
0x1800873d8  lea     rdx, aFidorequestser_0; "FidoRequestSerializer::CreateClientData"
0x1800873df  mov     ebx, 8007000Eh
0x1800873e4  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x1800873eb  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800873f0  jmp     loc_1800874BE
0x1800873f5  lea     rdx, [rbp+4Fh+arg_20]; unsigned __int64 *
0x1800873f9  mov     [rbp+4Fh+arg_20], rdi
0x1800873fd  lea     rcx, [rbp+4Fh+arg_0]; unsigned __int16 **
0x180087401  mov     [rbp+4Fh+arg_0], rax
0x180087405  call    ?PrintJsonStart@@YAJPEAPEAGPEA_K@Z; PrintJsonStart(ushort * *,unsigned __int64 *)
0x18008740a  mov     ebx, eax
0x18008740c  test    eax, eax
0x18008740e  jns     short loc_18008741C
0x180087410  lea     r8, aPrintjsonstart; "PrintJsonStart"
0x180087417  jmp     loc_1800874A8
0x18008741c  xor     r9d, r9d; int
0x18008741f  lea     r8, [rbp+4Fh+var_90]; struct struct_json_field *
0x180087423  lea     rdx, [rbp+4Fh+arg_20]; unsigned __int64 *
0x180087427  lea     rcx, [rbp+4Fh+arg_0]; unsigned __int16 **
0x18008742b  call    ?PrintJsonField@@YAJPEAPEAGPEA_KAEAUstruct_json_field@@H@Z; PrintJsonField(ushort * *,unsigned __int64 *,struct_json_field &,int)
0x180087430  mov     ebx, eax
0x180087432  test    eax, eax
0x180087434  jns     short loc_18008743F
0x180087436  lea     r8, aPrintjsonfield; "PrintJsonField"
0x18008743d  jmp     short loc_1800874A8
0x18008743f  mov     r9d, r13d; int
0x180087442  lea     r8, [rsp+100h+var_E0]; struct struct_json_field *
0x180087447  lea     rdx, [rbp+4Fh+arg_20]; unsigned __int64 *
0x18008744b  lea     rcx, [rbp+4Fh+arg_0]; unsigned __int16 **
0x18008744f  call    ?PrintJsonField@@YAJPEAPEAGPEA_KAEAUstruct_json_field@@H@Z; PrintJsonField(ushort * *,unsigned __int64 *,struct_json_field &,int)
0x180087454  mov     ebx, eax
0x180087456  test    eax, eax
0x180087458  js      short loc_180087436
0x18008745a  mov     r9d, r13d; int
0x18008745d  lea     r8, [rbp+4Fh+var_B8]; struct struct_json_field *
0x180087461  lea     rdx, [rbp+4Fh+arg_20]; unsigned __int64 *
0x180087465  lea     rcx, [rbp+4Fh+arg_0]; unsigned __int16 **
0x180087469  call    ?PrintJsonField@@YAJPEAPEAGPEA_KAEAUstruct_json_field@@H@Z; PrintJsonField(ushort * *,unsigned __int64 *,struct_json_field &,int)
0x18008746e  mov     ebx, eax
0x180087470  test    eax, eax
0x180087472  js      short loc_180087436
0x180087474  mov     r9d, r13d; int
0x180087477  lea     r8, [rbp+4Fh+var_68]; struct struct_json_field *
0x18008747b  lea     rdx, [rbp+4Fh+arg_20]; unsigned __int64 *
0x18008747f  lea     rcx, [rbp+4Fh+arg_0]; unsigned __int16 **
0x180087483  call    ?PrintJsonField@@YAJPEAPEAGPEA_KAEAUstruct_json_field@@H@Z; PrintJsonField(ushort * *,unsigned __int64 *,struct_json_field &,int)
0x180087488  mov     ebx, eax
0x18008748a  test    eax, eax
0x18008748c  js      short loc_180087436
0x18008748e  lea     rdx, [rbp+4Fh+arg_20]; unsigned __int64 *
0x180087492  lea     rcx, [rbp+4Fh+arg_0]; unsigned __int16 **
0x180087496  call    ?PrintJsonEnd@@YAJPEAPEAGPEA_K@Z; PrintJsonEnd(ushort * *,unsigned __int64 *)
0x18008749b  mov     ebx, eax
0x18008749d  test    eax, eax
0x18008749f  jns     short loc_1800874EB
0x1800874a1  lea     r8, aPrintjsonend; "PrintJsonEnd"
0x1800874a8  mov     r9d, eax
0x1800874ab  lea     rdx, aFidorequestser_0; "FidoRequestSerializer::CreateClientData"
0x1800874b2  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800874b9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800874be  mov     rcx, [r15]; lpMem
0x1800874c1  test    rcx, rcx
0x1800874c4  jz      short loc_1800874D9
0x1800874c6  add     rdi, rdi
0x1800874c9  jz      short loc_1800874D9
0x1800874cb  mov     rax, rcx
0x1800874ce  mov     [rax], r12b
0x1800874d1  add     rax, r13
0x1800874d4  sub     rdi, r13
0x1800874d7  jnz     short loc_1800874CE
0x1800874d9  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800874de  mov     [r15], r12
0x1800874e1  test    rsi, rsi
0x1800874e4  jz      short loc_1800874F7
0x1800874e6  mov     [rsi], r12
0x1800874e9  jmp     short loc_1800874F7
0x1800874eb  test    rsi, rsi
0x1800874ee  jz      short loc_1800874F7
0x1800874f0  sub     rdi, [rbp+4Fh+arg_20]
0x1800874f4  mov     [rsi], rdi
0x1800874f7  mov     eax, ebx
0x1800874f9  add     rsp, 0C8h
0x180087500  pop     r15
0x180087502  pop     r14
0x180087504  pop     r13
0x180087506  pop     r12
0x180087508  pop     rdi
0x180087509  pop     rsi
0x18008750a  pop     rbx
0x18008750b  pop     rbp
0x18008750c  retn
```
