# PmIoctlPerformance(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140024fd4`
- end: `0x1400250e3`
- name: `?PmIoctlPerformance@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400068b0`

## callees

- `0x140011440`
- `0x14001c2c0`
- `0x140024fd4`
- `0x1400250f0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140025076`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140025076`

## pseudocode

```c
__int64 __fastcall PmIoctlPerformance(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  int RegistryValues; // ebx
  PVOID DeviceExtension; // rbp
  struct _DISK_PERFORMANCE *MasterIrp; // r14
  _QWORD v7[14]; // [rsp+30h] [rbp-88h] BYREF
  int v8; // [rsp+C0h] [rbp+8h] BYREF

  v8 = 0;
  if ( a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length >= 0x58 )
  {
    DeviceExtension = a1->DeviceExtension;
    RegistryValues = 0;
    MasterIrp = (struct _DISK_PERFORMANCE *)a2->AssociatedIrp.MasterIrp;
    if ( *(_DWORD *)(*((_QWORD *)DeviceExtension + 90) + 56LL) )
      goto LABEL_7;
    memset(v7, 0, sizeof(v7));
    v7[2] = L"EnableCounterForIoctl";
    LODWORD(v7[1]) = 288;
    v7[3] = &v8;
    LODWORD(v7[4]) = 0x4000000;
    RegistryValues = RtlQueryRegistryValuesEx(1, off_140017050, v7, 0, 0);
    if ( RegistryValues >= 0 )
    {
      if ( v8 != 1 )
        return (unsigned int)-1073741808;
      RegistryValues = PmWmiCounterEnable((struct _PERF_COUNTER_CONTEXT **)DeviceExtension + 90);
      if ( RegistryValues >= 0 )
      {
LABEL_7:
        PmWmiCounterQuery(
          *((struct _PERF_COUNTER_CONTEXT **)DeviceExtension + 90),
          MasterIrp,
          L"Partmgr ",
          *((_DWORD *)DeviceExtension + 42));
        a2->IoStatus.Information = 88;
      }
    }
  }
  else
  {
    return (unsigned int)-1073741789;
  }
  return (unsigned int)RegistryValues;
}

```

## disassembly

```asm
0x140024fd4  mov     rax, rsp
0x140024fd7  mov     [rax+10h], rbx
0x140024fdb  mov     [rax+18h], rbp
0x140024fdf  push    rsi
0x140024fe0  push    rdi
0x140024fe1  push    r14
0x140024fe3  sub     rsp, 0A0h
0x140024fea  mov     dword ptr [rax+8], 0
0x140024ff1  mov     rdi, rdx
0x140024ff4  mov     rax, [rdx+0B8h]
0x140024ffb  cmp     dword ptr [rax+8], 58h ; 'X'
0x140024fff  jnb     short loc_14002500B
0x140025001  mov     ebx, 0C0000023h
0x140025006  jmp     loc_1400250C1
0x14002500b  mov     rbp, [rcx+40h]
0x14002500f  xor     ebx, ebx
0x140025011  mov     r14, [rdx+18h]
0x140025015  lea     rsi, [rbp+2D0h]
0x14002501c  mov     rax, [rsi]
0x14002501f  mov     ecx, [rax+38h]
0x140025022  test    ecx, ecx
0x140025024  jnz     short loc_1400250A0
0x140025026  xor     edx, edx; Val
0x140025028  lea     r8d, [rbx+70h]; Size
0x14002502c  lea     rcx, [rsp+0B8h+var_88]; void *
0x140025031  call    memset
0x140025036  mov     rdx, cs:off_140017050; "Partmgr"
0x14002503d  lea     rax, aEnablecounterf; "EnableCounterForIoctl"
0x140025044  mov     [rsp+0B8h+var_78], rax
0x140025049  lea     r8, [rsp+0B8h+var_88]
0x14002504e  lea     rax, [rsp+0B8h+arg_0]
0x140025056  mov     [rsp+0B8h+var_80], 120h
0x14002505e  xor     r9d, r9d
0x140025061  mov     [rsp+0B8h+var_70], rax
0x140025066  lea     ecx, [rbx+1]
0x140025069  mov     [rsp+0B8h+var_68], 4000000h
0x140025071  mov     [rsp+0B8h+var_98], rbx
0x140025076  call    cs:__imp_RtlQueryRegistryValuesEx
0x14002507d  nop     dword ptr [rax+rax+00h]
0x140025082  mov     ebx, eax
0x140025084  test    eax, eax
0x140025086  js      short loc_1400250C1
0x140025088  cmp     [rsp+0B8h+arg_0], 1
0x140025090  jnz     short loc_1400250DC
0x140025092  mov     rcx, rsi; struct _PERF_COUNTER_CONTEXT **
0x140025095  call    ?PmWmiCounterEnable@@YAJPEAPEAU_PERF_COUNTER_CONTEXT@@@Z; PmWmiCounterEnable(_PERF_COUNTER_CONTEXT * *)
0x14002509a  mov     ebx, eax
0x14002509c  test    eax, eax
0x14002509e  js      short loc_1400250C1
0x1400250a0  mov     r9d, [rbp+0A8h]; unsigned int
0x1400250a7  lea     r8, aPartmgr_0; "Partmgr "
0x1400250ae  mov     rcx, [rsi]; struct _PERF_COUNTER_CONTEXT *
0x1400250b1  mov     rdx, r14; struct _DISK_PERFORMANCE *
0x1400250b4  call    ?PmWmiCounterQuery@@YAXPEAU_PERF_COUNTER_CONTEXT@@PEAU_DISK_PERFORMANCE@@PEAGK@Z; PmWmiCounterQuery(_PERF_COUNTER_CONTEXT *,_DISK_PERFORMANCE *,ushort *,ulong)
0x1400250b9  mov     qword ptr [rdi+38h], 58h ; 'X'
0x1400250c1  lea     r11, [rsp+0B8h+var_18]
0x1400250c9  mov     eax, ebx
0x1400250cb  mov     rbx, [r11+28h]
0x1400250cf  mov     rbp, [r11+30h]
0x1400250d3  mov     rsp, r11
0x1400250d6  pop     r14
0x1400250d8  pop     rdi
0x1400250d9  pop     rsi
0x1400250da  retn
0x1400250dc  mov     ebx, 0C0000010h
0x1400250e1  jmp     short loc_1400250C1
```
