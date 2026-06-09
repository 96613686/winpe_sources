# CngSiloCreateNotify

- ea: `0x18005d6f0`
- end: `0x18005d748`
- name: `CngSiloCreateNotify`
- size: `88`
- prototype: `__int64 __fastcall(struct _EJOB *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18005d6f0`
- `0x18005f9d8`
- `0x18006d088`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005d702`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005d702`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005d729`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005d729`

## pseudocode

```c
__int64 __fastcall CngSiloCreateNotify(struct _EJOB *a1)
{
  __int64 v2; // rsi
  int v3; // ebx

  v2 = PsAttachSiloToCurrentThread();
  v3 = InitializeConfig();
  if ( v3 >= 0 )
    v3 = InitializeTlsConfig(a1);
  PsDetachSiloFromCurrentThread(v2);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18005d6f0  mov     [rsp+arg_0], rbx
0x18005d6f5  mov     [rsp+arg_8], rsi
0x18005d6fa  push    rdi
0x18005d6fb  sub     rsp, 20h
0x18005d6ff  mov     rdi, rcx
0x18005d702  call    cs:__imp_PsAttachSiloToCurrentThread
0x18005d709  nop     dword ptr [rax+rax+00h]
0x18005d70e  mov     rsi, rax
0x18005d711  call    InitializeConfig
0x18005d716  mov     ebx, eax
0x18005d718  test    eax, eax
0x18005d71a  js      short loc_18005D726
0x18005d71c  mov     rcx, rdi; struct _EJOB *
0x18005d71f  call    InitializeTlsConfig
0x18005d724  mov     ebx, eax
0x18005d726  mov     rcx, rsi
0x18005d729  call    cs:__imp_PsDetachSiloFromCurrentThread
0x18005d730  nop     dword ptr [rax+rax+00h]
0x18005d735  mov     rsi, [rsp+28h+arg_8]
0x18005d73a  mov     eax, ebx
0x18005d73c  mov     rbx, [rsp+28h+arg_0]
0x18005d741  add     rsp, 20h
0x18005d745  pop     rdi
0x18005d746  retn
```
