# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180006da0`
- end: `0x180006ed6`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(__int64, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005860`
- `0x180006da0`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006dda`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006dda`
- `iisutil!PuCreateDebugPrintsObject` at `0x180006dc1`
- `iisutil!PuCreateDebugPrintsObject` at `0x180006dc1`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180006e06`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180006e06`
- `iisutil!PuDbgPrint` at `0x180006e8f`
- `iisutil!PuDbgPrint` at `0x180006e8f`

## string_xrefs

- `0x180006dd3`: `Unable to Create Debug Print Object \n`
- `0x180006e76`: `servercommon\inetsrv\iis\iisrearc\iis70\requestfiltering\module.cxx`
- `0x180006dff`: `System\CurrentControlSet\Services\W3SVC\Parameters\modrqflt`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  __int64 DebugPrintsObject; // rax
  _QWORD *v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 result; // rax

  DebugPrintsObject = PuCreateDebugPrintsObject("modrqflt", 1);
  g_pDebug = DebugPrintsObject;
  if ( !DebugPrintsObject )
  {
    OutputDebugStringA("Unable to Create Debug Print Object \n");
    DebugPrintsObject = g_pDebug;
    if ( !g_pDebug )
      return 2147500037LL;
  }
  if ( !*(_DWORD *)(DebugPrintsObject + 640) )
    return 2147500037LL;
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\modrqflt", 0);
  v6 = operator new(0x10u);
  if ( !v6 )
    return 2147942408LL;
  *v6 = &CIISModuleFactory::`vftable';
  v6[1] = &CIISHttpModule::`vftable';
  v7 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, _QWORD))(*(_QWORD *)a2 + 16LL))(
         a2,
         v6,
         134217729,
         0);
  v8 = v7;
  if ( v7 >= 0 )
  {
    g_pModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
    result = 0;
    g_pGlobalInfo = a3;
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\requestfiltering\\module.cxx",
        102,
        "RegisterModule",
        "Error 0x%08x occurred setting notifications.\r\n",
        v7);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180006da0  mov     [rsp+arg_0], rbx
0x180006da5  mov     [rsp+arg_8], rsi
0x180006daa  push    rdi
0x180006dab  sub     rsp, 30h
0x180006daf  mov     rdi, rdx
0x180006db2  lea     rcx, aModrqflt; "modrqflt"
0x180006db9  mov     edx, 1
0x180006dbe  mov     rsi, r8
0x180006dc1  call    cs:__imp_PuCreateDebugPrintsObject
0x180006dc7  mov     cs:g_pDebug, rax
0x180006dce  test    rax, rax
0x180006dd1  jnz     short loc_180006DF0
0x180006dd3  lea     rcx, aUnableToCreate; "Unable to Create Debug Print Object \n"
0x180006dda  call    cs:__imp_OutputDebugStringA
0x180006de0  mov     rax, cs:g_pDebug
0x180006de7  test    rax, rax
0x180006dea  jz      loc_180006EC1
0x180006df0  cmp     dword ptr [rax+280h], 0
0x180006df7  jz      loc_180006EC1
0x180006dfd  xor     edx, edx
0x180006dff  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x180006e06  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180006e0c  mov     ecx, 10h; Size
0x180006e11  mov     cs:g_dwDebugFlags, eax
0x180006e17  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006e1c  mov     rdx, rax
0x180006e1f  test    rax, rax
0x180006e22  jz      loc_180006EBA
0x180006e28  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x180006e2f  xor     r9d, r9d
0x180006e32  mov     [rdx], rax
0x180006e35  mov     r8d, 8000001h
0x180006e3b  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x180006e42  mov     [rdx+8], rax
0x180006e46  mov     rcx, [rdi]
0x180006e49  mov     rax, [rcx+10h]
0x180006e4d  mov     rcx, rdi
0x180006e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e55  mov     ebx, eax
0x180006e57  test    eax, eax
0x180006e59  jns     short loc_180006E99
0x180006e5b  test    byte ptr cs:g_dwDebugFlags, 3
0x180006e62  jz      short loc_180006E95
0x180006e64  mov     rcx, cs:g_pDebug
0x180006e6b  lea     r9, aRegistermodule_0; "RegisterModule"
0x180006e72  mov     [rsp+38h+var_10], eax
0x180006e76  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006e7d  lea     rax, aError0x08xOccu; "Error 0x%08x occurred setting notificat"...
0x180006e84  mov     r8d, 66h ; 'f'
0x180006e8a  mov     [rsp+38h+var_18], rax
0x180006e8f  call    cs:__imp_PuDbgPrint
0x180006e95  mov     eax, ebx
0x180006e97  jmp     short loc_180006EC6
0x180006e99  mov     rax, [rdi]
0x180006e9c  mov     rcx, rdi
0x180006e9f  mov     rax, [rax+8]
0x180006ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea8  mov     cs:?g_pModuleContext@@3PEAXEA, rax; void * g_pModuleContext
0x180006eaf  xor     eax, eax
0x180006eb1  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, rsi; IHttpServer * g_pGlobalInfo
0x180006eb8  jmp     short loc_180006EC6
0x180006eba  mov     eax, 80070008h
0x180006ebf  jmp     short loc_180006EC6
0x180006ec1  mov     eax, 80004005h
0x180006ec6  mov     rbx, [rsp+38h+arg_0]
0x180006ecb  mov     rsi, [rsp+38h+arg_8]
0x180006ed0  add     rsp, 30h
0x180006ed4  pop     rdi
0x180006ed5  retn
```
