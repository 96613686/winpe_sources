# CEventLogger::StartFileTrace(void)

- ea: `0x180022430`
- end: `0x18002252e`
- name: `?StartFileTrace@CEventLogger@@EEAAJXZ`
- size: `254`
- prototype: `__int64 __fastcall(CEventLogger *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006fa0`
- `0x1800221a4`
- `0x180022430`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002249d`
- `KERNEL32!GetLastError` at `0x18002249d`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180022493`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180022493`
- `ADVAPI32!StartTraceW` at `0x1800224f7`
- `ADVAPI32!StartTraceW` at `0x1800224f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800224b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800224b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022502`

## string_xrefs

- `0x180022486`: `%systemroot%\system32\NDF\eventlog.etl`

## pseudocode

```c
__int64 __fastcall CEventLogger::StartFileTrace(CEventLogger *this)
{
  struct _EVENT_TRACE_PROPERTIES *v2; // rax
  struct _EVENT_TRACE_PROPERTIES *v3; // rdi
  __int64 v5; // rcx
  char *v6; // rax
  signed int LastError; // eax
  signed int started; // ebx

  v2 = AllocProperties();
  v3 = v2;
  if ( !v2 )
  {
    *((_QWORD *)this + 1) = -1;
    return 2147942414LL;
  }
  v2->LogFileMode |= 2u;
  v2->MaximumFileSize = 1;
  v5 = 520;
  v6 = (char *)this + 16;
  do
  {
    *v6++ = 0;
    --v5;
  }
  while ( v5 );
  if ( !ExpandEnvironmentStringsW(L"%systemroot%\\system32\\NDF\\eventlog.etl", (LPWSTR)this + 8, 0x104u) )
  {
    LastError = GetLastError();
    started = LastError;
    if ( LastError > 0 )
      started = (unsigned __int16)LastError | 0x80070000;
    if ( started < 0 )
    {
      CoTaskMemFree(v3);
      return (unsigned int)started;
    }
  }
  StringCchCopyW((unsigned __int16 *)((char *)v3 + v3->LogFileNameOffset), 0x104u, (const unsigned __int16 *)this + 8);
  v3->BufferSize = 128;
  v3->MinimumBuffers = 3;
  v3->MaximumBuffers = 20;
  started = StartTraceW((PTRACEHANDLE)this + 1, *((LPCWSTR *)this + 67), v3);
  CoTaskMemFree(v3);
  if ( started )
  {
    *((_QWORD *)this + 1) = -1;
    if ( started > 0 )
      return (unsigned __int16)started | 0x80070000;
    return (unsigned int)started;
  }
  return 0;
}

```

## disassembly

```asm
0x180022430  push    rbx
0x180022432  push    rbp
0x180022433  push    rsi
0x180022434  push    rdi
0x180022435  push    r14
0x180022437  sub     rsp, 20h
0x18002243b  mov     rsi, rcx
0x18002243e  call    ?AllocProperties@@YAPEAU_EVENT_TRACE_PROPERTIES@@XZ; AllocProperties(void)
0x180022443  mov     rdi, rax
0x180022446  test    rax, rax
0x180022449  jnz     short loc_18002245D
0x18002244b  mov     qword ptr [rsi+8], 0FFFFFFFFFFFFFFFFh
0x180022453  mov     eax, 8007000Eh
0x180022458  jmp     loc_180022523
0x18002245d  or      dword ptr [rax+40h], 2
0x180022461  lea     rbp, [rsi+10h]
0x180022465  mov     dword ptr [rax+3Ch], 1
0x18002246c  mov     ecx, 208h
0x180022471  mov     rax, rbp
0x180022474  mov     byte ptr [rax], 0
0x180022477  inc     rax
0x18002247a  sub     rcx, 1
0x18002247e  jnz     short loc_180022474
0x180022480  mov     r14d, 104h
0x180022486  lea     rcx, Src; "%systemroot%\\system32\\NDF\\eventlog.e"...
0x18002248d  mov     r8d, r14d; nSize
0x180022490  mov     rdx, rbp; lpDst
0x180022493  call    cs:__imp_ExpandEnvironmentStringsW
0x180022499  test    eax, eax
0x18002249b  jnz     short loc_1800224C3
0x18002249d  call    cs:__imp_GetLastError
0x1800224a3  mov     ebx, eax
0x1800224a5  test    eax, eax
0x1800224a7  jle     short loc_1800224B2
0x1800224a9  movzx   ebx, ax
0x1800224ac  or      ebx, 80070000h
0x1800224b2  test    ebx, ebx
0x1800224b4  jns     short loc_1800224C3
0x1800224b6  mov     rcx, rdi; pv
0x1800224b9  call    cs:__imp_CoTaskMemFree
0x1800224bf  mov     eax, ebx
0x1800224c1  jmp     short loc_180022523
0x1800224c3  mov     ecx, [rdi+70h]
0x1800224c6  mov     r8, rbp; unsigned __int16 *
0x1800224c9  add     rcx, rdi; unsigned __int16 *
0x1800224cc  mov     rdx, r14; unsigned __int64
0x1800224cf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800224d4  mov     dword ptr [rdi+30h], 80h
0x1800224db  lea     rcx, [rsi+8]; TraceHandle
0x1800224df  mov     dword ptr [rdi+34h], 3
0x1800224e6  mov     r8, rdi; Properties
0x1800224e9  mov     dword ptr [rdi+38h], 14h
0x1800224f0  mov     rdx, [rsi+218h]; InstanceName
0x1800224f7  call    cs:__imp_StartTraceW
0x1800224fd  mov     rcx, rdi; pv
0x180022500  mov     ebx, eax
0x180022502  call    cs:__imp_CoTaskMemFree
0x180022508  test    ebx, ebx
0x18002250a  jz      short loc_180022521
0x18002250c  mov     qword ptr [rsi+8], 0FFFFFFFFFFFFFFFFh
0x180022514  jle     short loc_1800224BF
0x180022516  movzx   ebx, bx
0x180022519  or      ebx, 80070000h
0x18002251f  jmp     short loc_1800224BF
0x180022521  xor     eax, eax
0x180022523  add     rsp, 20h
0x180022527  pop     r14
0x180022529  pop     rdi
0x18002252a  pop     rsi
0x18002252b  pop     rbp
0x18002252c  pop     rbx
0x18002252d  retn
```
