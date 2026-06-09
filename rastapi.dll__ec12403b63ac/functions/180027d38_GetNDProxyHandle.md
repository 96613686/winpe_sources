# GetNDProxyHandle

- ea: `0x180027d38`
- end: `0x180027e31`
- name: `GetNDProxyHandle`
- size: `249`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800231f8`
- `0x180023404`
- `0x180023a14`
- `0x180023e24`
- `0x1800244ec`
- `0x180024b38`
- `0x180025244`

## callees

- `0x180027270`
- `0x180027d38`
- `0x180028b5c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027dd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027dff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027dd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027dff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180027dca`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180027dca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027df4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027df4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027ddf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027ddf`
- `rtutils!TracePrintfA` at `0x180027db1`
- `rtutils!TracePrintfA` at `0x180027db1`

## string_xrefs

- `0x180027d8a`: `GetNdisTapiHandle: wait for the outbound call to complete...`
- `0x180027daa`: `GetNdisTapiHandle: wait for the outbound call to complete...`

## pseudocode

```c
__int64 __fastcall GetNDProxyHandle(__int64 a1, _QWORD *a2)
{
  __int64 result; // rax
  unsigned int v5; // esi
  unsigned int *v6; // [rsp+30h] [rbp+8h] BYREF

  result = 0;
  v6 = (unsigned int *)a1;
  *a2 = 0;
  if ( *(_DWORD *)a1 == 1329807692 && *(_DWORD *)(a1 + 64) )
  {
    v5 = *(_DWORD *)(a1 + 8);
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC48 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
          gNdpspEtwContext,
          qword_18003EC48,
          L"GetNdisTapiHandle: wait for the outbound call to complete...");
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(dwTraceId, "GetNdisTapiHandle: wait for the outbound call to complete...");
    }
    do
    {
      ReleaseObjReadLock(v5);
      if ( RasTapiMutex && !ReleaseMutex(RasTapiMutex) )
        GetLastError();
      Sleep(0xFAu);
      if ( RasTapiMutex && WaitForSingleObject(RasTapiMutex, 0xFFFFFFFF) == -1 )
        GetLastError();
      result = GetCallObjWithReadLock(v5, &v6);
    }
    while ( !(_DWORD)result && *(_DWORD *)(a1 + 64) );
  }
  *a2 = *(_QWORD *)(a1 + 24);
  return result;
}

```

## disassembly

```asm
0x180027d38  mov     [rsp+arg_8], rbx
0x180027d3d  mov     [rsp+arg_10], rsi
0x180027d42  push    rdi
0x180027d43  sub     rsp, 20h
0x180027d47  xor     eax, eax
0x180027d49  mov     [rsp+28h+arg_0], rcx
0x180027d4e  mov     [rdx], rax
0x180027d51  mov     rdi, rdx
0x180027d54  cmp     dword ptr [rcx], 4F43414Ch
0x180027d5a  mov     rbx, rcx
0x180027d5d  jnz     loc_180027E1A
0x180027d63  cmp     [rcx+40h], eax
0x180027d66  jz      loc_180027E1A
0x180027d6c  cmp     cs:gIsndpspEtwTracingAvailable, eax
0x180027d72  mov     esi, [rcx+8]
0x180027d75  jz      short loc_180027D9F
0x180027d77  mov     rdx, cs:qword_18003EC48
0x180027d7e  test    rdx, rdx
0x180027d81  jz      short loc_180027DB7
0x180027d83  mov     rcx, cs:gNdpspEtwContext
0x180027d8a  lea     r8, aGetndistapihan_0; "GetNdisTapiHandle: wait for the outboun"...
0x180027d91  mov     rax, cs:gNdpspTemplateFunc
0x180027d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d9d  jmp     short loc_180027DB7
0x180027d9f  mov     ecx, cs:dwTraceId; dwTraceID
0x180027da5  cmp     ecx, 0FFFFFFFFh
0x180027da8  jz      short loc_180027DB7
0x180027daa  lea     rdx, aGetndistapihan; "GetNdisTapiHandle: wait for the outboun"...
0x180027db1  call    cs:__imp_TracePrintfA
0x180027db7  mov     ecx, esi
0x180027db9  call    ReleaseObjReadLock
0x180027dbe  mov     rcx, cs:RasTapiMutex; hMutex
0x180027dc5  test    rcx, rcx
0x180027dc8  jz      short loc_180027DDA
0x180027dca  call    cs:__imp_ReleaseMutex
0x180027dd0  test    eax, eax
0x180027dd2  jnz     short loc_180027DDA
0x180027dd4  call    cs:__imp_GetLastError
0x180027dda  mov     ecx, 0FAh; dwMilliseconds
0x180027ddf  call    cs:__imp_Sleep
0x180027de5  mov     rcx, cs:RasTapiMutex; hHandle
0x180027dec  test    rcx, rcx
0x180027def  jz      short loc_180027E05
0x180027df1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180027df4  call    cs:__imp_WaitForSingleObject
0x180027dfa  cmp     eax, 0FFFFFFFFh
0x180027dfd  jnz     short loc_180027E05
0x180027dff  call    cs:__imp_GetLastError
0x180027e05  lea     rdx, [rsp+28h+arg_0]
0x180027e0a  mov     ecx, esi
0x180027e0c  call    GetCallObjWithReadLock
0x180027e11  test    eax, eax
0x180027e13  jnz     short loc_180027E1A
0x180027e15  cmp     [rbx+40h], eax
0x180027e18  jnz     short loc_180027DB7
0x180027e1a  mov     rcx, [rbx+18h]
0x180027e1e  mov     rbx, [rsp+28h+arg_8]
0x180027e23  mov     rsi, [rsp+28h+arg_10]
0x180027e28  mov     [rdi], rcx
0x180027e2b  add     rsp, 20h
0x180027e2f  pop     rdi
0x180027e30  retn
```
