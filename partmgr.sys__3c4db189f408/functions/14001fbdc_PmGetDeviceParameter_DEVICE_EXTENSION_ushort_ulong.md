# PmGetDeviceParameter(_DEVICE_EXTENSION *,ushort *,ulong *)

- ea: `0x14001fbdc`
- end: `0x14001fcb3`
- name: `?PmGetDeviceParameter@@YAJPEAU_DEVICE_EXTENSION@@PEAGPEAK@Z`
- size: `215`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14001cc58`

## callees

- `0x140011440`
- `0x14001fbdc`
- `0x140023540`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14001fc79`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14001fc79`
- `ntoskrnl!ZwClose` at `0x14001fc8f`
- `ntoskrnl!ZwClose` at `0x14001fc8f`

## pseudocode

```c
__int64 __fastcall PmGetDeviceParameter(struct _DEVICE_EXTENSION *a1, unsigned __int16 *a2, unsigned int *a3)
{
  NTSTATUS v4; // eax
  HANDLE v5; // rbx
  unsigned int RegistryValues; // edi
  _QWORD v8[14]; // [rsp+30h] [rbp-78h] BYREF
  HANDLE Handle; // [rsp+B8h] [rbp+10h] BYREF

  Handle = 0;
  memset(v8, 0, sizeof(v8));
  v4 = PmOpenDeviceParameter(a1, &Handle);
  v5 = Handle;
  RegistryValues = v4;
  if ( v4 >= 0 )
  {
    v8[0] = 0;
    v8[2] = ATTRIBUTES;
    LODWORD(v8[1]) = 292;
    v8[3] = a3;
    LODWORD(v8[4]) = 0x4000000;
    RegistryValues = RtlQueryRegistryValuesEx(0x40000000, Handle, v8, 0, 0);
  }
  if ( v5 )
    ZwClose(v5);
  return RegistryValues;
}

```

## disassembly

```asm
0x14001fbdc  mov     rax, rsp
0x14001fbdf  mov     [rax+8], rbx
0x14001fbe3  mov     [rax+18h], rsi
0x14001fbe7  mov     [rax+10h], rdx
0x14001fbeb  push    rdi
0x14001fbec  sub     rsp, 0A0h
0x14001fbf3  xor     edx, edx; Val
0x14001fbf5  mov     qword ptr [rax+10h], 0
0x14001fbfd  mov     rsi, r8
0x14001fc00  mov     qword ptr [rax-78h], 0
0x14001fc08  mov     rbx, rcx
0x14001fc0b  lea     rcx, [rax-70h]; void *
0x14001fc0f  lea     r8d, [rdx+68h]; Size
0x14001fc13  call    memset
0x14001fc18  lea     rdx, [rsp+0A8h+Handle]; void **
0x14001fc20  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14001fc23  call    ?PmOpenDeviceParameter@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAX@Z; PmOpenDeviceParameter(_DEVICE_EXTENSION *,void * *)
0x14001fc28  mov     rbx, [rsp+0A8h+Handle]
0x14001fc30  mov     edi, eax
0x14001fc32  test    eax, eax
0x14001fc34  js      short loc_14001FC87
0x14001fc36  lea     rax, ?ATTRIBUTES@@3PAGA; "Attributes"
0x14001fc3d  mov     [rsp+0A8h+var_78], 0
0x14001fc46  xor     r9d, r9d
0x14001fc49  mov     [rsp+0A8h+var_68], rax
0x14001fc4e  lea     r8, [rsp+0A8h+var_78]
0x14001fc53  mov     [rsp+0A8h+var_70], 124h
0x14001fc5b  mov     rdx, rbx
0x14001fc5e  mov     [rsp+0A8h+var_60], rsi
0x14001fc63  mov     ecx, 40000000h
0x14001fc68  mov     [rsp+0A8h+var_58], 4000000h
0x14001fc70  mov     [rsp+0A8h+var_88], 0
0x14001fc79  call    cs:__imp_RtlQueryRegistryValuesEx
0x14001fc80  nop     dword ptr [rax+rax+00h]
0x14001fc85  mov     edi, eax
0x14001fc87  test    rbx, rbx
0x14001fc8a  jz      short loc_14001FC9B
0x14001fc8c  mov     rcx, rbx; Handle
0x14001fc8f  call    cs:__imp_ZwClose
0x14001fc96  nop     dword ptr [rax+rax+00h]
0x14001fc9b  lea     r11, [rsp+0A8h+var_8]
0x14001fca3  mov     eax, edi
0x14001fca5  mov     rbx, [r11+10h]
0x14001fca9  mov     rsi, [r11+20h]
0x14001fcad  mov     rsp, r11
0x14001fcb0  pop     rdi
0x14001fcb1  retn
```
