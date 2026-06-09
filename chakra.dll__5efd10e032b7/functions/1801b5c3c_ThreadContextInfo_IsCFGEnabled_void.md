# ThreadContextInfo::IsCFGEnabled(void)

- ea: `0x1801b5c3c`
- end: `0x1801b5cc2`
- name: `?IsCFGEnabled@ThreadContextInfo@@QEAA_NXZ`
- size: `134`
- prototype: `bool __fastcall(ThreadContextInfo *__hidden this)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1801b45b4`
- `0x1801b4b98`
- `0x1801b4f58`
- `0x1801b5ad4`
- `0x1803f07e8`
- `0x180560b70`
- `0x180560e34`

## callees

- `0x1801b5c3c`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801b5cac`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801b5cac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801b5c59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801b5c59`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x1801b5c77`
- `api-ms-win-core-processthreads-l1-1-1!GetProcessMitigationPolicy` at `0x1801b5c77`

## pseudocode

```c
bool __fastcall ThreadContextInfo::IsCFGEnabled(ThreadContextInfo *this)
{
  HANDLE CurrentProcess; // rax
  const WCHAR *v4; // rax
  _DWORD v5[6]; // [rsp+20h] [rbp-18h] BYREF

  v5[0] = 0;
  if ( !*((_BYTE *)this + 64) )
  {
    v4 = (const WCHAR *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 6) + 8LL))((char *)this + 48);
    *((_QWORD *)this + 7) = LoadLibraryExW(v4, 0, 0x800u);
    *((_BYTE *)this + 64) = 1;
  }
  CurrentProcess = GetCurrentProcess();
  GetProcessMitigationPolicy(CurrentProcess, 7, v5);
  return v5[0] & 1;
}

```

## disassembly

```asm
0x1801b5c3c  mov     [rsp+arg_0], rcx
0x1801b5c41  push    rbx
0x1801b5c42  sub     rsp, 30h
0x1801b5c46  mov     rbx, [rsp+38h+arg_0]
0x1801b5c4b  mov     [rsp+38h+var_18], 0
0x1801b5c53  cmp     byte ptr [rbx+40h], 0
0x1801b5c57  jz      short loc_1801B5C90
0x1801b5c59  call    cs:__imp_GetCurrentProcess
0x1801b5c60  nop     dword ptr [rax+rax+00h]
0x1801b5c65  mov     r9d, 4
0x1801b5c6b  lea     r8, [rsp+38h+var_18]
0x1801b5c70  mov     rcx, rax
0x1801b5c73  lea     edx, [r9+3]
0x1801b5c77  call    cs:__imp_GetProcessMitigationPolicy
0x1801b5c7e  nop     dword ptr [rax+rax+00h]
0x1801b5c83  mov     al, byte ptr [rsp+38h+var_18]
0x1801b5c87  and     al, 1
0x1801b5c89  add     rsp, 30h
0x1801b5c8d  pop     rbx
0x1801b5c8e  retn
0x1801b5c90  mov     rax, [rbx+30h]
0x1801b5c94  lea     rcx, [rbx+30h]
0x1801b5c98  mov     rax, [rax+8]
0x1801b5c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5ca1  mov     rcx, rax; lpLibFileName
0x1801b5ca4  xor     edx, edx; hFile
0x1801b5ca6  mov     r8d, 800h; dwFlags
0x1801b5cac  call    cs:__imp_LoadLibraryExW
0x1801b5cb3  nop     dword ptr [rax+rax+00h]
0x1801b5cb8  mov     [rbx+38h], rax
0x1801b5cbc  mov     byte ptr [rbx+40h], 1
0x1801b5cc0  jmp     short loc_1801B5C59
```
