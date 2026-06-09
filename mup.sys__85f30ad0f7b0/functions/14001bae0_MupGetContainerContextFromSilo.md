# MupGetContainerContextFromSilo

- ea: `0x14001bae0`
- end: `0x14001bb70`
- name: `MupGetContainerContextFromSilo`
- size: `144`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140003140`
- `0x1400033d0`
- `0x140019994`
- `0x140019d10`
- `0x140019fb0`
- `0x14001a3c0`
- `0x14001a7b0`
- `0x14001b8b0`
- `0x14001ce70`
- `0x14001d040`

## callees

- `0x140002614`
- `0x14001bae0`

## import_xrefs

- `ntoskrnl!PsGetPermanentSiloContext` at `0x14001bb21`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14001bb21`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14001bb0d`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14001bb0d`

## pseudocode

```c
__int64 __fastcall MupGetContainerContextFromSilo(__int64 a1, _QWORD *a2)
{
  __int64 result; // rax
  unsigned int SiloMonitorContextSlot; // eax

  if ( a1 )
  {
    SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(ContainerMonitor);
    result = PsGetPermanentSiloContext(a1, SiloMonitorContextSlot, a2);
    if ( (int)result < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids, a1, result);
      }
      result = 0;
      *a2 = 0;
    }
  }
  else
  {
    result = 0;
    *a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001bae0  mov     [rsp+arg_0], rbx
0x14001bae5  push    rdi
0x14001bae6  sub     rsp, 30h
0x14001baea  mov     rbx, rdx
0x14001baed  mov     rdi, rcx
0x14001baf0  test    rcx, rcx
0x14001baf3  jnz     short loc_14001BB06
0x14001baf5  xor     eax, eax
0x14001baf7  mov     [rdx], rax
0x14001bafa  mov     rbx, [rsp+38h+arg_0]
0x14001baff  add     rsp, 30h
0x14001bb03  pop     rdi
0x14001bb04  retn
0x14001bb06  mov     rcx, cs:ContainerMonitor
0x14001bb0d  call    cs:__imp_PsGetSiloMonitorContextSlot
0x14001bb14  nop     dword ptr [rax+rax+00h]
0x14001bb19  mov     r8, rbx
0x14001bb1c  mov     rcx, rdi
0x14001bb1f  mov     edx, eax
0x14001bb21  call    cs:__imp_PsGetPermanentSiloContext
0x14001bb28  nop     dword ptr [rax+rax+00h]
0x14001bb2d  test    eax, eax
0x14001bb2f  jns     short loc_14001BAFA
0x14001bb31  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb38  lea     rdx, WPP_GLOBAL_Control
0x14001bb3f  cmp     rcx, rdx
0x14001bb42  jz      short loc_14001BB69
0x14001bb44  test    dword ptr [rcx+2Ch], 1000000h
0x14001bb4b  jz      short loc_14001BB69
0x14001bb4d  mov     rcx, [rcx+18h]
0x14001bb51  lea     r8, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids
0x14001bb58  mov     edx, 14h
0x14001bb5d  mov     [rsp+38h+var_18], eax
0x14001bb61  mov     r9, rdi
0x14001bb64  call    WPP_SF_qD
0x14001bb69  xor     eax, eax
0x14001bb6b  mov     [rbx], rax
0x14001bb6e  jmp     short loc_14001BAFA
```
