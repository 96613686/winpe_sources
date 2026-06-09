# DriverEntry

- ea: `0x14006503c`
- end: `0x140065145`
- name: `DriverEntry`
- size: `265`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400277d4`

## callees

- `0x140027f2c`
- `0x14003c980`
- `0x14003e928`
- `0x14003edb4`
- `0x14003ee80`
- `0x14006503c`
- `0x14006514c`

## import_xrefs

- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140065126`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140065126`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006506b`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14006506b`
- `ntoskrnl!PsGetHostSilo` at `0x14006505c`
- `ntoskrnl!PsGetHostSilo` at `0x14006505c`

## string_xrefs

- `0x1400650f7`: `WdfDriverCreate`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  __int64 HostSilo; // rax
  __int64 v5; // rsi
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  NTSTATUS v9; // ebx
  _DWORD v11[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v12; // [rsp+48h] [rbp-20h]
  __int64 (__fastcall *v13)(); // [rsp+50h] [rbp-18h]
  int v14; // [rsp+58h] [rbp-10h]
  int v15; // [rsp+5Ch] [rbp-Ch]
  __int64 v16; // [rsp+88h] [rbp+20h] BYREF

  v16 = 0;
  HostSilo = PsGetHostSilo();
  v5 = PsAttachSiloToCurrentThread(HostSilo);
  MsQuicLibraryLoad();
  v11[1] = 0;
  v12 = 0;
  v11[0] = 32;
  v13 = EvtDriverUnload;
  v14 = 1;
  v15 = 1128879441;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _DRIVER_OBJECT *, PUNICODE_STRING, _QWORD, _DWORD *, __int64 *))(WdfFunctions_01015 + 928))(
         WdfDriverGlobals,
         DriverObject,
         RegistryPath,
         0,
         v11,
         &v16);
  v9 = v6;
  if ( v6 < 0 )
  {
    if ( (Microsoft_QuicEnableBits & 4) != 0 )
      McTemplateU0qs_EtwWriteTransfer(v8, v7, (unsigned int)v6, "WdfDriverCreate");
    goto LABEL_6;
  }
  v9 = MsQuicPcwStartup();
  if ( v9 < 0 || (v9 = MsQuicRegisterNmrProvider(), v9 < 0) )
LABEL_6:
    MsQuicLibraryUnload();
  PsDetachSiloFromCurrentThread(v5);
  return v9;
}

```

## disassembly

```asm
0x14006503c  mov     r11, rsp
0x14006503f  mov     [r11+8], rbx
0x140065043  mov     [r11+10h], rsi
0x140065047  push    rdi
0x140065048  sub     rsp, 60h
0x14006504c  xor     eax, eax
0x14006504e  mov     rbx, rdx
0x140065051  and     [r11+20h], rax
0x140065055  mov     rdi, rcx
0x140065058  mov     [rsp+68h+var_24], eax
0x14006505c  call    cs:__imp_PsGetHostSilo
0x140065063  nop     dword ptr [rax+rax+00h]
0x140065068  mov     rcx, rax
0x14006506b  call    cs:__imp_PsAttachSiloToCurrentThread
0x140065072  nop     dword ptr [rax+rax+00h]
0x140065077  mov     rsi, rax
0x14006507a  call    MsQuicLibraryLoad
0x14006507f  mov     rcx, cs:WdfFunctions_01015
0x140065086  lea     rax, EvtDriverUnload
0x14006508d  and     [rsp+68h+var_24], 0
0x140065092  xor     r9d, r9d
0x140065095  and     [rsp+68h+var_20], 0
0x14006509b  mov     r8, rbx
0x14006509e  mov     [rsp+68h+var_28], 20h ; ' '
0x1400650a6  mov     rdx, rdi
0x1400650a9  mov     [rsp+68h+var_18], rax
0x1400650ae  mov     [rsp+68h+var_10], 1
0x1400650b6  mov     [rsp+68h+var_C], 43495551h
0x1400650be  mov     rax, [rcx+3A0h]
0x1400650c5  lea     rcx, [rsp+68h+arg_18]
0x1400650cd  mov     [rsp+68h+var_40], rcx
0x1400650d2  lea     rcx, [rsp+68h+var_28]
0x1400650d7  mov     [rsp+68h+var_48], rcx
0x1400650dc  mov     rcx, cs:WdfDriverGlobals
0x1400650e3  call    _guard_dispatch_icall
0x1400650e8  mov     ebx, eax
0x1400650ea  test    eax, eax
0x1400650ec  jns     short loc_140065108
0x1400650ee  test    cs:Microsoft_QuicEnableBits, 4
0x1400650f5  jz      short loc_14006511E
0x1400650f7  lea     r9, aWdfdrivercreat; "WdfDriverCreate"
0x1400650fe  mov     r8d, eax
0x140065101  call    McTemplateU0qs_EtwWriteTransfer
0x140065106  jmp     short loc_14006511E
0x140065108  call    MsQuicPcwStartup
0x14006510d  mov     ebx, eax
0x14006510f  test    eax, eax
0x140065111  js      short loc_14006511E
0x140065113  call    MsQuicRegisterNmrProvider
0x140065118  mov     ebx, eax
0x14006511a  test    eax, eax
0x14006511c  jns     short loc_140065123
0x14006511e  call    MsQuicLibraryUnload
0x140065123  mov     rcx, rsi
0x140065126  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14006512d  nop     dword ptr [rax+rax+00h]
0x140065132  mov     rsi, [rsp+68h+arg_8]
0x140065137  mov     eax, ebx
0x140065139  mov     rbx, [rsp+68h+arg_0]
0x14006513e  add     rsp, 60h
0x140065142  pop     rdi
0x140065143  retn
```
