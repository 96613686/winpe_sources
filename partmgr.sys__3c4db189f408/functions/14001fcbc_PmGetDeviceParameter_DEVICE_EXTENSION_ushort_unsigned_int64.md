# PmGetDeviceParameter(_DEVICE_EXTENSION *,ushort *,unsigned __int64 *)

- ea: `0x14001fcbc`
- end: `0x14001fd9a`
- name: `?PmGetDeviceParameter@@YAJPEAU_DEVICE_EXTENSION@@PEAGPEA_K@Z`
- size: `222`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14001cc58`

## callees

- `0x140011440`
- `0x14001fcbc`
- `0x140023540`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14001fd60`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14001fd60`
- `ntoskrnl!ZwClose` at `0x14001fd76`
- `ntoskrnl!ZwClose` at `0x14001fd76`

## pseudocode

```c
__int64 __fastcall PmGetDeviceParameter(struct _DEVICE_EXTENSION *a1, unsigned __int16 *a2, unsigned __int64 *a3)
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
    *a3 = -8;
    v8[2] = ATTRIBUTES;
    v8[0] = 0;
    LODWORD(v8[1]) = 292;
    v8[3] = a3;
    LODWORD(v8[4]) = 184549376;
    RegistryValues = RtlQueryRegistryValuesEx(0x40000000, v5, v8, 0, 0);
  }
  if ( v5 )
    ZwClose(v5);
  return RegistryValues;
}

```

## disassembly

```asm
0x14001fcbc  mov     rax, rsp
0x14001fcbf  mov     [rax+8], rbx
0x14001fcc3  mov     [rax+18h], rsi
0x14001fcc7  mov     [rax+10h], rdx
0x14001fccb  push    rdi
0x14001fccc  sub     rsp, 0A0h
0x14001fcd3  xor     edx, edx; Val
0x14001fcd5  mov     qword ptr [rax+10h], 0
0x14001fcdd  mov     rsi, r8
0x14001fce0  mov     qword ptr [rax-78h], 0
0x14001fce8  mov     rbx, rcx
0x14001fceb  lea     rcx, [rax-70h]; void *
0x14001fcef  lea     r8d, [rdx+68h]; Size
0x14001fcf3  call    memset
0x14001fcf8  lea     rdx, [rsp+0A8h+Handle]; void **
0x14001fd00  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14001fd03  call    ?PmOpenDeviceParameter@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAX@Z; PmOpenDeviceParameter(_DEVICE_EXTENSION *,void * *)
0x14001fd08  mov     rbx, [rsp+0A8h+Handle]
0x14001fd10  mov     edi, eax
0x14001fd12  test    eax, eax
0x14001fd14  js      short loc_14001FD6E
0x14001fd16  lea     rax, ?ATTRIBUTES@@3PAGA; "Attributes"
0x14001fd1d  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFF8h
0x14001fd24  xor     r9d, r9d
0x14001fd27  mov     [rsp+0A8h+var_68], rax
0x14001fd2c  lea     r8, [rsp+0A8h+var_78]
0x14001fd31  mov     [rsp+0A8h+var_78], 0
0x14001fd3a  mov     rdx, rbx
0x14001fd3d  mov     [rsp+0A8h+var_70], 124h
0x14001fd45  mov     ecx, 40000000h
0x14001fd4a  mov     [rsp+0A8h+var_60], rsi
0x14001fd4f  mov     [rsp+0A8h+var_58], 0B000000h
0x14001fd57  mov     [rsp+0A8h+var_88], 0
0x14001fd60  call    cs:__imp_RtlQueryRegistryValuesEx
0x14001fd67  nop     dword ptr [rax+rax+00h]
0x14001fd6c  mov     edi, eax
0x14001fd6e  test    rbx, rbx
0x14001fd71  jz      short loc_14001FD82
0x14001fd73  mov     rcx, rbx; Handle
0x14001fd76  call    cs:__imp_ZwClose
0x14001fd7d  nop     dword ptr [rax+rax+00h]
0x14001fd82  lea     r11, [rsp+0A8h+var_8]
0x14001fd8a  mov     eax, edi
0x14001fd8c  mov     rbx, [r11+10h]
0x14001fd90  mov     rsi, [r11+20h]
0x14001fd94  mov     rsp, r11
0x14001fd97  pop     rdi
0x14001fd98  retn
```
