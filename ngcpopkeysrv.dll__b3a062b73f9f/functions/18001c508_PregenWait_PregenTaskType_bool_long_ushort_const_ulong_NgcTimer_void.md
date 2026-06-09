# PregenWait(PregenTaskType,bool,long,ushort const *,ulong,NgcTimer *,void * *)

- ea: `0x18001c508`
- end: `0x18001c700`
- name: `?PregenWait@@YAJW4PregenTaskType@@_NJPEBGKPEAVNgcTimer@@PEAPEAX@Z`
- size: `504`
- prototype: `int __fastcall(__int64, char, int Event, const unsigned __int16 *, DWORD, int *, void **)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019f44`
- `0x18001a170`
- `0x18001bee8`

## callees

- `0x18000b0dc`
- `0x18000b0fc`
- `0x18000db5c`
- `0x18001069c`
- `0x180010730`
- `0x1800136b0`
- `0x18001c268`
- `0x18001c508`
- `0x18001d2e0`
- `0x180022ef4`
- `0x18002308c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001c5ae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001c5ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c594`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c594`

## string_xrefs

- `0x18001c524`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
int __fastcall PregenWait(__int64 a1, char a2, int Event, const unsigned __int16 *a4, DWORD a5, int *a6, void **a7)
{
  int v9; // eax
  __int64 v10; // rdx
  void **v11; // rdi
  int v12; // ebx
  DWORD v13; // eax
  DWORD v14; // edx
  DWORD v15; // eax
  const char *v16; // r9
  const unsigned __int16 *v18; // rdx
  NgcUtils *v19; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned __int64 v21; // r9
  __int64 v22; // rdx
  const unsigned __int16 *v23; // rdx
  NgcUtils *v24; // rcx
  int v25; // eax
  HKEY v26; // [rsp+20h] [rbp-10h] BYREF
  HKEY v27; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  int v29; // [rsp+58h] [rbp+28h] BYREF

  if ( !a2 )
  {
    v9 = NgcTriggerTask(a1);
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x228,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v9,
        (int)v26);
  }
  if ( !a5 && Event < 0 )
  {
    v10 = 558;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)(unsigned int)Event,
      (int)v26);
    return Event;
  }
  v11 = a7;
  if ( !*a7 )
  {
    Event = PregenGetEvent(a7);
    if ( Event < 0 )
    {
      v10 = 566;
      goto LABEL_7;
    }
  }
  v12 = *a6;
  v13 = GetTickCount() - v12;
  v14 = 1000;
  if ( v13 < a5 )
    v14 = a5 - v13;
  v15 = WaitForSingleObject(*v11, v14);
  if ( !v15 )
  {
    v27 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v27,
      0);
    NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                          v19,
                                          v18,
                                          a4,
                                          (unsigned __int16 *)&v27);
    Event = NgcStateSeparatedRegistryLocation;
    if ( NgcStateSeparatedRegistryLocation >= 0 )
    {
      v29 = 0;
      Event = NgcUtils::GetRegistryDwordValue(
                (NgcUtils *)0xFFFFFFFF80000002LL,
                v27,
                (const unsigned __int16 *)&stru_18002B278,
                (const unsigned __int16 *)&v29,
                (unsigned int *)v26);
      if ( Event == -2147024894 )
      {
        v26 = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v26,
          0);
        v25 = NgcUtils::GetNgcStateSeparatedRegistryLocation(v24, v23, L"PregenKeys", (unsigned __int16 *)&v26);
        Event = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x25C,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
            (const char *)(unsigned int)v25,
            (int)v26);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
LABEL_30:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
          return Event;
        }
        v29 = 0;
        Event = NgcUtils::GetRegistryDwordValue(
                  (NgcUtils *)0xFFFFFFFF80000002LL,
                  v26,
                  (const unsigned __int16 *)&stru_18002B278,
                  (const unsigned __int16 *)&v29,
                  (unsigned int *)v26);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
      }
      if ( Event >= 0 )
      {
        Event = v29;
        if ( v29 >= 0 )
        {
          Event = 0;
          goto LABEL_30;
        }
        v22 = 616;
      }
      else
      {
        v22 = 614;
      }
      v21 = (unsigned int)Event;
    }
    else
    {
      v21 = (unsigned int)NgcStateSeparatedRegistryLocation;
      v22 = 590;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)v21,
      (int)v26);
    goto LABEL_30;
  }
  if ( v15 == -1 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x247,
             (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
             v16);
  else
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x248,
             (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
             (const char *)v15,
             (unsigned int)v26);
}

```

