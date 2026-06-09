# IISCORE_PROTOCOL_MANAGER::InitializeInstance(IWorkerProcessFramework *)

- ea: `0x180030e44`
- end: `0x180030f86`
- name: `?InitializeInstance@IISCORE_PROTOCOL_MANAGER@@QEAAJPEAVIWorkerProcessFramework@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this, struct IWorkerProcessFramework *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030b30`

## callees

- `0x180030e44`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180030e87`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180030e87`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180030eb3`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180030eb3`
- `iisutil!IISGetPlatformType` at `0x180030ebf`
- `iisutil!IISGetPlatformType` at `0x180030ebf`
- `iisutil!PuCreateDebugPrintsObject` at `0x180030e6e`
- `iisutil!PuCreateDebugPrintsObject` at `0x180030e6e`

## string_xrefs

- `0x180030e80`: `Unable to Create Debug Print Object \n`
- `0x180030eac`: `System\CurrentControlSet\Services\W3SVC\Parameters\iiscore`

## pseudocode

```c
__int64 __fastcall IISCORE_PROTOCOL_MANAGER::InitializeInstance(
        IISCORE_PROTOCOL_MANAGER *this,
        struct IWorkerProcessFramework *a2)
{
  __int64 DebugPrintsObject; // rax
  int v5; // ebx
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  DebugPrintsObject = PuCreateDebugPrintsObject("iiscore", 1);
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
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\iiscore", 0);
  IISGetPlatformType();
  *((_QWORD *)this + 8) = a2;
  v5 = (*(__int64 (__fastcall **)(struct IWorkerProcessFramework *, __int64, char *))(*(_QWORD *)a2 + 24LL))(
         a2,
         200,
         (char *)this + 80);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 8) + 24LL))(
           *((_QWORD *)this + 8),
           300,
           (char *)this + 88);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)this + 8) + 16LL))(
             *((_QWORD *)this + 8),
             3,
             &v7);
      if ( v5 >= 0 )
      {
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 11) + 16LL))(*((_QWORD *)this + 11), 1);
        v5 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v7 + 40LL))(v7, 1, (char *)this + 96);
      }
    }
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180030e44  mov     [rsp+arg_0], rbx
0x180030e49  mov     [rsp+arg_8], rsi
0x180030e4e  push    rdi
0x180030e4f  sub     rsp, 20h
0x180030e53  mov     rbx, rdx
0x180030e56  mov     [rsp+28h+arg_10], 0
0x180030e5f  mov     rdi, rcx
0x180030e62  mov     edx, 1
0x180030e67  lea     rcx, aIiscore; "iiscore"
0x180030e6e  call    cs:__imp_PuCreateDebugPrintsObject
0x180030e74  mov     cs:g_pDebug, rax
0x180030e7b  test    rax, rax
0x180030e7e  jnz     short loc_180030E9D
0x180030e80  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x180030e87  call    cs:__imp_OutputDebugStringA
0x180030e8d  mov     rax, cs:g_pDebug
0x180030e94  test    rax, rax
0x180030e97  jz      loc_180030F71
0x180030e9d  cmp     dword ptr [rax+280h], 0
0x180030ea4  jz      loc_180030F71
0x180030eaa  xor     edx, edx
0x180030eac  lea     rcx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\W3"...
0x180030eb3  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180030eb9  mov     cs:g_dwDebugFlags, eax
0x180030ebf  call    cs:__imp_IISGetPlatformType
0x180030ec5  mov     [rdi+40h], rbx
0x180030ec9  lea     r8, [rdi+50h]
0x180030ecd  mov     rax, [rbx]
0x180030ed0  mov     edx, 0C8h
0x180030ed5  mov     rcx, rbx
0x180030ed8  mov     rax, [rax+18h]
0x180030edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ee1  mov     ebx, eax
0x180030ee3  test    eax, eax
0x180030ee5  js      short loc_180030F57
0x180030ee7  mov     rcx, [rdi+40h]
0x180030eeb  lea     r8, [rdi+58h]
0x180030eef  mov     edx, 12Ch
0x180030ef4  mov     rax, [rcx]
0x180030ef7  mov     rax, [rax+18h]
0x180030efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f00  mov     ebx, eax
0x180030f02  test    eax, eax
0x180030f04  js      short loc_180030F57
0x180030f06  mov     rcx, [rdi+40h]
0x180030f0a  lea     r8, [rsp+28h+arg_10]
0x180030f0f  mov     edx, 3
0x180030f14  mov     rax, [rcx]
0x180030f17  mov     rax, [rax+10h]
0x180030f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f20  mov     ebx, eax
0x180030f22  test    eax, eax
0x180030f24  js      short loc_180030F57
0x180030f26  mov     rcx, [rdi+58h]
0x180030f2a  mov     edx, 1
0x180030f2f  mov     rax, [rcx]
0x180030f32  mov     rax, [rax+10h]
0x180030f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f3b  mov     rcx, [rsp+28h+arg_10]
0x180030f40  lea     r8, [rdi+60h]
0x180030f44  mov     edx, 1
0x180030f49  mov     rax, [rcx]
0x180030f4c  mov     rax, [rax+28h]
0x180030f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f55  mov     ebx, eax
0x180030f57  mov     rcx, [rsp+28h+arg_10]
0x180030f5c  test    rcx, rcx
0x180030f5f  jz      short loc_180030F6D
0x180030f61  mov     rax, [rcx]
0x180030f64  mov     rax, [rax+8]
0x180030f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f6d  mov     eax, ebx
0x180030f6f  jmp     short loc_180030F76
0x180030f71  mov     eax, 80004005h
0x180030f76  mov     rbx, [rsp+28h+arg_0]
0x180030f7b  mov     rsi, [rsp+28h+arg_8]
0x180030f80  add     rsp, 20h
0x180030f84  pop     rdi
0x180030f85  retn
```
