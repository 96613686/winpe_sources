# MupGetContainerContextFromSilo

- ea: `0x14001ba90`
- end: `0x14001bb20`
- name: `MupGetContainerContextFromSilo`
- size: `144`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140003140`
- `0x1400033d0`
- `0x140019944`
- `0x140019cc0`
- `0x140019f60`
- `0x14001a370`
- `0x14001a760`
- `0x14001b860`
- `0x14001ce20`
- `0x14001cff0`

## callees

- `0x140002614`
- `0x14001ba90`

## import_xrefs

- `ntoskrnl!PsGetPermanentSiloContext` at `0x14001bad1`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14001bad1`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14001babd`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14001babd`

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
0x14001ba90  mov     [rsp+arg_0], rbx
0x14001ba95  push    rdi
0x14001ba96  sub     rsp, 30h
0x14001ba9a  mov     rbx, rdx
0x14001ba9d  mov     rdi, rcx
0x14001baa0  test    rcx, rcx
0x14001baa3  jnz     short loc_14001BAB6
0x14001baa5  xor     eax, eax
0x14001baa7  mov     [rdx], rax
0x14001baaa  mov     rbx, [rsp+38h+arg_0]
0x14001baaf  add     rsp, 30h
0x14001bab3  pop     rdi
0x14001bab4  retn
0x14001bab6  mov     rcx, cs:ContainerMonitor
0x14001babd  call    cs:__imp_PsGetSiloMonitorContextSlot
0x14001bac4  nop     dword ptr [rax+rax+00h]
0x14001bac9  mov     r8, rbx
0x14001bacc  mov     rcx, rdi
0x14001bacf  mov     edx, eax
0x14001bad1  call    cs:__imp_PsGetPermanentSiloContext
0x14001bad8  nop     dword ptr [rax+rax+00h]
0x14001badd  test    eax, eax
0x14001badf  jns     short loc_14001BAAA
0x14001bae1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bae8  lea     rdx, WPP_GLOBAL_Control
0x14001baef  cmp     rcx, rdx
0x14001baf2  jz      short loc_14001BB19
0x14001baf4  test    dword ptr [rcx+2Ch], 1000000h
0x14001bafb  jz      short loc_14001BB19
0x14001bafd  mov     rcx, [rcx+18h]
0x14001bb01  lea     r8, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids
0x14001bb08  mov     edx, 14h
0x14001bb0d  mov     [rsp+38h+var_18], eax
0x14001bb11  mov     r9, rdi
0x14001bb14  call    WPP_SF_qD
0x14001bb19  xor     eax, eax
0x14001bb1b  mov     [rbx], rax
0x14001bb1e  jmp     short loc_14001BAAA
```
