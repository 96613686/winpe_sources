# LowMemoryPriority::LowMemoryPriority(void)

- ea: `0x18011f978`
- end: `0x18011fa00`
- name: `??0LowMemoryPriority@@QEAA@XZ`
- size: `136`
- prototype: `LowMemoryPriority *__fastcall(LowMemoryPriority *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18011e558`
- `0x18011f190`
- `0x18012c688`
- `0x1801e45dc`

## callees

- `0x18011f978`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18011f9b7`
- `ntdll!NtQueryInformationThread` at `0x18011f9b7`
- `ntdll!NtSetInformationThread` at `0x18011f9e2`
- `ntdll!NtSetInformationThread` at `0x18011f9e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011f98b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011f98b`

## pseudocode

```c
LowMemoryPriority *__fastcall LowMemoryPriority::LowMemoryPriority(LowMemoryPriority *this)
{
  HANDLE CurrentThread; // rax
  void *v3; // rdi
  unsigned int ThreadInformation; // [rsp+40h] [rbp+8h] BYREF
  int v6; // [rsp+48h] [rbp+10h] BYREF

  *(_DWORD *)this = 0;
  CurrentThread = GetCurrentThread();
  ThreadInformation = 0;
  v3 = CurrentThread;
  if ( NtQueryInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u, 0) >= 0
    && ThreadInformation > 2 )
  {
    v6 = 2;
    if ( NtSetInformationThread(v3, ThreadPagePriority, &v6, 4u) >= 0 )
      *(_DWORD *)this = ThreadInformation;
  }
  return this;
}

```

## disassembly

```asm
0x18011f978  mov     [rsp+arg_10], rbx
0x18011f97d  push    rdi
0x18011f97e  sub     rsp, 30h
0x18011f982  mov     rbx, rcx
0x18011f985  mov     dword ptr [rcx], 0
0x18011f98b  call    cs:__imp_GetCurrentThread
0x18011f991  mov     r9d, 4; ThreadInformationLength
0x18011f997  mov     [rsp+38h+ThreadInformation], 0
0x18011f99f  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x18011f9a4  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x18011f9ad  mov     rcx, rax; ThreadHandle
0x18011f9b0  mov     rdi, rax
0x18011f9b3  lea     edx, [r9+14h]; ThreadInformationClass
0x18011f9b7  call    cs:__imp_NtQueryInformationThread
0x18011f9bd  test    eax, eax
0x18011f9bf  js      short loc_18011F9F2
0x18011f9c1  cmp     [rsp+38h+ThreadInformation], 2
0x18011f9c6  jbe     short loc_18011F9F2
0x18011f9c8  mov     r9d, 4; ThreadInformationLength
0x18011f9ce  mov     [rsp+38h+arg_8], 2
0x18011f9d6  lea     r8, [rsp+38h+arg_8]; ThreadInformation
0x18011f9db  mov     rcx, rdi; ThreadHandle
0x18011f9de  lea     edx, [r9+14h]; ThreadInformationClass
0x18011f9e2  call    cs:__imp_NtSetInformationThread
0x18011f9e8  test    eax, eax
0x18011f9ea  js      short loc_18011F9F2
0x18011f9ec  mov     eax, [rsp+38h+ThreadInformation]
0x18011f9f0  mov     [rbx], eax
0x18011f9f2  mov     rax, rbx
0x18011f9f5  mov     rbx, [rsp+38h+arg_10]
0x18011f9fa  add     rsp, 30h
0x18011f9fe  pop     rdi
0x18011f9ff  retn
```
