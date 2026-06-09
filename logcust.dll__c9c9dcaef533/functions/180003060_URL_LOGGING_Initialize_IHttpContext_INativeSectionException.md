# URL_LOGGING::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x180003060`
- end: `0x1800031b1`
- name: `?Initialize@URL_LOGGING@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(URL_LOGGING *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002378`

## callees

- `0x180003060`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall URL_LOGGING::Initialize(
        URL_LOGGING *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall ***v6)(_QWORD); // rax
  __int64 v7; // rbp
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rax
  int v9; // ebx
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF

  v3 = *(_QWORD *)a2;
  v12 = 0;
  v11 = 0;
  v6 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160))(a2);
  v7 = (**v6)(v6);
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v9 = (**v8)(v8, &IID_INativeConfigurationSystem, &v12);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v12 + 24LL))(
           v12,
           L"system.webServer/httpLogging",
           v7,
           &v11,
           a3,
           0);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v11 + 48LL))(
             v11,
             L"selectiveLogging",
             (char *)this + 8,
             0,
             0);
      if ( v9 >= 0 )
        v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v11 + 72LL))(
               v11,
               L"dontLog",
               (char *)this + 12,
               0,
               0);
    }
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003060  mov     [rsp+arg_0], rbx
0x180003065  push    rbp
0x180003066  push    rsi
0x180003067  push    rdi
0x180003068  sub     rsp, 40h
0x18000306c  mov     rax, [rdx]
0x18000306f  mov     rdi, rcx
0x180003072  mov     rcx, rdx
0x180003075  mov     [rsp+58h+arg_18], 0
0x18000307e  mov     rsi, r8
0x180003081  mov     [rsp+58h+arg_8], 0
0x18000308a  mov     rax, [rax+0A0h]
0x180003091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003096  mov     rcx, rax
0x180003099  mov     rdx, [rax]
0x18000309c  mov     rax, [rdx]
0x18000309f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a4  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800030ab  mov     rbp, rax
0x1800030ae  mov     rdx, [rcx]
0x1800030b1  mov     rax, [rdx+38h]
0x1800030b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ba  mov     r9, rax
0x1800030bd  lea     r8, [rsp+58h+arg_18]
0x1800030c2  lea     rdx, IID_INativeConfigurationSystem
0x1800030c9  mov     rcx, [rax]
0x1800030cc  mov     rax, [rcx]
0x1800030cf  mov     rcx, r9
0x1800030d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d7  mov     ebx, eax
0x1800030d9  test    eax, eax
0x1800030db  js      loc_18000316D
0x1800030e1  mov     rcx, [rsp+58h+arg_18]
0x1800030e6  lea     r9, [rsp+58h+arg_8]
0x1800030eb  mov     [rsp+58h+var_30], 0
0x1800030f4  lea     rdx, aSystemWebserve; "system.webServer/httpLogging"
0x1800030fb  mov     r8, rbp
0x1800030fe  mov     [rsp+58h+var_38], rsi
0x180003103  mov     rax, [rcx]
0x180003106  mov     rax, [rax+18h]
0x18000310a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000310f  mov     ebx, eax
0x180003111  test    eax, eax
0x180003113  js      short loc_18000316D
0x180003115  mov     rcx, [rsp+58h+arg_8]
0x18000311a  lea     r8, [rdi+8]
0x18000311e  xor     r9d, r9d
0x180003121  mov     [rsp+58h+var_38], 0
0x18000312a  lea     rdx, aSelectiveloggi; "selectiveLogging"
0x180003131  mov     rax, [rcx]
0x180003134  mov     rax, [rax+30h]
0x180003138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000313d  mov     ebx, eax
0x18000313f  test    eax, eax
0x180003141  js      short loc_18000316D
0x180003143  mov     rcx, [rsp+58h+arg_8]
0x180003148  lea     r8, [rdi+0Ch]
0x18000314c  xor     r9d, r9d
0x18000314f  mov     [rsp+58h+var_38], 0
0x180003158  lea     rdx, aDontlog; "dontLog"
0x18000315f  mov     rax, [rcx]
0x180003162  mov     rax, [rax+48h]
0x180003166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000316b  mov     ebx, eax
0x18000316d  mov     rcx, [rsp+58h+arg_8]
0x180003172  test    rcx, rcx
0x180003175  jz      short loc_18000318C
0x180003177  mov     rax, [rcx]
0x18000317a  mov     rax, [rax+10h]
0x18000317e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003183  mov     [rsp+58h+arg_8], 0
0x18000318c  mov     rcx, [rsp+58h+arg_18]
0x180003191  test    rcx, rcx
0x180003194  jz      short loc_1800031A2
0x180003196  mov     rax, [rcx]
0x180003199  mov     rax, [rax+10h]
0x18000319d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a2  mov     eax, ebx
0x1800031a4  mov     rbx, [rsp+58h+arg_0]
0x1800031a9  add     rsp, 40h
0x1800031ad  pop     rdi
0x1800031ae  pop     rsi
0x1800031af  pop     rbp
0x1800031b0  retn
```
