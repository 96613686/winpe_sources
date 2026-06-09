# HTTP_COMPRESSION::InitializeCompressionSchemes(INativeSectionException * *)

- ea: `0x180002e00`
- end: `0x180002fc6`
- name: `?InitializeCompressionSchemes@HTTP_COMPRESSION@@CAJPEAPEAVINativeSectionException@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002bb0`

## callees

- `0x180002e00`
- `0x180003d50`
- `0x180003e90`
- `0x180005460`
- `0x1800054a0`
- `0x180007f68`
- `0x180009010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180006f18`
- `iisutil!PuDbgPrint` at `0x180006f18`

## string_xrefs

- `0x180002e76`: `system.webServer/httpCompression`
- `0x180006ef4`: `HTTP_COMPRESSION::InitializeCompressionSchemes`
- `0x180006eff`: `servercommon\inetsrv\iis\iisrearc\iis70\compression\common\compress.cxx`

## pseudocode

```c
__int64 __fastcall HTTP_COMPRESSION::InitializeCompressionSchemes(struct INativeSectionException **a1)
{
  __int64 v2; // rax
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rax
  int v4; // ebx
  unsigned int v5; // edi
  COMPRESSION_SCHEME *v6; // rax
  COMPRESSION_SCHEME *v7; // rax
  COMPRESSION_SCHEME *v8; // rsi
  signed int v9; // eax
  __int64 v11; // [rsp+40h] [rbp-10h] BYREF
  __int64 v12; // [rsp+88h] [rbp+38h] BYREF
  struct INativeConfigurationElement *v13; // [rsp+90h] [rbp+40h] BYREF
  __int64 v14; // [rsp+98h] [rbp+48h] BYREF

  v11 = 0;
  v14 = 0;
  v12 = 0;
  v2 = *(_QWORD *)g_pGlobalInfo;
  v13 = 0;
  v3 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(v2 + 56))(g_pGlobalInfo);
  v4 = (**v3)(v3, &IID_INativeConfigurationSystem, &v11);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v11 + 24LL))(
           v11,
           L"system.webServer/httpCompression",
           L"MACHINE/WEBROOT/APPHOST",
           &v14,
           a1,
           0);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 40LL))(v14, &v12);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v12 + 24LL))(
               v12,
               &HTTP_COMPRESSION::sm_dwNumberOfSchemes);
        if ( v4 >= 0 )
        {
          v5 = 0;
          if ( !HTTP_COMPRESSION::sm_dwNumberOfSchemes )
          {
LABEL_12:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            v12 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
            v14 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            return 0;
          }
          while ( 1 )
          {
            v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v12 + 32LL))(
                   v12,
                   v5,
                   &v13);
            if ( v4 < 0 )
              break;
            v6 = (COMPRESSION_SCHEME *)operator new(0xF8u);
            if ( !v6 || (v7 = COMPRESSION_SCHEME::COMPRESSION_SCHEME(v6), (v8 = v7) == 0) )
            {
              v4 = -2147024888;
              break;
            }
            v9 = COMPRESSION_SCHEME::Initialize(v7, v13);
            v4 = v9;
            if ( v9 < 0 )
            {
              if ( (g_dwDebugFlags & 3) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\compression\\common\\compress.cxx",
                  830,
                  "HTTP_COMPRESSION::InitializeCompressionSchemes",
                  "Error initializing scheme, error %x\n",
                  v9);
              COMPRESSION_SCHEME::~COMPRESSION_SCHEME(v8);
              operator delete(v8);
              break;
            }
            (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v13 + 16LL))(v13);
            v13 = 0;
            (&HTTP_COMPRESSION::sm_pCompressionSchemes)[v5] = (struct COMPRESSION_SCHEME * near *)v8;
            if ( v5 != 99 && ++v5 < HTTP_COMPRESSION::sm_dwNumberOfSchemes )
              continue;
            goto LABEL_12;
          }
        }
      }
    }
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002e00  mov     [rsp-28h+arg_0], rbx
0x180002e05  push    rbp
0x180002e06  push    rsi
0x180002e07  push    rdi
0x180002e08  push    r14
0x180002e0a  push    r15
0x180002e0c  mov     rbp, rsp
0x180002e0f  sub     rsp, 50h
0x180002e13  xor     r14d, r14d
0x180002e16  mov     rdi, rcx
0x180002e19  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002e20  mov     [rbp+var_10], r14
0x180002e24  mov     [rbp+arg_18], r14
0x180002e28  mov     [rbp+arg_8], r14
0x180002e2c  mov     rax, [rcx]
0x180002e2f  mov     [rbp+arg_10], r14
0x180002e33  mov     rax, [rax+38h]
0x180002e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e3c  mov     r9, rax
0x180002e3f  lea     r8, [rbp+var_10]
0x180002e43  lea     rdx, IID_INativeConfigurationSystem
0x180002e4a  mov     rcx, [rax]
0x180002e4d  mov     rax, [rcx]
0x180002e50  mov     rcx, r9
0x180002e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e58  mov     ebx, eax
0x180002e5a  test    eax, eax
0x180002e5c  js      loc_180006F35
0x180002e62  mov     rcx, [rbp+var_10]
0x180002e66  lea     r9, [rbp+arg_18]
0x180002e6a  mov     [rsp+50h+var_28], r14
0x180002e6f  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180002e76  lea     rdx, aSystemWebserve_1; "system.webServer/httpCompression"
0x180002e7d  mov     [rsp+50h+var_30], rdi
0x180002e82  mov     rax, [rcx]
0x180002e85  mov     rax, [rax+18h]
0x180002e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e8e  mov     ebx, eax
0x180002e90  test    eax, eax
0x180002e92  js      loc_180006F35
0x180002e98  mov     rcx, [rbp+arg_18]
0x180002e9c  lea     rdx, [rbp+arg_8]
0x180002ea0  mov     rax, [rcx]
0x180002ea3  mov     rax, [rax+28h]
0x180002ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eac  mov     ebx, eax
0x180002eae  test    eax, eax
0x180002eb0  js      loc_180006F35
0x180002eb6  mov     rcx, [rbp+arg_8]
0x180002eba  lea     rdx, ?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwNumberOfSchemes
0x180002ec1  mov     rax, [rcx]
0x180002ec4  mov     rax, [rax+18h]
0x180002ec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ecd  mov     ebx, eax
0x180002ecf  test    eax, eax
0x180002ed1  js      loc_180006F35
0x180002ed7  cmp     cs:?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA, r14d; ulong HTTP_COMPRESSION::sm_dwNumberOfSchemes
0x180002ede  mov     edi, r14d
0x180002ee1  jbe     loc_180002F78
0x180002ee7  lea     r15, ?sm_pCompressionSchemes@HTTP_COMPRESSION@@0PAPEAVCOMPRESSION_SCHEME@@A; COMPRESSION_SCHEME * near * HTTP_COMPRESSION::sm_pCompressionSchemes
0x180002eee  mov     rcx, [rbp+arg_8]
0x180002ef2  lea     r8, [rbp+arg_10]
0x180002ef6  mov     edx, edi
0x180002ef8  mov     rax, [rcx]
0x180002efb  mov     rax, [rax+20h]
0x180002eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f04  mov     ebx, eax
0x180002f06  test    eax, eax
0x180002f08  js      loc_180006F35
0x180002f0e  mov     ecx, 0F8h; Size
0x180002f13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002f18  test    rax, rax
0x180002f1b  jz      loc_180006F30
0x180002f21  mov     rcx, rax; this
0x180002f24  call    ??0COMPRESSION_SCHEME@@QEAA@XZ; COMPRESSION_SCHEME::COMPRESSION_SCHEME(void)
0x180002f29  mov     rsi, rax
0x180002f2c  test    rax, rax
0x180002f2f  jz      loc_180006F30
0x180002f35  mov     rdx, [rbp+arg_10]; struct INativeConfigurationElement *
0x180002f39  mov     rcx, rax; this
0x180002f3c  call    ?Initialize@COMPRESSION_SCHEME@@QEAAJPEAVINativeConfigurationElement@@@Z; COMPRESSION_SCHEME::Initialize(INativeConfigurationElement *)
0x180002f41  mov     ebx, eax
0x180002f43  test    eax, eax
0x180002f45  js      loc_180006EE4
0x180002f4b  mov     rcx, [rbp+arg_10]
0x180002f4f  mov     rdx, [rcx]
0x180002f52  mov     rax, [rdx+10h]
0x180002f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f5b  mov     eax, edi
0x180002f5d  mov     [rbp+arg_10], r14
0x180002f61  mov     [r15+rax*8], rsi
0x180002f65  cmp     edi, 63h ; 'c'
0x180002f68  jz      short loc_180002F78
0x180002f6a  inc     edi
0x180002f6c  cmp     edi, cs:?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwNumberOfSchemes
0x180002f72  jb      loc_180002EEE
0x180002f78  mov     rcx, [rbp+arg_8]
0x180002f7c  mov     rax, [rcx]
0x180002f7f  mov     rax, [rax+10h]
0x180002f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f88  mov     rcx, [rbp+arg_18]
0x180002f8c  mov     [rbp+arg_8], r14
0x180002f90  mov     rax, [rcx]
0x180002f93  mov     rax, [rax+10h]
0x180002f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f9c  mov     rcx, [rbp+var_10]
0x180002fa0  mov     [rbp+arg_18], r14
0x180002fa4  mov     rax, [rcx]
0x180002fa7  mov     rax, [rax+10h]
0x180002fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fb0  xor     eax, eax
0x180002fb2  mov     rbx, [rsp+50h+arg_0]
0x180002fba  add     rsp, 50h
0x180002fbe  pop     r15
0x180002fc0  pop     r14
0x180002fc2  pop     rdi
0x180002fc3  pop     rsi
0x180002fc4  pop     rbp
0x180002fc5  retn
0x180006ee4  test    cs:g_dwDebugFlags, 3
0x180006eeb  jz      short loc_180006F1E
0x180006eed  mov     rcx, cs:g_pDebug
0x180006ef4  lea     r9, aHttpCompressio; "HTTP_COMPRESSION::InitializeCompression"...
0x180006efb  mov     dword ptr [rsp+50h+var_28], eax
0x180006eff  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006f06  lea     rax, aErrorInitializ; "Error initializing scheme, error %x\n"
0x180006f0d  mov     r8d, 33Eh
0x180006f13  mov     [rsp+50h+var_30], rax
0x180006f18  call    cs:__imp_PuDbgPrint
0x180006f1e  mov     rcx, rsi; this
0x180006f21  call    ??1COMPRESSION_SCHEME@@QEAA@XZ; COMPRESSION_SCHEME::~COMPRESSION_SCHEME(void)
0x180006f26  mov     rcx, rsi; Block
0x180006f29  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006f2e  jmp     short loc_180006F35
0x180006f30  mov     ebx, 80070008h
0x180006f35  mov     rcx, [rbp+arg_10]
0x180006f39  test    rcx, rcx
0x180006f3c  jz      short loc_180006F4E
0x180006f3e  mov     rax, [rcx]
0x180006f41  mov     rax, [rax+10h]
0x180006f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f4a  mov     [rbp+arg_10], r14
0x180006f4e  mov     rcx, [rbp+arg_8]
0x180006f52  test    rcx, rcx
0x180006f55  jz      short loc_180006F67
0x180006f57  mov     rax, [rcx]
0x180006f5a  mov     rax, [rax+10h]
0x180006f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f63  mov     [rbp+arg_8], r14
0x180006f67  mov     rcx, [rbp+arg_18]
0x180006f6b  test    rcx, rcx
0x180006f6e  jz      short loc_180006F80
0x180006f70  mov     rax, [rcx]
0x180006f73  mov     rax, [rax+10h]
0x180006f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f7c  mov     [rbp+arg_18], r14
0x180006f80  mov     rcx, [rbp+var_10]
0x180006f84  test    rcx, rcx
0x180006f87  jz      short loc_180006F95
0x180006f89  mov     rax, [rcx]
0x180006f8c  mov     rax, [rax+10h]
0x180006f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f95  mov     eax, ebx
0x180006f97  jmp     loc_180002FB2
```
