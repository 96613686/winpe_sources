# CngSiloCreateNotify

- ea: `0x18005ce00`
- end: `0x18005ce58`
- name: `CngSiloCreateNotify`
- size: `88`
- prototype: `__int64 __fastcall(struct _EJOB *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18005ce00`
- `0x18005f0e8`
- `0x18006c688`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005ce12`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005ce12`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005ce39`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005ce39`

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
0x18005ce00  mov     [rsp+arg_0], rbx
0x18005ce05  mov     [rsp+arg_8], rsi
0x18005ce0a  push    rdi
0x18005ce0b  sub     rsp, 20h
0x18005ce0f  mov     rdi, rcx
0x18005ce12  call    cs:__imp_PsAttachSiloToCurrentThread
0x18005ce19  nop     dword ptr [rax+rax+00h]
0x18005ce1e  mov     rsi, rax
0x18005ce21  call    InitializeConfig
0x18005ce26  mov     ebx, eax
0x18005ce28  test    eax, eax
0x18005ce2a  js      short loc_18005CE36
0x18005ce2c  mov     rcx, rdi; struct _EJOB *
0x18005ce2f  call    InitializeTlsConfig
0x18005ce34  mov     ebx, eax
0x18005ce36  mov     rcx, rsi
0x18005ce39  call    cs:__imp_PsDetachSiloFromCurrentThread
0x18005ce40  nop     dword ptr [rax+rax+00h]
0x18005ce45  mov     rsi, [rsp+28h+arg_8]
0x18005ce4a  mov     eax, ebx
0x18005ce4c  mov     rbx, [rsp+28h+arg_0]
0x18005ce51  add     rsp, 20h
0x18005ce55  pop     rdi
0x18005ce56  retn
```
