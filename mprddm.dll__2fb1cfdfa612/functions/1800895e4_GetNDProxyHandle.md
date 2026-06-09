# GetNDProxyHandle

- ea: `0x1800895e4`
- end: `0x1800896dd`
- name: `GetNDProxyHandle`
- size: `249`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800855e8`
- `0x180085818`
- `0x180085e4c`
- `0x18008625c`
- `0x1800864d8`
- `0x180086ad0`

## callees

- `0x180088b1c`
- `0x1800895e4`
- `0x18008a408`
- `0x18008e010`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x180089676`
- `KERNEL32!ReleaseMutex` at `0x180089676`
- `KERNEL32!Sleep` at `0x18008968b`
- `KERNEL32!Sleep` at `0x18008968b`
- `KERNEL32!GetLastError` at `0x180089680`
- `KERNEL32!GetLastError` at `0x1800896ab`
- `KERNEL32!GetLastError` at `0x180089680`
- `KERNEL32!GetLastError` at `0x1800896ab`
- `KERNEL32!WaitForSingleObject` at `0x1800896a0`
- `KERNEL32!WaitForSingleObject` at `0x1800896a0`
- `rtutils!TracePrintfA` at `0x18008965d`
- `rtutils!TracePrintfA` at `0x18008965d`

## string_xrefs

- `0x180089656`: `GetNdisTapiHandle: wait for the outbound call to complete...`
- `0x180089636`: `GetNdisTapiHandle: wait for the outbound call to complete...`

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
      if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
          gNdpspEtwContext,
          *((_QWORD *)&xmmword_1800C9BE0 + 1),
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
0x1800895e4  mov     [rsp+arg_8], rbx
0x1800895e9  mov     [rsp+arg_10], rsi
0x1800895ee  push    rdi
0x1800895ef  sub     rsp, 20h
0x1800895f3  xor     eax, eax
0x1800895f5  mov     [rsp+28h+arg_0], rcx
0x1800895fa  mov     [rdx], rax
0x1800895fd  mov     rdi, rdx
0x180089600  cmp     dword ptr [rcx], 4F43414Ch
0x180089606  mov     rbx, rcx
0x180089609  jnz     loc_1800896C6
0x18008960f  cmp     [rcx+40h], eax
0x180089612  jz      loc_1800896C6
0x180089618  cmp     cs:gIsndpspEtwTracingAvailable, eax
0x18008961e  mov     esi, [rcx+8]
0x180089621  jz      short loc_18008964B
0x180089623  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x18008962a  test    rdx, rdx
0x18008962d  jz      short loc_180089663
0x18008962f  mov     rcx, cs:gNdpspEtwContext
0x180089636  lea     r8, aGetndistapihan_0; "GetNdisTapiHandle: wait for the outboun"...
0x18008963d  mov     rax, cs:gNdpspTemplateFunc
0x180089644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089649  jmp     short loc_180089663
0x18008964b  mov     ecx, cs:dwTraceId; dwTraceID
0x180089651  cmp     ecx, 0FFFFFFFFh
0x180089654  jz      short loc_180089663
0x180089656  lea     rdx, aGetndistapihan; "GetNdisTapiHandle: wait for the outboun"...
0x18008965d  call    cs:__imp_TracePrintfA
0x180089663  mov     ecx, esi
0x180089665  call    ReleaseObjReadLock
0x18008966a  mov     rcx, cs:RasTapiMutex; hMutex
0x180089671  test    rcx, rcx
0x180089674  jz      short loc_180089686
0x180089676  call    cs:__imp_ReleaseMutex
0x18008967c  test    eax, eax
0x18008967e  jnz     short loc_180089686
0x180089680  call    cs:__imp_GetLastError
0x180089686  mov     ecx, 0FAh; dwMilliseconds
0x18008968b  call    cs:__imp_Sleep
0x180089691  mov     rcx, cs:RasTapiMutex; hHandle
0x180089698  test    rcx, rcx
0x18008969b  jz      short loc_1800896B1
0x18008969d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800896a0  call    cs:__imp_WaitForSingleObject
0x1800896a6  cmp     eax, 0FFFFFFFFh
0x1800896a9  jnz     short loc_1800896B1
0x1800896ab  call    cs:__imp_GetLastError
0x1800896b1  lea     rdx, [rsp+28h+arg_0]
0x1800896b6  mov     ecx, esi
0x1800896b8  call    GetCallObjWithReadLock
0x1800896bd  test    eax, eax
0x1800896bf  jnz     short loc_1800896C6
0x1800896c1  cmp     [rbx+40h], eax
0x1800896c4  jnz     short loc_180089663
0x1800896c6  mov     rcx, [rbx+18h]
0x1800896ca  mov     rbx, [rsp+28h+arg_8]
0x1800896cf  mov     rsi, [rsp+28h+arg_10]
0x1800896d4  mov     [rdi], rcx
0x1800896d7  add     rsp, 20h
0x1800896db  pop     rdi
0x1800896dc  retn
```
