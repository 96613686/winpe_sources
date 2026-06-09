# NsiContainerCreateCallback

- ea: `0x1400a9d30`
- end: `0x1400a9e20`
- name: `NsiContainerCreateCallback`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400600d0`
- `0x1400600f4`
- `0x1400a9d30`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400a9d95`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400a9d95`
- `ntoskrnl!PsInsertSiloContext` at `0x1400a9de0`
- `ntoskrnl!PsInsertSiloContext` at `0x1400a9de0`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x1400a9dca`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x1400a9dca`
- `ntoskrnl!PsCreateSiloContext` at `0x1400a9d65`
- `ntoskrnl!PsCreateSiloContext` at `0x1400a9d65`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400a9db3`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400a9db3`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400a9e01`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400a9e01`

## pseudocode

```c
__int64 __fastcall NsiContainerCreateCallback(__int64 a1)
{
  __int64 result; // rax
  RPC_BINDING_HANDLE *v3; // rax
  __int64 v4; // rbx
  int inserted; // edi
  unsigned int SiloMonitorContextSlot; // eax
  RPC_BINDING_HANDLE *Binding; // [rsp+48h] [rbp+10h] BYREF

  Binding = 0;
  result = PsCreateSiloContext(a1, 56, 512, NsiContextCleanup, &Binding);
  if ( (int)result >= 0 )
  {
    v3 = Binding;
    *(_OWORD *)Binding = 0;
    *((_OWORD *)v3 + 1) = 0;
    *((_OWORD *)v3 + 2) = 0;
    v3[6] = 0;
    v4 = PsAttachSiloToCurrentThread(a1);
    inserted = NsipInitializeRpcState(Binding);
    PsDetachSiloFromCurrentThread(v4);
    if ( inserted < 0
      || (SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(NsiContainerMonitor),
          inserted = PsInsertSiloContext(a1, SiloMonitorContextSlot, Binding),
          inserted < 0) )
    {
      NsipCleanupRpcState(Binding);
    }
    PsDereferenceSiloContext(Binding);
    return (unsigned int)inserted;
  }
  return result;
}

```

## disassembly

```asm
0x1400a9d30  mov     r11, rsp
0x1400a9d33  mov     [r11+8], rbx
0x1400a9d37  mov     [r11+18h], rsi
0x1400a9d3b  push    rdi
0x1400a9d3c  sub     rsp, 30h
0x1400a9d40  lea     rax, [r11+10h]
0x1400a9d44  mov     qword ptr [r11+10h], 0
0x1400a9d4c  lea     r9, NsiContextCleanup
0x1400a9d53  mov     [r11-18h], rax
0x1400a9d57  mov     edx, 38h ; '8'
0x1400a9d5c  mov     r8d, 200h
0x1400a9d62  mov     rsi, rcx
0x1400a9d65  call    cs:__imp_PsCreateSiloContext
0x1400a9d6c  nop     dword ptr [rax+rax+00h]
0x1400a9d71  test    eax, eax
0x1400a9d73  js      loc_1400A9E0F
0x1400a9d79  mov     rax, [rsp+38h+Binding]
0x1400a9d7e  xorps   xmm0, xmm0
0x1400a9d81  xor     ecx, ecx
0x1400a9d83  movups  xmmword ptr [rax], xmm0
0x1400a9d86  movups  xmmword ptr [rax+10h], xmm0
0x1400a9d8a  movups  xmmword ptr [rax+20h], xmm0
0x1400a9d8e  mov     [rax+30h], rcx
0x1400a9d92  mov     rcx, rsi
0x1400a9d95  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400a9d9c  nop     dword ptr [rax+rax+00h]
0x1400a9da1  mov     rcx, [rsp+38h+Binding]; Binding
0x1400a9da6  mov     rbx, rax
0x1400a9da9  call    NsipInitializeRpcState
0x1400a9dae  mov     rcx, rbx
0x1400a9db1  mov     edi, eax
0x1400a9db3  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1400a9dba  nop     dword ptr [rax+rax+00h]
0x1400a9dbf  test    edi, edi
0x1400a9dc1  js      short loc_1400A9DF2
0x1400a9dc3  mov     rcx, cs:NsiContainerMonitor
0x1400a9dca  call    cs:__imp_PsGetSiloMonitorContextSlot
0x1400a9dd1  nop     dword ptr [rax+rax+00h]
0x1400a9dd6  mov     r8, [rsp+38h+Binding]
0x1400a9ddb  mov     rcx, rsi
0x1400a9dde  mov     edx, eax
0x1400a9de0  call    cs:__imp_PsInsertSiloContext
0x1400a9de7  nop     dword ptr [rax+rax+00h]
0x1400a9dec  mov     edi, eax
0x1400a9dee  test    eax, eax
0x1400a9df0  jns     short loc_1400A9DFC
0x1400a9df2  mov     rcx, [rsp+38h+Binding]
0x1400a9df7  call    NsipCleanupRpcState
0x1400a9dfc  mov     rcx, [rsp+38h+Binding]
0x1400a9e01  call    cs:__imp_PsDereferenceSiloContext
0x1400a9e08  nop     dword ptr [rax+rax+00h]
0x1400a9e0d  mov     eax, edi
0x1400a9e0f  mov     rbx, [rsp+38h+arg_0]
0x1400a9e14  mov     rsi, [rsp+38h+arg_10]
0x1400a9e19  add     rsp, 30h
0x1400a9e1d  pop     rdi
0x1400a9e1e  retn
```
