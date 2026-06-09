# URL_LOGGING::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x180004b30`
- end: `0x180004c81`
- name: `?Initialize@URL_LOGGING@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(URL_LOGGING *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001080`

## callees

- `0x180004b30`
- `0x180006010`

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
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
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
0x180004b30  mov     [rsp+arg_0], rbx
0x180004b35  push    rbp
0x180004b36  push    rsi
0x180004b37  push    rdi
0x180004b38  sub     rsp, 40h
0x180004b3c  mov     rax, [rdx]
0x180004b3f  mov     rdi, rcx
0x180004b42  mov     rcx, rdx
0x180004b45  mov     [rsp+58h+arg_18], 0
0x180004b4e  mov     rsi, r8
0x180004b51  mov     [rsp+58h+arg_8], 0
0x180004b5a  mov     rax, [rax+0A0h]
0x180004b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b66  mov     rcx, rax
0x180004b69  mov     rdx, [rax]
0x180004b6c  mov     rax, [rdx]
0x180004b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b74  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180004b7b  mov     rbp, rax
0x180004b7e  mov     rdx, [rcx]
0x180004b81  mov     rax, [rdx+38h]
0x180004b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b8a  mov     r9, rax
0x180004b8d  lea     r8, [rsp+58h+arg_18]
0x180004b92  lea     rdx, IID_INativeConfigurationSystem
0x180004b99  mov     rcx, [rax]
0x180004b9c  mov     rax, [rcx]
0x180004b9f  mov     rcx, r9
0x180004ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ba7  mov     ebx, eax
0x180004ba9  test    eax, eax
0x180004bab  js      loc_180004C3D
0x180004bb1  mov     rcx, [rsp+58h+arg_18]
0x180004bb6  lea     r9, [rsp+58h+arg_8]
0x180004bbb  mov     [rsp+58h+var_30], 0
0x180004bc4  lea     rdx, aSystemWebserve; "system.webServer/httpLogging"
0x180004bcb  mov     r8, rbp
0x180004bce  mov     [rsp+58h+var_38], rsi
0x180004bd3  mov     rax, [rcx]
0x180004bd6  mov     rax, [rax+18h]
0x180004bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bdf  mov     ebx, eax
0x180004be1  test    eax, eax
0x180004be3  js      short loc_180004C3D
0x180004be5  mov     rcx, [rsp+58h+arg_8]
0x180004bea  lea     r8, [rdi+8]
0x180004bee  xor     r9d, r9d
0x180004bf1  mov     [rsp+58h+var_38], 0
0x180004bfa  lea     rdx, aSelectiveloggi; "selectiveLogging"
0x180004c01  mov     rax, [rcx]
0x180004c04  mov     rax, [rax+30h]
0x180004c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c0d  mov     ebx, eax
0x180004c0f  test    eax, eax
0x180004c11  js      short loc_180004C3D
0x180004c13  mov     rcx, [rsp+58h+arg_8]
0x180004c18  lea     r8, [rdi+0Ch]
0x180004c1c  xor     r9d, r9d
0x180004c1f  mov     [rsp+58h+var_38], 0
0x180004c28  lea     rdx, aDontlog; "dontLog"
0x180004c2f  mov     rax, [rcx]
0x180004c32  mov     rax, [rax+48h]
0x180004c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c3b  mov     ebx, eax
0x180004c3d  mov     rcx, [rsp+58h+arg_8]
0x180004c42  test    rcx, rcx
0x180004c45  jz      short loc_180004C5C
0x180004c47  mov     rax, [rcx]
0x180004c4a  mov     rax, [rax+10h]
0x180004c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c53  mov     [rsp+58h+arg_8], 0
0x180004c5c  mov     rcx, [rsp+58h+arg_18]
0x180004c61  test    rcx, rcx
0x180004c64  jz      short loc_180004C72
0x180004c66  mov     rax, [rcx]
0x180004c69  mov     rax, [rax+10h]
0x180004c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c72  mov     eax, ebx
0x180004c74  mov     rbx, [rsp+58h+arg_0]
0x180004c79  add     rsp, 40h
0x180004c7d  pop     rdi
0x180004c7e  pop     rsi
0x180004c7f  pop     rbp
0x180004c80  retn
```
