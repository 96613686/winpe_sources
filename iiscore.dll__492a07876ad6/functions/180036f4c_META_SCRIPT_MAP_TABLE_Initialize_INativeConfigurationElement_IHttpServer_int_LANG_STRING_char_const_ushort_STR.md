# META_SCRIPT_MAP_TABLE::Initialize(INativeConfigurationElement *,IHttpServer *,int,LANG_STRING *,char const *,ushort,STRU *,IHttpTraceContext *)

- ea: `0x180036f4c`
- end: `0x18003740c`
- name: `?Initialize@META_SCRIPT_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@PEAVIHttpServer@@HPEAVLANG_STRING@@PEBDGPEAVSTRU@@PEAVIHttpTraceContext@@@Z`
- size: `1216`
- prototype: `__int64 __fastcall(META_SCRIPT_MAP_TABLE *this, struct INativeConfigurationElement *, struct IHttpServer *, unsigned int, struct LANG_STRING *, const char *, unsigned __int16, struct STRU *, struct IHttpTraceContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180036e10`

## callees

- `0x180009030`
- `0x18001ab30`
- `0x180036818`
- `0x180036a38`
- `0x180036f4c`
- `0x180037414`
- `0x180038010`

## import_xrefs

- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180037392`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180037392`
- `iisutil!SAFE_snwprintf` at `0x1800373b1`
- `iisutil!SAFE_snwprintf` at `0x1800373b1`

## string_xrefs

- `0x1800371fe`: `requireAccess`
- `0x18003722b`: `allowPathInfo`

## pseudocode

