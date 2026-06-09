# ScriptEngine::CheckForExternalProfiler(IActiveScriptProfilerCallback * *)

- ea: `0x18021b2f0`
- end: `0x18021b3bb`
- name: `?CheckForExternalProfiler@ScriptEngine@@SAJPEAPEAUIActiveScriptProfilerCallback@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1801c9468`
- `0x180225df8`

## callees

- `0x1801cc26b`
- `0x18021b2f0`
- `0x1803481f0`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x18021b346`
- `KERNEL32!GetEnvironmentVariableW` at `0x18021b346`
- `api-ms-win-downlevel-ole32-l1-1-0!IIDFromString` at `0x18021b360`
- `api-ms-win-downlevel-ole32-l1-1-0!IIDFromString` at `0x18021b360`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18021b389`
- `api-ms-win-downlevel-ole32-l1-1-0!CoCreateInstance` at `0x18021b389`

## pseudocode

```c
__int64 __fastcall ScriptEngine::CheckForExternalProfiler(LPVOID *ppv)
{
  HRESULT v2; // ebx
  GUID iid; // [rsp+30h] [rbp-78h] BYREF
  WCHAR Buffer[40]; // [rsp+40h] [rbp-68h] BYREF

  memset_0(Buffer, 0, 0x4Eu);
  iid = 0;
  v2 = -2147467259;
  if ( GetEnvironmentVariableW(L"JS_PROFILER", Buffer, 0x27u) )
  {
    v2 = IIDFromString(Buffer, &iid);
    if ( v2 >= 0 )
      return (unsigned int)CoCreateInstance(&iid, 0, 1u, &GUID_740eca23_7d9d_42e5_ba9d_f8b24b1c7a9b, ppv);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18021b2f0  mov     r11, rsp
0x18021b2f3  mov     [r11+10h], rbx
0x18021b2f7  mov     [r11+8], rcx
0x18021b2fb  push    rdi
0x18021b2fc  sub     rsp, 0A0h
0x18021b303  mov     rax, cs:__security_cookie
0x18021b30a  xor     rax, rsp
0x18021b30d  mov     [rsp+0A8h+var_18], rax
0x18021b315  xor     edx, edx; Val
0x18021b317  mov     rdi, rcx
0x18021b31a  lea     rcx, [r11-68h]; void *
0x18021b31e  lea     r8d, [rdx+4Eh]; Size
0x18021b322  call    memset_0
0x18021b327  xorps   xmm0, xmm0
0x18021b32a  lea     rdx, [rsp+0A8h+Buffer]; lpBuffer
0x18021b32f  mov     r8d, 27h ; '''; nSize
0x18021b335  lea     rcx, aJsProfiler; "JS_PROFILER"
0x18021b33c  movups  xmmword ptr [rsp+0A8h+iid.Data1], xmm0
0x18021b341  mov     ebx, 80004005h
0x18021b346  call    cs:__imp_GetEnvironmentVariableW
0x18021b34d  nop     dword ptr [rax+rax+00h]
0x18021b352  test    eax, eax
0x18021b354  jz      short loc_18021B397
0x18021b356  lea     rdx, [rsp+0A8h+iid]; lpiid
0x18021b35b  lea     rcx, [rsp+0A8h+Buffer]; lpsz
0x18021b360  call    cs:__imp_IIDFromString
0x18021b367  nop     dword ptr [rax+rax+00h]
0x18021b36c  mov     ebx, eax
0x18021b36e  test    eax, eax
0x18021b370  js      short loc_18021B397
0x18021b372  xor     edx, edx; pUnkOuter
0x18021b374  mov     [rsp+0A8h+ppv], rdi; ppv
0x18021b379  lea     r9, _GUID_740eca23_7d9d_42e5_ba9d_f8b24b1c7a9b; riid
0x18021b380  lea     rcx, [rsp+0A8h+iid]; rclsid
0x18021b385  lea     r8d, [rdx+1]; dwClsContext
0x18021b389  call    cs:__imp_CoCreateInstance
0x18021b390  nop     dword ptr [rax+rax+00h]
0x18021b395  mov     ebx, eax
0x18021b397  mov     eax, ebx
0x18021b399  mov     rcx, [rsp+0A8h+var_18]
0x18021b3a1  xor     rcx, rsp; StackCookie
0x18021b3a4  call    __security_check_cookie
0x18021b3a9  mov     rbx, [rsp+0A8h+arg_8]
0x18021b3b1  add     rsp, 0A0h
0x18021b3b8  pop     rdi
0x18021b3b9  retn
```
