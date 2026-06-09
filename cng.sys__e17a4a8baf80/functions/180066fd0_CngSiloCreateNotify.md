# CngSiloCreateNotify

- ea: `0x180066fd0`
- end: `0x180067028`
- name: `CngSiloCreateNotify`
- size: `88`
- prototype: `__int64 __fastcall(struct _EJOB *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180066fd0`
- `0x1800692b8`
- `0x180076828`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180066fe2`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180066fe2`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180067009`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180067009`

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
0x180066fd0  mov     [rsp+arg_0], rbx
0x180066fd5  mov     [rsp+arg_8], rsi
0x180066fda  push    rdi
0x180066fdb  sub     rsp, 20h
0x180066fdf  mov     rdi, rcx
0x180066fe2  call    cs:__imp_PsAttachSiloToCurrentThread
0x180066fe9  nop     dword ptr [rax+rax+00h]
0x180066fee  mov     rsi, rax
0x180066ff1  call    InitializeConfig
0x180066ff6  mov     ebx, eax
0x180066ff8  test    eax, eax
0x180066ffa  js      short loc_180067006
0x180066ffc  mov     rcx, rdi; struct _EJOB *
0x180066fff  call    InitializeTlsConfig
0x180067004  mov     ebx, eax
0x180067006  mov     rcx, rsi
0x180067009  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180067010  nop     dword ptr [rax+rax+00h]
0x180067015  mov     rsi, [rsp+28h+arg_8]
0x18006701a  mov     eax, ebx
0x18006701c  mov     rbx, [rsp+28h+arg_0]
0x180067021  add     rsp, 20h
0x180067025  pop     rdi
0x180067026  retn
```
