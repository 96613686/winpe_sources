# SystemFunction028

- ea: `0x180002550`
- end: `0x18000259f`
- name: `SystemFunction028`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001f50`
- `0x180002550`

## import_xrefs

- `ntdll!NtClose` at `0x18000258a`
- `ntdll!NtClose` at `0x18000258a`
- `RPCRT4!NDRCContextBinding` at `0x180002562`
- `RPCRT4!NDRCContextBinding` at `0x180002562`

## pseudocode

```c
int __fastcall SystemFunction028(void *a1, _OWORD *a2)
{
  RPC_BINDING_HANDLE v3; // rax
  int result; // eax
  int v5; // ebx
  HANDLE Handle; // [rsp+40h] [rbp+18h] BYREF

  Handle = 0;
  v3 = NDRCContextBinding(a1);
  result = SystemFunction034(v3, &Handle, a2);
  v5 = result;
  if ( Handle )
  {
    NtClose(Handle);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180002550  push    rbx
0x180002552  sub     rsp, 20h
0x180002556  mov     rbx, rdx
0x180002559  mov     [rsp+28h+Handle], 0
0x180002562  call    cs:__imp_NDRCContextBinding
0x180002569  nop     dword ptr [rax+rax+00h]
0x18000256e  mov     r8, rbx
0x180002571  lea     rdx, [rsp+28h+Handle]
0x180002576  mov     rcx, rax
0x180002579  call    SystemFunction034
0x18000257e  mov     rcx, [rsp+28h+Handle]; Handle
0x180002583  mov     ebx, eax
0x180002585  test    rcx, rcx
0x180002588  jz      short loc_180002598
0x18000258a  call    cs:__imp_NtClose
0x180002591  nop     dword ptr [rax+rax+00h]
0x180002596  mov     eax, ebx
0x180002598  add     rsp, 20h
0x18000259c  pop     rbx
0x18000259d  retn
```
