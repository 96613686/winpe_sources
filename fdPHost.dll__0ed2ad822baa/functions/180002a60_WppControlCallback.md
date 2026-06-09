# WppControlCallback

- ea: `0x180002a60`
- end: `0x180002ae2`
- name: `WppControlCallback`
- size: `130`
- prototype: `__int64 __fastcall(WMIDPREQUESTCODE RequestCode, _QWORD *RequestContext, ULONG *BufferSize, PVOID Buffer)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002a60`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceEnableFlags` at `0x180002aae`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceEnableFlags` at `0x180002aae`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceEnableLevel` at `0x180002aa2`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceEnableLevel` at `0x180002aa2`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceLoggerHandle` at `0x180002a96`
- `api-ms-win-eventing-classicprovider-l1-1-0!GetTraceLoggerHandle` at `0x180002a96`

## pseudocode

```c
__int64 __fastcall WppControlCallback(
        WMIDPREQUESTCODE RequestCode,
        _QWORD *RequestContext,
        ULONG *BufferSize,
        PVOID Buffer)
{
  int v5; // ecx
  __int64 result; // rax
  TRACEHANDLE TraceLoggerHandle; // rdi
  ULONG TraceEnableFlags; // eax
  UCHAR TraceEnableLevel; // si

  *BufferSize = 0;
  v5 = RequestCode - 4;
  if ( v5 )
  {
    if ( v5 != 1 )
      return 87;
    TraceLoggerHandle = 0;
    TraceEnableFlags = 0;
    TraceEnableLevel = 0;
  }
  else
  {
    TraceLoggerHandle = GetTraceLoggerHandle(Buffer);
    TraceEnableLevel = GetTraceEnableLevel(TraceLoggerHandle);
    TraceEnableFlags = GetTraceEnableFlags(TraceLoggerHandle);
  }
  if ( (*((_BYTE *)RequestContext + 26) & 2) != 0 )
  {
    if ( RequestContext[2] )
      RequestContext = (_QWORD *)RequestContext[2];
  }
  *((_DWORD *)RequestContext + 7) = TraceEnableFlags;
  result = 0;
  RequestContext[2] = TraceLoggerHandle;
  *((_BYTE *)RequestContext + 25) = TraceEnableLevel;
  return result;
}

```

## disassembly

```asm
0x180002a60  mov     [rsp+arg_0], rbx
0x180002a65  mov     [rsp+arg_8], rsi
0x180002a6a  push    rdi
0x180002a6b  sub     rsp, 20h
0x180002a6f  mov     dword ptr [r8], 0
0x180002a76  mov     rbx, rdx
0x180002a79  sub     ecx, 4
0x180002a7c  jz      short loc_180002A93
0x180002a7e  cmp     ecx, 1
0x180002a81  jz      short loc_180002A8A
0x180002a83  mov     eax, 57h ; 'W'
0x180002a88  jmp     short loc_180002AD2
0x180002a8a  xor     edi, edi
0x180002a8c  xor     eax, eax
0x180002a8e  xor     sil, sil
0x180002a91  jmp     short loc_180002AB4
0x180002a93  mov     rcx, r9; Buffer
0x180002a96  call    cs:__imp_GetTraceLoggerHandle
0x180002a9c  mov     rcx, rax; TraceHandle
0x180002a9f  mov     rdi, rax
0x180002aa2  call    cs:__imp_GetTraceEnableLevel
0x180002aa8  mov     rcx, rdi; TraceHandle
0x180002aab  mov     sil, al
0x180002aae  call    cs:__imp_GetTraceEnableFlags
0x180002ab4  test    byte ptr [rbx+1Ah], 2
0x180002ab8  jz      short loc_180002AC5
0x180002aba  mov     rcx, [rbx+10h]
0x180002abe  test    rcx, rcx
0x180002ac1  cmovnz  rbx, rcx
0x180002ac5  mov     [rbx+1Ch], eax
0x180002ac8  xor     eax, eax
0x180002aca  mov     [rbx+10h], rdi
0x180002ace  mov     [rbx+19h], sil
0x180002ad2  mov     rbx, [rsp+28h+arg_0]
0x180002ad7  mov     rsi, [rsp+28h+arg_8]
0x180002adc  add     rsp, 20h
0x180002ae0  pop     rdi
0x180002ae1  retn
```
