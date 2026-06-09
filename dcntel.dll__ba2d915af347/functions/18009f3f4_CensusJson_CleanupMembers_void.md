# CensusJson::CleanupMembers(void)

- ea: `0x18009f3f4`
- end: `0x18009f496`
- name: `?CleanupMembers@CensusJson@@AEAAXXZ`
- size: `162`
- prototype: `void __fastcall(CensusJson *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18009f050`
- `0x18009f0fc`
- `0x1800a2cd0`
- `0x1800a47e0`

## callees

- `0x18009f3f4`
- `0x18018e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009f44f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18009f44f`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18009f478`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18009f478`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009f406`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009f41d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009f482`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009f406`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009f41d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009f482`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18009f45f`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18009f45f`

## pseudocode

```c
void __fastcall CensusJson::CleanupMembers(CensusJson *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  TRACEHANDLE v5; // rcx
  void *v6; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 2) = 0;
  }
  if ( *(_QWORD *)this )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
    *(_QWORD *)this = 0;
  }
  v4 = (void *)*((_QWORD *)this + 4);
  if ( v4 )
    free(v4);
  v5 = *((_QWORD *)this + 6);
  if ( v5 != -1 )
  {
    CloseTrace(v5);
    *((_QWORD *)this + 6) = -1;
  }
  v6 = (void *)*((_QWORD *)this + 5);
  if ( v6 )
  {
    TerminateThread(v6, 0);
    CloseHandle(*((HANDLE *)this + 5));
    *((_QWORD *)this + 5) = 0;
  }
}

```

## disassembly

```asm
0x18009f3f4  push    rbx
0x18009f3f6  sub     rsp, 20h
0x18009f3fa  mov     rbx, rcx
0x18009f3fd  mov     rcx, [rcx+8]; hObject
0x18009f401  test    rcx, rcx
0x18009f404  jz      short loc_18009F414
0x18009f406  call    cs:__imp_CloseHandle
0x18009f40c  mov     qword ptr [rbx+8], 0
0x18009f414  mov     rcx, [rbx+10h]; hObject
0x18009f418  test    rcx, rcx
0x18009f41b  jz      short loc_18009F42B
0x18009f41d  call    cs:__imp_CloseHandle
0x18009f423  mov     qword ptr [rbx+10h], 0
0x18009f42b  mov     rcx, [rbx]
0x18009f42e  test    rcx, rcx
0x18009f431  jz      short loc_18009F446
0x18009f433  mov     rax, [rcx]
0x18009f436  mov     rax, [rax+10h]
0x18009f43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f43f  mov     qword ptr [rbx], 0
0x18009f446  mov     rcx, [rbx+20h]; Block
0x18009f44a  test    rcx, rcx
0x18009f44d  jz      short loc_18009F455
0x18009f44f  call    cs:__imp_free
0x18009f455  mov     rcx, [rbx+30h]; TraceHandle
0x18009f459  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18009f45d  jz      short loc_18009F46D
0x18009f45f  call    cs:__imp_CloseTrace
0x18009f465  mov     qword ptr [rbx+30h], 0FFFFFFFFFFFFFFFFh
0x18009f46d  mov     rcx, [rbx+28h]; hThread
0x18009f471  test    rcx, rcx
0x18009f474  jz      short loc_18009F490
0x18009f476  xor     edx, edx; dwExitCode
0x18009f478  call    cs:__imp_TerminateThread
0x18009f47e  mov     rcx, [rbx+28h]; hObject
0x18009f482  call    cs:__imp_CloseHandle
0x18009f488  mov     qword ptr [rbx+28h], 0
0x18009f490  add     rsp, 20h
0x18009f494  pop     rbx
0x18009f495  retn
```
