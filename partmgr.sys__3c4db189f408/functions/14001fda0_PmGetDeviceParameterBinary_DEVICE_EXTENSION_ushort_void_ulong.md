# PmGetDeviceParameterBinary(_DEVICE_EXTENSION *,ushort *,void * *,ulong *)

- ea: `0x14001fda0`
- end: `0x14001fe89`
- name: `?PmGetDeviceParameterBinary@@YAJPEAU_DEVICE_EXTENSION@@PEAGPEAPEAXPEAK@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, unsigned __int16 *, void **, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000aa60`
- `0x14000ca1c`
- `0x14000da9c`

## callees

- `0x140011440`
- `0x14001fda0`
- `0x140023540`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14001fe4c`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14001fe4c`
- `ntoskrnl!ZwClose` at `0x14001fe62`
- `ntoskrnl!ZwClose` at `0x14001fe62`

## pseudocode

```c
__int64 __fastcall PmGetDeviceParameterBinary(
        struct _DEVICE_EXTENSION *a1,
        unsigned __int16 *a2,
        void **a3,
        unsigned int *a4)
{
  NTSTATUS v7; // eax
  HANDLE v8; // rbx
  unsigned int RegistryValues; // edi
  _QWORD v11[14]; // [rsp+30h] [rbp-88h] BYREF
  HANDLE Handle; // [rsp+D0h] [rbp+18h] BYREF

  Handle = 0;
  memset(v11, 0, sizeof(v11));
  *a3 = 0;
  *a4 = 0;
  v7 = PmOpenDeviceParameter(a1, &Handle);
  v8 = Handle;
  RegistryValues = v7;
  if ( v7 >= 0 )
  {
    LODWORD(v11[1]) = 260;
    v11[0] = PmGetDeviceParameterBinaryCallback;
    v11[2] = a2;
    v11[3] = a3;
    LODWORD(v11[4]) = 50331648;
    RegistryValues = RtlQueryRegistryValuesEx(0x40000000, Handle, v11, a4, 0);
  }
  if ( v8 )
    ZwClose(v8);
  return RegistryValues;
}

```

## disassembly

```asm
0x14001fda0  mov     rax, rsp
0x14001fda3  mov     [rax+8], rbx
0x14001fda7  mov     [rax+10h], rbp
0x14001fdab  push    rsi
0x14001fdac  push    rdi
0x14001fdad  push    r14
0x14001fdaf  sub     rsp, 0A0h
0x14001fdb6  mov     rbp, rdx
0x14001fdb9  mov     qword ptr [rax+18h], 0
0x14001fdc1  xor     edx, edx; Val
0x14001fdc3  mov     [rsp+0B8h+var_88], 0
0x14001fdcc  mov     r14, r8
0x14001fdcf  mov     rbx, rcx
0x14001fdd2  lea     rcx, [rax-80h]; void *
0x14001fdd6  mov     rsi, r9
0x14001fdd9  lea     r8d, [rdx+68h]; Size
0x14001fddd  call    memset
0x14001fde2  mov     qword ptr [r14], 0
0x14001fde9  lea     rdx, [rsp+0B8h+Handle]; void **
0x14001fdf1  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14001fdf4  mov     dword ptr [rsi], 0
0x14001fdfa  call    ?PmOpenDeviceParameter@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAX@Z; PmOpenDeviceParameter(_DEVICE_EXTENSION *,void * *)
0x14001fdff  mov     rbx, [rsp+0B8h+Handle]
0x14001fe07  mov     edi, eax
0x14001fe09  test    eax, eax
0x14001fe0b  js      short loc_14001FE5A
0x14001fe0d  lea     rax, ?PmGetDeviceParameterBinaryCallback@@YAJPEAGKPEAXK11@Z; PmGetDeviceParameterBinaryCallback(ushort *,ulong,void *,ulong,void *,void *)
0x14001fe14  mov     [rsp+0B8h+var_80], 104h
0x14001fe1c  mov     r9, rsi
0x14001fe1f  mov     [rsp+0B8h+var_88], rax
0x14001fe24  lea     r8, [rsp+0B8h+var_88]
0x14001fe29  mov     [rsp+0B8h+var_78], rbp
0x14001fe2e  mov     rdx, rbx
0x14001fe31  mov     [rsp+0B8h+var_70], r14
0x14001fe36  mov     ecx, 40000000h
0x14001fe3b  mov     [rsp+0B8h+var_68], 3000000h
0x14001fe43  mov     [rsp+0B8h+var_98], 0
0x14001fe4c  call    cs:__imp_RtlQueryRegistryValuesEx
0x14001fe53  nop     dword ptr [rax+rax+00h]
0x14001fe58  mov     edi, eax
0x14001fe5a  test    rbx, rbx
0x14001fe5d  jz      short loc_14001FE6E
0x14001fe5f  mov     rcx, rbx; Handle
0x14001fe62  call    cs:__imp_ZwClose
0x14001fe69  nop     dword ptr [rax+rax+00h]
0x14001fe6e  lea     r11, [rsp+0B8h+var_18]
0x14001fe76  mov     eax, edi
0x14001fe78  mov     rbx, [r11+20h]
0x14001fe7c  mov     rbp, [r11+28h]
0x14001fe80  mov     rsp, r11
0x14001fe83  pop     r14
0x14001fe85  pop     rdi
0x14001fe86  pop     rsi
0x14001fe87  retn
```