## disassembly

```asm
0x18001c508  mov     [rsp-18h+arg_0], rbx
0x18001c50d  mov     [rsp-18h+arg_10], rdi
0x18001c512  push    rbp
0x18001c513  push    r12
0x18001c515  push    r14
0x18001c517  mov     rbp, rsp
0x18001c51a  sub     rsp, 30h
0x18001c51e  mov     r14, r9
0x18001c521  mov     ebx, r8d
0x18001c524  lea     r12, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c52b  test    dl, dl
0x18001c52d  jnz     short loc_18001C54C
0x18001c52f  call    NgcTriggerTask
0x18001c534  mov     rcx, [rbp+18h]; this
0x18001c538  test    eax, eax
0x18001c53a  jns     short loc_18001C54C
0x18001c53c  mov     r9d, eax; char *
0x18001c53f  mov     r8, r12; unsigned int
0x18001c542  mov     edx, 228h; void *
0x18001c547  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c54c  cmp     [rbp+arg_20], 0
0x18001c550  jnz     short loc_18001C56F
0x18001c552  test    ebx, ebx
0x18001c554  jns     short loc_18001C56F
0x18001c556  mov     edx, 22Eh; void *
0x18001c55b  mov     r8, r12; unsigned int
0x18001c55e  mov     r9d, ebx; char *
0x18001c561  mov     rcx, [rbp+18h]; this
0x18001c565  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c56a  jmp     loc_18001C6EA
0x18001c56f  mov     rdi, [rbp+arg_30]
0x18001c573  cmp     qword ptr [rdi], 0
0x18001c577  jnz     short loc_18001C58E
0x18001c579  mov     rcx, rdi; void **
0x18001c57c  call    ?PregenGetEvent@@YAJPEAPEAX@Z; PregenGetEvent(void * *)
0x18001c581  mov     ebx, eax
0x18001c583  test    eax, eax
0x18001c585  jns     short loc_18001C58E
0x18001c587  mov     edx, 236h
0x18001c58c  jmp     short loc_18001C55B
0x18001c58e  mov     rax, [rbp+arg_28]
0x18001c592  mov     ebx, [rax]
0x18001c594  call    cs:__imp_GetTickCount
0x18001c59a  sub     eax, ebx
0x18001c59c  mov     edx, 3E8h
0x18001c5a1  cmp     eax, [rbp+arg_20]
0x18001c5a4  jnb     short loc_18001C5AB
0x18001c5a6  mov     edx, [rbp+arg_20]
0x18001c5a9  sub     edx, eax; dwMilliseconds
0x18001c5ab  mov     rcx, [rdi]; hHandle
0x18001c5ae  call    cs:__imp_WaitForSingleObject
0x18001c5b4  test    eax, eax
0x18001c5b6  jz      short loc_18001C5E5
0x18001c5b8  mov     rcx, [rbp+18h]; this
0x18001c5bc  mov     r8, r12; unsigned int
0x18001c5bf  cmp     eax, 0FFFFFFFFh
0x18001c5c2  jnz     short loc_18001C5D3
0x18001c5c4  mov     edx, 247h; void *
0x18001c5c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c5ce  jmp     loc_18001C6EC
0x18001c5d3  mov     r9d, eax; char *
0x18001c5d6  mov     edx, 248h; void *
0x18001c5db  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001c5e0  jmp     loc_18001C6EC
0x18001c5e5  mov     [rbp+var_8], 0
0x18001c5ed  xor     edx, edx
0x18001c5ef  lea     rcx, [rbp+var_8]
0x18001c5f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001c5f8  lea     r9, [rbp+var_8]; unsigned __int16 *
0x18001c5fc  mov     r8, r14; unsigned __int16 *
0x18001c5ff  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001c604  mov     ebx, eax
0x18001c606  test    eax, eax
0x18001c608  jns     short loc_18001C617
0x18001c60a  mov     r9d, eax
0x18001c60d  mov     edx, 24Eh
0x18001c612  jmp     loc_18001C6C3
0x18001c617  mov     [rbp+arg_8], 0
0x18001c61e  lea     r9, [rbp+arg_8]; unsigned __int16 *
0x18001c622  lea     r8, stru_18002B278; unsigned __int16 *
0x18001c629  mov     rdx, [rbp+var_8]; HKEY
0x18001c62d  mov     rdi, 0FFFFFFFF80000002h
0x18001c634  mov     rcx, rdi; this
0x18001c637  call    ?GetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1PEAK@Z; NgcUtils::GetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001c63c  mov     ebx, eax
0x18001c63e  cmp     eax, 80070002h
0x18001c643  jnz     short loc_18001C6B7
0x18001c645  mov     [rbp+var_10], 0
0x18001c64d  xor     edx, edx
0x18001c64f  lea     rcx, [rbp+var_10]
0x18001c653  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001c658  lea     r9, [rbp+var_10]; unsigned __int16 *
0x18001c65c  lea     r8, aPregenkeys; "PregenKeys"
0x18001c663  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001c668  mov     ebx, eax
0x18001c66a  test    eax, eax
0x18001c66c  jns     short loc_18001C68E
0x18001c66e  mov     rcx, [rbp+18h]; this
0x18001c672  mov     r9d, eax; char *
0x18001c675  mov     r8, r12; unsigned int
0x18001c678  mov     edx, 25Ch; void *
0x18001c67d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c682  nop
0x18001c683  lea     rcx, [rbp+var_10]
0x18001c687  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001c68c  jmp     short loc_18001C6E1
0x18001c68e  mov     [rbp+arg_8], 0
0x18001c695  lea     r9, [rbp+arg_8]; unsigned __int16 *
0x18001c699  lea     r8, stru_18002B278; unsigned __int16 *
0x18001c6a0  mov     rdx, [rbp+var_10]; HKEY
0x18001c6a4  mov     rcx, rdi; this
0x18001c6a7  call    ?GetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1PEAK@Z; NgcUtils::GetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001c6ac  mov     ebx, eax
0x18001c6ae  lea     rcx, [rbp+var_10]
0x18001c6b2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001c6b7  test    ebx, ebx
0x18001c6b9  jns     short loc_18001C6D1
0x18001c6bb  mov     edx, 266h; void *
0x18001c6c0  mov     r9d, ebx; char *
0x18001c6c3  mov     rcx, [rbp+18h]; this
0x18001c6c7  mov     r8, r12; unsigned int
0x18001c6ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c6cf  jmp     short loc_18001C6E1
0x18001c6d1  mov     ebx, [rbp+arg_8]
0x18001c6d4  test    ebx, ebx
0x18001c6d6  jns     short loc_18001C6DF
0x18001c6d8  mov     edx, 268h
0x18001c6dd  jmp     short loc_18001C6C0
0x18001c6df  xor     ebx, ebx
0x18001c6e1  lea     rcx, [rbp+var_8]
0x18001c6e5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001c6ea  mov     eax, ebx
0x18001c6ec  mov     rbx, [rsp+30h+arg_0]
0x18001c6f1  mov     rdi, [rsp+30h+arg_10]
0x18001c6f6  add     rsp, 30h
0x18001c6fa  pop     r14
0x18001c6fc  pop     r12
0x18001c6fe  pop     rbp
0x18001c6ff  retn
```
