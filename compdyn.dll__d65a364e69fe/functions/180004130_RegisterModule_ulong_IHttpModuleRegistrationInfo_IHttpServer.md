# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180004130`
- end: `0x1800041ea`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004130`
- `0x180004210`
- `0x180004250`
- `0x180008010`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180005a19`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180005a19`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000417d`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000417d`

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
      return (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, __int64))(*(_QWORD *)a2 + 16LL))(
               a2,
               v6,
               0x20000000,
               256);
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
0x180004130  mov     [rsp+arg_0], rbx
0x180004135  push    rdi
0x180004136  sub     rsp, 30h
0x18000413a  mov     rax, [rdx]
0x18000413d  mov     rcx, rdx
0x180004140  mov     rbx, r8
0x180004143  mov     rdi, rdx
0x180004146  mov     rax, [rax+8]
0x18000414a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000414f  mov     ecx, 8; Size
0x180004154  mov     cs:?g_pModuleContext@@3PEAXEA, rax; void * g_pModuleContext
0x18000415b  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * g_pGlobalInfo
0x180004162  mov     cs:?g_fHttpCompressionInited@@3HA, 0; int g_fHttpCompressionInited
0x18000416c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004171  test    rax, rax
0x180004174  jz      loc_180005A27
0x18000417a  mov     rcx, rax
0x18000417d  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180004183  mov     cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA, rax; CReaderWriterLock3 * g_pCompressionLock
0x18000418a  test    rax, rax
0x18000418d  jz      short loc_1800041E3
0x18000418f  mov     ecx, 10h; Size
0x180004194  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004199  test    rax, rax
0x18000419c  jz      loc_180005A0A
0x1800041a2  lea     rcx, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x1800041a9  mov     rdx, rax
0x1800041ac  mov     [rax], rcx
0x1800041af  mov     r9d, 100h
0x1800041b5  lea     rcx, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x1800041bc  mov     r8d, 20000000h
0x1800041c2  mov     [rax+8], rcx
0x1800041c6  mov     rcx, [rdi]
0x1800041c9  mov     r10, [rcx+10h]
0x1800041cd  mov     rcx, rdi
0x1800041d0  mov     rax, r10
0x1800041d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041d8  mov     rbx, [rsp+38h+arg_0]
0x1800041dd  add     rsp, 30h
0x1800041e1  pop     rdi
0x1800041e2  retn
0x1800041e3  mov     eax, 80070008h
0x1800041e8  jmp     short loc_1800041D8
0x180005a0a  mov     rbx, cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * g_pCompressionLock
0x180005a11  test    rbx, rbx
0x180005a14  jz      short loc_180005A27
0x180005a16  mov     rcx, rbx
0x180005a19  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x180005a1f  mov     rcx, rbx; Block
0x180005a22  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005a27  mov     cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA, 0; CReaderWriterLock3 * g_pCompressionLock
0x180005a32  jmp     loc_1800041E3
```
