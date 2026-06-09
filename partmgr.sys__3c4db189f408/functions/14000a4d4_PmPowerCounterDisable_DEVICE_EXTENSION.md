# PmPowerCounterDisable(_DEVICE_EXTENSION *)

- ea: `0x14000a4d4`
- end: `0x14000a52a`
- name: `?PmPowerCounterDisable@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `86`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000743c`

## callees

- `0x14000a4d4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000a4fe`
- `ntoskrnl!ObfDereferenceObject` at `0x14000a4fe`

## pseudocode

```c
void __fastcall PmPowerCounterDisable(struct _DEVICE_EXTENSION *a1)
{
  __int64 v1; // rax
  void *v3; // rcx

  v1 = *((_QWORD *)a1 + 143);
  if ( v1 && *((_BYTE *)a1 + 1152) )
  {
    v3 = *(void **)(v1 + 208);
    if ( v3 )
    {
      ObfDereferenceObject(v3);
      *(_QWORD *)(*((_QWORD *)a1 + 143) + 208LL) = 0;
    }
    *((_BYTE *)a1 + 1152) = 0;
  }
}

```

## disassembly

```asm
0x14000a4d4  push    rbx
0x14000a4d6  sub     rsp, 20h
0x14000a4da  mov     rax, [rcx+478h]
0x14000a4e1  mov     rbx, rcx
0x14000a4e4  test    rax, rax
0x14000a4e7  jz      short loc_14000A523
0x14000a4e9  cmp     byte ptr [rcx+480h], 0
0x14000a4f0  jz      short loc_14000A523
0x14000a4f2  mov     rcx, [rax+0D0h]; Object
0x14000a4f9  test    rcx, rcx
0x14000a4fc  jz      short loc_14000A51C
0x14000a4fe  call    cs:__imp_ObfDereferenceObject
0x14000a505  nop     dword ptr [rax+rax+00h]
0x14000a50a  mov     rax, [rbx+478h]
0x14000a511  mov     qword ptr [rax+0D0h], 0
0x14000a51c  mov     byte ptr [rbx+480h], 0
0x14000a523  add     rsp, 20h
0x14000a527  pop     rbx
0x14000a528  retn
```
