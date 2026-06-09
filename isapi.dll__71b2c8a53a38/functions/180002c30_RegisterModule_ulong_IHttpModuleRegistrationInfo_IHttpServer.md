# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180002c30`
- end: `0x180002d93`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001020`
- `0x180001f2c`
- `0x180002c30`
- `0x180013010`

## import_xrefs

- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180002c9c`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180002c9c`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002d4b`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002d4b`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  EVENT_LOG *v5; // rbx
  int v6; // eax
  const unsigned __int16 *v7; // rdx
  _QWORD *v8; // rax
  __int64 result; // rax
  _QWORD *v10; // rax
  struct IHttpServer *v11; // rbx
  CReaderWriterLock3 *v12; // rax

  g_pModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  g_pGlobalInfo = a3;
  v5 = (EVENT_LOG *)operator new(4u);
  if ( v5 )
  {
    v6 = (**(__int64 (__fastcall ***)(struct IHttpServer *))g_pGlobalInfo)(g_pGlobalInfo);
    v7 = L"HostableWebCore";
    if ( !v6 )
      v7 = L"W3SVC-WP";
    g_pEventLog = EVENT_LOG::EVENT_LOG(v5, v7);
    if ( g_pEventLog )
    {
      v8 = operator new(0x10u);
      if ( v8 )
      {
        *v8 = &CIISModuleFactory::`vftable';
        v8[1] = &CIISHttpModule::`vftable';
        result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
                   a2,
                   v8,
                   536871040,
                   0);
        if ( (int)result < 0 )
          return result;
        v10 = operator new(8u);
        if ( v10 )
        {
          *v10 = &CIISGlobalModule::`vftable';
          result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 24LL))(
                     a2,
                     v10,
                     64);
          if ( (int)result < 0 )
            return result;
          v11 = g_pGlobalInfo;
          v12 = (CReaderWriterLock3 *)operator new(8u);
          if ( v12 )
          {
            W3_RESTRICTION_LIST::sm_pRestrictionLock = CReaderWriterLock3::CReaderWriterLock3(v12);
            if ( W3_RESTRICTION_LIST::sm_pRestrictionLock )
            {
              W3_RESTRICTION_LIST::sm_pGlobalInfo = v11;
              return InitIsapiModule();
            }
          }
          else
          {
            W3_RESTRICTION_LIST::sm_pRestrictionLock = 0;
          }
        }
      }
    }
  }
  else
  {
    g_pEventLog = 0;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180002c30  mov     [rsp+arg_0], rbx
0x180002c35  push    rdi
0x180002c36  sub     rsp, 30h
0x180002c3a  mov     rax, [rdx]
0x180002c3d  mov     rcx, rdx
0x180002c40  mov     rbx, r8
0x180002c43  mov     rdi, rdx
0x180002c46  mov     rax, [rax+8]
0x180002c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c4f  mov     ecx, 4; Size
0x180002c54  mov     cs:?g_pModuleContext@@3PEAXEA, rax; void * g_pModuleContext
0x180002c5b  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * g_pGlobalInfo
0x180002c62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002c67  mov     rbx, rax
0x180002c6a  test    rax, rax
0x180002c6d  jz      loc_180002D78
0x180002c73  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002c7a  mov     rdx, [rcx]
0x180002c7d  mov     rax, [rdx]
0x180002c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c85  test    eax, eax
0x180002c87  lea     rcx, aW3svcWp; "W3SVC-WP"
0x180002c8e  lea     rdx, aHostablewebcor; "HostableWebCore"
0x180002c95  cmovz   rdx, rcx
0x180002c99  mov     rcx, rbx
0x180002c9c  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x180002ca2  mov     cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA, rax; EVENT_LOG * g_pEventLog
0x180002ca9  test    rax, rax
0x180002cac  jz      loc_180002D83
0x180002cb2  mov     ecx, 10h; Size
0x180002cb7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002cbc  mov     rdx, rax
0x180002cbf  test    rax, rax
0x180002cc2  jz      loc_180002D83
0x180002cc8  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x180002ccf  xor     r9d, r9d
0x180002cd2  mov     [rdx], rax
0x180002cd5  mov     r8d, 20000080h
0x180002cdb  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x180002ce2  mov     [rdx+8], rax
0x180002ce6  mov     rcx, [rdi]
0x180002ce9  mov     rax, [rcx+10h]
0x180002ced  mov     rcx, rdi
0x180002cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cf5  test    eax, eax
0x180002cf7  js      loc_180002D88
0x180002cfd  mov     ecx, 8; Size
0x180002d02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002d07  mov     rdx, rax
0x180002d0a  test    rax, rax
0x180002d0d  jz      short loc_180002D83
0x180002d0f  lea     rax, ??_7CIISGlobalModule@@6B@; const CIISGlobalModule::`vftable'
0x180002d16  mov     r8d, 40h ; '@'
0x180002d1c  mov     [rdx], rax
0x180002d1f  mov     rcx, [rdi]
0x180002d22  mov     rax, [rcx+18h]
0x180002d26  mov     rcx, rdi
0x180002d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d2e  test    eax, eax
0x180002d30  js      short loc_180002D88
0x180002d32  mov     rbx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002d39  mov     ecx, 8; Size
0x180002d3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002d43  test    rax, rax
0x180002d46  jz      short loc_180002D6B
0x180002d48  mov     rcx, rax
0x180002d4b  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180002d51  mov     cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA, rax; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x180002d58  test    rax, rax
0x180002d5b  jz      short loc_180002D83
0x180002d5d  mov     cs:?sm_pGlobalInfo@W3_RESTRICTION_LIST@@0PEAVIHttpServer@@EA, rbx; IHttpServer * W3_RESTRICTION_LIST::sm_pGlobalInfo
0x180002d64  call    ?InitIsapiModule@@YAJXZ; InitIsapiModule(void)
0x180002d69  jmp     short loc_180002D88
0x180002d6b  mov     cs:?sm_pRestrictionLock@W3_RESTRICTION_LIST@@0PEAVCReaderWriterLock3@@EA, 0; CReaderWriterLock3 * W3_RESTRICTION_LIST::sm_pRestrictionLock
0x180002d76  jmp     short loc_180002D83
0x180002d78  mov     cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA, 0; EVENT_LOG * g_pEventLog
0x180002d83  mov     eax, 80070008h
0x180002d88  mov     rbx, [rsp+38h+arg_0]
0x180002d8d  add     rsp, 30h
0x180002d91  pop     rdi
0x180002d92  retn
```
