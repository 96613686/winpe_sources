# DfscGetContainerContextFromIrp

- ea: `0x140001010`
- end: `0x1400010ca`
- name: `DfscGetContainerContextFromIrp`
- size: `186`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x140004314`
- `0x140014910`
- `0x140014d30`
- `0x140015050`
- `0x14001520c`
- `0x140015520`
- `0x1400158f0`
- `0x140015f30`
- `0x140016070`
- `0x1400169f8`
- `0x140016b80`
- `0x14001d9b0`
- `0x140021300`
- `0x140021410`
- `0x140021e28`
- `0x140022b60`
- `0x140025f20`
- `0x1400270f0`
- `0x140028004`
- `0x1400282f4`
- `0x14002856c`
- `0x140029160`

## callees

- `0x140001010`
- `0x140002340`

## import_xrefs

- `ntoskrnl!IoGetSiloParameters` at `0x14000102b`
- `ntoskrnl!IoGetSiloParameters` at `0x14000102b`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140001064`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140001064`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140001078`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140001078`

## pseudocode

```c
__int64 __fastcall DfscGetContainerContextFromIrp(__int64 a1, _QWORD *a2)
{
  __int64 SiloParameters; // rax
  __int64 result; // rax
  __int64 v6; // rbx
  unsigned int SiloMonitorContextSlot; // eax

  SiloParameters = IoGetSiloParameters(*(_QWORD *)(*(_QWORD *)(a1 + 184) + 48LL));
  if ( !SiloParameters || !*(_QWORD *)(SiloParameters + 8) )
  {
LABEL_2:
    result = 0;
    *a2 = 0;
    return result;
  }
  v6 = *(_QWORD *)(SiloParameters + 8);
  SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(qword_14000C7F8);
  result = PsGetPermanentSiloContext(v6, SiloMonitorContextSlot, a2);
  if ( (int)result < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_32bb75f7aa823fb724b87f7e3287c67a_Traceguids, a1, result);
    }
    goto LABEL_2;
  }
  return result;
}

```

## disassembly

```asm
0x140001010  mov     [rsp+arg_8], rsi
0x140001015  push    rdi
0x140001016  sub     rsp, 30h
0x14000101a  mov     rsi, rcx
0x14000101d  mov     rdi, rdx
0x140001020  mov     rcx, [rcx+0B8h]
0x140001027  mov     rcx, [rcx+30h]
0x14000102b  call    cs:__imp_IoGetSiloParameters
0x140001032  nop     dword ptr [rax+rax+00h]
0x140001037  test    rax, rax
0x14000103a  jnz     short loc_14000104D
0x14000103c  xor     eax, eax
0x14000103e  mov     [rdi], rax
0x140001041  mov     rsi, [rsp+38h+arg_8]
0x140001046  add     rsp, 30h
0x14000104a  pop     rdi
0x14000104b  retn
0x14000104d  cmp     qword ptr [rax+8], 0
0x140001052  jz      short loc_14000103C
0x140001054  mov     rcx, cs:qword_14000C7F8
0x14000105b  mov     [rsp+38h+arg_0], rbx
0x140001060  mov     rbx, [rax+8]
0x140001064  call    cs:__imp_PsGetSiloMonitorContextSlot
0x14000106b  nop     dword ptr [rax+rax+00h]
0x140001070  mov     r8, rdi
0x140001073  mov     rcx, rbx
0x140001076  mov     edx, eax
0x140001078  call    cs:__imp_PsGetPermanentSiloContext
0x14000107f  nop     dword ptr [rax+rax+00h]
0x140001084  mov     rbx, [rsp+38h+arg_0]
0x140001089  test    eax, eax
0x14000108b  jns     short loc_140001041
0x14000108d  mov     rcx, cs:WPP_GLOBAL_Control
0x140001094  lea     rdx, WPP_GLOBAL_Control
0x14000109b  cmp     rcx, rdx
0x14000109e  jz      short loc_14000103C
0x1400010a0  test    dword ptr [rcx+2Ch], 100000h
0x1400010a7  jz      short loc_14000103C
0x1400010a9  mov     rcx, [rcx+18h]
0x1400010ad  lea     r8, WPP_32bb75f7aa823fb724b87f7e3287c67a_Traceguids
0x1400010b4  mov     edx, 1Ah
0x1400010b9  mov     [rsp+38h+var_18], eax
0x1400010bd  mov     r9, rsi
0x1400010c0  call    WPP_SF_qD
0x1400010c5  jmp     loc_14000103C
```
