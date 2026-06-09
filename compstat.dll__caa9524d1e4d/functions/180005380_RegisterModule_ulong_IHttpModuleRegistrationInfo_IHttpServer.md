# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180005380`
- end: `0x180005437`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005380`
- `0x180005460`
- `0x1800054a0`
- `0x180009010`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180007553`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180007553`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x1800053cd`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x1800053cd`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  CReaderWriterLock3 *v5; // rax
  _QWORD *v6; // rax
  void *v8; // rbx

  g_pModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  g_pGlobalInfo = a3;
  g_fHttpCompressionInited = 0;
  v5 = (CReaderWriterLock3 *)operator new(8u);
  if ( !v5 )
  {
LABEL_8:
    g_pCompressionLock = 0;
    return 2147942408LL;
  }
  g_pCompressionLock = CReaderWriterLock3::CReaderWriterLock3(v5);
  if ( g_pCompressionLock )
  {
    v6 = operator new(0x10u);
    if ( v6 )
    {
      *v6 = &CIISModuleFactory::`vftable';
      v6[1] = &CIISHttpModule::`vftable';
      return (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
               a2,
               v6,
               272,
               0);
    }
    v8 = g_pCompressionLock;
    if ( g_pCompressionLock )
    {
      CReaderWriterLock3::~CReaderWriterLock3((CReaderWriterLock3 *)g_pCompressionLock);
      operator delete(v8);
    }
    goto LABEL_8;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180005380  mov     [rsp+arg_0], rbx
0x180005385  push    rdi
0x180005386  sub     rsp, 30h
0x18000538a  mov     rax, [rdx]
0x18000538d  mov     rcx, rdx
0x180005390  mov     rbx, r8
0x180005393  mov     rdi, rdx
0x180005396  mov     rax, [rax+8]
0x18000539a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000539f  mov     ecx, 8; Size
0x1800053a4  mov     cs:?g_pModuleContext@@3PEAXEA, rax; void * g_pModuleContext
0x1800053ab  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * g_pGlobalInfo
0x1800053b2  mov     cs:?g_fHttpCompressionInited@@3HA, 0; int g_fHttpCompressionInited
0x1800053bc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800053c1  test    rax, rax
0x1800053c4  jz      loc_180007561
0x1800053ca  mov     rcx, rax
0x1800053cd  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x1800053d3  mov     cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA, rax; CReaderWriterLock3 * g_pCompressionLock
0x1800053da  test    rax, rax
0x1800053dd  jz      short loc_180005430
0x1800053df  mov     ecx, 10h; Size
0x1800053e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800053e9  test    rax, rax
0x1800053ec  jz      loc_180007544
0x1800053f2  lea     rcx, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x1800053f9  mov     rdx, rax
0x1800053fc  mov     [rax], rcx
0x1800053ff  xor     r9d, r9d
0x180005402  lea     rcx, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x180005409  mov     r8d, 110h
0x18000540f  mov     [rax+8], rcx
0x180005413  mov     rcx, [rdi]
0x180005416  mov     r10, [rcx+10h]
0x18000541a  mov     rcx, rdi
0x18000541d  mov     rax, r10
0x180005420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005425  mov     rbx, [rsp+38h+arg_0]
0x18000542a  add     rsp, 30h
0x18000542e  pop     rdi
0x18000542f  retn
0x180005430  mov     eax, 80070008h
0x180005435  jmp     short loc_180005425
0x180007544  mov     rbx, cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * g_pCompressionLock
0x18000754b  test    rbx, rbx
0x18000754e  jz      short loc_180007561
0x180007550  mov     rcx, rbx
0x180007553  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x180007559  mov     rcx, rbx; Block
0x18000755c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007561  mov     cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA, 0; CReaderWriterLock3 * g_pCompressionLock
0x18000756c  jmp     loc_180005430
```
