# FileTimeToTaskTimeString(_FILETIME const *,ushort * *)

- ea: `0x180015748`
- end: `0x1800159f4`
- name: `?FileTimeToTaskTimeString@@YAJPEBU_FILETIME@@PEAPEAG@Z`
- size: `684`
- prototype: `__int64 __fastcall(const struct _FILETIME *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800154ec`

## callees

- `0x180006330`
- `0x18000cc14`
- `0x18000cc34`
- `0x18000ff9c`
- `0x180010310`
- `0x180014bcc`
- `0x180015748`
- `0x18001c754`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800159ac`
- `OLEAUT32!__imp_SysAllocString` at `0x1800159ac`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180015885`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180015918`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180015885`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180015918`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x1800157c6`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180015831`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x1800157c6`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180015831`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001577d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001577d`

## string_xrefs

- `0x18001578c`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x1800157fd`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x18001583f`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015895`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x1800158d1`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015926`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x180015980`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall FileTimeToTaskTimeString(const struct _FILETIME *a1, unsigned __int16 **a2)
{
  const char *v3; // r9
  __int64 v4; // rdx
  unsigned int TimeFormat; // eax
  int cchTime; // ebx
  unsigned int LastError; // ebx
  const char *v9; // r9
  unsigned int DateFormat; // eax
  const char *v11; // r9
  int v12; // ebx
  const char *v13; // r9
  int v14; // eax
  int lpTimeStr; // [rsp+20h] [rbp-50h]
  int lpTimeStra; // [rsp+20h] [rbp-50h]
  int lpTimeStrb; // [rsp+20h] [rbp-50h]
  LPWSTR lpDateStr; // [rsp+40h] [rbp-30h] BYREF
  OLECHAR *psz; // [rsp+48h] [rbp-28h] BYREF
  LPWSTR v20; // [rsp+50h] [rbp-20h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  *a2 = 0;
  SystemTime = 0;
  if ( !FileTimeToSystemTime(a1, &SystemTime) )
  {
    v4 = 175;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
             v3);
  }
  TimeFormat = GetTimeFormatEx(L"!x-sys-default-locale", 0, &SystemTime, L"HH':'mm':'ss", 0, 0);
  cchTime = TimeFormat;
  if ( !TimeFormat )
  {
    v4 = 186;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
             v3);
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v20,
    0,
    TimeFormat,
    v3);
  if ( v20 )
  {
    if ( GetTimeFormatEx(L"!x-sys-default-locale", 0, &SystemTime, L"HH':'mm':'ss", v20, cchTime) )
    {
      DateFormat = GetDateFormatEx(L"!x-sys-default-locale", 0, &SystemTime, L"yyyy'-'MM'-'dd'T'", 0, 0, 0);
      v12 = DateFormat;
      if ( DateFormat )
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &lpDateStr,
          0,
          DateFormat,
          v11);
        if ( lpDateStr )
        {
          if ( GetDateFormatEx(L"!x-sys-default-locale", 0, &SystemTime, L"yyyy'-'MM'-'dd'T'", lpDateStr, v12, 0) )
          {
            psz = 0;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &psz,
              0);
            v14 = NgcUtils::CombineSeparateStrings(
                    (NgcUtils *)lpDateStr,
                    &qword_180024840,
                    v20,
                    (unsigned __int16 *)&psz);
            LastError = v14;
            if ( v14 >= 0 )
            {
              *a2 = SysAllocString(psz);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&psz);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpDateStr);
              LastError = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xEA,
                (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
                (const char *)(unsigned int)v14,
                lpTimeStrb);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&psz);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpDateStr);
            }
          }
          else
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0xE3,
                          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
                          v13);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpDateStr);
          }
        }
        else
        {
          LastError = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD7,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
            (const char *)0x8007000ELL,
            lpTimeStra);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&lpDateStr);
        }
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xD4,
                      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
                      v11);
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xC5,
                    (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
                    v9);
    }
  }
  else
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
      (const char *)0x8007000ELL,
      lpTimeStr);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v20);
  return LastError;
}

