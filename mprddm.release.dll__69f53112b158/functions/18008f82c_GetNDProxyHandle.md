# GetNDProxyHandle

- ea: `0x18008f82c`
- end: `0x18008f94e`
- name: `GetNDProxyHandle`
- size: `290`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18008b5f8`
- `0x18008b828`
- `0x18008beac`
- `0x18008c2d8`
- `0x18008c578`
- `0x18008cb84`

## callees

- `0x18008ed64`
- `0x18008f82c`
- `0x180090714`
- `0x180095010`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x18008f8c4`
- `KERNEL32!ReleaseMutex` at `0x18008f8c4`
- `KERNEL32!Sleep` at `0x18008f8e5`
- `KERNEL32!Sleep` at `0x18008f8e5`
- `KERNEL32!GetLastError` at `0x18008f8d4`
- `KERNEL32!GetLastError` at `0x18008f911`
- `KERNEL32!GetLastError` at `0x18008f8d4`
- `KERNEL32!GetLastError` at `0x18008f911`
- `KERNEL32!WaitForSingleObject` at `0x18008f900`
- `KERNEL32!WaitForSingleObject` at `0x18008f900`
- `rtutils!TracePrintfA` at `0x18008f8a5`
- `rtutils!TracePrintfA` at `0x18008f8a5`

## string_xrefs

- `0x18008f89e`: `GetNdisTapiHandle: wait for the outbound call to complete...`
- `0x18008f87e`: `GetNdisTapiHandle: wait for the outbound call to complete...`

## pseudocode

```c
__int64 __fastcall GetNDProxyHandle(__int64 a1, _QWORD *a2)
{
  __int64 result; // rax
  unsigned int v5; // esi
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  result = 0;
  v6 = a1;
  *a2 = 0;
  v5 = *(_DWORD *)(a1 + 8);
  if ( *(_DWORD *)a1 == 1329807692 && *(_DWORD *)(a1 + 64) )
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
          gNdpspEtwContext,
          *((_QWORD *)&xmmword_1800D0BE0 + 1),
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
0x18008f82c  mov     [rsp+arg_8], rbx
0x18008f831  mov     [rsp+arg_10], rsi
0x18008f836  push    rdi
0x18008f837  sub     rsp, 20h
0x18008f83b  xor     eax, eax
0x18008f83d  mov     [rsp+28h+arg_0], rcx
0x18008f842  and     [rdx], rax
0x18008f845  mov     rdi, rdx
0x18008f848  cmp     dword ptr [rcx], 4F43414Ch
0x18008f84e  mov     rbx, rcx
0x18008f851  mov     esi, [rcx+8]
0x18008f854  jnz     loc_18008F936
0x18008f85a  cmp     [rcx+40h], eax
0x18008f85d  jz      loc_18008F936
0x18008f863  cmp     cs:gIsndpspEtwTracingAvailable, eax
0x18008f869  jz      short loc_18008F893
0x18008f86b  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x18008f872  test    rdx, rdx
0x18008f875  jz      short loc_18008F8B1
0x18008f877  mov     rcx, cs:gNdpspEtwContext
0x18008f87e  lea     r8, aGetndistapihan_0; "GetNdisTapiHandle: wait for the outboun"...
0x18008f885  mov     rax, cs:gNdpspTemplateFunc
0x18008f88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f891  jmp     short loc_18008F8B1
0x18008f893  mov     ecx, cs:dwTraceId; dwTraceID
0x18008f899  cmp     ecx, 0FFFFFFFFh
0x18008f89c  jz      short loc_18008F8B1
0x18008f89e  lea     rdx, aGetndistapihan; "GetNdisTapiHandle: wait for the outboun"...
0x18008f8a5  call    cs:__imp_TracePrintfA
0x18008f8ac  nop     dword ptr [rax+rax+00h]
0x18008f8b1  mov     ecx, esi
0x18008f8b3  call    ReleaseObjReadLock
0x18008f8b8  mov     rcx, cs:RasTapiMutex; hMutex
0x18008f8bf  test    rcx, rcx
0x18008f8c2  jz      short loc_18008F8E0
0x18008f8c4  call    cs:__imp_ReleaseMutex
0x18008f8cb  nop     dword ptr [rax+rax+00h]
0x18008f8d0  test    eax, eax
0x18008f8d2  jnz     short loc_18008F8E0
0x18008f8d4  call    cs:__imp_GetLastError
0x18008f8db  nop     dword ptr [rax+rax+00h]
0x18008f8e0  mov     ecx, 0FAh; dwMilliseconds
0x18008f8e5  call    cs:__imp_Sleep
0x18008f8ec  nop     dword ptr [rax+rax+00h]
0x18008f8f1  mov     rcx, cs:RasTapiMutex; hHandle
0x18008f8f8  test    rcx, rcx
0x18008f8fb  jz      short loc_18008F91D
0x18008f8fd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18008f900  call    cs:__imp_WaitForSingleObject
0x18008f907  nop     dword ptr [rax+rax+00h]
0x18008f90c  cmp     eax, 0FFFFFFFFh
0x18008f90f  jnz     short loc_18008F91D
0x18008f911  call    cs:__imp_GetLastError
0x18008f918  nop     dword ptr [rax+rax+00h]
0x18008f91d  lea     rdx, [rsp+28h+arg_0]
0x18008f922  mov     ecx, esi
0x18008f924  call    GetCallObjWithReadLock
0x18008f929  test    eax, eax
0x18008f92b  jnz     short loc_18008F936
0x18008f92d  cmp     [rbx+40h], eax
0x18008f930  jnz     loc_18008F8B1
0x18008f936  mov     rcx, [rbx+18h]
0x18008f93a  mov     rbx, [rsp+28h+arg_8]
0x18008f93f  mov     rsi, [rsp+28h+arg_10]
0x18008f944  mov     [rdi], rcx
0x18008f947  add     rsp, 20h
0x18008f94b  pop     rdi
0x18008f94c  retn
```
