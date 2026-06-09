# HTTP_COMPRESSION::InitializeCompressionSchemes(INativeSectionException * *)

- ea: `0x1800012b0`
- end: `0x180001476`
- name: `?InitializeCompressionSchemes@HTTP_COMPRESSION@@CAJPEAPEAVINativeSectionException@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x1800012b0`
- `0x180003c30`
- `0x180003cc0`
- `0x180004210`
- `0x180004250`
- `0x1800064e8`
- `0x180008010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180004ff8`
- `iisutil!PuDbgPrint` at `0x180004ff8`

## string_xrefs

- `0x180001326`: `system.webServer/httpCompression`
- `0x180004fd4`: `HTTP_COMPRESSION::InitializeCompressionSchemes`
- `0x180004fdf`: `servercommon\inetsrv\iis\iisrearc\iis70\compression\common\compress.cxx`

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
0x1800012b0  mov     [rsp-28h+arg_0], rbx
0x1800012b5  push    rbp
0x1800012b6  push    rsi
0x1800012b7  push    rdi
0x1800012b8  push    r14
0x1800012ba  push    r15
0x1800012bc  mov     rbp, rsp
0x1800012bf  sub     rsp, 50h
0x1800012c3  xor     r14d, r14d
0x1800012c6  mov     rdi, rcx
0x1800012c9  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800012d0  mov     [rbp+var_10], r14
0x1800012d4  mov     [rbp+arg_18], r14
0x1800012d8  mov     [rbp+arg_8], r14
0x1800012dc  mov     rax, [rcx]
0x1800012df  mov     [rbp+arg_10], r14
0x1800012e3  mov     rax, [rax+38h]
0x1800012e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012ec  mov     r9, rax
0x1800012ef  lea     r8, [rbp+var_10]
0x1800012f3  lea     rdx, IID_INativeConfigurationSystem
0x1800012fa  mov     rcx, [rax]
0x1800012fd  mov     rax, [rcx]
0x180001300  mov     rcx, r9
0x180001303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001308  mov     ebx, eax
0x18000130a  test    eax, eax
0x18000130c  js      loc_180005015
0x180001312  mov     rcx, [rbp+var_10]
0x180001316  lea     r9, [rbp+arg_18]
0x18000131a  mov     [rsp+50h+var_28], r14
0x18000131f  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180001326  lea     rdx, aSystemWebserve_0; "system.webServer/httpCompression"
0x18000132d  mov     [rsp+50h+var_30], rdi
0x180001332  mov     rax, [rcx]
0x180001335  mov     rax, [rax+18h]
0x180001339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000133e  mov     ebx, eax
0x180001340  test    eax, eax
0x180001342  js      loc_180005015
0x180001348  mov     rcx, [rbp+arg_18]
0x18000134c  lea     rdx, [rbp+arg_8]
0x180001350  mov     rax, [rcx]
0x180001353  mov     rax, [rax+28h]
0x180001357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000135c  mov     ebx, eax
0x18000135e  test    eax, eax
0x180001360  js      loc_180005015
0x180001366  mov     rcx, [rbp+arg_8]
0x18000136a  lea     rdx, ?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwNumberOfSchemes
0x180001371  mov     rax, [rcx]
0x180001374  mov     rax, [rax+18h]
0x180001378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000137d  mov     ebx, eax
0x18000137f  test    eax, eax
0x180001381  js      loc_180005015
0x180001387  cmp     cs:?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA, r14d; ulong HTTP_COMPRESSION::sm_dwNumberOfSchemes
0x18000138e  mov     edi, r14d
0x180001391  jbe     loc_180001428
0x180001397  lea     r15, ?sm_pCompressionSchemes@HTTP_COMPRESSION@@0PAPEAVCOMPRESSION_SCHEME@@A; COMPRESSION_SCHEME * near * HTTP_COMPRESSION::sm_pCompressionSchemes
0x18000139e  mov     rcx, [rbp+arg_8]
0x1800013a2  lea     r8, [rbp+arg_10]
0x1800013a6  mov     edx, edi
0x1800013a8  mov     rax, [rcx]
0x1800013ab  mov     rax, [rax+20h]
0x1800013af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013b4  mov     ebx, eax
0x1800013b6  test    eax, eax
0x1800013b8  js      loc_180005015
0x1800013be  mov     ecx, 0F8h; Size
0x1800013c3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800013c8  test    rax, rax
0x1800013cb  jz      loc_180005010
0x1800013d1  mov     rcx, rax; this
0x1800013d4  call    ??0COMPRESSION_SCHEME@@QEAA@XZ; COMPRESSION_SCHEME::COMPRESSION_SCHEME(void)
0x1800013d9  mov     rsi, rax
0x1800013dc  test    rax, rax
0x1800013df  jz      loc_180005010
0x1800013e5  mov     rdx, [rbp+arg_10]; struct INativeConfigurationElement *
0x1800013e9  mov     rcx, rax; this
0x1800013ec  call    ?Initialize@COMPRESSION_SCHEME@@QEAAJPEAVINativeConfigurationElement@@@Z; COMPRESSION_SCHEME::Initialize(INativeConfigurationElement *)
0x1800013f1  mov     ebx, eax
0x1800013f3  test    eax, eax
0x1800013f5  js      loc_180004FC4
0x1800013fb  mov     rcx, [rbp+arg_10]
0x1800013ff  mov     rdx, [rcx]
0x180001402  mov     rax, [rdx+10h]
0x180001406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000140b  mov     eax, edi
0x18000140d  mov     [rbp+arg_10], r14
0x180001411  mov     [r15+rax*8], rsi
0x180001415  cmp     edi, 63h ; 'c'
0x180001418  jz      short loc_180001428
0x18000141a  inc     edi
0x18000141c  cmp     edi, cs:?sm_dwNumberOfSchemes@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwNumberOfSchemes
0x180001422  jb      loc_18000139E
0x180001428  mov     rcx, [rbp+arg_8]
0x18000142c  mov     rax, [rcx]
0x18000142f  mov     rax, [rax+10h]
0x180001433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001438  mov     rcx, [rbp+arg_18]
0x18000143c  mov     [rbp+arg_8], r14
0x180001440  mov     rax, [rcx]
0x180001443  mov     rax, [rax+10h]
0x180001447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000144c  mov     rcx, [rbp+var_10]
0x180001450  mov     [rbp+arg_18], r14
0x180001454  mov     rax, [rcx]
0x180001457  mov     rax, [rax+10h]
0x18000145b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001460  xor     eax, eax
0x180001462  mov     rbx, [rsp+50h+arg_0]
0x18000146a  add     rsp, 50h
0x18000146e  pop     r15
0x180001470  pop     r14
0x180001472  pop     rdi
0x180001473  pop     rsi
0x180001474  pop     rbp
0x180001475  retn
0x180004fc4  test    cs:g_dwDebugFlags, 3
0x180004fcb  jz      short loc_180004FFE
0x180004fcd  mov     rcx, cs:g_pDebug
0x180004fd4  lea     r9, aHttpCompressio; "HTTP_COMPRESSION::InitializeCompression"...
0x180004fdb  mov     dword ptr [rsp+50h+var_28], eax
0x180004fdf  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004fe6  lea     rax, aErrorInitializ; "Error initializing scheme, error %x\n"
0x180004fed  mov     r8d, 33Eh
0x180004ff3  mov     [rsp+50h+var_30], rax
0x180004ff8  call    cs:__imp_PuDbgPrint
0x180004ffe  mov     rcx, rsi; this
0x180005001  call    ??1COMPRESSION_SCHEME@@QEAA@XZ; COMPRESSION_SCHEME::~COMPRESSION_SCHEME(void)
0x180005006  mov     rcx, rsi; Block
0x180005009  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000500e  jmp     short loc_180005015
0x180005010  mov     ebx, 80070008h
0x180005015  mov     rcx, [rbp+arg_10]
0x180005019  test    rcx, rcx
0x18000501c  jz      short loc_18000502E
0x18000501e  mov     rax, [rcx]
0x180005021  mov     rax, [rax+10h]
0x180005025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000502a  mov     [rbp+arg_10], r14
0x18000502e  mov     rcx, [rbp+arg_8]
0x180005032  test    rcx, rcx
0x180005035  jz      short loc_180005047
0x180005037  mov     rax, [rcx]
0x18000503a  mov     rax, [rax+10h]
0x18000503e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005043  mov     [rbp+arg_8], r14
0x180005047  mov     rcx, [rbp+arg_18]
0x18000504b  test    rcx, rcx
0x18000504e  jz      short loc_180005060
0x180005050  mov     rax, [rcx]
0x180005053  mov     rax, [rax+10h]
0x180005057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000505c  mov     [rbp+arg_18], r14
0x180005060  mov     rcx, [rbp+var_10]
0x180005064  test    rcx, rcx
0x180005067  jz      short loc_180005075
0x180005069  mov     rax, [rcx]
0x18000506c  mov     rax, [rax+10h]
0x180005070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005075  mov     eax, ebx
0x180005077  jmp     loc_180001462
```
