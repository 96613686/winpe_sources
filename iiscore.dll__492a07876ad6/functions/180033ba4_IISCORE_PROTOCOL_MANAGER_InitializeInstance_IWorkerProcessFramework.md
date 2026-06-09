# IISCORE_PROTOCOL_MANAGER::InitializeInstance(IWorkerProcessFramework *)

- ea: `0x180033ba4`
- end: `0x180033cff`
- name: `?InitializeInstance@IISCORE_PROTOCOL_MANAGER@@QEAAJPEAVIWorkerProcessFramework@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(IISCORE_PROTOCOL_MANAGER *__hidden this, struct IWorkerProcessFramework *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033830`

## callees

- `0x180033ba4`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180033bed`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180033bed`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180033c1f`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180033c1f`
- `iisutil!IISGetPlatformType` at `0x180033c31`
- `iisutil!IISGetPlatformType` at `0x180033c31`
- `iisutil!PuCreateDebugPrintsObject` at `0x180033bce`
- `iisutil!PuCreateDebugPrintsObject` at `0x180033bce`

## string_xrefs

- `0x180033be6`: `Unable to Create Debug Print Object \n`
- `0x180033c18`: `System\CurrentControlSet\Services\W3SVC\Parameters\iiscore`

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
0x180033ba4  mov     [rsp+arg_0], rbx
0x180033ba9  mov     [rsp+arg_8], rsi
0x180033bae  push    rdi
0x180033baf  sub     rsp, 20h
0x180033bb3  mov     rbx, rdx
0x180033bb6  mov     [rsp+28h+arg_10], 0
0x180033bbf  mov     rdi, rcx
0x180033bc2  mov     edx, 1
0x180033bc7  lea     rcx, aIiscore; "iiscore"
0x180033bce  call    cs:__imp_PuCreateDebugPrintsObject
0x180033bd5  nop     dword ptr [rax+rax+00h]
0x180033bda  mov     cs:g_pDebug, rax
0x180033be1  test    rax, rax
0x180033be4  jnz     short loc_180033C09
0x180033be6  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x180033bed  call    cs:__imp_OutputDebugStringA
0x180033bf4  nop     dword ptr [rax+rax+00h]
0x180033bf9  mov     rax, cs:g_pDebug
0x180033c00  test    rax, rax
0x180033c03  jz      loc_180033CE9
0x180033c09  cmp     dword ptr [rax+280h], 0
0x180033c10  jz      loc_180033CE9
0x180033c16  xor     edx, edx
0x180033c18  lea     rcx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\W3"...
0x180033c1f  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180033c26  nop     dword ptr [rax+rax+00h]
0x180033c2b  mov     cs:g_dwDebugFlags, eax
0x180033c31  call    cs:__imp_IISGetPlatformType
0x180033c38  nop     dword ptr [rax+rax+00h]
0x180033c3d  mov     [rdi+40h], rbx
0x180033c41  lea     r8, [rdi+50h]
0x180033c45  mov     rax, [rbx]
0x180033c48  mov     edx, 0C8h
0x180033c4d  mov     rcx, rbx
0x180033c50  mov     rax, [rax+18h]
0x180033c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c59  mov     ebx, eax
0x180033c5b  test    eax, eax
0x180033c5d  js      short loc_180033CCF
0x180033c5f  mov     rcx, [rdi+40h]
0x180033c63  lea     r8, [rdi+58h]
0x180033c67  mov     edx, 12Ch
0x180033c6c  mov     rax, [rcx]
0x180033c6f  mov     rax, [rax+18h]
0x180033c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c78  mov     ebx, eax
0x180033c7a  test    eax, eax
0x180033c7c  js      short loc_180033CCF
0x180033c7e  mov     rcx, [rdi+40h]
0x180033c82  lea     r8, [rsp+28h+arg_10]
0x180033c87  mov     edx, 3
0x180033c8c  mov     rax, [rcx]
0x180033c8f  mov     rax, [rax+10h]
0x180033c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c98  mov     ebx, eax
0x180033c9a  test    eax, eax
0x180033c9c  js      short loc_180033CCF
0x180033c9e  mov     rcx, [rdi+58h]
0x180033ca2  mov     edx, 1
0x180033ca7  mov     rax, [rcx]
0x180033caa  mov     rax, [rax+10h]
0x180033cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033cb3  mov     rcx, [rsp+28h+arg_10]
0x180033cb8  lea     r8, [rdi+60h]
0x180033cbc  mov     edx, 1
0x180033cc1  mov     rax, [rcx]
0x180033cc4  mov     rax, [rax+28h]
0x180033cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ccd  mov     ebx, eax
0x180033ccf  mov     rcx, [rsp+28h+arg_10]
0x180033cd4  test    rcx, rcx
0x180033cd7  jz      short loc_180033CE5
0x180033cd9  mov     rax, [rcx]
0x180033cdc  mov     rax, [rax+8]
0x180033ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ce5  mov     eax, ebx
0x180033ce7  jmp     short loc_180033CEE
0x180033ce9  mov     eax, 80004005h
0x180033cee  mov     rbx, [rsp+28h+arg_0]
0x180033cf3  mov     rsi, [rsp+28h+arg_8]
0x180033cf8  add     rsp, 20h
0x180033cfc  pop     rdi
0x180033cfd  retn
```
