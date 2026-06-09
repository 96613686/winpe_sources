# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180002a10`
- end: `0x180002abc`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `172`
- prototype: `signed int __fastcall(__int64, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001008`
- `0x180002a10`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002a70`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180002a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a7a`

## pseudocode

```c
signed int __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  _QWORD *v4; // rax
  signed int result; // eax

  s_pModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, struct IHttpModuleRegistrationInfo *, struct IHttpServer *))(*(_QWORD *)a2 + 8LL))(
                               a2,
                               a2,
                               a3);
  v4 = operator new(8u);
  if ( !v4 )
    return -2147024888;
  *v4 = &CIISGlobalModule::`vftable';
  result = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 24LL))(
             a2,
             v4,
             4352);
  if ( result >= 0 )
  {
    if ( InitializeCriticalSectionAndSpinCount(&IIS_REQMON_CONTEXT::sm_csRequestList, 0xC8u) )
    {
      IIS_REQMON_CONTEXT::sm_fInitializedcsRequestList = 1;
      qword_180007680 = (__int64)&IIS_REQMON_CONTEXT::sm_RequestListHead;
      IIS_REQMON_CONTEXT::sm_RequestListHead.Flink = &IIS_REQMON_CONTEXT::sm_RequestListHead;
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002a10  push    rbx
0x180002a12  sub     rsp, 20h
0x180002a16  mov     rax, [rdx]
0x180002a19  mov     rcx, rdx
0x180002a1c  mov     rbx, rdx
0x180002a1f  mov     rax, [rax+8]
0x180002a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a28  mov     ecx, 8; Size
0x180002a2d  mov     cs:?s_pModuleContext@@3PEAXEA, rax; void * s_pModuleContext
0x180002a34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002a39  mov     rdx, rax
0x180002a3c  test    rax, rax
0x180002a3f  jz      short loc_180002AB1
0x180002a41  lea     rax, ??_7CIISGlobalModule@@6B@; const CIISGlobalModule::`vftable'
0x180002a48  mov     r8d, 1100h
0x180002a4e  mov     [rdx], rax
0x180002a51  mov     rcx, [rbx]
0x180002a54  mov     rax, [rcx+18h]
0x180002a58  mov     rcx, rbx
0x180002a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a60  test    eax, eax
0x180002a62  js      short loc_180002AB6
0x180002a64  mov     edx, 0C8h; dwSpinCount
0x180002a69  lea     rcx, ?sm_csRequestList@IIS_REQMON_CONTEXT@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002a70  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180002a76  test    eax, eax
0x180002a78  jnz     short loc_180002A8E
0x180002a7a  call    cs:__imp_GetLastError
0x180002a80  test    eax, eax
0x180002a82  jle     short loc_180002AB6
0x180002a84  movzx   eax, ax
0x180002a87  or      eax, 80070000h
0x180002a8c  jmp     short loc_180002AB6
0x180002a8e  lea     rax, ?sm_RequestListHead@IIS_REQMON_CONTEXT@@0U_LIST_ENTRY@@A; _LIST_ENTRY IIS_REQMON_CONTEXT::sm_RequestListHead
0x180002a95  mov     cs:?sm_fInitializedcsRequestList@IIS_REQMON_CONTEXT@@0HA, 1; int IIS_REQMON_CONTEXT::sm_fInitializedcsRequestList
0x180002a9f  mov     cs:qword_180007680, rax
0x180002aa6  mov     cs:?sm_RequestListHead@IIS_REQMON_CONTEXT@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY IIS_REQMON_CONTEXT::sm_RequestListHead
0x180002aad  xor     eax, eax
0x180002aaf  jmp     short loc_180002AB6
0x180002ab1  mov     eax, 80070008h
0x180002ab6  add     rsp, 20h
0x180002aba  pop     rbx
0x180002abb  retn
```