```

## disassembly

```asm
0x180015748  mov     [rsp-8+arg_10], rbx
0x18001574d  mov     [rsp-8+arg_18], rdi
0x180015752  push    rbp
0x180015753  mov     rbp, rsp
0x180015756  sub     rsp, 70h
0x18001575a  mov     rax, cs:__security_cookie
0x180015761  xor     rax, rsp
0x180015764  mov     [rbp+var_8], rax
0x180015768  mov     rdi, rdx
0x18001576b  mov     qword ptr [rdx], 0
0x180015772  xorps   xmm0, xmm0
0x180015775  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180015779  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18001577d  call    cs:__imp_FileTimeToSystemTime
0x180015783  test    eax, eax
0x180015785  jnz     short loc_1800157A1
0x180015787  mov     edx, 0AFh; void *
0x18001578c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015793  mov     rcx, [rbp+8]; this
0x180015797  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001579c  jmp     loc_1800159D6
0x1800157a1  mov     [rsp+70h+cchTime], 0; cchTime
0x1800157a9  mov     [rsp+70h+lpTimeStr], 0; int
0x1800157b2  lea     r9, Format; "HH':'mm':'ss"
0x1800157b9  lea     r8, [rbp+SystemTime]; lpTime
0x1800157bd  xor     edx, edx; dwFlags
0x1800157bf  lea     rcx, LocaleName; "!x-sys-default-locale"
0x1800157c6  call    cs:__imp_GetTimeFormatEx
0x1800157cc  mov     ebx, eax
0x1800157ce  test    eax, eax
0x1800157d0  jnz     short loc_1800157D9
0x1800157d2  mov     edx, 0BAh
0x1800157d7  jmp     short loc_18001578C
0x1800157d9  mov     r8, rbx
0x1800157dc  xor     edx, edx
0x1800157de  lea     rcx, [rbp+var_20]
0x1800157e2  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800157e7  nop
0x1800157e8  mov     rax, [rbp+var_20]
0x1800157ec  test    rax, rax
0x1800157ef  jnz     short loc_180015814
0x1800157f1  mov     rcx, [rbp+8]; this
0x1800157f5  mov     ebx, 8007000Eh
0x1800157fa  mov     r9d, ebx; char *
0x1800157fd  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015804  mov     edx, 0BDh; void *
0x180015809  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001580e  nop
0x18001580f  jmp     loc_1800159CB
0x180015814  mov     [rsp+70h+cchTime], ebx; cchTime
0x180015818  mov     [rsp+70h+lpTimeStr], rax; lpTimeStr
0x18001581d  lea     r9, Format; "HH':'mm':'ss"
0x180015824  lea     r8, [rbp+SystemTime]; lpTime
0x180015828  xor     edx, edx; dwFlags
0x18001582a  lea     rcx, LocaleName; "!x-sys-default-locale"
0x180015831  call    cs:__imp_GetTimeFormatEx
0x180015837  test    eax, eax
0x180015839  jnz     short loc_180015857
0x18001583b  mov     rcx, [rbp+8]; this
0x18001583f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015846  mov     edx, 0C5h; void *
0x18001584b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015850  mov     ebx, eax
0x180015852  jmp     loc_1800159CB
0x180015857  mov     [rsp+70h+lpCalendar], 0; lpCalendar
0x180015860  mov     [rsp+70h+cchTime], 0; cchDate
0x180015868  mov     [rsp+70h+lpTimeStr], 0; int
0x180015871  lea     r9, aYyyyMmDdT; "yyyy'-'MM'-'dd'T'"
0x180015878  lea     r8, [rbp+SystemTime]; lpDate
0x18001587c  xor     edx, edx; dwFlags
0x18001587e  lea     rcx, LocaleName; "!x-sys-default-locale"
0x180015885  call    cs:__imp_GetDateFormatEx
0x18001588b  mov     ebx, eax
0x18001588d  test    eax, eax
0x18001588f  jnz     short loc_1800158AD
0x180015891  mov     rcx, [rbp+8]; this
0x180015895  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001589c  mov     edx, 0D4h; void *
0x1800158a1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800158a6  mov     ebx, eax
0x1800158a8  jmp     loc_1800159CB
0x1800158ad  mov     r8, rbx
0x1800158b0  xor     edx, edx
0x1800158b2  lea     rcx, [rbp+lpDateStr]
0x1800158b6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800158bb  nop
0x1800158bc  mov     rax, [rbp+lpDateStr]
0x1800158c0  test    rax, rax
0x1800158c3  jnz     short loc_1800158F2
0x1800158c5  mov     rcx, [rbp+8]; this
0x1800158c9  mov     ebx, 8007000Eh
0x1800158ce  mov     r9d, ebx; char *
0x1800158d1  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800158d8  mov     edx, 0D7h; void *
0x1800158dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800158e2  nop
0x1800158e3  lea     rcx, [rbp+lpDateStr]
0x1800158e7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800158ec  nop
0x1800158ed  jmp     loc_1800159CB
0x1800158f2  mov     [rsp+70h+lpCalendar], 0; lpCalendar
0x1800158fb  mov     [rsp+70h+cchTime], ebx; cchDate
0x1800158ff  mov     [rsp+70h+lpTimeStr], rax; int
0x180015904  lea     r9, aYyyyMmDdT; "yyyy'-'MM'-'dd'T'"
0x18001590b  lea     r8, [rbp+SystemTime]; lpDate
0x18001590f  xor     edx, edx; dwFlags
0x180015911  lea     rcx, LocaleName; "!x-sys-default-locale"
0x180015918  call    cs:__imp_GetDateFormatEx
0x18001591e  test    eax, eax
0x180015920  jnz     short loc_180015948
0x180015922  mov     rcx, [rbp+8]; this
0x180015926  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001592d  mov     edx, 0E3h; void *
0x180015932  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015937  mov     ebx, eax
0x180015939  lea     rcx, [rbp+lpDateStr]
0x18001593d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180015942  nop
0x180015943  jmp     loc_1800159CB
0x180015948  mov     [rbp+psz], 0
0x180015950  xor     edx, edx
0x180015952  lea     rcx, [rbp+psz]
0x180015956  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001595b  lea     r9, [rbp+psz]; unsigned __int16 *
0x18001595f  mov     r8, [rbp+var_20]; unsigned __int16 *
0x180015963  lea     rdx, qword_180024840; unsigned __int16 *
0x18001596a  mov     rcx, [rbp+lpDateStr]; this
0x18001596e  call    ?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)
0x180015973  mov     ebx, eax
0x180015975  test    eax, eax
0x180015977  jns     short loc_1800159A8
0x180015979  mov     rcx, [rbp+8]; this
0x18001597d  mov     r9d, eax; char *
0x180015980  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015987  mov     edx, 0EAh; void *
0x18001598c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015991  nop
0x180015992  lea     rcx, [rbp+psz]
0x180015996  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001599b  nop
0x18001599c  lea     rcx, [rbp+lpDateStr]
0x1800159a0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800159a5  nop
0x1800159a6  jmp     short loc_1800159CB
0x1800159a8  mov     rcx, [rbp+psz]; psz
0x1800159ac  call    cs:__imp_SysAllocString
0x1800159b2  mov     [rdi], rax
0x1800159b5  lea     rcx, [rbp+psz]
0x1800159b9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800159be  nop
0x1800159bf  lea     rcx, [rbp+lpDateStr]
0x1800159c3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800159c8  nop
0x1800159c9  xor     ebx, ebx
0x1800159cb  lea     rcx, [rbp+var_20]
0x1800159cf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800159d4  mov     eax, ebx
0x1800159d6  mov     rcx, [rbp+var_8]
0x1800159da  xor     rcx, rsp; StackCookie
0x1800159dd  call    __security_check_cookie
0x1800159e2  lea     r11, [rsp+70h+var_s0]
0x1800159e7  mov     rbx, [r11+20h]
0x1800159eb  mov     rdi, [r11+28h]
0x1800159ef  mov     rsp, r11
0x1800159f2  pop     rbp
0x1800159f3  retn
```
