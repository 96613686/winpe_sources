# META_SCRIPT_MAP_TABLE::Initialize(INativeConfigurationElement *,IHttpServer *,int,LANG_STRING *,char const *,ushort,STRU *,IHttpTraceContext *)

- ea: `0x180033b70`
- end: `0x18003407a`
- name: `?Initialize@META_SCRIPT_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@PEAVIHttpServer@@HPEAVLANG_STRING@@PEBDGPEAVSTRU@@PEAVIHttpTraceContext@@@Z`
- size: `1290`
- prototype: `__int64 __fastcall(META_SCRIPT_MAP_TABLE *this, struct INativeConfigurationElement *, struct IHttpServer *, unsigned int, struct LANG_STRING *, const char *, unsigned __int16, struct STRU *, struct IHttpTraceContext *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180033a40`

## callees

- `0x180008930`
- `0x180019558`
- `0x180033718`
- `0x180033b70`
- `0x180034080`
- `0x180035010`

## import_xrefs

- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x180033ed4`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x180033ed4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180033ebd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180033ec7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180033ee1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180033eee`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180033efb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180033ebd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180033ec7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180033ee1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180033eee`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180033efb`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x18003400d`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x18003400d`
- `iisutil!SAFE_snwprintf` at `0x180034026`
- `iisutil!SAFE_snwprintf` at `0x180034026`

## string_xrefs

