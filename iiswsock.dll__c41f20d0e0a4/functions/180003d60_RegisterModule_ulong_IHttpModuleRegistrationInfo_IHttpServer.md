# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180003d60`
- end: `0x180003ef3`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(__int64, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task`

## callees

- `0x180001008`
- `0x180001048`
- `0x180003d60`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003e25`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180003e25`
- `iisutil!PuCreateDebugPrintsObject` at `0x180003e0c`
- `iisutil!PuCreateDebugPrintsObject` at `0x180003e0c`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180003e51`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180003e51`

## string_xrefs

- `0x180003e1e`: `Unable to Create Debug Print Object \n`
- `0x180003e4a`: `System\CurrentControlSet\Services\W3SVC\Parameters\websockets`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  __int64 v3; // rax
  __int64 v6; // rax
  int v7; // edi
  __int64 DebugPrintsObject; // rax
  _QWORD *v9; // rax
  void *v10; // rbx
  __int64 v12; // [rsp+48h] [rbp+10h] BYREF
  __int64 v13; // [rsp+50h] [rbp+18h] BYREF

  v3 = *(_QWORD *)a2;
  v13 = 0;
  g_pWebSocketModuleId = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(v3 + 8))(a2);
  v6 = *(_QWORD *)a3;
  g_pGlobalInfo = a3;
  v12 = 0;
  v7 = (*(__int64 (__fastcall **)(struct IHttpServer *, _QWORD, __int64 *))(v6 + 200))(a3, 0, &v12);
  if ( v7 < 0 )
    return (unsigned int)v7;
  v7 = (*(__int64 (__fastcall **)(__int64, GUID *, struct IHttpModuleRegistrationInfo *, GUID *, __int64 *))(*(_QWORD *)v12 + 224LL))(
         v12,
         &GUID_07e5beb3_b798_459d_a98a_e6c485b2b3bc,
         a2,
         &GUID_4fd11cbf_8cc5_418e_8000_c9e765f88533,
         &v13);
  if ( v7 < 0 )
    return (unsigned int)v7;
  DebugPrintsObject = PuCreateDebugPrintsObject("iiswsock", 1);
  g_pDebug = DebugPrintsObject;
  if ( DebugPrintsObject
    || (OutputDebugStringA("Unable to Create Debug Print Object \n"), (DebugPrintsObject = g_pDebug) != 0) )
  {
    if ( *(_DWORD *)(DebugPrintsObject + 640) )
    {
      g_dwDebugFlags = PuLoadDebugFlagsFromRegStr(
                         "System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\websockets",
                         0);
      v9 = operator new(0x10u);
      v10 = v9;
      if ( v9 )
      {
        *v9 = &WEBSOCKET_MODULE_FACTORY::`vftable';
        v9[1] = &WEBSOCKET_MODULE::`vftable';
        v7 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, __int64))(*(_QWORD *)a2 + 16LL))(
               a2,
               v9,
               134217729,
               2048);
        if ( v7 < 0
          || (v7 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *))(*(_QWORD *)v13 + 48LL))(
                     v13,
                     2048,
                     L"LAST"),
              v7 < 0) )
        {
          operator delete(v10);
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
      return (unsigned int)v7;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180003d60  mov     [rsp+arg_0], rbx
0x180003d65  mov     [rsp+arg_18], rsi
0x180003d6a  push    rdi
0x180003d6b  sub     rsp, 30h
0x180003d6f  mov     rax, [rdx]
0x180003d72  mov     rcx, rdx
0x180003d75  mov     rbx, r8
0x180003d78  mov     [rsp+38h+arg_10], 0
0x180003d81  mov     rsi, rdx
0x180003d84  mov     rax, [rax+8]
0x180003d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d8d  mov     cs:?g_pWebSocketModuleId@@3PEAXEA, rax; void * g_pWebSocketModuleId
0x180003d94  lea     r8, [rsp+38h+arg_8]
0x180003d99  mov     rax, [rbx]
0x180003d9c  xor     edx, edx
0x180003d9e  mov     rcx, rbx
0x180003da1  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * g_pGlobalInfo
0x180003da8  mov     [rsp+38h+arg_8], 0
0x180003db1  mov     rax, [rax+0C8h]
0x180003db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dbd  mov     edi, eax
0x180003dbf  test    eax, eax
0x180003dc1  js      loc_180003ED3
0x180003dc7  mov     rcx, [rsp+38h+arg_8]
0x180003dcc  lea     rdx, [rsp+38h+arg_10]
0x180003dd1  mov     [rsp+38h+var_18], rdx
0x180003dd6  lea     r9, _GUID_4fd11cbf_8cc5_418e_8000_c9e765f88533
0x180003ddd  mov     r8, rsi
0x180003de0  lea     rdx, _GUID_07e5beb3_b798_459d_a98a_e6c485b2b3bc
0x180003de7  mov     rax, [rcx]
0x180003dea  mov     rax, [rax+0E0h]
0x180003df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003df6  mov     edi, eax
0x180003df8  test    eax, eax
0x180003dfa  js      loc_180003ED3
0x180003e00  mov     edx, 1
0x180003e05  lea     rcx, aIiswsock; "iiswsock"
0x180003e0c  call    cs:__imp_PuCreateDebugPrintsObject
0x180003e12  mov     cs:g_pDebug, rax
0x180003e19  test    rax, rax
0x180003e1c  jnz     short loc_180003E3B
0x180003e1e  lea     rcx, aUnableToCreate; "Unable to Create Debug Print Object \n"
0x180003e25  call    cs:__imp_OutputDebugStringA
0x180003e2b  mov     rax, cs:g_pDebug
0x180003e32  test    rax, rax
0x180003e35  jz      loc_180003EEC
0x180003e3b  cmp     dword ptr [rax+280h], 0
0x180003e42  jz      loc_180003EEC
0x180003e48  xor     edx, edx
0x180003e4a  lea     rcx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x180003e51  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180003e57  mov     ecx, 10h; Size
0x180003e5c  mov     cs:g_dwDebugFlags, eax
0x180003e62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003e67  mov     rbx, rax
0x180003e6a  test    rax, rax
0x180003e6d  jz      short loc_180003EE5
0x180003e6f  lea     rax, ??_7WEBSOCKET_MODULE_FACTORY@@6B@; const WEBSOCKET_MODULE_FACTORY::`vftable'
0x180003e76  mov     r9d, 800h
0x180003e7c  mov     [rbx], rax
0x180003e7f  mov     r8d, 8000001h
0x180003e85  lea     rax, ??_7WEBSOCKET_MODULE@@6B@; const WEBSOCKET_MODULE::`vftable'
0x180003e8c  mov     rdx, rbx
0x180003e8f  mov     [rbx+8], rax
0x180003e93  mov     rcx, rsi
0x180003e96  mov     rax, [rsi]
0x180003e99  mov     rax, [rax+10h]
0x180003e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ea2  mov     edi, eax
0x180003ea4  test    eax, eax
0x180003ea6  js      short loc_180003ECB
0x180003ea8  mov     rcx, [rsp+38h+arg_10]
0x180003ead  lea     r8, aLast; "LAST"
0x180003eb4  mov     edx, 800h
0x180003eb9  mov     rax, [rcx]
0x180003ebc  mov     rax, [rax+30h]
0x180003ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ec5  mov     edi, eax
0x180003ec7  test    eax, eax
0x180003ec9  jns     short loc_180003ED3
0x180003ecb  mov     rcx, rbx; Block
0x180003ece  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003ed3  mov     eax, edi
0x180003ed5  mov     rbx, [rsp+38h+arg_0]
0x180003eda  mov     rsi, [rsp+38h+arg_18]
0x180003edf  add     rsp, 30h
0x180003ee3  pop     rdi
0x180003ee4  retn
0x180003ee5  mov     edi, 8007000Eh
0x180003eea  jmp     short loc_180003ED3
0x180003eec  mov     eax, 80004005h
0x180003ef1  jmp     short loc_180003ED5
```
