# PmWmiFunctionControl(_DEVICE_OBJECT *,_IRP *,ulong,_WMIENABLEDISABLECONTROL,uchar)

- ea: `0x1400203c0`
- end: `0x140020444`
- name: `?PmWmiFunctionControl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@KW4_WMIENABLEDISABLECONTROL@@E@Z`
- size: `132`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, unsigned int@<r8d>, enum _WMIENABLEDISABLECONTROL@<r9d>, unsigned __int8)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001c2c0`
- `0x1400203c0`
- `0x140024ac0`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x140020427`
- `WMILIB!WmiCompleteRequest` at `0x140020427`

## pseudocode

```c
NTSTATUS __fastcall PmWmiFunctionControl(
        PDEVICE_OBJECT DeviceObject,
        PIRP Irp,
        int a3,
        enum _WMIENABLEDISABLECONTROL a4,
        unsigned __int8 a5)
{
  NTSTATUS v7; // ebx
  char *DeviceExtension; // rax
  struct _PERF_COUNTER_CONTEXT **v9; // rcx

  if ( a3 || (DeviceExtension = (char *)DeviceObject->DeviceExtension, *((_DWORD *)DeviceExtension + 42) == -1) )
  {
    v7 = -1073741163;
  }
  else
  {
    v7 = 0;
    if ( a4 == WmiDataBlockControl )
    {
      v9 = (struct _PERF_COUNTER_CONTEXT **)(DeviceExtension + 720);
      if ( a5 )
        v7 = PmWmiCounterEnable(v9);
      else
        PmWmiCounterDisable(v9, 0, 0);
    }
  }
  return WmiCompleteRequest(DeviceObject, Irp, v7, 0, 0);
}

```

## disassembly

```asm
0x1400203c0  mov     [rsp+arg_0], rbx
0x1400203c5  mov     [rsp+arg_8], rsi
0x1400203ca  push    rdi
0x1400203cb  sub     rsp, 30h
0x1400203cf  mov     rsi, rdx
0x1400203d2  mov     rdi, rcx
0x1400203d5  test    r8d, r8d
0x1400203d8  jz      short loc_1400203E1
0x1400203da  mov     ebx, 0C0000295h
0x1400203df  jmp     short loc_140020416
0x1400203e1  mov     rax, [rcx+40h]
0x1400203e5  cmp     dword ptr [rax+0A8h], 0FFFFFFFFh
0x1400203ec  jz      short loc_1400203DA
0x1400203ee  xor     ebx, ebx
0x1400203f0  cmp     r9d, 1
0x1400203f4  jnz     short loc_140020416
0x1400203f6  lea     rcx, [rax+2D0h]; struct _PERF_COUNTER_CONTEXT **
0x1400203fd  cmp     [rsp+38h+arg_20], bl
0x140020401  jz      short loc_14002040C
0x140020403  call    ?PmWmiCounterEnable@@YAJPEAPEAU_PERF_COUNTER_CONTEXT@@@Z; PmWmiCounterEnable(_PERF_COUNTER_CONTEXT * *)
0x140020408  mov     ebx, eax
0x14002040a  jmp     short loc_140020416
0x14002040c  xor     r8d, r8d; unsigned __int8
0x14002040f  xor     edx, edx; unsigned __int8
0x140020411  call    ?PmWmiCounterDisable@@YAEPEAPEAU_PERF_COUNTER_CONTEXT@@EE@Z; PmWmiCounterDisable(_PERF_COUNTER_CONTEXT * *,uchar,uchar)
0x140020416  xor     r9d, r9d; BufferUsed
0x140020419  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x14002041e  mov     r8d, ebx; Status
0x140020421  mov     rdx, rsi; Irp
0x140020424  mov     rcx, rdi; DeviceObject
0x140020427  call    cs:__imp_WmiCompleteRequest
0x14002042e  nop     dword ptr [rax+rax+00h]
0x140020433  mov     rbx, [rsp+38h+arg_0]
0x140020438  mov     rsi, [rsp+38h+arg_8]
0x14002043d  add     rsp, 30h
0x140020441  pop     rdi
0x140020442  retn
```
