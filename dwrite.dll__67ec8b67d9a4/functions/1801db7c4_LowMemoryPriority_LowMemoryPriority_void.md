# LowMemoryPriority::~LowMemoryPriority(void)

- ea: `0x1801db7c4`
- end: `0x1801db7f5`
- name: `??1LowMemoryPriority@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(LowMemoryPriority *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18011f190`
- `0x18012c688`
- `0x18031a7d2`
- `0x18031a920`
- `0x18031c0d0`
- `0x180325fa8`

## callees

- `0x1801db7c4`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x1801db7ea`
- `ntdll!NtSetInformationThread` at `0x1801db7ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801db7d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801db7d2`

## pseudocode

```c
void __fastcall LowMemoryPriority::~LowMemoryPriority(LowMemoryPriority *this)
{
  HANDLE CurrentThread; // rax
  int ThreadInformation; // [rsp+30h] [rbp+8h] BYREF

  if ( *(_DWORD *)this )
  {
    ThreadInformation = *(_DWORD *)this;
    CurrentThread = GetCurrentThread();
    NtSetInformationThread(CurrentThread, ThreadPagePriority, &ThreadInformation, 4u);
  }
}

```

## disassembly

```asm
0x1801db7c4  sub     rsp, 28h
0x1801db7c8  mov     eax, [rcx]
0x1801db7ca  test    eax, eax
0x1801db7cc  jz      short loc_1801DB7F0
0x1801db7ce  mov     [rsp+28h+ThreadInformation], eax
0x1801db7d2  call    cs:__imp_GetCurrentThread
0x1801db7d8  mov     r9d, 4; ThreadInformationLength
0x1801db7de  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x1801db7e3  mov     rcx, rax; ThreadHandle
0x1801db7e6  lea     edx, [r9+14h]; ThreadInformationClass
0x1801db7ea  call    cs:__imp_NtSetInformationThread
0x1801db7f0  add     rsp, 28h
0x1801db7f4  retn
```
