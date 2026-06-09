# ThreadProcHelper::~ThreadProcHelper(void)

- ea: `0x100380b7`
- end: `0x100380f5`
- name: `??1ThreadProcHelper@@MAE@XZ`
- size: `62`
- prototype: `void __thiscall(ThreadProcHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10037fa0`

## callees

- `0x10007630`
- `0x100380b7`
- `0x10038250`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x100380ee`
- `KERNEL32!CloseHandle` at `0x100380ee`
- `KERNEL32!DeleteCriticalSection` at `0x100380cc`
- `KERNEL32!DeleteCriticalSection` at `0x100380cc`

## pseudocode

```c
void __thiscall ThreadProcHelper::~ThreadProcHelper(ThreadProcHelper *this)
{
  int v2; // eax
  void *v3; // [esp+0h] [ebp-4h]

  *(_DWORD *)this = &ThreadProcHelper::`vftable';
  ThreadProcHelper::Shutdown(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 28));
  if ( *((_DWORD *)this + 6) )
    wil::details::CloseHandle(*((HANDLE *)this + 6), v3);
  v2 = *((_DWORD *)this + 4);
  if ( v2 )
  {
    if ( v2 != -1 )
      CloseHandle(*((HANDLE *)this + 4));
  }
}

```

## disassembly

```asm
0x100380b7  mov     edi, edi
0x100380b9  push    esi; void *
0x100380ba  mov     esi, ecx
0x100380bc  push    esi; this
0x100380bd  mov     dword ptr [esi], offset ??_7ThreadProcHelper@@6B@; const ThreadProcHelper::`vftable'
0x100380c3  call    ?Shutdown@ThreadProcHelper@@UAGJXZ; ThreadProcHelper::Shutdown(void)
0x100380c8  lea     eax, [esi+1Ch]
0x100380cb  push    eax; lpCriticalSection
0x100380cc  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x100380d2  cmp     dword ptr [esi+18h], 0
0x100380d6  jz      short loc_100380E0
0x100380d8  push    dword ptr [esi+18h]; hObject
0x100380db  call    ?CloseHandle@details@wil@@YGXPAX@Z; wil::details::CloseHandle(void *)
0x100380e0  mov     eax, [esi+10h]
0x100380e3  pop     esi
0x100380e4  test    eax, eax
0x100380e6  jz      short locret_100380F4
0x100380e8  cmp     eax, 0FFFFFFFFh
0x100380eb  jz      short locret_100380F4
0x100380ed  push    eax; hObject
0x100380ee  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100380f4  retn
```
