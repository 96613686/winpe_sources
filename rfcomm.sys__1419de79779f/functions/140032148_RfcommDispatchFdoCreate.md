# RfcommDispatchFdoCreate

- ea: `0x140032148`
- end: `0x1400322b0`
- name: `RfcommDispatchFdoCreate`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000256c`

## callees

- `0x140003bf4`
- `0x140032148`
- `0x1400328e8`
- `0x140033edc`
- `0x140034048`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x14003215d`
- `ntoskrnl!IoGetRequestorProcess` at `0x14003215d`

## pseudocode

```c
__int64 __fastcall RfcommDispatchFdoCreate(__int64 a1, IRP *a2)
{
  struct _KPROCESS *RequestorProcess; // rax
  int v4; // edx
  unsigned int IsAppContainer; // ebx
  int v6; // r9d
  int v7; // r9d
  char v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = 1;
  RequestorProcess = IoGetRequestorProcess(a2);
  IsAppContainer = QueryIsAppContainer(RequestorProcess, (bool *)&v9);
  if ( (IsAppContainer & 0x80000000) == 0 )
  {
    if ( v9 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v6 = 42;
LABEL_15:
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v4,
          19,
          v6,
          (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
        return (unsigned int)-1073741790;
      }
      return (unsigned int)-1073741790;
    }
    if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 96LL) + 49LL) )
    {
      if ( !IsCallingProcess(`IsCallingProcessBthservEx'::`2'::s_sdBthserv, 1)
        && !IsCallingProcess(`IsCallingProcessProximityService'::`2'::s_sdProximitySvc, 1)
        && !IsCallingProcess(`IsCallingProcessShellHwDetectionService'::`2'::s_sdShellHwSvc, 1)
        && !IsCallingProcess(`IsCallingProcessBluetoothAudioService'::`2'::s_sdBthAvctpSvc, 1)
        && !RfcommIsCallingProcessRuntimeBroker(a1) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v6 = 45;
          goto LABEL_15;
        }
        return (unsigned int)-1073741790;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return IsAppContainer;
      v7 = 44;
LABEL_19:
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        19,
        v7,
        (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
      return IsAppContainer;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = 43;
      goto LABEL_19;
    }
  }
  return IsAppContainer;
}

```

## disassembly

```asm
0x140032148  mov     [rsp+arg_0], rbx
0x14003214d  push    rdi
0x14003214e  sub     rsp, 30h
0x140032152  mov     rdi, rcx
0x140032155  mov     [rsp+38h+arg_10], 1
0x14003215a  mov     rcx, rdx; Irp
0x14003215d  call    cs:__imp_IoGetRequestorProcess
0x140032164  nop     dword ptr [rax+rax+00h]
0x140032169  mov     rcx, rax
0x14003216c  lea     rdx, [rsp+38h+arg_10]
0x140032171  call    QueryIsAppContainer
0x140032176  mov     ebx, eax
0x140032178  test    eax, eax
0x14003217a  js      loc_1400322A2
0x140032180  cmp     [rsp+38h+arg_10], 0
0x140032185  jz      short loc_1400321A6
0x140032187  lea     rax, WPP_RECORDER_INITIALIZED
0x14003218e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140032195  jz      loc_140032263
0x14003219b  mov     r9d, 2Ah ; '*'
0x1400321a1  jmp     loc_140032241
0x1400321a6  mov     rax, [rdi+40h]
0x1400321aa  mov     rcx, [rax+60h]
0x1400321ae  cmp     byte ptr [rcx+31h], 0
0x1400321b2  jz      short loc_1400321D3
0x1400321b4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400321bb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400321c2  jz      loc_1400322A2
0x1400321c8  mov     r9d, 2Bh ; '+'
0x1400321ce  jmp     loc_140032280
0x1400321d3  mov     dl, 1
0x1400321d5  lea     rcx, ?s_sdBthserv@?1??IsCallingProcessBthservEx@@9@9; SecurityDescriptor
0x1400321dc  call    IsCallingProcess
0x1400321e1  test    al, al
0x1400321e3  jnz     loc_14003226A
0x1400321e9  mov     dl, 1
0x1400321eb  lea     rcx, ?s_sdProximitySvc@?1??IsCallingProcessProximityService@@9@9; SecurityDescriptor
0x1400321f2  call    IsCallingProcess
0x1400321f7  test    al, al
0x1400321f9  jnz     short loc_14003226A
0x1400321fb  mov     dl, 1
0x1400321fd  lea     rcx, ?s_sdShellHwSvc@?1??IsCallingProcessShellHwDetectionService@@9@9; SecurityDescriptor
0x140032204  call    IsCallingProcess
0x140032209  test    al, al
0x14003220b  jnz     short loc_14003226A
0x14003220d  mov     dl, 1
0x14003220f  lea     rcx, ?s_sdBthAvctpSvc@?1??IsCallingProcessBluetoothAudioService@@9@9; SecurityDescriptor
0x140032216  call    IsCallingProcess
0x14003221b  test    al, al
0x14003221d  jnz     short loc_14003226A
0x14003221f  mov     rcx, rdi
0x140032222  call    RfcommIsCallingProcessRuntimeBroker
0x140032227  test    al, al
0x140032229  jnz     short loc_14003226A
0x14003222b  lea     rax, WPP_RECORDER_INITIALIZED
0x140032232  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140032239  jz      short loc_140032263
0x14003223b  mov     r9d, 2Dh ; '-'
0x140032241  mov     rcx, cs:WPP_GLOBAL_Control
0x140032248  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x14003224f  mov     r8d, 13h
0x140032255  mov     [rsp+38h+var_18], rax
0x14003225a  mov     rcx, [rcx+40h]
0x14003225e  call    WPP_RECORDER_SF_
0x140032263  mov     ebx, 0C0000022h
0x140032268  jmp     short loc_1400322A2
0x14003226a  lea     rax, WPP_RECORDER_INITIALIZED
0x140032271  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140032278  jz      short loc_1400322A2
0x14003227a  mov     r9d, 2Ch ; ','
0x140032280  mov     rcx, cs:WPP_GLOBAL_Control
0x140032287  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x14003228e  mov     r8d, 13h
0x140032294  mov     [rsp+38h+var_18], rax
0x140032299  mov     rcx, [rcx+40h]
0x14003229d  call    WPP_RECORDER_SF_
0x1400322a2  mov     eax, ebx
0x1400322a4  mov     rbx, [rsp+38h+arg_0]
0x1400322a9  add     rsp, 30h
0x1400322ad  pop     rdi
0x1400322ae  retn
```
