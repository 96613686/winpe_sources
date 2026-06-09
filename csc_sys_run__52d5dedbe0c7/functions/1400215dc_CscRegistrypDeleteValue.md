# CscRegistrypDeleteValue

- ea: `0x1400215dc`
- end: `0x14002163e`
- name: `CscRegistrypDeleteValue`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14002166c`
- `0x1400525ac`

## callees

- `0x14001a69c`
- `0x1400215dc`

## import_xrefs

- `ntoskrnl!ZwDeleteValueKey` at `0x1400215e9`
- `ntoskrnl!ZwDeleteValueKey` at `0x1400215e9`

## pseudocode

```c
__int64 __fastcall CscRegistrypDeleteValue(void *a1, struct _UNICODE_STRING *a2)
{
  int v2; // edi
  unsigned int v3; // ebx

  v2 = (int)a2;
  v3 = ZwDeleteValueKey(a1, a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_ZD(
      WPP_GLOBAL_Control->AttachedDevice,
      18,
      (unsigned int)WPP_d79ea00412a8325f3b090053ac99afd3_Traceguids,
      v2,
      v3);
  return v3;
}

```

## disassembly

```asm
0x1400215dc  mov     [rsp+arg_0], rbx
0x1400215e1  push    rdi
0x1400215e2  sub     rsp, 30h
0x1400215e6  mov     rdi, rdx
0x1400215e9  call    cs:__imp_ZwDeleteValueKey
0x1400215f0  nop     dword ptr [rax+rax+00h]
0x1400215f5  mov     ebx, eax
0x1400215f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400215fe  lea     rax, WPP_GLOBAL_Control
0x140021605  cmp     rcx, rax
0x140021608  jz      short loc_140021630
0x14002160a  mov     r8d, [rcx+2Ch]
0x14002160e  test    r8b, 40h
0x140021612  jz      short loc_140021630
0x140021614  mov     rcx, [rcx+18h]
0x140021618  lea     r8, WPP_d79ea00412a8325f3b090053ac99afd3_Traceguids
0x14002161f  mov     edx, 12h
0x140021624  mov     [rsp+38h+var_18], ebx
0x140021628  mov     r9, rdi
0x14002162b  call    WPP_SF_ZD
0x140021630  mov     eax, ebx
0x140021632  mov     rbx, [rsp+38h+arg_0]
0x140021637  add     rsp, 30h
0x14002163b  pop     rdi
0x14002163c  retn
```