- `0x180033e22`: `requireAccess`
- `0x180033e4f`: `allowPathInfo`

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
  char *v18; // rsi
  __int64 v19; // rax
  char *v20; // rdi
  bool v21; // zf
  char *v22; // rax
  char **v23; // rcx
  __int64 v24; // rcx
  struct STRU *v25; // rdi
  __int64 v27; // [rsp+68h] [rbp-61h] BYREF
  int v28; // [rsp+70h] [rbp-59h] BYREF
  int v29; // [rsp+74h] [rbp-55h] BYREF
  int v30; // [rsp+78h] [rbp-51h] BYREF
  int v31; // [rsp+7Ch] [rbp-4Dh] BYREF
  __int64 *v32; // [rsp+80h] [rbp-49h] BYREF
  unsigned __int16 *v33; // [rsp+88h] [rbp-41h] BYREF
  unsigned __int16 *v34; // [rsp+90h] [rbp-39h] BYREF
  unsigned int v35; // [rsp+98h] [rbp-31h] BYREF
  unsigned __int16 *v36; // [rsp+A0h] [rbp-29h] BYREF
  unsigned __int16 *v37; // [rsp+A8h] [rbp-21h] BYREF
  unsigned __int16 *v38; // [rsp+B0h] [rbp-19h] BYREF
  unsigned __int16 *v39; // [rsp+B8h] [rbp-11h] BYREF
  unsigned __int16 *v40; // [rsp+C0h] [rbp-9h] BYREF
  const unsigned __int16 *v41; // [rsp+C8h] [rbp-1h] BYREF
  int v42; // [rsp+110h] [rbp+47h] BYREF
  unsigned int v43; // [rsp+120h] [rbp+57h] BYREF

  v43 = a4;
  v9 = *(_QWORD *)a2;
  v32 = 0;
  v27 = 0;
  v33 = 0;
  v11 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 **))(v9 + 40);
  v34 = 0;
  v40 = 0;
  v39 = 0;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  v43 = 0;
  v42 = 0;
  v35 = 0;
  v41 = 0;
  v13 = v11(a2, &v32);
  if ( v13 >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v32 + 24))(v32, &v43);
    if ( v13 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v15 = *v32;
        if ( i >= v43 )
          break;
        v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v15 + 32))(v32, i, &v27);
        if ( v13 < 0 )
          goto LABEL_36;
        v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v27 + 64LL))(
                v27,
                L"name",
                &v34,
                0,
                0);
        if ( v13 < 0 )
          goto LABEL_36;
        v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v27 + 64LL))(
                v27,
                L"preCondition",
                &v33,
                0,
                0);
        if ( v13 < 0 )
          goto LABEL_36;
        v16 = (*(__int64 (__fastcall **)(struct IHttpServer *, unsigned __int16 *, int *))(*(_QWORD *)a3 + 176LL))(
                a3,
                v33,
                &v42);
        if ( v42 )
        {
          v25 = a8;
          v13 = -2147024883;
          if ( a8 && (int)LANG_STRING::GetString(a5, a6, a7, 0x31FEu, &v41, &v35) >= 0 )
            SAFE_snwprintf(v25, v41, v34, v33);
          goto LABEL_36;
        }
        if ( v16 )
        {
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v27 + 64LL))(
                  v27,
                  L"path",
                  &v40,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_36;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v27 + 64LL))(
                  v27,
                  L"verb",
                  &v39,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_36;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v27 + 64LL))(
                  v27,
                  L"modules",
                  &v38,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_36;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v27 + 64LL))(
                  v27,
                  L"scriptProcessor",
                  &v37,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_36;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v27 + 64LL))(
                  v27,
                  L"type",
                  &v36,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_36;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v27 + 48LL))(
                  v27,
                  L"resourceType",
                  &v31,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_36;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v27 + 48LL))(
                  v27,
                  L"requireAccess",
                  &v30,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_36;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v27 + 72LL))(
                  v27,
                  L"allowPathInfo",
                  &v29,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_36;
          v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v27 + 48LL))(
                  v27,
                  L"responseBufferLimit",
                  &v28,
                  0,
                  0);
          if ( v13 < 0 )
            goto LABEL_36;
          v18 = (char *)operator new(0x180u);
          if ( !v18 )
          {
            v13 = -2147024888;
            goto LABEL_36;
          }
          *(_QWORD *)v18 = &META_SCRIPT_MAP_ENTRY::`vftable';
          STRU::STRU((STRU *)(v18 + 24));
          STRU::STRU((STRU *)(v18 + 80));
          MULTISZA::MULTISZA((MULTISZA *)(v18 + 136));
          STRU::STRU((STRU *)(v18 + 192));
          STRU::STRU((STRU *)(v18 + 248));
          STRU::STRU((STRU *)(v18 + 304));
          *((_QWORD *)v18 + 46) = 0;
          *((_QWORD *)v18 + 2) = v18 + 8;
          *((_QWORD *)v18 + 1) = v18 + 8;
          v13 = META_SCRIPT_MAP_ENTRY::Create(
                  (META_SCRIPT_MAP_ENTRY *)v18,
                  v34,
                  v40,
                  v39,
                  v38,
                  v37,
                  v36,
                  v31,
                  v30,
                  v29,
                  v28);
          v19 = *(_QWORD *)v18;
          if ( v13 < 0 )
          {
            (*(void (__fastcall **)(char *, __int64))(v19 + 88))(v18, 1);
            goto LABEL_36;
          }
          v20 = v18 + 8;
          v21 = (*(unsigned int (__fastcall **)(char *))(v19 + 64))(v18) == 0;
          v22 = (char *)this + 24;
          if ( v21 )
            v22 = (char *)this + 8;
          v23 = (char **)*((_QWORD *)v22 + 1);
          if ( *v23 != v22 )
            __fastfail(3u);
          *(_QWORD *)v20 = v22;
          *((_QWORD *)v18 + 2) = v23;
          *v23 = v20;
          v24 = v27;
          *((_QWORD *)v22 + 1) = v20;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        else
        {
          if ( a9 )
          {
            if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(a9, 0, 4) )
              IISGeneralEvents::HANDLER_PRECONDITION_NOT_MATCH::RaiseEvent(a9, v17, v34, v33);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        v27 = 0;
      }
      goto LABEL_40;
    }
  }
LABEL_36:
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v32 )
  {
    v15 = *v32;
LABEL_40:
    (*(void (**)(void))(v15 + 16))();
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180033b70  mov     rax, rsp
0x180033b73  mov     [rax+8], rbx
0x180033b77  mov     [rax+18h], rsi
0x180033b7b  mov     [rax+20h], r9d
0x180033b7f  push    rbp
0x180033b80  push    rdi
0x180033b81  push    r12
0x180033b83  push    r13
0x180033b85  push    r14
0x180033b87  lea     rbp, [rax-37h]
0x180033b8b  sub     rsp, 0D0h
0x180033b92  mov     rax, [rdx]
0x180033b95  xor     edi, edi
0x180033b97  mov     r9, rdx
0x180033b9a  mov     [rbp+2Fh+var_78], rdi
0x180033b9e  mov     r13, rcx
0x180033ba1  mov     [rbp+2Fh+var_90], rdi
0x180033ba5  lea     rdx, [rbp+2Fh+var_78]
0x180033ba9  mov     [rbp+2Fh+var_70], rdi
0x180033bad  mov     rax, [rax+28h]
0x180033bb1  mov     rcx, r9
0x180033bb4  mov     r12, r8
0x180033bb7  mov     [rbp+2Fh+var_68], rdi
0x180033bbb  mov     [rbp+2Fh+var_38], rdi
0x180033bbf  mov     [rbp+2Fh+var_40], rdi
0x180033bc3  mov     [rbp+2Fh+var_48], rdi
0x180033bc7  mov     [rbp+2Fh+var_50], rdi
0x180033bcb  mov     [rbp+2Fh+var_58], rdi
0x180033bcf  mov     [rbp+2Fh+var_7C], edi
0x180033bd2  mov     [rbp+2Fh+var_80], edi
0x180033bd5  mov     [rbp+2Fh+var_84], edi
0x180033bd8  mov     [rbp+2Fh+var_88], edi
0x180033bdb  mov     [rbp+2Fh+arg_18], edi
0x180033bde  mov     [rbp+2Fh+arg_8], edi
0x180033be1  mov     [rbp+2Fh+var_60], edi
0x180033be4  mov     [rbp+2Fh+var_30], rdi
0x180033be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033bed  mov     ebx, eax
0x180033bef  test    eax, eax
0x180033bf1  js      loc_18003402E
0x180033bf7  mov     rcx, [rbp+2Fh+var_78]
0x180033bfb  lea     rdx, [rbp+2Fh+arg_18]
0x180033bff  mov     rax, [rcx]
0x180033c02  mov     rax, [rax+18h]
0x180033c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c0b  mov     ebx, eax
0x180033c0d  test    eax, eax
0x180033c0f  js      loc_18003402E
0x180033c15  mov     r14d, edi
0x180033c18  mov     rcx, [rbp+2Fh+var_78]
0x180033c1c  mov     rax, [rcx]
0x180033c1f  cmp     r14d, [rbp+2Fh+arg_18]
0x180033c23  jnb     loc_180034053
0x180033c29  mov     rax, [rax+20h]
0x180033c2d  lea     r8, [rbp+2Fh+var_90]
0x180033c31  mov     edx, r14d
0x180033c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c39  mov     ebx, eax
0x180033c3b  test    eax, eax
0x180033c3d  js      loc_18003402E
0x180033c43  mov     rcx, [rbp+2Fh+var_90]
0x180033c47  lea     r8, [rbp+2Fh+var_68]
0x180033c4b  xor     r9d, r9d
0x180033c4e  mov     [rsp+0F0h+var_D0], rdi
0x180033c53  lea     rdx, aName_0; "name"
0x180033c5a  mov     rax, [rcx]
0x180033c5d  mov     rax, [rax+40h]
0x180033c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c66  mov     ebx, eax
0x180033c68  test    eax, eax
0x180033c6a  js      loc_18003402E
0x180033c70  mov     rcx, [rbp+2Fh+var_90]
0x180033c74  lea     r8, [rbp+2Fh+var_70]
0x180033c78  xor     r9d, r9d
0x180033c7b  mov     [rsp+0F0h+var_D0], rdi
0x180033c80  lea     rdx, aPrecondition; "preCondition"
0x180033c87  mov     rax, [rcx]
0x180033c8a  mov     rax, [rax+40h]
0x180033c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c93  mov     ebx, eax
0x180033c95  test    eax, eax
0x180033c97  js      loc_18003402E
0x180033c9d  mov     rax, [r12]
0x180033ca1  lea     r8, [rbp+2Fh+arg_8]
0x180033ca5  mov     rdx, [rbp+2Fh+var_70]
0x180033ca9  mov     rcx, r12
0x180033cac  mov     rax, [rax+0B0h]
0x180033cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cb8  cmp     [rbp+2Fh+arg_8], edi
0x180033cbb  jnz     loc_180033FDA
0x180033cc1  test    eax, eax
0x180033cc3  jnz     short loc_180033D04
0x180033cc5  cmp     [rbp+2Fh+arg_40], rdi
0x180033cc9  jz      short loc_180033CEF
0x180033ccb  mov     rcx, [rbp+2Fh+arg_40]
0x180033ccf  lea     r8d, [rax+4]
0x180033cd3  xor     edx, edx
0x180033cd5  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180033cda  test    eax, eax
0x180033cdc  jz      short loc_180033CEF
0x180033cde  mov     r9, [rbp+2Fh+var_70]; unsigned __int16 *
0x180033ce2  mov     r8, [rbp+2Fh+var_68]; unsigned __int16 *
0x180033ce6  mov     rcx, [rbp+2Fh+arg_40]; struct IHttpTraceContext *
0x180033cea  call    ?RaiseEvent@HANDLER_PRECONDITION_NOT_MATCH@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG2@Z; IISGeneralEvents::HANDLER_PRECONDITION_NOT_MATCH::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ushort const *)
0x180033cef  mov     rcx, [rbp+2Fh+var_90]
0x180033cf3  mov     rax, [rcx]
0x180033cf6  mov     rax, [rax+10h]
0x180033cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cff  jmp     loc_180033FB0
0x180033d04  mov     rcx, [rbp+2Fh+var_90]
0x180033d08  lea     r8, [rbp+2Fh+var_38]
0x180033d0c  xor     r9d, r9d
0x180033d0f  mov     [rsp+0F0h+var_D0], rdi
0x180033d14  lea     rdx, aPath; "path"
0x180033d1b  mov     rax, [rcx]
0x180033d1e  mov     rax, [rax+40h]
0x180033d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d27  mov     ebx, eax
0x180033d29  test    eax, eax
0x180033d2b  js      loc_18003402E
0x180033d31  mov     rcx, [rbp+2Fh+var_90]
0x180033d35  lea     r8, [rbp+2Fh+var_40]
0x180033d39  xor     r9d, r9d
0x180033d3c  mov     [rsp+0F0h+var_D0], rdi
0x180033d41  lea     rdx, aVerb; "verb"
0x180033d48  mov     rax, [rcx]
0x180033d4b  mov     rax, [rax+40h]
0x180033d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d54  mov     ebx, eax
0x180033d56  test    eax, eax
0x180033d58  js      loc_18003402E
0x180033d5e  mov     rcx, [rbp+2Fh+var_90]
0x180033d62  lea     r8, [rbp+2Fh+var_48]
0x180033d66  xor     r9d, r9d
0x180033d69  mov     [rsp+0F0h+var_D0], rdi
0x180033d6e  lea     rdx, aModules; "modules"
0x180033d75  mov     rax, [rcx]
0x180033d78  mov     rax, [rax+40h]
0x180033d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033d81  mov     ebx, eax
0x180033d83  test    eax, eax
0x180033d85  js      loc_18003402E
0x180033d8b  mov     rcx, [rbp+2Fh+var_90]
0x180033d8f  lea     r8, [rbp+2Fh+var_50]
0x180033d93  xor     r9d, r9d
0x180033d96  mov     [rsp+0F0h+var_D0], rdi
0x180033d9b  lea     rdx, aScriptprocesso; "scriptProcessor"
0x180033da2  mov     rax, [rcx]
0x180033da5  mov     rax, [rax+40h]
0x180033da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033dae  mov     ebx, eax
0x180033db0  test    eax, eax
0x180033db2  js      loc_18003402E
0x180033db8  mov     rcx, [rbp+2Fh+var_90]
0x180033dbc  lea     r8, [rbp+2Fh+var_58]
0x180033dc0  xor     r9d, r9d
0x180033dc3  mov     [rsp+0F0h+var_D0], rdi
0x180033dc8  lea     rdx, aType; "type"
0x180033dcf  mov     rax, [rcx]
0x180033dd2  mov     rax, [rax+40h]
0x180033dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ddb  mov     ebx, eax
0x180033ddd  test    eax, eax
0x180033ddf  js      loc_18003402E
0x180033de5  mov     rcx, [rbp+2Fh+var_90]
0x180033de9  lea     r8, [rbp+2Fh+var_7C]
0x180033ded  xor     r9d, r9d
0x180033df0  mov     [rsp+0F0h+var_D0], rdi
0x180033df5  lea     rdx, aResourcetype; "resourceType"
0x180033dfc  mov     rax, [rcx]
0x180033dff  mov     rax, [rax+30h]
0x180033e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e08  mov     ebx, eax
0x180033e0a  test    eax, eax
0x180033e0c  js      loc_18003402E
0x180033e12  mov     rcx, [rbp+2Fh+var_90]
0x180033e16  lea     r8, [rbp+2Fh+var_80]
0x180033e1a  xor     r9d, r9d
0x180033e1d  mov     [rsp+0F0h+var_D0], rdi
0x180033e22  lea     rdx, aRequireaccess; "requireAccess"
0x180033e29  mov     rax, [rcx]
0x180033e2c  mov     rax, [rax+30h]
0x180033e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e35  mov     ebx, eax
0x180033e37  test    eax, eax
0x180033e39  js      loc_18003402E
0x180033e3f  mov     rcx, [rbp+2Fh+var_90]
0x180033e43  lea     r8, [rbp+2Fh+var_84]
0x180033e47  xor     r9d, r9d
0x180033e4a  mov     [rsp+0F0h+var_D0], rdi
0x180033e4f  lea     rdx, aAllowpathinfo; "allowPathInfo"
0x180033e56  mov     rax, [rcx]
0x180033e59  mov     rax, [rax+48h]
0x180033e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e62  mov     ebx, eax
0x180033e64  test    eax, eax
0x180033e66  js      loc_18003402E
0x180033e6c  mov     rcx, [rbp+2Fh+var_90]
0x180033e70  lea     r8, [rbp+2Fh+var_88]
0x180033e74  xor     r9d, r9d
0x180033e77  mov     [rsp+0F0h+var_D0], rdi
0x180033e7c  lea     rdx, aResponsebuffer; "responseBufferLimit"
0x180033e83  mov     rax, [rcx]
0x180033e86  mov     rax, [rax+30h]
0x180033e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e8f  mov     ebx, eax
0x180033e91  test    eax, eax
0x180033e93  js      loc_18003402E
0x180033e99  mov     ecx, 180h; Size
0x180033e9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033ea3  mov     rsi, rax
0x180033ea6  test    rax, rax
0x180033ea9  jz      loc_180033FD3
0x180033eaf  lea     rax, ??_7META_SCRIPT_MAP_ENTRY@@6B@; const META_SCRIPT_MAP_ENTRY::`vftable'
0x180033eb6  lea     rcx, [rsi+18h]
0x180033eba  mov     [rsi], rax
0x180033ebd  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180033ec3  lea     rcx, [rsi+50h]
0x180033ec7  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180033ecd  lea     rcx, [rsi+88h]
0x180033ed4  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x180033eda  lea     rcx, [rsi+0C0h]
0x180033ee1  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180033ee7  lea     rcx, [rsi+0F8h]
0x180033eee  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180033ef4  lea     rcx, [rsi+130h]
0x180033efb  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180033f01  mov     qword ptr [rsi+170h], 0
0x180033f0c  lea     rax, [rsi+8]
0x180033f10  mov     [rsi+10h], rax
0x180033f14  mov     rcx, rsi; this
0x180033f17  mov     [rax], rax
0x180033f1a  mov     eax, [rbp+2Fh+var_88]
0x180033f1d  mov     r9, [rbp+2Fh+var_40]; unsigned __int16 *
0x180033f21  mov     r8, [rbp+2Fh+var_38]; unsigned __int16 *
0x180033f25  mov     rdx, [rbp+2Fh+var_68]; unsigned __int16 *
0x180033f29  mov     [rsp+0F0h+var_A0], eax; int
0x180033f2d  mov     eax, [rbp+2Fh+var_84]
0x180033f30  mov     [rsp+0F0h+var_A8], eax; int
0x180033f34  mov     eax, [rbp+2Fh+var_80]
0x180033f37  mov     [rsp+0F0h+var_B0], eax; int
0x180033f3b  mov     eax, [rbp+2Fh+var_7C]
0x180033f3e  mov     [rsp+0F0h+var_B8], eax; int
0x180033f42  mov     rax, [rbp+2Fh+var_58]
0x180033f46  mov     [rsp+0F0h+var_C0], rax; unsigned __int16 *
0x180033f4b  mov     rax, [rbp+2Fh+var_50]
0x180033f4f  mov     [rsp+0F0h+var_C8], rax; unsigned __int16 *
0x180033f54  mov     rax, [rbp+2Fh+var_48]
0x180033f58  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x180033f5d  call    ?Create@META_SCRIPT_MAP_ENTRY@@QEAAJPEBG00000JJHJ@Z; META_SCRIPT_MAP_ENTRY::Create(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,long,long,int,long)
0x180033f62  mov     ebx, eax
0x180033f64  mov     rcx, rsi
0x180033f67  mov     rax, [rsi]
0x180033f6a  test    ebx, ebx
0x180033f6c  js      short loc_180033FC3
0x180033f6e  mov     rax, [rax+40h]
0x180033f72  lea     rdi, [rsi+8]
0x180033f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f7b  test    eax, eax
0x180033f7d  lea     rax, [r13+18h]
0x180033f81  jnz     short loc_180033F87
0x180033f83  lea     rax, [r13+8]
0x180033f87  mov     rcx, [rax+8]
0x180033f8b  cmp     [rcx], rax
0x180033f8e  jnz     short loc_180033FBC
0x180033f90  mov     [rdi], rax
0x180033f93  mov     [rdi+8], rcx
0x180033f97  mov     [rcx], rdi
0x180033f9a  mov     rcx, [rbp+2Fh+var_90]
0x180033f9e  mov     [rax+8], rdi
0x180033fa2  mov     rax, [rcx]
0x180033fa5  mov     rax, [rax+10h]
0x180033fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033fae  xor     edi, edi
0x180033fb0  mov     [rbp+2Fh+var_90], rdi
0x180033fb4  inc     r14d
0x180033fb7  jmp     loc_180033C18
0x180033fbc  mov     ecx, 3
0x180033fc1  int     29h; Win8: RtlFailFast(ecx)
0x180033fc3  mov     rax, [rax+58h]
0x180033fc7  mov     edx, 1
0x180033fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033fd1  jmp     short loc_18003402E
0x180033fd3  mov     ebx, 80070008h
0x180033fd8  jmp     short loc_18003402E
0x180033fda  mov     rdi, [rbp+2Fh+arg_38]
0x180033fde  mov     ebx, 8007000Dh
0x180033fe3  test    rdi, rdi
0x180033fe6  jz      short loc_18003402C
0x180033fe8  movzx   r8d, [rbp+2Fh+arg_30]
0x180033fed  lea     rax, [rbp+2Fh+var_60]
0x180033ff1  mov     rdx, [rbp+2Fh+arg_28]
0x180033ff5  mov     r9d, 31FEh
0x180033ffb  mov     rcx, [rbp+2Fh+arg_20]
0x180033fff  mov     [rsp+0F0h+var_C8], rax
0x180034004  lea     rax, [rbp+2Fh+var_30]
0x180034008  mov     [rsp+0F0h+var_D0], rax
0x18003400d  call    cs:__imp_?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z; LANG_STRING::GetString(char const *,ulong,uint,ushort const * *,ulong *)
0x180034013  test    eax, eax
0x180034015  js      short loc_18003402C
  ... truncated ...
```
