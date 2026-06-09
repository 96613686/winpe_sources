# ISAPI_META_CONTEXT::Initialize(IHttpContext *)

- ea: `0x1800108d0`
- end: `0x180010a78`
- name: `?Initialize@ISAPI_META_CONTEXT@@AEAAJPEAVIHttpContext@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(ISAPI_META_CONTEXT *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800107c8`

## callees

- `0x1800108d0`
- `0x180013010`

## string_xrefs

- `0x180010a05`: `accessPolicy`
- `0x1800109a2`: `uploadReadAheadSize`

## pseudocode

```c
__int64 __fastcall ISAPI_META_CONTEXT::Initialize(ISAPI_META_CONTEXT *this, struct IHttpContext *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall ***v4)(_QWORD); // rax
  __int64 v5; // rdi
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rax
  __int64 result; // rax
  int v8; // ebx
  __int64 v9; // [rsp+68h] [rbp+28h] BYREF
  __int64 v10; // [rsp+70h] [rbp+30h] BYREF
  __int64 v11; // [rsp+78h] [rbp+38h] BYREF

  v2 = *(_QWORD *)a2;
  v11 = 0;
  v10 = 0;
  v9 = 0;
  v4 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IHttpContext *))(v2 + 160))(a2);
  v5 = (**v4)(v4);
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  result = (**v6)(v6, &IID_INativeConfigurationSystem, &v11);
  if ( (int)result >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v11 + 24LL))(
           v11,
           L"system.webServer/serverRuntime",
           v5,
           &v10,
           0,
           0);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v10 + 48LL))(
             v10,
             L"uploadReadAheadSize",
             (char *)this + 8,
             0,
             0);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v11 + 24LL))(
               v11,
               L"system.webServer/handlers",
               v5,
               &v9,
               0,
               0);
        if ( v8 >= 0 )
          v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v9 + 48LL))(
                 v9,
                 L"accessPolicy",
                 (char *)this + 12,
                 0,
                 0);
      }
    }
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      v9 = 0;
    }
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v10 = 0;
    }
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x1800108d0  mov     [rsp-18h+arg_0], rbx
0x1800108d5  push    rbp
0x1800108d6  push    rsi
0x1800108d7  push    rdi
0x1800108d8  mov     rbp, rsp
0x1800108db  sub     rsp, 40h
0x1800108df  mov     rax, [rdx]
0x1800108e2  mov     rsi, rcx
0x1800108e5  mov     rcx, rdx
0x1800108e8  mov     [rbp+arg_18], 0
0x1800108f0  mov     [rbp+arg_10], 0
0x1800108f8  mov     [rbp+arg_8], 0
0x180010900  mov     rax, [rax+0A0h]
0x180010907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001090c  mov     rcx, rax
0x18001090f  mov     rdx, [rax]
0x180010912  mov     rax, [rdx]
0x180010915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001091a  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180010921  mov     rdi, rax
0x180010924  mov     rdx, [rcx]
0x180010927  mov     rax, [rdx+38h]
0x18001092b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010930  mov     r9, rax
0x180010933  lea     r8, [rbp+arg_18]
0x180010937  lea     rdx, IID_INativeConfigurationSystem
0x18001093e  mov     rcx, [rax]
0x180010941  mov     rax, [rcx]
0x180010944  mov     rcx, r9
0x180010947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001094c  test    eax, eax
0x18001094e  js      loc_180010A6B
0x180010954  mov     rcx, [rbp+arg_18]
0x180010958  lea     r9, [rbp+arg_10]
0x18001095c  mov     [rsp+40h+var_18], 0
0x180010965  lea     rdx, aSystemWebserve_4; "system.webServer/serverRuntime"
0x18001096c  mov     r8, rdi
0x18001096f  mov     [rsp+40h+var_20], 0
0x180010978  mov     rax, [rcx]
0x18001097b  mov     rax, [rax+18h]
0x18001097f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010984  mov     ebx, eax
0x180010986  test    eax, eax
0x180010988  js      loc_180010A1A
0x18001098e  mov     rcx, [rbp+arg_10]
0x180010992  lea     r8, [rsi+8]
0x180010996  xor     r9d, r9d
0x180010999  mov     [rsp+40h+var_20], 0
0x1800109a2  lea     rdx, aUploadreadahea; "uploadReadAheadSize"
0x1800109a9  mov     rax, [rcx]
0x1800109ac  mov     rax, [rax+30h]
0x1800109b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109b5  mov     ebx, eax
0x1800109b7  test    eax, eax
0x1800109b9  js      short loc_180010A1A
0x1800109bb  mov     rcx, [rbp+arg_18]
0x1800109bf  lea     r9, [rbp+arg_8]
0x1800109c3  mov     [rsp+40h+var_18], 0
0x1800109cc  lea     rdx, aSystemWebserve_2; "system.webServer/handlers"
0x1800109d3  mov     r8, rdi
0x1800109d6  mov     [rsp+40h+var_20], 0
0x1800109df  mov     rax, [rcx]
0x1800109e2  mov     rax, [rax+18h]
0x1800109e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109eb  mov     ebx, eax
0x1800109ed  test    eax, eax
0x1800109ef  js      short loc_180010A1A
0x1800109f1  mov     rcx, [rbp+arg_8]
0x1800109f5  lea     r8, [rsi+0Ch]
0x1800109f9  xor     r9d, r9d
0x1800109fc  mov     [rsp+40h+var_20], 0
0x180010a05  lea     rdx, aAccesspolicy; "accessPolicy"
0x180010a0c  mov     rax, [rcx]
0x180010a0f  mov     rax, [rax+30h]
0x180010a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a18  mov     ebx, eax
0x180010a1a  mov     rcx, [rbp+arg_8]
0x180010a1e  test    rcx, rcx
0x180010a21  jz      short loc_180010A37
0x180010a23  mov     rax, [rcx]
0x180010a26  mov     rax, [rax+10h]
0x180010a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a2f  mov     [rbp+arg_8], 0
0x180010a37  mov     rcx, [rbp+arg_10]
0x180010a3b  test    rcx, rcx
0x180010a3e  jz      short loc_180010A54
0x180010a40  mov     rax, [rcx]
0x180010a43  mov     rax, [rax+10h]
0x180010a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a4c  mov     [rbp+arg_10], 0
0x180010a54  mov     rcx, [rbp+arg_18]
0x180010a58  test    rcx, rcx
0x180010a5b  jz      short loc_180010A69
0x180010a5d  mov     rax, [rcx]
0x180010a60  mov     rax, [rax+10h]
0x180010a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a69  mov     eax, ebx
0x180010a6b  mov     rbx, [rsp+40h+arg_0]
0x180010a70  add     rsp, 40h
0x180010a74  pop     rdi
0x180010a75  pop     rsi
0x180010a76  pop     rbp
0x180010a77  retn
```
