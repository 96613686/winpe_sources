# FreeThreadGlobals

- ea: `0x180013868`
- end: `0x1800138cd`
- name: `FreeThreadGlobals`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180014e08`

## callees

- `0x180013868`
- `0x1800142e0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180013885`
- `KERNEL32!CloseHandle` at `0x1800138a4`
- `KERNEL32!CloseHandle` at `0x180013885`
- `KERNEL32!CloseHandle` at `0x1800138a4`
- `KERNEL32!TlsGetValue` at `0x180013877`
- `KERNEL32!TlsGetValue` at `0x180013896`
- `KERNEL32!TlsGetValue` at `0x1800138b5`
- `KERNEL32!TlsGetValue` at `0x180013877`
- `KERNEL32!TlsGetValue` at `0x180013896`
- `KERNEL32!TlsGetValue` at `0x1800138b5`

## pseudocode

```c
void FreeThreadGlobals()
{
  void *Value; // rax
  void *v1; // rax
  void *v2; // rax
  CFreeRPCHandles *v3; // rcx

  if ( g_dwThreadEventIndex != -1 )
  {
    Value = TlsGetValue(g_dwThreadEventIndex);
    if ( Value )
      CloseHandle(Value);
  }
  if ( g_hThreadIndex != -1 )
  {
    v1 = TlsGetValue(g_hThreadIndex);
    if ( v1 )
      CloseHandle(v1);
  }
  if ( g_hBindIndex != -1 )
  {
    v2 = TlsGetValue(g_hBindIndex);
    if ( v2 )
      CFreeRPCHandles::Remove(v3, v2);
  }
}

```

## disassembly

```asm
0x180013868  sub     rsp, 28h
0x18001386c  mov     ecx, cs:?g_dwThreadEventIndex@@3KA; dwTlsIndex
0x180013872  cmp     ecx, 0FFFFFFFFh
0x180013875  jz      short loc_18001388B
0x180013877  call    cs:__imp_TlsGetValue
0x18001387d  test    rax, rax
0x180013880  jz      short loc_18001388B
0x180013882  mov     rcx, rax; hObject
0x180013885  call    cs:__imp_CloseHandle
0x18001388b  mov     ecx, cs:?g_hThreadIndex@@3KA; dwTlsIndex
0x180013891  cmp     ecx, 0FFFFFFFFh
0x180013894  jz      short loc_1800138AA
0x180013896  call    cs:__imp_TlsGetValue
0x18001389c  test    rax, rax
0x18001389f  jz      short loc_1800138AA
0x1800138a1  mov     rcx, rax; hObject
0x1800138a4  call    cs:__imp_CloseHandle
0x1800138aa  mov     ecx, cs:?g_hBindIndex@@3KA; dwTlsIndex
0x1800138b0  cmp     ecx, 0FFFFFFFFh
0x1800138b3  jz      short loc_1800138C8
0x1800138b5  call    cs:__imp_TlsGetValue
0x1800138bb  test    rax, rax
0x1800138be  jz      short loc_1800138C8
0x1800138c0  mov     rdx, rax; void *
0x1800138c3  call    ?Remove@CFreeRPCHandles@@QEAAXPEAX@Z; CFreeRPCHandles::Remove(void *)
0x1800138c8  add     rsp, 28h
0x1800138cc  retn
```
