# DIRLIST_CONFIG::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x180003590`
- end: `0x180003774`
- name: `?Initialize@DIRLIST_CONFIG@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(DIRLIST_CONFIG *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800037e8`

## callees

- `0x180003590`
- `0x180004010`

## string_xrefs

- `0x180003669`: `accessPolicy`
- `0x180003697`: `system.webServer/directoryBrowse`

## pseudocode

```c
__int64 __fastcall DIRLIST_CONFIG::Initialize(
        DIRLIST_CONFIG *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall ***v6)(_QWORD); // rax
  __int64 v7; // r14
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rax
  int v9; // ebx
  __int64 v11; // [rsp+40h] [rbp-10h] BYREF
  __int64 v12; // [rsp+78h] [rbp+28h] BYREF
  __int64 v13; // [rsp+88h] [rbp+38h] BYREF

  v3 = *(_QWORD *)a2;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v6 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160))(a2);
  v7 = (**v6)(v6);
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v9 = (**v8)(v8, &IID_INativeConfigurationSystem, &v11);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v11 + 24LL))(
           v11,
           L"system.webServer/handlers",
           v7,
           &v13,
           a3,
           0);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v13 + 48LL))(
             v13,
             L"accessPolicy",
             (char *)this + 8,
             0,
             0);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v11 + 24LL))(
               v11,
               L"system.webServer/directoryBrowse",
               v7,
               &v12,
               a3,
               0);
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v12 + 72LL))(
                 v12,
                 L"enabled",
                 (char *)this + 12,
                 0,
                 0);
          if ( v9 >= 0 )
            v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v12 + 48LL))(
                   v12,
                   L"showFlags",
                   (char *)this + 16,
                   0,
                   0);
        }
      }
    }
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003590  mov     [rsp-18h+arg_0], rbx
0x180003595  mov     [rsp-18h+arg_10], rsi
0x18000359a  push    rbp
0x18000359b  push    rdi
0x18000359c  push    r14
0x18000359e  mov     rbp, rsp
0x1800035a1  sub     rsp, 50h
0x1800035a5  mov     rax, [rdx]
0x1800035a8  mov     rdi, rcx
0x1800035ab  mov     rcx, rdx
0x1800035ae  mov     [rbp+var_10], 0
0x1800035b6  mov     rsi, r8
0x1800035b9  mov     [rbp+arg_8], 0
0x1800035c1  mov     [rbp+arg_18], 0
0x1800035c9  mov     rax, [rax+0A0h]
0x1800035d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035d5  mov     rcx, rax
0x1800035d8  mov     rdx, [rax]
0x1800035db  mov     rax, [rdx]
0x1800035de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e3  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800035ea  mov     r14, rax
0x1800035ed  mov     rdx, [rcx]
0x1800035f0  mov     rax, [rdx+38h]
0x1800035f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f9  mov     r9, rax
0x1800035fc  lea     r8, [rbp+var_10]
0x180003600  lea     rdx, IID_INativeConfigurationSystem
0x180003607  mov     rcx, [rax]
0x18000360a  mov     rax, [rcx]
0x18000360d  mov     rcx, r9
0x180003610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003615  mov     ebx, eax
0x180003617  test    eax, eax
0x180003619  js      loc_18000370E
0x18000361f  mov     rcx, [rbp+var_10]
0x180003623  lea     r9, [rbp+arg_18]
0x180003627  mov     [rsp+50h+var_28], 0
0x180003630  lea     rdx, aSystemWebserve_0; "system.webServer/handlers"
0x180003637  mov     r8, r14
0x18000363a  mov     [rsp+50h+var_30], rsi
0x18000363f  mov     rax, [rcx]
0x180003642  mov     rax, [rax+18h]
0x180003646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000364b  mov     ebx, eax
0x18000364d  test    eax, eax
0x18000364f  js      loc_18000370E
0x180003655  mov     rcx, [rbp+arg_18]
0x180003659  lea     r8, [rdi+8]
0x18000365d  xor     r9d, r9d
0x180003660  mov     [rsp+50h+var_30], 0
0x180003669  lea     rdx, aAccesspolicy; "accessPolicy"
0x180003670  mov     rax, [rcx]
0x180003673  mov     rax, [rax+30h]
0x180003677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000367c  mov     ebx, eax
0x18000367e  test    eax, eax
0x180003680  js      loc_18000370E
0x180003686  mov     rcx, [rbp+var_10]
0x18000368a  lea     r9, [rbp+arg_8]
0x18000368e  mov     [rsp+50h+var_28], 0
0x180003697  lea     rdx, aSystemWebserve; "system.webServer/directoryBrowse"
0x18000369e  mov     r8, r14
0x1800036a1  mov     [rsp+50h+var_30], rsi
0x1800036a6  mov     rax, [rcx]
0x1800036a9  mov     rax, [rax+18h]
0x1800036ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036b2  mov     ebx, eax
0x1800036b4  test    eax, eax
0x1800036b6  js      short loc_18000370E
0x1800036b8  mov     rcx, [rbp+arg_8]
0x1800036bc  lea     r8, [rdi+0Ch]
0x1800036c0  xor     r9d, r9d
0x1800036c3  mov     [rsp+50h+var_30], 0
0x1800036cc  lea     rdx, aEnabled; "enabled"
0x1800036d3  mov     rax, [rcx]
0x1800036d6  mov     rax, [rax+48h]
0x1800036da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036df  mov     ebx, eax
0x1800036e1  test    eax, eax
0x1800036e3  js      short loc_18000370E
0x1800036e5  mov     rcx, [rbp+arg_8]
0x1800036e9  lea     r8, [rdi+10h]
0x1800036ed  xor     r9d, r9d
0x1800036f0  mov     [rsp+50h+var_30], 0
0x1800036f9  lea     rdx, aShowflags; "showFlags"
0x180003700  mov     rax, [rcx]
0x180003703  mov     rax, [rax+30h]
0x180003707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000370c  mov     ebx, eax
0x18000370e  mov     rcx, [rbp+arg_8]
0x180003712  test    rcx, rcx
0x180003715  jz      short loc_18000372B
0x180003717  mov     rax, [rcx]
0x18000371a  mov     rax, [rax+10h]
0x18000371e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003723  mov     [rbp+arg_8], 0
0x18000372b  mov     rcx, [rbp+arg_18]
0x18000372f  test    rcx, rcx
0x180003732  jz      short loc_180003748
0x180003734  mov     rax, [rcx]
0x180003737  mov     rax, [rax+10h]
0x18000373b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003740  mov     [rbp+arg_18], 0
0x180003748  mov     rcx, [rbp+var_10]
0x18000374c  test    rcx, rcx
0x18000374f  jz      short loc_18000375D
0x180003751  mov     rax, [rcx]
0x180003754  mov     rax, [rax+10h]
0x180003758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000375d  lea     r11, [rsp+50h+var_s0]
0x180003762  mov     eax, ebx
0x180003764  mov     rbx, [r11+20h]
0x180003768  mov     rsi, [r11+30h]
0x18000376c  mov     rsp, r11
0x18000376f  pop     r14
0x180003771  pop     rdi
0x180003772  pop     rbp
0x180003773  retn
```
