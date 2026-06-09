# HidpIrpMajorSystemControl

- ea: `0x18003fb20`
- end: `0x18003fbb5`
- name: `HidpIrpMajorSystemControl`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004c00`

## callees

- `0x18000a264`
- `0x18003fb20`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18003fb95`
- `ntoskrnl!IofCompleteRequest` at `0x18003fb95`
- `WMILIB!WmiSystemControl` at `0x18003fb55`
- `WMILIB!WmiSystemControl` at `0x18003fb55`

## pseudocode

```c
__int64 __fastcall HidpIrpMajorSystemControl(__int64 a1, IRP *a2)
{
  bool v2; // zf
  struct _DEVICE_OBJECT *v6; // rdx
  struct _WMILIB_CONTEXT *v7; // rcx
  unsigned int v8; // esi
  __int64 v9; // r8
  int v11; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_BYTE *)(a1 + 24) == 0;
  v11 = 0;
  if ( v2 )
  {
    v6 = *(struct _DEVICE_OBJECT **)(a1 + 32);
    v7 = (struct _WMILIB_CONTEXT *)(a1 + 552);
  }
  else
  {
    v6 = *(struct _DEVICE_OBJECT **)(a1 + 80);
    v7 = (struct _WMILIB_CONTEXT *)(a1 + 304);
  }
  v8 = WmiSystemControl(v7, v6, a2, (PSYSCTL_IRP_DISPOSITION)&v11);
  if ( v11 )
  {
    if ( v11 == 1 )
      IofCompleteRequest(a2, 0);
    else
      return (unsigned int)HidpIrpMajorDefault(a1, a2, v9);
  }
  return v8;
}

```

## disassembly

```asm
0x18003fb20  mov     rax, rsp
0x18003fb23  mov     [rax+10h], rbx
0x18003fb27  mov     [rax+18h], rsi
0x18003fb2b  push    rdi
0x18003fb2c  sub     rsp, 20h
0x18003fb30  cmp     byte ptr [rcx+18h], 0
0x18003fb34  lea     r9, [rax+8]; IrpDisposition
0x18003fb38  mov     rdi, rdx
0x18003fb3b  mov     dword ptr [rax+8], 0
0x18003fb42  mov     rbx, rcx
0x18003fb45  mov     r8, rdx; Irp
0x18003fb48  jnz     short loc_18003FB7E
0x18003fb4a  mov     rdx, [rbx+20h]; DeviceObject
0x18003fb4e  add     rcx, 228h; WmiLibInfo
0x18003fb55  call    cs:__imp_WmiSystemControl
0x18003fb5c  nop     dword ptr [rax+rax+00h]
0x18003fb61  mov     ecx, [rsp+28h+arg_0]
0x18003fb65  mov     esi, eax
0x18003fb67  test    ecx, ecx
0x18003fb69  jnz     short loc_18003FB8B
0x18003fb6b  mov     rbx, [rsp+28h+arg_8]
0x18003fb70  mov     eax, esi
0x18003fb72  mov     rsi, [rsp+28h+arg_10]
0x18003fb77  add     rsp, 20h
0x18003fb7b  pop     rdi
0x18003fb7c  retn
0x18003fb7e  mov     rdx, [rbx+50h]
0x18003fb82  add     rcx, 130h
0x18003fb89  jmp     short loc_18003FB55
0x18003fb8b  sub     ecx, 1
0x18003fb8e  jnz     short loc_18003FBA3
0x18003fb90  xor     edx, edx; PriorityBoost
0x18003fb92  mov     rcx, rdi; Irp
0x18003fb95  call    cs:__imp_IofCompleteRequest
0x18003fb9c  nop     dword ptr [rax+rax+00h]
0x18003fba1  jmp     short loc_18003FB6B
0x18003fba3  sub     ecx, 1
0x18003fba6  mov     rdx, rdi
0x18003fba9  mov     rcx, rbx
0x18003fbac  call    HidpIrpMajorDefault
0x18003fbb1  mov     esi, eax
0x18003fbb3  jmp     short loc_18003FB6B
```
