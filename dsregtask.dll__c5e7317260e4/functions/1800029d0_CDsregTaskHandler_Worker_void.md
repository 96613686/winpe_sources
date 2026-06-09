# CDsregTaskHandler::Worker(void)

- ea: `0x1800029d0`
- end: `0x180002a90`
- name: `?Worker@CDsregTaskHandler@@EEAAJXZ`
- size: `192`
- prototype: `__int64 __fastcall(CDsregTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000273c`
- `0x1800029d0`
- `0x180003000`
- `0x180003074`
- `0x1800035d8`

## string_xrefs

- `0x180002a51`: `UpdateDevice`
- `0x1800029e2`: `CDsregTaskHandler::Worker`
- `0x180002a24`: `StringCompare`
- `0x180002a5d`: `%s: Unknown task specified: %s`

## pseudocode

```c
__int64 __fastcall CDsregTaskHandler::Worker(CDsregTaskHandler *this)
{
  const unsigned __int16 *v2; // rdx
  unsigned int v3; // r8d
  bool v4; // zf
  const unsigned __int16 *v5; // rdi
  int updated; // eax
  unsigned int v7; // ebx
  const wchar_t *v8; // r8
  int v10; // [rsp+30h] [rbp+8h] BYREF

  Logger::TraceVerbose(L"%s started", L"CDsregTaskHandler::Worker");
  v4 = *((_QWORD *)this + 1) == 0;
  v5 = &LocaleName;
  v10 = 0;
  if ( !v4 )
    v5 = (const unsigned __int16 *)*((_QWORD *)this + 1);
  updated = StringCompare(v5, v2, v3, &v10);
  v7 = updated;
  if ( updated < 0 )
  {
    v8 = L"StringCompare";
LABEL_5:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"CDsregTaskHandler::Worker",
      v8,
      (unsigned int)updated);
    goto LABEL_10;
  }
  if ( !v10 )
  {
    Logger::TraceError(L"%s: Unknown task specified: %s", L"CDsregTaskHandler::Worker", v5);
    goto LABEL_10;
  }
  updated = UpdateDevice();
  v7 = updated;
  if ( updated < 0 )
  {
    v8 = L"UpdateDevice";
    goto LABEL_5;
  }
LABEL_10:
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"CDsregTaskHandler::Worker", v7);
  return v7;
}

```

## disassembly

```asm
0x1800029d0  mov     [rsp+arg_8], rbx
0x1800029d5  mov     [rsp+arg_10], rsi
0x1800029da  push    rdi
0x1800029db  sub     rsp, 20h
0x1800029df  mov     rbx, rcx
0x1800029e2  lea     rsi, aCdsregtaskhand; "CDsregTaskHandler::Worker"
0x1800029e9  mov     rdx, rsi
0x1800029ec  lea     rcx, aSStarted; "%s started"
0x1800029f3  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800029f8  cmp     qword ptr [rbx+8], 0
0x1800029fd  lea     rdi, LocaleName
0x180002a04  lea     r9, [rsp+28h+arg_0]; int *
0x180002a09  mov     [rsp+28h+arg_0], 0
0x180002a11  cmovnz  rdi, [rbx+8]
0x180002a16  mov     rcx, rdi; unsigned __int16 *
0x180002a19  call    ?StringCompare@@YAJPEBG0KPEAH@Z; StringCompare(ushort const *,ushort const *,ulong,int *)
0x180002a1e  mov     ebx, eax
0x180002a20  test    eax, eax
0x180002a22  jns     short loc_180002A3F
0x180002a24  lea     r8, aStringcompare; "StringCompare"
0x180002a2b  mov     r9d, eax
0x180002a2e  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x."
0x180002a35  mov     rdx, rsi
0x180002a38  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180002a3d  jmp     short loc_180002A6C
0x180002a3f  cmp     [rsp+28h+arg_0], 0
0x180002a44  jz      short loc_180002A5A
0x180002a46  call    ?UpdateDevice@@YAJXZ; UpdateDevice(void)
0x180002a4b  mov     ebx, eax
0x180002a4d  test    eax, eax
0x180002a4f  jns     short loc_180002A6C
0x180002a51  lea     r8, aUpdatedevice; "UpdateDevice"
0x180002a58  jmp     short loc_180002A2B
0x180002a5a  mov     r8, rdi
0x180002a5d  lea     rcx, aSUnknownTaskSp; "%s: Unknown task specified: %s"
0x180002a64  mov     rdx, rsi
0x180002a67  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180002a6c  mov     r8d, ebx
0x180002a6f  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180002a76  mov     rdx, rsi
0x180002a79  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180002a7e  mov     rsi, [rsp+28h+arg_10]
0x180002a83  mov     eax, ebx
0x180002a85  mov     rbx, [rsp+28h+arg_8]
0x180002a8a  add     rsp, 20h
0x180002a8e  pop     rdi
0x180002a8f  retn
```