```c
__int64 __fastcall META_SCRIPT_MAP_TABLE::Initialize(
        META_SCRIPT_MAP_TABLE *this,
        struct INativeConfigurationElement *a2,
        struct IHttpServer *a3,
        unsigned int a4,
        struct LANG_STRING *a5,
        const char *a6,
        unsigned __int16 a7,
        struct STRU *a8,
        struct IHttpTraceContext *a9)
{
  __int64 v9; // rax
  __int64 (__fastcall *v11)(struct INativeConfigurationElement *, __int64 **); // rax
  int v13; // ebx
  unsigned int i; // r14d
  __int64 v15; // rax
  int v16; // eax
  const struct _GUID *v17; // rdx
  META_SCRIPT_MAP_ENTRY *v18; // rax
  META_SCRIPT_MAP_ENTRY *v19; // rsi
  __int64 v20; // rax
  char *v21; // rdi
  bool v22; // zf
  char *v23; // rax
  char **v24; // rcx
  __int64 v25; // rcx
  struct STRU *v26; // rdi
  __int64 v28; // [rsp+68h] [rbp-61h] BYREF
  int v29; // [rsp+70h] [rbp-59h] BYREF
  int v30; // [rsp+74h] [rbp-55h] BYREF
  int v31; // [rsp+78h] [rbp-51h] BYREF
  int v32; // [rsp+7Ch] [rbp-4Dh] BYREF
  __int64 *v33; // [rsp+80h] [rbp-49h] BYREF
  unsigned __int16 *v34; // [rsp+88h] [rbp-41h] BYREF
  unsigned __int16 *v35; // [rsp+90h] [rbp-39h] BYREF
  unsigned int v36; // [rsp+98h] [rbp-31h] BYREF
  unsigned __int16 *v37; // [rsp+A0h] [rbp-29h] BYREF
  unsigned __int16 *v38; // [rsp+A8h] [rbp-21h] BYREF
  unsigned __int16 *v39; // [rsp+B0h] [rbp-19h] BYREF
  unsigned __int16 *v40; // [rsp+B8h] [rbp-11h] BYREF
  unsigned __int16 *v41; // [rsp+C0h] [rbp-9h] BYREF
  const unsigned __int16 *v42; // [rsp+C8h] [rbp-1h] BYREF
  int v43; // [rsp+110h] [rbp+47h] BYREF
  unsigned int v44; // [rsp+120h] [rbp+57h] BYREF

  v44 = a4;
  v9 = *(_QWORD *)a2;
  v33 = 0;
  v28 = 0;
  v34 = 0;
  v11 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 **))(v9 + 40);
  v35 = 0;
  v41 = 0;
  v40 = 0;
  v39 = 0;
  v38 = 0;
  v37 = 0;
  v32 = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  v44 = 0;
  v43 = 0;
  v36 = 0;
  v42 = 0;
  v13 = v11(a2, &v33);
  if ( v13 >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v33 + 24))(v33, &v44);
    if ( v13 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v15 = *v33;
        if ( i >= v44 )
          break;
        v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v15 + 32))(v33, i, &v28);
        if ( v13 < 0 )
          goto LABEL_37;
        v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v28 + 64LL))(
                v28,
                L"name",
                &v35,
                0,
                0);
        if ( v13 < 0 )
          goto LABEL_37;
        v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v28 + 64LL))(
                v28,
                L"preCondition",
                &v34,
                0,
                0);
        if ( v13 < 0 )
          goto LABEL_37;
        v16 = (*(__int64 (__fastcall **)(struct IHttpServer *, unsigned __int16 *, int *))(*(_QWORD *)a3 + 176LL))(
                a3,
                v34,
                &v43);
        if ( v43 )
        {
          v26 = a8;
          v13 = -2147024883;
          if ( a8 && (int)LANG_STRING::GetString(a5, a6, a7, 0x31FEu, &v42, &v36) >= 0 )
            SAFE_snwprintf(v26, v42, v35, v34);
          goto LABEL_37;
        }
        if ( v16 )
        {
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v28 + 64LL))(
                  v28,
                  L"path",
                  &v41,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_37;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v28 + 64LL))(
                  v28,
                  L"verb",
                  &v40,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_37;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v28 + 64LL))(
                  v28,
                  L"modules",
                  &v39,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_37;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v28 + 64LL))(
                  v28,
                  L"scriptProcessor",
                  &v38,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_37;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v28 + 64LL))(
                  v28,
                  L"type",
                  &v37,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_37;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
                  v28,
                  L"resourceType",
                  &v32,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_37;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
                  v28,
                  L"requireAccess",
                  &v31,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_37;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 72LL))(
                  v28,
                  L"allowPathInfo",
                  &v30,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_37;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v28 + 48LL))(
                  v28,
                  L"responseBufferLimit",
                  &v29,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_37;
          v18 = (META_SCRIPT_MAP_ENTRY *)operator new(0x180u);
          if ( !v18 || (v19 = META_SCRIPT_MAP_ENTRY::META_SCRIPT_MAP_ENTRY(v18)) == 0 )
          {
            v13 = -2147024888;
            goto LABEL_37;
          }
          v13 = META_SCRIPT_MAP_ENTRY::Create(v19, v35, v41, v40, v39, v38, v37, v32, v31, v30, v29);
          v20 = *(_QWORD *)v19;
          if ( v13 < 0 )
          {
            (*(void (__fastcall **)(META_SCRIPT_MAP_ENTRY *, __int64))(v20 + 88))(v19, 1);
            goto LABEL_37;
          }
          v21 = (char *)v19 + 8;
          v22 = (*(unsigned int (__fastcall **)(META_SCRIPT_MAP_ENTRY *))(v20 + 64))(v19) == 0;
          v23 = (char *)this + 24;
          if ( v22 )
            v23 = (char *)this + 8;
          v24 = (char **)*((_QWORD *)v23 + 1);
          if ( *v24 != v23 )
            __fastfail(3u);
          *(_QWORD *)v21 = v23;
          *((_QWORD *)v19 + 2) = v24;
          *v24 = v21;
          v25 = v28;
          *((_QWORD *)v23 + 1) = v21;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
        else
        {
          if ( a9 )
          {
            if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(a9, 0, 4) )
              IISGeneralEvents::HANDLER_PRECONDITION_NOT_MATCH::RaiseEvent(a9, v17, v35, v34);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        }
        v28 = 0;
      }
      goto LABEL_41;
    }
  }
LABEL_37:
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v33 )
  {
    v15 = *v33;
LABEL_41:
    (*(void (**)(void))(v15 + 16))();
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180036f4c  mov     rax, rsp
0x180036f4f  mov     [rax+8], rbx
0x180036f53  mov     [rax+18h], rsi
0x180036f57  mov     [rax+20h], r9d
0x180036f5b  push    rbp
0x180036f5c  push    rdi
0x180036f5d  push    r12
0x180036f5f  push    r13
0x180036f61  push    r14
0x180036f63  lea     rbp, [rax-37h]
0x180036f67  sub     rsp, 0D0h
0x180036f6e  mov     rax, [rdx]
0x180036f71  xor     edi, edi
0x180036f73  mov     r9, rdx
0x180036f76  mov     [rbp+2Fh+var_78], rdi
0x180036f7a  mov     r13, rcx
0x180036f7d  mov     [rbp+2Fh+var_90], rdi
0x180036f81  lea     rdx, [rbp+2Fh+var_78]
0x180036f85  mov     [rbp+2Fh+var_70], rdi
0x180036f89  mov     rax, [rax+28h]
0x180036f8d  mov     rcx, r9
0x180036f90  mov     r12, r8
0x180036f93  mov     [rbp+2Fh+var_68], rdi
0x180036f97  mov     [rbp+2Fh+var_38], rdi
0x180036f9b  mov     [rbp+2Fh+var_40], rdi
0x180036f9f  mov     [rbp+2Fh+var_48], rdi
0x180036fa3  mov     [rbp+2Fh+var_50], rdi
0x180036fa7  mov     [rbp+2Fh+var_58], rdi
0x180036fab  mov     [rbp+2Fh+var_7C], edi
0x180036fae  mov     [rbp+2Fh+var_80], edi
0x180036fb1  mov     [rbp+2Fh+var_84], edi
0x180036fb4  mov     [rbp+2Fh+var_88], edi
0x180036fb7  mov     [rbp+2Fh+arg_18], edi
0x180036fba  mov     [rbp+2Fh+arg_8], edi
0x180036fbd  mov     [rbp+2Fh+var_60], edi
0x180036fc0  mov     [rbp+2Fh+var_30], rdi
0x180036fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fc9  mov     ebx, eax
0x180036fcb  test    eax, eax
0x180036fcd  js      loc_1800373BF
0x180036fd3  mov     rcx, [rbp+2Fh+var_78]
0x180036fd7  lea     rdx, [rbp+2Fh+arg_18]
0x180036fdb  mov     rax, [rcx]
0x180036fde  mov     rax, [rax+18h]
0x180036fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fe7  mov     ebx, eax
0x180036fe9  test    eax, eax
0x180036feb  js      loc_1800373BF
0x180036ff1  mov     r14d, edi
0x180036ff4  mov     rcx, [rbp+2Fh+var_78]
0x180036ff8  mov     rax, [rcx]
0x180036ffb  cmp     r14d, [rbp+2Fh+arg_18]
0x180036fff  jnb     loc_1800373E4
0x180037005  mov     rax, [rax+20h]
0x180037009  lea     r8, [rbp+2Fh+var_90]
0x18003700d  mov     edx, r14d
0x180037010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037015  mov     ebx, eax
0x180037017  test    eax, eax
0x180037019  js      loc_1800373BF
0x18003701f  mov     rcx, [rbp+2Fh+var_90]
0x180037023  lea     r8, [rbp+2Fh+var_68]
0x180037027  xor     r9d, r9d
0x18003702a  mov     [rsp+0F0h+var_D0], rdi
0x18003702f  lea     rdx, aName_0; "name"
0x180037036  mov     rax, [rcx]
0x180037039  mov     rax, [rax+40h]
0x18003703d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037042  mov     ebx, eax
0x180037044  test    eax, eax
0x180037046  js      loc_1800373BF
0x18003704c  mov     rcx, [rbp+2Fh+var_90]
0x180037050  lea     r8, [rbp+2Fh+var_70]
0x180037054  xor     r9d, r9d
0x180037057  mov     [rsp+0F0h+var_D0], rdi
0x18003705c  lea     rdx, aPrecondition; "preCondition"
0x180037063  mov     rax, [rcx]
0x180037066  mov     rax, [rax+40h]
0x18003706a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003706f  mov     ebx, eax
0x180037071  test    eax, eax
0x180037073  js      loc_1800373BF
0x180037079  mov     rax, [r12]
0x18003707d  lea     r8, [rbp+2Fh+arg_8]
0x180037081  mov     rdx, [rbp+2Fh+var_70]
0x180037085  mov     rcx, r12
0x180037088  mov     rax, [rax+0B0h]
0x18003708f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037094  cmp     [rbp+2Fh+arg_8], edi
0x180037097  jnz     loc_18003735F
0x18003709d  test    eax, eax
0x18003709f  jnz     short loc_1800370E0
0x1800370a1  cmp     [rbp+2Fh+arg_40], rdi
0x1800370a5  jz      short loc_1800370CB
0x1800370a7  mov     rcx, [rbp+2Fh+arg_40]
0x1800370ab  lea     r8d, [rax+4]
0x1800370af  xor     edx, edx
0x1800370b1  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800370b6  test    eax, eax
0x1800370b8  jz      short loc_1800370CB
0x1800370ba  mov     r9, [rbp+2Fh+var_70]; unsigned __int16 *
0x1800370be  mov     r8, [rbp+2Fh+var_68]; unsigned __int16 *
0x1800370c2  mov     rcx, [rbp+2Fh+arg_40]; struct IHttpTraceContext *
0x1800370c6  call    ?RaiseEvent@HANDLER_PRECONDITION_NOT_MATCH@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG2@Z; IISGeneralEvents::HANDLER_PRECONDITION_NOT_MATCH::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ushort const *)
0x1800370cb  mov     rcx, [rbp+2Fh+var_90]
0x1800370cf  mov     rax, [rcx]
0x1800370d2  mov     rax, [rax+10h]
0x1800370d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800370db  jmp     loc_180037335
0x1800370e0  mov     rcx, [rbp+2Fh+var_90]
0x1800370e4  lea     r8, [rbp+2Fh+var_38]
0x1800370e8  xor     r9d, r9d
0x1800370eb  mov     [rsp+0F0h+var_D0], rdi
0x1800370f0  lea     rdx, aPath; "path"
0x1800370f7  mov     rax, [rcx]
0x1800370fa  mov     rax, [rax+40h]
0x1800370fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037103  mov     ebx, eax
0x180037105  test    eax, eax
0x180037107  js      loc_1800373BF
0x18003710d  mov     rcx, [rbp+2Fh+var_90]
0x180037111  lea     r8, [rbp+2Fh+var_40]
0x180037115  xor     r9d, r9d
0x180037118  mov     [rsp+0F0h+var_D0], rdi
0x18003711d  lea     rdx, aVerb; "verb"
0x180037124  mov     rax, [rcx]
0x180037127  mov     rax, [rax+40h]
0x18003712b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037130  mov     ebx, eax
0x180037132  test    eax, eax
0x180037134  js      loc_1800373BF
0x18003713a  mov     rcx, [rbp+2Fh+var_90]
0x18003713e  lea     r8, [rbp+2Fh+var_48]
0x180037142  xor     r9d, r9d
0x180037145  mov     [rsp+0F0h+var_D0], rdi
0x18003714a  lea     rdx, aModules; "modules"
0x180037151  mov     rax, [rcx]
0x180037154  mov     rax, [rax+40h]
0x180037158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003715d  mov     ebx, eax
0x18003715f  test    eax, eax
0x180037161  js      loc_1800373BF
0x180037167  mov     rcx, [rbp+2Fh+var_90]
0x18003716b  lea     r8, [rbp+2Fh+var_50]
0x18003716f  xor     r9d, r9d
0x180037172  mov     [rsp+0F0h+var_D0], rdi
0x180037177  lea     rdx, aScriptprocesso; "scriptProcessor"
0x18003717e  mov     rax, [rcx]
0x180037181  mov     rax, [rax+40h]
0x180037185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003718a  mov     ebx, eax
0x18003718c  test    eax, eax
0x18003718e  js      loc_1800373BF
0x180037194  mov     rcx, [rbp+2Fh+var_90]
0x180037198  lea     r8, [rbp+2Fh+var_58]
0x18003719c  xor     r9d, r9d
0x18003719f  mov     [rsp+0F0h+var_D0], rdi
0x1800371a4  lea     rdx, aType; "type"
0x1800371ab  mov     rax, [rcx]
0x1800371ae  mov     rax, [rax+40h]
0x1800371b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371b7  mov     ebx, eax
0x1800371b9  test    eax, eax
0x1800371bb  js      loc_1800373BF
0x1800371c1  mov     rcx, [rbp+2Fh+var_90]
0x1800371c5  lea     r8, [rbp+2Fh+var_7C]
0x1800371c9  xor     r9d, r9d
0x1800371cc  mov     [rsp+0F0h+var_D0], rdi
0x1800371d1  lea     rdx, aResourcetype; "resourceType"
0x1800371d8  mov     rax, [rcx]
0x1800371db  mov     rax, [rax+30h]
0x1800371df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371e4  mov     ebx, eax
0x1800371e6  test    eax, eax
0x1800371e8  js      loc_1800373BF
0x1800371ee  mov     rcx, [rbp+2Fh+var_90]
0x1800371f2  lea     r8, [rbp+2Fh+var_80]
0x1800371f6  xor     r9d, r9d
0x1800371f9  mov     [rsp+0F0h+var_D0], rdi
0x1800371fe  lea     rdx, aRequireaccess; "requireAccess"
0x180037205  mov     rax, [rcx]
0x180037208  mov     rax, [rax+30h]
0x18003720c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037211  mov     ebx, eax
0x180037213  test    eax, eax
0x180037215  js      loc_1800373BF
0x18003721b  mov     rcx, [rbp+2Fh+var_90]
0x18003721f  lea     r8, [rbp+2Fh+var_84]
0x180037223  xor     r9d, r9d
0x180037226  mov     [rsp+0F0h+var_D0], rdi
0x18003722b  lea     rdx, aAllowpathinfo; "allowPathInfo"
0x180037232  mov     rax, [rcx]
0x180037235  mov     rax, [rax+48h]
0x180037239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003723e  mov     ebx, eax
0x180037240  test    eax, eax
0x180037242  js      loc_1800373BF
0x180037248  mov     rcx, [rbp+2Fh+var_90]
0x18003724c  lea     r8, [rbp+2Fh+var_88]
0x180037250  xor     r9d, r9d
0x180037253  mov     [rsp+0F0h+var_D0], rdi
0x180037258  lea     rdx, aResponsebuffer; "responseBufferLimit"
0x18003725f  mov     rax, [rcx]
0x180037262  mov     rax, [rax+30h]
0x180037266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003726b  mov     ebx, eax
0x18003726d  test    eax, eax
0x18003726f  js      loc_1800373BF
0x180037275  mov     ecx, 180h; Size
0x18003727a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003727f  test    rax, rax
0x180037282  jz      loc_180037358
0x180037288  mov     rcx, rax; this
0x18003728b  call    ??0META_SCRIPT_MAP_ENTRY@@QEAA@XZ; META_SCRIPT_MAP_ENTRY::META_SCRIPT_MAP_ENTRY(void)
0x180037290  mov     rsi, rax
0x180037293  test    rax, rax
0x180037296  jz      loc_180037358
0x18003729c  mov     ecx, [rbp+2Fh+var_88]
0x18003729f  mov     rax, [rbp+2Fh+var_48]
0x1800372a3  mov     r9, [rbp+2Fh+var_40]; unsigned __int16 *
0x1800372a7  mov     r8, [rbp+2Fh+var_38]; unsigned __int16 *
0x1800372ab  mov     rdx, [rbp+2Fh+var_68]; unsigned __int16 *
0x1800372af  mov     [rsp+0F0h+var_A0], ecx; int
0x1800372b3  mov     ecx, [rbp+2Fh+var_84]
0x1800372b6  mov     [rsp+0F0h+var_A8], ecx; int
0x1800372ba  mov     ecx, [rbp+2Fh+var_80]
0x1800372bd  mov     [rsp+0F0h+var_B0], ecx; int
0x1800372c1  mov     ecx, [rbp+2Fh+var_7C]
0x1800372c4  mov     [rsp+0F0h+var_B8], ecx; int
0x1800372c8  mov     rcx, [rbp+2Fh+var_58]
0x1800372cc  mov     [rsp+0F0h+var_C0], rcx; unsigned __int16 *
0x1800372d1  mov     rcx, [rbp+2Fh+var_50]
0x1800372d5  mov     [rsp+0F0h+var_C8], rcx; unsigned __int16 *
0x1800372da  mov     rcx, rsi; this
0x1800372dd  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x1800372e2  call    ?Create@META_SCRIPT_MAP_ENTRY@@QEAAJPEBG00000JJHJ@Z; META_SCRIPT_MAP_ENTRY::Create(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,long,long,int,long)
0x1800372e7  mov     ebx, eax
0x1800372e9  mov     rcx, rsi
0x1800372ec  mov     rax, [rsi]
0x1800372ef  test    ebx, ebx
0x1800372f1  js      short loc_180037348
0x1800372f3  mov     rax, [rax+40h]
0x1800372f7  lea     rdi, [rsi+8]
0x1800372fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037300  test    eax, eax
0x180037302  lea     rax, [r13+18h]
0x180037306  jnz     short loc_18003730C
0x180037308  lea     rax, [r13+8]
0x18003730c  mov     rcx, [rax+8]
0x180037310  cmp     [rcx], rax
0x180037313  jnz     short loc_180037341
0x180037315  mov     [rdi], rax
0x180037318  mov     [rdi+8], rcx
0x18003731c  mov     [rcx], rdi
0x18003731f  mov     rcx, [rbp+2Fh+var_90]
0x180037323  mov     [rax+8], rdi
0x180037327  mov     rax, [rcx]
0x18003732a  mov     rax, [rax+10h]
0x18003732e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037333  xor     edi, edi
0x180037335  mov     [rbp+2Fh+var_90], rdi
0x180037339  inc     r14d
0x18003733c  jmp     loc_180036FF4
0x180037341  mov     ecx, 3
0x180037346  int     29h; Win8: RtlFailFast(ecx)
0x180037348  mov     rax, [rax+58h]
0x18003734c  mov     edx, 1
0x180037351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037356  jmp     short loc_1800373BF
0x180037358  mov     ebx, 80070008h
0x18003735d  jmp     short loc_1800373BF
0x18003735f  mov     rdi, [rbp+2Fh+arg_38]
0x180037363  mov     ebx, 8007000Dh
0x180037368  test    rdi, rdi
0x18003736b  jz      short loc_1800373BD
0x18003736d  movzx   r8d, [rbp+2Fh+arg_30]
0x180037372  lea     rax, [rbp+2Fh+var_60]
0x180037376  mov     rdx, [rbp+2Fh+arg_28]
0x18003737a  mov     r9d, 31FEh
0x180037380  mov     rcx, [rbp+2Fh+arg_20]
0x180037384  mov     [rsp+0F0h+var_C8], rax
0x180037389  lea     rax, [rbp+2Fh+var_30]
0x18003738d  mov     [rsp+0F0h+var_D0], rax
0x180037392  call    cs:__imp_?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z; LANG_STRING::GetString(char const *,ulong,uint,ushort const * *,ulong *)
0x180037399  nop     dword ptr [rax+rax+00h]
0x18003739e  test    eax, eax
0x1800373a0  js      short loc_1800373BD
0x1800373a2  mov     r9, [rbp+2Fh+var_70]
0x1800373a6  mov     rcx, rdi
0x1800373a9  mov     r8, [rbp+2Fh+var_68]
0x1800373ad  mov     rdx, [rbp+2Fh+var_30]
0x1800373b1  call    cs:__imp_?SAFE_snwprintf@@YAJPEAVSTRU@@PEBGZZ; SAFE_snwprintf(STRU *,ushort const *,...)
0x1800373b8  nop     dword ptr [rax+rax+00h]
0x1800373bd  xor     edi, edi
0x1800373bf  mov     rcx, [rbp+2Fh+var_90]
0x1800373c3  test    rcx, rcx
0x1800373c6  jz      short loc_1800373D8
0x1800373c8  mov     rax, [rcx]
0x1800373cb  mov     rax, [rax+10h]
0x1800373cf  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
